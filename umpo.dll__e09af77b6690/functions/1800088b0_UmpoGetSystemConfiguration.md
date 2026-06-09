# UmpoGetSystemConfiguration

- ea: `0x1800088b0`
- end: `0x180008972`
- name: `UmpoGetSystemConfiguration`
- size: `194`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008be0`
- `0x18000a574`
- `0x180014a90`

## callees

- `0x180007ee8`
- `0x1800088b0`
- `0x180008978`
- `0x18000f3dc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000895a`
- `ntdll!RtlNtStatusToDosError` at `0x18000895a`
- `ntdll!NtPowerInformation` at `0x1800088e8`
- `ntdll!NtPowerInformation` at `0x1800088e8`

## pseudocode

```c
__int64 __fastcall UmpoGetSystemConfiguration(int *a1)
{
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  unsigned int ProcessorType; // ebx
  int v6; // edi
  int v7; // ebp
  int v8; // esi
  char IsServerSku; // al
  int v10; // ecx
  int v12; // [rsp+68h] [rbp+10h] BYREF
  int v13; // [rsp+70h] [rbp+18h] BYREF
  int v14; // [rsp+78h] [rbp+20h] BYREF

  v12 = 0;
  v13 = 0;
  v14 = 0;
  v2 = NtPowerInformation(ProcessorInformation|0x40, 0, 0, &v14, 4u);
  if ( v2 < 0 )
  {
    return RtlNtStatusToDosError(v2);
  }
  else
  {
    ProcessorType = UmpoGetProcessorType(&v13, &v12);
    if ( !ProcessorType )
    {
      v6 = v12;
      v7 = 0;
      if ( v12 == 16 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v4, v3);
      v8 = v13;
      if ( v13 == 5 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v4, v3);
      if ( UmpoAoAc )
        v7 = 1;
      IsServerSku = UmpoIsServerSku();
      a1[2] = v6;
      v10 = v7 | 2;
      a1[3] = v8;
      a1[1] = v14;
      if ( !IsServerSku )
        v10 = v7;
      *a1 = v10;
    }
  }
  return ProcessorType;
}

```

## disassembly

```asm
0x1800088b0  mov     rax, rsp
0x1800088b3  push    rbx
0x1800088b4  push    rbp
0x1800088b5  push    rsi
0x1800088b6  push    rdi
0x1800088b7  push    r14
0x1800088b9  sub     rsp, 30h
0x1800088bd  xor     edx, edx; InputBuffer
0x1800088bf  mov     dword ptr [rax+10h], 0
0x1800088c6  mov     r14, rcx
0x1800088c9  mov     dword ptr [rax+18h], 0
0x1800088d0  lea     r9, [rax+20h]; OutputBuffer
0x1800088d4  mov     dword ptr [rax+20h], 0
0x1800088db  xor     r8d, r8d; InputBufferLength
0x1800088de  mov     dword ptr [rax-38h], 4
0x1800088e5  lea     ecx, [rdx+4Bh]; PowerInformationLevel
0x1800088e8  call    cs:__imp_NtPowerInformation
0x1800088ee  test    eax, eax
0x1800088f0  js      short loc_180008958
0x1800088f2  lea     rdx, [rsp+58h+arg_8]
0x1800088f7  lea     rcx, [rsp+58h+arg_10]
0x1800088fc  call    UmpoGetProcessorType
0x180008901  mov     ebx, eax
0x180008903  test    eax, eax
0x180008905  jnz     short loc_18000894B
0x180008907  mov     edi, [rsp+58h+arg_8]
0x18000890b  xor     ebp, ebp
0x18000890d  cmp     edi, 10h
0x180008910  jz      short loc_180008964
0x180008912  mov     esi, [rsp+58h+arg_10]
0x180008916  cmp     esi, 5
0x180008919  jz      short loc_18000896B
0x18000891b  cmp     cs:UmpoAoAc, ebp
0x180008921  mov     eax, 1
0x180008926  cmovnz  ebp, eax
0x180008929  call    UmpoIsServerSku
0x18000892e  mov     ecx, ebp
0x180008930  mov     [r14+8], edi
0x180008934  or      ecx, 2
0x180008937  mov     [r14+0Ch], esi
0x18000893b  test    al, al
0x18000893d  mov     eax, [rsp+58h+arg_18]
0x180008941  mov     [r14+4], eax
0x180008945  cmovz   ecx, ebp
0x180008948  mov     [r14], ecx
0x18000894b  mov     eax, ebx
0x18000894d  add     rsp, 30h
0x180008951  pop     r14
0x180008953  pop     rdi
0x180008954  pop     rsi
0x180008955  pop     rbp
0x180008956  pop     rbx
0x180008957  retn
0x180008958  mov     ecx, eax; Status
0x18000895a  call    cs:__imp_RtlNtStatusToDosError
0x180008960  mov     ebx, eax
0x180008962  jmp     short loc_18000894B
0x180008964  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008969  jmp     short loc_180008912
0x18000896b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008970  jmp     short loc_18000891B
```
