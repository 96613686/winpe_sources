# ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)

- ea: `0x1800079ac`
- end: `0x180007aa6`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z`
- size: `250`
- prototype: `__int64 __fastcall(ATL::CRegKey *this, HKEY, const wchar_t *, REGSAM)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180005770`
- `0x180007aac`
- `0x180007ee0`

## callees

- `0x1800079ac`
- `0x18002ffd0`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800079f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800079f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007a06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007a06`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007a5f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007a5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a73`

## string_xrefs

- `0x1800079fc`: `RegOpenKeyTransactedW`
- `0x1800079ea`: `Advapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY a2, const wchar_t *a3, REGSAM a4)
{
  __int64 v8; // rsi
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  unsigned int v11; // eax
  __int64 v12; // rcx
  HKEY phkResult; // [rsp+40h] [rbp-38h] BYREF

  phkResult = 0;
  v8 = *((_QWORD *)this + 2);
  if ( !v8 )
    goto LABEL_8;
  if ( !*(_QWORD *)v8 )
  {
    if ( !*(_DWORD *)(v8 + 8) )
    {
LABEL_7:
      v12 = 1;
      goto LABEL_10;
    }
LABEL_8:
    v11 = RegOpenKeyExW(a2, a3, 0, a4, &phkResult);
    goto LABEL_9;
  }
  ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
  if ( !ModuleHandleW )
    goto LABEL_7;
  ProcAddress = GetProcAddress(ModuleHandleW, "RegOpenKeyTransactedW");
  if ( !ProcAddress )
    goto LABEL_7;
  v11 = ((__int64 (__fastcall *)(HKEY, const wchar_t *, _QWORD, _QWORD, HKEY *, _QWORD, _QWORD))ProcAddress)(
          a2,
          a3,
          0,
          a4,
          &phkResult,
          *(_QWORD *)v8,
          0);
LABEL_9:
  v12 = v11;
LABEL_10:
  if ( !(_DWORD)v12 )
  {
    if ( *(_QWORD *)this != v12 )
      LODWORD(v12) = RegCloseKey(*(HKEY *)this);
    *(_QWORD *)this = phkResult;
    *((_DWORD *)this + 2) = a4 & 0x300;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800079ac  push    rbx
0x1800079ae  push    rbp
0x1800079af  push    rsi
0x1800079b0  push    rdi
0x1800079b1  push    r14
0x1800079b3  sub     rsp, 50h
0x1800079b7  mov     rax, cs:__security_cookie
0x1800079be  xor     rax, rsp
0x1800079c1  mov     [rsp+78h+var_30], rax
0x1800079c6  mov     ebx, r9d
0x1800079c9  mov     r14, r8
0x1800079cc  mov     rbp, rdx
0x1800079cf  mov     rdi, rcx
0x1800079d2  mov     [rsp+78h+var_38], 0
0x1800079db  mov     rsi, [rcx+10h]
0x1800079df  test    rsi, rsi
0x1800079e2  jz      short loc_180007A4C
0x1800079e4  cmp     qword ptr [rsi], 0
0x1800079e8  jz      short loc_180007A3F
0x1800079ea  lea     rcx, aAdvapi32Dll; "Advapi32.dll"
0x1800079f1  call    cs:__imp_GetModuleHandleW
0x1800079f7  test    rax, rax
0x1800079fa  jz      short loc_180007A45
0x1800079fc  lea     rdx, aRegopenkeytran; "RegOpenKeyTransactedW"
0x180007a03  mov     rcx, rax; hModule
0x180007a06  call    cs:__imp_GetProcAddress
0x180007a0c  test    rax, rax
0x180007a0f  jz      short loc_180007A45
0x180007a11  mov     [rsp+78h+var_48], 0
0x180007a1a  mov     r8, [rsi]
0x180007a1d  mov     [rsp+78h+var_50], r8
0x180007a22  lea     rcx, [rsp+78h+var_38]
0x180007a27  mov     [rsp+78h+phkResult], rcx
0x180007a2c  mov     r9d, ebx
0x180007a2f  xor     r8d, r8d
0x180007a32  mov     rdx, r14
0x180007a35  mov     rcx, rbp
0x180007a38  call    _guard_dispatch_icall
0x180007a3d  jmp     short loc_180007A65
0x180007a3f  cmp     dword ptr [rsi+8], 0
0x180007a43  jnz     short loc_180007A4C
0x180007a45  mov     ecx, 1
0x180007a4a  jmp     short loc_180007A67
0x180007a4c  lea     rax, [rsp+78h+var_38]
0x180007a51  mov     [rsp+78h+phkResult], rax; phkResult
0x180007a56  xor     r8d, r8d; ulOptions
0x180007a59  mov     rdx, r14; lpSubKey
0x180007a5c  mov     rcx, rbp; hKey
0x180007a5f  call    cs:__imp_RegOpenKeyExW
0x180007a65  mov     ecx, eax
0x180007a67  test    ecx, ecx
0x180007a69  jnz     short loc_180007A8C
0x180007a6b  cmp     [rdi], rcx
0x180007a6e  jz      short loc_180007A7B
0x180007a70  mov     rcx, [rdi]; hKey
0x180007a73  call    cs:__imp_RegCloseKey
0x180007a79  mov     ecx, eax
0x180007a7b  mov     rax, [rsp+78h+var_38]
0x180007a80  mov     [rdi], rax
0x180007a83  and     ebx, 300h
0x180007a89  mov     [rdi+8], ebx
0x180007a8c  mov     eax, ecx
0x180007a8e  mov     rcx, [rsp+78h+var_30]
0x180007a93  xor     rcx, rsp; StackCookie
0x180007a96  call    __security_check_cookie
0x180007a9b  add     rsp, 50h
0x180007a9f  pop     r14
0x180007aa1  pop     rdi
0x180007aa2  pop     rsi
0x180007aa3  pop     rbp
0x180007aa4  pop     rbx
0x180007aa5  retn
```
