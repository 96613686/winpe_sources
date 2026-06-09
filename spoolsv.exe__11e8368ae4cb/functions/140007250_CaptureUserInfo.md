# CaptureUserInfo

- ea: `0x140007250`
- end: `0x14000749d`
- name: `CaptureUserInfo`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d0a0`

## callees

- `0x1400065f0`
- `0x140006b30`
- `0x140007250`
- `0x1400079f0`
- `0x140007bdc`
- `0x140007c00`
- `0x14000e100`
- `0x1400140cc`
- `0x14002a830`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007402`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000742b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007402`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000742b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400073c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400073c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400072fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400072fd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400072f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140007320`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400072f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140007320`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400072de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140007308`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400072de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140007308`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000735a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000735a`

## pseudocode

```c
__int64 CaptureUserInfo()
{
  _DWORD *v0; // rax
  struct NCoreLibrary::TReferenceCount *v1; // rdx
  _DWORD *v2; // rdi
  char *v3; // rax
  HANDLE CurrentThread; // rax
  HANDLE v5; // rax
  int LastErrorAsHResult; // ebx
  void *v7; // rcx
  int v8; // esi
  volatile signed __int32 *v10; // rbx
  signed __int32 v11; // eax
  int v12; // eax
  int v13; // eax
  DWORD ReturnLength; // [rsp+50h] [rbp+8h] BYREF

  v0 = operator new(0x78u);
  v2 = v0;
  if ( !v0 )
  {
    v2 = 0;
    v8 = -2147024882;
    goto LABEL_11;
  }
  v0[2] = 1;
  *((_QWORD *)v0 + 3) = 0;
  v3 = (char *)(v0 + 8);
  *((_DWORD *)v3 + 2) = 1802398836;
  *((_QWORD *)v3 + 2) = v3;
  *((_QWORD *)v3 + 3) = v3;
  *((_QWORD *)v2 + 8) = 1953063799;
  *(_QWORD *)v2 = &NRouter::TSessionCapture::`vftable'{for `NCoreLibrary::TReferenceCount'};
  *((_QWORD *)v2 + 2) = &NRouter::TSessionCapture::`vftable'{for `NThreadingLibrary::TTpSetWorkEnv'};
  *(_QWORD *)v3 = &NRouter::TSessionCapture::`vftable'{for `NCoreLibrary::TLink'};
  v2[18] = 0;
  v2[22] = 0;
  *((_QWORD *)v2 + 10) = 0;
  v2[24] = 1633903987;
  v2[25] = -2147467259;
  v2[26] = 0;
  *((_QWORD *)v2 + 14) = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 0, (PHANDLE)v2 + 14) )
  {
    if ( GetLastError() != 5 || (v5 = GetCurrentThread(), !OpenThreadToken(v5, 0xEu, 1, (PHANDLE)v2 + 14)) )
    {
      LastErrorAsHResult = GetLastErrorAsHResult();
      if ( LastErrorAsHResult < 0 )
        goto LABEL_22;
    }
  }
  v7 = (void *)*((_QWORD *)v2 + 14);
  ReturnLength = 0;
  LastErrorAsHResult = GetTokenInformation(v7, TokenSessionId, v2 + 26, 4u, &ReturnLength) ? 0 : GetLastErrorAsHResult();
  if ( LastErrorAsHResult < 0 )
    goto LABEL_22;
  v12 = IsTokenLocalSystem(*((void **)v2 + 14));
  LastErrorAsHResult = v12;
  if ( v12 < 0 )
    goto LABEL_22;
  if ( !v12 )
  {
    LastErrorAsHResult = -2147023888;
    goto LABEL_10;
  }
  v13 = CheckLocalCall();
  LastErrorAsHResult = v13;
  if ( v13 != 1 )
  {
    if ( v13 >= 0 )
      goto LABEL_10;
LABEL_22:
    if ( LastErrorAsHResult != -2147023888 )
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "NRouter::TSessionCapture::TSessionCapture",
        L"Failed.  Error hr: 0x%x.",
        (unsigned int)LastErrorAsHResult);
    goto LABEL_10;
  }
  LastErrorAsHResult = -2147023888;
LABEL_10:
  v2[25] = LastErrorAsHResult;
  v8 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 16LL))(v2);
  if ( v8 >= 0 )
  {
    EnterCriticalSection(&RouterNotifySection);
    v10 = (volatile signed __int32 *)qword_1400CBC48;
    if ( qword_1400CBC48 )
    {
      v11 = *((_DWORD *)qword_1400CBC48 + 2);
      if ( v11 != 0x7FFFFFFF )
      {
        do
        {
          if ( v11 == _InterlockedCompareExchange(v10 + 2, v11 + 1, v11) )
            break;
          v11 = *((_DWORD *)v10 + 2);
        }
        while ( v11 != 0x7FFFFFFF );
        v10 = (volatile signed __int32 *)qword_1400CBC48;
      }
      LeaveCriticalSection(&RouterNotifySection);
      v8 = NThreadingLibrary::TWorkCrew::AddItem(
             (NThreadingLibrary::TWorkCrew *)v10,
             (struct NThreadingLibrary::TWorkItem *)v2);
      if ( v10 )
        NCoreLibrary::TReferenceCount::Release((NCoreLibrary::TReferenceCount *)v10);
    }
    else
    {
      LeaveCriticalSection(&RouterNotifySection);
      v8 = -2147467261;
    }
  }
LABEL_11:
  NCoreLibrary::EasyRelease((NCoreLibrary *)v2, v1);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140007250  push    rbx
0x140007252  push    rsi
0x140007253  push    rdi
0x140007254  sub     rsp, 30h
0x140007258  mov     ecx, 78h ; 'x'; Size
0x14000725d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007262  xor     esi, esi
0x140007264  mov     rdi, rax
0x140007267  test    rax, rax
0x14000726a  jz      loc_140007374
0x140007270  mov     dword ptr [rax+8], 1
0x140007277  lea     rcx, ??_7TSessionCapture@NRouter@@6BTReferenceCount@NCoreLibrary@@@; const NRouter::TSessionCapture::`vftable'{for `NCoreLibrary::TReferenceCount'}
0x14000727e  mov     [rax+18h], rsi
0x140007282  add     rax, 20h ; ' '
0x140007286  mov     [rsp+48h+arg_8], r14
0x14000728b  mov     [rsp+48h+arg_10], r15
0x140007290  mov     dword ptr [rax+8], 6B6E6C74h
0x140007297  mov     [rax+10h], rax
0x14000729b  mov     [rax+18h], rax
0x14000729f  mov     qword ptr [rdi+40h], 74696377h
0x1400072a7  mov     [rdi], rcx
0x1400072aa  lea     rcx, ??_7TSessionCapture@NRouter@@6BTTpSetWorkEnv@NThreadingLibrary@@@; const NRouter::TSessionCapture::`vftable'{for `NThreadingLibrary::TTpSetWorkEnv'}
0x1400072b1  mov     [rdi+10h], rcx
0x1400072b5  lea     rcx, ??_7TSessionCapture@NRouter@@6BTLink@NCoreLibrary@@@; const NRouter::TSessionCapture::`vftable'{for `NCoreLibrary::TLink'}
0x1400072bc  mov     [rax], rcx
0x1400072bf  mov     [rdi+48h], esi
0x1400072c2  mov     [rdi+58h], esi
0x1400072c5  mov     [rdi+50h], rsi
0x1400072c9  mov     dword ptr [rdi+60h], 61636573h
0x1400072d0  mov     dword ptr [rdi+64h], 80004005h
0x1400072d7  mov     [rdi+68h], esi
0x1400072da  mov     [rdi+70h], rsi
0x1400072de  call    cs:__imp_GetCurrentThread
0x1400072e4  lea     r9, [rdi+70h]; TokenHandle
0x1400072e8  xor     r8d, r8d; OpenAsSelf
0x1400072eb  mov     rcx, rax; ThreadHandle
0x1400072ee  mov     edx, 0Eh; DesiredAccess
0x1400072f3  call    cs:__imp_OpenThreadToken
0x1400072f9  test    eax, eax
0x1400072fb  jnz     short loc_140007339
0x1400072fd  call    cs:__imp_GetLastError
0x140007303  cmp     eax, 5
0x140007306  jnz     short loc_14000732A
0x140007308  call    cs:__imp_GetCurrentThread
0x14000730e  lea     r9, [rdi+70h]; TokenHandle
0x140007312  mov     edx, 0Eh; DesiredAccess
0x140007317  mov     rcx, rax; ThreadHandle
0x14000731a  mov     r8d, 1; OpenAsSelf
0x140007320  call    cs:__imp_OpenThreadToken
0x140007326  test    eax, eax
0x140007328  jnz     short loc_140007339
0x14000732a  call    GetLastErrorAsHResult
0x14000732f  mov     ebx, eax
0x140007331  test    eax, eax
0x140007333  js      loc_140007441
0x140007339  mov     rcx, [rdi+70h]; TokenHandle
0x14000733d  lea     rax, [rsp+48h+arg_0]
0x140007342  mov     r9d, 4; TokenInformationLength
0x140007348  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14000734d  lea     r8, [rdi+68h]; TokenInformation
0x140007351  mov     [rsp+48h+arg_0], esi
0x140007355  mov     edx, 0Ch; TokenInformationClass
0x14000735a  call    cs:__imp_GetTokenInformation
0x140007360  test    eax, eax
0x140007362  jnz     loc_14000743B
0x140007368  call    GetLastErrorAsHResult
0x14000736d  mov     ebx, eax
0x14000736f  jmp     loc_14000743D
0x140007374  mov     rdi, rsi
0x140007377  mov     esi, 8007000Eh
0x14000737c  jmp     short loc_1400073A8
0x14000737e  test    eax, eax
0x140007380  js      loc_140007441
0x140007386  mov     [rdi+64h], ebx
0x140007389  mov     rcx, rdi
0x14000738c  mov     rax, [rdi]
0x14000738f  mov     rax, [rax+10h]
0x140007393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007398  mov     r15, [rsp+48h+arg_10]
0x14000739d  mov     esi, eax
0x14000739f  mov     r14, [rsp+48h+arg_8]
0x1400073a4  test    eax, eax
0x1400073a6  jns     short loc_1400073BA
0x1400073a8  mov     rcx, rdi; this
0x1400073ab  call    ?EasyRelease@NCoreLibrary@@YAXPEAVTReferenceCount@1@@Z; NCoreLibrary::EasyRelease(NCoreLibrary::TReferenceCount *)
0x1400073b0  mov     eax, esi
0x1400073b2  add     rsp, 30h
0x1400073b6  pop     rdi
0x1400073b7  pop     rsi
0x1400073b8  pop     rbx
0x1400073b9  retn
0x1400073ba  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400073c1  call    cs:__imp_EnterCriticalSection
0x1400073c7  mov     rbx, cs:qword_1400CBC48
0x1400073ce  test    rbx, rbx
0x1400073d1  jz      short loc_140007424
0x1400073d3  mov     eax, [rbx+8]
0x1400073d6  cmp     eax, 7FFFFFFFh
0x1400073db  jz      short loc_1400073FB
0x1400073dd  nop     dword ptr [rax]
0x1400073e0  lea     edx, [rax+1]
0x1400073e3  lock cmpxchg [rbx+8], edx
0x1400073e8  jz      short loc_1400073F4
0x1400073ea  mov     eax, [rbx+8]
0x1400073ed  cmp     eax, 7FFFFFFFh
0x1400073f2  jnz     short loc_1400073E0
0x1400073f4  mov     rbx, cs:qword_1400CBC48
0x1400073fb  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140007402  call    cs:__imp_LeaveCriticalSection
0x140007408  mov     rdx, rdi; struct NThreadingLibrary::TWorkItem *
0x14000740b  mov     rcx, rbx; this
0x14000740e  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x140007413  mov     esi, eax
0x140007415  test    rbx, rbx
0x140007418  jz      short loc_1400073A8
0x14000741a  mov     rcx, rbx; this
0x14000741d  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x140007422  jmp     short loc_1400073A8
0x140007424  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000742b  call    cs:__imp_LeaveCriticalSection
0x140007431  mov     esi, 80004003h
0x140007436  jmp     loc_1400073A8
0x14000743b  mov     ebx, esi
0x14000743d  test    ebx, ebx
0x14000743f  jns     short loc_140007468
0x140007441  cmp     ebx, 800703F0h
0x140007447  jz      loc_140007386
0x14000744d  mov     r8d, ebx
0x140007450  lea     rdx, aFailedErrorHr0_1; "Failed.  Error hr: 0x%x."
0x140007457  lea     rcx, aNrouterTsessio; "NRouter::TSessionCapture::TSessionCaptu"...
0x14000745e  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140007463  jmp     loc_140007386
0x140007468  mov     rcx, [rdi+70h]; void *
0x14000746c  call    ?IsTokenLocalSystem@@YAJPEAX@Z; IsTokenLocalSystem(void *)
0x140007471  mov     ebx, eax
0x140007473  test    eax, eax
0x140007475  js      short loc_140007441
0x140007477  jnz     short loc_140007483
0x140007479  mov     ebx, 800703F0h
0x14000747e  jmp     loc_140007386
0x140007483  call    CheckLocalCall
0x140007488  mov     ebx, eax
0x14000748a  cmp     eax, 1
0x14000748d  jnz     loc_14000737E
0x140007493  mov     ebx, 800703F0h
0x140007498  jmp     loc_140007386
```
