# Windows::Configuration::IsDomainJoined(void)

- ea: `0x18008eea0`
- end: `0x18008efd9`
- name: `?IsDomainJoined@Configuration@Windows@@UEBA_NXZ`
- size: `313`
- prototype: `bool __fastcall(Windows::Configuration *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x18008eea0`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008ef02`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008ef15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008ef02`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008ef15`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008ef85`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008efab`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008ef85`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008efab`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008eed8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008eed8`

## string_xrefs

- `0x18008eed1`: `netapi32.dll`

## pseudocode

```c
bool __fastcall Windows::Configuration::IsDomainJoined(Windows::Configuration *this)
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  bool v3; // di
  bool v4; // si
  FARPROC ProcAddress; // r14
  FARPROC v6; // rax
  bool v7; // di
  __int64 v9; // [rsp+40h] [rbp-20h] BYREF
  void (__fastcall *v10)(__int64); // [rsp+48h] [rbp-18h]
  int v11; // [rsp+50h] [rbp-10h] BYREF

  Library = LoadLibraryExW(L"netapi32.dll", 0, 0x800u);
  v2 = Library;
  v3 = Library != 0;
  v4 = Library != 0;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "NetGetJoinInformation");
    v6 = GetProcAddress(v2, "NetApiBufferFree");
    v10 = (void (__fastcall *)(__int64))v6;
    if ( ProcAddress )
    {
      if ( v6 )
      {
        v9 = 0;
        v11 = 0;
        if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *, int *))ProcAddress)(0, &v9, &v11) )
        {
          v7 = v11 == 3;
          if ( v9 )
            v10(v9);
          if ( v4 )
            FreeLibrary(v2);
          return v7;
        }
        if ( v9 )
          v10(v9);
      }
    }
  }
  if ( v3 )
    FreeLibrary(v2);
  return 0;
}

```

## disassembly

```asm
0x18008eea0  mov     rax, rsp
0x18008eea3  mov     [rax+8], rbx
0x18008eea7  mov     [rax+10h], rsi
0x18008eeab  mov     [rax+18h], rdi
0x18008eeaf  mov     [rax+20h], r14
0x18008eeb3  push    rbp
0x18008eeb4  mov     rbp, rsp
0x18008eeb7  sub     rsp, 60h
0x18008eebb  mov     rax, cs:__security_cookie
0x18008eec2  xor     rax, rsp
0x18008eec5  mov     [rbp+var_8], rax
0x18008eec9  xor     edx, edx; hFile
0x18008eecb  mov     r8d, 800h; dwFlags
0x18008eed1  lea     rcx, aNetapi32Dll; "netapi32.dll"
0x18008eed8  call    cs:__imp_LoadLibraryExW
0x18008eede  mov     rbx, rax
0x18008eee1  mov     [rbp+var_40], rax
0x18008eee5  test    rax, rax
0x18008eee8  setnz   dil
0x18008eeec  mov     sil, dil
0x18008eeef  test    rax, rax
0x18008eef2  jz      loc_18008EFA3
0x18008eef8  lea     rdx, aNetgetjoininfo; "NetGetJoinInformation"
0x18008eeff  mov     rcx, rax; hModule
0x18008ef02  call    cs:__imp_GetProcAddress
0x18008ef08  mov     r14, rax
0x18008ef0b  lea     rdx, aNetapibufferfr; "NetApiBufferFree"
0x18008ef12  mov     rcx, rbx; hModule
0x18008ef15  call    cs:__imp_GetProcAddress
0x18008ef1b  mov     [rbp+var_18], rax
0x18008ef1f  test    r14, r14
0x18008ef22  jz      short loc_18008EFA3
0x18008ef24  test    rax, rax
0x18008ef27  jz      short loc_18008EFA3
0x18008ef29  mov     [rbp+var_20], 0
0x18008ef31  mov     [rbp+var_10], 0
0x18008ef38  lea     rax, [rbp+var_20]
0x18008ef3c  mov     [rbp+var_38], rax
0x18008ef40  lea     rax, [rbp+var_18]
0x18008ef44  mov     [rbp+var_30], rax
0x18008ef48  mov     [rbp+var_28], 1
0x18008ef4c  lea     r8, [rbp+var_10]
0x18008ef50  lea     rdx, [rbp+var_20]
0x18008ef54  xor     ecx, ecx
0x18008ef56  mov     rax, r14
0x18008ef59  call    _guard_dispatch_icall
0x18008ef5e  test    eax, eax
0x18008ef60  jnz     short loc_18008EF90
0x18008ef62  cmp     [rbp+var_10], 3
0x18008ef66  setz    dil
0x18008ef6a  mov     rcx, [rbp+var_20]
0x18008ef6e  test    rcx, rcx
0x18008ef71  jz      short loc_18008EF7D
0x18008ef73  mov     rax, [rbp+var_18]
0x18008ef77  call    _guard_dispatch_icall
0x18008ef7c  nop
0x18008ef7d  test    sil, sil
0x18008ef80  jz      short loc_18008EF8B
0x18008ef82  mov     rcx, rbx; hLibModule
0x18008ef85  call    cs:__imp_FreeLibrary
0x18008ef8b  mov     al, dil
0x18008ef8e  jmp     short loc_18008EFB3
0x18008ef90  mov     rcx, [rbp+var_20]
0x18008ef94  test    rcx, rcx
0x18008ef97  jz      short loc_18008EFA3
0x18008ef99  mov     rax, [rbp+var_18]
0x18008ef9d  call    _guard_dispatch_icall
0x18008efa2  nop
0x18008efa3  test    dil, dil
0x18008efa6  jz      short loc_18008EFB1
0x18008efa8  mov     rcx, rbx; hLibModule
0x18008efab  call    cs:__imp_FreeLibrary
0x18008efb1  xor     al, al
0x18008efb3  mov     rcx, [rbp+var_8]
0x18008efb7  xor     rcx, rsp; StackCookie
0x18008efba  call    __security_check_cookie
0x18008efbf  lea     r11, [rsp+60h+var_s0]
0x18008efc4  mov     rbx, [r11+10h]
0x18008efc8  mov     rsi, [r11+18h]
0x18008efcc  mov     rdi, [r11+20h]
0x18008efd0  mov     r14, [r11+28h]
0x18008efd4  mov     rsp, r11
0x18008efd7  pop     rbp
0x18008efd8  retn
```
