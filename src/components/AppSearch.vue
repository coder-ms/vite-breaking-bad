<template>
    <div class="container">
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
    display: flex;
    color: white;
    justify-content: center;
    align-items: center;
    padding-bottom: 10px;

    form {
        justify-content: space-between;

        .col-12 {
            button {
                margin-top: 15px;
            }
        }
    }
}
</style>
