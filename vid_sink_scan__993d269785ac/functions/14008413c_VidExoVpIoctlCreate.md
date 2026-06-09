# VidExoVpIoctlCreate

- ea: `0x14008413c`
- end: `0x140084458`
- name: `VidExoVpIoctlCreate`
- size: `796`
- prototype: `__int64 __fastcall(_QWORD *DeferredContext, unsigned int, unsigned __int8, __int128 *, HANDLE Handle)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140037fd0`

## callees

- `0x140024754`
- `0x140034554`
- `0x140034584`
- `0x140034914`
- `0x140038630`
- `0x14008413c`
- `0x140084884`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400841c8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400841c8`
- `ntoskrnl!ExEventObjectType` at `0x140084187`
- `ntoskrnl!ObfDereferenceObject` at `0x1400843a1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400843a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400843d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400843d6`
- `ntoskrnl!ExAllocatePool2` at `0x14008424f`
- `ntoskrnl!ExAllocatePool2` at `0x14008424f`

## string_xrefs

- `0x140084171`: `VidExoVpIoctlCreate`
- `0x140084202`: `VidExoVpIoctlCreate`
- `0x14008428a`: `VidExoVpIoctlCreate`
- `0x1400842ec`: `VidExoVpIoctlCreate`
- `0x14008435b`: `VidExoVpIoctlCreate`
- `0x140084435`: `VidExoVpIoctlCreate`

## pseudocode

```c
__int64 __fastcall VidExoVpIoctlCreate(
        char *DeferredContext,
        unsigned int a2,
        unsigned __int8 a3,
        __int128 *a4,
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
      (__int64)(DeferredContext + 656));
    return (unsigned int)v7;
  }
  v8 = 0;
  v9 = 0;
  v22 = 0;
  v21 = 0;
  Object = 0;
  v7 = ObReferenceObjectByHandle(Handle, 2u, (POBJECT_TYPE)ExEventObjectType, 1, &Object, 0);
  v10 = (unsigned int *)(DeferredContext + 11984);
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
      *(_QWORD *)(*((_QWORD *)DeferredContext + 1497) + 8LL * i) = ExAllocatePool2(64, 1024, 1917084758);
      if ( !*(_QWORD *)(*((_QWORD *)DeferredContext + 1497) + 8LL * i) )
      {
        VidTraceErrorInternal0("VidExoVpIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\videxovp.c", 497);
        v7 = -1073741670;
        goto LABEL_5;
      }
    }
  }
  v14 = 16 * (v5 & 0x3F) + *(_QWORD *)(*((_QWORD *)DeferredContext + 1497) + 8 * (v5 >> 6));
  v21 = (_DWORD *)v14;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)v14, 1, 0) )
  {
    VidTraceErrorInternal0("VidExoVpIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\videxovp.c", 520);
    v7 = -1073740024;
    goto LABEL_5;
  }
  v15 = a3 | 0x80000000;
  if ( DeferredContext[16] < 0 )
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
        v16 = *(void **)(*((_QWORD *)DeferredContext + 1497) + 8LL * v8);
        if ( v16 )
        {
          ExFreePoolWithTag(v16, 0x72446456u);
          *(_QWORD *)(*((_QWORD *)DeferredContext + 1497) + 8LL * v8) = 0;
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
0x14008413c  mov     [rsp+arg_0], rbx
0x140084141  mov     [rsp+arg_18], r9
0x140084146  mov     [rsp+arg_10], r8b
0x14008414b  push    rbp
0x14008414c  push    rsi
0x14008414d  push    rdi
0x14008414e  push    r12
0x140084150  push    r13
0x140084152  sub     rsp, 50h
0x140084156  mov     r12d, edx
0x140084159  mov     rdi, rcx
0x14008415c  cmp     edx, 800h
0x140084162  jb      short loc_140084187
0x140084164  mov     r8d, 1C2h
0x14008416a  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x140084171  lea     rcx, aVidexovpioctlc; "VidExoVpIoctlCreate"
0x140084178  call    VidTraceErrorInternal0
0x14008417d  mov     ebx, 0C000000Dh
0x140084182  jmp     loc_140084419
0x140084187  mov     r8, cs:ExEventObjectType
0x14008418e  xor     eax, eax
0x140084190  mov     rcx, [rsp+78h+Handle]; Handle
0x140084198  mov     ebp, eax
0x14008419a  mov     [rsp+78h+HandleInformation], rax; HandleInformation
0x14008419f  mov     r13d, eax
0x1400841a2  mov     [rsp+78h+arg_8], al
0x1400841a9  mov     r9b, 1; AccessMode
0x1400841ac  mov     r8, [r8]; ObjectType
0x1400841af  mov     edx, 2; DesiredAccess
0x1400841b4  mov     [rsp+78h+var_30], rax
0x1400841b9  mov     [rsp+78h+var_38], rax
0x1400841be  lea     rax, [rsp+78h+var_38]
0x1400841c3  mov     [rsp+78h+Object], rax; Object
0x1400841c8  call    cs:__imp_ObReferenceObjectByHandle
0x1400841cf  nop     dword ptr [rax+rax+00h]
0x1400841d4  mov     ebx, eax
0x1400841d6  lea     rsi, [rdi+2ED0h]
0x1400841dd  mov     rax, [rsp+78h+var_38]
0x1400841e2  mov     [rsp+78h+var_40], rax
0x1400841e7  mov     [rsp+78h+var_38], rax
0x1400841ec  test    ebx, ebx
0x1400841ee  jns     short loc_140084218
0x1400841f0  mov     [rsp+78h+var_48], bpl
0x1400841f5  mov     r8d, 1D3h
0x1400841fb  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x140084202  lea     rcx, aVidexovpioctlc; "VidExoVpIoctlCreate"
0x140084209  call    VidTraceErrorInternal0
0x14008420e  mov     rcx, [rsp+78h+var_40]
0x140084213  jmp     loc_14008439C
0x140084218  mov     rcx, rdi
0x14008421b  call    VidObjectLockAcquireExclusive
0x140084220  mov     eax, [rsi]
0x140084222  mov     [rsp+78h+var_48], 1
0x140084227  cmp     r12d, eax
0x14008422a  jb      short loc_1400842A0
0x14008422c  mov     ebp, eax
0x14008422e  mov     r13d, r12d
0x140084231  shr     ebp, 6
0x140084234  shr     r13d, 6
0x140084238  mov     ebx, ebp
0x14008423a  cmp     ebx, r13d
0x14008423d  ja      short loc_1400842B0
0x14008423f  mov     edx, 400h
0x140084244  mov     ecx, 40h ; '@'
0x140084249  mov     r8d, 72446456h
0x14008424f  call    cs:__imp_ExAllocatePool2
0x140084256  nop     dword ptr [rax+rax+00h]
0x14008425b  mov     rcx, rax
0x14008425e  mov     edx, ebx
0x140084260  mov     rax, [rdi+2EC8h]
0x140084267  mov     [rax+rdx*8], rcx
0x14008426b  mov     rax, [rdi+2EC8h]
0x140084272  cmp     qword ptr [rax+rdx*8], 0
0x140084277  jz      short loc_14008427D
0x140084279  inc     ebx
0x14008427b  jmp     short loc_14008423A
0x14008427d  mov     r8d, 1F1h
0x140084283  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x14008428a  lea     rcx, aVidexovpioctlc; "VidExoVpIoctlCreate"
0x140084291  call    VidTraceErrorInternal0
0x140084296  mov     ebx, 0C000009Ah
0x14008429b  jmp     loc_14008420E
0x1400842a0  mov     rcx, rdi
0x1400842a3  call    VidObjectLockRelease
0x1400842a8  mov     rcx, rdi
0x1400842ab  call    VidObjectLockAcquireShared
0x1400842b0  mov     rax, [rdi+2EC8h]
0x1400842b7  mov     rdx, r12
0x1400842ba  and     edx, 3Fh
0x1400842bd  mov     rcx, r12
0x1400842c0  shr     rcx, 6
0x1400842c4  shl     rdx, 4
0x1400842c8  mov     rcx, [rax+rcx*8]
0x1400842cc  add     rcx, rdx
0x1400842cf  xor     eax, eax
0x1400842d1  mov     [rsp+78h+var_30], rcx
0x1400842d6  lea     edx, [rax+1]
0x1400842d9  lock cmpxchg [rcx], edx
0x1400842dd  jz      short loc_140084302
0x1400842df  mov     r8d, 208h
0x1400842e5  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x1400842ec  lea     rcx, aVidexovpioctlc; "VidExoVpIoctlCreate"
0x1400842f3  call    VidTraceErrorInternal0
0x1400842f8  mov     ebx, 0C0000708h
0x1400842fd  jmp     loc_14008420E
0x140084302  movzx   edx, [rsp+78h+arg_10]
0x14008430a  lea     rax, [rsp+78h+var_38]
0x14008430f  mov     r9, [rsp+78h+arg_18]
0x140084317  add     rcx, 8
0x14008431b  mov     r8d, edx
0x14008431e  mov     [rsp+78h+HandleInformation], rcx; __int64
0x140084323  bts     r8d, 1Fh
0x140084328  mov     [rsp+78h+Object], rax; __int64
0x14008432d  test    byte ptr [rdi+10h], 80h
0x140084331  mov     rcx, rdi; DeferredContext
0x140084334  cmovnz  r8d, edx
0x140084338  mov     edx, r12d
0x14008433b  call    VidExoVppCreate
0x140084340  mov     ebx, eax
0x140084342  test    eax, eax
0x140084344  jns     short loc_140084369
0x140084346  mov     [rsp+78h+arg_8], 1
0x14008434e  mov     r8d, 21Eh
0x140084354  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x14008435b  lea     rcx, aVidexovpioctlc; "VidExoVpIoctlCreate"
0x140084362  call    VidTraceErrorInternal0
0x140084367  jmp     short loc_140084397
0x140084369  mov     rax, [rsp+78h+var_30]
0x14008436e  mov     dword ptr [rax], 2
0x140084374  mov     ecx, [rsi]
0x140084376  cmp     r12d, ecx
0x140084379  jb      short loc_14008438D
0x14008437b  mov     eax, r13d
0x14008437e  sub     eax, ebp
0x140084380  inc     eax
0x140084382  shl     eax, 6
0x140084385  add     eax, ecx
0x140084387  mov     [rdi+2ED0h], eax
0x14008438d  mov     [rsp+78h+arg_8], 0
0x140084395  xor     ebx, ebx
0x140084397  mov     rcx, [rsp+78h+var_38]; Object
0x14008439c  test    rcx, rcx
0x14008439f  jz      short loc_1400843AD
0x1400843a1  call    cs:__imp_ObfDereferenceObject
0x1400843a8  nop     dword ptr [rax+rax+00h]
0x1400843ad  cmp     [rsp+78h+var_48], 0
0x1400843b2  jz      short loc_140084400
0x1400843b4  test    ebx, ebx
0x1400843b6  jns     short loc_1400843F8
0x1400843b8  cmp     r12d, [rsi]
0x1400843bb  jb      short loc_1400843F8
0x1400843bd  jmp     short loc_1400843F3
0x1400843bf  mov     rax, [rdi+2EC8h]
0x1400843c6  mov     esi, ebp
0x1400843c8  mov     rcx, [rax+rsi*8]; P
0x1400843cc  test    rcx, rcx
0x1400843cf  jz      short loc_1400843F1
0x1400843d1  mov     edx, 72446456h; Tag
0x1400843d6  call    cs:__imp_ExFreePoolWithTag
0x1400843dd  nop     dword ptr [rax+rax+00h]
0x1400843e2  mov     rax, [rdi+2EC8h]
0x1400843e9  mov     qword ptr [rax+rsi*8], 0
0x1400843f1  inc     ebp
0x1400843f3  cmp     ebp, r13d
0x1400843f6  jbe     short loc_1400843BF
0x1400843f8  mov     rcx, rdi
0x1400843fb  call    VidObjectLockRelease
0x140084400  cmp     [rsp+78h+arg_8], 0
0x140084408  jz      short loc_140084415
0x14008440a  mov     rax, [rsp+78h+var_30]
0x14008440f  mov     dword ptr [rax], 0
0x140084415  test    ebx, ebx
0x140084417  jns     short loc_140084441
0x140084419  lea     rax, [rdi+290h]
0x140084420  mov     r9d, ebx
0x140084423  mov     r8d, 25Ah
0x140084429  mov     [rsp+78h+Object], rax
0x14008442e  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x140084435  lea     rcx, aVidexovpioctlc; "VidExoVpIoctlCreate"
0x14008443c  call    VidTraceErrorStatusPartitionInternal0
0x140084441  mov     eax, ebx
0x140084443  mov     rbx, [rsp+78h+arg_0]
0x14008444b  add     rsp, 50h
0x14008444f  pop     r13
0x140084451  pop     r12
0x140084453  pop     rdi
0x140084454  pop     rsi
0x140084455  pop     rbp
0x140084456  retn
```
