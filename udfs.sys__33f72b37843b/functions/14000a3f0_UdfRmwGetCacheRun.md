# UdfRmwGetCacheRun

- ea: `0x14000a3f0`
- end: `0x14000a6bd`
- name: `UdfRmwGetCacheRun`
- size: `717`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14001b770`
- `0x140059540`

## callees

- `0x14000a3f0`
- `0x14000ba88`
- `0x14000cad4`
- `0x140058c54`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14000a518`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a518`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000a529`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000a529`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000a643`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000a643`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000a68b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000a68b`

## pseudocode

```c
__int64 __fastcall UdfRmwGetCacheRun(__int64 a1, __int64 a2, unsigned int a3, _QWORD *a4, _BYTE *a5, int a6)
{
  _BYTE *v6; // r14
  _QWORD **v7; // r12
  _QWORD *v10; // r8
  bool v11; // bl
  _QWORD *v12; // rdi
  _DWORD *v13; // rdx
  unsigned int v14; // ecx
  int v15; // ecx
  __int64 v16; // r14
  int v17; // ebp
  _QWORD *v18; // rcx
  _QWORD *v19; // rcx
  _QWORD *v20; // rcx
  __int64 v21; // rax
  _QWORD *v22; // rdx
  unsigned int v23; // r15d
  _QWORD *i; // rax
  _QWORD *v25; // rdx
  int v26; // eax
  unsigned int v27; // ecx
  _QWORD *v28; // rax
  __int64 v29; // rdx
  _QWORD *v30; // r8
  _QWORD *v31; // r8
  unsigned int v34; // [rsp+78h] [rbp+10h] BYREF
  _QWORD *v35; // [rsp+88h] [rbp+20h]

  v35 = a4;
  v6 = a5;
  v7 = (_QWORD **)(a2 + 40);
  while ( 1 )
  {
    v10 = *v7;
    v11 = 0;
    while ( 1 )
    {
      v12 = 0;
      if ( v10 == v7 )
        goto LABEL_20;
      v13 = v10 - 4;
      v14 = *((_DWORD *)v10 - 8);
      if ( v14 > a3 )
        goto LABEL_20;
      if ( *(_DWORD *)(a2 + 12) + v14 > a3 )
        break;
      v10 = (_QWORD *)*v10;
    }
    v12 = v10 - 4;
    if ( v10 != (_QWORD *)32 )
    {
      v15 = v13[1];
      if ( *v13 == v15 )
        goto LABEL_46;
      if ( v15 == v13[2] )
      {
        if ( (a6 & 4) != 0 )
          goto LABEL_46;
        v11 = 1;
      }
      else
      {
        v11 = (a6 & 4) != 0;
        if ( (a6 & 4) == 0 )
          goto LABEL_11;
      }
    }
LABEL_20:
    if ( *v6 )
      break;
    ExReleaseResourceLite((PERESOURCE)(a2 + 128));
    ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 128), 1u);
    *v6 = 1;
  }
  if ( !v12 )
  {
    v18 = *(_QWORD **)(a2 + 56);
    while ( 1 )
    {
      if ( v18 == (_QWORD *)(a2 + 56) )
        goto LABEL_11;
      v12 = v18 - 6;
      if ( (v18[2] & 3) == 0 )
        break;
      v18 = (_QWORD *)*v18;
      v12 = 0;
    }
    v11 = 1;
LABEL_12:
    if ( (v12[8] & 3) != 0 )
      goto LABEL_14;
    goto LABEL_13;
  }
LABEL_11:
  if ( v11 )
    goto LABEL_12;
LABEL_13:
  if ( v12 )
  {
    v16 = a1;
    goto LABEL_34;
  }
LABEL_14:
  v16 = a1;
  v17 = UdfRmwFlushCache(a1, a2, a6, a6 & 1);
  if ( v17 >= 0 )
  {
    if ( !v12 )
    {
      v19 = *(_QWORD **)(a2 + 56);
      while ( v19 != (_QWORD *)(a2 + 56) )
      {
        v12 = v19 - 6;
        if ( (v19[2] & 3) == 0 )
          goto LABEL_35;
        v19 = (_QWORD *)*v19;
        v12 = 0;
      }
    }
LABEL_34:
    if ( v11 )
    {
LABEL_35:
      v20 = v12 + 4;
      v21 = v12[4];
      if ( *(_QWORD **)(v21 + 8) != v12 + 4 )
        goto LABEL_51;
      v22 = (_QWORD *)v12[5];
      if ( (_QWORD *)*v22 != v20 )
        goto LABEL_51;
      *v22 = v21;
      *(_QWORD *)(v21 + 8) = v22;
      v23 = a3 - a3 % *(_DWORD *)(a2 + 12);
      *(_DWORD *)v12 = v23;
      for ( i = *v7; i != v7 && *((_DWORD *)i - 8) <= v23; i = (_QWORD *)*i )
        ;
      v25 = (_QWORD *)i[1];
      if ( (_QWORD *)*v25 != i )
        goto LABEL_51;
      *v20 = i;
      v12[5] = v25;
      *v25 = v20;
      i[1] = v20;
      UdfLookupSparingInfo(v16, *(_DWORD *)v12, *(_DWORD *)(a2 + 12), (unsigned int *)v12 + 1, &v34);
      v26 = *((_DWORD *)v12 + 1);
      v27 = *(_DWORD *)v12;
      *((_DWORD *)v12 + 2) = v26;
      if ( v27 != v26 && (a6 & 4) == 0 )
        *((_DWORD *)v12 + 2) = v27;
      v12[3] = 0;
    }
LABEL_46:
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 72));
    v28 = v12 + 6;
    v29 = v12[6];
    if ( *(_QWORD **)(v29 + 8) == v12 + 6 )
    {
      v30 = (_QWORD *)v12[7];
      if ( (_QWORD *)*v30 == v28 )
      {
        *v30 = v29;
        *(_QWORD *)(v29 + 8) = v30;
        v31 = *(_QWORD **)(a2 + 64);
        if ( *v31 == a2 + 56 )
        {
          *v28 = a2 + 56;
          v12[7] = v31;
          *v31 = v28;
          *(_QWORD *)(a2 + 64) = v28;
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 72));
          v17 = 0;
          *v35 = v12;
          return (unsigned int)v17;
        }
      }
    }
LABEL_51:
    __fastfail(3u);
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 47, WPP_e04914546632397e8b30a0a107c62418_Traceguids);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x14000a3f0  mov     [rsp+arg_18], r9
0x14000a3f5  mov     qword ptr [rsp+arg_0], rcx
0x14000a3fa  push    rbx
0x14000a3fb  push    rbp
0x14000a3fc  push    rsi
0x14000a3fd  push    rdi
0x14000a3fe  push    r12
0x14000a400  push    r14
0x14000a402  push    r15
0x14000a404  sub     rsp, 30h
0x14000a408  mov     r14, [rsp+68h+arg_20]
0x14000a410  lea     r12, [rdx+28h]
0x14000a414  mov     r15d, r8d
0x14000a417  mov     rsi, rdx
0x14000a41a  mov     r8, [r12]
0x14000a41e  xor     bl, bl
0x14000a420  xor     edi, edi
0x14000a422  cmp     r8, r12
0x14000a425  jz      loc_14000A508
0x14000a42b  lea     rdx, [r8-20h]
0x14000a42f  mov     ecx, [rdx]
0x14000a431  cmp     ecx, r15d
0x14000a434  ja      loc_14000A508
0x14000a43a  add     ecx, [rsi+0Ch]
0x14000a43d  cmp     ecx, r15d
0x14000a440  ja      short loc_14000A447
0x14000a442  mov     r8, [r8]
0x14000a445  jmp     short loc_14000A420
0x14000a447  mov     rdi, rdx
0x14000a44a  test    rdx, rdx
0x14000a44d  jz      loc_14000A508
0x14000a453  mov     ecx, [rdx+4]
0x14000a456  cmp     [rdx], ecx
0x14000a458  jz      loc_14000A63F
0x14000a45e  mov     eax, [rsp+68h+arg_28]
0x14000a465  and     eax, 4
0x14000a468  cmp     ecx, [rdx+8]
0x14000a46b  jz      loc_14000A4FE
0x14000a471  test    eax, eax
0x14000a473  setnz   bl
0x14000a476  test    eax, eax
0x14000a478  jnz     loc_14000A508
0x14000a47e  test    bl, bl
0x14000a480  jz      short loc_14000A489
0x14000a482  mov     eax, [rdi+40h]
0x14000a485  test    al, 3
0x14000a487  jnz     short loc_14000A492
0x14000a489  test    rdi, rdi
0x14000a48c  jnz     loc_14000A593
0x14000a492  mov     r9b, byte ptr [rsp+68h+arg_28]
0x14000a49a  mov     rdx, rsi
0x14000a49d  mov     r14, qword ptr [rsp+68h+arg_0]
0x14000a4a2  and     r9b, 1
0x14000a4a6  mov     r8d, [rsp+68h+arg_28]
0x14000a4ae  mov     rcx, r14; int
0x14000a4b1  call    UdfRmwFlushCache
0x14000a4b6  mov     ebp, eax
0x14000a4b8  test    eax, eax
0x14000a4ba  jns     loc_14000A570
0x14000a4c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a4c7  lea     rax, WPP_GLOBAL_Control
0x14000a4ce  cmp     rcx, rax
0x14000a4d1  jz      loc_14000A6A4
0x14000a4d7  test    dword ptr [rcx+2Ch], 20000000h
0x14000a4de  jz      loc_14000A6A4
0x14000a4e4  mov     rcx, [rcx+18h]
0x14000a4e8  lea     r8, WPP_e04914546632397e8b30a0a107c62418_Traceguids
0x14000a4ef  mov     edx, 2Fh ; '/'
0x14000a4f4  call    WPP_SF_
0x14000a4f9  jmp     loc_14000A6A4
0x14000a4fe  test    eax, eax
0x14000a500  jnz     loc_14000A63F
0x14000a506  mov     bl, 1
0x14000a508  cmp     byte ptr [r14], 0
0x14000a50c  jnz     short loc_14000A53E
0x14000a50e  lea     rbx, [rsi+80h]
0x14000a515  mov     rcx, rbx; Resource
0x14000a518  call    cs:__imp_ExReleaseResourceLite
0x14000a51f  nop     dword ptr [rax+rax+00h]
0x14000a524  mov     dl, 1; Wait
0x14000a526  mov     rcx, rbx; Resource
0x14000a529  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000a530  nop     dword ptr [rax+rax+00h]
0x14000a535  mov     byte ptr [r14], 1
0x14000a539  jmp     loc_14000A41A
0x14000a53e  test    rdi, rdi
0x14000a541  jnz     loc_14000A47E
0x14000a547  lea     rdx, [rsi+38h]
0x14000a54b  mov     rcx, [rdx]
0x14000a54e  cmp     rcx, rdx
0x14000a551  jz      loc_14000A47E
0x14000a557  lea     rdi, [rcx-30h]
0x14000a55b  mov     eax, [rdi+40h]
0x14000a55e  test    al, 3
0x14000a560  jz      short loc_14000A569
0x14000a562  mov     rcx, [rcx]
0x14000a565  xor     edi, edi
0x14000a567  jmp     short loc_14000A54E
0x14000a569  mov     bl, 1
0x14000a56b  jmp     loc_14000A482
0x14000a570  test    rdi, rdi
0x14000a573  jnz     short loc_14000A598
0x14000a575  lea     rdx, [rsi+38h]
0x14000a579  mov     rcx, [rdx]
0x14000a57c  cmp     rcx, rdx
0x14000a57f  jz      short loc_14000A598
0x14000a581  lea     rdi, [rcx-30h]
0x14000a585  mov     eax, [rdi+40h]
0x14000a588  test    al, 3
0x14000a58a  jz      short loc_14000A5A0
0x14000a58c  mov     rcx, [rcx]
0x14000a58f  xor     edi, edi
0x14000a591  jmp     short loc_14000A57C
0x14000a593  mov     r14, qword ptr [rsp+68h+arg_0]
0x14000a598  test    bl, bl
0x14000a59a  jz      loc_14000A63F
0x14000a5a0  lea     rcx, [rdi+20h]
0x14000a5a4  mov     rax, [rcx]
0x14000a5a7  cmp     [rax+8], rcx
0x14000a5ab  jnz     loc_14000A6B6
0x14000a5b1  mov     rdx, [rcx+8]
0x14000a5b5  cmp     [rdx], rcx
0x14000a5b8  jnz     loc_14000A6B6
0x14000a5be  mov     [rdx], rax
0x14000a5c1  mov     [rax+8], rdx
0x14000a5c5  mov     eax, r15d
0x14000a5c8  xor     edx, edx
0x14000a5ca  div     dword ptr [rsi+0Ch]
0x14000a5cd  sub     r15d, edx
0x14000a5d0  mov     [rdi], r15d
0x14000a5d3  mov     rax, [r12]
0x14000a5d7  jmp     short loc_14000A5E2
0x14000a5d9  cmp     [rax-20h], r15d
0x14000a5dd  ja      short loc_14000A5E7
0x14000a5df  mov     rax, [rax]
0x14000a5e2  cmp     rax, r12
0x14000a5e5  jnz     short loc_14000A5D9
0x14000a5e7  mov     rdx, [rax+8]
0x14000a5eb  cmp     [rdx], rax
0x14000a5ee  jnz     loc_14000A6B6
0x14000a5f4  mov     [rcx], rax
0x14000a5f7  lea     r9, [rdi+4]
0x14000a5fb  mov     [rcx+8], rdx
0x14000a5ff  mov     [rdx], rcx
0x14000a602  mov     [rax+8], rcx
0x14000a606  lea     rax, [rsp+68h+arg_8]
0x14000a60b  mov     r8d, [rsi+0Ch]
0x14000a60f  mov     rcx, r14
0x14000a612  mov     edx, [rdi]
0x14000a614  mov     [rsp+68h+var_48], rax
0x14000a619  call    UdfLookupSparingInfo
0x14000a61e  mov     eax, [rdi+4]
0x14000a621  mov     ecx, [rdi]
0x14000a623  mov     [rdi+8], eax
0x14000a626  cmp     ecx, eax
0x14000a628  jz      short loc_14000A637
0x14000a62a  test    byte ptr [rsp+68h+arg_28], 4
0x14000a632  jnz     short loc_14000A637
0x14000a634  mov     [rdi+8], ecx
0x14000a637  mov     qword ptr [rdi+18h], 0
0x14000a63f  lea     rcx, [rsi+48h]; FastMutex
0x14000a643  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14000a64a  nop     dword ptr [rax+rax+00h]
0x14000a64f  lea     rax, [rdi+30h]
0x14000a653  mov     rdx, [rax]
0x14000a656  cmp     [rdx+8], rax
0x14000a65a  jnz     short loc_14000A6B6
0x14000a65c  mov     r8, [rax+8]
0x14000a660  cmp     [r8], rax
0x14000a663  jnz     short loc_14000A6B6
0x14000a665  mov     [r8], rdx
0x14000a668  mov     [rdx+8], r8
0x14000a66c  lea     rdx, [rsi+38h]
0x14000a670  mov     r8, [rdx+8]
0x14000a674  cmp     [r8], rdx
0x14000a677  jnz     short loc_14000A6B6
0x14000a679  mov     [rax], rdx
0x14000a67c  lea     rcx, [rsi+48h]; FastMutex
0x14000a680  mov     [rax+8], r8
0x14000a684  mov     [r8], rax
0x14000a687  mov     [rdx+8], rax
0x14000a68b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14000a692  nop     dword ptr [rax+rax+00h]
0x14000a697  mov     rax, [rsp+68h+arg_18]
0x14000a69f  xor     ebp, ebp
0x14000a6a1  mov     [rax], rdi
0x14000a6a4  mov     eax, ebp
0x14000a6a6  add     rsp, 30h
0x14000a6aa  pop     r15
0x14000a6ac  pop     r14
0x14000a6ae  pop     r12
0x14000a6b0  pop     rdi
0x14000a6b1  pop     rsi
0x14000a6b2  pop     rbp
0x14000a6b3  pop     rbx
0x14000a6b4  retn
0x14000a6b6  mov     ecx, 3
0x14000a6bb  int     29h; Win8: RtlFailFast(ecx)
```
