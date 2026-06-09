# _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)

- ea: `0x180025548`
- end: `0x1800255be`
- name: `?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ`
- size: `118`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ec10`
- `0x18003431c`

## callees

- `0x1800011ec`
- `0x180025548`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180025583`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002559a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180025583`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002559a`

## pseudocode

```c
ULONG __fastcall _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  ULONG result; // eax

  result = dword_180048098;
  if ( (unsigned int)dword_180048098 > 5
    && (result = tlgKeywordOn(&dword_180048098, 0x400000000000LL, a3, a4), (_BYTE)result) )
  {
    EventActivityIdControl(3u, (LPGUID)(a1 + 8));
    *(_OWORD *)(a1 + 24) = *(_OWORD *)(a1 + 8);
    result = EventActivityIdControl(4u, (LPGUID)(a1 + 24));
    *(_BYTE *)(a1 + 4) = 1;
  }
  else
  {
    *(_OWORD *)(a1 + 8) = 0;
  }
  *(_DWORD *)a1 = 1;
  return result;
}

```

## disassembly

```asm
0x180025548  mov     [rsp+arg_0], rbx
0x18002554d  push    rdi
0x18002554e  sub     rsp, 20h
0x180025552  mov     eax, cs:dword_180048098
0x180025558  mov     rdi, rcx
0x18002555b  cmp     eax, 5
0x18002555e  jbe     short loc_1800255A6
0x180025560  mov     rdx, 400000000000h
0x18002556a  lea     rcx, dword_180048098
0x180025571  call    _tlgKeywordOn
0x180025576  test    al, al
0x180025578  jz      short loc_1800255A6
0x18002557a  lea     rdx, [rdi+8]; ActivityId
0x18002557e  mov     ecx, 3; ControlCode
0x180025583  call    cs:__imp_EventActivityIdControl
0x180025589  movups  xmm0, xmmword ptr [rdi+8]
0x18002558d  lea     rdx, [rdi+18h]; ActivityId
0x180025591  mov     ecx, 4; ControlCode
0x180025596  movdqu  xmmword ptr [rdx], xmm0
0x18002559a  call    cs:__imp_EventActivityIdControl
0x1800255a0  mov     byte ptr [rdi+4], 1
0x1800255a4  jmp     short loc_1800255AD
0x1800255a6  xorps   xmm0, xmm0
0x1800255a9  movups  xmmword ptr [rdi+8], xmm0
0x1800255ad  mov     rbx, [rsp+28h+arg_0]
0x1800255b2  mov     dword ptr [rdi], 1
0x1800255b8  add     rsp, 20h
0x1800255bc  pop     rdi
0x1800255bd  retn
```
