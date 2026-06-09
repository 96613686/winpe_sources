# VMX_CONFIG_COPY::ReadSectors(unsigned __int64,ulong,uchar * *,ulong *)

- ea: `0x1400463d4`
- end: `0x1400465a9`
- name: `?ReadSectors@VMX_CONFIG_COPY@@QEAAJ_KKPEAPEAEPEAK@Z`
- size: `469`
- prototype: `__int64 __fastcall(VMX_CONFIG_COPY *this, unsigned __int64, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140045ddc`
- `0x1400462ec`
- `0x140059780`
- `0x140059c38`

## callees

- `0x14001bb80`
- `0x1400463d4`
- `0x1400465b0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140046448`
- `ntoskrnl!ExAllocatePool2` at `0x140046448`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046510`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004655e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046510`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004655e`

## pseudocode

```c
__int64 __fastcall VMX_CONFIG_COPY::ReadSectors(
        VMX_CONFIG_COPY *this,
        unsigned __int64 a2,
        unsigned int a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  unsigned __int8 *Pool2; // rdi
  unsigned __int64 v9; // rcx
  unsigned int v11; // r12d
  __int64 *i; // r15
  unsigned __int64 v13; // r8
  unsigned __int64 v14; // rbx
  unsigned int v15; // ebx
  int Sectors; // r13d
  unsigned __int8 *v17; // [rsp+20h] [rbp-58h]
  void *Src; // [rsp+28h] [rbp-50h] BYREF
  size_t v19; // [rsp+30h] [rbp-48h]
  int v20; // [rsp+80h] [rbp+8h]

  Pool2 = *a4;
  Src = 0;
  *a5 = 0;
  v20 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 16LL) + 36LL);
  if ( !Pool2 )
  {
    v9 = a3 * (unsigned __int64)*(unsigned int *)(*(_QWORD *)(*(_QWORD *)this + 16LL) + 36LL);
    if ( v9 > 0xFFFFFFFF )
      return 3221225621LL;
    Pool2 = (unsigned __int8 *)ExAllocatePool2(258, (unsigned int)v9, 1967287638);
    if ( !Pool2 )
      return 3221225626LL;
  }
  v11 = a3;
  v17 = Pool2;
  for ( i = *(__int64 **)(*((_QWORD *)this + 1) + 16LL); ; i = (__int64 *)*i )
  {
    if ( i == (__int64 *)(*((_QWORD *)this + 1) + 16LL) )
    {
LABEL_21:
      *a4 = Pool2;
      *a5 = a3 - v11;
      return 0;
    }
    v13 = *((unsigned int *)i + 11);
    if ( a2 >= v13 )
    {
      v14 = v13 + i[4];
      if ( a2 < v14 )
        break;
    }
LABEL_15:
    ;
  }
  if ( v11 > v14 - a2 )
    v15 = v14 - a2;
  else
    v15 = v11;
  Sectors = VMX_PHYSICAL_DISK::ReadSectors(
              *(VMX_PHYSICAL_DISK **)this,
              a2 + i[3] + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)this + 88LL) + 152LL) - v13,
              v15,
              (unsigned __int8 **)&Src);
  if ( Sectors >= 0 )
  {
    v19 = v15 * v20;
    memmove(v17, Src, v19);
    ExFreePoolWithTag(Src, 0);
    v11 -= v15;
    if ( !v11 )
      goto LABEL_21;
    v17 += v19;
    a2 += v15;
    goto LABEL_15;
  }
  *((_BYTE *)this + 19) = 0;
  if ( Sectors != -1073741670 )
    *((_BYTE *)this + 17) = 1;
  if ( !*a4 )
    ExFreePoolWithTag(Pool2, 0);
  return (unsigned int)Sectors;
}

```

## disassembly

```asm
0x1400463d4  mov     [rsp+arg_8], rbx
0x1400463d9  mov     [rsp+arg_18], r9
0x1400463de  push    rbp
0x1400463df  push    rsi
0x1400463e0  push    rdi
0x1400463e1  push    r12
0x1400463e3  push    r13
0x1400463e5  push    r14
0x1400463e7  push    r15
0x1400463e9  sub     rsp, 40h
0x1400463ed  mov     rax, [rsp+78h+arg_20]
0x1400463f5  mov     rbp, rdx
0x1400463f8  mov     rdi, [r9]
0x1400463fb  mov     r14, rcx
0x1400463fe  mov     esi, r8d
0x140046401  mov     [rsp+78h+Src], 0
0x14004640a  mov     dword ptr [rax], 0
0x140046410  mov     rax, [rcx]
0x140046413  mov     r10, [rax+10h]
0x140046417  mov     eax, [r10+24h]
0x14004641b  mov     [rsp+78h+arg_0], eax
0x140046422  test    rdi, rdi
0x140046425  jnz     short loc_140046466
0x140046427  mov     ecx, eax
0x140046429  mov     eax, 0FFFFFFFFh
0x14004642e  imul    rcx, rsi
0x140046432  cmp     rcx, rax
0x140046435  ja      loc_14004658B
0x14004643b  mov     edx, ecx
0x14004643d  mov     r8d, 75426D56h
0x140046443  mov     ecx, 102h
0x140046448  call    cs:__imp_ExAllocatePool2
0x14004644f  nop     dword ptr [rax+rax+00h]
0x140046454  mov     rdi, rax
0x140046457  test    rax, rax
0x14004645a  jnz     short loc_140046466
0x14004645c  mov     eax, 0C000009Ah
0x140046461  jmp     loc_140046590
0x140046466  mov     rax, [r14+8]
0x14004646a  mov     r12d, esi
0x14004646d  mov     [rsp+78h+var_58], rdi
0x140046472  mov     r15, [rax+10h]
0x140046476  mov     rax, [r14+8]
0x14004647a  add     rax, 10h
0x14004647e  cmp     r15, rax
0x140046481  jz      loc_14004656F
0x140046487  mov     r8d, [r15+2Ch]
0x14004648b  cmp     rbp, r8
0x14004648e  jb      loc_140046530
0x140046494  mov     rbx, [r15+20h]
0x140046498  add     rbx, r8
0x14004649b  cmp     rbp, rbx
0x14004649e  jnb     loc_140046530
0x1400464a4  mov     rcx, rbx
0x1400464a7  mov     eax, r12d
0x1400464aa  sub     rcx, rbp
0x1400464ad  cmp     rax, rcx
0x1400464b0  ja      short loc_1400464B7
0x1400464b2  mov     ebx, r12d
0x1400464b5  jmp     short loc_1400464B9
0x1400464b7  sub     ebx, ebp
0x1400464b9  mov     rcx, [r14]; this
0x1400464bc  lea     r9, [rsp+78h+Src]; unsigned __int8 **
0x1400464c1  mov     rax, [rcx+58h]
0x1400464c5  mov     rdx, [rax+98h]
0x1400464cc  add     rdx, [r15+18h]
0x1400464d0  sub     rdx, r8
0x1400464d3  mov     r8d, ebx; unsigned int
0x1400464d6  add     rdx, rbp; unsigned __int64
0x1400464d9  call    ?ReadSectors@VMX_PHYSICAL_DISK@@QEAAJ_KKPEAPEAE@Z; VMX_PHYSICAL_DISK::ReadSectors(unsigned __int64,ulong,uchar * *)
0x1400464de  mov     r13d, eax
0x1400464e1  test    eax, eax
0x1400464e3  js      short loc_140046538
0x1400464e5  mov     eax, [rsp+78h+arg_0]
0x1400464ec  mov     r13, [rsp+78h+var_58]
0x1400464f1  mov     rdx, [rsp+78h+Src]; Src
0x1400464f6  mov     rcx, r13; void *
0x1400464f9  imul    eax, ebx
0x1400464fc  mov     r8d, eax; Size
0x1400464ff  mov     [rsp+78h+var_48], rax
0x140046504  call    memmove
0x140046509  mov     rcx, [rsp+78h+Src]; P
0x14004650e  xor     edx, edx; Tag
0x140046510  call    cs:__imp_ExFreePoolWithTag
0x140046517  nop     dword ptr [rax+rax+00h]
0x14004651c  sub     r12d, ebx
0x14004651f  jz      short loc_14004656F
0x140046521  add     r13, [rsp+78h+var_48]
0x140046526  mov     eax, ebx
0x140046528  mov     [rsp+78h+var_58], r13
0x14004652d  add     rbp, rax
0x140046530  mov     r15, [r15]
0x140046533  jmp     loc_140046476
0x140046538  mov     byte ptr [r14+13h], 0
0x14004653d  cmp     r13d, 0C000009Ah
0x140046544  jz      short loc_14004654B
0x140046546  mov     byte ptr [r14+11h], 1
0x14004654b  mov     rax, [rsp+78h+arg_18]
0x140046553  cmp     qword ptr [rax], 0
0x140046557  jnz     short loc_14004656A
0x140046559  xor     edx, edx; Tag
0x14004655b  mov     rcx, rdi; P
0x14004655e  call    cs:__imp_ExFreePoolWithTag
0x140046565  nop     dword ptr [rax+rax+00h]
0x14004656a  mov     eax, r13d
0x14004656d  jmp     short loc_140046590
0x14004656f  mov     rax, [rsp+78h+arg_18]
0x140046577  sub     esi, r12d
0x14004657a  mov     [rax], rdi
0x14004657d  mov     rax, [rsp+78h+arg_20]
0x140046585  mov     [rax], esi
0x140046587  xor     eax, eax
0x140046589  jmp     short loc_140046590
0x14004658b  mov     eax, 0C0000095h
0x140046590  mov     rbx, [rsp+78h+arg_8]
0x140046598  add     rsp, 40h
0x14004659c  pop     r15
0x14004659e  pop     r14
0x1400465a0  pop     r13
0x1400465a2  pop     r12
0x1400465a4  pop     rdi
0x1400465a5  pop     rsi
0x1400465a6  pop     rbp
0x1400465a7  retn
```
