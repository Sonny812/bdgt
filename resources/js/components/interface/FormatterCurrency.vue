<script>
export default {
    functional: true,

    props: {
        amount: {},
        currency: {
            type: String,
            default: 'USD',
        },
        negative: {
            type: Boolean,
            default: false,
        },
    },

    render(h, context) {
        const amount = context.props.amount.toLocaleString(undefined, {
            style: 'currency',
            currency: context.props.currency,
        })

        return h('span', context.data, (
            context.props.negative && amount.indexOf('-') !== 0
            ? '-'
            : ''
        ) + amount)
    },
}
</script>
