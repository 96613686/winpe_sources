# WUSystemInterfaceHelper::LoadWUSystemInterface(void)

- ea: `0x1800996cc`
- end: `0x1800998f7`
- name: `?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ`
- size: `555`
- prototype: `__int64 __fastcall(WUSystemInterfaceHelper *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18008673c`
- `0x180099900`
- `0x180099990`

## callees

- `0x180006ac4`
- `0x180007d34`
- `0x1800996cc`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009972f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009972f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180099719`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180099726`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180099719`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180099726`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180099705`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180099705`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800998c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800998c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180099780`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180099780`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18009979b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18009979b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800997ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800997ad`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180099756`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180099756`

## string_xrefs

- `0x18009974f`: `wusys.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
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
0x1800996cc  mov     rax, rsp
0x1800996cf  mov     [rax+8], rbx
0x1800996d3  mov     [rax+10h], rsi
0x1800996d7  mov     [rax+18h], rdi
0x1800996db  push    rbp
0x1800996dc  lea     rbp, [rax-178h]
0x1800996e3  sub     rsp, 270h
0x1800996ea  mov     rax, cs:__security_cookie
0x1800996f1  xor     rax, rsp
0x1800996f4  mov     [rbp+170h+var_10], rax
0x1800996fb  lea     rsi, ?g_LoadWUSysLock@@3Vsrwlock@wil@@A; wil::srwlock g_LoadWUSysLock
0x180099702  mov     rcx, rsi; SRWLock
0x180099705  call    cs:__imp_AcquireSRWLockShared
0x18009970b  xor     ebx, ebx
0x18009970d  mov     rcx, rsi; SRWLock
0x180099710  cmp     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x180099717  jz      short loc_180099726
0x180099719  call    cs:__imp_ReleaseSRWLockShared
0x18009971f  xor     eax, eax
0x180099721  jmp     loc_1800998CF
0x180099726  call    cs:__imp_ReleaseSRWLockShared
0x18009972c  mov     rcx, rsi; SRWLock
0x18009972f  call    cs:__imp_AcquireSRWLockExclusive
0x180099735  mov     [rsp+270h+var_238], rsi
0x18009973a  cmp     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x180099741  jnz     loc_1800998C2
0x180099747  xor     edx, edx; hFile
0x180099749  mov     r8d, 880h; dwFlags
0x18009974f  lea     rcx, aWusysDll; "wusys.dll"
0x180099756  call    cs:__imp_LoadLibraryExW
0x18009975c  mov     cs:?g_hWUSysModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hWUSysModule
0x180099763  test    rax, rax
0x180099766  jnz     short loc_18009976D
0x180099768  lea     edx, [rax+28h]
0x18009976b  jmp     short loc_1800997BB
0x18009976d  mov     [rsp+270h+phModule], rbx
0x180099772  mov     r8d, 105h; nSize
0x180099778  lea     rdx, [rsp+270h+Filename]; lpFilename
0x18009977d  mov     rcx, rax; hModule
0x180099780  call    cs:__imp_GetModuleFileNameW
0x180099786  mov     edi, 1
0x18009978b  test    eax, eax
0x18009978d  jz      short loc_1800997A1
0x18009978f  lea     r8, [rsp+270h+phModule]; phModule
0x180099794  lea     rdx, [rsp+270h+Filename]; lpModuleName
0x180099799  mov     ecx, edi; dwFlags
0x18009979b  call    cs:__imp_GetModuleHandleExW
0x1800997a1  mov     edx, 0A425h; lpProcName
0x1800997a6  mov     rcx, cs:?g_hWUSysModule@@3PEAUHINSTANCE__@@EA; hModule
0x1800997ad  call    cs:__imp_GetProcAddress
0x1800997b3  test    rax, rax
0x1800997b6  jnz     short loc_1800997D5
0x1800997b8  lea     edx, [rax+33h]; void *
0x1800997bb  lea     r8, aCW1SSrcClientL_11; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x1800997c2  mov     rcx, [rbp+178h]; this
0x1800997c9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800997ce  mov     ebx, eax
0x1800997d0  jmp     loc_1800998C2
0x1800997d5  mov     [rsp+270h+var_228], rbx
0x1800997da  lea     rdx, [rsp+270h+var_228]
0x1800997df  mov     qword ptr [rsp+270h+var_250], rdx; int
0x1800997e4  mov     [rsp+270h+var_248], rbx
0x1800997e9  mov     byte ptr [rsp+270h+var_240], dil
0x1800997ee  lea     rdx, [rsp+270h+var_248]
0x1800997f3  mov     ecx, edi
0x1800997f5  call    _guard_dispatch_icall
0x1800997fa  mov     edi, eax
0x1800997fc  cmp     byte ptr [rsp+270h+var_240], bl
0x180099800  jz      short loc_180099824
0x180099802  mov     r8, qword ptr [rsp+270h+var_250]
0x180099807  mov     rcx, [r8]
0x18009980a  mov     rdx, [rsp+270h+var_248]
0x18009980f  mov     [r8], rdx
0x180099812  test    rcx, rcx
0x180099815  jz      short loc_180099824
0x180099817  mov     rax, [rcx]
0x18009981a  mov     rax, [rax+10h]
0x18009981e  call    _guard_dispatch_icall
0x180099823  nop
0x180099824  test    edi, edi
0x180099826  jns     short loc_180099832
0x180099828  mov     r9d, edi
0x18009982b  mov     edx, 36h ; '6'
0x180099830  jmp     short loc_18009987E
0x180099832  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x180099839  mov     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x180099840  test    rcx, rcx
0x180099843  jz      short loc_180099852
0x180099845  mov     rax, [rcx]
0x180099848  mov     rax, [rax+10h]
0x18009984c  call    _guard_dispatch_icall
0x180099851  nop
0x180099852  mov     rcx, [rsp+270h+var_228]
0x180099857  mov     rax, [rcx]
0x18009985a  lea     r8, ?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x180099861  lea     rdx, _GUID_07186f27_adf4_4d8c_862a_5d403bd2010a
0x180099868  mov     rax, [rax]
0x18009986b  call    _guard_dispatch_icall
0x180099870  mov     edi, eax
0x180099872  test    eax, eax
0x180099874  jns     short loc_1800998AB
0x180099876  mov     r9d, eax; char *
0x180099879  mov     edx, 37h ; '7'; void *
0x18009987e  lea     r8, aCW1SSrcClientL_11; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x180099885  mov     rcx, [rbp+178h]; this
0x18009988c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099891  nop
0x180099892  mov     rcx, [rsp+270h+var_228]
0x180099897  test    rcx, rcx
0x18009989a  jz      short loc_1800998A9
0x18009989c  mov     rax, [rcx]
0x18009989f  mov     rax, [rax+10h]
0x1800998a3  call    _guard_dispatch_icall
0x1800998a8  nop
0x1800998a9  jmp     short loc_1800998C4
0x1800998ab  mov     rcx, [rsp+270h+var_228]
0x1800998b0  test    rcx, rcx
0x1800998b3  jz      short loc_1800998C2
0x1800998b5  mov     rax, [rcx]
0x1800998b8  mov     rax, [rax+10h]
0x1800998bc  call    _guard_dispatch_icall
0x1800998c1  nop
0x1800998c2  mov     edi, ebx
0x1800998c4  mov     rcx, rsi; SRWLock
0x1800998c7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800998cd  mov     eax, edi
0x1800998cf  mov     rcx, [rbp+170h+var_10]
0x1800998d6  xor     rcx, rsp; StackCookie
0x1800998d9  call    __security_check_cookie
0x1800998de  lea     r11, [rsp+270h+var_s0]
0x1800998e6  mov     rbx, [r11+10h]
0x1800998ea  mov     rsi, [r11+18h]
0x1800998ee  mov     rdi, [r11+20h]
0x1800998f2  mov     rsp, r11
0x1800998f5  pop     rbp
0x1800998f6  retn
```
