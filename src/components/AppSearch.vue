<template>
    <div class="container d-flex justify-content-center p-4">
        <form class="row row-cols-lg-auto g-3 align-items-center">
            <div class="col-12">
                <label>Search name</label>
                <input type="text" class="form-control" placeholder="Search name">
            </div>

            <div class="col-12">
                <label>Search status</label>
                <select class="form-select" id="searchStatus">
                    <option>Choose...</option>
                    <option>Status</option>
                </select>
            </div>

            <div class="col-12">
                <button type="submit" class="btn btn-primary">Search</button>
            </div>

            <div class="col-12">
                <button type="reset" class="btn btn-primary">Reset</button>
            </div>
        </form>
    </div>

</template>

<script>
export default {
    name: 'AppSearch',
}
</script>

<style lang="scss" scoped>
.container {
    color: white;
}
</style>
