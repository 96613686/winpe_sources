# ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)

- ea: `0x18007ce08`
- end: `0x18007cf02`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z`
- size: `250`
- prototype: `int(ATL::CRegKey *__hidden this, HKEY, const wchar_t *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18007b140`
- `0x18007cf08`
- `0x18007d33c`

## callees

- `0x18007ce08`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007ce62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007ce62`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007ce4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007ce4d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007cebb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007cebb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007cecf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007cecf`

## string_xrefs

- `0x18007ce58`: `RegOpenKeyTransactedW`
- `0x18007ce46`: `Advapi32.dll`

## pseudocode

```c
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
0x18007ce08  push    rbx
0x18007ce0a  push    rbp
0x18007ce0b  push    rsi
0x18007ce0c  push    rdi
0x18007ce0d  push    r14
0x18007ce0f  sub     rsp, 50h
0x18007ce13  mov     rax, cs:__security_cookie
0x18007ce1a  xor     rax, rsp
0x18007ce1d  mov     [rsp+78h+var_30], rax
0x18007ce22  mov     ebx, r9d
0x18007ce25  mov     r14, r8
0x18007ce28  mov     rbp, rdx
0x18007ce2b  mov     rdi, rcx
0x18007ce2e  mov     [rsp+78h+var_38], 0
0x18007ce37  mov     rsi, [rcx+10h]
0x18007ce3b  test    rsi, rsi
0x18007ce3e  jz      short loc_18007CEA8
0x18007ce40  cmp     qword ptr [rsi], 0
0x18007ce44  jz      short loc_18007CE9B
0x18007ce46  lea     rcx, aAdvapi32Dll; "Advapi32.dll"
0x18007ce4d  call    cs:__imp_GetModuleHandleW
0x18007ce53  test    rax, rax
0x18007ce56  jz      short loc_18007CEA1
0x18007ce58  lea     rdx, aRegopenkeytran; "RegOpenKeyTransactedW"
0x18007ce5f  mov     rcx, rax; hModule
0x18007ce62  call    cs:__imp_GetProcAddress
0x18007ce68  test    rax, rax
0x18007ce6b  jz      short loc_18007CEA1
0x18007ce6d  mov     [rsp+78h+var_48], 0
0x18007ce76  mov     r8, [rsi]
0x18007ce79  mov     [rsp+78h+var_50], r8
0x18007ce7e  lea     rcx, [rsp+78h+var_38]
0x18007ce83  mov     [rsp+78h+phkResult], rcx
0x18007ce88  mov     r9d, ebx
0x18007ce8b  xor     r8d, r8d
0x18007ce8e  mov     rdx, r14
0x18007ce91  mov     rcx, rbp
0x18007ce94  call    _guard_dispatch_icall
0x18007ce99  jmp     short loc_18007CEC1
0x18007ce9b  cmp     dword ptr [rsi+8], 0
0x18007ce9f  jnz     short loc_18007CEA8
0x18007cea1  mov     ecx, 1
0x18007cea6  jmp     short loc_18007CEC3
0x18007cea8  lea     rax, [rsp+78h+var_38]
0x18007cead  mov     [rsp+78h+phkResult], rax; phkResult
0x18007ceb2  xor     r8d, r8d; ulOptions
0x18007ceb5  mov     rdx, r14; lpSubKey
0x18007ceb8  mov     rcx, rbp; hKey
0x18007cebb  call    cs:__imp_RegOpenKeyExW
0x18007cec1  mov     ecx, eax
0x18007cec3  test    ecx, ecx
0x18007cec5  jnz     short loc_18007CEE8
0x18007cec7  cmp     [rdi], rcx
0x18007ceca  jz      short loc_18007CED7
0x18007cecc  mov     rcx, [rdi]; hKey
0x18007cecf  call    cs:__imp_RegCloseKey
0x18007ced5  mov     ecx, eax
0x18007ced7  mov     rax, [rsp+78h+var_38]
0x18007cedc  mov     [rdi], rax
0x18007cedf  and     ebx, 300h
0x18007cee5  mov     [rdi+8], ebx
0x18007cee8  mov     eax, ecx
0x18007ceea  mov     rcx, [rsp+78h+var_30]
0x18007ceef  xor     rcx, rsp; StackCookie
0x18007cef2  call    __security_check_cookie
0x18007cef7  add     rsp, 50h
0x18007cefb  pop     r14
0x18007cefd  pop     rdi
0x18007cefe  pop     rsi
0x18007ceff  pop     rbp
0x18007cf00  pop     rbx
0x18007cf01  retn
```
