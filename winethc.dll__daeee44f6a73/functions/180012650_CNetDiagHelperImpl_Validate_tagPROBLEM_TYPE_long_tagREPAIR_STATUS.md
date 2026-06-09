# CNetDiagHelperImpl::Validate(tagPROBLEM_TYPE,long *,tagREPAIR_STATUS *)

- ea: `0x180012650`
- end: `0x1800126a9`
- name: `?Validate@CNetDiagHelperImpl@@UEAAJW4tagPROBLEM_TYPE@@PEAJPEAW4tagREPAIR_STATUS@@@Z`
- size: `89`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, enum tagPROBLEM_TYPE, int *, enum tagREPAIR_STATUS *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180012650`
- `0x180012ca0`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::Validate(
        CNetDiagHelperImpl *this,
        enum tagPROBLEM_TYPE a2,
        int *a3,
        enum tagREPAIR_STATUS *a4)
{
  __int64 result; // rax

  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  result = 2147500033LL;
  *a3 = 0;
  *a4 = RS_NOT_IMPLEMENTED;
  return result;
}

```

## disassembly

```asm
0x180012650  mov     [rsp+arg_0], rbx
0x180012655  mov     [rsp+arg_8], rsi
0x18001265a  push    rdi
0x18001265b  sub     rsp, 20h
0x18001265f  mov     rbx, r9
0x180012662  mov     rdi, r8
0x180012665  mov     rsi, rcx
0x180012668  test    r8, r8
0x18001266b  jnz     short loc_180012672
0x18001266d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180012672  test    rbx, rbx
0x180012675  jnz     short loc_18001267C
0x180012677  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001267c  cmp     dword ptr [rsi+10h], 1
0x180012680  jz      short loc_180012687
0x180012682  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180012687  mov     rsi, [rsp+28h+arg_8]
0x18001268c  mov     eax, 80004001h
0x180012691  mov     dword ptr [rdi], 0
0x180012697  mov     dword ptr [rbx], 0
0x18001269d  mov     rbx, [rsp+28h+arg_0]
0x1800126a2  add     rsp, 20h
0x1800126a6  pop     rdi
0x1800126a7  retn
```
