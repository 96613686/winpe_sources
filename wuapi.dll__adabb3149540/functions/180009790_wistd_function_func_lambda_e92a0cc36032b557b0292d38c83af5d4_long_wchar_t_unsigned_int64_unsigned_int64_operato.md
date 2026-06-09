# wistd::__function::__func<_lambda_e92a0cc36032b557b0292d38c83af5d4_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x180009790`
- end: `0x1800097d8`
- name: `??R?$__func@V_lambda_e92a0cc36032b557b0292d38c83af5d4_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEA_W$$QEA_K$$QEAPEA_K@Z`
- size: `72`
- prototype: `__int64 __fastcall(__int64, LPWSTR *, DWORD *, _QWORD **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003784`
- `0x180009790`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800097a6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800097a6`

## string_xrefs

- `0x1800097bd`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

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
0x180009790  push    rbx
0x180009792  sub     rsp, 20h
0x180009796  mov     rcx, [rcx+8]
0x18000979a  mov     r8d, [r8]; nSize
0x18000979d  mov     rdx, [rdx]; lpDst
0x1800097a0  mov     rbx, [r9]
0x1800097a3  mov     rcx, [rcx]; lpSrc
0x1800097a6  call    cs:__imp_ExpandEnvironmentStringsW
0x1800097ac  mov     eax, eax
0x1800097ae  xor     ecx, ecx
0x1800097b0  mov     [rbx], rax
0x1800097b3  test    rax, rax
0x1800097b6  jnz     short loc_1800097D0
0x1800097b8  mov     rcx, [rsp+28h]; this
0x1800097bd  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800097c4  mov     edx, 181h; void *
0x1800097c9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800097ce  mov     ecx, eax
0x1800097d0  mov     eax, ecx
0x1800097d2  add     rsp, 20h
0x1800097d6  pop     rbx
0x1800097d7  retn
```
