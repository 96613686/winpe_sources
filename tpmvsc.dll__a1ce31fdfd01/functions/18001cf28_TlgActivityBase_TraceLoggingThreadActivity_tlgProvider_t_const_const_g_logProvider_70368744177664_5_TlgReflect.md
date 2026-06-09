# _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)

- ea: `0x18001cf28`
- end: `0x18001cf6d`
- name: `??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ`
- size: `69`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001cbb8`
- `0x18001ec10`
- `0x18003431c`

## callees

- `0x18001cabc`
- `0x18001cf28`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001cf45`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001cf45`

## pseudocode

```c
__int64 __fastcall _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_DWORD *)a1 == 1 )
  {
    if ( *(_BYTE *)(a1 + 4) )
      EventActivityIdControl(4u, (LPGUID)(a1 + 24));
    *(_DWORD *)a1 = 2;
    result = _tlgWriteActivityAutoStop<70368744177664,5>((unsigned int *)&dword_180048098, a1 + 8);
  }
  *(_DWORD *)a1 = 3;
  return result;
}

```

## disassembly

```asm
0x18001cf28  push    rbx
0x18001cf2a  sub     rsp, 20h
0x18001cf2e  cmp     dword ptr [rcx], 1
0x18001cf31  mov     rbx, rcx
0x18001cf34  jnz     short loc_18001CF61
0x18001cf36  cmp     byte ptr [rcx+4], 0
0x18001cf3a  jz      short loc_18001CF4B
0x18001cf3c  lea     rdx, [rcx+18h]; ActivityId
0x18001cf40  mov     ecx, 4; ControlCode
0x18001cf45  call    cs:__imp_EventActivityIdControl
0x18001cf4b  lea     rdx, [rbx+8]
0x18001cf4f  mov     dword ptr [rbx], 2
0x18001cf55  lea     rcx, dword_180048098
0x18001cf5c  call    ??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)
0x18001cf61  mov     dword ptr [rbx], 3
0x18001cf67  add     rsp, 20h
0x18001cf6b  pop     rbx
0x18001cf6c  retn
```
