<template>
    <Page>
        <ActionBar>
            <Label text="Home"/>
        </ActionBar>

        <GridLayout>
            <Label class="info">
                <FormattedString>
                    <Span class="fas" text.decode="&#xf135; "/>
                    <Span :text="message"/>
                </FormattedString>
            </Label>
        </GridLayout>
        <StackLayout>
            <Button text="Login" @tap="onLogin"></Button>
        </StackLayout>
    </Page>
</template>

<script>
    import {TnsEcho} from 'nativescript-laravel-echo';

    export default {
        computed: {
            message() {
                return "Blank {N}-Vue app";
            }
        },
        methods: {
            onLogin() {
                const token = 'Asdsd3dsdsTytf';//Your token
                const apiUrl = 'https://cb924de75169.ngrok.io';
                this.echo = new TnsEcho({
                    broadcaster: 'pusher',
                    host: apiUrl,
                    key: '158797eead9426132706',
                    authEndpoint: apiUrl + '/api/broadcasting/auth',
                    cluster: "ap2",
                    headers: {
                        auth: {
                            'Authorization': 'Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJhdWQiOiI3IiwianRpIjoiOGM3YjEwZTA3ZDljZTVkN2JjNmUxYzEyNGRhMTljNjcwNjM3ZmIzMzRjNTQ4MjVjMmI3YzhkYzRhOTNmYTI5MWQ1NGMwYzVmNDgxZDlmMDAiLCJpYXQiOjE2MjAyMDQ5MjIsIm5iZiI6MTYyMDIwNDkyMiwiZXhwIjoxNjUxNzQwOTIyLCJzdWIiOiI0MSIsInNjb3BlcyI6W119.HHi-Q5BlRsE20WKM8Zznehm6utpMQYk_s2IqCjozBx_Lgq9UEtXUR2xZtbZbRa1xdq7-PD3qzneuxpEYx0sYRiHi_Dtxo7-rR_6yUULe45fRGQnmZ-uCbl5FqL3K9v1rhlY0JXHqJ1_kP3KbFK7dWVsGpfJXjkzmcU4BFX1wmCcGNL20LLS52OiGA0XcQggIGlyiGYRNrVjGNVnN7g3sF-r1vYldqtFsjvZLAERHP5jCR_xyEGTeA5BY-SAMNVKVmFR1NY4gxfHwoen-hK2tUQU6BQi_ywlAnhZWDLPEweFi1R5vAgTsUnpZL9Bp15nprxGZfKzvbjdLq0kVuweB_gmVEJeWCUF9YvoCBMixHJjzW893OFKjwqGxduDTTr8f9_JkcnuJwLmyE1_dWyWgMb95UgCIoojnxEpWNvhKMkL90Ge9bqrv2voCjeMwC1OmMggcwnl7rA27ksfGbMpNJzfltj27Tw0bI60a9IqSfHNSRJm6ZCcu34P8B9GlYJvYBsxuBS7dJCL_iJjBs-ufsuVVMDzXfFYYYtZBXltSs6n41bIJwRLwIYHkmGlzFXnTmq3HWuRXqldPF6ot8x9J0wCA4JHfuE2POS_v0Y5wopvS0dIXW_98827zo7RQQW_fnGgtGuq2qqmuCAcY_AoPymA1yhaC5SMmR1msj4ifzSU'
                        },
                    }
                });
                console.log(this.echo)
                this.echo.connector.pusher.config.auth.headers = {
                    'Authorization': 'Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJhdWQiOiI3IiwianRpIjoiOGM3YjEwZTA3ZDljZTVkN2JjNmUxYzEyNGRhMTljNjcwNjM3ZmIzMzRjNTQ4MjVjMmI3YzhkYzRhOTNmYTI5MWQ1NGMwYzVmNDgxZDlmMDAiLCJpYXQiOjE2MjAyMDQ5MjIsIm5iZiI6MTYyMDIwNDkyMiwiZXhwIjoxNjUxNzQwOTIyLCJzdWIiOiI0MSIsInNjb3BlcyI6W119.HHi-Q5BlRsE20WKM8Zznehm6utpMQYk_s2IqCjozBx_Lgq9UEtXUR2xZtbZbRa1xdq7-PD3qzneuxpEYx0sYRiHi_Dtxo7-rR_6yUULe45fRGQnmZ-uCbl5FqL3K9v1rhlY0JXHqJ1_kP3KbFK7dWVsGpfJXjkzmcU4BFX1wmCcGNL20LLS52OiGA0XcQggIGlyiGYRNrVjGNVnN7g3sF-r1vYldqtFsjvZLAERHP5jCR_xyEGTeA5BY-SAMNVKVmFR1NY4gxfHwoen-hK2tUQU6BQi_ywlAnhZWDLPEweFi1R5vAgTsUnpZL9Bp15nprxGZfKzvbjdLq0kVuweB_gmVEJeWCUF9YvoCBMixHJjzW893OFKjwqGxduDTTr8f9_JkcnuJwLmyE1_dWyWgMb95UgCIoojnxEpWNvhKMkL90Ge9bqrv2voCjeMwC1OmMggcwnl7rA27ksfGbMpNJzfltj27Tw0bI60a9IqSfHNSRJm6ZCcu34P8B9GlYJvYBsxuBS7dJCL_iJjBs-ufsuVVMDzXfFYYYtZBXltSs6n41bIJwRLwIYHkmGlzFXnTmq3HWuRXqldPF6ot8x9J0wCA4JHfuE2POS_v0Y5wopvS0dIXW_98827zo7RQQW_fnGgtGuq2qqmuCAcY_AoPymA1yhaC5SMmR1msj4ifzSU'
                }
                console.log(this.echo.connector.pusher.config.auth.headers)
                // this.echo.connector.pusher.config.auth.headers['Authorization'] = 'Bearer eyJpdiI6IjVRUzA3VXlMRk81eEZxMDRDaUo4d1E9PSIsInZhbHVlIjoiSjJ3WnpkZis2b0RiOGJrVTgzNG1kUk1NM1Izak1EWUEwaUp0TEQvS1RUMHFOVWlUNlNnY3dLVW8wWjhIU285ZFY0cDZZYzNmK0Z6OTUvTkM3SVF2bU80MUJUU1RHOXRISWtpdjZ2aTdtN1RkZlFVZTJPL2Q4b2dtcCt2d3dWWk0iLCJtYWMiOiJlYmQyYTNmODk3Yzg4Mzk0YzM2MzhmNDgwOWIwZWRhMzk3NDg4YjY3Y2Y1MWNjYTc2MTVhY2UyZTBjOWE0YmFmIn0%3D';
                this.echo.private(`users.41`)
                    .notification((notification) => {
                        console.log(notification)
                    })
            }
        }
    };
</script>

<style scoped lang="scss">
    @import '~@nativescript/theme/scss/variables/blue';

    // Custom styles
    .fas {
        @include colorize($color: accent);
    }

    .info {
        font-size: 20;
        horizontal-align: center;
        vertical-align: center;
    }
</style>
