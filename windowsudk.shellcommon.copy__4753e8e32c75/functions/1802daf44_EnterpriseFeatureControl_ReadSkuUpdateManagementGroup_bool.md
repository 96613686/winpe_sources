# EnterpriseFeatureControl::ReadSkuUpdateManagementGroup(bool *)

- ea: `0x1802daf44`
- end: `0x1802db04d`
- name: `?ReadSkuUpdateManagementGroup@EnterpriseFeatureControl@@CAJPEA_N@Z`
- size: `265`
- prototype: `static int(bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180048e70`

## callees

- `0x1800e2988`
- `0x1800e34bc`
- `0x1802daf44`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1802db035`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1802db035`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802dafcd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802dafcd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1802daf97`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1802daf97`

## string_xrefs

- `0x1802daf90`: `ext-ms-win-security-slc-l1-1-0`
- `0x1802daff7`: `UpdatePolicy-UpdateManagementGroup`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnterpriseFeatureControl::ReadSkuUpdateManagementGroup(bool *a1)
{
  HMODULE Library; // rax
  const char *v4; // r9
  HMODULE v5; // rbx
  FARPROC ProcAddress; // rax
  const char *v7; // r9
  unsigned int LastError; // edi
  int v9; // eax
  int v10; // esi
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v13; // [rsp+30h] [rbp+8h] BYREF
  HMODULE v14; // [rsp+38h] [rbp+10h]

  v13 = 0;
  if ( a1 )
  {
    Library = LoadLibraryExW(L"ext-ms-win-security-slc-l1-1-0", 0, 0x800u);
    v5 = Library;
    v14 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "SLGetWindowsInformationDWORD");
      if ( ProcAddress )
      {
        v9 = ((__int64 (__fastcall *)(const wchar_t *, int *))ProcAddress)(L"UpdatePolicy-UpdateManagementGroup", &v13);
        v10 = v9;
        if ( v9 >= 0 )
        {
          *a1 = v13 == 0;
          LastError = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBF,
            (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
            (const char *)(unsigned int)v9,
            v11);
          LastError = v10;
        }
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xBE,
                      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
                      v7);
      }
      FreeLibrary(v5);
      return LastError;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xBA,
               (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
               v4);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)0x80004003LL,
      v11);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1802daf44  mov     [rsp+arg_10], rbx
0x1802daf49  mov     [rsp+arg_18], rsi
0x1802daf4e  push    rdi; int
0x1802daf4f  sub     rsp, 20h
0x1802daf53  mov     rdi, rcx
0x1802daf56  mov     [rsp+28h+arg_0], 0
0x1802daf5e  test    rcx, rcx
0x1802daf61  jnz     short loc_1802DAF88
0x1802daf63  mov     rcx, [rsp+28h]; this
0x1802daf68  mov     ebx, 80004003h
0x1802daf6d  mov     r9d, ebx; char *
0x1802daf70  lea     r8, aOnecoreInterna_12; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1802daf77  mov     edx, 0B7h; void *
0x1802daf7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802daf81  mov     eax, ebx
0x1802daf83  jmp     loc_1802DB03D
0x1802daf88  xor     edx, edx; hFile
0x1802daf8a  mov     r8d, 800h; dwFlags
0x1802daf90  lea     rcx, aExtMsWinSecuri_0; "ext-ms-win-security-slc-l1-1-0"
0x1802daf97  call    cs:__imp_LoadLibraryExW
0x1802daf9d  mov     rbx, rax
0x1802dafa0  mov     [rsp+28h+arg_8], rax
0x1802dafa5  test    rax, rax
0x1802dafa8  jnz     short loc_1802DAFC3
0x1802dafaa  mov     rcx, [rsp+28h]; this
0x1802dafaf  lea     r8, aOnecoreInterna_12; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1802dafb6  mov     edx, 0BAh; void *
0x1802dafbb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802dafc0  nop
0x1802dafc1  jmp     short loc_1802DB03D
0x1802dafc3  lea     rdx, aSlgetwindowsin_0; "SLGetWindowsInformationDWORD"
0x1802dafca  mov     rcx, rbx; hModule
0x1802dafcd  call    cs:__imp_GetProcAddress
0x1802dafd3  test    rax, rax
0x1802dafd6  jnz     short loc_1802DAFF2
0x1802dafd8  mov     rcx, [rsp+28h]; this
0x1802dafdd  lea     r8, aOnecoreInterna_12; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1802dafe4  mov     edx, 0BEh; void *
0x1802dafe9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802dafee  mov     edi, eax
0x1802daff0  jmp     short loc_1802DB032
0x1802daff2  lea     rdx, [rsp+28h+arg_0]
0x1802daff7  lea     rcx, aUpdatepolicyUp; "UpdatePolicy-UpdateManagementGroup"
0x1802daffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802db003  mov     esi, eax
0x1802db005  test    eax, eax
0x1802db007  jns     short loc_1802DB026
0x1802db009  mov     rcx, [rsp+28h]; this
0x1802db00e  mov     r9d, eax; char *
0x1802db011  lea     r8, aOnecoreInterna_12; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1802db018  mov     edx, 0BFh; void *
0x1802db01d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802db022  mov     edi, esi
0x1802db024  jmp     short loc_1802DB032
0x1802db026  cmp     [rsp+28h+arg_0], 0
0x1802db02b  setz    al
0x1802db02e  mov     [rdi], al
0x1802db030  xor     edi, edi
0x1802db032  mov     rcx, rbx; hLibModule
0x1802db035  call    cs:__imp_FreeLibrary
0x1802db03b  mov     eax, edi
0x1802db03d  mov     rbx, [rsp+28h+arg_10]
0x1802db042  mov     rsi, [rsp+28h+arg_18]
0x1802db047  add     rsp, 20h
0x1802db04b  pop     rdi
0x1802db04c  retn
```
