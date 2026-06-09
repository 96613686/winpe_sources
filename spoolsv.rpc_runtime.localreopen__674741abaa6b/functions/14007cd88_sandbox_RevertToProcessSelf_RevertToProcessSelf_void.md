# sandbox::RevertToProcessSelf::RevertToProcessSelf(void)

- ea: `0x14007cd88`
- end: `0x14007ce59`
- name: `??0RevertToProcessSelf@sandbox@@QEAA@XZ`
- size: `209`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14007b9d0`
- `0x14007baf0`
- `0x14007bbf0`
- `0x14007bdb0`

## callees

- `0x1400087c8`
- `0x14000fb58`
- `0x140016120`
- `0x140016314`
- `0x14005d4e0`
- `0x14007cd88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007ce0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007ce0c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14007ce37`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14007ce37`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14007cdfc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14007cdfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14007cdaf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14007cddf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14007cdaf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14007cddf`

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
0x14007cd88  push    rbx
0x14007cd8a  sub     rsp, 20h
0x14007cd8e  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x14007cd95  mov     rbx, rcx
0x14007cd98  mov     dword ptr [rcx+8], 0
0x14007cd9f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x14007cda6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x14007cdab  test    al, al
0x14007cdad  jz      short loc_14007CDDF
0x14007cdaf  call    cs:__imp_GetCurrentThread
0x14007cdb6  nop     dword ptr [rax+rax+00h]
0x14007cdbb  mov     r8, rbx; TokenHandle
0x14007cdbe  mov     edx, 0F01FFh; DesiredAccess
0x14007cdc3  mov     rcx, rax; ThreadHandle
0x14007cdc6  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x14007cdcb  test    eax, eax
0x14007cdcd  jz      short loc_14007CE27
0x14007cdcf  cmp     eax, 3F0h
0x14007cdd4  jz      short loc_14007CE27
0x14007cdd6  mov     ecx, eax; this
0x14007cdd8  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x14007cddd  jmp     short loc_14007CE24
0x14007cddf  call    cs:__imp_GetCurrentThread
0x14007cde6  nop     dword ptr [rax+rax+00h]
0x14007cdeb  mov     r9, rbx; TokenHandle
0x14007cdee  mov     edx, 0F01FFh; DesiredAccess
0x14007cdf3  mov     rcx, rax; ThreadHandle
0x14007cdf6  mov     r8d, 1; OpenAsSelf
0x14007cdfc  call    cs:__imp_OpenThreadToken
0x14007ce03  nop     dword ptr [rax+rax+00h]
0x14007ce08  test    eax, eax
0x14007ce0a  jnz     short loc_14007CE27
0x14007ce0c  call    cs:__imp_GetLastError
0x14007ce13  nop     dword ptr [rax+rax+00h]
0x14007ce18  cmp     eax, 3F0h
0x14007ce1d  jz      short loc_14007CE27
0x14007ce1f  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x14007ce24  mov     [rbx+8], eax
0x14007ce27  mov     rax, [rbx]
0x14007ce2a  dec     rax
0x14007ce2d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14007ce31  ja      short loc_14007CE4F
0x14007ce33  xor     edx, edx; Token
0x14007ce35  xor     ecx, ecx; Thread
0x14007ce37  call    cs:__imp_SetThreadToken
0x14007ce3e  nop     dword ptr [rax+rax+00h]
0x14007ce43  test    eax, eax
0x14007ce45  jnz     short loc_14007CE4F
0x14007ce47  call    GetLastErrorAsHResult
0x14007ce4c  mov     [rbx+8], eax
0x14007ce4f  mov     rax, rbx
0x14007ce52  add     rsp, 20h
0x14007ce56  pop     rbx
0x14007ce57  retn
```
