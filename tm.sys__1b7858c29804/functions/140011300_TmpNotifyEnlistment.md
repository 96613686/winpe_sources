# TmpNotifyEnlistment

- ea: `0x140011300`
- end: `0x1400114a4`
- name: `TmpNotifyEnlistment`
- size: `420`
- prototype: `__int64 __usercall@<rax>(PVOID Object@<rcx>, int)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c010`
- `0x14000c320`
- `0x14000c480`
- `0x140010330`
- `0x1400108c0`
- `0x1400110f4`
- `0x140011ab4`
- `0x140011c80`
- `0x14001b594`

## callees

- `0x14000c9ac`
- `0x140011300`
- `0x14001c010`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140011357`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001145f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011357`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001145f`
- `ntoskrnl!KeReleaseMutex` at `0x1400113dd`
- `ntoskrnl!KeReleaseMutex` at `0x140011478`
- `ntoskrnl!KeReleaseMutex` at `0x1400113dd`
- `ntoskrnl!KeReleaseMutex` at `0x140011478`
- `ntoskrnl!ObfDereferenceObject` at `0x140011487`
- `ntoskrnl!ObfDereferenceObject` at `0x140011487`
- `ntoskrnl!ObfReferenceObject` at `0x14001132e`
- `ntoskrnl!ObfReferenceObject` at `0x14001132e`
- `ntoskrnl!DbgPrintEx` at `0x140011413`
- `ntoskrnl!DbgPrintEx` at `0x140011413`

## pseudocode

```c
__int64 __fastcall TmpNotifyEnlistment(char *Object, char a2, unsigned int a3, char a4, int a5)
{
  unsigned int v10; // r14d
  int v11; // edx
  bool v12; // di
  __int64 v13; // rdx
  size_t Size; // [rsp+28h] [rbp-50h]

  if ( (*((_DWORD *)Object + 44) & a3) == 0 )
    return 0;
  v10 = 0;
  ObfReferenceObject(Object);
  if ( a4 )
  {
    KeWaitForSingleObject(Object + 64, Executive, 0, 0, 0);
    *((_DWORD *)Object + 42) = a5;
    if ( (*((_DWORD *)Object + 43) & 1) != 0 )
    {
      v12 = 0;
      if ( (unsigned int)(a5 - 260) <= 0xB )
      {
        v11 = 2561;
        if ( _bittest(&v11, a5 - 260) )
          v12 = 1;
      }
    }
    else
    {
      v12 = ((a5 - 269) & 0xFFFFFFFD) == 0;
    }
    *(_DWORD *)&Object[8 * *((unsigned int *)Object + 78) + 316] = a3;
    *(_DWORD *)&Object[8 * (*((_DWORD *)Object + 78))++ + 320] = a5;
    if ( *((_DWORD *)Object + 78) >= 0x14u )
      *((_DWORD *)Object + 78) = 0;
    KeReleaseMutex((PRKMUTEX)(Object + 64), 0);
  }
  else
  {
    v12 = 0;
  }
  if ( a2 )
  {
    DbgPrintEx(0x6Cu, 0x80000020, "KTM:  Notifying RM of %d for tx %lx\n", a3, *((_QWORD *)Object + 20));
    LODWORD(Size) = 0;
    v10 = TmpSetNotificationResourceManager(
            *((PRKEVENT *)Object + 19),
            v13,
            (__int64)Object,
            *((struct _LIST_ENTRY **)Object + 23),
            a3,
            Size,
            0);
  }
  if ( v12 )
  {
    KeWaitForSingleObject(Object + 64, Executive, 0, 0, 0);
    TmpFinalizeEnlistment(Object);
    KeReleaseMutex((PRKMUTEX)(Object + 64), 0);
  }
  ObfDereferenceObject(Object);
  return v10;
}

```

## disassembly

```asm
0x140011300  push    rbx
0x140011302  push    rbp
0x140011303  push    rsi
0x140011304  push    rdi
0x140011305  push    r14
0x140011307  push    r15
0x140011309  sub     rsp, 48h
0x14001130d  mov     eax, [rcx+0B0h]
0x140011313  mov     dil, r9b
0x140011316  mov     ebp, r8d
0x140011319  mov     r15b, dl
0x14001131c  mov     rbx, rcx
0x14001131f  test    r8d, eax
0x140011322  jnz     short loc_14001132B
0x140011324  xor     eax, eax
0x140011326  jmp     loc_140011496
0x14001132b  xor     r14d, r14d
0x14001132e  call    cs:__imp_ObfReferenceObject
0x140011335  nop     dword ptr [rax+rax+00h]
0x14001133a  lea     rsi, [rbx+40h]
0x14001133e  test    dil, dil
0x140011341  jz      loc_1400113EB
0x140011347  xor     r9d, r9d; Alertable
0x14001134a  mov     [rsp+78h+Timeout], r14; Timeout
0x14001134f  xor     r8d, r8d; WaitMode
0x140011352  xor     edx, edx; WaitReason
0x140011354  mov     rcx, rsi; Object
0x140011357  call    cs:__imp_KeWaitForSingleObject
0x14001135e  nop     dword ptr [rax+rax+00h]
0x140011363  mov     ecx, [rsp+78h+arg_20]
0x14001136a  mov     [rbx+0A8h], ecx
0x140011370  mov     eax, [rbx+0ACh]
0x140011376  test    al, 1
0x140011378  jz      short loc_140011399
0x14001137a  lea     eax, [rcx-104h]
0x140011380  cmp     eax, 0Bh
0x140011383  ja      short loc_140011395
0x140011385  mov     edx, 0A01h
0x14001138a  bt      edx, eax
0x14001138d  jnb     short loc_140011395
0x14001138f  lea     edi, [r14+1]
0x140011393  jmp     short loc_1400113A8
0x140011395  xor     edi, edi
0x140011397  jmp     short loc_1400113A8
0x140011399  lea     eax, [rcx-10Dh]
0x14001139f  test    eax, 0FFFFFFFDh
0x1400113a4  setz    dil
0x1400113a8  mov     eax, [rbx+138h]
0x1400113ae  mov     [rbx+rax*8+13Ch], ebp
0x1400113b5  mov     eax, [rbx+138h]
0x1400113bb  mov     [rbx+rax*8+140h], ecx
0x1400113c2  inc     dword ptr [rbx+138h]
0x1400113c8  cmp     dword ptr [rbx+138h], 14h
0x1400113cf  jb      short loc_1400113D8
0x1400113d1  mov     [rbx+138h], r14d
0x1400113d8  xor     edx, edx; Wait
0x1400113da  mov     rcx, rsi; Mutex
0x1400113dd  call    cs:__imp_KeReleaseMutex
0x1400113e4  nop     dword ptr [rax+rax+00h]
0x1400113e9  jmp     short loc_1400113EE
0x1400113eb  xor     dil, dil
0x1400113ee  test    r15b, r15b
0x1400113f1  jz      short loc_140011446
0x1400113f3  mov     rax, [rbx+0A0h]
0x1400113fa  lea     r8, aKtmNotifyingRm; "KTM:  Notifying RM of %d for tx %lx\n"
0x140011401  mov     r9d, ebp
0x140011404  mov     [rsp+78h+Timeout], rax
0x140011409  mov     edx, 80000020h; Level
0x14001140e  mov     ecx, 6Ch ; 'l'; ComponentId
0x140011413  call    cs:__imp_DbgPrintEx
0x14001141a  nop     dword ptr [rax+rax+00h]
0x14001141f  mov     r9, [rbx+0B8h]
0x140011426  mov     r8, rbx
0x140011429  mov     rcx, [rbx+98h]; Event
0x140011430  mov     [rsp+78h+Src], r14; Src
0x140011435  mov     dword ptr [rsp+78h+Size], r14d; Size
0x14001143a  mov     dword ptr [rsp+78h+Timeout], ebp; int
0x14001143e  call    TmpSetNotificationResourceManager
0x140011443  mov     r14d, eax
0x140011446  test    dil, dil
0x140011449  jz      short loc_140011484
0x14001144b  xor     r9d, r9d; Alertable
0x14001144e  mov     [rsp+78h+Timeout], 0; Timeout
0x140011457  xor     r8d, r8d; WaitMode
0x14001145a  xor     edx, edx; WaitReason
0x14001145c  mov     rcx, rsi; Object
0x14001145f  call    cs:__imp_KeWaitForSingleObject
0x140011466  nop     dword ptr [rax+rax+00h]
0x14001146b  mov     rcx, rbx; Object
0x14001146e  call    TmpFinalizeEnlistment
0x140011473  xor     edx, edx; Wait
0x140011475  mov     rcx, rsi; Mutex
0x140011478  call    cs:__imp_KeReleaseMutex
0x14001147f  nop     dword ptr [rax+rax+00h]
0x140011484  mov     rcx, rbx; Object
0x140011487  call    cs:__imp_ObfDereferenceObject
0x14001148e  nop     dword ptr [rax+rax+00h]
0x140011493  mov     eax, r14d
0x140011496  add     rsp, 48h
0x14001149a  pop     r15
0x14001149c  pop     r14
0x14001149e  pop     rdi
0x14001149f  pop     rsi
0x1400114a0  pop     rbp
0x1400114a1  pop     rbx
0x1400114a2  retn
```
