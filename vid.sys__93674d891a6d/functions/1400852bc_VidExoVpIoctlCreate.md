# VidExoVpIoctlCreate

- ea: `0x1400852bc`
- end: `0x1400855d8`
- name: `VidExoVpIoctlCreate`
- size: `796`
- prototype: `__int64 __usercall@<rax>(PVOID DeferredContext@<rcx>, HANDLE Handle)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140038040`

## callees

- `0x1400248f4`
- `0x1400347a4`
- `0x1400347d4`
- `0x140034b64`
- `0x1400386a0`
- `0x1400852bc`
- `0x140085a04`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140085348`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140085348`
- `ntoskrnl!ExEventObjectType` at `0x140085307`
- `ntoskrnl!ObfDereferenceObject` at `0x140085521`
- `ntoskrnl!ObfDereferenceObject` at `0x140085521`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085556`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085556`
- `ntoskrnl!ExAllocatePool2` at `0x1400853cf`
- `ntoskrnl!ExAllocatePool2` at `0x1400853cf`

## string_xrefs

- `0x1400852f1`: `VidExoVpIoctlCreate`
- `0x140085382`: `VidExoVpIoctlCreate`
- `0x14008540a`: `VidExoVpIoctlCreate`
- `0x14008546c`: `VidExoVpIoctlCreate`
- `0x1400854db`: `VidExoVpIoctlCreate`
- `0x1400855b5`: `VidExoVpIoctlCreate`

## pseudocode

```c
__int64 __fastcall VidExoVpIoctlCreate(
        _QWORD *DeferredContext,
        unsigned int a2,
        unsigned __int8 a3,
        _OWORD *a4,
        HANDLE Handle)
{
  unsigned __int64 v5; // r12
  int v7; // ebx
  unsigned int v8; // ebp
  unsigned int v9; // r13d
  unsigned int *v10; // rsi
  PVOID v11; // rcx
  unsigned int v12; // eax
  unsigned int i; // ebx
  __int64 v14; // rcx
  unsigned int v15; // r8d
  void *v16; // rcx
  char v18; // [rsp+30h] [rbp-48h]
  PVOID v19; // [rsp+38h] [rbp-40h]
  PVOID Object; // [rsp+40h] [rbp-38h] BYREF
  _DWORD *v21; // [rsp+48h] [rbp-30h]
  char v22; // [rsp+88h] [rbp+10h]

  v5 = a2;
  if ( a2 >= 0x800 )
  {
    VidTraceErrorInternal0("VidExoVpIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\videxovp.c", 450);
    v7 = -1073741811;
LABEL_37:
    VidTraceErrorStatusPartitionInternal0(
      (unsigned int)"VidExoVpIoctlCreate",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\videxovp.c",
      602,
      v7,
      (__int64)(DeferredContext + 82));
    return (unsigned int)v7;
  }
  v8 = 0;
  v9 = 0;
  v22 = 0;
  v21 = 0;
  Object = 0;
  v7 = ObReferenceObjectByHandle(Handle, 2u, (POBJECT_TYPE)ExEventObjectType, 1, &Object, 0);
  v10 = (unsigned int *)(DeferredContext + 1498);
  v19 = Object;
  if ( v7 < 0 )
  {
    v18 = 0;
    VidTraceErrorInternal0("VidExoVpIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\videxovp.c", 467);
LABEL_5:
    v11 = v19;
    goto LABEL_23;
  }
  VidObjectLockAcquireExclusive(DeferredContext);
  v12 = *v10;
  v18 = 1;
  if ( (unsigned int)v5 < *v10 )
  {
    VidObjectLockRelease(DeferredContext);
    VidObjectLockAcquireShared(DeferredContext);
  }
  else
  {
    v8 = v12 >> 6;
    v9 = (unsigned int)v5 >> 6;
    for ( i = v12 >> 6; i <= v9; ++i )
    {
      *(_QWORD *)(DeferredContext[1497] + 8LL * i) = ExAllocatePool2(64, 1024, 1917084758);
      if ( !*(_QWORD *)(DeferredContext[1497] + 8LL * i) )
      {
        VidTraceErrorInternal0("VidExoVpIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\videxovp.c", 497);
        v7 = -1073741670;
        goto LABEL_5;
      }
    }
  }
  v14 = 16 * (v5 & 0x3F) + *(_QWORD *)(DeferredContext[1497] + 8 * (v5 >> 6));
  v21 = (_DWORD *)v14;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)v14, 1, 0) )
  {
    VidTraceErrorInternal0("VidExoVpIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\videxovp.c", 520);
    v7 = -1073740024;
    goto LABEL_5;
  }
  v15 = a3 | 0x80000000;
  if ( *((char *)DeferredContext + 16) < 0 )
    v15 = a3;
  v7 = VidExoVppCreate(DeferredContext, v5, v15, a4, &Object, (unsigned int **)(v14 + 8));
  if ( v7 >= 0 )
  {
    *v21 = 2;
    if ( (unsigned int)v5 >= *v10 )
      *((_DWORD *)DeferredContext + 2996) = *v10 + ((v9 - v8 + 1) << 6);
    v22 = 0;
    v7 = 0;
  }
  else
  {
    v22 = 1;
    VidTraceErrorInternal0("VidExoVpIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\videxovp.c", 542);
  }
  v11 = Object;
LABEL_23:
  if ( v11 )
    ObfDereferenceObject(v11);
  if ( v18 )
  {
    if ( v7 < 0 && (unsigned int)v5 >= *v10 )
    {
      while ( v8 <= v9 )
      {
        v16 = *(void **)(DeferredContext[1497] + 8LL * v8);
        if ( v16 )
        {
          ExFreePoolWithTag(v16, 0x72446456u);
          *(_QWORD *)(DeferredContext[1497] + 8LL * v8) = 0;
        }
        ++v8;
      }
    }
    VidObjectLockRelease(DeferredContext);
  }
  if ( v22 )
    *v21 = 0;
  if ( v7 < 0 )
    goto LABEL_37;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400852bc  mov     [rsp+arg_0], rbx
0x1400852c1  mov     [rsp+arg_18], r9
0x1400852c6  mov     [rsp+arg_10], r8b
0x1400852cb  push    rbp
0x1400852cc  push    rsi
0x1400852cd  push    rdi
0x1400852ce  push    r12
0x1400852d0  push    r13
0x1400852d2  sub     rsp, 50h
0x1400852d6  mov     r12d, edx
0x1400852d9  mov     rdi, rcx
0x1400852dc  cmp     edx, 800h
0x1400852e2  jb      short loc_140085307
0x1400852e4  mov     r8d, 1C2h
0x1400852ea  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x1400852f1  lea     rcx, aVidexovpioctlc; "VidExoVpIoctlCreate"
0x1400852f8  call    VidTraceErrorInternal0
0x1400852fd  mov     ebx, 0C000000Dh
0x140085302  jmp     loc_140085599
0x140085307  mov     r8, cs:ExEventObjectType
0x14008530e  xor     eax, eax
0x140085310  mov     rcx, [rsp+78h+Handle]; Handle
0x140085318  mov     ebp, eax
0x14008531a  mov     [rsp+78h+HandleInformation], rax; HandleInformation
0x14008531f  mov     r13d, eax
0x140085322  mov     [rsp+78h+arg_8], al
0x140085329  mov     r9b, 1; AccessMode
0x14008532c  mov     r8, [r8]; ObjectType
0x14008532f  mov     edx, 2; DesiredAccess
0x140085334  mov     [rsp+78h+var_30], rax
0x140085339  mov     [rsp+78h+var_38], rax
0x14008533e  lea     rax, [rsp+78h+var_38]
0x140085343  mov     [rsp+78h+Object], rax; Object
0x140085348  call    cs:__imp_ObReferenceObjectByHandle
0x14008534f  nop     dword ptr [rax+rax+00h]
0x140085354  mov     ebx, eax
0x140085356  lea     rsi, [rdi+2ED0h]
0x14008535d  mov     rax, [rsp+78h+var_38]
0x140085362  mov     [rsp+78h+var_40], rax
0x140085367  mov     [rsp+78h+var_38], rax
0x14008536c  test    ebx, ebx
0x14008536e  jns     short loc_140085398
0x140085370  mov     [rsp+78h+var_48], bpl
0x140085375  mov     r8d, 1D3h
0x14008537b  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x140085382  lea     rcx, aVidexovpioctlc; "VidExoVpIoctlCreate"
0x140085389  call    VidTraceErrorInternal0
0x14008538e  mov     rcx, [rsp+78h+var_40]
0x140085393  jmp     loc_14008551C
0x140085398  mov     rcx, rdi
0x14008539b  call    VidObjectLockAcquireExclusive
0x1400853a0  mov     eax, [rsi]
0x1400853a2  mov     [rsp+78h+var_48], 1
0x1400853a7  cmp     r12d, eax
0x1400853aa  jb      short loc_140085420
0x1400853ac  mov     ebp, eax
0x1400853ae  mov     r13d, r12d
0x1400853b1  shr     ebp, 6
0x1400853b4  shr     r13d, 6
0x1400853b8  mov     ebx, ebp
0x1400853ba  cmp     ebx, r13d
0x1400853bd  ja      short loc_140085430
0x1400853bf  mov     edx, 400h
0x1400853c4  mov     ecx, 40h ; '@'
0x1400853c9  mov     r8d, 72446456h
0x1400853cf  call    cs:__imp_ExAllocatePool2
0x1400853d6  nop     dword ptr [rax+rax+00h]
0x1400853db  mov     rcx, rax
0x1400853de  mov     edx, ebx
0x1400853e0  mov     rax, [rdi+2EC8h]
0x1400853e7  mov     [rax+rdx*8], rcx
0x1400853eb  mov     rax, [rdi+2EC8h]
0x1400853f2  cmp     qword ptr [rax+rdx*8], 0
0x1400853f7  jz      short loc_1400853FD
0x1400853f9  inc     ebx
0x1400853fb  jmp     short loc_1400853BA
0x1400853fd  mov     r8d, 1F1h
0x140085403  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x14008540a  lea     rcx, aVidexovpioctlc; "VidExoVpIoctlCreate"
0x140085411  call    VidTraceErrorInternal0
0x140085416  mov     ebx, 0C000009Ah
0x14008541b  jmp     loc_14008538E
0x140085420  mov     rcx, rdi
0x140085423  call    VidObjectLockRelease
0x140085428  mov     rcx, rdi
0x14008542b  call    VidObjectLockAcquireShared
0x140085430  mov     rax, [rdi+2EC8h]
0x140085437  mov     rdx, r12
0x14008543a  and     edx, 3Fh
0x14008543d  mov     rcx, r12
0x140085440  shr     rcx, 6
0x140085444  shl     rdx, 4
0x140085448  mov     rcx, [rax+rcx*8]
0x14008544c  add     rcx, rdx
0x14008544f  xor     eax, eax
0x140085451  mov     [rsp+78h+var_30], rcx
0x140085456  lea     edx, [rax+1]
0x140085459  lock cmpxchg [rcx], edx
0x14008545d  jz      short loc_140085482
0x14008545f  mov     r8d, 208h
0x140085465  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x14008546c  lea     rcx, aVidexovpioctlc; "VidExoVpIoctlCreate"
0x140085473  call    VidTraceErrorInternal0
0x140085478  mov     ebx, 0C0000708h
0x14008547d  jmp     loc_14008538E
0x140085482  movzx   edx, [rsp+78h+arg_10]
0x14008548a  lea     rax, [rsp+78h+var_38]
0x14008548f  mov     r9, [rsp+78h+arg_18]
0x140085497  add     rcx, 8
0x14008549b  mov     r8d, edx
0x14008549e  mov     [rsp+78h+HandleInformation], rcx; __int64
0x1400854a3  bts     r8d, 1Fh
0x1400854a8  mov     [rsp+78h+Object], rax; __int64
0x1400854ad  test    byte ptr [rdi+10h], 80h
0x1400854b1  mov     rcx, rdi; DeferredContext
0x1400854b4  cmovnz  r8d, edx
0x1400854b8  mov     edx, r12d
0x1400854bb  call    VidExoVppCreate
0x1400854c0  mov     ebx, eax
0x1400854c2  test    eax, eax
0x1400854c4  jns     short loc_1400854E9
0x1400854c6  mov     [rsp+78h+arg_8], 1
0x1400854ce  mov     r8d, 21Eh
0x1400854d4  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x1400854db  lea     rcx, aVidexovpioctlc; "VidExoVpIoctlCreate"
0x1400854e2  call    VidTraceErrorInternal0
0x1400854e7  jmp     short loc_140085517
0x1400854e9  mov     rax, [rsp+78h+var_30]
0x1400854ee  mov     dword ptr [rax], 2
0x1400854f4  mov     ecx, [rsi]
0x1400854f6  cmp     r12d, ecx
0x1400854f9  jb      short loc_14008550D
0x1400854fb  mov     eax, r13d
0x1400854fe  sub     eax, ebp
0x140085500  inc     eax
0x140085502  shl     eax, 6
0x140085505  add     eax, ecx
0x140085507  mov     [rdi+2ED0h], eax
0x14008550d  mov     [rsp+78h+arg_8], 0
0x140085515  xor     ebx, ebx
0x140085517  mov     rcx, [rsp+78h+var_38]; Object
0x14008551c  test    rcx, rcx
0x14008551f  jz      short loc_14008552D
0x140085521  call    cs:__imp_ObfDereferenceObject
0x140085528  nop     dword ptr [rax+rax+00h]
0x14008552d  cmp     [rsp+78h+var_48], 0
0x140085532  jz      short loc_140085580
0x140085534  test    ebx, ebx
0x140085536  jns     short loc_140085578
0x140085538  cmp     r12d, [rsi]
0x14008553b  jb      short loc_140085578
0x14008553d  jmp     short loc_140085573
0x14008553f  mov     rax, [rdi+2EC8h]
0x140085546  mov     esi, ebp
0x140085548  mov     rcx, [rax+rsi*8]; P
0x14008554c  test    rcx, rcx
0x14008554f  jz      short loc_140085571
0x140085551  mov     edx, 72446456h; Tag
0x140085556  call    cs:__imp_ExFreePoolWithTag
0x14008555d  nop     dword ptr [rax+rax+00h]
0x140085562  mov     rax, [rdi+2EC8h]
0x140085569  mov     qword ptr [rax+rsi*8], 0
0x140085571  inc     ebp
0x140085573  cmp     ebp, r13d
0x140085576  jbe     short loc_14008553F
0x140085578  mov     rcx, rdi
0x14008557b  call    VidObjectLockRelease
0x140085580  cmp     [rsp+78h+arg_8], 0
0x140085588  jz      short loc_140085595
0x14008558a  mov     rax, [rsp+78h+var_30]
0x14008558f  mov     dword ptr [rax], 0
0x140085595  test    ebx, ebx
0x140085597  jns     short loc_1400855C1
0x140085599  lea     rax, [rdi+290h]
0x1400855a0  mov     r9d, ebx
0x1400855a3  mov     r8d, 25Ah
0x1400855a9  mov     [rsp+78h+Object], rax
0x1400855ae  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x1400855b5  lea     rcx, aVidexovpioctlc; "VidExoVpIoctlCreate"
0x1400855bc  call    VidTraceErrorStatusPartitionInternal0
0x1400855c1  mov     eax, ebx
0x1400855c3  mov     rbx, [rsp+78h+arg_0]
0x1400855cb  add     rsp, 50h
0x1400855cf  pop     r13
0x1400855d1  pop     r12
0x1400855d3  pop     rdi
0x1400855d4  pop     rsi
0x1400855d5  pop     rbp
0x1400855d6  retn
```
