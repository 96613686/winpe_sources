# IPxlatInitialize

- ea: `0x140036cac`
- end: `0x140036dbb`
- name: `IPxlatInitialize`
- size: `271`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140036078`

## callees

- `0x14000caa0`
- `0x140017034`
- `0x14002e008`
- `0x14002e4e8`
- `0x140036cac`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140036d79`
- `ntoskrnl!ExDeleteResourceLite` at `0x140036d79`
- `ntoskrnl!KeInitializeSpinLock` at `0x140036cdc`
- `ntoskrnl!KeInitializeSpinLock` at `0x140036cdc`
- `ntoskrnl!ExInitializeResourceLite` at `0x140036cef`
- `ntoskrnl!ExInitializeResourceLite` at `0x140036cef`
- `fwpkclnt!FwpmBfeStateSubscribeChanges0` at `0x140036d3e`
- `fwpkclnt!FwpmBfeStateSubscribeChanges0` at `0x140036d3e`

## pseudocode

```c
__int64 __fastcall IPxlatInitialize(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  NTSTATUS v5; // ebx
  __int64 v6; // r8
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  char v10; // [rsp+20h] [rbp-18h]

  if ( IPxlatGlobalState )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  qword_1400278E8 = (__int64)&qword_1400278E0;
  qword_1400278E0 = &qword_1400278E0;
  KeInitializeSpinLock(&qword_140027958);
  v5 = ExInitializeResourceLite(&stru_1400278F0);
  if ( v5 >= 0 )
  {
    v7 = IPxlatConfigureCallouts(1);
    v4 = 0x80000000LL;
    v5 = v7;
    v3 = 3221225635LL;
    if ( (int)(v7 + 0x80000000) < 0 || v7 == -1073741661 )
    {
      if ( v7 != -1073741661 )
      {
        IPxlatGlobalState = 1;
LABEL_12:
        if ( v5 >= 0 )
          goto LABEL_14;
        goto LABEL_13;
      }
      v8 = FwpmBfeStateSubscribeChanges0(deviceObject, IPxlatBfeStateChangeCallback, 0, &changeHandle);
      v5 = v8;
      if ( v8 < 0 && (xmmword_1400272D0 & 2) != 0 )
        WPP_SF_d(513, 11, WPP_00475dad78ff34078f24129d9bdcf001_Traceguids, (unsigned int)v8);
    }
    ExDeleteResourceLite(&stru_1400278F0);
    goto LABEL_12;
  }
LABEL_13:
  MicrosoftTelemetryAssertTriggeredNoArgsKM(v4, v3, v6);
LABEL_14:
  if ( (xmmword_1400272E0 & 2) != 0 )
  {
    v10 = IPxlatGlobalState;
    WPP_SF_dc(v4, v3, v6, (unsigned int)v5, v10);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140036cac  push    rbx
0x140036cae  sub     rsp, 30h
0x140036cb2  cmp     cs:IPxlatGlobalState, 0
0x140036cb9  jz      short loc_140036CC0
0x140036cbb  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140036cc0  lea     rax, qword_1400278E0
0x140036cc7  lea     rcx, qword_140027958; SpinLock
0x140036cce  mov     cs:qword_1400278E8, rax
0x140036cd5  mov     cs:qword_1400278E0, rax
0x140036cdc  call    cs:__imp_KeInitializeSpinLock
0x140036ce3  nop     dword ptr [rax+rax+00h]
0x140036ce8  lea     rcx, stru_1400278F0; Resource
0x140036cef  call    cs:__imp_ExInitializeResourceLite
0x140036cf6  nop     dword ptr [rax+rax+00h]
0x140036cfb  mov     ebx, eax
0x140036cfd  test    eax, eax
0x140036cff  js      loc_140036D92
0x140036d05  mov     cl, 1
0x140036d07  call    IPxlatConfigureCallouts
0x140036d0c  mov     ecx, 80000000h
0x140036d11  mov     ebx, eax
0x140036d13  add     eax, ecx
0x140036d15  mov     edx, 0C00000A3h
0x140036d1a  test    ecx, eax
0x140036d1c  jnz     short loc_140036D22
0x140036d1e  cmp     ebx, edx
0x140036d20  jnz     short loc_140036D72
0x140036d22  cmp     ebx, edx
0x140036d24  jnz     short loc_140036D87
0x140036d26  mov     rcx, cs:deviceObject; deviceObject
0x140036d2d  lea     r9, changeHandle; changeHandle
0x140036d34  xor     r8d, r8d; context
0x140036d37  lea     rdx, IPxlatBfeStateChangeCallback; callback
0x140036d3e  call    cs:__imp_FwpmBfeStateSubscribeChanges0
0x140036d45  nop     dword ptr [rax+rax+00h]
0x140036d4a  mov     ebx, eax
0x140036d4c  test    eax, eax
0x140036d4e  jns     short loc_140036D72
0x140036d50  test    byte ptr cs:xmmword_1400272D0, 2
0x140036d57  jz      short loc_140036D72
0x140036d59  mov     edx, 0Bh
0x140036d5e  lea     r8, WPP_00475dad78ff34078f24129d9bdcf001_Traceguids
0x140036d65  mov     ecx, 201h
0x140036d6a  mov     r9d, eax
0x140036d6d  call    WPP_SF_d
0x140036d72  lea     rcx, stru_1400278F0; Resource
0x140036d79  call    cs:__imp_ExDeleteResourceLite
0x140036d80  nop     dword ptr [rax+rax+00h]
0x140036d85  jmp     short loc_140036D8E
0x140036d87  mov     cs:IPxlatGlobalState, 1
0x140036d8e  test    ebx, ebx
0x140036d90  jns     short loc_140036D97
0x140036d92  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140036d97  test    byte ptr cs:xmmword_1400272E0, 2
0x140036d9e  jz      short loc_140036DB2
0x140036da0  mov     al, cs:IPxlatGlobalState
0x140036da6  mov     r9d, ebx
0x140036da9  mov     [rsp+38h+var_18], al
0x140036dad  call    WPP_SF_dc
0x140036db2  mov     eax, ebx
0x140036db4  add     rsp, 30h
0x140036db8  pop     rbx
0x140036db9  retn
```
