# UbpmpDelayedTerminateProcessCallback

- ea: `0x180031940`
- end: `0x1800319da`
- name: `UbpmpDelayedTerminateProcessCallback`
- size: `154`
- prototype: `__int64 __fastcall(HANDLE hObject)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x18002b5bc`
- `0x180031940`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18003195b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18003195b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003198b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003198b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003196f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003196f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800319c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800319c2`

## pseudocode

```c
void __fastcall UbpmpDelayedTerminateProcessCallback(HANDLE hObject)
{
  DWORD LastError; // edi
  DWORD ProcessId; // eax
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  DWORD v7; // [rsp+40h] [rbp+8h] BYREF
  DWORD v8; // [rsp+58h] [rbp+20h] BYREF

  if ( hObject )
  {
    if ( TerminateProcess(hObject, 0x42Bu) )
      LastError = 0;
    else
      LastError = GetLastError();
    if ( (unsigned int)dword_18004F0F0 > 5 )
    {
      ProcessId = GetProcessId(hObject);
      v8 = LastError;
      v7 = ProcessId;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v4,
        (unsigned __int8 *)&dword_18004746C,
        v5,
        v6,
        (__int64)&v8,
        (__int64)&v7);
    }
    CloseHandle(hObject);
  }
}

```

## disassembly

```asm
0x180031940  test    rcx, rcx
0x180031943  jz      locret_1800319D8
0x180031949  mov     [rsp+arg_8], rbx
0x18003194e  push    rdi
0x18003194f  sub     rsp, 30h
0x180031953  mov     edx, 42Bh; uExitCode
0x180031958  mov     rbx, rcx
0x18003195b  call    cs:__imp_TerminateProcess
0x180031962  nop     dword ptr [rax+rax+00h]
0x180031967  test    eax, eax
0x180031969  jz      short loc_18003196F
0x18003196b  xor     edi, edi
0x18003196d  jmp     short loc_18003197D
0x18003196f  call    cs:__imp_GetLastError
0x180031976  nop     dword ptr [rax+rax+00h]
0x18003197b  mov     edi, eax
0x18003197d  mov     ecx, cs:dword_18004F0F0
0x180031983  cmp     ecx, 5
0x180031986  jbe     short loc_1800319BF
0x180031988  mov     rcx, rbx; Process
0x18003198b  call    cs:__imp_GetProcessId
0x180031992  nop     dword ptr [rax+rax+00h]
0x180031997  lea     rdx, dword_18004746C
0x18003199e  mov     [rsp+38h+arg_18], edi
0x1800319a2  mov     [rsp+38h+arg_0], eax
0x1800319a6  lea     rax, [rsp+38h+arg_0]
0x1800319ab  mov     [rsp+38h+var_10], rax
0x1800319b0  lea     rax, [rsp+38h+arg_18]
0x1800319b5  mov     [rsp+38h+var_18], rax
0x1800319ba  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800319bf  mov     rcx, rbx; hObject
0x1800319c2  call    cs:__imp_CloseHandle
0x1800319c9  nop     dword ptr [rax+rax+00h]
0x1800319ce  mov     rbx, [rsp+38h+arg_8]
0x1800319d3  add     rsp, 30h
0x1800319d7  pop     rdi
0x1800319d8  retn
```
