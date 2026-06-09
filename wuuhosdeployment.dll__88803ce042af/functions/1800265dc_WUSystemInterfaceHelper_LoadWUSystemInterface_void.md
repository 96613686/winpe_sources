# WUSystemInterfaceHelper::LoadWUSystemInterface(void)

- ea: `0x1800265dc`
- end: `0x180026807`
- name: `?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ`
- size: `555`
- prototype: `__int64 __fastcall(WUSystemInterfaceHelper *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180026810`
- `0x180031804`
- `0x18003a118`

## callees

- `0x180003950`
- `0x180003974`
- `0x1800265dc`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180026690`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180026690`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180026666`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180026666`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800266ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800266ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800266bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800266bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002663f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002663f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800267d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800267d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180026615`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180026615`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180026629`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180026636`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180026629`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180026636`

## string_xrefs

- `0x18002665f`: `wusys.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x1800265dc  mov     rax, rsp
0x1800265df  mov     [rax+8], rbx
0x1800265e3  mov     [rax+10h], rsi
0x1800265e7  mov     [rax+18h], rdi
0x1800265eb  push    rbp
0x1800265ec  lea     rbp, [rax-178h]
0x1800265f3  sub     rsp, 270h
0x1800265fa  mov     rax, cs:__security_cookie
0x180026601  xor     rax, rsp
0x180026604  mov     [rbp+170h+var_10], rax
0x18002660b  lea     rsi, ?g_LoadWUSysLock@@3Vsrwlock@wil@@A; wil::srwlock g_LoadWUSysLock
0x180026612  mov     rcx, rsi; SRWLock
0x180026615  call    cs:__imp_AcquireSRWLockShared
0x18002661b  xor     ebx, ebx
0x18002661d  mov     rcx, rsi; SRWLock
0x180026620  cmp     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x180026627  jz      short loc_180026636
0x180026629  call    cs:__imp_ReleaseSRWLockShared
0x18002662f  xor     eax, eax
0x180026631  jmp     loc_1800267DF
0x180026636  call    cs:__imp_ReleaseSRWLockShared
0x18002663c  mov     rcx, rsi; SRWLock
0x18002663f  call    cs:__imp_AcquireSRWLockExclusive
0x180026645  mov     [rsp+270h+var_238], rsi
0x18002664a  cmp     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x180026651  jnz     loc_1800267D2
0x180026657  xor     edx, edx; hFile
0x180026659  mov     r8d, 880h; dwFlags
0x18002665f  lea     rcx, aWusysDll; "wusys.dll"
0x180026666  call    cs:__imp_LoadLibraryExW
0x18002666c  mov     cs:?g_hWUSysModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hWUSysModule
0x180026673  test    rax, rax
0x180026676  jnz     short loc_18002667D
0x180026678  lea     edx, [rax+28h]
0x18002667b  jmp     short loc_1800266CB
0x18002667d  mov     [rsp+270h+phModule], rbx
0x180026682  mov     r8d, 105h; nSize
0x180026688  lea     rdx, [rsp+270h+Filename]; lpFilename
0x18002668d  mov     rcx, rax; hModule
0x180026690  call    cs:__imp_GetModuleFileNameW
0x180026696  mov     edi, 1
0x18002669b  test    eax, eax
0x18002669d  jz      short loc_1800266B1
0x18002669f  lea     r8, [rsp+270h+phModule]; phModule
0x1800266a4  lea     rdx, [rsp+270h+Filename]; lpModuleName
0x1800266a9  mov     ecx, edi; dwFlags
0x1800266ab  call    cs:__imp_GetModuleHandleExW
0x1800266b1  mov     edx, 0A425h; lpProcName
0x1800266b6  mov     rcx, cs:?g_hWUSysModule@@3PEAUHINSTANCE__@@EA; hModule
0x1800266bd  call    cs:__imp_GetProcAddress
0x1800266c3  test    rax, rax
0x1800266c6  jnz     short loc_1800266E5
0x1800266c8  lea     edx, [rax+33h]; void *
0x1800266cb  lea     r8, aCW1SSrcClientL_11; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x1800266d2  mov     rcx, [rbp+178h]; this
0x1800266d9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800266de  mov     ebx, eax
0x1800266e0  jmp     loc_1800267D2
0x1800266e5  mov     [rsp+270h+var_228], rbx
0x1800266ea  lea     rdx, [rsp+270h+var_228]
0x1800266ef  mov     qword ptr [rsp+270h+var_250], rdx; int
0x1800266f4  mov     [rsp+270h+var_248], rbx
0x1800266f9  mov     byte ptr [rsp+270h+var_240], dil
0x1800266fe  lea     rdx, [rsp+270h+var_248]
0x180026703  mov     ecx, edi
0x180026705  call    _guard_dispatch_icall
0x18002670a  mov     edi, eax
0x18002670c  cmp     byte ptr [rsp+270h+var_240], bl
0x180026710  jz      short loc_180026734
0x180026712  mov     r8, qword ptr [rsp+270h+var_250]
0x180026717  mov     rcx, [r8]
0x18002671a  mov     rdx, [rsp+270h+var_248]
0x18002671f  mov     [r8], rdx
0x180026722  test    rcx, rcx
0x180026725  jz      short loc_180026734
0x180026727  mov     rax, [rcx]
0x18002672a  mov     rax, [rax+10h]
0x18002672e  call    _guard_dispatch_icall
0x180026733  nop
0x180026734  test    edi, edi
0x180026736  jns     short loc_180026742
0x180026738  mov     r9d, edi
0x18002673b  mov     edx, 36h ; '6'
0x180026740  jmp     short loc_18002678E
0x180026742  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x180026749  mov     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x180026750  test    rcx, rcx
0x180026753  jz      short loc_180026762
0x180026755  mov     rax, [rcx]
0x180026758  mov     rax, [rax+10h]
0x18002675c  call    _guard_dispatch_icall
0x180026761  nop
0x180026762  mov     rcx, [rsp+270h+var_228]
0x180026767  mov     rax, [rcx]
0x18002676a  lea     r8, ?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x180026771  lea     rdx, _GUID_07186f27_adf4_4d8c_862a_5d403bd2010a
0x180026778  mov     rax, [rax]
0x18002677b  call    _guard_dispatch_icall
0x180026780  mov     edi, eax
0x180026782  test    eax, eax
0x180026784  jns     short loc_1800267BB
0x180026786  mov     r9d, eax; char *
0x180026789  mov     edx, 37h ; '7'; void *
0x18002678e  lea     r8, aCW1SSrcClientL_11; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x180026795  mov     rcx, [rbp+178h]; this
0x18002679c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800267a1  nop
0x1800267a2  mov     rcx, [rsp+270h+var_228]
0x1800267a7  test    rcx, rcx
0x1800267aa  jz      short loc_1800267B9
0x1800267ac  mov     rax, [rcx]
0x1800267af  mov     rax, [rax+10h]
0x1800267b3  call    _guard_dispatch_icall
0x1800267b8  nop
0x1800267b9  jmp     short loc_1800267D4
0x1800267bb  mov     rcx, [rsp+270h+var_228]
0x1800267c0  test    rcx, rcx
0x1800267c3  jz      short loc_1800267D2
0x1800267c5  mov     rax, [rcx]
0x1800267c8  mov     rax, [rax+10h]
0x1800267cc  call    _guard_dispatch_icall
0x1800267d1  nop
0x1800267d2  mov     edi, ebx
0x1800267d4  mov     rcx, rsi; SRWLock
0x1800267d7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800267dd  mov     eax, edi
0x1800267df  mov     rcx, [rbp+170h+var_10]
0x1800267e6  xor     rcx, rsp; StackCookie
0x1800267e9  call    __security_check_cookie
0x1800267ee  lea     r11, [rsp+270h+var_s0]
0x1800267f6  mov     rbx, [r11+10h]
0x1800267fa  mov     rsi, [r11+18h]
0x1800267fe  mov     rdi, [r11+20h]
0x180026802  mov     rsp, r11
0x180026805  pop     rbp
0x180026806  retn
```
