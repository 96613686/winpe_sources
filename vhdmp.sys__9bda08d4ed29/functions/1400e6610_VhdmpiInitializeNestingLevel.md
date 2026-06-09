# VhdmpiInitializeNestingLevel

- ea: `0x1400e6610`
- end: `0x1400e68ba`
- name: `VhdmpiInitializeNestingLevel`
- size: `682`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14004a7e4`
- `0x1400ad718`
- `0x1400ec068`
- `0x1400ee078`
- `0x1400ee1f0`

## callees

- `0x14001bc1c`
- `0x14001c088`
- `0x1400e6610`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400e6776`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400e6776`
- `ntoskrnl!KeRundownQueue` at `0x1400e67b6`
- `ntoskrnl!KeRundownQueue` at `0x1400e67ea`
- `ntoskrnl!KeRundownQueue` at `0x1400e67b6`
- `ntoskrnl!KeRundownQueue` at `0x1400e67ea`
- `ntoskrnl!KeInitializeQueue` at `0x1400e6705`
- `ntoskrnl!KeInitializeQueue` at `0x1400e6705`
- `ntoskrnl!ObfDereferenceObject` at `0x1400e6817`
- `ntoskrnl!ObfDereferenceObject` at `0x1400e6817`
- `ntoskrnl!ZwClose` at `0x1400e6797`
- `ntoskrnl!ZwClose` at `0x1400e6797`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e6807`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e6807`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e684a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e684a`
- `ntoskrnl!PsCreateSystemThread` at `0x1400e673b`
- `ntoskrnl!PsCreateSystemThread` at `0x1400e673b`
- `ntoskrnl!ExAllocatePool2` at `0x1400e6673`
- `ntoskrnl!ExAllocatePool2` at `0x1400e6673`

## pseudocode

```c
__int64 __fastcall VhdmpiInitializeNestingLevel(unsigned int a1, int a2)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  __int64 v4; // r13
  _BYTE *Pool2; // rbx
  NTSTATUS v6; // edi
  unsigned int v7; // r12d
  __int64 v8; // r14
  _BYTE *v9; // r15
  __int64 j; // rsi
  PVOID *v11; // r14
  unsigned int i; // edx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  int v15; // [rsp+B0h] [rbp+40h]
  void *ThreadHandle; // [rsp+C0h] [rbp+50h] BYREF
  PVOID Object; // [rsp+C8h] [rbp+58h] BYREF

  v2 = a1;
  v3 = a2;
  ThreadHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v15 = 0;
  VhdmpiAcquirePassiveLock(&VhdmpThreadPoolLock);
  v4 = (unsigned int)v2;
  Pool2 = (_BYTE *)*((_QWORD *)VhdmpThreadPool + v2);
  if ( Pool2 )
  {
    if ( Pool2[288] || (_DWORD)v3 != 4 && *(_QWORD *)&Pool2[72 * v3 + 64] )
    {
LABEL_36:
      v6 = 0;
      goto LABEL_37;
    }
LABEL_7:
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    v7 = v3;
    ObjectAttributes.ObjectName = 0;
    v8 = 0;
    if ( (_DWORD)v3 != 4 )
    {
      v7 = v3 + 1;
      v8 = (unsigned int)v3;
    }
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    while ( (unsigned int)v8 < v7 )
    {
      v9 = &Pool2[72 * v8];
      if ( *((_QWORD *)v9 + 8) )
      {
        *((_BYTE *)&v15 + v8) = 1;
      }
      else
      {
        KeInitializeQueue((PRKQUEUE)&Pool2[72 * v8], 0);
        v6 = PsCreateSystemThread(
               &ThreadHandle,
               0x1FFFFFu,
               &ObjectAttributes,
               0,
               0,
               (PKSTART_ROUTINE)VhdmpiThreadPoolThreadRoutine,
               &Pool2[72 * v8]);
        if ( v6 < 0 )
        {
          KeRundownQueue((PRKQUEUE)&Pool2[72 * v8]);
          goto LABEL_18;
        }
        Object = 0;
        v6 = ObReferenceObjectByHandle(ThreadHandle, 0x100020u, 0, 0, &Object, 0);
        *((_QWORD *)v9 + 8) = Object;
        if ( v6 < 0 )
          goto LABEL_18;
        ZwClose(ThreadHandle);
      }
      v8 = (unsigned int)(v8 + 1);
    }
    if ( (_DWORD)v3 == 4 )
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
    *((_QWORD *)VhdmpThreadPool + v4) = Pool2;
    goto LABEL_36;
  }
  Pool2 = (_BYTE *)ExAllocatePool2(64, 296, 1732528214);
  if ( Pool2 )
    goto LABEL_7;
  v6 = -1073741670;
LABEL_18:
  if ( (_DWORD)v3 == 4 && Pool2 )
  {
    for ( j = 0; j != 4; ++j )
    {
      v11 = (PVOID *)&Pool2[72 * j];
      if ( v11[8] && *((_BYTE *)&v15 + j) != 1 )
      {
        KeRundownQueue((PRKQUEUE)&Pool2[72 * j]);
        KeWaitForSingleObject(v11[8], Executive, 0, 0, 0);
        ObfDereferenceObject(v11[8]);
        v11[8] = 0;
      }
    }
  }
  if ( !*((_QWORD *)VhdmpThreadPool + v4) && Pool2 )
    ExFreePoolWithTag(Pool2, 0x67444856u);
LABEL_37:
  VhdmpiReleasePassiveLock(&VhdmpThreadPoolLock);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400e6610  mov     [rsp-38h+arg_8], rbx
0x1400e6615  push    rbp
0x1400e6616  push    rsi
0x1400e6617  push    rdi
0x1400e6618  push    r12
0x1400e661a  push    r13
0x1400e661c  push    r14
0x1400e661e  push    r15
0x1400e6620  mov     rbp, rsp
0x1400e6623  sub     rsp, 70h
0x1400e6627  xorps   xmm0, xmm0
0x1400e662a  mov     ebx, ecx
0x1400e662c  xor     r15d, r15d
0x1400e662f  movsxd  rsi, edx
0x1400e6632  lea     rcx, ?VhdmpThreadPoolLock@@3U_VHD_PASSIVE_LOCK@@A; _VHD_PASSIVE_LOCK VhdmpThreadPoolLock
0x1400e6639  mov     [rbp+ThreadHandle], r15
0x1400e663d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400e6641  mov     [rbp+arg_0], r15d
0x1400e6645  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400e6649  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400e664d  call    VhdmpiAcquirePassiveLock
0x1400e6652  mov     rax, cs:VhdmpThreadPool
0x1400e6659  mov     r13d, ebx
0x1400e665c  mov     rbx, [rax+rbx*8]
0x1400e6660  test    rbx, rbx
0x1400e6663  jnz     short loc_1400E6691
0x1400e6665  mov     edx, 128h
0x1400e666a  lea     ecx, [rbx+40h]
0x1400e666d  mov     r8d, 67444856h
0x1400e6673  call    cs:__imp_ExAllocatePool2
0x1400e667a  nop     dword ptr [rax+rax+00h]
0x1400e667f  mov     rbx, rax
0x1400e6682  test    rax, rax
0x1400e6685  jnz     short loc_1400E66B2
0x1400e6687  mov     edi, 0C000009Ah
0x1400e668c  jmp     loc_1400E67C5
0x1400e6691  cmp     [rbx+120h], r15b
0x1400e6698  jnz     loc_1400E6890
0x1400e669e  cmp     esi, 4
0x1400e66a1  jz      short loc_1400E66B2
0x1400e66a3  lea     rcx, [rsi+rsi*8]
0x1400e66a7  cmp     [rbx+rcx*8+40h], r15
0x1400e66ac  jnz     loc_1400E6890
0x1400e66b2  cmp     esi, 4
0x1400e66b5  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400e66bc  xorps   xmm0, xmm0
0x1400e66bf  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x1400e66c3  lea     eax, [rsi+1]
0x1400e66c6  mov     [rbp+ObjectAttributes.Attributes], 200h
0x1400e66cd  mov     r12d, esi
0x1400e66d0  mov     [rbp+ObjectAttributes.ObjectName], r15
0x1400e66d4  mov     r14d, r15d
0x1400e66d7  cmovnz  r12d, eax
0x1400e66db  cmovnz  r14d, esi
0x1400e66df  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400e66e4  cmp     r14d, r12d
0x1400e66e7  jnb     loc_1400E6858
0x1400e66ed  lea     rax, [r14+r14*8]
0x1400e66f1  lea     r15, [rbx+rax*8]
0x1400e66f5  cmp     qword ptr [r15+40h], 0
0x1400e66fa  jnz     loc_1400E67A5
0x1400e6700  xor     edx, edx; Count
0x1400e6702  mov     rcx, r15; Queue
0x1400e6705  call    cs:__imp_KeInitializeQueue
0x1400e670c  nop     dword ptr [rax+rax+00h]
0x1400e6711  lea     rax, ?VhdmpiThreadPoolThreadRoutine@@YAXPEAX@Z; VhdmpiThreadPoolThreadRoutine(void *)
0x1400e6718  mov     [rsp+70h+StartContext], r15; StartContext
0x1400e671d  mov     [rsp+70h+StartRoutine], rax; StartRoutine
0x1400e6722  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400e6726  xor     r9d, r9d; ProcessHandle
0x1400e6729  mov     [rsp+70h+ClientId], 0; ClientId
0x1400e6732  mov     edx, 1FFFFFh; DesiredAccess
0x1400e6737  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x1400e673b  call    cs:__imp_PsCreateSystemThread
0x1400e6742  nop     dword ptr [rax+rax+00h]
0x1400e6747  mov     edi, eax
0x1400e6749  test    eax, eax
0x1400e674b  js      short loc_1400E67B3
0x1400e674d  mov     rcx, [rbp+ThreadHandle]; Handle
0x1400e6751  lea     rax, [rbp+Object]
0x1400e6755  mov     [rsp+70h+StartRoutine], 0; HandleInformation
0x1400e675e  xor     r9d, r9d; AccessMode
0x1400e6761  xor     r8d, r8d; ObjectType
0x1400e6764  mov     [rsp+70h+ClientId], rax; Object
0x1400e6769  mov     edx, 100020h; DesiredAccess
0x1400e676e  mov     [rbp+Object], 0
0x1400e6776  call    cs:__imp_ObReferenceObjectByHandle
0x1400e677d  nop     dword ptr [rax+rax+00h]
0x1400e6782  mov     edi, eax
0x1400e6784  mov     rax, [rbp+Object]
0x1400e6788  mov     [r15+40h], rax
0x1400e678c  xor     r15d, r15d
0x1400e678f  test    edi, edi
0x1400e6791  js      short loc_1400E67C5
0x1400e6793  mov     rcx, [rbp+ThreadHandle]; Handle
0x1400e6797  call    cs:__imp_ZwClose
0x1400e679e  nop     dword ptr [rax+rax+00h]
0x1400e67a3  jmp     short loc_1400E67AB
0x1400e67a5  mov     byte ptr [rbp+r14+arg_0], 1
0x1400e67ab  inc     r14d
0x1400e67ae  jmp     loc_1400E66E4
0x1400e67b3  mov     rcx, r15; Queue
0x1400e67b6  call    cs:__imp_KeRundownQueue
0x1400e67bd  nop     dword ptr [rax+rax+00h]
0x1400e67c2  xor     r15d, r15d
0x1400e67c5  cmp     esi, 4
0x1400e67c8  jnz     short loc_1400E6830
0x1400e67ca  test    rbx, rbx
0x1400e67cd  jz      short loc_1400E6830
0x1400e67cf  mov     rsi, r15
0x1400e67d2  lea     rax, [rsi+rsi*8]
0x1400e67d6  lea     r14, [rbx+rax*8]
0x1400e67da  cmp     [r14+40h], r15
0x1400e67de  jz      short loc_1400E6827
0x1400e67e0  cmp     byte ptr [rbp+rsi+arg_0], 1
0x1400e67e5  jz      short loc_1400E6827
0x1400e67e7  mov     rcx, r14; Queue
0x1400e67ea  call    cs:__imp_KeRundownQueue
0x1400e67f1  nop     dword ptr [rax+rax+00h]
0x1400e67f6  mov     rcx, [r14+40h]; Object
0x1400e67fa  xor     r9d, r9d; Alertable
0x1400e67fd  xor     r8d, r8d; WaitMode
0x1400e6800  mov     [rsp+70h+ClientId], r15; Timeout
0x1400e6805  xor     edx, edx; WaitReason
0x1400e6807  call    cs:__imp_KeWaitForSingleObject
0x1400e680e  nop     dword ptr [rax+rax+00h]
0x1400e6813  mov     rcx, [r14+40h]; Object
0x1400e6817  call    cs:__imp_ObfDereferenceObject
0x1400e681e  nop     dword ptr [rax+rax+00h]
0x1400e6823  mov     [r14+40h], r15
0x1400e6827  inc     rsi
0x1400e682a  cmp     rsi, 4
0x1400e682e  jnz     short loc_1400E67D2
0x1400e6830  mov     rax, cs:VhdmpThreadPool
0x1400e6837  cmp     [rax+r13*8], r15
0x1400e683b  jnz     short loc_1400E6893
0x1400e683d  test    rbx, rbx
0x1400e6840  jz      short loc_1400E6893
0x1400e6842  mov     edx, 67444856h; Tag
0x1400e6847  mov     rcx, rbx; P
0x1400e684a  call    cs:__imp_ExFreePoolWithTag
0x1400e6851  nop     dword ptr [rax+rax+00h]
0x1400e6856  jmp     short loc_1400E6893
0x1400e6858  xor     r15d, r15d
0x1400e685b  cmp     esi, 4
0x1400e685e  jz      short loc_1400E687E
0x1400e6860  mov     edx, r15d
0x1400e6863  mov     eax, edx
0x1400e6865  lea     rcx, [rax+rax*8]
0x1400e6869  cmp     [rbx+rcx*8+40h], r15
0x1400e686e  jz      short loc_1400E6885
0x1400e6870  cmp     edx, 3
0x1400e6873  jz      short loc_1400E687E
0x1400e6875  inc     edx
0x1400e6877  cmp     edx, 4
0x1400e687a  jb      short loc_1400E6863
0x1400e687c  jmp     short loc_1400E6885
0x1400e687e  mov     byte ptr [rbx+120h], 1
0x1400e6885  mov     rax, cs:VhdmpThreadPool
0x1400e688c  mov     [rax+r13*8], rbx
0x1400e6890  mov     edi, r15d
0x1400e6893  lea     rcx, ?VhdmpThreadPoolLock@@3U_VHD_PASSIVE_LOCK@@A; _VHD_PASSIVE_LOCK VhdmpThreadPoolLock
0x1400e689a  call    VhdmpiReleasePassiveLock
0x1400e689f  mov     rbx, [rsp+70h+arg_8]
0x1400e68a7  mov     eax, edi
0x1400e68a9  add     rsp, 70h
0x1400e68ad  pop     r15
0x1400e68af  pop     r14
0x1400e68b1  pop     r13
0x1400e68b3  pop     r12
0x1400e68b5  pop     rdi
0x1400e68b6  pop     rsi
0x1400e68b7  pop     rbp
0x1400e68b8  retn
```
