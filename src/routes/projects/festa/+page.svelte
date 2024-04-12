<script lang="ts">
	import ProjectFeature from '$lib/components/projects/ProjectFeature.svelte';

	let salesDescr = "Through the ticket sales page, staff are able to sell tickets to attendees by scanning the QR code on the ticket and entering the attendee\'s full name";
	let checkDescr = "The check-in page allow staff to validate the tickets by scanning the QR code on the ticket and checking the attendee\'s full name.\n	This is the most important feature because it allows the staff to quickly clear the queue that is created at the entrance";
	let dashDescr = "The dashboard displays the number of non-sold tickets, sold tickets, and checked-in tickets in real-time. In addition, it displays charts about the sales and check-in progress.\nFeature achieved through the realtime update of the Firebase Firestore and ECharts";
</script>

<div class="px-5 mt-12 mb-20 w-full items-center flex flex-col gap-12 text-primary-foreground">
	<p class="text-xl"><span class="text-secondary-foreground font-medium text-2xl">Goal:</span> Speed up <b>sales</b> and <b>validation</b> of the event tickets</p>
	<div class="flex flex-col gap-10">
		<ProjectFeature title='Sales' description={salesDescr} imageSrc="/projects/festa/sell.png" />
		<ProjectFeature title='Check-in' description={checkDescr} inverted imageSrc="/projects/festa/checkin.png" />
		<ProjectFeature title='Realtime Dashboard' description={dashDescr} imageSrc="/projects/festa/dashboard.png"  />
	</div>
</div>