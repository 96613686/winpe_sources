# VhdmpiInitializeNestingLevel

- ea: `0x1400e6680`
- end: `0x1400e692a`
- name: `VhdmpiInitializeNestingLevel`
- size: `682`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14004a3f4`
- `0x1400ad718`
- `0x1400ec0d8`
- `0x1400ee078`
- `0x1400ee1f0`

## callees

- `0x14001b7fc`
- `0x14001bc68`
- `0x1400e6680`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400e67e6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400e67e6`
- `ntoskrnl!KeRundownQueue` at `0x1400e6826`
- `ntoskrnl!KeRundownQueue` at `0x1400e685a`
- `ntoskrnl!KeRundownQueue` at `0x1400e6826`
- `ntoskrnl!KeRundownQueue` at `0x1400e685a`
- `ntoskrnl!KeInitializeQueue` at `0x1400e6775`
- `ntoskrnl!KeInitializeQueue` at `0x1400e6775`
- `ntoskrnl!ObfDereferenceObject` at `0x1400e6887`
- `ntoskrnl!ObfDereferenceObject` at `0x1400e6887`
- `ntoskrnl!ZwClose` at `0x1400e6807`
- `ntoskrnl!ZwClose` at `0x1400e6807`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e6877`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e6877`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e68ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e68ba`
- `ntoskrnl!PsCreateSystemThread` at `0x1400e67ab`
- `ntoskrnl!PsCreateSystemThread` at `0x1400e67ab`
- `ntoskrnl!ExAllocatePool2` at `0x1400e66e3`
- `ntoskrnl!ExAllocatePool2` at `0x1400e66e3`

## pseudocode

```c
__int64 __fastcall VhdmpiInitializeNestingLevel(unsigned int a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v4; // rsi
  __int64 v5; // r13
  _BYTE *Pool2; // rbx
  NTSTATUS v7; // edi
  unsigned int v8; // r12d
  __int64 v9; // r14
  _BYTE *v10; // r15
  __int64 j; // rsi
  PVOID *v12; // r14
  unsigned int i; // edx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  int v16; // [rsp+B0h] [rbp+40h]
  void *ThreadHandle; // [rsp+C0h] [rbp+50h] BYREF
  PVOID Object; // [rsp+C8h] [rbp+58h] BYREF

  v3 = a1;
  v4 = (int)a2;
  ThreadHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v16 = 0;
  VhdmpiAcquirePassiveLock(&VhdmpThreadPoolLock, a2, a3);
  v5 = (unsigned int)v3;
  Pool2 = (_BYTE *)*((_QWORD *)VhdmpThreadPool + v3);
  if ( Pool2 )
  {
    if ( Pool2[288] || (_DWORD)v4 != 4 && *(_QWORD *)&Pool2[72 * v4 + 64] )
    {
LABEL_36:
      v7 = 0;
      goto LABEL_37;
    }
LABEL_7:
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    v8 = v4;
    ObjectAttributes.ObjectName = 0;
    v9 = 0;
    if ( (_DWORD)v4 != 4 )
    {
      v8 = v4 + 1;
      v9 = (unsigned int)v4;
    }
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    while ( (unsigned int)v9 < v8 )
    {
      v10 = &Pool2[72 * v9];
      if ( *((_QWORD *)v10 + 8) )
      {
        *((_BYTE *)&v16 + v9) = 1;
      }
      else
      {
        KeInitializeQueue((PRKQUEUE)&Pool2[72 * v9], 0);
        v7 = PsCreateSystemThread(
               &ThreadHandle,
               0x1FFFFFu,
               &ObjectAttributes,
               0,
               0,
               (PKSTART_ROUTINE)VhdmpiThreadPoolThreadRoutine,
               &Pool2[72 * v9]);
        if ( v7 < 0 )
        {
          KeRundownQueue((PRKQUEUE)&Pool2[72 * v9]);
          goto LABEL_18;
        }
        Object = 0;
        v7 = ObReferenceObjectByHandle(ThreadHandle, 0x100020u, 0, 0, &Object, 0);
        *((_QWORD *)v10 + 8) = Object;
        if ( v7 < 0 )
          goto LABEL_18;
        ZwClose(ThreadHandle);
      }
      v9 = (unsigned int)(v9 + 1);
    }
    if ( (_DWORD)v4 == 4 )
    {
LABEL_34:
      Pool2[288] = 1;
    }
    else
    {
      for ( i = 0; i < 4; ++i )
      {
        if ( !*(_QWORD *)&Pool2[72 * i + 64] )
          break;
        if ( i == 3 )
          goto LABEL_34;
      }
    }
    *((_QWORD *)VhdmpThreadPool + v5) = Pool2;
    goto LABEL_36;
  }
  Pool2 = (_BYTE *)ExAllocatePool2(64, 296, 1732528214);
  if ( Pool2 )
    goto LABEL_7;
  v7 = -1073741670;
LABEL_18:
  if ( (_DWORD)v4 == 4 && Pool2 )
  {
    for ( j = 0; j != 4; ++j )
    {
      v12 = (PVOID *)&Pool2[72 * j];
      if ( v12[8] && *((_BYTE *)&v16 + j) != 1 )
      {
        KeRundownQueue((PRKQUEUE)&Pool2[72 * j]);
        KeWaitForSingleObject(v12[8], Executive, 0, 0, 0);
        ObfDereferenceObject(v12[8]);
        v12[8] = 0;
      }
    }
  }
  if ( !*((_QWORD *)VhdmpThreadPool + v5) && Pool2 )
    ExFreePoolWithTag(Pool2, 0x67444856u);
LABEL_37:
  VhdmpiReleasePassiveLock(&VhdmpThreadPoolLock);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400e6680  mov     [rsp-38h+arg_8], rbx
0x1400e6685  push    rbp
0x1400e6686  push    rsi
0x1400e6687  push    rdi
0x1400e6688  push    r12
0x1400e668a  push    r13
0x1400e668c  push    r14
0x1400e668e  push    r15
0x1400e6690  mov     rbp, rsp
0x1400e6693  sub     rsp, 70h
0x1400e6697  xorps   xmm0, xmm0
0x1400e669a  mov     ebx, ecx
0x1400e669c  xor     r15d, r15d
0x1400e669f  movsxd  rsi, edx
0x1400e66a2  lea     rcx, ?VhdmpThreadPoolLock@@3U_VHD_PASSIVE_LOCK@@A; _VHD_PASSIVE_LOCK VhdmpThreadPoolLock
0x1400e66a9  mov     [rbp+ThreadHandle], r15
0x1400e66ad  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400e66b1  mov     [rbp+arg_0], r15d
0x1400e66b5  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400e66b9  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400e66bd  call    VhdmpiAcquirePassiveLock
0x1400e66c2  mov     rax, cs:VhdmpThreadPool
0x1400e66c9  mov     r13d, ebx
0x1400e66cc  mov     rbx, [rax+rbx*8]
0x1400e66d0  test    rbx, rbx
0x1400e66d3  jnz     short loc_1400E6701
0x1400e66d5  mov     edx, 128h
0x1400e66da  lea     ecx, [rbx+40h]
0x1400e66dd  mov     r8d, 67444856h
0x1400e66e3  call    cs:__imp_ExAllocatePool2
0x1400e66ea  nop     dword ptr [rax+rax+00h]
0x1400e66ef  mov     rbx, rax
0x1400e66f2  test    rax, rax
0x1400e66f5  jnz     short loc_1400E6722
0x1400e66f7  mov     edi, 0C000009Ah
0x1400e66fc  jmp     loc_1400E6835
0x1400e6701  cmp     [rbx+120h], r15b
0x1400e6708  jnz     loc_1400E6900
0x1400e670e  cmp     esi, 4
0x1400e6711  jz      short loc_1400E6722
0x1400e6713  lea     rcx, [rsi+rsi*8]
0x1400e6717  cmp     [rbx+rcx*8+40h], r15
0x1400e671c  jnz     loc_1400E6900
0x1400e6722  cmp     esi, 4
0x1400e6725  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400e672c  xorps   xmm0, xmm0
0x1400e672f  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x1400e6733  lea     eax, [rsi+1]
0x1400e6736  mov     [rbp+ObjectAttributes.Attributes], 200h
0x1400e673d  mov     r12d, esi
0x1400e6740  mov     [rbp+ObjectAttributes.ObjectName], r15
0x1400e6744  mov     r14d, r15d
0x1400e6747  cmovnz  r12d, eax
0x1400e674b  cmovnz  r14d, esi
0x1400e674f  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400e6754  cmp     r14d, r12d
0x1400e6757  jnb     loc_1400E68C8
0x1400e675d  lea     rax, [r14+r14*8]
0x1400e6761  lea     r15, [rbx+rax*8]
0x1400e6765  cmp     qword ptr [r15+40h], 0
0x1400e676a  jnz     loc_1400E6815
0x1400e6770  xor     edx, edx; Count
0x1400e6772  mov     rcx, r15; Queue
0x1400e6775  call    cs:__imp_KeInitializeQueue
0x1400e677c  nop     dword ptr [rax+rax+00h]
0x1400e6781  lea     rax, ?VhdmpiThreadPoolThreadRoutine@@YAXPEAX@Z; VhdmpiThreadPoolThreadRoutine(void *)
0x1400e6788  mov     [rsp+70h+StartContext], r15; StartContext
0x1400e678d  mov     [rsp+70h+StartRoutine], rax; StartRoutine
0x1400e6792  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400e6796  xor     r9d, r9d; ProcessHandle
0x1400e6799  mov     [rsp+70h+ClientId], 0; ClientId
0x1400e67a2  mov     edx, 1FFFFFh; DesiredAccess
0x1400e67a7  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x1400e67ab  call    cs:__imp_PsCreateSystemThread
0x1400e67b2  nop     dword ptr [rax+rax+00h]
0x1400e67b7  mov     edi, eax
0x1400e67b9  test    eax, eax
0x1400e67bb  js      short loc_1400E6823
0x1400e67bd  mov     rcx, [rbp+ThreadHandle]; Handle
0x1400e67c1  lea     rax, [rbp+Object]
0x1400e67c5  mov     [rsp+70h+StartRoutine], 0; HandleInformation
0x1400e67ce  xor     r9d, r9d; AccessMode
0x1400e67d1  xor     r8d, r8d; ObjectType
0x1400e67d4  mov     [rsp+70h+ClientId], rax; Object
0x1400e67d9  mov     edx, 100020h; DesiredAccess
0x1400e67de  mov     [rbp+Object], 0
0x1400e67e6  call    cs:__imp_ObReferenceObjectByHandle
0x1400e67ed  nop     dword ptr [rax+rax+00h]
0x1400e67f2  mov     edi, eax
0x1400e67f4  mov     rax, [rbp+Object]
0x1400e67f8  mov     [r15+40h], rax
0x1400e67fc  xor     r15d, r15d
0x1400e67ff  test    edi, edi
0x1400e6801  js      short loc_1400E6835
0x1400e6803  mov     rcx, [rbp+ThreadHandle]; Handle
0x1400e6807  call    cs:__imp_ZwClose
0x1400e680e  nop     dword ptr [rax+rax+00h]
0x1400e6813  jmp     short loc_1400E681B
0x1400e6815  mov     byte ptr [rbp+r14+arg_0], 1
0x1400e681b  inc     r14d
0x1400e681e  jmp     loc_1400E6754
0x1400e6823  mov     rcx, r15; Queue
0x1400e6826  call    cs:__imp_KeRundownQueue
0x1400e682d  nop     dword ptr [rax+rax+00h]
0x1400e6832  xor     r15d, r15d
0x1400e6835  cmp     esi, 4
0x1400e6838  jnz     short loc_1400E68A0
0x1400e683a  test    rbx, rbx
0x1400e683d  jz      short loc_1400E68A0
0x1400e683f  mov     rsi, r15
0x1400e6842  lea     rax, [rsi+rsi*8]
0x1400e6846  lea     r14, [rbx+rax*8]
0x1400e684a  cmp     [r14+40h], r15
0x1400e684e  jz      short loc_1400E6897
0x1400e6850  cmp     byte ptr [rbp+rsi+arg_0], 1
0x1400e6855  jz      short loc_1400E6897
0x1400e6857  mov     rcx, r14; Queue
0x1400e685a  call    cs:__imp_KeRundownQueue
0x1400e6861  nop     dword ptr [rax+rax+00h]
0x1400e6866  mov     rcx, [r14+40h]; Object
0x1400e686a  xor     r9d, r9d; Alertable
0x1400e686d  xor     r8d, r8d; WaitMode
0x1400e6870  mov     [rsp+70h+ClientId], r15; Timeout
0x1400e6875  xor     edx, edx; WaitReason
0x1400e6877  call    cs:__imp_KeWaitForSingleObject
0x1400e687e  nop     dword ptr [rax+rax+00h]
0x1400e6883  mov     rcx, [r14+40h]; Object
0x1400e6887  call    cs:__imp_ObfDereferenceObject
0x1400e688e  nop     dword ptr [rax+rax+00h]
0x1400e6893  mov     [r14+40h], r15
0x1400e6897  inc     rsi
0x1400e689a  cmp     rsi, 4
0x1400e689e  jnz     short loc_1400E6842
0x1400e68a0  mov     rax, cs:VhdmpThreadPool
0x1400e68a7  cmp     [rax+r13*8], r15
0x1400e68ab  jnz     short loc_1400E6903
0x1400e68ad  test    rbx, rbx
0x1400e68b0  jz      short loc_1400E6903
0x1400e68b2  mov     edx, 67444856h; Tag
0x1400e68b7  mov     rcx, rbx; P
0x1400e68ba  call    cs:__imp_ExFreePoolWithTag
0x1400e68c1  nop     dword ptr [rax+rax+00h]
0x1400e68c6  jmp     short loc_1400E6903
0x1400e68c8  xor     r15d, r15d
0x1400e68cb  cmp     esi, 4
0x1400e68ce  jz      short loc_1400E68EE
0x1400e68d0  mov     edx, r15d
0x1400e68d3  mov     eax, edx
0x1400e68d5  lea     rcx, [rax+rax*8]
0x1400e68d9  cmp     [rbx+rcx*8+40h], r15
0x1400e68de  jz      short loc_1400E68F5
0x1400e68e0  cmp     edx, 3
0x1400e68e3  jz      short loc_1400E68EE
0x1400e68e5  inc     edx
0x1400e68e7  cmp     edx, 4
0x1400e68ea  jb      short loc_1400E68D3
0x1400e68ec  jmp     short loc_1400E68F5
0x1400e68ee  mov     byte ptr [rbx+120h], 1
0x1400e68f5  mov     rax, cs:VhdmpThreadPool
0x1400e68fc  mov     [rax+r13*8], rbx
0x1400e6900  mov     edi, r15d
0x1400e6903  lea     rcx, ?VhdmpThreadPoolLock@@3U_VHD_PASSIVE_LOCK@@A; _VHD_PASSIVE_LOCK VhdmpThreadPoolLock
0x1400e690a  call    VhdmpiReleasePassiveLock
0x1400e690f  mov     rbx, [rsp+70h+arg_8]
0x1400e6917  mov     eax, edi
0x1400e6919  add     rsp, 70h
0x1400e691d  pop     r15
0x1400e691f  pop     r14
0x1400e6921  pop     r13
0x1400e6923  pop     r12
0x1400e6925  pop     rdi
0x1400e6926  pop     rsi
0x1400e6927  pop     rbp
0x1400e6928  retn
```
