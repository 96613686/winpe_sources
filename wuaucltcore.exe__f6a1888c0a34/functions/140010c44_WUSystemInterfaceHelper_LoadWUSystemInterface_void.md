# WUSystemInterfaceHelper::LoadWUSystemInterface(void)

- ea: `0x140010c44`
- end: `0x140010e6f`
- name: `?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ`
- size: `555`
- prototype: `__int64 __fastcall(WUSystemInterfaceHelper *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400080bc`
- `0x140010e78`

## callees

- `0x140002ac0`
- `0x140003e74`
- `0x140010c44`
- `0x14001aa60`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140010d25`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140010d25`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140010cce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140010cce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140010cf8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140010cf8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140010d13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140010d13`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140010c7d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140010c7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140010c91`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140010c9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140010c91`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140010c9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010e3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010e3f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010ca7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010ca7`

## string_xrefs

- `0x140010cc7`: `wusys.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WUSystemInterfaceHelper::LoadWUSystemInterface(WUSystemInterfaceHelper *this)
{
  int LastError; // ebx
  HMODULE Library; // rax
  const char *v4; // r9
  __int64 v5; // rdx
  FARPROC ProcAddress; // rax
  int v7; // edi
  __int64 v8; // rcx
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v14; // [rsp+38h] [rbp-D0h]
  RTL_SRWLOCK *v15; // [rsp+40h] [rbp-C8h]
  HMODULE phModule; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B8h] BYREF
  WCHAR Filename[264]; // [rsp+58h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  AcquireSRWLockShared(&g_LoadWUSysLock);
  LastError = 0;
  if ( g_WUSystemInterface )
  {
    ReleaseSRWLockShared(&g_LoadWUSysLock);
    return 0;
  }
  ReleaseSRWLockShared(&g_LoadWUSysLock);
  AcquireSRWLockExclusive(&g_LoadWUSysLock);
  v15 = &g_LoadWUSysLock;
  if ( g_WUSystemInterface )
    goto LABEL_25;
  Library = LoadLibraryExW(L"wusys.dll", 0, 0x880u);
  g_hWUSysModule = Library;
  if ( Library )
  {
    phModule = 0;
    if ( GetModuleFileNameW(Library, Filename, 0x105u) )
      GetModuleHandleExW(1u, Filename, &phModule);
    ProcAddress = GetProcAddress(g_hWUSysModule, (LPCSTR)0xA425);
    if ( ProcAddress )
    {
      v17 = 0;
      v13 = 0;
      LOBYTE(v14) = 1;
      v7 = ((__int64 (__fastcall *)(__int64, __int64 *))ProcAddress)(1, &v13);
      if ( (_BYTE)v14 )
      {
        v8 = v17;
        v17 = v13;
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      if ( v7 >= 0 )
      {
        v11 = g_WUSystemInterface;
        g_WUSystemInterface = 0;
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        v12 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v17)(
                v17,
                &GUID_07186f27_adf4_4d8c_862a_5d403bd2010a,
                &g_WUSystemInterface);
        v7 = v12;
        if ( v12 >= 0 )
        {
          if ( v17 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          goto LABEL_25;
        }
        v9 = (unsigned int)v12;
        v10 = 55;
      }
      else
      {
        v9 = (unsigned int)v7;
        v10 = 54;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusyshelper\\wusyshelper.cpp",
        (const char *)v9,
        (int)&v17);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      goto LABEL_26;
    }
    v5 = 51;
  }
  else
  {
    v5 = 40;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v5,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusyshelper\\wusyshelper.cpp",
                v4);
LABEL_25:
  v7 = LastError;
LABEL_26:
  ReleaseSRWLockExclusive(&g_LoadWUSysLock);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140010c44  mov     rax, rsp
0x140010c47  mov     [rax+8], rbx
0x140010c4b  mov     [rax+10h], rsi
0x140010c4f  mov     [rax+18h], rdi
0x140010c53  push    rbp
0x140010c54  lea     rbp, [rax-178h]
0x140010c5b  sub     rsp, 270h
0x140010c62  mov     rax, cs:__security_cookie
0x140010c69  xor     rax, rsp
0x140010c6c  mov     [rbp+170h+var_10], rax
0x140010c73  lea     rsi, ?g_LoadWUSysLock@@3Vsrwlock@wil@@A; wil::srwlock g_LoadWUSysLock
0x140010c7a  mov     rcx, rsi; SRWLock
0x140010c7d  call    cs:__imp_AcquireSRWLockShared
0x140010c83  xor     ebx, ebx
0x140010c85  mov     rcx, rsi; SRWLock
0x140010c88  cmp     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x140010c8f  jz      short loc_140010C9E
0x140010c91  call    cs:__imp_ReleaseSRWLockShared
0x140010c97  xor     eax, eax
0x140010c99  jmp     loc_140010E47
0x140010c9e  call    cs:__imp_ReleaseSRWLockShared
0x140010ca4  mov     rcx, rsi; SRWLock
0x140010ca7  call    cs:__imp_AcquireSRWLockExclusive
0x140010cad  mov     [rsp+270h+var_238], rsi
0x140010cb2  cmp     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x140010cb9  jnz     loc_140010E3A
0x140010cbf  xor     edx, edx; hFile
0x140010cc1  mov     r8d, 880h; dwFlags
0x140010cc7  lea     rcx, aWusysDll; "wusys.dll"
0x140010cce  call    cs:__imp_LoadLibraryExW
0x140010cd4  mov     cs:?g_hWUSysModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hWUSysModule
0x140010cdb  test    rax, rax
0x140010cde  jnz     short loc_140010CE5
0x140010ce0  lea     edx, [rax+28h]
0x140010ce3  jmp     short loc_140010D33
0x140010ce5  mov     [rsp+270h+phModule], rbx
0x140010cea  mov     r8d, 105h; nSize
0x140010cf0  lea     rdx, [rsp+270h+Filename]; lpFilename
0x140010cf5  mov     rcx, rax; hModule
0x140010cf8  call    cs:__imp_GetModuleFileNameW
0x140010cfe  mov     edi, 1
0x140010d03  test    eax, eax
0x140010d05  jz      short loc_140010D19
0x140010d07  lea     r8, [rsp+270h+phModule]; phModule
0x140010d0c  lea     rdx, [rsp+270h+Filename]; lpModuleName
0x140010d11  mov     ecx, edi; dwFlags
0x140010d13  call    cs:__imp_GetModuleHandleExW
0x140010d19  mov     edx, 0A425h; lpProcName
0x140010d1e  mov     rcx, cs:?g_hWUSysModule@@3PEAUHINSTANCE__@@EA; hModule
0x140010d25  call    cs:__imp_GetProcAddress
0x140010d2b  test    rax, rax
0x140010d2e  jnz     short loc_140010D4D
0x140010d30  lea     edx, [rax+33h]; void *
0x140010d33  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x140010d3a  mov     rcx, [rbp+178h]; this
0x140010d41  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140010d46  mov     ebx, eax
0x140010d48  jmp     loc_140010E3A
0x140010d4d  mov     [rsp+270h+var_228], rbx
0x140010d52  lea     rdx, [rsp+270h+var_228]
0x140010d57  mov     qword ptr [rsp+270h+var_250], rdx; int
0x140010d5c  mov     [rsp+270h+var_248], rbx
0x140010d61  mov     byte ptr [rsp+270h+var_240], dil
0x140010d66  lea     rdx, [rsp+270h+var_248]
0x140010d6b  mov     ecx, edi
0x140010d6d  call    _guard_dispatch_icall
0x140010d72  mov     edi, eax
0x140010d74  cmp     byte ptr [rsp+270h+var_240], bl
0x140010d78  jz      short loc_140010D9C
0x140010d7a  mov     r8, qword ptr [rsp+270h+var_250]
0x140010d7f  mov     rcx, [r8]
0x140010d82  mov     rdx, [rsp+270h+var_248]
0x140010d87  mov     [r8], rdx
0x140010d8a  test    rcx, rcx
0x140010d8d  jz      short loc_140010D9C
0x140010d8f  mov     rax, [rcx]
0x140010d92  mov     rax, [rax+10h]
0x140010d96  call    _guard_dispatch_icall
0x140010d9b  nop
0x140010d9c  test    edi, edi
0x140010d9e  jns     short loc_140010DAA
0x140010da0  mov     r9d, edi
0x140010da3  mov     edx, 36h ; '6'
0x140010da8  jmp     short loc_140010DF6
0x140010daa  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x140010db1  mov     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x140010db8  test    rcx, rcx
0x140010dbb  jz      short loc_140010DCA
0x140010dbd  mov     rax, [rcx]
0x140010dc0  mov     rax, [rax+10h]
0x140010dc4  call    _guard_dispatch_icall
0x140010dc9  nop
0x140010dca  mov     rcx, [rsp+270h+var_228]
0x140010dcf  mov     rax, [rcx]
0x140010dd2  lea     r8, ?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x140010dd9  lea     rdx, _GUID_07186f27_adf4_4d8c_862a_5d403bd2010a
0x140010de0  mov     rax, [rax]
0x140010de3  call    _guard_dispatch_icall
0x140010de8  mov     edi, eax
0x140010dea  test    eax, eax
0x140010dec  jns     short loc_140010E23
0x140010dee  mov     r9d, eax; char *
0x140010df1  mov     edx, 37h ; '7'; void *
0x140010df6  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x140010dfd  mov     rcx, [rbp+178h]; this
0x140010e04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010e09  nop
0x140010e0a  mov     rcx, [rsp+270h+var_228]
0x140010e0f  test    rcx, rcx
0x140010e12  jz      short loc_140010E21
0x140010e14  mov     rax, [rcx]
0x140010e17  mov     rax, [rax+10h]
0x140010e1b  call    _guard_dispatch_icall
0x140010e20  nop
0x140010e21  jmp     short loc_140010E3C
0x140010e23  mov     rcx, [rsp+270h+var_228]
0x140010e28  test    rcx, rcx
0x140010e2b  jz      short loc_140010E3A
0x140010e2d  mov     rax, [rcx]
0x140010e30  mov     rax, [rax+10h]
0x140010e34  call    _guard_dispatch_icall
0x140010e39  nop
0x140010e3a  mov     edi, ebx
0x140010e3c  mov     rcx, rsi; SRWLock
0x140010e3f  call    cs:__imp_ReleaseSRWLockExclusive
0x140010e45  mov     eax, edi
0x140010e47  mov     rcx, [rbp+170h+var_10]
0x140010e4e  xor     rcx, rsp; StackCookie
0x140010e51  call    __security_check_cookie
0x140010e56  lea     r11, [rsp+270h+var_s0]
0x140010e5e  mov     rbx, [r11+10h]
0x140010e62  mov     rsi, [r11+18h]
0x140010e66  mov     rdi, [r11+20h]
0x140010e6a  mov     rsp, r11
0x140010e6d  pop     rbp
0x140010e6e  retn
```
