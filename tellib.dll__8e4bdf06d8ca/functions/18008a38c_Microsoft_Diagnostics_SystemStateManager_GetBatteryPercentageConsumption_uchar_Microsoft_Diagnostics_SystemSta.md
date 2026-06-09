# Microsoft::Diagnostics::SystemStateManager::GetBatteryPercentageConsumption(uchar &,Microsoft::Diagnostics::SystemStateManager::BatteryInfo const &)

- ea: `0x18008a38c`
- end: `0x18008a6af`
- name: `?GetBatteryPercentageConsumption@SystemStateManager@Diagnostics@Microsoft@@CA_NAEAEAEBUBatteryInfo@123@@Z`
- size: `803`
- prototype: `bool __fastcall(unsigned __int8 *, const struct Microsoft::Diagnostics::SystemStateManager::BatteryInfo *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18010a900`
- `0x18019eafc`

## callees

- `0x180053a84`
- `0x18008a38c`
- `0x18008b3c8`
- `0x1800a1e24`
- `0x18012de40`
- `0x180173794`
- `0x18019c3f4`
- `0x18019e3d0`
- `0x180346010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008a3f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008a424`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008a3f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008a424`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18008a496`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18008a496`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18008a465`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18008a465`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18008a3ca`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18008a3ca`

## string_xrefs

- `0x18008a408`: `onecore\base\telemetry\utc\service\engine\systemstatemanager.cpp`
- `0x18008a43c`: `onecore\base\telemetry\utc\service\engine\systemstatemanager.cpp`
- `0x18008a479`: `onecore\base\telemetry\utc\service\engine\systemstatemanager.cpp`
- `0x18008a4ec`: `onecore\base\telemetry\utc\service\engine\systemstatemanager.cpp`
- `0x18008a658`: `onecore\base\telemetry\utc\service\engine\systemstatemanager.cpp`
- `0x18008a3c3`: `srumapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall Microsoft::Diagnostics::SystemStateManager::GetBatteryPercentageConsumption(
        unsigned __int8 *a1,
        const struct Microsoft::Diagnostics::SystemStateManager::BatteryInfo *a2)
{
  HMODULE LibraryW; // rax
  HMODULE v4; // rbx
  FARPROC ProcAddress; // rsi
  const char *v6; // r9
  void (*v7)(void); // rdi
  const char *v8; // r9
  const char *v9; // r9
  unsigned int v10; // edx
  unsigned int v11; // ebx
  unsigned int v13[2]; // [rsp+30h] [rbp-59h] BYREF
  HMODULE v14; // [rsp+38h] [rbp-51h] BYREF
  FILETIME FileTime; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int8 *v16; // [rsp+48h] [rbp-41h]
  __int64 v17; // [rsp+50h] [rbp-39h] BYREF
  struct _SYSTEMTIME v18; // [rsp+80h] [rbp-9h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v16 = a1;
  *a1 = 0;
  LibraryW = LoadLibraryW(L"srumapi.dll");
  v4 = LibraryW;
  v14 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "SruQueryStats");
    if ( !ProcAddress )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x577,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\systemstatemanager.cpp",
        v6);
    v7 = (void (*)(void))GetProcAddress(v4, "SruFreeRecordSet");
    if ( !v7 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x579,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\systemstatemanager.cpp",
        v8);
    FileTime = (FILETIME)*((_QWORD *)a2 + 1);
    SystemTime = 0;
    if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x57D,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\systemstatemanager.cpp",
        v9);
    v18 = 0;
    GetSystemTime(&v18);
    *(_QWORD *)v13 = 0;
    CRPCTimeout::CRPCTimeout((CRPCTimeout *)&v17, v10);
    v11 = ((__int64 (__fastcall *)(__int64, struct _SYSTEMTIME *, struct _SYSTEMTIME *))ProcAddress)(
            7,
            &SystemTime,
            &v18);
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&v17);
    if ( v11 )
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x59E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\systemstatemanager.cpp",
        (const char *)v11,
        (unsigned int)v13);
    else
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x5A4,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\systemstatemanager.cpp",
        (const char *)0xE8,
        (unsigned int)v13);
    if ( *(_QWORD *)v13 )
      v7();
  }
  Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&v14);
  return 0;
}

```

## disassembly

```asm
0x18008a38c  mov     [rsp-8+arg_10], rbx
0x18008a391  push    rbp
0x18008a392  push    rsi
0x18008a393  push    rdi
0x18008a394  push    r12
0x18008a396  push    r13
0x18008a398  push    r14
0x18008a39a  push    r15
0x18008a39c  lea     rbp, [rsp-27h]
0x18008a3a1  sub     rsp, 0B0h
0x18008a3a8  mov     rax, cs:__security_cookie
0x18008a3af  xor     rax, rsp
0x18008a3b2  mov     [rbp+57h+var_40], rax
0x18008a3b6  mov     r13, rdx
0x18008a3b9  mov     [rbp+57h+var_98], rcx
0x18008a3bd  xor     r14d, r14d
0x18008a3c0  mov     [rcx], r14b
0x18008a3c3  lea     rcx, LibFileName; "srumapi.dll"
0x18008a3ca  call    cs:__imp_LoadLibraryW
0x18008a3d1  nop     dword ptr [rax+rax+00h]
0x18008a3d6  mov     rbx, rax
0x18008a3d9  mov     [rbp+57h+var_A8], rax
0x18008a3dd  test    rax, rax
0x18008a3e0  jz      loc_18008A67C
0x18008a3e6  lea     rdx, ProcName; "SruQueryStats"
0x18008a3ed  mov     rcx, rax; hModule
0x18008a3f0  call    cs:__imp_GetProcAddress
0x18008a3f7  nop     dword ptr [rax+rax+00h]
0x18008a3fc  mov     rsi, rax
0x18008a3ff  mov     rcx, [rbp+5Fh]; this
0x18008a403  test    rax, rax
0x18008a406  jnz     short loc_18008A41A
0x18008a408  lea     r8, aOnecoreBaseTel_47; "onecore\\base\\telemetry\\utc\\service"...
0x18008a40f  mov     edx, 577h; void *
0x18008a414  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18008a41a  lea     rdx, aSrufreerecords; "SruFreeRecordSet"
0x18008a421  mov     rcx, rbx; hModule
0x18008a424  call    cs:__imp_GetProcAddress
0x18008a42b  nop     dword ptr [rax+rax+00h]
0x18008a430  mov     rdi, rax
0x18008a433  mov     rcx, [rbp+5Fh]; this
0x18008a437  test    rax, rax
0x18008a43a  jnz     short loc_18008A44E
0x18008a43c  lea     r8, aOnecoreBaseTel_47; "onecore\\base\\telemetry\\utc\\service"...
0x18008a443  mov     edx, 579h; void *
0x18008a448  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18008a44e  mov     rax, [r13+8]
0x18008a452  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rax
0x18008a456  xorps   xmm0, xmm0
0x18008a459  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18008a45d  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x18008a461  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x18008a465  call    cs:__imp_FileTimeToSystemTime
0x18008a46c  nop     dword ptr [rax+rax+00h]
0x18008a471  mov     rcx, [rbp+5Fh]; this
0x18008a475  test    eax, eax
0x18008a477  jnz     short loc_18008A48B
0x18008a479  lea     r8, aOnecoreBaseTel_47; "onecore\\base\\telemetry\\utc\\service"...
0x18008a480  mov     edx, 57Dh; void *
0x18008a485  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18008a48b  xorps   xmm0, xmm0
0x18008a48e  movups  xmmword ptr [rbp+57h+var_60.wYear], xmm0
0x18008a492  lea     rcx, [rbp+57h+var_60]; lpSystemTime
0x18008a496  call    cs:__imp_GetSystemTime
0x18008a49d  nop     dword ptr [rax+rax+00h]
0x18008a4a2  mov     qword ptr [rbp+57h+var_B0], r14
0x18008a4a6  lea     rcx, [rbp+57h+var_90]; this
0x18008a4aa  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x18008a4af  nop
0x18008a4b0  lea     rax, [rbp+57h+var_B0]
0x18008a4b4  mov     qword ptr [rsp+0E0h+var_C0], rax; unsigned int
0x18008a4b9  mov     r9d, 2
0x18008a4bf  lea     r8, [rbp+57h+var_60]
0x18008a4c3  lea     rdx, [rbp+57h+SystemTime]
0x18008a4c7  lea     ecx, [r9+5]
0x18008a4cb  mov     rax, rsi
0x18008a4ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a4d3  mov     ebx, eax
0x18008a4d5  lea     rcx, [rbp+57h+var_90]; this
0x18008a4d9  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x18008a4de  xor     r10d, r10d
0x18008a4e1  test    ebx, ebx
0x18008a4e3  jz      short loc_18008A503
0x18008a4e5  mov     rcx, [rbp+5Fh]; this
0x18008a4e9  mov     r9d, ebx; char *
0x18008a4ec  lea     r8, aOnecoreBaseTel_47; "onecore\\base\\telemetry\\utc\\service"...
0x18008a4f3  mov     edx, 59Eh; void *
0x18008a4f8  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18008a4fd  nop
0x18008a4fe  jmp     loc_18008A66A
0x18008a503  mov     rcx, qword ptr [rbp+57h+var_B0]
0x18008a507  test    rcx, rcx
0x18008a50a  jz      loc_18008A64E
0x18008a510  cmp     [rcx], r10d
0x18008a513  jz      loc_18008A64E
0x18008a519  mov     r12, r10
0x18008a51c  mov     r15d, r10d
0x18008a51f  mov     r14d, r10d
0x18008a522  jbe     loc_18008A64C
0x18008a528  mov     ebx, r14d
0x18008a52b  shl     rbx, 6
0x18008a52f  mov     rsi, [rcx+8]
0x18008a533  cmp     [rbx+rsi+10h], r10d
0x18008a538  jnz     loc_18008A601
0x18008a53e  mov     rdx, [rbx+rsi+18h]
0x18008a543  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008a547  inc     rax
0x18008a54a  cmp     [rdx+rax*2], r10w
0x18008a54f  jnz     short loc_18008A547
0x18008a551  cmp     rax, 9
0x18008a555  jb      loc_18008A601
0x18008a55b  add     rax, 0FFFFFFFFFFFFFFF8h
0x18008a55f  lea     rcx, [rdx+rax*2]
0x18008a563  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008a567  inc     rax
0x18008a56a  cmp     [rcx+rax*2], r10w
0x18008a56f  jnz     short loc_18008A567
0x18008a571  lea     rdx, aUtcsvc_0; "[utcsvc]"
0x18008a578  mov     [rbp+57h+var_70], rdx
0x18008a57c  mov     [rbp+57h+var_68], 8
0x18008a584  mov     [rbp+57h+var_90], rcx
0x18008a588  mov     [rbp+57h+var_88], rax
0x18008a58c  lea     rdx, [rbp+57h+var_70]
0x18008a590  lea     rcx, [rbp+57h+var_90]
0x18008a594  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18008a599  xor     r10d, r10d
0x18008a59c  test    eax, eax
0x18008a59e  jnz     short loc_18008A5FD
0x18008a5a0  inc     r15d
0x18008a5a3  mov     r8d, r10d
0x18008a5a6  movzx   r9d, word ptr [rbx+rsi+30h]
0x18008a5ac  test    r9d, r9d
0x18008a5af  jz      short loc_18008A5FA
0x18008a5b1  mov     edx, r10d
0x18008a5b4  mov     r11, [rbx+rsi+38h]
0x18008a5b9  mov     eax, edx
0x18008a5bb  lea     rcx, [rax+rax*2]
0x18008a5bf  mov     rax, [r11+rcx*8+10h]
0x18008a5c4  movzx   r10d, word ptr [rax+8]
0x18008a5c9  movzx   ecx, byte ptr [rax+1]
0x18008a5cd  and     ecx, 8
0x18008a5d0  or      rcx, 10h
0x18008a5d4  add     rcx, rax
0x18008a5d7  mov     eax, 2
0x18008a5dc  bt      r10d, eax
0x18008a5e0  jnb     short loc_18008A5E9
0x18008a5e2  add     r8, [rcx]
0x18008a5e5  add     rcx, 8
0x18008a5e9  inc     eax
0x18008a5eb  cmp     eax, 0Ah
0x18008a5ee  jle     short loc_18008A5DC
0x18008a5f0  inc     edx
0x18008a5f2  cmp     edx, r9d
0x18008a5f5  jl      short loc_18008A5B9
0x18008a5f7  xor     r10d, r10d
0x18008a5fa  add     r12, r8
0x18008a5fd  mov     rcx, qword ptr [rbp+57h+var_B0]
0x18008a601  inc     r14d
0x18008a604  cmp     r14d, [rcx]
0x18008a607  jb      loc_18008A528
0x18008a60d  test    r15d, r15d
0x18008a610  jz      short loc_18008A64C
0x18008a612  test    rcx, rcx
0x18008a615  jz      short loc_18008A620
0x18008a617  mov     rax, rdi
0x18008a61a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a61f  nop
0x18008a620  mov     ecx, [r13+0]
0x18008a624  imul    r8, rcx, 0E10h
0x18008a62b  test    r8, r8
0x18008a62e  jz      short loc_18008A63F
0x18008a630  imul    rax, r12, 64h ; 'd'
0x18008a634  xor     edx, edx
0x18008a636  div     r8
0x18008a639  mov     rcx, [rbp+57h+var_98]
0x18008a63d  mov     [rcx], al
0x18008a63f  lea     rcx, [rbp+57h+var_A8]
0x18008a643  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x18008a648  mov     al, 1
0x18008a64a  jmp     short loc_18008A687
0x18008a64c  jmp     short loc_18008A66E
0x18008a64e  mov     rcx, [rbp+5Fh]; this
0x18008a652  mov     r9d, 0E8h; char *
0x18008a658  lea     r8, aOnecoreBaseTel_47; "onecore\\base\\telemetry\\utc\\service"...
0x18008a65f  mov     edx, 5A4h; void *
0x18008a664  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18008a669  nop
0x18008a66a  mov     rcx, qword ptr [rbp+57h+var_B0]
0x18008a66e  test    rcx, rcx
0x18008a671  jz      short loc_18008A67C
0x18008a673  mov     rax, rdi
0x18008a676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a67b  nop
0x18008a67c  lea     rcx, [rbp+57h+var_A8]
0x18008a680  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x18008a685  xor     al, al
0x18008a687  mov     rcx, [rbp+57h+var_40]
0x18008a68b  xor     rcx, rsp; StackCookie
0x18008a68e  call    __security_check_cookie
0x18008a693  mov     rbx, [rsp+0E0h+arg_10]
0x18008a69b  add     rsp, 0B0h
0x18008a6a2  pop     r15
0x18008a6a4  pop     r14
0x18008a6a6  pop     r13
0x18008a6a8  pop     r12
0x18008a6aa  pop     rdi
0x18008a6ab  pop     rsi
0x18008a6ac  pop     rbp
0x18008a6ad  retn
```
