# CaptureUserInfo

- ea: `0x140007d80`
- end: `0x140007fd7`
- name: `CaptureUserInfo`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000e250`

## callees

- `0x140007090`
- `0x140007600`
- `0x140007d80`
- `0x140008550`
- `0x1400085b0`
- `0x1400087c8`
- `0x1400087f0`
- `0x14000f290`
- `0x140015378`
- `0x14002cd10`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007f52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007f88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007f52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007f88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140007f09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140007f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007e3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007e3b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140007e2b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140007e6a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140007e2b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140007e6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140007e10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140007e4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140007e10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140007e4c`

## pseudocode

```c
__int64 CaptureUserInfo()
{
  struct NThreadingLibrary::TWorkItem *v0; // rax
  struct NCoreLibrary::TReferenceCount *v1; // rdx
  struct NThreadingLibrary::TWorkItem *v2; // rdi
  char *v3; // rax
  HANDLE CurrentThread; // rax
  NRouter::TSessionCapture *v5; // rcx
  HANDLE v6; // rax
  int LastErrorAsHResult; // ebx
  int v8; // esi
  volatile signed __int32 *v10; // rbx
  signed __int32 v11; // eax
  int v12; // eax
  int v13; // eax

  v0 = (struct NThreadingLibrary::TWorkItem *)operator new(0x78u);
  v2 = v0;
  if ( !v0 )
  {
    v2 = 0;
    v8 = -2147024882;
    goto LABEL_12;
  }
  *((_DWORD *)v0 + 2) = 1;
  *((_QWORD *)v0 + 3) = 0;
  v3 = (char *)v0 + 32;
  *((_DWORD *)v3 + 2) = 1802398836;
  *((_QWORD *)v3 + 2) = v3;
  *((_QWORD *)v3 + 3) = v3;
  *((_QWORD *)v2 + 8) = 1953063799;
  *(_QWORD *)v2 = &NRouter::TSessionCapture::`vftable'{for `NCoreLibrary::TReferenceCount'};
  *((_QWORD *)v2 + 2) = &NRouter::TSessionCapture::`vftable'{for `NThreadingLibrary::TTpSetWorkEnv'};
  *(_QWORD *)v3 = &NRouter::TSessionCapture::`vftable'{for `NCoreLibrary::TLink'};
  *((_DWORD *)v2 + 18) = 0;
  *((_DWORD *)v2 + 22) = 0;
  *((_QWORD *)v2 + 10) = 0;
  *((_DWORD *)v2 + 24) = 1633903987;
  *((_DWORD *)v2 + 25) = -2147467259;
  *((_DWORD *)v2 + 26) = 0;
  *((_QWORD *)v2 + 14) = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 0, (PHANDLE)v2 + 14) )
  {
    if ( GetLastError() != 5 || (v6 = GetCurrentThread(), !OpenThreadToken(v6, 0xEu, 1, (PHANDLE)v2 + 14)) )
    {
      LastErrorAsHResult = GetLastErrorAsHResult();
      if ( LastErrorAsHResult < 0 )
        goto LABEL_7;
    }
  }
  LastErrorAsHResult = NRouter::TSessionCapture::GetTokenSession(v5, *((void **)v2 + 14), (unsigned int *)v2 + 26);
  if ( LastErrorAsHResult < 0 )
    goto LABEL_7;
  v12 = IsTokenLocalSystem(*((void **)v2 + 14));
  LastErrorAsHResult = v12;
  if ( v12 < 0 )
    goto LABEL_7;
  if ( !v12 )
  {
    LastErrorAsHResult = -2147023888;
    goto LABEL_11;
  }
  v13 = CheckLocalCall();
  LastErrorAsHResult = v13;
  if ( v13 != 1 )
  {
    if ( v13 >= 0 )
      goto LABEL_11;
LABEL_7:
    if ( LastErrorAsHResult != -2147023888 )
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "NRouter::TSessionCapture::TSessionCapture",
        L"Failed.  Error hr: 0x%x.",
        (unsigned int)LastErrorAsHResult);
    goto LABEL_11;
  }
  LastErrorAsHResult = -2147023888;
LABEL_11:
  *((_DWORD *)v2 + 25) = LastErrorAsHResult;
  v8 = (*(__int64 (__fastcall **)(struct NThreadingLibrary::TWorkItem *))(*(_QWORD *)v2 + 16LL))(v2);
  if ( v8 >= 0 )
  {
    EnterCriticalSection(&RouterNotifySection);
    v10 = (volatile signed __int32 *)qword_1400D2DC8;
    if ( qword_1400D2DC8 )
    {
      v11 = *((_DWORD *)qword_1400D2DC8 + 2);
      if ( v11 != 0x7FFFFFFF )
      {
        do
        {
          if ( v11 == _InterlockedCompareExchange(v10 + 2, v11 + 1, v11) )
            break;
          v11 = *((_DWORD *)v10 + 2);
        }
        while ( v11 != 0x7FFFFFFF );
        v10 = (volatile signed __int32 *)qword_1400D2DC8;
      }
      LeaveCriticalSection(&RouterNotifySection);
      v8 = NThreadingLibrary::TWorkCrew::AddItem((NThreadingLibrary::TWorkCrew *)v10, v2);
      if ( v10 )
        NCoreLibrary::TReferenceCount::Release((NCoreLibrary::TReferenceCount *)v10);
    }
    else
    {
      LeaveCriticalSection(&RouterNotifySection);
      v8 = -2147467261;
    }
  }
LABEL_12:
  NCoreLibrary::EasyRelease(v2, v1);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140007d80  mov     [rsp+arg_8], rbx
0x140007d85  mov     [rsp+arg_10], rsi
0x140007d8a  push    rdi
0x140007d8b  sub     rsp, 20h
0x140007d8f  mov     ecx, 78h ; 'x'; Size
0x140007d94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007d99  xor     ecx, ecx
0x140007d9b  mov     rdi, rax
0x140007d9e  test    rax, rax
0x140007da1  jz      loc_140007EBC
0x140007da7  mov     dword ptr [rax+8], 1
0x140007dae  lea     rdx, ??_7TSessionCapture@NRouter@@6BTReferenceCount@NCoreLibrary@@@; const NRouter::TSessionCapture::`vftable'{for `NCoreLibrary::TReferenceCount'}
0x140007db5  mov     [rax+18h], rcx
0x140007db9  add     rax, 20h ; ' '
0x140007dbd  mov     [rsp+28h+arg_0], r14
0x140007dc2  mov     dword ptr [rax+8], 6B6E6C74h
0x140007dc9  mov     [rax+10h], rax
0x140007dcd  mov     [rax+18h], rax
0x140007dd1  mov     qword ptr [rdi+40h], 74696377h
0x140007dd9  mov     [rdi], rdx
0x140007ddc  lea     rdx, ??_7TSessionCapture@NRouter@@6BTTpSetWorkEnv@NThreadingLibrary@@@; const NRouter::TSessionCapture::`vftable'{for `NThreadingLibrary::TTpSetWorkEnv'}
0x140007de3  mov     [rdi+10h], rdx
0x140007de7  lea     rdx, ??_7TSessionCapture@NRouter@@6BTLink@NCoreLibrary@@@; const NRouter::TSessionCapture::`vftable'{for `NCoreLibrary::TLink'}
0x140007dee  mov     [rax], rdx
0x140007df1  mov     [rdi+48h], ecx
0x140007df4  mov     [rdi+58h], ecx
0x140007df7  mov     [rdi+50h], rcx
0x140007dfb  mov     dword ptr [rdi+60h], 61636573h
0x140007e02  mov     dword ptr [rdi+64h], 80004005h
0x140007e09  mov     [rdi+68h], ecx
0x140007e0c  mov     [rdi+70h], rcx
0x140007e10  call    cs:__imp_GetCurrentThread
0x140007e17  nop     dword ptr [rax+rax+00h]
0x140007e1c  lea     r9, [rdi+70h]; TokenHandle
0x140007e20  xor     r8d, r8d; OpenAsSelf
0x140007e23  mov     rcx, rax; ThreadHandle
0x140007e26  mov     edx, 0Eh; DesiredAccess
0x140007e2b  call    cs:__imp_OpenThreadToken
0x140007e32  nop     dword ptr [rax+rax+00h]
0x140007e37  test    eax, eax
0x140007e39  jnz     short loc_140007E85
0x140007e3b  call    cs:__imp_GetLastError
0x140007e42  nop     dword ptr [rax+rax+00h]
0x140007e47  cmp     eax, 5
0x140007e4a  jnz     short loc_140007E7A
0x140007e4c  call    cs:__imp_GetCurrentThread
0x140007e53  nop     dword ptr [rax+rax+00h]
0x140007e58  lea     r9, [rdi+70h]; TokenHandle
0x140007e5c  mov     edx, 0Eh; DesiredAccess
0x140007e61  mov     rcx, rax; ThreadHandle
0x140007e64  mov     r8d, 1; OpenAsSelf
0x140007e6a  call    cs:__imp_OpenThreadToken
0x140007e71  nop     dword ptr [rax+rax+00h]
0x140007e76  test    eax, eax
0x140007e78  jnz     short loc_140007E85
0x140007e7a  call    GetLastErrorAsHResult
0x140007e7f  mov     ebx, eax
0x140007e81  test    eax, eax
0x140007e83  js      short loc_140007E9C
0x140007e85  mov     rdx, [rdi+70h]; void *
0x140007e89  lea     r8, [rdi+68h]; unsigned int *
0x140007e8d  call    ?GetTokenSession@TSessionCapture@NRouter@@AEBAJPEAXPEAK@Z; NRouter::TSessionCapture::GetTokenSession(void *,ulong *)
0x140007e92  mov     ebx, eax
0x140007e94  test    eax, eax
0x140007e96  jns     loc_140007F9E
0x140007e9c  cmp     ebx, 800703F0h
0x140007ea2  jz      short loc_140007ECA
0x140007ea4  mov     r8d, ebx
0x140007ea7  lea     rdx, aFailedErrorHr0_1; "Failed.  Error hr: 0x%x."
0x140007eae  lea     rcx, aNrouterTsessio; "NRouter::TSessionCapture::TSessionCaptu"...
0x140007eb5  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140007eba  jmp     short loc_140007ECA
0x140007ebc  mov     rdi, rcx
0x140007ebf  mov     esi, 8007000Eh
0x140007ec4  jmp     short loc_140007EE7
0x140007ec6  test    eax, eax
0x140007ec8  js      short loc_140007E9C
0x140007eca  mov     [rdi+64h], ebx
0x140007ecd  mov     rcx, rdi
0x140007ed0  mov     rax, [rdi]
0x140007ed3  mov     rax, [rax+10h]
0x140007ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007edc  mov     r14, [rsp+28h+arg_0]
0x140007ee1  mov     esi, eax
0x140007ee3  test    eax, eax
0x140007ee5  jns     short loc_140007F02
0x140007ee7  mov     rcx, rdi; this
0x140007eea  call    ?EasyRelease@NCoreLibrary@@YAXPEAVTReferenceCount@1@@Z; NCoreLibrary::EasyRelease(NCoreLibrary::TReferenceCount *)
0x140007eef  mov     rbx, [rsp+28h+arg_8]
0x140007ef4  mov     eax, esi
0x140007ef6  mov     rsi, [rsp+28h+arg_10]
0x140007efb  add     rsp, 20h
0x140007eff  pop     rdi
0x140007f00  retn
0x140007f02  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140007f09  call    cs:__imp_EnterCriticalSection
0x140007f10  nop     dword ptr [rax+rax+00h]
0x140007f15  mov     rbx, cs:qword_1400D2DC8
0x140007f1c  test    rbx, rbx
0x140007f1f  jz      short loc_140007F81
0x140007f21  mov     eax, [rbx+8]
0x140007f24  cmp     eax, 7FFFFFFFh
0x140007f29  jz      short loc_140007F4B
0x140007f2b  nop     dword ptr [rax+rax+00h]
0x140007f30  lea     edx, [rax+1]
0x140007f33  lock cmpxchg [rbx+8], edx
0x140007f38  jz      short loc_140007F44
0x140007f3a  mov     eax, [rbx+8]
0x140007f3d  cmp     eax, 7FFFFFFFh
0x140007f42  jnz     short loc_140007F30
0x140007f44  mov     rbx, cs:qword_1400D2DC8
0x140007f4b  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140007f52  call    cs:__imp_LeaveCriticalSection
0x140007f59  nop     dword ptr [rax+rax+00h]
0x140007f5e  mov     rdx, rdi; struct NThreadingLibrary::TWorkItem *
0x140007f61  mov     rcx, rbx; this
0x140007f64  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x140007f69  mov     esi, eax
0x140007f6b  test    rbx, rbx
0x140007f6e  jz      loc_140007EE7
0x140007f74  mov     rcx, rbx; this
0x140007f77  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x140007f7c  jmp     loc_140007EE7
0x140007f81  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140007f88  call    cs:__imp_LeaveCriticalSection
0x140007f8f  nop     dword ptr [rax+rax+00h]
0x140007f94  mov     esi, 80004003h
0x140007f99  jmp     loc_140007EE7
0x140007f9e  mov     rcx, [rdi+70h]; void *
0x140007fa2  call    ?IsTokenLocalSystem@@YAJPEAX@Z; IsTokenLocalSystem(void *)
0x140007fa7  mov     ebx, eax
0x140007fa9  test    eax, eax
0x140007fab  js      loc_140007E9C
0x140007fb1  jnz     short loc_140007FBD
0x140007fb3  mov     ebx, 800703F0h
0x140007fb8  jmp     loc_140007ECA
0x140007fbd  call    CheckLocalCall
0x140007fc2  mov     ebx, eax
0x140007fc4  cmp     eax, 1
0x140007fc7  jnz     loc_140007EC6
0x140007fcd  mov     ebx, 800703F0h
0x140007fd2  jmp     loc_140007ECA
```
