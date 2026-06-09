# Execution::ExecutionServices::_WorkerThread(void *)

- ea: `0x18007cfa0`
- end: `0x18007d0b5`
- name: `?_WorkerThread@ExecutionServices@Execution@@KAKPEAX@Z`
- size: `277`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180039090`
- `0x18007cfa0`
- `0x18007d134`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007d079`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007d079`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007cfd1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007cfd1`
- `CoreMessaging!CoreUICreate` at `0x18007d006`
- `CoreMessaging!CoreUICreate` at `0x18007d006`

## pseudocode

```c
__int64 __fastcall Execution::ExecutionServices::_WorkerThread(_DWORD *Parameter)
{
  __int64 v2; // rcx
  char v3; // di
  bool v4; // zf
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  _DWORD *v9; // [rsp+48h] [rbp+10h] BYREF

  v9 = Parameter;
  if ( !Parameter )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v2 = 0;
  v3 = 0;
  v4 = Parameter[35] == 1;
  v8 = 0;
  if ( v4 )
  {
    if ( CoInitializeEx(0, 0) < 0 )
      goto LABEL_14;
    v2 = v8;
    v3 = 1;
  }
  if ( v2 )
  {
    v8 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  if ( (int)CoreUICreate(&v8) >= 0
    && (*(int (__fastcall **)(__int64, _QWORD, __int64 (__fastcall *)(void *, unsigned int, void *), _DWORD *))(*(_QWORD *)v8 + 272LL))(
         v8,
         *((_QWORD *)Parameter + 15),
         Execution::ExecutionServices::_DoWorkCallback,
         Parameter) >= 0
    && (*(int (__fastcall **)(__int64, _QWORD, __int64 (__fastcall *)(void *, unsigned int, void *), _DWORD *))(*(_QWORD *)v8 + 272LL))(
         v8,
         *((_QWORD *)Parameter + 14),
         Execution::ExecutionServices::_TerminateCallback,
         Parameter) >= 0 )
  {
    v5 = v8;
    *((_QWORD *)Parameter + 7) = v8;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 232LL))(v5);
  }
  if ( v3 )
    CoUninitialize();
LABEL_14:
  v6 = v8;
  if ( v8 )
  {
    v8 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  return 0;
}

```

## disassembly

```asm
0x18007cfa0  mov     [rsp+arg_10], rbx
0x18007cfa5  push    rdi
0x18007cfa6  sub     rsp, 30h
0x18007cfaa  mov     [rsp+38h+arg_8], rcx
0x18007cfaf  mov     rbx, rcx
0x18007cfb2  test    rcx, rcx
0x18007cfb5  jnz     short loc_18007CFBC
0x18007cfb7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007cfbc  xor     ecx, ecx; pvReserved
0x18007cfbe  xor     dil, dil
0x18007cfc1  cmp     dword ptr [rbx+8Ch], 1
0x18007cfc8  mov     [rsp+38h+arg_0], rcx
0x18007cfcd  jnz     short loc_18007CFE7
0x18007cfcf  xor     edx, edx; dwCoInit
0x18007cfd1  call    cs:__imp_CoInitializeEx
0x18007cfd7  test    eax, eax
0x18007cfd9  js      loc_18007D07F
0x18007cfdf  mov     rcx, [rsp+38h+arg_0]
0x18007cfe4  mov     dil, 1
0x18007cfe7  test    rcx, rcx
0x18007cfea  jz      short loc_18007D001
0x18007cfec  mov     [rsp+38h+arg_0], 0
0x18007cff5  mov     rax, [rcx]
0x18007cff8  mov     rax, [rax+10h]
0x18007cffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d001  lea     rcx, [rsp+38h+arg_0]
0x18007d006  call    cs:__imp_CoreUICreate
0x18007d00c  test    eax, eax
0x18007d00e  js      short loc_18007D074
0x18007d010  mov     rcx, [rsp+38h+arg_0]
0x18007d015  lea     r8, ?_DoWorkCallback@ExecutionServices@Execution@@KAJPEAXK0@Z; Execution::ExecutionServices::_DoWorkCallback(void *,ulong,void *)
0x18007d01c  mov     rdx, [rbx+78h]
0x18007d020  mov     r9, rbx
0x18007d023  mov     rax, [rcx]
0x18007d026  mov     rax, [rax+110h]
0x18007d02d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d032  test    eax, eax
0x18007d034  js      short loc_18007D074
0x18007d036  mov     rcx, [rsp+38h+arg_0]
0x18007d03b  lea     r8, ?_TerminateCallback@ExecutionServices@Execution@@KAJPEAXK0@Z; Execution::ExecutionServices::_TerminateCallback(void *,ulong,void *)
0x18007d042  mov     rdx, [rbx+70h]
0x18007d046  mov     r9, rbx
0x18007d049  mov     rax, [rcx]
0x18007d04c  mov     rax, [rax+110h]
0x18007d053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d058  test    eax, eax
0x18007d05a  js      short loc_18007D074
0x18007d05c  mov     rcx, [rsp+38h+arg_0]
0x18007d061  mov     [rbx+38h], rcx
0x18007d065  mov     rax, [rcx]
0x18007d068  mov     rax, [rax+0E8h]
0x18007d06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d074  test    dil, dil
0x18007d077  jz      short loc_18007D07F
0x18007d079  call    cs:__imp_CoUninitialize
0x18007d07f  mov     rcx, [rsp+38h+arg_0]
0x18007d084  test    rcx, rcx
0x18007d087  jz      short loc_18007D09E
0x18007d089  mov     [rsp+38h+arg_0], 0
0x18007d092  mov     rax, [rcx]
0x18007d095  mov     rax, [rax+10h]
0x18007d099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d09e  lea     rcx, [rsp+38h+arg_8]
0x18007d0a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007d0a8  mov     rbx, [rsp+38h+arg_10]
0x18007d0ad  xor     eax, eax
0x18007d0af  add     rsp, 30h
0x18007d0b3  pop     rdi
0x18007d0b4  retn
```
