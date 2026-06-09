# TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>(void)

- ea: `0x180006638`
- end: `0x18000663d`
- name: `??1?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180035256`
- `0x1800353d0`

## callees

- `0x180006858`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>(
        __int64 a1)
{
  return _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(a1);
}

```

## disassembly

```asm
0x180006638  jmp     ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
```
