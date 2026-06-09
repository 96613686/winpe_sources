# wistd::__function::__func<_lambda_f8283d5da69bb462f85d4baf89ac4f9d_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x140022470`
- end: `0x1400224b9`
- name: `??R?$__func@V_lambda_f8283d5da69bb462f85d4baf89ac4f9d_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `73`
- prototype: `__int64 __fastcall(__int64, LPWSTR *, DWORD *, _QWORD **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140006824`
- `0x140022470`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x140022486`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140022486`

## string_xrefs

- `0x14002249b`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_f8283d5da69bb462f85d4baf89ac4f9d_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
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
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
             v6);
}

```

## disassembly

```asm
0x140022470  push    rbx
0x140022472  sub     rsp, 20h
0x140022476  mov     rcx, [rcx+8]
0x14002247a  mov     r8d, [r8]; nSize
0x14002247d  mov     rdx, [rdx]; lpDst
0x140022480  mov     rbx, [r9]
0x140022483  mov     rcx, [rcx]; lpSrc
0x140022486  call    cs:__imp_ExpandEnvironmentStringsW
0x14002248c  mov     eax, eax
0x14002248e  mov     [rbx], rax
0x140022491  test    rax, rax
0x140022494  jnz     short loc_1400224B1
0x140022496  mov     rcx, [rsp+28h]; this
0x14002249b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400224a2  mov     edx, 191h; void *
0x1400224a7  add     rsp, 20h
0x1400224ab  pop     rbx
0x1400224ac  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400224b1  xor     eax, eax
0x1400224b3  add     rsp, 20h
0x1400224b7  pop     rbx
0x1400224b8  retn
```
