# _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)

- ea: `0x180006858`
- end: `0x18000689d`
- name: `??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ`
- size: `69`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006638`
- `0x180008d28`
- `0x18000a46c`

## callees

- `0x180006494`
- `0x180006858`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180006875`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180006875`

## pseudocode

```c
__int64 __fastcall _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_DWORD *)a1 == 1 )
  {
    if ( *(_BYTE *)(a1 + 4) )
      EventActivityIdControl(4u, (LPGUID)(a1 + 24));
    *(_DWORD *)a1 = 2;
    result = _tlgWriteActivityAutoStop<0,5>((unsigned int *)&dword_180048098, a1 + 8);
  }
  *(_DWORD *)a1 = 3;
  return result;
}

```

## disassembly

```asm
0x180006858  push    rbx
0x18000685a  sub     rsp, 20h
0x18000685e  cmp     dword ptr [rcx], 1
0x180006861  mov     rbx, rcx
0x180006864  jnz     short loc_180006891
0x180006866  cmp     byte ptr [rcx+4], 0
0x18000686a  jz      short loc_18000687B
0x18000686c  lea     rdx, [rcx+18h]; ActivityId
0x180006870  mov     ecx, 4; ControlCode
0x180006875  call    cs:__imp_EventActivityIdControl
0x18000687b  lea     rdx, [rbx+8]
0x18000687f  mov     dword ptr [rbx], 2
0x180006885  lea     rcx, dword_180048098
0x18000688c  call    ??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)
0x180006891  mov     dword ptr [rbx], 3
0x180006897  add     rsp, 20h
0x18000689b  pop     rbx
0x18000689c  retn
```
