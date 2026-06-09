# WUSystemInterfaceHelper::LoadWUSystemInterface(void)

- ea: `0x18002d3fc`
- end: `0x18002d627`
- name: `?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ`
- size: `555`
- prototype: `__int64 __fastcall(WUSystemInterfaceHelper *__hidden this)`
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000d590`
- `0x18002d630`
- `0x18002d6a0`
- `0x18002d730`
- `0x18002d85c`
- `0x18002d99c`

## callees

- `0x18000aac0`
- `0x18000aae4`
- `0x18002d3fc`
- `0x18002ffd0`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d486`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d486`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002d4b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002d4b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002d4cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002d4cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d4dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d4dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002d435`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002d435`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002d449`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002d456`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002d449`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002d456`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d45f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d45f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002d5f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002d5f7`

## string_xrefs

- `0x18002d47f`: `wusys.dll`

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
0x18002d3fc  mov     rax, rsp
0x18002d3ff  mov     [rax+8], rbx
0x18002d403  mov     [rax+10h], rsi
0x18002d407  mov     [rax+18h], rdi
0x18002d40b  push    rbp
0x18002d40c  lea     rbp, [rax-178h]
0x18002d413  sub     rsp, 270h
0x18002d41a  mov     rax, cs:__security_cookie
0x18002d421  xor     rax, rsp
0x18002d424  mov     [rbp+170h+var_10], rax
0x18002d42b  lea     rsi, ?g_LoadWUSysLock@@3Vsrwlock@wil@@A; wil::srwlock g_LoadWUSysLock
0x18002d432  mov     rcx, rsi; SRWLock
0x18002d435  call    cs:__imp_AcquireSRWLockShared
0x18002d43b  xor     ebx, ebx
0x18002d43d  mov     rcx, rsi; SRWLock
0x18002d440  cmp     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18002d447  jz      short loc_18002D456
0x18002d449  call    cs:__imp_ReleaseSRWLockShared
0x18002d44f  xor     eax, eax
0x18002d451  jmp     loc_18002D5FF
0x18002d456  call    cs:__imp_ReleaseSRWLockShared
0x18002d45c  mov     rcx, rsi; SRWLock
0x18002d45f  call    cs:__imp_AcquireSRWLockExclusive
0x18002d465  mov     [rsp+270h+var_238], rsi
0x18002d46a  cmp     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18002d471  jnz     loc_18002D5F2
0x18002d477  xor     edx, edx; hFile
0x18002d479  mov     r8d, 880h; dwFlags
0x18002d47f  lea     rcx, aWusysDll; "wusys.dll"
0x18002d486  call    cs:__imp_LoadLibraryExW
0x18002d48c  mov     cs:?g_hWUSysModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hWUSysModule
0x18002d493  test    rax, rax
0x18002d496  jnz     short loc_18002D49D
0x18002d498  lea     edx, [rax+28h]
0x18002d49b  jmp     short loc_18002D4EB
0x18002d49d  mov     [rsp+270h+phModule], rbx
0x18002d4a2  mov     r8d, 105h; nSize
0x18002d4a8  lea     rdx, [rsp+270h+Filename]; lpFilename
0x18002d4ad  mov     rcx, rax; hModule
0x18002d4b0  call    cs:__imp_GetModuleFileNameW
0x18002d4b6  mov     edi, 1
0x18002d4bb  test    eax, eax
0x18002d4bd  jz      short loc_18002D4D1
0x18002d4bf  lea     r8, [rsp+270h+phModule]; phModule
0x18002d4c4  lea     rdx, [rsp+270h+Filename]; lpModuleName
0x18002d4c9  mov     ecx, edi; dwFlags
0x18002d4cb  call    cs:__imp_GetModuleHandleExW
0x18002d4d1  mov     edx, 0A425h; lpProcName
0x18002d4d6  mov     rcx, cs:?g_hWUSysModule@@3PEAUHINSTANCE__@@EA; hModule
0x18002d4dd  call    cs:__imp_GetProcAddress
0x18002d4e3  test    rax, rax
0x18002d4e6  jnz     short loc_18002D505
0x18002d4e8  lea     edx, [rax+33h]; void *
0x18002d4eb  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x18002d4f2  mov     rcx, [rbp+178h]; this
0x18002d4f9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d4fe  mov     ebx, eax
0x18002d500  jmp     loc_18002D5F2
0x18002d505  mov     [rsp+270h+var_228], rbx
0x18002d50a  lea     rdx, [rsp+270h+var_228]
0x18002d50f  mov     qword ptr [rsp+270h+var_250], rdx; int
0x18002d514  mov     [rsp+270h+var_248], rbx
0x18002d519  mov     byte ptr [rsp+270h+var_240], dil
0x18002d51e  lea     rdx, [rsp+270h+var_248]
0x18002d523  mov     ecx, edi
0x18002d525  call    _guard_dispatch_icall
0x18002d52a  mov     edi, eax
0x18002d52c  cmp     byte ptr [rsp+270h+var_240], bl
0x18002d530  jz      short loc_18002D554
0x18002d532  mov     r8, qword ptr [rsp+270h+var_250]
0x18002d537  mov     rcx, [r8]
0x18002d53a  mov     rdx, [rsp+270h+var_248]
0x18002d53f  mov     [r8], rdx
0x18002d542  test    rcx, rcx
0x18002d545  jz      short loc_18002D554
0x18002d547  mov     rax, [rcx]
0x18002d54a  mov     rax, [rax+10h]
0x18002d54e  call    _guard_dispatch_icall
0x18002d553  nop
0x18002d554  test    edi, edi
0x18002d556  jns     short loc_18002D562
0x18002d558  mov     r9d, edi
0x18002d55b  mov     edx, 36h ; '6'
0x18002d560  jmp     short loc_18002D5AE
0x18002d562  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18002d569  mov     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18002d570  test    rcx, rcx
0x18002d573  jz      short loc_18002D582
0x18002d575  mov     rax, [rcx]
0x18002d578  mov     rax, [rax+10h]
0x18002d57c  call    _guard_dispatch_icall
0x18002d581  nop
0x18002d582  mov     rcx, [rsp+270h+var_228]
0x18002d587  mov     rax, [rcx]
0x18002d58a  lea     r8, ?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18002d591  lea     rdx, _GUID_07186f27_adf4_4d8c_862a_5d403bd2010a
0x18002d598  mov     rax, [rax]
0x18002d59b  call    _guard_dispatch_icall
0x18002d5a0  mov     edi, eax
0x18002d5a2  test    eax, eax
0x18002d5a4  jns     short loc_18002D5DB
0x18002d5a6  mov     r9d, eax; char *
0x18002d5a9  mov     edx, 37h ; '7'; void *
0x18002d5ae  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x18002d5b5  mov     rcx, [rbp+178h]; this
0x18002d5bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d5c1  nop
0x18002d5c2  mov     rcx, [rsp+270h+var_228]
0x18002d5c7  test    rcx, rcx
0x18002d5ca  jz      short loc_18002D5D9
0x18002d5cc  mov     rax, [rcx]
0x18002d5cf  mov     rax, [rax+10h]
0x18002d5d3  call    _guard_dispatch_icall
0x18002d5d8  nop
0x18002d5d9  jmp     short loc_18002D5F4
0x18002d5db  mov     rcx, [rsp+270h+var_228]
0x18002d5e0  test    rcx, rcx
0x18002d5e3  jz      short loc_18002D5F2
0x18002d5e5  mov     rax, [rcx]
0x18002d5e8  mov     rax, [rax+10h]
0x18002d5ec  call    _guard_dispatch_icall
0x18002d5f1  nop
0x18002d5f2  mov     edi, ebx
0x18002d5f4  mov     rcx, rsi; SRWLock
0x18002d5f7  call    cs:__imp_ReleaseSRWLockExclusive
0x18002d5fd  mov     eax, edi
0x18002d5ff  mov     rcx, [rbp+170h+var_10]
0x18002d606  xor     rcx, rsp; StackCookie
0x18002d609  call    __security_check_cookie
0x18002d60e  lea     r11, [rsp+270h+var_s0]
0x18002d616  mov     rbx, [r11+10h]
0x18002d61a  mov     rsi, [r11+18h]
0x18002d61e  mov     rdi, [r11+20h]
0x18002d622  mov     rsp, r11
0x18002d625  pop     rbp
0x18002d626  retn
```
