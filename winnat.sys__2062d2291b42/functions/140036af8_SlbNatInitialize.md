# SlbNatInitialize

- ea: `0x140036af8`
- end: `0x140036ca3`
- name: `SlbNatInitialize`
- size: `427`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140036078`

## callees

- `0x14000caa0`
- `0x140014224`
- `0x140018df8`
- `0x140018e4c`
- `0x1400343cc`
- `0x1400344fc`
- `0x140036af8`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x140036b96`
- `ntoskrnl!IoAllocateWorkItem` at `0x140036c4d`
- `ntoskrnl!IoAllocateWorkItem` at `0x140036b96`
- `ntoskrnl!IoAllocateWorkItem` at `0x140036c4d`
- `ntoskrnl!ExDeleteResourceLite` at `0x140036be8`
- `ntoskrnl!ExDeleteResourceLite` at `0x140036be8`
- `ntoskrnl!KeInitializeSpinLock` at `0x140036c89`
- `ntoskrnl!KeInitializeSpinLock` at `0x140036c89`
- `ntoskrnl!ExInitializeResourceLite` at `0x140036b7a`
- `ntoskrnl!ExInitializeResourceLite` at `0x140036b7a`
- `ntoskrnl!IoFreeWorkItem` at `0x140036bd0`
- `ntoskrnl!IoFreeWorkItem` at `0x140036bd0`

## pseudocode

```c
__int64 __fastcall SlbNatInitialize(__int64 a1, __int64 a2, __int64 a3)
{
  char v3; // di
  char v4; // si
  NTSTATUS inited; // ebx
  __int64 result; // rax

  v3 = 0;
  v4 = 0;
  if ( SlbNatGlobalState )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  if ( IoWorkItem )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  if ( qword_1400273D8 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  qword_140027340 = (__int64)&qword_140027338;
  qword_140027338 = &qword_140027338;
  qword_140027360 = (__int64)&qword_140027358;
  qword_140027358 = &qword_140027358;
  inited = SlbNatIpsInitializeDataPathState();
  if ( inited >= 0 )
  {
    v3 = 1;
    inited = ExInitializeResourceLite(&Resource);
    if ( inited >= 0 )
    {
      v4 = 1;
      IoWorkItem = IoAllocateWorkItem(deviceObject);
      if ( IoWorkItem
        && (qword_1400273D8 = (PVOID)WinNatLibInitializeState(0, (unsigned int)dword_140027B60, qword_140027B68)) != 0
        && (xmmword_1400273E0 = 0, dword_140027334 = 1, (qword_1400274C8 = IoAllocateWorkItem(deviceObject)) != 0) )
      {
        dword_1400274D0 = 0;
        inited = InitWsk();
        if ( inited >= 0 )
        {
          KeInitializeSpinLock(&qword_1400274D8);
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
  if ( qword_1400273D8 )
    WinNatLibCleanupState(qword_1400273D8);
  if ( IoWorkItem )
    IoFreeWorkItem(IoWorkItem);
  if ( v4 )
    ExDeleteResourceLite(&Resource);
  if ( v3 )
    SlbNatIpsCleanupDataPathState();
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140036af8  mov     [rsp+arg_0], rbx
0x140036afd  mov     [rsp+arg_8], rsi
0x140036b02  push    rdi
0x140036b03  sub     rsp, 20h
0x140036b07  xor     dil, dil
0x140036b0a  xor     sil, sil
0x140036b0d  cmp     cs:SlbNatGlobalState, sil
0x140036b14  jz      short loc_140036B1B
0x140036b16  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140036b1b  cmp     cs:IoWorkItem, 0
0x140036b23  jz      short loc_140036B2A
0x140036b25  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140036b2a  cmp     cs:qword_1400273D8, 0
0x140036b32  jz      short loc_140036B39
0x140036b34  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140036b39  lea     rax, qword_140027338
0x140036b40  mov     cs:qword_140027340, rax
0x140036b47  mov     cs:qword_140027338, rax
0x140036b4e  lea     rax, qword_140027358
0x140036b55  mov     cs:qword_140027360, rax
0x140036b5c  mov     cs:qword_140027358, rax
0x140036b63  call    SlbNatIpsInitializeDataPathState
0x140036b68  mov     ebx, eax
0x140036b6a  test    eax, eax
0x140036b6c  js      short loc_140036BB3
0x140036b6e  lea     rcx, Resource; Resource
0x140036b75  mov     edi, 1
0x140036b7a  call    cs:__imp_ExInitializeResourceLite
0x140036b81  nop     dword ptr [rax+rax+00h]
0x140036b86  mov     ebx, eax
0x140036b88  test    eax, eax
0x140036b8a  js      short loc_140036BB3
0x140036b8c  mov     rcx, cs:deviceObject; DeviceObject
0x140036b93  mov     sil, dil
0x140036b96  call    cs:__imp_IoAllocateWorkItem
0x140036b9d  nop     dword ptr [rax+rax+00h]
0x140036ba2  mov     cs:IoWorkItem, rax
0x140036ba9  test    rax, rax
0x140036bac  jnz     short loc_140036C11
0x140036bae  mov     ebx, 0C000009Ah
0x140036bb3  mov     rcx, cs:qword_1400273D8; P
0x140036bba  test    rcx, rcx
0x140036bbd  jz      short loc_140036BC4
0x140036bbf  call    WinNatLibCleanupState
0x140036bc4  mov     rcx, cs:IoWorkItem; IoWorkItem
0x140036bcb  test    rcx, rcx
0x140036bce  jz      short loc_140036BDC
0x140036bd0  call    cs:__imp_IoFreeWorkItem
0x140036bd7  nop     dword ptr [rax+rax+00h]
0x140036bdc  test    sil, sil
0x140036bdf  jz      short loc_140036BF4
0x140036be1  lea     rcx, Resource; Resource
0x140036be8  call    cs:__imp_ExDeleteResourceLite
0x140036bef  nop     dword ptr [rax+rax+00h]
0x140036bf4  test    dil, dil
0x140036bf7  jz      short loc_140036BFE
0x140036bf9  call    SlbNatIpsCleanupDataPathState
0x140036bfe  mov     eax, ebx
0x140036c00  mov     rbx, [rsp+28h+arg_0]
0x140036c05  mov     rsi, [rsp+28h+arg_8]
0x140036c0a  add     rsp, 20h
0x140036c0e  pop     rdi
0x140036c0f  retn
0x140036c11  mov     r8, cs:qword_140027B68
0x140036c18  xor     ecx, ecx
0x140036c1a  mov     edx, cs:dword_140027B60
0x140036c20  call    WinNatLibInitializeState
0x140036c25  mov     cs:qword_1400273D8, rax
0x140036c2c  test    rax, rax
0x140036c2f  jz      loc_140036BAE
0x140036c35  mov     rcx, cs:deviceObject; DeviceObject
0x140036c3c  xorps   xmm0, xmm0
0x140036c3f  movdqa  cs:xmmword_1400273E0, xmm0
0x140036c47  mov     cs:dword_140027334, edi
0x140036c4d  call    cs:__imp_IoAllocateWorkItem
0x140036c54  nop     dword ptr [rax+rax+00h]
0x140036c59  mov     cs:qword_1400274C8, rax
0x140036c60  test    rax, rax
0x140036c63  jz      loc_140036BAE
0x140036c69  mov     cs:dword_1400274D0, 0
0x140036c73  call    InitWsk
0x140036c78  mov     ebx, eax
0x140036c7a  test    eax, eax
0x140036c7c  js      loc_140036BB3
0x140036c82  lea     rcx, qword_1400274D8; SpinLock
0x140036c89  call    cs:__imp_KeInitializeSpinLock
0x140036c90  nop     dword ptr [rax+rax+00h]
0x140036c95  xor     eax, eax
0x140036c97  mov     cs:SlbNatGlobalState, dil
0x140036c9e  jmp     loc_140036C00
```
