# sandbox::RevertToProcessSelf::RevertToProcessSelf(void)

- ea: `0x140075b58`
- end: `0x140075c0a`
- name: `??0RevertToProcessSelf@sandbox@@QEAA@XZ`
- size: `178`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140074810`
- `0x140074930`
- `0x140074a30`
- `0x140074bf0`

## callees

- `0x140007bdc`
- `0x14000e904`
- `0x140014e14`
- `0x140014fc4`
- `0x140057e2c`
- `0x140075b58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140075bca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140075bca`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140075bef`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140075bef`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140075bc0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140075bc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140075b7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140075ba9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140075b7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140075ba9`

## pseudocode

```c
HANDLE *__fastcall sandbox::RevertToProcessSelf::RevertToProcessSelf(HANDLE *TokenHandle)
{
  HANDLE CurrentThread; // rax
  void **v3; // r9
  unsigned int v4; // eax
  int v5; // edx
  int LastErrorAsFailHRNoBreak; // eax
  HANDLE v7; // rax
  NCoreLibrary *v8; // rcx

  *TokenHandle = (HANDLE)-1LL;
  *((_DWORD *)TokenHandle + 2) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    CurrentThread = GetCurrentThread();
    v4 = SecurityHelper::OpenThreadToken(CurrentThread, 0xF01FFu, TokenHandle, v3);
    if ( v4 && v4 != 1008 )
    {
      LastErrorAsFailHRNoBreak = NCoreLibrary::HResultFromWin32((NCoreLibrary *)v4, v5);
LABEL_8:
      *((_DWORD *)TokenHandle + 2) = LastErrorAsFailHRNoBreak;
    }
  }
  else
  {
    v7 = GetCurrentThread();
    if ( !OpenThreadToken(v7, 0xF01FFu, 1, TokenHandle) && GetLastError() != 1008 )
    {
      LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v8);
      goto LABEL_8;
    }
  }
  if ( (char *)*TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && !SetThreadToken(0, 0) )
    *((_DWORD *)TokenHandle + 2) = GetLastErrorAsHResult();
  return TokenHandle;
}

```

## disassembly

```asm
0x140075b58  push    rbx
0x140075b5a  sub     rsp, 20h
0x140075b5e  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x140075b65  mov     rbx, rcx
0x140075b68  mov     dword ptr [rcx+8], 0
0x140075b6f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x140075b76  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140075b7b  test    al, al
0x140075b7d  jz      short loc_140075BA9
0x140075b7f  call    cs:__imp_GetCurrentThread
0x140075b85  mov     r8, rbx; TokenHandle
0x140075b88  mov     edx, 0F01FFh; DesiredAccess
0x140075b8d  mov     rcx, rax; ThreadHandle
0x140075b90  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x140075b95  test    eax, eax
0x140075b97  jz      short loc_140075BDF
0x140075b99  cmp     eax, 3F0h
0x140075b9e  jz      short loc_140075BDF
0x140075ba0  mov     ecx, eax; this
0x140075ba2  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x140075ba7  jmp     short loc_140075BDC
0x140075ba9  call    cs:__imp_GetCurrentThread
0x140075baf  mov     r9, rbx; TokenHandle
0x140075bb2  mov     edx, 0F01FFh; DesiredAccess
0x140075bb7  mov     rcx, rax; ThreadHandle
0x140075bba  mov     r8d, 1; OpenAsSelf
0x140075bc0  call    cs:__imp_OpenThreadToken
0x140075bc6  test    eax, eax
0x140075bc8  jnz     short loc_140075BDF
0x140075bca  call    cs:__imp_GetLastError
0x140075bd0  cmp     eax, 3F0h
0x140075bd5  jz      short loc_140075BDF
0x140075bd7  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140075bdc  mov     [rbx+8], eax
0x140075bdf  mov     rax, [rbx]
0x140075be2  dec     rax
0x140075be5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140075be9  ja      short loc_140075C01
0x140075beb  xor     edx, edx; Token
0x140075bed  xor     ecx, ecx; Thread
0x140075bef  call    cs:__imp_SetThreadToken
0x140075bf5  test    eax, eax
0x140075bf7  jnz     short loc_140075C01
0x140075bf9  call    GetLastErrorAsHResult
0x140075bfe  mov     [rbx+8], eax
0x140075c01  mov     rax, rbx
0x140075c04  add     rsp, 20h
0x140075c08  pop     rbx
0x140075c09  retn
```
