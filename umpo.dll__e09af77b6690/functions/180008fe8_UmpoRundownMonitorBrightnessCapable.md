# UmpoRundownMonitorBrightnessCapable

- ea: `0x180008fe8`
- end: `0x180009095`
- name: `UmpoRundownMonitorBrightnessCapable`
- size: `173`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008c80`

## callees

- `0x180008fe8`
- `0x180010070`
- `0x180010946`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000908d`
- `ntdll!EtwEventWrite` at `0x18000908d`
- `ntdll!NtPowerInformation` at `0x180009036`
- `ntdll!NtPowerInformation` at `0x180009036`

## pseudocode

```c
NTSTATUS UmpoRundownMonitorBrightnessCapable()
{
  NTSTATUS result; // eax
  int v1; // [rsp+30h] [rbp-88h] BYREF
  __int128 v2; // [rsp+38h] [rbp-80h] BYREF
  _BYTE OutputBuffer[80]; // [rsp+50h] [rbp-68h] BYREF

  v1 = 0;
  v2 = 0;
  memset_0(OutputBuffer, 0, 0x4Cu);
  result = NtPowerInformation(SystemPowerCapabilities, 0, 0, OutputBuffer, 0x4Cu);
  if ( result >= 0 )
  {
    v1 = OutputBuffer[10];
    *((_QWORD *)&v2 + 1) = 4;
    *(_QWORD *)&v2 = &v1;
    return EtwEventWrite(UmpoProviderHandle, UMPO_EVT_RUNDOWN_MONITOR_BRIGHTNESS_CAPABLE, 1, &v2);
  }
  return result;
}

```

## disassembly

```asm
0x180008fe8  sub     rsp, 0B8h
0x180008fef  mov     rax, cs:__security_cookie
0x180008ff6  xor     rax, rsp
0x180008ff9  mov     [rsp+0B8h+var_18], rax
0x180009001  xor     edx, edx; Val
0x180009003  mov     [rsp+0B8h+var_88], 0
0x18000900b  xorps   xmm0, xmm0
0x18000900e  lea     rcx, [rsp+0B8h+OutputBuffer]; void *
0x180009013  movups  [rsp+0B8h+var_80], xmm0
0x180009018  lea     r8d, [rdx+4Ch]; Size
0x18000901c  call    memset_0
0x180009021  xor     edx, edx; InputBuffer
0x180009023  mov     [rsp+0B8h+OutputBufferLength], 4Ch ; 'L'; OutputBufferLength
0x18000902b  lea     r9, [rsp+0B8h+OutputBuffer]; OutputBuffer
0x180009030  xor     r8d, r8d; InputBufferLength
0x180009033  lea     ecx, [rdx+4]; PowerInformationLevel
0x180009036  call    cs:__imp_NtPowerInformation
0x18000903c  test    eax, eax
0x18000903e  jns     short loc_180009058
0x180009040  mov     rcx, [rsp+0B8h+var_18]
0x180009048  xor     rcx, rsp; StackCookie
0x18000904b  call    __security_check_cookie
0x180009050  add     rsp, 0B8h
0x180009057  retn
0x180009058  movzx   eax, [rsp+0B8h+var_5E]
0x18000905d  lea     r9, [rsp+0B8h+var_80]
0x180009062  mov     rcx, cs:UmpoProviderHandle
0x180009069  lea     rdx, UMPO_EVT_RUNDOWN_MONITOR_BRIGHTNESS_CAPABLE
0x180009070  mov     [rsp+0B8h+var_88], eax
0x180009074  mov     r8d, 1
0x18000907a  lea     rax, [rsp+0B8h+var_88]
0x18000907f  mov     qword ptr [rsp+0B8h+var_80+8], 4
0x180009088  mov     qword ptr [rsp+0B8h+var_80], rax
0x18000908d  call    cs:__imp_EtwEventWrite
0x180009093  jmp     short loc_180009040
```
