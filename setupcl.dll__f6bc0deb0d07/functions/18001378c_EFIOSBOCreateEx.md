# EFIOSBOCreateEx

- ea: `0x18001378c`
- end: `0x180013b08`
- name: `EFIOSBOCreateEx`
- size: `892`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000f4e4`

## callees

- `0x180012c90`
- `0x180012dfc`
- `0x18001378c`
- `0x180013b10`
- `0x1800142b4`
- `0x180014304`
- `0x180014354`
- `0x1800143a4`
- `0x1800143f4`
- `0x180014784`
- `0x1800179c5`
- `0x180018010`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x1800137be`
- `ntdll!RtlAdjustPrivilege` at `0x1800137be`

## pseudocode

```c
__int64 __fastcall EFIOSBOCreateEx(int a1)
{
  __int64 v1; // rdi
  void *v2; // rax
  int v3; // eax
  int v4; // r8d
  __int64 (__fastcall *v5)(_QWORD); // rax
  __int64 (__fastcall *v6)(_QWORD); // rax
  _DWORD *v7; // rsi
  __int64 v8; // rbx
  _QWORD *v9; // r14
  __int64 i; // rcx
  _QWORD *v11; // rax
  int v12; // eax
  void *v13; // rax
  void *v14; // r15
  _DWORD *v15; // rsi
  int **v16; // r14
  int v17; // edx
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rax
  unsigned int *v21; // rsi
  int v22; // r14d
  _QWORD *v23; // rax
  __int64 v24; // rcx
  int v25; // eax
  void *v26; // rax
  void *v27; // rsi
  int OldValue; // [rsp+50h] [rbp+30h] BYREF
  size_t Size; // [rsp+58h] [rbp+38h] BYREF

  OldValue = a1;
  LOBYTE(OldValue) = 0;
  if ( !PriviledgeSet )
  {
    v1 = 0;
    if ( RtlAdjustPrivilege(0x16u, 1u, 0, (PBOOLEAN)&OldValue) < 0 )
      return v1;
  }
  PriviledgeSet = 1;
  if ( !AllocRoutine )
    return 0;
  v2 = (void *)AllocRoutine(168);
  v1 = (__int64)v2;
  if ( !v2 )
    return v1;
  LODWORD(Size) = 0;
  memset_0(v2, 0, 0xA8u);
  *(_QWORD *)(v1 + 96) = EFIOSBODelete;
  *(_QWORD *)(v1 + 104) = EFIOSBOFlush;
  *(_QWORD *)(v1 + 112) = EFIOSBOAddNewBootEntry;
  *(_QWORD *)(v1 + 120) = OSBODeleteBootEntry;
  *(_QWORD *)(v1 + 128) = EFIDEAddNewDriverEntry;
  *(_QWORD *)(v1 + 136) = OSBODeleteDriverEntry;
  v3 = EfiQueryBootOptions(0, &Size);
  if ( (_DWORD)Size )
  {
    v5 = AllocRoutine;
    if ( AllocRoutine )
      v5 = (__int64 (__fastcall *)(_QWORD))AllocRoutine((unsigned int)Size);
    *(_QWORD *)(v1 + 144) = v5;
    if ( !v5 || (int)EfiQueryBootOptions(v5, &Size) < 0 )
      goto LABEL_56;
    *(_DWORD *)(v1 + 8) = *(_DWORD *)(*(_QWORD *)(v1 + 144) + 8LL);
    LODWORD(Size) = 0;
    v3 = EfiEnumerateBootEntries(0, &Size);
    if ( (_DWORD)Size )
    {
      v6 = AllocRoutine;
      if ( AllocRoutine )
        v6 = (__int64 (__fastcall *)(_QWORD))AllocRoutine((unsigned int)Size);
      *(_QWORD *)(v1 + 152) = v6;
      if ( !v6 )
        goto LABEL_56;
      v3 = EfiEnumerateBootEntries(v6, &Size);
    }
  }
  if ( v3 < 0 )
  {
LABEL_56:
    v8 = v1;
    goto LABEL_57;
  }
  v7 = *(_DWORD **)(v1 + 152);
  v8 = v1;
  if ( v7 )
  {
    v9 = 0;
LABEL_18:
    for ( i = (__int64)(v7 + 1); i; i = 0 )
    {
      v11 = EFIOSBECreate(i, v1, v4);
      if ( !v11 )
        goto LABEL_57;
      ++*(_DWORD *)(v1 + 40);
      v11[392] = v1;
      if ( !*(_QWORD *)(v1 + 24) )
        *(_QWORD *)(v1 + 24) = v11;
      if ( v9 )
        v9[393] = v11;
      v9 = v11;
      if ( *v7 )
      {
        v7 = (_DWORD *)((char *)v7 + (unsigned int)*v7);
        goto LABEL_18;
      }
    }
  }
  LODWORD(Size) = 0;
  v12 = EfiQueryBootEntryOrder(0, &Size);
  if ( (_DWORD)Size )
  {
    if ( !AllocRoutine )
      goto LABEL_57;
    v13 = (void *)AllocRoutine(4LL * (unsigned int)Size);
    v14 = v13;
    if ( !v13 )
      goto LABEL_57;
    memset_0(v13, 0, (unsigned int)Size);
    v15 = (_DWORD *)(v1 + 56);
    *(_DWORD *)(v1 + 56) = Size;
    v16 = (int **)(v1 + 48);
    *(_QWORD *)(v1 + 48) = v14;
    v12 = EfiQueryBootEntryOrder(v14, &Size);
  }
  else
  {
    v15 = (_DWORD *)(v1 + 56);
    v16 = (int **)(v1 + 48);
  }
  if ( v12 < 0 )
    goto LABEL_57;
  v17 = -1;
  if ( *v15 )
    v17 = **v16;
  if ( v17 == -1 )
    v18 = 0;
  else
    v18 = OSBOFindBootEntry(v1);
  *(_QWORD *)(v1 + 32) = v18;
  v19 = EfiEnumerateDriverEntries(0, &Size);
  if ( v19 < 0 )
  {
    if ( v19 != -1073741789 )
      goto LABEL_57;
    if ( !AllocRoutine )
      goto LABEL_57;
    v20 = AllocRoutine((unsigned int)Size);
    v21 = (unsigned int *)v20;
    if ( !v20 || (int)EfiEnumerateDriverEntries(v20, &Size) < 0 )
      goto LABEL_57;
    *(_QWORD *)(v1 + 160) = v21;
    do
    {
      v22 = *v21;
      v23 = EFIDECreateDriverEntry(v21, v1);
      if ( v23 )
      {
        v24 = *(_QWORD *)(v1 + 64);
        if ( v24 )
          v23[262] = v24;
        *(_QWORD *)(v1 + 64) = v23;
        ++*(_DWORD *)(v1 + 72);
      }
      v21 = (unsigned int *)((char *)v21 + *v21);
    }
    while ( v22 );
  }
  LODWORD(Size) = 0;
  v25 = EfiQueryDriverEntryOrder(0, &Size);
  if ( (_DWORD)Size )
  {
    if ( !AllocRoutine )
      goto LABEL_57;
    v26 = (void *)AllocRoutine(4LL * (unsigned int)Size);
    v27 = v26;
    if ( !v26 )
      goto LABEL_57;
    memset_0(v26, 0, (unsigned int)Size);
    *(_DWORD *)(v1 + 88) = Size;
    *(_QWORD *)(v1 + 80) = v27;
    v25 = EfiQueryDriverEntryOrder(v27, &Size);
  }
  if ( v25 < 0 )
  {
LABEL_57:
    EFIOSBODelete(v8);
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x18001378c  mov     [rsp-28h+arg_10], rbx
0x180013791  mov     [rsp-28h+OldValue], ecx
0x180013795  push    rbp
0x180013796  push    rsi
0x180013797  push    rdi
0x180013798  push    r14
0x18001379a  push    r15
0x18001379c  mov     rbp, rsp
0x18001379f  sub     rsp, 20h
0x1800137a3  cmp     cs:PriviledgeSet, 0
0x1800137aa  mov     byte ptr [rbp+OldValue], 0
0x1800137ae  jnz     short loc_1800137CC
0x1800137b0  xor     edi, edi
0x1800137b2  lea     r9, [rbp+OldValue]; OldValue
0x1800137b6  xor     r8d, r8d; ForThread
0x1800137b9  mov     dl, 1; NewValue
0x1800137bb  lea     ecx, [rdi+16h]; Privilege
0x1800137be  call    cs:__imp_RtlAdjustPrivilege
0x1800137c4  test    eax, eax
0x1800137c6  js      loc_180013AF4
0x1800137cc  mov     rax, cs:AllocRoutine
0x1800137d3  mov     cs:PriviledgeSet, 1
0x1800137da  test    rax, rax
0x1800137dd  jz      loc_180013AF2
0x1800137e3  mov     ebx, 0A8h
0x1800137e8  mov     ecx, ebx
0x1800137ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137ef  mov     rdi, rax
0x1800137f2  test    rax, rax
0x1800137f5  jz      loc_180013AF4
0x1800137fb  mov     r8d, ebx; Size
0x1800137fe  mov     dword ptr [rbp+Size], 0
0x180013805  xor     edx, edx; Val
0x180013807  mov     rcx, rax; void *
0x18001380a  call    memset_0
0x18001380f  lea     rax, EFIOSBODelete
0x180013816  xor     ecx, ecx
0x180013818  mov     [rdi+60h], rax
0x18001381c  lea     rdx, [rbp+Size]
0x180013820  lea     rax, EFIOSBOFlush
0x180013827  mov     [rdi+68h], rax
0x18001382b  lea     rax, EFIOSBOAddNewBootEntry
0x180013832  mov     [rdi+70h], rax
0x180013836  lea     rax, OSBODeleteBootEntry
0x18001383d  mov     [rdi+78h], rax
0x180013841  lea     rax, EFIDEAddNewDriverEntry
0x180013848  mov     [rdi+80h], rax
0x18001384f  lea     rax, OSBODeleteDriverEntry
0x180013856  mov     [rdi+88h], rax
0x18001385d  call    EfiQueryBootOptions
0x180013862  mov     ecx, dword ptr [rbp+Size]
0x180013865  test    ecx, ecx
0x180013867  jz      loc_1800138F5
0x18001386d  mov     rax, cs:AllocRoutine
0x180013874  test    rax, rax
0x180013877  jz      short loc_18001387E
0x180013879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001387e  mov     [rdi+90h], rax
0x180013885  test    rax, rax
0x180013888  jz      loc_180013AE7
0x18001388e  lea     rdx, [rbp+Size]
0x180013892  mov     rcx, rax
0x180013895  call    EfiQueryBootOptions
0x18001389a  test    eax, eax
0x18001389c  js      loc_180013AE7
0x1800138a2  mov     rax, [rdi+90h]
0x1800138a9  lea     rdx, [rbp+Size]
0x1800138ad  mov     ecx, [rax+8]
0x1800138b0  mov     [rdi+8], ecx
0x1800138b3  xor     ecx, ecx
0x1800138b5  mov     dword ptr [rbp+Size], 0
0x1800138bc  call    EfiEnumerateBootEntries
0x1800138c1  mov     ecx, dword ptr [rbp+Size]
0x1800138c4  test    ecx, ecx
0x1800138c6  jz      short loc_1800138F5
0x1800138c8  mov     rax, cs:AllocRoutine
0x1800138cf  test    rax, rax
0x1800138d2  jz      short loc_1800138D9
0x1800138d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138d9  mov     [rdi+98h], rax
0x1800138e0  test    rax, rax
0x1800138e3  jz      loc_180013AE7
0x1800138e9  lea     rdx, [rbp+Size]
0x1800138ed  mov     rcx, rax
0x1800138f0  call    EfiEnumerateBootEntries
0x1800138f5  test    eax, eax
0x1800138f7  js      loc_180013AE7
0x1800138fd  mov     rsi, [rdi+98h]
0x180013904  mov     rbx, rdi
0x180013907  test    rsi, rsi
0x18001390a  jz      short loc_18001395D
0x18001390c  xor     r14d, r14d
0x18001390f  lea     rcx, [rsi+4]
0x180013913  test    rcx, rcx
0x180013916  jz      short loc_18001395D
0x180013918  mov     rdx, rbx
0x18001391b  call    EFIOSBECreate
0x180013920  test    rax, rax
0x180013923  jz      loc_180013AEA
0x180013929  inc     dword ptr [rdi+28h]
0x18001392c  mov     [rax+0C40h], rbx
0x180013933  cmp     qword ptr [rdi+18h], 0
0x180013938  jnz     short loc_18001393E
0x18001393a  mov     [rdi+18h], rax
0x18001393e  test    r14, r14
0x180013941  jz      short loc_18001394A
0x180013943  mov     [r14+0C48h], rax
0x18001394a  cmp     dword ptr [rsi], 0
0x18001394d  mov     r14, rax
0x180013950  jz      short loc_180013959
0x180013952  mov     eax, [rsi]
0x180013954  add     rsi, rax
0x180013957  jmp     short loc_18001390F
0x180013959  xor     ecx, ecx
0x18001395b  jmp     short loc_180013913
0x18001395d  lea     rdx, [rbp+Size]
0x180013961  mov     dword ptr [rbp+Size], 0
0x180013968  xor     ecx, ecx
0x18001396a  call    EfiQueryBootEntryOrder
0x18001396f  mov     ecx, dword ptr [rbp+Size]
0x180013972  test    ecx, ecx
0x180013974  jz      short loc_1800139C7
0x180013976  mov     rax, cs:AllocRoutine
0x18001397d  test    rax, rax
0x180013980  jz      loc_180013AEA
0x180013986  shl     rcx, 2
0x18001398a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001398f  mov     r15, rax
0x180013992  test    rax, rax
0x180013995  jz      loc_180013AEA
0x18001399b  mov     r8d, dword ptr [rbp+Size]; Size
0x18001399f  xor     edx, edx; Val
0x1800139a1  mov     rcx, rax; void *
0x1800139a4  call    memset_0
0x1800139a9  mov     ecx, dword ptr [rbp+Size]
0x1800139ac  lea     rsi, [rbx+38h]
0x1800139b0  mov     [rsi], ecx
0x1800139b2  lea     r14, [rbx+30h]
0x1800139b6  mov     rcx, r15
0x1800139b9  mov     [r14], r15
0x1800139bc  lea     rdx, [rbp+Size]
0x1800139c0  call    EfiQueryBootEntryOrder
0x1800139c5  jmp     short loc_1800139CF
0x1800139c7  lea     rsi, [rdi+38h]
0x1800139cb  lea     r14, [rdi+30h]
0x1800139cf  test    eax, eax
0x1800139d1  js      loc_180013AEA
0x1800139d7  or      ecx, 0FFFFFFFFh
0x1800139da  cmp     dword ptr [rsi], 0
0x1800139dd  mov     edx, ecx
0x1800139df  jbe     short loc_1800139E6
0x1800139e1  mov     rax, [r14]
0x1800139e4  mov     edx, [rax]
0x1800139e6  cmp     edx, ecx
0x1800139e8  jz      short loc_1800139F4
0x1800139ea  mov     rcx, rbx
0x1800139ed  call    OSBOFindBootEntry
0x1800139f2  jmp     short loc_1800139F6
0x1800139f4  xor     eax, eax
0x1800139f6  lea     rdx, [rbp+Size]
0x1800139fa  mov     [rbx+20h], rax
0x1800139fe  xor     ecx, ecx
0x180013a00  call    EfiEnumerateDriverEntries
0x180013a05  test    eax, eax
0x180013a07  jns     short loc_180013A87
0x180013a09  cmp     eax, 0C0000023h
0x180013a0e  jnz     loc_180013AEA
0x180013a14  mov     rax, cs:AllocRoutine
0x180013a1b  test    rax, rax
0x180013a1e  jz      loc_180013AEA
0x180013a24  mov     ecx, dword ptr [rbp+Size]
0x180013a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a2c  mov     rsi, rax
0x180013a2f  test    rax, rax
0x180013a32  jz      loc_180013AEA
0x180013a38  lea     rdx, [rbp+Size]
0x180013a3c  mov     rcx, rax
0x180013a3f  call    EfiEnumerateDriverEntries
0x180013a44  test    eax, eax
0x180013a46  js      loc_180013AEA
0x180013a4c  mov     [rbx+0A0h], rsi
0x180013a53  mov     r14d, [rsi]
0x180013a56  mov     rdx, rbx
0x180013a59  mov     rcx, rsi
0x180013a5c  call    EFIDECreateDriverEntry
0x180013a61  test    rax, rax
0x180013a64  jz      short loc_180013A7D
0x180013a66  mov     rcx, [rbx+40h]
0x180013a6a  test    rcx, rcx
0x180013a6d  jz      short loc_180013A76
0x180013a6f  mov     [rax+830h], rcx
0x180013a76  mov     [rbx+40h], rax
0x180013a7a  inc     dword ptr [rbx+48h]
0x180013a7d  mov     eax, [rsi]
0x180013a7f  add     rsi, rax
0x180013a82  test    r14d, r14d
0x180013a85  jnz     short loc_180013A53
0x180013a87  lea     rdx, [rbp+Size]
0x180013a8b  mov     dword ptr [rbp+Size], 0
0x180013a92  xor     ecx, ecx
0x180013a94  call    EfiQueryDriverEntryOrder
0x180013a99  mov     ecx, dword ptr [rbp+Size]
0x180013a9c  test    ecx, ecx
0x180013a9e  jz      short loc_180013AE1
0x180013aa0  mov     rax, cs:AllocRoutine
0x180013aa7  test    rax, rax
0x180013aaa  jz      short loc_180013AEA
0x180013aac  shl     rcx, 2
0x180013ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ab5  mov     rsi, rax
0x180013ab8  test    rax, rax
0x180013abb  jz      short loc_180013AEA
0x180013abd  mov     r8d, dword ptr [rbp+Size]; Size
0x180013ac1  xor     edx, edx; Val
0x180013ac3  mov     rcx, rax; void *
0x180013ac6  call    memset_0
0x180013acb  mov     ecx, dword ptr [rbp+Size]
0x180013ace  lea     rdx, [rbp+Size]
0x180013ad2  mov     [rbx+58h], ecx
0x180013ad5  mov     rcx, rsi
0x180013ad8  mov     [rbx+50h], rsi
0x180013adc  call    EfiQueryDriverEntryOrder
0x180013ae1  test    eax, eax
0x180013ae3  jns     short loc_180013AF4
0x180013ae5  jmp     short loc_180013AEA
0x180013ae7  mov     rbx, rdi
0x180013aea  mov     rcx, rbx
0x180013aed  call    EFIOSBODelete
0x180013af2  xor     edi, edi
0x180013af4  mov     rbx, [rsp+20h+arg_10]
0x180013af9  mov     rax, rdi
0x180013afc  add     rsp, 20h
0x180013b00  pop     r15
0x180013b02  pop     r14
0x180013b04  pop     rdi
0x180013b05  pop     rsi
0x180013b06  pop     rbp
0x180013b07  retn
```
