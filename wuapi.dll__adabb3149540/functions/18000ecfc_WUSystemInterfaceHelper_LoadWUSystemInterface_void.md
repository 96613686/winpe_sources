# WUSystemInterfaceHelper::LoadWUSystemInterface(void)

- ea: `0x18000ecfc`
- end: `0x18000ef27`
- name: `?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ`
- size: `555`
- prototype: `__int64 __fastcall(WUSystemInterfaceHelper *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000ef30`

## callees

- `0x180003760`
- `0x180003784`
- `0x18000ecfc`
- `0x18000fce0`
- `0x180015a00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ed86`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ed86`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000eddd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000eddd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000edcb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000edcb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000edb0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000edb0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ed5f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ed5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ed49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ed56`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ed49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ed56`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000ed35`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000ed35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eef7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eef7`

## string_xrefs

- `0x18000ed7f`: `wusys.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000ecfc  mov     rax, rsp
0x18000ecff  mov     [rax+8], rbx
0x18000ed03  mov     [rax+10h], rsi
0x18000ed07  mov     [rax+18h], rdi
0x18000ed0b  push    rbp
0x18000ed0c  lea     rbp, [rax-178h]
0x18000ed13  sub     rsp, 270h
0x18000ed1a  mov     rax, cs:__security_cookie
0x18000ed21  xor     rax, rsp
0x18000ed24  mov     [rbp+170h+var_10], rax
0x18000ed2b  lea     rsi, ?g_LoadWUSysLock@@3Vsrwlock@wil@@A; wil::srwlock g_LoadWUSysLock
0x18000ed32  mov     rcx, rsi; SRWLock
0x18000ed35  call    cs:__imp_AcquireSRWLockShared
0x18000ed3b  xor     ebx, ebx
0x18000ed3d  mov     rcx, rsi; SRWLock
0x18000ed40  cmp     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18000ed47  jz      short loc_18000ED56
0x18000ed49  call    cs:__imp_ReleaseSRWLockShared
0x18000ed4f  xor     eax, eax
0x18000ed51  jmp     loc_18000EEFF
0x18000ed56  call    cs:__imp_ReleaseSRWLockShared
0x18000ed5c  mov     rcx, rsi; SRWLock
0x18000ed5f  call    cs:__imp_AcquireSRWLockExclusive
0x18000ed65  mov     [rsp+270h+var_238], rsi
0x18000ed6a  cmp     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18000ed71  jnz     loc_18000EEF2
0x18000ed77  xor     edx, edx; hFile
0x18000ed79  mov     r8d, 880h; dwFlags
0x18000ed7f  lea     rcx, LibFileName; "wusys.dll"
0x18000ed86  call    cs:__imp_LoadLibraryExW
0x18000ed8c  mov     cs:?g_hWUSysModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hWUSysModule
0x18000ed93  test    rax, rax
0x18000ed96  jnz     short loc_18000ED9D
0x18000ed98  lea     edx, [rax+28h]
0x18000ed9b  jmp     short loc_18000EDEB
0x18000ed9d  mov     [rsp+270h+phModule], rbx
0x18000eda2  mov     r8d, 105h; nSize
0x18000eda8  lea     rdx, [rsp+270h+Filename]; lpFilename
0x18000edad  mov     rcx, rax; hModule
0x18000edb0  call    cs:__imp_GetModuleFileNameW
0x18000edb6  mov     edi, 1
0x18000edbb  test    eax, eax
0x18000edbd  jz      short loc_18000EDD1
0x18000edbf  lea     r8, [rsp+270h+phModule]; phModule
0x18000edc4  lea     rdx, [rsp+270h+Filename]; lpModuleName
0x18000edc9  mov     ecx, edi; dwFlags
0x18000edcb  call    cs:__imp_GetModuleHandleExW
0x18000edd1  mov     edx, 0A425h; lpProcName
0x18000edd6  mov     rcx, cs:?g_hWUSysModule@@3PEAUHINSTANCE__@@EA; hModule
0x18000eddd  call    cs:__imp_GetProcAddress
0x18000ede3  test    rax, rax
0x18000ede6  jnz     short loc_18000EE05
0x18000ede8  lea     edx, [rax+33h]; void *
0x18000edeb  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x18000edf2  mov     rcx, [rbp+178h]; this
0x18000edf9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000edfe  mov     ebx, eax
0x18000ee00  jmp     loc_18000EEF2
0x18000ee05  mov     [rsp+270h+var_228], rbx
0x18000ee0a  lea     rdx, [rsp+270h+var_228]
0x18000ee0f  mov     qword ptr [rsp+270h+var_250], rdx; int
0x18000ee14  mov     [rsp+270h+var_248], rbx
0x18000ee19  mov     byte ptr [rsp+270h+var_240], dil
0x18000ee1e  lea     rdx, [rsp+270h+var_248]
0x18000ee23  mov     ecx, edi
0x18000ee25  call    _guard_dispatch_icall
0x18000ee2a  mov     edi, eax
0x18000ee2c  cmp     byte ptr [rsp+270h+var_240], bl
0x18000ee30  jz      short loc_18000EE54
0x18000ee32  mov     r8, qword ptr [rsp+270h+var_250]
0x18000ee37  mov     rcx, [r8]
0x18000ee3a  mov     rdx, [rsp+270h+var_248]
0x18000ee3f  mov     [r8], rdx
0x18000ee42  test    rcx, rcx
0x18000ee45  jz      short loc_18000EE54
0x18000ee47  mov     rax, [rcx]
0x18000ee4a  mov     rax, [rax+10h]
0x18000ee4e  call    _guard_dispatch_icall
0x18000ee53  nop
0x18000ee54  test    edi, edi
0x18000ee56  jns     short loc_18000EE62
0x18000ee58  mov     r9d, edi
0x18000ee5b  mov     edx, 36h ; '6'
0x18000ee60  jmp     short loc_18000EEAE
0x18000ee62  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18000ee69  mov     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18000ee70  test    rcx, rcx
0x18000ee73  jz      short loc_18000EE82
0x18000ee75  mov     rax, [rcx]
0x18000ee78  mov     rax, [rax+10h]
0x18000ee7c  call    _guard_dispatch_icall
0x18000ee81  nop
0x18000ee82  mov     rcx, [rsp+270h+var_228]
0x18000ee87  mov     rax, [rcx]
0x18000ee8a  lea     r8, ?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18000ee91  lea     rdx, _GUID_07186f27_adf4_4d8c_862a_5d403bd2010a
0x18000ee98  mov     rax, [rax]
0x18000ee9b  call    _guard_dispatch_icall
0x18000eea0  mov     edi, eax
0x18000eea2  test    eax, eax
0x18000eea4  jns     short loc_18000EEDB
0x18000eea6  mov     r9d, eax; char *
0x18000eea9  mov     edx, 37h ; '7'; void *
0x18000eeae  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x18000eeb5  mov     rcx, [rbp+178h]; this
0x18000eebc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eec1  nop
0x18000eec2  mov     rcx, [rsp+270h+var_228]
0x18000eec7  test    rcx, rcx
0x18000eeca  jz      short loc_18000EED9
0x18000eecc  mov     rax, [rcx]
0x18000eecf  mov     rax, [rax+10h]
0x18000eed3  call    _guard_dispatch_icall
0x18000eed8  nop
0x18000eed9  jmp     short loc_18000EEF4
0x18000eedb  mov     rcx, [rsp+270h+var_228]
0x18000eee0  test    rcx, rcx
0x18000eee3  jz      short loc_18000EEF2
0x18000eee5  mov     rax, [rcx]
0x18000eee8  mov     rax, [rax+10h]
0x18000eeec  call    _guard_dispatch_icall
0x18000eef1  nop
0x18000eef2  mov     edi, ebx
0x18000eef4  mov     rcx, rsi; SRWLock
0x18000eef7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000eefd  mov     eax, edi
0x18000eeff  mov     rcx, [rbp+170h+var_10]
0x18000ef06  xor     rcx, rsp; StackCookie
0x18000ef09  call    __security_check_cookie
0x18000ef0e  lea     r11, [rsp+270h+var_s0]
0x18000ef16  mov     rbx, [r11+10h]
0x18000ef1a  mov     rsi, [r11+18h]
0x18000ef1e  mov     rdi, [r11+20h]
0x18000ef22  mov     rsp, r11
0x18000ef25  pop     rbp
0x18000ef26  retn
```
