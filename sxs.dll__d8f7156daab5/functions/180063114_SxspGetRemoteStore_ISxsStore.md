# SxspGetRemoteStore(ISxsStore * *)

- ea: `0x180063114`
- end: `0x1800632c4`
- name: `?SxspGetRemoteStore@@YAJPEAPEAUISxsStore@@@Z`
- size: `432`
- prototype: `__int64 __fastcall(struct ISxsStore **)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005cfa0`
- `0x18005ed70`
- `0x18005f1f0`

## callees

- `0x180063074`
- `0x180063114`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063243`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063243`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063293`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063293`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180063285`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180063285`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800631ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800631ac`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180063184`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180063184`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800631f6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800631f6`

## string_xrefs

- `0x180063136`: `ole32.dll`
- `0x1800631a2`: `CoCreateInstance`

## pseudocode

```c
__int64 __fastcall SxspGetRemoteStore(struct ISxsStore **a1)
{
  HMODULE v1; // rdi
  int IsAdmin; // ebx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rbp
  unsigned int i; // esi
  struct ISxsStore *v7; // rcx
  DWORD LastError; // esi
  __int64 v10; // [rsp+30h] [rbp-48h] BYREF
  struct ISxsStore *v11; // [rsp+38h] [rbp-40h] BYREF
  WCHAR LibFileName[12]; // [rsp+40h] [rbp-38h] BYREF

  v1 = 0;
  v10 = 0;
  v11 = 0;
  wcscpy(LibFileName, L"ole32.dll");
  if ( a1 )
  {
    IsAdmin = SxspEnsureUserIsAdmin();
    if ( IsAdmin >= 0 )
    {
      LibraryW = LoadLibraryW(LibFileName);
      v1 = LibraryW;
      if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "CoCreateInstance")) != 0 )
      {
        for ( i = 0; i < 0xA; ++i )
        {
          IsAdmin = ((__int64 (__fastcall *)(GUID *, _QWORD, __int64, GUID *, __int64 *))ProcAddress)(
                      &CLSID_SxsStore,
                      0,
                      4,
                      &IID_IUnknown,
                      &v10);
          if ( IsAdmin != -2146959355 )
            break;
          Sleep(0x64u);
        }
        if ( IsAdmin >= 0 )
        {
          IsAdmin = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ISxsStore **))v10)(v10, &IID_ISxsStore, &v11);
          if ( IsAdmin >= 0 )
          {
            v7 = v11;
            *a1 = v11;
            (*(void (__fastcall **)(struct ISxsStore *))(*(_QWORD *)v7 + 8LL))(v7);
          }
        }
      }
      else
      {
        IsAdmin = -2147023611;
      }
    }
  }
  else
  {
    IsAdmin = -2147024809;
  }
  LastError = GetLastError();
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v11 )
    (*(void (__fastcall **)(struct ISxsStore *))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v1 )
    FreeLibrary(v1);
  SetLastError(LastError);
  return (unsigned int)IsAdmin;
}

```

## disassembly

```asm
0x180063114  mov     r11, rsp
0x180063117  mov     [r11+10h], rbx
0x18006311b  mov     [r11+18h], rbp
0x18006311f  push    rsi
0x180063120  push    rdi
0x180063121  push    r14
0x180063123  sub     rsp, 60h
0x180063127  mov     rax, cs:__security_cookie
0x18006312e  xor     rax, rsp
0x180063131  mov     [rsp+78h+var_20], rax
0x180063136  movups  xmm0, xmmword ptr cs:aOle32Dll; "ole32.dll"
0x18006313d  mov     eax, dword ptr cs:aOle32Dll+10h; "l"
0x180063143  xor     edi, edi
0x180063145  mov     qword ptr [r11-48h], 0
0x18006314d  mov     r14, rcx
0x180063150  mov     qword ptr [r11-40h], 0
0x180063158  mov     [rsp+78h+var_28], eax
0x18006315c  movups  xmmword ptr [rsp+78h+LibFileName], xmm0
0x180063161  test    rcx, rcx
0x180063164  jnz     short loc_180063170
0x180063166  mov     ebx, 80070057h
0x18006316b  jmp     loc_180063243
0x180063170  call    ?SxspEnsureUserIsAdmin@@YAJXZ; SxspEnsureUserIsAdmin(void)
0x180063175  mov     ebx, eax
0x180063177  test    eax, eax
0x180063179  js      loc_180063243
0x18006317f  lea     rcx, [rsp+78h+LibFileName]; lpLibFileName
0x180063184  call    cs:__imp_LoadLibraryW
0x18006318b  nop     dword ptr [rax+rax+00h]
0x180063190  mov     rdi, rax
0x180063193  test    rax, rax
0x180063196  jnz     short loc_1800631A2
0x180063198  mov     ebx, 80070505h
0x18006319d  jmp     loc_180063243
0x1800631a2  lea     rdx, aCocreateinstan; "CoCreateInstance"
0x1800631a9  mov     rcx, rax; hModule
0x1800631ac  call    cs:__imp_GetProcAddress
0x1800631b3  nop     dword ptr [rax+rax+00h]
0x1800631b8  mov     rbp, rax
0x1800631bb  test    rax, rax
0x1800631be  jz      short loc_180063198
0x1800631c0  xor     esi, esi
0x1800631c2  xor     edx, edx
0x1800631c4  lea     rax, [rsp+78h+var_48]
0x1800631c9  mov     [rsp+78h+var_58], rax
0x1800631ce  lea     r9, IID_IUnknown
0x1800631d5  lea     rcx, CLSID_SxsStore
0x1800631dc  mov     rax, rbp
0x1800631df  lea     r8d, [rdx+4]
0x1800631e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800631e8  mov     ebx, eax
0x1800631ea  cmp     eax, 80080005h
0x1800631ef  jnz     short loc_180063209
0x1800631f1  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800631f6  call    cs:__imp_Sleep
0x1800631fd  nop     dword ptr [rax+rax+00h]
0x180063202  inc     esi
0x180063204  cmp     esi, 0Ah
0x180063207  jb      short loc_1800631C2
0x180063209  test    ebx, ebx
0x18006320b  js      short loc_180063243
0x18006320d  mov     rcx, [rsp+78h+var_48]
0x180063212  lea     r8, [rsp+78h+var_40]
0x180063217  lea     rdx, IID_ISxsStore
0x18006321e  mov     rax, [rcx]
0x180063221  mov     rax, [rax]
0x180063224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063229  mov     ebx, eax
0x18006322b  test    eax, eax
0x18006322d  js      short loc_180063243
0x18006322f  mov     rcx, [rsp+78h+var_40]
0x180063234  mov     [r14], rcx
0x180063237  mov     rax, [rcx]
0x18006323a  mov     rax, [rax+8]
0x18006323e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063243  call    cs:__imp_GetLastError
0x18006324a  nop     dword ptr [rax+rax+00h]
0x18006324f  mov     rcx, [rsp+78h+var_48]
0x180063254  mov     esi, eax
0x180063256  test    rcx, rcx
0x180063259  jz      short loc_180063267
0x18006325b  mov     rdx, [rcx]
0x18006325e  mov     rax, [rdx+10h]
0x180063262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063267  mov     rcx, [rsp+78h+var_40]
0x18006326c  test    rcx, rcx
0x18006326f  jz      short loc_18006327D
0x180063271  mov     rax, [rcx]
0x180063274  mov     rax, [rax+10h]
0x180063278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006327d  test    rdi, rdi
0x180063280  jz      short loc_180063291
0x180063282  mov     rcx, rdi; hLibModule
0x180063285  call    cs:__imp_FreeLibrary
0x18006328c  nop     dword ptr [rax+rax+00h]
0x180063291  mov     ecx, esi; dwErrCode
0x180063293  call    cs:__imp_SetLastError
0x18006329a  nop     dword ptr [rax+rax+00h]
0x18006329f  mov     eax, ebx
0x1800632a1  mov     rcx, [rsp+78h+var_20]
0x1800632a6  xor     rcx, rsp; StackCookie
0x1800632a9  call    __security_check_cookie
0x1800632ae  lea     r11, [rsp+78h+var_18]
0x1800632b3  mov     rbx, [r11+28h]
0x1800632b7  mov     rbp, [r11+30h]
0x1800632bb  mov     rsp, r11
0x1800632be  pop     r14
0x1800632c0  pop     rdi
0x1800632c1  pop     rsi
0x1800632c2  retn
```
