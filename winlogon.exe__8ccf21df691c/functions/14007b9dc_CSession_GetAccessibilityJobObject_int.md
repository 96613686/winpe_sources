# CSession::GetAccessibilityJobObject(int)

- ea: `0x14007b9dc`
- end: `0x14007bc02`
- name: `?GetAccessibilityJobObject@CSession@@QEAAPEAXH@Z`
- size: `550`
- prototype: `void *__fastcall(CSession *__hidden this, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140019df8`
- `0x14005a06c`

## callees

- `0x1400057f4`
- `0x140028aac`
- `0x140053720`
- `0x1400544e0`
- `0x14007b9dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14007ba08`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14007ba08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007ba60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bb25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bbaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007ba60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bb25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bbaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14007bb53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14007bb5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14007bb53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14007bb5c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14007bb88`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14007bb88`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x14007bac3`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x14007bac3`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x14007ba33`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x14007ba33`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x14007bb03`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x14007bb03`

## string_xrefs

- `0x14007ba2a`: `WinlogonAccess`

## pseudocode

```c
HANDLE __fastcall CSession::GetAccessibilityJobObject(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rbx
  PVOID Ptr; // rdi
  HANDLE JobObjectW; // rax
  DWORD LastError; // eax
  DWORD v7; // eax
  __int64 v8; // rdx
  HANDLE CurrentProcess; // rbx
  HANDLE v10; // rax
  DWORD v11; // eax
  HANDLE v12; // rbx
  HANDLE TargetHandle; // [rsp+40h] [rbp-D8h] BYREF
  RTL_SRWLOCK *v14; // [rsp+48h] [rbp-D0h] BYREF
  _BYTE JobObjectInformation[16]; // [rsp+50h] [rbp-C8h] BYREF
  int v16; // [rsp+60h] [rbp-B8h]

  v1 = this + 48;
  AcquireSRWLockExclusive(this + 48);
  Ptr = this[20].Ptr;
  v14 = v1;
  if ( Ptr )
    goto LABEL_19;
  JobObjectW = CreateJobObjectW(0, L"WinlogonAccess");
  this[20].Ptr = JobObjectW;
  Ptr = JobObjectW;
  if ( !JobObjectW )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids, LastError);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
    return 0;
  }
  memset_0(JobObjectInformation, 0, 0x90u);
  if ( QueryInformationJobObject(Ptr, JobObjectExtendedLimitInformation, JobObjectInformation, 0x90u, 0) )
  {
    v16 |= 0x800u;
    if ( SetInformationJobObject(Ptr, JobObjectExtendedLimitInformation, JobObjectInformation, 0x90u)
      || WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_19;
    }
    v7 = GetLastError();
    v8 = 54;
  }
  else
  {
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_19;
    }
    v7 = GetLastError();
    v8 = 53;
  }
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids, v7);
LABEL_19:
  TargetHandle = 0;
  CurrentProcess = GetCurrentProcess();
  v10 = GetCurrentProcess();
  if ( DuplicateHandle(v10, Ptr, CurrentProcess, &TargetHandle, 0, 0, 2u) )
  {
    v12 = TargetHandle;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids, v11);
    }
    v12 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  return v12;
}

```

## disassembly

```asm
0x14007b9dc  push    rbx
0x14007b9de  push    rsi
0x14007b9df  push    rdi
0x14007b9e0  push    r12
0x14007b9e2  sub     rsp, 0F8h
0x14007b9e9  mov     rax, cs:__security_cookie
0x14007b9f0  xor     rax, rsp
0x14007b9f3  mov     [rsp+118h+var_38], rax
0x14007b9fb  lea     rbx, [rcx+180h]
0x14007ba02  mov     rsi, rcx
0x14007ba05  mov     rcx, rbx; SRWLock
0x14007ba08  call    cs:__imp_AcquireSRWLockExclusive
0x14007ba0e  mov     rdi, [rsi+0A0h]
0x14007ba15  lea     r12, WPP_GLOBAL_Control
0x14007ba1c  mov     [rsp+118h+var_D0], rbx
0x14007ba21  test    rdi, rdi
0x14007ba24  jnz     loc_14007BB4A
0x14007ba2a  lea     rdx, aWinlogonaccess; "WinlogonAccess"
0x14007ba31  xor     ecx, ecx; lpJobAttributes
0x14007ba33  call    cs:__imp_CreateJobObjectW
0x14007ba39  mov     [rsi+0A0h], rax
0x14007ba40  mov     rdi, rax
0x14007ba43  test    rax, rax
0x14007ba46  jnz     short loc_14007BA94
0x14007ba48  mov     rax, cs:WPP_GLOBAL_Control
0x14007ba4f  cmp     rax, r12
0x14007ba52  jz      short loc_14007BA83
0x14007ba54  test    byte ptr [rax+1Ch], 10h
0x14007ba58  jz      short loc_14007BA83
0x14007ba5a  cmp     byte ptr [rax+19h], 2
0x14007ba5e  jb      short loc_14007BA83
0x14007ba60  call    cs:__imp_GetLastError
0x14007ba66  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ba6d  lea     edx, [rdi+34h]
0x14007ba70  mov     r9d, eax
0x14007ba73  lea     r8, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids
0x14007ba7a  mov     rcx, [rcx+10h]
0x14007ba7e  call    WPP_SF_d
0x14007ba83  lea     rcx, [rsp+118h+var_D0]
0x14007ba88  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14007ba8d  xor     eax, eax
0x14007ba8f  jmp     loc_14007BBE5
0x14007ba94  mov     ebx, 90h
0x14007ba99  lea     rcx, [rsp+118h+JobObjectInformation]; void *
0x14007ba9e  mov     r8d, ebx; Size
0x14007baa1  xor     edx, edx; Val
0x14007baa3  call    memset_0
0x14007baa8  mov     esi, 9
0x14007baad  mov     [rsp+118h+lpReturnLength], 0; lpReturnLength
0x14007bab6  mov     edx, esi; JobObjectInformationClass
0x14007bab8  lea     r8, [rsp+118h+JobObjectInformation]; lpJobObjectInformation
0x14007babd  mov     r9d, ebx; cbJobObjectInformationLength
0x14007bac0  mov     rcx, rdi; hJob
0x14007bac3  call    cs:__imp_QueryInformationJobObject
0x14007bac9  test    eax, eax
0x14007bacb  jnz     short loc_14007BAF0
0x14007bacd  mov     rax, cs:WPP_GLOBAL_Control
0x14007bad4  cmp     rax, r12
0x14007bad7  jz      short loc_14007BB4A
0x14007bad9  test    byte ptr [rax+1Ch], 10h
0x14007badd  jz      short loc_14007BB4A
0x14007badf  cmp     byte ptr [rax+19h], 2
0x14007bae3  jb      short loc_14007BB4A
0x14007bae5  call    cs:__imp_GetLastError
0x14007baeb  lea     edx, [rbx-5Bh]
0x14007baee  jmp     short loc_14007BB30
0x14007baf0  bts     [rsp+118h+var_B8], 0Bh
0x14007baf6  lea     r8, [rsp+118h+JobObjectInformation]; lpJobObjectInformation
0x14007bafb  mov     r9d, ebx; cbJobObjectInformationLength
0x14007bafe  mov     edx, esi; JobObjectInformationClass
0x14007bb00  mov     rcx, rdi; hJob
0x14007bb03  call    cs:__imp_SetInformationJobObject
0x14007bb09  test    eax, eax
0x14007bb0b  jnz     short loc_14007BB4A
0x14007bb0d  mov     rax, cs:WPP_GLOBAL_Control
0x14007bb14  cmp     rax, r12
0x14007bb17  jz      short loc_14007BB4A
0x14007bb19  test    byte ptr [rax+1Ch], 10h
0x14007bb1d  jz      short loc_14007BB4A
0x14007bb1f  cmp     byte ptr [rax+19h], 2
0x14007bb23  jb      short loc_14007BB4A
0x14007bb25  call    cs:__imp_GetLastError
0x14007bb2b  mov     edx, 36h ; '6'
0x14007bb30  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bb37  lea     r8, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids
0x14007bb3e  mov     r9d, eax
0x14007bb41  mov     rcx, [rcx+10h]
0x14007bb45  call    WPP_SF_d
0x14007bb4a  mov     [rsp+118h+TargetHandle], 0
0x14007bb53  call    cs:__imp_GetCurrentProcess
0x14007bb59  mov     rbx, rax
0x14007bb5c  call    cs:__imp_GetCurrentProcess
0x14007bb62  mov     [rsp+118h+dwOptions], 2; dwOptions
0x14007bb6a  lea     r9, [rsp+118h+TargetHandle]; lpTargetHandle
0x14007bb6f  mov     rcx, rax; hSourceProcessHandle
0x14007bb72  mov     [rsp+118h+bInheritHandle], 0; bInheritHandle
0x14007bb7a  mov     r8, rbx; hTargetProcessHandle
0x14007bb7d  mov     dword ptr [rsp+118h+lpReturnLength], 0; dwDesiredAccess
0x14007bb85  mov     rdx, rdi; hSourceHandle
0x14007bb88  call    cs:__imp_DuplicateHandle
0x14007bb8e  test    eax, eax
0x14007bb90  jnz     short loc_14007BBD3
0x14007bb92  mov     rax, cs:WPP_GLOBAL_Control
0x14007bb99  cmp     rax, r12
0x14007bb9c  jz      short loc_14007BBCF
0x14007bb9e  test    byte ptr [rax+1Ch], 10h
0x14007bba2  jz      short loc_14007BBCF
0x14007bba4  cmp     byte ptr [rax+19h], 2
0x14007bba8  jb      short loc_14007BBCF
0x14007bbaa  call    cs:__imp_GetLastError
0x14007bbb0  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bbb7  lea     r8, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids
0x14007bbbe  mov     edx, 37h ; '7'
0x14007bbc3  mov     r9d, eax
0x14007bbc6  mov     rcx, [rcx+10h]
0x14007bbca  call    WPP_SF_d
0x14007bbcf  xor     ebx, ebx
0x14007bbd1  jmp     short loc_14007BBD8
0x14007bbd3  mov     rbx, [rsp+118h+TargetHandle]
0x14007bbd8  lea     rcx, [rsp+118h+var_D0]
0x14007bbdd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14007bbe2  mov     rax, rbx
0x14007bbe5  mov     rcx, [rsp+118h+var_38]
0x14007bbed  xor     rcx, rsp; StackCookie
0x14007bbf0  call    __security_check_cookie
0x14007bbf5  add     rsp, 0F8h
0x14007bbfc  pop     r12
0x14007bbfe  pop     rdi
0x14007bbff  pop     rsi
0x14007bc00  pop     rbx
0x14007bc01  retn
```
