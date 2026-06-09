# wistd::__function::__func<_lambda_ed01672e02d6682bf5b3b76f9b133eec_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x140008be0`
- end: `0x140008c29`
- name: `??R?$__func@V_lambda_ed01672e02d6682bf5b3b76f9b133eec_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `73`
- prototype: `__int64 __fastcall(__int64, LPWSTR *, DWORD *, _QWORD **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140005414`
- `0x140008be0`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140008bf6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140008bf6`

## string_xrefs

- `0x140008c0b`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_ed01672e02d6682bf5b3b76f9b133eec_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
        __int64 a1,
        LPWSTR *a2,
        DWORD *a3,
        _QWORD **a4)
{
  _QWORD *v4; // rbx
  DWORD v5; // eax
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *a4;
  v5 = ExpandEnvironmentStringsW(**(LPCWSTR **)(a1 + 8), *a2, *a3);
  *v4 = v5;
  if ( v5 )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x191,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
             v6);
}

```

## disassembly

```asm
0x140008be0  push    rbx
0x140008be2  sub     rsp, 20h
0x140008be6  mov     rcx, [rcx+8]
0x140008bea  mov     r8d, [r8]; nSize
0x140008bed  mov     rdx, [rdx]; lpDst
0x140008bf0  mov     rbx, [r9]
0x140008bf3  mov     rcx, [rcx]; lpSrc
0x140008bf6  call    cs:__imp_ExpandEnvironmentStringsW
0x140008bfc  mov     eax, eax
0x140008bfe  mov     [rbx], rax
0x140008c01  test    rax, rax
0x140008c04  jnz     short loc_140008C21
0x140008c06  mov     rcx, [rsp+28h]; this
0x140008c0b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140008c12  mov     edx, 191h; void *
0x140008c17  add     rsp, 20h
0x140008c1b  pop     rbx
0x140008c1c  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140008c21  xor     eax, eax
0x140008c23  add     rsp, 20h
0x140008c27  pop     rbx
0x140008c28  retn
```
