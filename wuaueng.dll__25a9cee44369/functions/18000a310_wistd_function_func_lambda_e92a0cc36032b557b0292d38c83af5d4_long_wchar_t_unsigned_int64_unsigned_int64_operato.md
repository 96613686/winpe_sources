# wistd::__function::__func<_lambda_e92a0cc36032b557b0292d38c83af5d4_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x18000a310`
- end: `0x18000a358`
- name: `??R?$__func@V_lambda_e92a0cc36032b557b0292d38c83af5d4_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEA_W$$QEA_K$$QEAPEA_K@Z`
- size: `72`
- prototype: `__int64 __fastcall(__int64, LPWSTR *, DWORD *, _QWORD **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003784`
- `0x18000a310`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000a326`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000a326`

## string_xrefs

- `0x18000a33d`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_e92a0cc36032b557b0292d38c83af5d4_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(
        __int64 a1,
        LPWSTR *a2,
        DWORD *a3,
        _QWORD **a4)
{
  _QWORD *v4; // rbx
  DWORD v5; // eax
  const char *v6; // r9
  unsigned int v7; // ecx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *a4;
  v5 = ExpandEnvironmentStringsW(**(LPCWSTR **)(a1 + 8), *a2, *a3);
  v7 = 0;
  *v4 = v5;
  if ( !v5 )
    return (unsigned int)wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0x181,
                           (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opens"
                                         "ource\\wil\\win32_helpers.h",
                           v6);
  return v7;
}

```

## disassembly

```asm
0x18000a310  push    rbx
0x18000a312  sub     rsp, 20h
0x18000a316  mov     rcx, [rcx+8]
0x18000a31a  mov     r8d, [r8]; nSize
0x18000a31d  mov     rdx, [rdx]; lpDst
0x18000a320  mov     rbx, [r9]
0x18000a323  mov     rcx, [rcx]; lpSrc
0x18000a326  call    cs:__imp_ExpandEnvironmentStringsW
0x18000a32c  mov     eax, eax
0x18000a32e  xor     ecx, ecx
0x18000a330  mov     [rbx], rax
0x18000a333  test    rax, rax
0x18000a336  jnz     short loc_18000A350
0x18000a338  mov     rcx, [rsp+28h]; this
0x18000a33d  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000a344  mov     edx, 181h; void *
0x18000a349  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a34e  mov     ecx, eax
0x18000a350  mov     eax, ecx
0x18000a352  add     rsp, 20h
0x18000a356  pop     rbx
0x18000a357  retn
```
