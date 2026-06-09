# UmpoRundownPowerSource

- ea: `0x180008dd0`
- end: `0x180008e62`
- name: `UmpoRundownPowerSource`
- size: `146`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008c80`

## callees

- `0x180008dd0`
- `0x180010070`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180008e4a`
- `ntdll!EtwEventWrite` at `0x180008e4a`
- `ntdll!NtPowerInformation` at `0x180008e11`
- `ntdll!NtPowerInformation` at `0x180008e11`

## pseudocode

```c
NTSTATUS UmpoRundownPowerSource()
{
  NTSTATUS result; // eax
  int v1; // [rsp+30h] [rbp-40h] BYREF
  __int128 v2; // [rsp+38h] [rbp-38h] BYREF
  _OWORD OutputBuffer[2]; // [rsp+48h] [rbp-28h] BYREF

  v1 = 0;
  memset(OutputBuffer, 0, sizeof(OutputBuffer));
  v2 = 0;
  result = NtPowerInformation(SystemBatteryState, 0, 0, OutputBuffer, 0x20u);
  if ( result >= 0 )
  {
    v1 = LOBYTE(OutputBuffer[0]);
    *((_QWORD *)&v2 + 1) = 4;
    *(_QWORD *)&v2 = &v1;
    return EtwEventWrite(UmpoProviderHandle, UMPO_EVT_RUNDOWN_POWER_SOURCE, 1, &v2);
  }
  return result;
}

```

## disassembly

```asm
0x180008dd0  push    rbp
0x180008dd2  mov     rbp, rsp
0x180008dd5  sub     rsp, 70h
0x180008dd9  mov     rax, cs:__security_cookie
0x180008de0  xor     rax, rsp
0x180008de3  mov     [rbp+var_8], rax
0x180008de7  xorps   xmm0, xmm0
0x180008dea  mov     [rbp+var_40], 0
0x180008df1  xor     edx, edx; InputBuffer
0x180008df3  mov     [rsp+70h+OutputBufferLength], 20h ; ' '; OutputBufferLength
0x180008dfb  lea     r9, [rbp+OutputBuffer]; OutputBuffer
0x180008dff  xor     r8d, r8d; InputBufferLength
0x180008e02  movups  [rbp+OutputBuffer], xmm0
0x180008e06  lea     ecx, [rdx+5]; PowerInformationLevel
0x180008e09  movups  [rbp+var_18], xmm0
0x180008e0d  movups  [rbp+var_38], xmm0
0x180008e11  call    cs:__imp_NtPowerInformation
0x180008e17  test    eax, eax
0x180008e19  js      short loc_180008E50
0x180008e1b  movzx   eax, byte ptr [rbp+OutputBuffer]
0x180008e1f  lea     r9, [rbp+var_38]
0x180008e23  mov     rcx, cs:UmpoProviderHandle
0x180008e2a  lea     rdx, UMPO_EVT_RUNDOWN_POWER_SOURCE
0x180008e31  mov     [rbp+var_40], eax
0x180008e34  mov     r8d, 1
0x180008e3a  lea     rax, [rbp+var_40]
0x180008e3e  mov     qword ptr [rbp+var_38+8], 4
0x180008e46  mov     qword ptr [rbp+var_38], rax
0x180008e4a  call    cs:__imp_EtwEventWrite
0x180008e50  mov     rcx, [rbp+var_8]
0x180008e54  xor     rcx, rsp; StackCookie
0x180008e57  call    __security_check_cookie
0x180008e5c  add     rsp, 70h
0x180008e60  pop     rbp
0x180008e61  retn
```
