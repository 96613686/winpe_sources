# WctGetObjectInfo(_WCT_CLIENT_HANDLE *,void *,tlx::unique_any<tlx::file_handle_traits> *,_WCT_OBJECT_TYPE *)

- ea: `0x180060264`
- end: `0x1800605c1`
- name: `?WctGetObjectInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAXPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEAW4_WCT_OBJECT_TYPE@@@Z`
- size: `861`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18005fa0c`

## callees

- `0x180004c64`
- `0x180007fd8`
- `0x180008004`
- `0x18001e0d0`
- `0x180020680`
- `0x180028760`
- `0x18002d930`
- `0x180060264`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006039d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006039d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800602df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180060303`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180060505`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800602df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180060303`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180060505`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800602ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800602ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060539`
- `ntdll!NtQueryObject` at `0x18006036a`
- `ntdll!NtQueryObject` at `0x1800603ed`
- `ntdll!NtQueryObject` at `0x18006036a`
- `ntdll!NtQueryObject` at `0x1800603ed`
- `ntdll!RtlNtStatusToDosError` at `0x18006037f`
- `ntdll!RtlNtStatusToDosError` at `0x18006037f`
- `ntdll!RtlInitUnicodeString` at `0x180060411`
- `ntdll!RtlInitUnicodeString` at `0x18006044e`
- `ntdll!RtlInitUnicodeString` at `0x18006048d`
- `ntdll!RtlInitUnicodeString` at `0x1800604c7`
- `ntdll!RtlInitUnicodeString` at `0x180060411`
- `ntdll!RtlInitUnicodeString` at `0x18006044e`
- `ntdll!RtlInitUnicodeString` at `0x18006048d`
- `ntdll!RtlInitUnicodeString` at `0x1800604c7`
- `ntdll!RtlEqualUnicodeString` at `0x180060427`
- `ntdll!RtlEqualUnicodeString` at `0x180060464`
- `ntdll!RtlEqualUnicodeString` at `0x1800604a3`
- `ntdll!RtlEqualUnicodeString` at `0x1800604dd`
- `ntdll!RtlEqualUnicodeString` at `0x180060427`
- `ntdll!RtlEqualUnicodeString` at `0x180060464`
- `ntdll!RtlEqualUnicodeString` at `0x1800604a3`
- `ntdll!RtlEqualUnicodeString` at `0x1800604dd`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18006032c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180060529`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18006032c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180060529`

## string_xrefs

- `0x180060482`: `Thread`

## pseudocode

```c
__int64 __fastcall WctGetObjectInfo(__int64 a1, HANDLE a2, __int64 a3, _DWORD *a4)
{
  DWORD dwDesiredAccess; // esi
  HANDLE CurrentProcess; // rax
  void *v10; // r12
  HANDLE *v11; // rbx
  HANDLE v12; // rax
  unsigned int v13; // edi
  int v14; // eax
  DWORD LastError; // eax
  UNICODE_STRING *v16; // rax
  UNICODE_STRING *v17; // rbx
  HANDLE *v18; // rbx
  HANDLE v19; // rax
  HANDLE Handle; // [rsp+40h] [rbp-38h] BYREF
  UNICODE_STRING *v22; // [rsp+48h] [rbp-30h] BYREF
  __int64 v23; // [rsp+50h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-20h] BYREF
  ULONG ReturnLength; // [rsp+C8h] [rbp+50h] BYREF

  dwDesiredAccess = 0;
  Handle = 0;
  v22 = 0;
  ReturnLength = 0;
  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  tlx::unique_any<tlx::file_handle_traits>::reset(a3, 0);
  if ( a2 == GetCurrentThread() )
  {
    CurrentProcess = GetCurrentProcess();
    a2 = *(HANDLE *)a1;
    v10 = CurrentProcess;
  }
  else
  {
    v10 = *(void **)(a1 + 8);
  }
  v11 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&Handle);
  v12 = GetCurrentProcess();
  if ( !DuplicateHandle(v10, a2, v12, v11, 0, 0, 2u) )
  {
LABEL_25:
    LastError = GetLastError();
LABEL_26:
    v13 = LastError;
    if ( LastError )
      goto LABEL_30;
    goto LABEL_29;
  }
  if ( (unsigned __int64)Handle + 1 > 1 )
  {
    v14 = NtQueryObject(Handle, ObjectTypeInformation, 0, ReturnLength, &ReturnLength);
    if ( v14 != -1073741820 )
      goto LABEL_11;
    v16 = (UNICODE_STRING *)HeapAlloc(g_hWerheap, 0, ReturnLength);
    v22 = 0;
    v17 = v16;
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v22);
    v23 = 0;
    v22 = v17;
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v23);
    if ( !v17 )
    {
      v13 = 8;
      goto LABEL_30;
    }
    v14 = NtQueryObject(Handle, ObjectTypeInformation, v17, ReturnLength, &ReturnLength);
    if ( v14 < 0 )
    {
LABEL_11:
      LastError = RtlNtStatusToDosError(v14);
      goto LABEL_26;
    }
    *a4 = 10;
    v13 = 0;
    RtlInitUnicodeString(&DestinationString, L"Event");
    if ( RtlEqualUnicodeString(&DestinationString, v17, 0) )
    {
      *a4 = 1;
      goto LABEL_29;
    }
    RtlInitUnicodeString(&DestinationString, L"Mutant");
    if ( RtlEqualUnicodeString(&DestinationString, v17, 0) )
    {
      *a4 = 3;
      dwDesiredAccess = 2031617;
      goto LABEL_24;
    }
    RtlInitUnicodeString(&DestinationString, L"Thread");
    if ( RtlEqualUnicodeString(&DestinationString, v17, 0) )
    {
      *a4 = 6;
    }
    else
    {
      RtlInitUnicodeString(&DestinationString, L"Process");
      if ( !RtlEqualUnicodeString(&DestinationString, v17, 0) )
        goto LABEL_24;
      *a4 = 7;
    }
    dwDesiredAccess = 0x1FFFFF;
LABEL_24:
    v18 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&Handle);
    v19 = GetCurrentProcess();
    if ( DuplicateHandle(v10, a2, v19, v18, dwDesiredAccess, 0, 0) )
    {
      if ( Handle == (HANDLE)-1LL || (char *)Handle + 1 == HANDLE_FLAG_INHERIT )
        goto LABEL_9;
LABEL_29:
      tlx::unique_any<tlx::file_handle_traits>::operator=(a3, &Handle);
      goto LABEL_30;
    }
    goto LABEL_25;
  }
LABEL_9:
  v13 = 87;
LABEL_30:
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v13);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v22);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&Handle);
  return v13;
}

```

## disassembly

```asm
0x180060264  push    rbp
0x180060266  push    rbx
0x180060267  push    rsi
0x180060268  push    rdi
0x180060269  push    r12
0x18006026b  push    r13
0x18006026d  push    r14
0x18006026f  push    r15
0x180060271  mov     rbp, rsp
0x180060274  sub     rsp, 78h
0x180060278  xor     esi, esi
0x18006027a  xorps   xmm0, xmm0
0x18006027d  mov     [rbp+Handle], rsi
0x180060281  mov     r14, r9
0x180060284  mov     [rbp+var_30], rsi
0x180060288  mov     r13, r8
0x18006028b  mov     [rbp+ReturnLength], esi
0x18006028e  mov     r15, rdx
0x180060291  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180060295  mov     rbx, rcx
0x180060298  mov     rcx, cs:WPP_GLOBAL_Control
0x18006029f  lea     rax, WPP_GLOBAL_Control
0x1800602a6  cmp     rcx, rax
0x1800602a9  jz      short loc_1800602C4
0x1800602ab  test    byte ptr [rcx+1Ch], 4
0x1800602af  jz      short loc_1800602C4
0x1800602b1  mov     rcx, [rcx+10h]
0x1800602b5  lea     edx, [rsi+18h]
0x1800602b8  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x1800602bf  call    WPP_SF_
0x1800602c4  xor     edx, edx
0x1800602c6  mov     rcx, r13
0x1800602c9  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800602ce  call    cs:__imp_GetCurrentThread
0x1800602d5  nop     dword ptr [rax+rax+00h]
0x1800602da  cmp     r15, rax
0x1800602dd  jnz     short loc_1800602F3
0x1800602df  call    cs:__imp_GetCurrentProcess
0x1800602e6  nop     dword ptr [rax+rax+00h]
0x1800602eb  mov     r15, [rbx]
0x1800602ee  mov     r12, rax
0x1800602f1  jmp     short loc_1800602F7
0x1800602f3  mov     r12, [rbx+8]
0x1800602f7  lea     rcx, [rbp+Handle]
0x1800602fb  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180060300  mov     rbx, rax
0x180060303  call    cs:__imp_GetCurrentProcess
0x18006030a  nop     dword ptr [rax+rax+00h]
0x18006030f  mov     edi, 2
0x180060314  mov     r9, rbx; lpTargetHandle
0x180060317  mov     [rsp+78h+dwOptions], edi; dwOptions
0x18006031b  mov     r8, rax; hTargetProcessHandle
0x18006031e  mov     [rsp+78h+bInheritHandle], esi; bInheritHandle
0x180060322  mov     rdx, r15; hSourceHandle
0x180060325  mov     rcx, r12; hSourceProcessHandle
0x180060328  mov     [rsp+78h+dwDesiredAccess], esi; dwDesiredAccess
0x18006032c  call    cs:__imp_DuplicateHandle
0x180060333  nop     dword ptr [rax+rax+00h]
0x180060338  test    eax, eax
0x18006033a  jz      loc_180060539
0x180060340  mov     rcx, [rbp+Handle]; Handle
0x180060344  lea     rax, [rcx+1]
0x180060348  cmp     rax, 1
0x18006034c  ja      short loc_180060358
0x18006034e  mov     edi, 57h ; 'W'
0x180060353  jmp     loc_18006056A
0x180060358  mov     r9d, [rbp+ReturnLength]; ObjectInformationLength
0x18006035c  lea     rax, [rbp+ReturnLength]
0x180060360  xor     r8d, r8d; ObjectInformation
0x180060363  mov     qword ptr [rsp+78h+dwDesiredAccess], rax; ReturnLength
0x180060368  mov     edx, edi; ObjectInformationClass
0x18006036a  call    cs:__imp_NtQueryObject
0x180060371  nop     dword ptr [rax+rax+00h]
0x180060376  cmp     eax, 0C0000004h
0x18006037b  jz      short loc_180060390
0x18006037d  mov     ecx, eax; Status
0x18006037f  call    cs:__imp_RtlNtStatusToDosError
0x180060386  nop     dword ptr [rax+rax+00h]
0x18006038b  jmp     loc_180060545
0x180060390  mov     r8d, [rbp+ReturnLength]; dwBytes
0x180060394  xor     edx, edx; dwFlags
0x180060396  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18006039d  call    cs:__imp_HeapAlloc
0x1800603a4  nop     dword ptr [rax+rax+00h]
0x1800603a9  lea     rcx, [rbp+var_30]; void *
0x1800603ad  mov     [rbp+var_30], rsi
0x1800603b1  mov     rbx, rax
0x1800603b4  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800603b9  lea     rcx, [rbp+var_28]; void *
0x1800603bd  mov     [rbp+var_28], rsi
0x1800603c1  mov     [rbp+var_30], rbx
0x1800603c5  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800603ca  test    rbx, rbx
0x1800603cd  jnz     short loc_1800603D7
0x1800603cf  lea     edi, [rbx+8]
0x1800603d2  jmp     loc_18006056A
0x1800603d7  mov     r9d, [rbp+ReturnLength]; ObjectInformationLength
0x1800603db  lea     rax, [rbp+ReturnLength]
0x1800603df  mov     rcx, [rbp+Handle]; Handle
0x1800603e3  mov     r8, rbx; ObjectInformation
0x1800603e6  mov     edx, edi; ObjectInformationClass
0x1800603e8  mov     qword ptr [rsp+78h+dwDesiredAccess], rax; ReturnLength
0x1800603ed  call    cs:__imp_NtQueryObject
0x1800603f4  nop     dword ptr [rax+rax+00h]
0x1800603f9  test    eax, eax
0x1800603fb  js      short loc_18006037D
0x1800603fd  lea     rdx, aEvent_0; "Event"
0x180060404  mov     dword ptr [r14], 0Ah
0x18006040b  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006040f  mov     edi, esi
0x180060411  call    cs:__imp_RtlInitUnicodeString
0x180060418  nop     dword ptr [rax+rax+00h]
0x18006041d  xor     r8d, r8d; CaseInsensitive
0x180060420  lea     rcx, [rbp+DestinationString]; String1
0x180060424  mov     rdx, rbx; String2
0x180060427  call    cs:__imp_RtlEqualUnicodeString
0x18006042e  nop     dword ptr [rax+rax+00h]
0x180060433  test    al, al
0x180060435  jz      short loc_180060443
0x180060437  mov     dword ptr [r14], 1
0x18006043e  jmp     loc_18006055E
0x180060443  lea     rdx, aMutant; "Mutant"
0x18006044a  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006044e  call    cs:__imp_RtlInitUnicodeString
0x180060455  nop     dword ptr [rax+rax+00h]
0x18006045a  xor     r8d, r8d; CaseInsensitive
0x18006045d  lea     rcx, [rbp+DestinationString]; String1
0x180060461  mov     rdx, rbx; String2
0x180060464  call    cs:__imp_RtlEqualUnicodeString
0x18006046b  nop     dword ptr [rax+rax+00h]
0x180060470  test    al, al
0x180060472  jz      short loc_180060482
0x180060474  mov     dword ptr [r14], 3
0x18006047b  mov     esi, 1F0001h
0x180060480  jmp     short loc_1800604F9
0x180060482  lea     rdx, aThread; "Thread"
0x180060489  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006048d  call    cs:__imp_RtlInitUnicodeString
0x180060494  nop     dword ptr [rax+rax+00h]
0x180060499  xor     r8d, r8d; CaseInsensitive
0x18006049c  lea     rcx, [rbp+DestinationString]; String1
0x1800604a0  mov     rdx, rbx; String2
0x1800604a3  call    cs:__imp_RtlEqualUnicodeString
0x1800604aa  nop     dword ptr [rax+rax+00h]
0x1800604af  test    al, al
0x1800604b1  jz      short loc_1800604BC
0x1800604b3  mov     dword ptr [r14], 6
0x1800604ba  jmp     short loc_1800604F4
0x1800604bc  lea     rdx, aProcess; "Process"
0x1800604c3  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800604c7  call    cs:__imp_RtlInitUnicodeString
0x1800604ce  nop     dword ptr [rax+rax+00h]
0x1800604d3  xor     r8d, r8d; CaseInsensitive
0x1800604d6  lea     rcx, [rbp+DestinationString]; String1
0x1800604da  mov     rdx, rbx; String2
0x1800604dd  call    cs:__imp_RtlEqualUnicodeString
0x1800604e4  nop     dword ptr [rax+rax+00h]
0x1800604e9  test    al, al
0x1800604eb  jz      short loc_1800604F9
0x1800604ed  mov     dword ptr [r14], 7
0x1800604f4  mov     esi, 1FFFFFh
0x1800604f9  lea     rcx, [rbp+Handle]
0x1800604fd  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180060502  mov     rbx, rax
0x180060505  call    cs:__imp_GetCurrentProcess
0x18006050c  nop     dword ptr [rax+rax+00h]
0x180060511  mov     [rsp+78h+dwOptions], edi; dwOptions
0x180060515  mov     r9, rbx; lpTargetHandle
0x180060518  mov     r8, rax; hTargetProcessHandle
0x18006051b  mov     [rsp+78h+bInheritHandle], edi; bInheritHandle
0x18006051f  mov     rdx, r15; hSourceHandle
0x180060522  mov     [rsp+78h+dwDesiredAccess], esi; dwDesiredAccess
0x180060526  mov     rcx, r12; hSourceProcessHandle
0x180060529  call    cs:__imp_DuplicateHandle
0x180060530  nop     dword ptr [rax+rax+00h]
0x180060535  test    eax, eax
0x180060537  jnz     short loc_18006054D
0x180060539  call    cs:__imp_GetLastError
0x180060540  nop     dword ptr [rax+rax+00h]
0x180060545  mov     edi, eax
0x180060547  test    eax, eax
0x180060549  jnz     short loc_18006056A
0x18006054b  jmp     short loc_18006055E
0x18006054d  mov     rax, [rbp+Handle]
0x180060551  inc     rax
0x180060554  cmp     rax, 1
0x180060558  jbe     loc_18006034E
0x18006055e  lea     rdx, [rbp+Handle]
0x180060562  mov     rcx, r13
0x180060565  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x18006056a  mov     rcx, cs:WPP_GLOBAL_Control
0x180060571  lea     rax, WPP_GLOBAL_Control
0x180060578  cmp     rcx, rax
0x18006057b  jz      short loc_18006059B
0x18006057d  test    byte ptr [rcx+1Ch], 4
0x180060581  jz      short loc_18006059B
0x180060583  mov     rcx, [rcx+10h]
0x180060587  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18006058e  mov     edx, 19h
0x180060593  mov     r9d, edi
0x180060596  call    WPP_SF_d
0x18006059b  lea     rcx, [rbp+var_30]; void *
0x18006059f  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800605a4  lea     rcx, [rbp+Handle]
0x1800605a8  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800605ad  mov     eax, edi
0x1800605af  add     rsp, 78h
0x1800605b3  pop     r15
0x1800605b5  pop     r14
0x1800605b7  pop     r13
0x1800605b9  pop     r12
0x1800605bb  pop     rdi
0x1800605bc  pop     rsi
0x1800605bd  pop     rbx
0x1800605be  pop     rbp
0x1800605bf  retn
```
