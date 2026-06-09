# IPxlatInitialize

- ea: `0x140035cac`
- end: `0x140035dbb`
- name: `IPxlatInitialize`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140035078`

## callees

- `0x14000caa0`
- `0x140016368`
- `0x14002d008`
- `0x14002d4e8`
- `0x140035cac`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140035cdc`
- `ntoskrnl!KeInitializeSpinLock` at `0x140035cdc`
- `ntoskrnl!ExDeleteResourceLite` at `0x140035d79`
- `ntoskrnl!ExDeleteResourceLite` at `0x140035d79`
- `ntoskrnl!ExInitializeResourceLite` at `0x140035cef`
- `ntoskrnl!ExInitializeResourceLite` at `0x140035cef`
- `fwpkclnt!FwpmBfeStateSubscribeChanges0` at `0x140035d3e`
- `fwpkclnt!FwpmBfeStateSubscribeChanges0` at `0x140035d3e`

## pseudocode

```c
__int64 __fastcall IPxlatInitialize(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  NTSTATUS v6; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  char v12; // [rsp+20h] [rbp-18h]

  if ( IPxlatGlobalState )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
  qword_1400268E8 = (__int64)&qword_1400268E0;
  qword_1400268E0 = &qword_1400268E0;
  KeInitializeSpinLock(&qword_140026958);
  v6 = ExInitializeResourceLite(&stru_1400268F0);
  if ( v6 >= 0 )
  {
    v9 = IPxlatConfigureCallouts(1);
    v5 = 0x80000000LL;
    v6 = v9;
    v4 = 3221225635LL;
    if ( (int)(v9 + 0x80000000) < 0 || v9 == -1073741661 )
    {
      if ( v9 != -1073741661 )
      {
        IPxlatGlobalState = 1;
LABEL_12:
        if ( v6 >= 0 )
          goto LABEL_14;
        goto LABEL_13;
      }
      v10 = FwpmBfeStateSubscribeChanges0(deviceObject, IPxlatBfeStateChangeCallback, 0, &changeHandle);
      v6 = v10;
      if ( v10 < 0 && (xmmword_1400262D0 & 2) != 0 )
        WPP_SF_d(513, 11, WPP_24083f43286932c6336729c882afb6f6_Traceguids, (unsigned int)v10);
    }
    ExDeleteResourceLite(&stru_1400268F0);
    goto LABEL_12;
  }
LABEL_13:
  MicrosoftTelemetryAssertTriggeredNoArgsKM(v5, v4, v7, v8);
LABEL_14:
  if ( (xmmword_1400262E0 & 2) != 0 )
  {
    v12 = IPxlatGlobalState;
    WPP_SF_dc(v5, v4, v7, (unsigned int)v6, v12);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140035cac  push    rbx
0x140035cae  sub     rsp, 30h
0x140035cb2  cmp     cs:IPxlatGlobalState, 0
0x140035cb9  jz      short loc_140035CC0
0x140035cbb  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140035cc0  lea     rax, qword_1400268E0
0x140035cc7  lea     rcx, qword_140026958; SpinLock
0x140035cce  mov     cs:qword_1400268E8, rax
0x140035cd5  mov     cs:qword_1400268E0, rax
0x140035cdc  call    cs:__imp_KeInitializeSpinLock
0x140035ce3  nop     dword ptr [rax+rax+00h]
0x140035ce8  lea     rcx, stru_1400268F0; Resource
0x140035cef  call    cs:__imp_ExInitializeResourceLite
0x140035cf6  nop     dword ptr [rax+rax+00h]
0x140035cfb  mov     ebx, eax
0x140035cfd  test    eax, eax
0x140035cff  js      loc_140035D92
0x140035d05  mov     cl, 1
0x140035d07  call    IPxlatConfigureCallouts
0x140035d0c  mov     ecx, 80000000h
0x140035d11  mov     ebx, eax
0x140035d13  add     eax, ecx
0x140035d15  mov     edx, 0C00000A3h
0x140035d1a  test    ecx, eax
0x140035d1c  jnz     short loc_140035D22
0x140035d1e  cmp     ebx, edx
0x140035d20  jnz     short loc_140035D72
0x140035d22  cmp     ebx, edx
0x140035d24  jnz     short loc_140035D87
0x140035d26  mov     rcx, cs:deviceObject; deviceObject
0x140035d2d  lea     r9, changeHandle; changeHandle
0x140035d34  xor     r8d, r8d; context
0x140035d37  lea     rdx, IPxlatBfeStateChangeCallback; callback
0x140035d3e  call    cs:__imp_FwpmBfeStateSubscribeChanges0
0x140035d45  nop     dword ptr [rax+rax+00h]
0x140035d4a  mov     ebx, eax
0x140035d4c  test    eax, eax
0x140035d4e  jns     short loc_140035D72
0x140035d50  test    byte ptr cs:xmmword_1400262D0, 2
0x140035d57  jz      short loc_140035D72
0x140035d59  mov     edx, 0Bh
0x140035d5e  lea     r8, WPP_24083f43286932c6336729c882afb6f6_Traceguids
0x140035d65  mov     ecx, 201h
0x140035d6a  mov     r9d, eax
0x140035d6d  call    WPP_SF_d
0x140035d72  lea     rcx, stru_1400268F0; Resource
0x140035d79  call    cs:__imp_ExDeleteResourceLite
0x140035d80  nop     dword ptr [rax+rax+00h]
0x140035d85  jmp     short loc_140035D8E
0x140035d87  mov     cs:IPxlatGlobalState, 1
0x140035d8e  test    ebx, ebx
0x140035d90  jns     short loc_140035D97
0x140035d92  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140035d97  test    byte ptr cs:xmmword_1400262E0, 2
0x140035d9e  jz      short loc_140035DB2
0x140035da0  mov     al, cs:IPxlatGlobalState
0x140035da6  mov     r9d, ebx
0x140035da9  mov     [rsp+38h+var_18], al
0x140035dad  call    WPP_SF_dc
0x140035db2  mov     eax, ebx
0x140035db4  add     rsp, 30h
0x140035db8  pop     rbx
0x140035db9  retn
```
