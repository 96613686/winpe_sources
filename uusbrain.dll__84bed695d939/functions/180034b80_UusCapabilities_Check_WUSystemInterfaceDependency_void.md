# UusCapabilities::Check_WUSystemInterfaceDependency(void)

- ea: `0x180034b80`
- end: `0x180034de0`
- name: `?Check_WUSystemInterfaceDependency@UusCapabilities@@AEAA_NXZ`
- size: `608`
- prototype: `char __fastcall(UusCapabilities *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180034914`

## callees

- `0x180034b80`
- `0x1800427d0`
- `0x180047a30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180034daf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180034daf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180034c17`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180034c17`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180034bf2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180034bf2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034c40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034c40`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180034c32`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180034c32`

## string_xrefs

- `0x180034beb`: `wusys.dll`

## pseudocode

```c
char __fastcall UusCapabilities::Check_WUSystemInterfaceDependency(UusCapabilities *this)
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  char v3; // di
  FARPROC ProcAddress; // rsi
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  HMODULE phModule; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v10; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v11; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v12; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+50h] [rbp-B8h] BYREF
  WCHAR Filename[264]; // [rsp+58h] [rbp-B0h] BYREF

  v13 = 0;
  v12 = 0;
  phModule = 0;
  v10 = 0;
  v11 = 0;
  Library = LoadLibraryExW(L"wusys.dll", 0, 0x880u);
  v2 = Library;
  if ( !Library )
    goto LABEL_18;
  v3 = 1;
  if ( GetModuleFileNameW(Library, Filename, 0x105u) )
    GetModuleHandleExW(1u, Filename, &phModule);
  ProcAddress = GetProcAddress(v2, (LPCSTR)0xA425);
  if ( !ProcAddress )
    goto LABEL_18;
  v5 = v13;
  v13 = 0;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( ((int (__fastcall *)(__int64, __int64 *))ProcAddress)(2, &v13) < 0 )
    goto LABEL_18;
  v6 = v12;
  v12 = 0;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v13)(v13, &GUID_07186f27_adf4_4d8c_862a_5d403bd2010a, &v12) < 0 )
    goto LABEL_18;
  v7 = v10;
  v10 = 0;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v12)(v12, &GUID_c3ac0127_4d4d_49ec_a06f_89298d5bdb36, &v10) < 0
    || (*(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v10 + 504LL))(v10, 1, &v11) < 0
    || !(_DWORD)v11
    || (*(int (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v10 + 504LL))(v10, 3, (char *)&v11 + 4) < 0
    || !HIDWORD(v11) )
  {
LABEL_18:
    v3 = 0;
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v2 )
    FreeLibrary(v2);
  return v3;
}

```

## disassembly

```asm
0x180034b80  mov     rax, rsp
0x180034b83  mov     [rax+8], rbx
0x180034b87  mov     [rax+10h], rsi
0x180034b8b  mov     [rax+18h], rdi
0x180034b8f  push    rbp
0x180034b90  lea     rbp, [rax-178h]
0x180034b97  sub     rsp, 270h
0x180034b9e  mov     rax, cs:__security_cookie
0x180034ba5  xor     rax, rsp
0x180034ba8  mov     [rbp+170h+var_10], rax
0x180034baf  mov     [rsp+270h+var_228], 0
0x180034bb8  mov     [rsp+270h+var_230], 0
0x180034bc1  mov     [rsp+270h+phModule], 0
0x180034bca  mov     [rsp+270h+var_240], 0
0x180034bd3  mov     dword ptr [rsp+270h+var_238], 0
0x180034bdb  mov     dword ptr [rsp+270h+var_238+4], 0
0x180034be3  xor     edx, edx; hFile
0x180034be5  mov     r8d, 880h; dwFlags
0x180034beb  lea     rcx, LibFileName; "wusys.dll"
0x180034bf2  call    cs:__imp_LoadLibraryExW
0x180034bf8  mov     rbx, rax
0x180034bfb  mov     [rsp+270h+var_250], rax
0x180034c00  test    rax, rax
0x180034c03  jz      loc_180034D5F
0x180034c09  mov     r8d, 105h; nSize
0x180034c0f  lea     rdx, [rsp+270h+Filename]; lpFilename
0x180034c14  mov     rcx, rax; hModule
0x180034c17  call    cs:__imp_GetModuleFileNameW
0x180034c1d  mov     edi, 1
0x180034c22  test    eax, eax
0x180034c24  jz      short loc_180034C38
0x180034c26  lea     r8, [rsp+270h+phModule]; phModule
0x180034c2b  lea     rdx, [rsp+270h+Filename]; lpModuleName
0x180034c30  mov     ecx, edi; dwFlags
0x180034c32  call    cs:__imp_GetModuleHandleExW
0x180034c38  mov     edx, 0A425h; lpProcName
0x180034c3d  mov     rcx, rbx; hModule
0x180034c40  call    cs:__imp_GetProcAddress
0x180034c46  mov     rsi, rax
0x180034c49  test    rax, rax
0x180034c4c  jz      loc_180034D5F
0x180034c52  mov     rcx, [rsp+270h+var_228]
0x180034c57  mov     [rsp+270h+var_228], 0
0x180034c60  test    rcx, rcx
0x180034c63  jz      short loc_180034C72
0x180034c65  mov     rdx, [rcx]
0x180034c68  mov     rax, [rdx+10h]
0x180034c6c  call    _guard_dispatch_icall
0x180034c71  nop
0x180034c72  lea     rdx, [rsp+270h+var_228]
0x180034c77  mov     ecx, 2
0x180034c7c  mov     rax, rsi
0x180034c7f  call    _guard_dispatch_icall
0x180034c84  test    eax, eax
0x180034c86  js      loc_180034D5F
0x180034c8c  mov     rcx, [rsp+270h+var_230]
0x180034c91  mov     [rsp+270h+var_230], 0
0x180034c9a  test    rcx, rcx
0x180034c9d  jz      short loc_180034CAC
0x180034c9f  mov     rax, [rcx]
0x180034ca2  mov     rax, [rax+10h]
0x180034ca6  call    _guard_dispatch_icall
0x180034cab  nop
0x180034cac  mov     rcx, [rsp+270h+var_228]
0x180034cb1  mov     rax, [rcx]
0x180034cb4  lea     r8, [rsp+270h+var_230]
0x180034cb9  lea     rdx, _GUID_07186f27_adf4_4d8c_862a_5d403bd2010a
0x180034cc0  mov     rax, [rax]
0x180034cc3  call    _guard_dispatch_icall
0x180034cc8  test    eax, eax
0x180034cca  js      loc_180034D5F
0x180034cd0  mov     rcx, [rsp+270h+var_240]
0x180034cd5  mov     [rsp+270h+var_240], 0
0x180034cde  test    rcx, rcx
0x180034ce1  jz      short loc_180034CF0
0x180034ce3  mov     rax, [rcx]
0x180034ce6  mov     rax, [rax+10h]
0x180034cea  call    _guard_dispatch_icall
0x180034cef  nop
0x180034cf0  mov     rcx, [rsp+270h+var_230]
0x180034cf5  mov     rax, [rcx]
0x180034cf8  lea     r8, [rsp+270h+var_240]
0x180034cfd  lea     rdx, _GUID_c3ac0127_4d4d_49ec_a06f_89298d5bdb36
0x180034d04  mov     rax, [rax]
0x180034d07  call    _guard_dispatch_icall
0x180034d0c  test    eax, eax
0x180034d0e  js      short loc_180034D5F
0x180034d10  mov     rcx, [rsp+270h+var_240]
0x180034d15  mov     rax, [rcx]
0x180034d18  lea     r8, [rsp+270h+var_238]
0x180034d1d  mov     edx, edi
0x180034d1f  mov     rax, [rax+1F8h]
0x180034d26  call    _guard_dispatch_icall
0x180034d2b  test    eax, eax
0x180034d2d  js      short loc_180034D5F
0x180034d2f  cmp     dword ptr [rsp+270h+var_238], 0
0x180034d34  jz      short loc_180034D5F
0x180034d36  mov     rcx, [rsp+270h+var_240]
0x180034d3b  mov     rax, [rcx]
0x180034d3e  lea     r8, [rsp+270h+var_238+4]
0x180034d43  mov     edx, 3
0x180034d48  mov     rax, [rax+1F8h]
0x180034d4f  call    _guard_dispatch_icall
0x180034d54  test    eax, eax
0x180034d56  js      short loc_180034D5F
0x180034d58  cmp     dword ptr [rsp+270h+var_238+4], 0
0x180034d5d  jnz     short loc_180034D62
0x180034d5f  xor     dil, dil
0x180034d62  mov     rcx, [rsp+270h+var_240]
0x180034d67  test    rcx, rcx
0x180034d6a  jz      short loc_180034D79
0x180034d6c  mov     rax, [rcx]
0x180034d6f  mov     rax, [rax+10h]
0x180034d73  call    _guard_dispatch_icall
0x180034d78  nop
0x180034d79  mov     rcx, [rsp+270h+var_230]
0x180034d7e  test    rcx, rcx
0x180034d81  jz      short loc_180034D90
0x180034d83  mov     rax, [rcx]
0x180034d86  mov     rax, [rax+10h]
0x180034d8a  call    _guard_dispatch_icall
0x180034d8f  nop
0x180034d90  mov     rcx, [rsp+270h+var_228]
0x180034d95  test    rcx, rcx
0x180034d98  jz      short loc_180034DA7
0x180034d9a  mov     rax, [rcx]
0x180034d9d  mov     rax, [rax+10h]
0x180034da1  call    _guard_dispatch_icall
0x180034da6  nop
0x180034da7  test    rbx, rbx
0x180034daa  jz      short loc_180034DB5
0x180034dac  mov     rcx, rbx; hLibModule
0x180034daf  call    cs:__imp_FreeLibrary
0x180034db5  mov     al, dil
0x180034db8  mov     rcx, [rbp+170h+var_10]
0x180034dbf  xor     rcx, rsp; StackCookie
0x180034dc2  call    __security_check_cookie
0x180034dc7  lea     r11, [rsp+270h+var_s0]
0x180034dcf  mov     rbx, [r11+10h]
0x180034dd3  mov     rsi, [r11+18h]
0x180034dd7  mov     rdi, [r11+20h]
0x180034ddb  mov     rsp, r11
0x180034dde  pop     rbp
0x180034ddf  retn
```
