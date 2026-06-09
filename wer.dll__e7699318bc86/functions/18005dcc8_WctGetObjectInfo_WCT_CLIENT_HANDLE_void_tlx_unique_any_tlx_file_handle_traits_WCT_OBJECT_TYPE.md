# WctGetObjectInfo(_WCT_CLIENT_HANDLE *,void *,tlx::unique_any<tlx::file_handle_traits> *,_WCT_OBJECT_TYPE *)

- ea: `0x18005dcc8`
- end: `0x18005dfb2`
- name: `?WctGetObjectInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAXPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEAW4_WCT_OBJECT_TYPE@@@Z`
- size: `746`
- prototype: `__int64 __fastcall(__int64, HANDLE, void **, _DWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18005d450`

## callees

- `0x180004bb4`
- `0x180007e10`
- `0x180007e34`
- `0x18001c650`
- `0x18001fe24`
- `0x180027884`
- `0x18002bed4`
- `0x18005dcc8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005dddd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005dddd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005dd3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005dd5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005df09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005dd3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005dd5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005df09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005dd32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005dd32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005df31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005df31`
- `ntdll!NtQueryObject` at `0x18005ddb6`
- `ntdll!NtQueryObject` at `0x18005de27`
- `ntdll!NtQueryObject` at `0x18005ddb6`
- `ntdll!NtQueryObject` at `0x18005de27`
- `ntdll!RtlNtStatusToDosError` at `0x18005ddc5`
- `ntdll!RtlNtStatusToDosError` at `0x18005ddc5`
- `ntdll!RtlInitUnicodeString` at `0x18005de45`
- `ntdll!RtlInitUnicodeString` at `0x18005de76`
- `ntdll!RtlInitUnicodeString` at `0x18005dea9`
- `ntdll!RtlInitUnicodeString` at `0x18005ded7`
- `ntdll!RtlInitUnicodeString` at `0x18005de45`
- `ntdll!RtlInitUnicodeString` at `0x18005de76`
- `ntdll!RtlInitUnicodeString` at `0x18005dea9`
- `ntdll!RtlInitUnicodeString` at `0x18005ded7`
- `ntdll!RtlEqualUnicodeString` at `0x18005de55`
- `ntdll!RtlEqualUnicodeString` at `0x18005de86`
- `ntdll!RtlEqualUnicodeString` at `0x18005deb9`
- `ntdll!RtlEqualUnicodeString` at `0x18005dee7`
- `ntdll!RtlEqualUnicodeString` at `0x18005de55`
- `ntdll!RtlEqualUnicodeString` at `0x18005de86`
- `ntdll!RtlEqualUnicodeString` at `0x18005deb9`
- `ntdll!RtlEqualUnicodeString` at `0x18005dee7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005dd7e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005df27`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005dd7e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005df27`

## string_xrefs

- `0x18005de9e`: `Thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WctGetObjectInfo(__int64 a1, HANDLE a2, void **a3, _DWORD *a4)
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_4c32fa7a72a13340317baef891270170_Traceguids);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_4c32fa7a72a13340317baef891270170_Traceguids, v13);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v22);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&Handle);
  return v13;
}

```

## disassembly

```asm
0x18005dcc8  push    rbp
0x18005dcca  push    rbx
0x18005dccb  push    rsi
0x18005dccc  push    rdi
0x18005dccd  push    r12
0x18005dccf  push    r13
0x18005dcd1  push    r14
0x18005dcd3  push    r15
0x18005dcd5  mov     rbp, rsp
0x18005dcd8  sub     rsp, 78h
0x18005dcdc  xor     esi, esi
0x18005dcde  xorps   xmm0, xmm0
0x18005dce1  mov     [rbp+Handle], rsi
0x18005dce5  mov     r14, r9
0x18005dce8  mov     [rbp+var_30], rsi
0x18005dcec  mov     r13, r8
0x18005dcef  mov     [rbp+ReturnLength], esi
0x18005dcf2  mov     r15, rdx
0x18005dcf5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18005dcf9  mov     rbx, rcx
0x18005dcfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005dd03  lea     rax, WPP_GLOBAL_Control
0x18005dd0a  cmp     rcx, rax
0x18005dd0d  jz      short loc_18005DD28
0x18005dd0f  test    byte ptr [rcx+1Ch], 4
0x18005dd13  jz      short loc_18005DD28
0x18005dd15  mov     rcx, [rcx+10h]
0x18005dd19  lea     edx, [rsi+18h]
0x18005dd1c  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005dd23  call    WPP_SF_
0x18005dd28  xor     edx, edx
0x18005dd2a  mov     rcx, r13
0x18005dd2d  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005dd32  call    cs:__imp_GetCurrentThread
0x18005dd38  cmp     r15, rax
0x18005dd3b  jnz     short loc_18005DD4B
0x18005dd3d  call    cs:__imp_GetCurrentProcess
0x18005dd43  mov     r15, [rbx]
0x18005dd46  mov     r12, rax
0x18005dd49  jmp     short loc_18005DD4F
0x18005dd4b  mov     r12, [rbx+8]
0x18005dd4f  lea     rcx, [rbp+Handle]
0x18005dd53  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18005dd58  mov     rbx, rax
0x18005dd5b  call    cs:__imp_GetCurrentProcess
0x18005dd61  mov     edi, 2
0x18005dd66  mov     r9, rbx; lpTargetHandle
0x18005dd69  mov     [rsp+78h+dwOptions], edi; dwOptions
0x18005dd6d  mov     r8, rax; hTargetProcessHandle
0x18005dd70  mov     [rsp+78h+bInheritHandle], esi; bInheritHandle
0x18005dd74  mov     rdx, r15; hSourceHandle
0x18005dd77  mov     rcx, r12; hSourceProcessHandle
0x18005dd7a  mov     [rsp+78h+dwDesiredAccess], esi; dwDesiredAccess
0x18005dd7e  call    cs:__imp_DuplicateHandle
0x18005dd84  test    eax, eax
0x18005dd86  jz      loc_18005DF31
0x18005dd8c  mov     rcx, [rbp+Handle]; Handle
0x18005dd90  lea     rax, [rcx+1]
0x18005dd94  cmp     rax, 1
0x18005dd98  ja      short loc_18005DDA4
0x18005dd9a  mov     edi, 57h ; 'W'
0x18005dd9f  jmp     loc_18005DF5C
0x18005dda4  mov     r9d, [rbp+ReturnLength]; ObjectInformationLength
0x18005dda8  lea     rax, [rbp+ReturnLength]
0x18005ddac  xor     r8d, r8d; ObjectInformation
0x18005ddaf  mov     qword ptr [rsp+78h+dwDesiredAccess], rax; ReturnLength
0x18005ddb4  mov     edx, edi; ObjectInformationClass
0x18005ddb6  call    cs:__imp_NtQueryObject
0x18005ddbc  cmp     eax, 0C0000004h
0x18005ddc1  jz      short loc_18005DDD0
0x18005ddc3  mov     ecx, eax; Status
0x18005ddc5  call    cs:__imp_RtlNtStatusToDosError
0x18005ddcb  jmp     loc_18005DF37
0x18005ddd0  mov     r8d, [rbp+ReturnLength]; dwBytes
0x18005ddd4  xor     edx, edx; dwFlags
0x18005ddd6  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18005dddd  call    cs:__imp_HeapAlloc
0x18005dde3  lea     rcx, [rbp+var_30]; void *
0x18005dde7  mov     [rbp+var_30], rsi
0x18005ddeb  mov     rbx, rax
0x18005ddee  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18005ddf3  lea     rcx, [rbp+var_28]; void *
0x18005ddf7  mov     [rbp+var_28], rsi
0x18005ddfb  mov     [rbp+var_30], rbx
0x18005ddff  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18005de04  test    rbx, rbx
0x18005de07  jnz     short loc_18005DE11
0x18005de09  lea     edi, [rbx+8]
0x18005de0c  jmp     loc_18005DF5C
0x18005de11  mov     r9d, [rbp+ReturnLength]; ObjectInformationLength
0x18005de15  lea     rax, [rbp+ReturnLength]
0x18005de19  mov     rcx, [rbp+Handle]; Handle
0x18005de1d  mov     r8, rbx; ObjectInformation
0x18005de20  mov     edx, edi; ObjectInformationClass
0x18005de22  mov     qword ptr [rsp+78h+dwDesiredAccess], rax; ReturnLength
0x18005de27  call    cs:__imp_NtQueryObject
0x18005de2d  test    eax, eax
0x18005de2f  js      short loc_18005DDC3
0x18005de31  lea     rdx, aEvent_0; "Event"
0x18005de38  mov     dword ptr [r14], 0Ah
0x18005de3f  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005de43  mov     edi, esi
0x18005de45  call    cs:__imp_RtlInitUnicodeString
0x18005de4b  xor     r8d, r8d; CaseInsensitive
0x18005de4e  lea     rcx, [rbp+DestinationString]; String1
0x18005de52  mov     rdx, rbx; String2
0x18005de55  call    cs:__imp_RtlEqualUnicodeString
0x18005de5b  test    al, al
0x18005de5d  jz      short loc_18005DE6B
0x18005de5f  mov     dword ptr [r14], 1
0x18005de66  jmp     loc_18005DF50
0x18005de6b  lea     rdx, aMutant; "Mutant"
0x18005de72  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005de76  call    cs:__imp_RtlInitUnicodeString
0x18005de7c  xor     r8d, r8d; CaseInsensitive
0x18005de7f  lea     rcx, [rbp+DestinationString]; String1
0x18005de83  mov     rdx, rbx; String2
0x18005de86  call    cs:__imp_RtlEqualUnicodeString
0x18005de8c  test    al, al
0x18005de8e  jz      short loc_18005DE9E
0x18005de90  mov     dword ptr [r14], 3
0x18005de97  mov     esi, 1F0001h
0x18005de9c  jmp     short loc_18005DEFD
0x18005de9e  lea     rdx, aThread; "Thread"
0x18005dea5  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005dea9  call    cs:__imp_RtlInitUnicodeString
0x18005deaf  xor     r8d, r8d; CaseInsensitive
0x18005deb2  lea     rcx, [rbp+DestinationString]; String1
0x18005deb6  mov     rdx, rbx; String2
0x18005deb9  call    cs:__imp_RtlEqualUnicodeString
0x18005debf  test    al, al
0x18005dec1  jz      short loc_18005DECC
0x18005dec3  mov     dword ptr [r14], 6
0x18005deca  jmp     short loc_18005DEF8
0x18005decc  lea     rdx, aProcess; "Process"
0x18005ded3  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005ded7  call    cs:__imp_RtlInitUnicodeString
0x18005dedd  xor     r8d, r8d; CaseInsensitive
0x18005dee0  lea     rcx, [rbp+DestinationString]; String1
0x18005dee4  mov     rdx, rbx; String2
0x18005dee7  call    cs:__imp_RtlEqualUnicodeString
0x18005deed  test    al, al
0x18005deef  jz      short loc_18005DEFD
0x18005def1  mov     dword ptr [r14], 7
0x18005def8  mov     esi, 1FFFFFh
0x18005defd  lea     rcx, [rbp+Handle]
0x18005df01  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18005df06  mov     rbx, rax
0x18005df09  call    cs:__imp_GetCurrentProcess
0x18005df0f  mov     [rsp+78h+dwOptions], edi; dwOptions
0x18005df13  mov     r9, rbx; lpTargetHandle
0x18005df16  mov     r8, rax; hTargetProcessHandle
0x18005df19  mov     [rsp+78h+bInheritHandle], edi; bInheritHandle
0x18005df1d  mov     rdx, r15; hSourceHandle
0x18005df20  mov     [rsp+78h+dwDesiredAccess], esi; dwDesiredAccess
0x18005df24  mov     rcx, r12; hSourceProcessHandle
0x18005df27  call    cs:__imp_DuplicateHandle
0x18005df2d  test    eax, eax
0x18005df2f  jnz     short loc_18005DF3F
0x18005df31  call    cs:__imp_GetLastError
0x18005df37  mov     edi, eax
0x18005df39  test    eax, eax
0x18005df3b  jnz     short loc_18005DF5C
0x18005df3d  jmp     short loc_18005DF50
0x18005df3f  mov     rax, [rbp+Handle]
0x18005df43  inc     rax
0x18005df46  cmp     rax, 1
0x18005df4a  jbe     loc_18005DD9A
0x18005df50  lea     rdx, [rbp+Handle]
0x18005df54  mov     rcx, r13
0x18005df57  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x18005df5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005df63  lea     rax, WPP_GLOBAL_Control
0x18005df6a  cmp     rcx, rax
0x18005df6d  jz      short loc_18005DF8D
0x18005df6f  test    byte ptr [rcx+1Ch], 4
0x18005df73  jz      short loc_18005DF8D
0x18005df75  mov     rcx, [rcx+10h]
0x18005df79  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005df80  mov     edx, 19h
0x18005df85  mov     r9d, edi
0x18005df88  call    WPP_SF_d
0x18005df8d  lea     rcx, [rbp+var_30]; void *
0x18005df91  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18005df96  lea     rcx, [rbp+Handle]
0x18005df9a  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18005df9f  mov     eax, edi
0x18005dfa1  add     rsp, 78h
0x18005dfa5  pop     r15
0x18005dfa7  pop     r14
0x18005dfa9  pop     r13
0x18005dfab  pop     r12
0x18005dfad  pop     rdi
0x18005dfae  pop     rsi
0x18005dfaf  pop     rbx
0x18005dfb0  pop     rbp
0x18005dfb1  retn
```
