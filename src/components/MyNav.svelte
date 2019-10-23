<script>
    import TopAppBar, {Row, Section, Title} from '@smui/top-app-bar';
    import IconButton from '@smui/icon-button';
    let prominent = false;
    let dense = false;
    let secondaryColor = false;
    export let appName = '';
</script>


<TopAppBar variant="fixed" {prominent} {dense} color={secondaryColor?'secondary':'primary'}>
    <Row>
        <Section>
            <IconButton class="material-icons">menu</IconButton>
            <Title>{appName}</Title>
        </Section>
        <Section align="end" toolbar>
            <IconButton class="material-icons" aria-label="Download">file_download</IconButton>
            <IconButton class="material-icons" aria-label="Print this page">print</IconButton>
            <IconButton class="material-icons" aria-label="Bookmark this page">bookmark</IconButton>
        </Section>
    </Row>
</TopAppBar>

