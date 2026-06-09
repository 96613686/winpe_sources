# WUSystemInterfaceHelper::LoadWUSystemInterface(void)

- ea: `0x18000ecac`
- end: `0x18000eed7`
- name: `?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ`
- size: `555`
- prototype: `__int64 __fastcall(WUSystemInterfaceHelper *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000eee0`

## callees

- `0x180003760`
- `0x180003784`
- `0x18000ecac`
- `0x18000fc90`
- `0x1800159b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ed36`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ed36`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ed8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ed8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000ed60`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000ed60`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000ed7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000ed7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000ece5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000ece5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ecf9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ed06`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ecf9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ed06`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ed0f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ed0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eea7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eea7`

## string_xrefs

- `0x18000ed2f`: `wusys.dll`

## pseudocode

```c
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
0x18000ecac  mov     rax, rsp
0x18000ecaf  mov     [rax+8], rbx
0x18000ecb3  mov     [rax+10h], rsi
0x18000ecb7  mov     [rax+18h], rdi
0x18000ecbb  push    rbp
0x18000ecbc  lea     rbp, [rax-178h]
0x18000ecc3  sub     rsp, 270h
0x18000ecca  mov     rax, cs:__security_cookie
0x18000ecd1  xor     rax, rsp
0x18000ecd4  mov     [rbp+170h+var_10], rax
0x18000ecdb  lea     rsi, ?g_LoadWUSysLock@@3Vsrwlock@wil@@A; wil::srwlock g_LoadWUSysLock
0x18000ece2  mov     rcx, rsi; SRWLock
0x18000ece5  call    cs:__imp_AcquireSRWLockShared
0x18000eceb  xor     ebx, ebx
0x18000eced  mov     rcx, rsi; SRWLock
0x18000ecf0  cmp     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18000ecf7  jz      short loc_18000ED06
0x18000ecf9  call    cs:__imp_ReleaseSRWLockShared
0x18000ecff  xor     eax, eax
0x18000ed01  jmp     loc_18000EEAF
0x18000ed06  call    cs:__imp_ReleaseSRWLockShared
0x18000ed0c  mov     rcx, rsi; SRWLock
0x18000ed0f  call    cs:__imp_AcquireSRWLockExclusive
0x18000ed15  mov     [rsp+270h+var_238], rsi
0x18000ed1a  cmp     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18000ed21  jnz     loc_18000EEA2
0x18000ed27  xor     edx, edx; hFile
0x18000ed29  mov     r8d, 880h; dwFlags
0x18000ed2f  lea     rcx, LibFileName; "wusys.dll"
0x18000ed36  call    cs:__imp_LoadLibraryExW
0x18000ed3c  mov     cs:?g_hWUSysModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hWUSysModule
0x18000ed43  test    rax, rax
0x18000ed46  jnz     short loc_18000ED4D
0x18000ed48  lea     edx, [rax+28h]
0x18000ed4b  jmp     short loc_18000ED9B
0x18000ed4d  mov     [rsp+270h+phModule], rbx
0x18000ed52  mov     r8d, 105h; nSize
0x18000ed58  lea     rdx, [rsp+270h+Filename]; lpFilename
0x18000ed5d  mov     rcx, rax; hModule
0x18000ed60  call    cs:__imp_GetModuleFileNameW
0x18000ed66  mov     edi, 1
0x18000ed6b  test    eax, eax
0x18000ed6d  jz      short loc_18000ED81
0x18000ed6f  lea     r8, [rsp+270h+phModule]; phModule
0x18000ed74  lea     rdx, [rsp+270h+Filename]; lpModuleName
0x18000ed79  mov     ecx, edi; dwFlags
0x18000ed7b  call    cs:__imp_GetModuleHandleExW
0x18000ed81  mov     edx, 0A425h; lpProcName
0x18000ed86  mov     rcx, cs:?g_hWUSysModule@@3PEAUHINSTANCE__@@EA; hModule
0x18000ed8d  call    cs:__imp_GetProcAddress
0x18000ed93  test    rax, rax
0x18000ed96  jnz     short loc_18000EDB5
0x18000ed98  lea     edx, [rax+33h]; void *
0x18000ed9b  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x18000eda2  mov     rcx, [rbp+178h]; this
0x18000eda9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000edae  mov     ebx, eax
0x18000edb0  jmp     loc_18000EEA2
0x18000edb5  mov     [rsp+270h+var_228], rbx
0x18000edba  lea     rdx, [rsp+270h+var_228]
0x18000edbf  mov     qword ptr [rsp+270h+var_250], rdx; int
0x18000edc4  mov     [rsp+270h+var_248], rbx
0x18000edc9  mov     byte ptr [rsp+270h+var_240], dil
0x18000edce  lea     rdx, [rsp+270h+var_248]
0x18000edd3  mov     ecx, edi
0x18000edd5  call    _guard_dispatch_icall
0x18000edda  mov     edi, eax
0x18000eddc  cmp     byte ptr [rsp+270h+var_240], bl
0x18000ede0  jz      short loc_18000EE04
0x18000ede2  mov     r8, qword ptr [rsp+270h+var_250]
0x18000ede7  mov     rcx, [r8]
0x18000edea  mov     rdx, [rsp+270h+var_248]
0x18000edef  mov     [r8], rdx
0x18000edf2  test    rcx, rcx
0x18000edf5  jz      short loc_18000EE04
0x18000edf7  mov     rax, [rcx]
0x18000edfa  mov     rax, [rax+10h]
0x18000edfe  call    _guard_dispatch_icall
0x18000ee03  nop
0x18000ee04  test    edi, edi
0x18000ee06  jns     short loc_18000EE12
0x18000ee08  mov     r9d, edi
0x18000ee0b  mov     edx, 36h ; '6'
0x18000ee10  jmp     short loc_18000EE5E
0x18000ee12  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18000ee19  mov     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18000ee20  test    rcx, rcx
0x18000ee23  jz      short loc_18000EE32
0x18000ee25  mov     rax, [rcx]
0x18000ee28  mov     rax, [rax+10h]
0x18000ee2c  call    _guard_dispatch_icall
0x18000ee31  nop
0x18000ee32  mov     rcx, [rsp+270h+var_228]
0x18000ee37  mov     rax, [rcx]
0x18000ee3a  lea     r8, ?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18000ee41  lea     rdx, _GUID_07186f27_adf4_4d8c_862a_5d403bd2010a
0x18000ee48  mov     rax, [rax]
0x18000ee4b  call    _guard_dispatch_icall
0x18000ee50  mov     edi, eax
0x18000ee52  test    eax, eax
0x18000ee54  jns     short loc_18000EE8B
0x18000ee56  mov     r9d, eax; char *
0x18000ee59  mov     edx, 37h ; '7'; void *
0x18000ee5e  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x18000ee65  mov     rcx, [rbp+178h]; this
0x18000ee6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ee71  nop
0x18000ee72  mov     rcx, [rsp+270h+var_228]
0x18000ee77  test    rcx, rcx
0x18000ee7a  jz      short loc_18000EE89
0x18000ee7c  mov     rax, [rcx]
0x18000ee7f  mov     rax, [rax+10h]
0x18000ee83  call    _guard_dispatch_icall
0x18000ee88  nop
0x18000ee89  jmp     short loc_18000EEA4
0x18000ee8b  mov     rcx, [rsp+270h+var_228]
0x18000ee90  test    rcx, rcx
0x18000ee93  jz      short loc_18000EEA2
0x18000ee95  mov     rax, [rcx]
0x18000ee98  mov     rax, [rax+10h]
0x18000ee9c  call    _guard_dispatch_icall
0x18000eea1  nop
0x18000eea2  mov     edi, ebx
0x18000eea4  mov     rcx, rsi; SRWLock
0x18000eea7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000eead  mov     eax, edi
0x18000eeaf  mov     rcx, [rbp+170h+var_10]
0x18000eeb6  xor     rcx, rsp; StackCookie
0x18000eeb9  call    __security_check_cookie
0x18000eebe  lea     r11, [rsp+270h+var_s0]
0x18000eec6  mov     rbx, [r11+10h]
0x18000eeca  mov     rsi, [r11+18h]
0x18000eece  mov     rdi, [r11+20h]
0x18000eed2  mov     rsp, r11
0x18000eed5  pop     rbp
0x18000eed6  retn
```
