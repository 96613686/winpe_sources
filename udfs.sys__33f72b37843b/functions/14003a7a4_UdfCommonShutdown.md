# UdfCommonShutdown

- ea: `0x14003a7a4`
- end: `0x14003aa3b`
- name: `UdfCommonShutdown`
- size: `663`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400077f0`
- `0x1400094c0`

## callees

- `0x1400030e0`
- `0x140008594`
- `0x14000b128`
- `0x14003a7a4`
- `0x14004ce50`
- `0x140052864`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14003a9a2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003a9ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c2be`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003a9a2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003a9ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c2be`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003a815`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003a815`
- `ntoskrnl!IofCallDriver` at `0x14003a942`
- `ntoskrnl!IofCallDriver` at `0x14003a942`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003a96b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003a96b`
- `ntoskrnl!KeClearEvent` at `0x14003a97c`
- `ntoskrnl!KeClearEvent` at `0x14003a97c`
- `ntoskrnl!IoDeleteDevice` at `0x14003a9f3`
- `ntoskrnl!IoDeleteDevice` at `0x14003aa06`
- `ntoskrnl!IoDeleteDevice` at `0x14005c2f7`
- `ntoskrnl!IoDeleteDevice` at `0x14005c30a`
- `ntoskrnl!IoDeleteDevice` at `0x14003a9f3`
- `ntoskrnl!IoDeleteDevice` at `0x14003aa06`
- `ntoskrnl!IoDeleteDevice` at `0x14005c2f7`
- `ntoskrnl!IoDeleteDevice` at `0x14005c30a`
- `ntoskrnl!KeInitializeEvent` at `0x14003a7f8`
- `ntoskrnl!KeInitializeEvent` at `0x14003a7f8`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x14003a92a`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x14003a92a`
- `ntoskrnl!IoUnregisterFileSystem` at `0x14003a9cd`
- `ntoskrnl!IoUnregisterFileSystem` at `0x14003a9e0`
- `ntoskrnl!IoUnregisterFileSystem` at `0x14005c2d1`
- `ntoskrnl!IoUnregisterFileSystem` at `0x14005c2e4`
- `ntoskrnl!IoUnregisterFileSystem` at `0x14003a9cd`
- `ntoskrnl!IoUnregisterFileSystem` at `0x14003a9e0`
- `ntoskrnl!IoUnregisterFileSystem` at `0x14005c2d1`
- `ntoskrnl!IoUnregisterFileSystem` at `0x14005c2e4`

## pseudocode

```c
__int64 __fastcall UdfCommonShutdown(__int64 a1, __int64 a2)
{
  _DWORD *v3; // r13
  __int64 *v4; // rdi
  __int64 v5; // rbx
  IRP *v6; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-60h] BYREF
  struct _KEVENT Object; // [rsp+78h] [rbp-50h] BYREF

  memset(&Object, 0, sizeof(Object));
  IoStatusBlock = 0;
  v3 = (_DWORD *)(a1 + 28);
  *(_DWORD *)(a1 + 28) |= 0x200u;
  KeInitializeEvent(&Object, NotificationEvent, 0);
  word_140025B56 |= 1u;
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  v4 = (__int64 *)qword_140025B20;
  while ( v4 != &qword_140025B20 )
  {
    v5 = (__int64)(v4 - 4);
    v4 = (__int64 *)*v4;
    if ( (*(_DWORD *)(v5 + 48) & 0x10000000) == 0 && *(_DWORD *)(v5 + 52) == 2 )
    {
      UdfAcquireResource(a1, v5 + 1480, 0, 0);
      *(_QWORD *)(a1 + 16) = v5;
      UdfFlushVolume(a1, v5, 0, 1, 1, 0);
      *v3 &= ~0x8000u;
      *(_QWORD *)(a1 + 16) = 0;
      v6 = IoBuildSynchronousFsdRequest(0x10u, *(PDEVICE_OBJECT *)(v5 + 24), 0, 0, 0, &Object, &IoStatusBlock);
      if ( v6 )
      {
        if ( IofCallDriver(*(PDEVICE_OBJECT *)(v5 + 24), v6) == 259 )
          KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
        KeClearEvent(&Object);
      }
      *(_DWORD *)(v5 + 48) |= 0x10000000u;
      if ( (unsigned __int8)UdfCheckForDismount(a1, v5, 0) )
        ExReleaseResourceLite((PERESOURCE)(v5 + 1480));
    }
  }
  ExReleaseResourceLite(&Resource);
  IoUnregisterFileSystem(DeviceObject);
  IoUnregisterFileSystem(qword_140025B10);
  IoDeleteDevice(DeviceObject);
  IoDeleteDevice(qword_140025B10);
  UdfCompleteRequest(a1, a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14003a7a4  mov     r11, rsp
0x14003a7a7  mov     [r11+10h], rdx
0x14003a7ab  mov     [r11+8], rcx
0x14003a7af  push    rbx
0x14003a7b0  push    rsi
0x14003a7b1  push    rdi
0x14003a7b2  push    r12
0x14003a7b4  push    r13
0x14003a7b6  push    r14
0x14003a7b8  push    r15
0x14003a7ba  sub     rsp, 90h
0x14003a7c1  mov     rsi, rcx
0x14003a7c4  xorps   xmm0, xmm0
0x14003a7c7  xor     eax, eax
0x14003a7c9  movups  xmmword ptr [rsp+0C8h+Object.Header], xmm0
0x14003a7ce  mov     [r11-40h], rax
0x14003a7d2  movups  xmmword ptr [rsp+0C8h+var_60], xmm0
0x14003a7d7  lea     r13, [rcx+1Ch]
0x14003a7db  mov     [rsp+0C8h+arg_10], r13
0x14003a7e3  mov     eax, [r13+0]
0x14003a7e7  bts     eax, 9
0x14003a7eb  mov     [r13+0], eax
0x14003a7ef  xor     r8d, r8d; State
0x14003a7f2  xor     edx, edx; Type
0x14003a7f4  lea     rcx, [r11-50h]; Event
0x14003a7f8  call    cs:__imp_KeInitializeEvent
0x14003a7ff  nop     dword ptr [rax+rax+00h]
0x14003a804  or      cs:word_140025B56, 1
0x14003a80c  mov     dl, 1; Wait
0x14003a80e  lea     rcx, Resource; Resource
0x14003a815  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14003a81c  nop     dword ptr [rax+rax+00h]
0x14003a821  nop
0x14003a822  mov     rdi, cs:qword_140025B20
0x14003a829  mov     [rsp+0C8h+var_88], rdi
0x14003a82e  lea     rax, qword_140025B20
0x14003a835  cmp     rdi, rax
0x14003a838  jz      loc_14003A9B3
0x14003a83e  lea     rbx, [rdi-20h]
0x14003a842  mov     [rsp+0C8h+arg_18], rbx
0x14003a84a  mov     [rsp+0C8h+var_68], rbx
0x14003a84f  mov     rdi, [rdi]
0x14003a852  mov     [rsp+0C8h+var_88], rdi
0x14003a857  lea     r14, [rbx+30h]
0x14003a85b  mov     [rsp+0C8h+var_80], r14
0x14003a860  mov     eax, [r14]
0x14003a863  bt      eax, 1Ch
0x14003a867  jb      loc_14003A9AE
0x14003a86d  cmp     dword ptr [rbx+34h], 2
0x14003a871  jnz     loc_14003A9AE
0x14003a877  lea     r15, [rbx+5C8h]
0x14003a87e  mov     [rsp+0C8h+var_78], r15
0x14003a883  xor     r9d, r9d
0x14003a886  xor     r8d, r8d
0x14003a889  mov     rdx, r15
0x14003a88c  mov     rcx, rsi
0x14003a88f  call    UdfAcquireResource
0x14003a894  lea     r12, [rsi+10h]
0x14003a898  mov     [rsp+0C8h+var_70], r12
0x14003a89d  mov     [r12], rbx
0x14003a8a1  mov     byte ptr [rsp+0C8h+Event], 0; char
0x14003a8a6  mov     byte ptr [rsp+0C8h+StartingOffset], 1; char
0x14003a8ab  mov     r9b, 1
0x14003a8ae  xor     r8d, r8d
0x14003a8b1  mov     rdx, rbx
0x14003a8b4  mov     rcx, rsi; int
0x14003a8b7  call    UdfFlushVolume
0x14003a8bc  jmp     short loc_14003A8F1
0x14003a8be  mov     rsi, [rsp+0C8h+arg_0]
0x14003a8c6  mov     dword ptr [rsi+18h], 0
0x14003a8cd  mov     rdi, [rsp+0C8h+var_88]
0x14003a8d2  mov     r13, [rsp+0C8h+arg_10]
0x14003a8da  mov     rbx, [rsp+0C8h+arg_18]
0x14003a8e2  mov     r14, [rsp+0C8h+var_80]
0x14003a8e7  mov     r15, [rsp+0C8h+var_78]
0x14003a8ec  mov     r12, [rsp+0C8h+var_70]
0x14003a8f1  btr     dword ptr [r13+0], 0Fh
0x14003a8f7  mov     qword ptr [r12], 0
0x14003a8ff  lea     rax, [rsp+0C8h+var_60]
0x14003a904  mov     [rsp+0C8h+IoStatusBlock], rax; IoStatusBlock
0x14003a909  lea     rax, [rsp+0C8h+Object]
0x14003a90e  mov     [rsp+0C8h+Event], rax; Event
0x14003a913  mov     [rsp+0C8h+StartingOffset], 0; StartingOffset
0x14003a91c  xor     r9d, r9d; Length
0x14003a91f  xor     r8d, r8d; Buffer
0x14003a922  mov     rdx, [rbx+18h]; DeviceObject
0x14003a926  lea     ecx, [r9+10h]; MajorFunction
0x14003a92a  call    cs:__imp_IoBuildSynchronousFsdRequest
0x14003a931  nop     dword ptr [rax+rax+00h]
0x14003a936  test    rax, rax
0x14003a939  jz      short loc_14003A988
0x14003a93b  mov     rdx, rax; Irp
0x14003a93e  mov     rcx, [rbx+18h]; DeviceObject
0x14003a942  call    cs:__imp_IofCallDriver
0x14003a949  nop     dword ptr [rax+rax+00h]
0x14003a94e  cmp     eax, 103h
0x14003a953  jnz     short loc_14003A977
0x14003a955  mov     [rsp+0C8h+StartingOffset], 0; Timeout
0x14003a95e  xor     r9d, r9d; Alertable
0x14003a961  xor     r8d, r8d; WaitMode
0x14003a964  xor     edx, edx; WaitReason
0x14003a966  lea     rcx, [rsp+0C8h+Object]; Object
0x14003a96b  call    cs:__imp_KeWaitForSingleObject
0x14003a972  nop     dword ptr [rax+rax+00h]
0x14003a977  lea     rcx, [rsp+0C8h+Object]; Event
0x14003a97c  call    cs:__imp_KeClearEvent
0x14003a983  nop     dword ptr [rax+rax+00h]
0x14003a988  bts     dword ptr [r14], 1Ch
0x14003a98d  xor     r8d, r8d
0x14003a990  mov     rdx, rbx
0x14003a993  mov     rcx, rsi
0x14003a996  call    UdfCheckForDismount
0x14003a99b  test    al, al
0x14003a99d  jz      short loc_14003A9AE
0x14003a99f  mov     rcx, r15; Resource
0x14003a9a2  call    cs:__imp_ExReleaseResourceLite
0x14003a9a9  nop     dword ptr [rax+rax+00h]
0x14003a9ae  jmp     loc_14003A82E
0x14003a9b3  lea     rcx, Resource; Resource
0x14003a9ba  call    cs:__imp_ExReleaseResourceLite
0x14003a9c1  nop     dword ptr [rax+rax+00h]
0x14003a9c6  mov     rcx, cs:DeviceObject; DeviceObject
0x14003a9cd  call    cs:__imp_IoUnregisterFileSystem
0x14003a9d4  nop     dword ptr [rax+rax+00h]
0x14003a9d9  mov     rcx, cs:qword_140025B10; DeviceObject
0x14003a9e0  call    cs:__imp_IoUnregisterFileSystem
0x14003a9e7  nop     dword ptr [rax+rax+00h]
0x14003a9ec  mov     rcx, cs:DeviceObject; DeviceObject
0x14003a9f3  call    cs:__imp_IoDeleteDevice
0x14003a9fa  nop     dword ptr [rax+rax+00h]
0x14003a9ff  mov     rcx, cs:qword_140025B10; DeviceObject
0x14003aa06  call    cs:__imp_IoDeleteDevice
0x14003aa0d  nop     dword ptr [rax+rax+00h]
0x14003aa12  xor     r8d, r8d
0x14003aa15  mov     rdx, [rsp+0C8h+arg_8]
0x14003aa1d  mov     rcx, rsi
0x14003aa20  call    UdfCompleteRequest
0x14003aa25  xor     eax, eax
0x14003aa27  add     rsp, 90h
0x14003aa2e  pop     r15
0x14003aa30  pop     r14
0x14003aa32  pop     r13
0x14003aa34  pop     r12
0x14003aa36  pop     rdi
0x14003aa37  pop     rsi
0x14003aa38  pop     rbx
0x14003aa39  retn
0x14005c28e  push    rbp
0x14005c290  sub     rsp, 40h
0x14005c294  mov     rbp, rdx
0x14005c297  mov     rdx, rcx
0x14005c29a  mov     rcx, [rbp+0D0h]
0x14005c2a1  call    UdfExceptionFilter
0x14005c2a6  nop
0x14005c2a7  add     rsp, 40h
0x14005c2ab  pop     rbp
0x14005c2ac  retn
0x14005c2ae  push    rbp
0x14005c2b0  sub     rsp, 40h
0x14005c2b4  mov     rbp, rdx
0x14005c2b7  lea     rcx, Resource; Resource
0x14005c2be  call    cs:__imp_ExReleaseResourceLite
0x14005c2c5  nop     dword ptr [rax+rax+00h]
0x14005c2ca  mov     rcx, cs:DeviceObject; DeviceObject
0x14005c2d1  call    cs:__imp_IoUnregisterFileSystem
0x14005c2d8  nop     dword ptr [rax+rax+00h]
0x14005c2dd  mov     rcx, cs:qword_140025B10; DeviceObject
0x14005c2e4  call    cs:__imp_IoUnregisterFileSystem
0x14005c2eb  nop     dword ptr [rax+rax+00h]
0x14005c2f0  mov     rcx, cs:DeviceObject; DeviceObject
0x14005c2f7  call    cs:__imp_IoDeleteDevice
0x14005c2fe  nop     dword ptr [rax+rax+00h]
0x14005c303  mov     rcx, cs:qword_140025B10; DeviceObject
0x14005c30a  call    cs:__imp_IoDeleteDevice
0x14005c311  nop     dword ptr [rax+rax+00h]
0x14005c316  xor     r8d, r8d
0x14005c319  mov     rdx, [rbp+0D8h]
0x14005c320  mov     rcx, [rbp+0D0h]
0x14005c327  call    UdfCompleteRequest
0x14005c32c  nop
0x14005c32d  add     rsp, 40h
0x14005c331  pop     rbp
0x14005c332  retn
```
