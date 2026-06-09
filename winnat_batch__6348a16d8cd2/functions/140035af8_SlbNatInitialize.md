# SlbNatInitialize

- ea: `0x140035af8`
- end: `0x140035ca3`
- name: `SlbNatInitialize`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140035078`

## callees

- `0x14000caa0`
- `0x1400138e4`
- `0x140018918`
- `0x14001896c`
- `0x14003329c`
- `0x1400333cc`
- `0x140035af8`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x140035b96`
- `ntoskrnl!IoAllocateWorkItem` at `0x140035c4d`
- `ntoskrnl!IoAllocateWorkItem` at `0x140035b96`
- `ntoskrnl!IoAllocateWorkItem` at `0x140035c4d`
- `ntoskrnl!IoFreeWorkItem` at `0x140035bd0`
- `ntoskrnl!IoFreeWorkItem` at `0x140035bd0`
- `ntoskrnl!KeInitializeSpinLock` at `0x140035c89`
- `ntoskrnl!KeInitializeSpinLock` at `0x140035c89`
- `ntoskrnl!ExDeleteResourceLite` at `0x140035be8`
- `ntoskrnl!ExDeleteResourceLite` at `0x140035be8`
- `ntoskrnl!ExInitializeResourceLite` at `0x140035b7a`
- `ntoskrnl!ExInitializeResourceLite` at `0x140035b7a`

## pseudocode

```c
__int64 __fastcall SlbNatInitialize(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char v4; // di
  char v5; // si
  NTSTATUS inited; // ebx
  __int64 result; // rax

  v4 = 0;
  v5 = 0;
  if ( SlbNatGlobalState )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
  if ( IoWorkItem )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
  if ( qword_1400263D8 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
  qword_140026340 = (__int64)&qword_140026338;
  qword_140026338 = &qword_140026338;
  qword_140026360 = (__int64)&qword_140026358;
  qword_140026358 = &qword_140026358;
  inited = SlbNatIpsInitializeDataPathState();
  if ( inited >= 0 )
  {
    v4 = 1;
    inited = ExInitializeResourceLite(&Resource);
    if ( inited >= 0 )
    {
      v5 = 1;
      IoWorkItem = IoAllocateWorkItem(deviceObject);
      if ( IoWorkItem
        && (qword_1400263D8 = (PVOID)WinNatLibInitializeState(0, (unsigned int)dword_140026B60, qword_140026B68)) != 0
        && (xmmword_1400263E0 = 0, dword_140026334 = 1, (qword_1400264C8 = IoAllocateWorkItem(deviceObject)) != 0) )
      {
        dword_1400264D0 = 0;
        inited = InitWsk();
        if ( inited >= 0 )
        {
          KeInitializeSpinLock(&qword_1400264D8);
          result = 0;
          SlbNatGlobalState = 1;
          return result;
        }
      }
      else
      {
        inited = -1073741670;
      }
    }
  }
  if ( qword_1400263D8 )
    WinNatLibCleanupState(qword_1400263D8);
  if ( IoWorkItem )
    IoFreeWorkItem(IoWorkItem);
  if ( v5 )
    ExDeleteResourceLite(&Resource);
  if ( v4 )
    SlbNatIpsCleanupDataPathState();
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140035af8  mov     [rsp+arg_0], rbx
0x140035afd  mov     [rsp+arg_8], rsi
0x140035b02  push    rdi
0x140035b03  sub     rsp, 20h
0x140035b07  xor     dil, dil
0x140035b0a  xor     sil, sil
0x140035b0d  cmp     cs:SlbNatGlobalState, sil
0x140035b14  jz      short loc_140035B1B
0x140035b16  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140035b1b  cmp     cs:IoWorkItem, 0
0x140035b23  jz      short loc_140035B2A
0x140035b25  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140035b2a  cmp     cs:qword_1400263D8, 0
0x140035b32  jz      short loc_140035B39
0x140035b34  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140035b39  lea     rax, qword_140026338
0x140035b40  mov     cs:qword_140026340, rax
0x140035b47  mov     cs:qword_140026338, rax
0x140035b4e  lea     rax, qword_140026358
0x140035b55  mov     cs:qword_140026360, rax
0x140035b5c  mov     cs:qword_140026358, rax
0x140035b63  call    SlbNatIpsInitializeDataPathState
0x140035b68  mov     ebx, eax
0x140035b6a  test    eax, eax
0x140035b6c  js      short loc_140035BB3
0x140035b6e  lea     rcx, Resource; Resource
0x140035b75  mov     edi, 1
0x140035b7a  call    cs:__imp_ExInitializeResourceLite
0x140035b81  nop     dword ptr [rax+rax+00h]
0x140035b86  mov     ebx, eax
0x140035b88  test    eax, eax
0x140035b8a  js      short loc_140035BB3
0x140035b8c  mov     rcx, cs:deviceObject; DeviceObject
0x140035b93  mov     sil, dil
0x140035b96  call    cs:__imp_IoAllocateWorkItem
0x140035b9d  nop     dword ptr [rax+rax+00h]
0x140035ba2  mov     cs:IoWorkItem, rax
0x140035ba9  test    rax, rax
0x140035bac  jnz     short loc_140035C11
0x140035bae  mov     ebx, 0C000009Ah
0x140035bb3  mov     rcx, cs:qword_1400263D8; P
0x140035bba  test    rcx, rcx
0x140035bbd  jz      short loc_140035BC4
0x140035bbf  call    WinNatLibCleanupState
0x140035bc4  mov     rcx, cs:IoWorkItem; IoWorkItem
0x140035bcb  test    rcx, rcx
0x140035bce  jz      short loc_140035BDC
0x140035bd0  call    cs:__imp_IoFreeWorkItem
0x140035bd7  nop     dword ptr [rax+rax+00h]
0x140035bdc  test    sil, sil
0x140035bdf  jz      short loc_140035BF4
0x140035be1  lea     rcx, Resource; Resource
0x140035be8  call    cs:__imp_ExDeleteResourceLite
0x140035bef  nop     dword ptr [rax+rax+00h]
0x140035bf4  test    dil, dil
0x140035bf7  jz      short loc_140035BFE
0x140035bf9  call    SlbNatIpsCleanupDataPathState
0x140035bfe  mov     eax, ebx
0x140035c00  mov     rbx, [rsp+28h+arg_0]
0x140035c05  mov     rsi, [rsp+28h+arg_8]
0x140035c0a  add     rsp, 20h
0x140035c0e  pop     rdi
0x140035c0f  retn
0x140035c11  mov     r8, cs:qword_140026B68
0x140035c18  xor     ecx, ecx
0x140035c1a  mov     edx, cs:dword_140026B60
0x140035c20  call    WinNatLibInitializeState
0x140035c25  mov     cs:qword_1400263D8, rax
0x140035c2c  test    rax, rax
0x140035c2f  jz      loc_140035BAE
0x140035c35  mov     rcx, cs:deviceObject; DeviceObject
0x140035c3c  xorps   xmm0, xmm0
0x140035c3f  movdqa  cs:xmmword_1400263E0, xmm0
0x140035c47  mov     cs:dword_140026334, edi
0x140035c4d  call    cs:__imp_IoAllocateWorkItem
0x140035c54  nop     dword ptr [rax+rax+00h]
0x140035c59  mov     cs:qword_1400264C8, rax
0x140035c60  test    rax, rax
0x140035c63  jz      loc_140035BAE
0x140035c69  mov     cs:dword_1400264D0, 0
0x140035c73  call    InitWsk
0x140035c78  mov     ebx, eax
0x140035c7a  test    eax, eax
0x140035c7c  js      loc_140035BB3
0x140035c82  lea     rcx, qword_1400264D8; SpinLock
0x140035c89  call    cs:__imp_KeInitializeSpinLock
0x140035c90  nop     dword ptr [rax+rax+00h]
0x140035c95  xor     eax, eax
0x140035c97  mov     cs:SlbNatGlobalState, dil
0x140035c9e  jmp     loc_140035C00
```
