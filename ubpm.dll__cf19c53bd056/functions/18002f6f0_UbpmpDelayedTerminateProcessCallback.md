# UbpmpDelayedTerminateProcessCallback

- ea: `0x18002f6f0`
- end: `0x18002f76d`
- name: `UbpmpDelayedTerminateProcessCallback`
- size: `125`
- prototype: `__int64 __fastcall(HANDLE hObject)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x1800295cc`
- `0x18002f6f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002f707`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002f707`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002f72b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002f72b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f715`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f75c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f75c`

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
    if ( (unsigned int)dword_18004C0F0 > 5 )
    {
      ProcessId = GetProcessId(hObject);
      v8 = LastError;
      v7 = ProcessId;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v4,
        (unsigned __int8 *)&dword_180044404,
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
0x18002f6f0  test    rcx, rcx
0x18002f6f3  jz      short locret_18002F76C
0x18002f6f5  mov     [rsp+arg_8], rbx
0x18002f6fa  push    rdi
0x18002f6fb  sub     rsp, 30h
0x18002f6ff  mov     edx, 42Bh; uExitCode
0x18002f704  mov     rbx, rcx
0x18002f707  call    cs:__imp_TerminateProcess
0x18002f70d  test    eax, eax
0x18002f70f  jz      short loc_18002F715
0x18002f711  xor     edi, edi
0x18002f713  jmp     short loc_18002F71D
0x18002f715  call    cs:__imp_GetLastError
0x18002f71b  mov     edi, eax
0x18002f71d  mov     ecx, cs:dword_18004C0F0
0x18002f723  cmp     ecx, 5
0x18002f726  jbe     short loc_18002F759
0x18002f728  mov     rcx, rbx; Process
0x18002f72b  call    cs:__imp_GetProcessId
0x18002f731  lea     rdx, dword_180044404
0x18002f738  mov     [rsp+38h+arg_18], edi
0x18002f73c  mov     [rsp+38h+arg_0], eax
0x18002f740  lea     rax, [rsp+38h+arg_0]
0x18002f745  mov     [rsp+38h+var_10], rax
0x18002f74a  lea     rax, [rsp+38h+arg_18]
0x18002f74f  mov     [rsp+38h+var_18], rax
0x18002f754  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002f759  mov     rcx, rbx; hObject
0x18002f75c  call    cs:__imp_CloseHandle
0x18002f762  mov     rbx, [rsp+38h+arg_8]
0x18002f767  add     rsp, 30h
0x18002f76b  pop     rdi
0x18002f76c  retn
```
