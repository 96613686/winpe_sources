# _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)

- ea: `0x18000c064`
- end: `0x18000c0c1`
- name: `?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ`
- size: `93`
- prototype: `ULONG __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008d28`
- `0x18000a46c`

## callees

- `0x18000c064`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000c088`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000c09e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000c088`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000c09e`

## pseudocode

```c
ULONG __fastcall _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(
        __int64 a1)
{
  ULONG result; // eax
  _OWORD *v2; // rdi

  result = dword_180048098;
  v2 = (_OWORD *)(a1 + 8);
  if ( (unsigned int)dword_180048098 <= 5 )
  {
    *v2 = 0;
  }
  else
  {
    EventActivityIdControl(3u, (LPGUID)(a1 + 8));
    *(_OWORD *)(a1 + 24) = *v2;
    result = EventActivityIdControl(4u, (LPGUID)(a1 + 24));
    *(_BYTE *)(a1 + 4) = 1;
  }
  *(_DWORD *)a1 = 1;
  return result;
}

```

## disassembly

```asm
0x18000c064  mov     [rsp+arg_0], rbx
0x18000c069  push    rdi
0x18000c06a  sub     rsp, 20h
0x18000c06e  mov     eax, cs:dword_180048098
0x18000c074  lea     rdi, [rcx+8]
0x18000c078  mov     rbx, rcx
0x18000c07b  cmp     eax, 5
0x18000c07e  jbe     short loc_18000C0AA
0x18000c080  mov     rdx, rdi; ActivityId
0x18000c083  mov     ecx, 3; ControlCode
0x18000c088  call    cs:__imp_EventActivityIdControl
0x18000c08e  movups  xmm0, xmmword ptr [rdi]
0x18000c091  lea     rdx, [rbx+18h]; ActivityId
0x18000c095  mov     ecx, 4; ControlCode
0x18000c09a  movdqu  xmmword ptr [rdx], xmm0
0x18000c09e  call    cs:__imp_EventActivityIdControl
0x18000c0a4  mov     byte ptr [rbx+4], 1
0x18000c0a8  jmp     short loc_18000C0B0
0x18000c0aa  xorps   xmm0, xmm0
0x18000c0ad  movups  xmmword ptr [rdi], xmm0
0x18000c0b0  mov     dword ptr [rbx], 1
0x18000c0b6  mov     rbx, [rsp+28h+arg_0]
0x18000c0bb  add     rsp, 20h
0x18000c0bf  pop     rdi
0x18000c0c0  retn
```
