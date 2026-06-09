# wistd::__function::__func<_lambda_e92a0cc36032b557b0292d38c83af5d4_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x140009be0`
- end: `0x140009c28`
- name: `??R?$__func@V_lambda_e92a0cc36032b557b0292d38c83af5d4_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEA_W$$QEA_K$$QEAPEA_K@Z`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003e74`
- `0x140009be0`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140009bf6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140009bf6`

## string_xrefs

- `0x140009c0d`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

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
0x140009be0  push    rbx
0x140009be2  sub     rsp, 20h
0x140009be6  mov     rcx, [rcx+8]
0x140009bea  mov     r8d, [r8]; nSize
0x140009bed  mov     rdx, [rdx]; lpDst
0x140009bf0  mov     rbx, [r9]
0x140009bf3  mov     rcx, [rcx]; lpSrc
0x140009bf6  call    cs:__imp_ExpandEnvironmentStringsW
0x140009bfc  mov     eax, eax
0x140009bfe  xor     ecx, ecx
0x140009c00  mov     [rbx], rax
0x140009c03  test    rax, rax
0x140009c06  jnz     short loc_140009C20
0x140009c08  mov     rcx, [rsp+28h]; this
0x140009c0d  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140009c14  mov     edx, 181h; void *
0x140009c19  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140009c1e  mov     ecx, eax
0x140009c20  mov     eax, ecx
0x140009c22  add     rsp, 20h
0x140009c26  pop     rbx
0x140009c27  retn
```
