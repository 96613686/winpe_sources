# YReader::ParseXmlDecl(void)

- ea: `0x1004098d0`
- end: `0x10040a010`
- name: `?ParseXmlDecl@YReader@@AEAAXXZ`
- size: `1856`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1004074d0`

## callees

- `0x100401780`
- `0x1004098d0`
- `0x10040f160`
- `0x100415560`
- `0x1004236e0`
- `0x1004394f0`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseXmlDecl(YReader *this)
{
  __int64 v1; // rax
  unsigned __int64 v3; // r15
  unsigned int v4; // eax
  struct BlockAlloc::Header *v5; // rbx
  __int64 v6; // r14
  void *v7; // rdx
  __int64 v8; // rcx
  struct BlockAlloc::Header *v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // eax
  struct BlockAlloc::Header *v12; // rbx
  __int64 v13; // r14
  void *v14; // rdx
  __int64 v15; // rcx
  struct BlockAlloc::Header *v16; // rax
  __int64 v17; // rcx
  unsigned int v18; // eax
  struct BlockAlloc::Header *v19; // rbx
  __int64 v20; // r14
  void *v21; // rdx
  __int64 v22; // rcx
  struct BlockAlloc::Header *v23; // rax
  __int64 v24; // rcx
  unsigned int v25; // ebx
  unsigned int v26; // eax
  struct BlockAlloc::Header *v27; // rbx
  __int64 v28; // r14
  void *v29; // rdx
  __int64 v30; // rcx
  struct BlockAlloc::Header *v31; // rax
  __int64 v32; // rcx
  unsigned int v33; // r8d
  unsigned __int16 *v34; // rdx
  __int64 v35; // r9
  int v36; // ecx
  unsigned int v37; // eax
  struct BlockAlloc::Header *v38; // rbx
  __int64 v39; // r14
  void *v40; // rdx
  __int64 v41; // rcx
  struct BlockAlloc::Header *v42; // rax
  __int64 v43; // rcx
  unsigned int v44; // eax
  struct BlockAlloc::Header *v45; // rbx
  __int64 v46; // r14
  void *v47; // rdx
  __int64 v48; // rcx
  struct BlockAlloc::Header *v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rbx
  void *v52; // r14
  unsigned int v53; // eax
  char v54; // al
  _QWORD *v55; // rcx
  _QWORD *v56; // rax
  void *Buf1; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v58; // [rsp+28h] [rbp-8h]

  v1 = *((_QWORD *)this + 55);
  v58 = 0;
  v3 = *(_QWORD *)(v1 + 16);
  (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
  if ( *((_DWORD *)this + 28) != 12 )
    goto LABEL_85;
  v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13));
  v5 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
  v6 = v4;
  v7 = (void *)*((_QWORD *)v5 + 2);
  if ( *((_DWORD *)v5 + 6) - (int)v7 < v4 )
  {
    v8 = *((_QWORD *)v5 + 1);
    if ( v8 )
    {
      while ( 1 )
      {
        v5 = (struct BlockAlloc::Header *)v8;
        if ( *(_DWORD *)(v8 + 24) - (int)v8 - 32 >= v4 )
          break;
        v8 = *(_QWORD *)(v8 + 8);
        if ( !v8 )
          goto LABEL_6;
      }
      *(_QWORD *)(v8 + 16) = v8 + 32;
    }
    else
    {
LABEL_6:
      _mm_lfence();
      v9 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v4, v5);
      *((_QWORD *)v5 + 1) = v9;
      v5 = v9;
    }
    *((_QWORD *)this + 55) = v5;
    v7 = (void *)*((_QWORD *)v5 + 2);
  }
  *((_QWORD *)v5 + 2) += v6;
  v10 = *((_QWORD *)this + 13);
  Buf1 = v7;
  (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v10 + 104LL))(v10, &Buf1);
  if ( v58 != dword_100450B88 )
    goto LABEL_85;
  if ( memcmp(Buf1, CodeStringPtr::version, 2LL * v58) )
    goto LABEL_85;
  *((_DWORD *)this + 77) = 0x7FFFFFFF;
  (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
  if ( *((_DWORD *)this + 28) != 7 )
    goto LABEL_85;
  v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13));
  v12 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
  v13 = v11;
  v14 = (void *)*((_QWORD *)v12 + 2);
  if ( *((_DWORD *)v12 + 6) - (int)v14 < v11 )
  {
    v15 = *((_QWORD *)v12 + 1);
    if ( v15 )
    {
      while ( 1 )
      {
        v12 = (struct BlockAlloc::Header *)v15;
        if ( *(_DWORD *)(v15 + 24) - (int)v15 - 32 >= v11 )
          break;
        v15 = *(_QWORD *)(v15 + 8);
        if ( !v15 )
          goto LABEL_15;
      }
      *(_QWORD *)(v15 + 16) = v15 + 32;
    }
    else
    {
LABEL_15:
      _mm_lfence();
      v16 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v11, v12);
      *((_QWORD *)v12 + 1) = v16;
      v12 = v16;
    }
    *((_QWORD *)this + 55) = v12;
    v14 = (void *)*((_QWORD *)v12 + 2);
  }
  *((_QWORD *)v12 + 2) += v13;
  v17 = *((_QWORD *)this + 13);
  Buf1 = v14;
  (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v17 + 104LL))(v17, &Buf1);
  if ( v58 != dword_100450B98 || memcmp(Buf1, CodeStringPtr::opz, 2LL * v58) )
    goto LABEL_85;
  CloneStringPtr::Assign((YReader *)((char *)this + 1744), *((struct IMalloc **)this + 1), (struct StringPtr *)&Buf1);
  (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
  if ( *((_DWORD *)this + 28) != 12 )
    goto LABEL_73;
  v18 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13));
  v19 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
  v20 = v18;
  v21 = (void *)*((_QWORD *)v19 + 2);
  if ( *((_DWORD *)v19 + 6) - (int)v21 < v18 )
  {
    v22 = *((_QWORD *)v19 + 1);
    if ( v22 )
    {
      while ( 1 )
      {
        v19 = (struct BlockAlloc::Header *)v22;
        if ( *(_DWORD *)(v22 + 24) - (int)v22 - 32 >= v18 )
          break;
        v22 = *(_QWORD *)(v22 + 8);
        if ( !v22 )
          goto LABEL_24;
      }
      *(_QWORD *)(v22 + 16) = v22 + 32;
    }
    else
    {
LABEL_24:
      _mm_lfence();
      v23 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v18, v19);
      *((_QWORD *)v19 + 1) = v23;
      v19 = v23;
    }
    *((_QWORD *)this + 55) = v19;
    v21 = (void *)*((_QWORD *)v19 + 2);
  }
  *((_QWORD *)v19 + 2) += v20;
  v24 = *((_QWORD *)this + 13);
  Buf1 = v21;
  (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v24 + 104LL))(v24, &Buf1);
  v25 = v58;
  if ( v58 == dword_100450BA8 && !memcmp(Buf1, CodeStringPtr::encoding, 2LL * v58) )
  {
    *((_DWORD *)this + 77) = 0x7FFFFFFF;
    (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
    if ( *((_DWORD *)this + 28) != 7 )
      goto LABEL_85;
    v26 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13));
    v27 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
    v28 = v26;
    v29 = (void *)*((_QWORD *)v27 + 2);
    if ( *((_DWORD *)v27 + 6) - (int)v29 < v26 )
    {
      v30 = *((_QWORD *)v27 + 1);
      if ( v30 )
      {
        while ( 1 )
        {
          v27 = (struct BlockAlloc::Header *)v30;
          if ( *(_DWORD *)(v30 + 24) - (int)v30 - 32 >= v26 )
            break;
          v30 = *(_QWORD *)(v30 + 8);
          if ( !v30 )
            goto LABEL_33;
        }
        *(_QWORD *)(v30 + 16) = v30 + 32;
      }
      else
      {
LABEL_33:
        _mm_lfence();
        v31 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v26, v27);
        *((_QWORD *)v27 + 1) = v31;
        v27 = v31;
      }
      *((_QWORD *)this + 55) = v27;
      v29 = (void *)*((_QWORD *)v27 + 2);
    }
    *((_QWORD *)v27 + 2) += v28;
    v32 = *((_QWORD *)this + 13);
    Buf1 = v29;
    (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v32 + 104LL))(v32, &Buf1);
    v33 = v58 - 1;
    if ( !v58 || (unsigned __int16)(*(_WORD *)Buf1 - 65) > 0x19u && (unsigned __int16)(*(_WORD *)Buf1 - 97) > 0x19u )
    {
LABEL_86:
      MXRRaiseException(-1072894399);
      __debugbreak();
    }
    v34 = (unsigned __int16 *)((char *)Buf1 + 2);
    if ( v58 != 1 )
    {
      v35 = 0x43FFFFFF01FFBLL;
      do
      {
        v36 = *v34;
        --v33;
        if ( ((unsigned __int16)(v36 - 45) > 0x32u || !_bittest64(&v35, (unsigned int)(v36 - 45)))
          && (unsigned __int16)(v36 - 97) > 0x19u )
        {
          goto LABEL_86;
        }
        ++v34;
      }
      while ( v33 );
    }
    CloneStringPtr::Assign((YReader *)((char *)this + 1760), *((struct IMalloc **)this + 1), (struct StringPtr *)&Buf1);
    (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
    if ( *((_DWORD *)this + 28) != 12 )
      goto LABEL_73;
    v37 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13));
    v38 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
    v39 = v37;
    v40 = (void *)*((_QWORD *)v38 + 2);
    if ( *((_DWORD *)v38 + 6) - (int)v40 < v37 )
    {
      v41 = *((_QWORD *)v38 + 1);
      if ( v41 )
      {
        while ( 1 )
        {
          v38 = (struct BlockAlloc::Header *)v41;
          if ( *(_DWORD *)(v41 + 24) - (int)v41 - 32 >= v37 )
            break;
          v41 = *(_QWORD *)(v41 + 8);
          if ( !v41 )
            goto LABEL_49;
        }
        *(_QWORD *)(v41 + 16) = v41 + 32;
      }
      else
      {
LABEL_49:
        _mm_lfence();
        v42 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v37, v38);
        *((_QWORD *)v38 + 1) = v42;
        v38 = v42;
      }
      *((_QWORD *)this + 55) = v38;
      v40 = (void *)*((_QWORD *)v38 + 2);
    }
    *((_QWORD *)v38 + 2) += v39;
    v43 = *((_QWORD *)this + 13);
    Buf1 = v40;
    (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v43 + 104LL))(v43, &Buf1);
    v25 = v58;
  }
  if ( v25 != dword_100450BB8
    || memcmp(Buf1, CodeStringPtr::standalone, 2LL * v25)
    || (*((_DWORD *)this + 77) = 0x7FFFFFFF,
        (*((void (__fastcall **)(char *))this + 27))((char *)this + 40),
        *((_DWORD *)this + 28) != 7) )
  {
LABEL_85:
    MXRRaiseException(-1072894400);
    __debugbreak();
  }
  v44 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13));
  v45 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
  v46 = v44;
  v47 = (void *)*((_QWORD *)v45 + 2);
  if ( *((_DWORD *)v45 + 6) - (int)v47 < v44 )
  {
    v48 = *((_QWORD *)v45 + 1);
    if ( v48 )
    {
      while ( 1 )
      {
        v45 = (struct BlockAlloc::Header *)v48;
        if ( *(_DWORD *)(v48 + 24) - (int)v48 - 32 >= v44 )
          break;
        v48 = *(_QWORD *)(v48 + 8);
        if ( !v48 )
          goto LABEL_59;
      }
      *(_QWORD *)(v48 + 16) = v48 + 32;
    }
    else
    {
LABEL_59:
      _mm_lfence();
      v49 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v44, v45);
      *((_QWORD *)v45 + 1) = v49;
      v45 = v49;
    }
    *((_QWORD *)this + 55) = v45;
    v47 = (void *)*((_QWORD *)v45 + 2);
  }
  *((_QWORD *)v45 + 2) += v46;
  v50 = *((_QWORD *)this + 13);
  Buf1 = v47;
  (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v50 + 104LL))(v50, &Buf1);
  v51 = v58;
  v52 = Buf1;
  if ( v58 == dword_100450BC8 && !memcmp(Buf1, CodeStringPtr::yes, 2LL * v58) )
  {
    *((_BYTE *)this + 1787) = 1;
LABEL_72:
    (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
    goto LABEL_73;
  }
  if ( (_DWORD)v51 == dword_100450BD8 && !memcmp(v52, CodeStringPtr::no, 2 * v51) )
    goto LABEL_72;
LABEL_73:
  if ( *((_DWORD *)this + 28) != 2 )
    goto LABEL_85;
  v53 = *((_DWORD *)this + 442);
  if ( v53 != dword_100450B38 || memcmp(*((const void **)this + 220), CodeStringPtr::empty, 2LL * v53) )
  {
    v54 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 24LL))(*((_QWORD *)this + 13));
    Scanner::SetEncoding((YReader *)((char *)this + 40), (YReader *)((char *)this + 1760), v54, 0);
  }
  v55 = (_QWORD *)*((_QWORD *)this + 55);
  if ( (unsigned __int64)v55 >= v3 || v3 > v55[2] )
  {
    v55 = (_QWORD *)*v55;
    *((_QWORD *)this + 55) = v55;
    if ( !v55 )
    {
LABEL_87:
      MXRRaiseException(-2147467259);
      JUMPOUT(0x10040A00FLL);
    }
    while ( (unsigned __int64)v55 >= v3 || v3 > v55[3] )
    {
      v56 = (_QWORD *)*v55;
      *((_QWORD *)this + 55) = *v55;
      v55 = v56;
      if ( !v56 )
        goto LABEL_87;
    }
  }
  v55[2] = v3;
}

```

## disassembly

```asm
0x1004098d0  mov     [rsp-18h+arg_0], rbx
0x1004098d5  mov     [rsp-18h+arg_8], rsi
0x1004098da  mov     [rsp-18h+arg_10], rdi
0x1004098df  mov     [rsp-18h+arg_18], r12
0x1004098e4  push    rbp
0x1004098e5  push    r14
0x1004098e7  push    r15
0x1004098e9  mov     rbp, rsp
0x1004098ec  sub     rsp, 30h
0x1004098f0  mov     rax, [rcx+1B8h]
0x1004098f7  mov     rdi, rcx
0x1004098fa  mov     [rbp+var_8], 0
0x100409901  add     rcx, 28h ; '('
0x100409905  mov     r15, [rax+10h]
0x100409909  mov     rax, [rdi+0D8h]
0x100409910  call    cs:__guard_dispatch_icall_fptr
0x100409916  cmp     dword ptr [rdi+70h], 0Ch
0x10040991a  jnz     loc_100409FEF
0x100409920  mov     rcx, [rdi+68h]
0x100409924  mov     rax, [rcx]
0x100409927  mov     rax, [rax+60h]
0x10040992b  call    cs:__guard_dispatch_icall_fptr
0x100409931  mov     rbx, [rdi+1B8h]
0x100409938  lea     r12, [rdi+1A0h]
0x10040993f  mov     r14d, eax
0x100409942  mov     rdx, [rbx+10h]
0x100409946  mov     ecx, [rbx+18h]
0x100409949  sub     ecx, edx
0x10040994b  cmp     ecx, eax
0x10040994d  jnb     short loc_1004099A0
0x10040994f  mov     rcx, [rbx+8]
0x100409953  test    rcx, rcx
0x100409956  jz      short loc_10040997D
0x100409958  nop     dword ptr [rax+rax+00000000h]
0x100409960  mov     eax, [rcx+18h]
0x100409963  mov     rbx, rcx
0x100409966  sub     eax, ecx
0x100409968  sub     eax, 20h ; ' '
0x10040996b  cmp     eax, r14d
0x10040996e  jnb     loc_100409EAE
0x100409974  mov     rcx, [rcx+8]
0x100409978  test    rcx, rcx
0x10040997b  jnz     short loc_100409960
0x10040997d  lfence
0x100409980  mov     r8, rbx; struct BlockAlloc::Header *
0x100409983  mov     edx, r14d; unsigned int
0x100409986  mov     rcx, r12; this
0x100409989  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x10040998e  mov     [rbx+8], rax
0x100409992  mov     rbx, rax
0x100409995  mov     [rdi+1B8h], rbx
0x10040999c  mov     rdx, [rbx+10h]
0x1004099a0  add     [rbx+10h], r14
0x1004099a4  mov     rcx, [rdi+68h]
0x1004099a8  mov     [rbp+Buf1], rdx
0x1004099ac  lea     rdx, [rbp+Buf1]
0x1004099b0  mov     rax, [rcx]
0x1004099b3  mov     rax, [rax+68h]
0x1004099b7  call    cs:__guard_dispatch_icall_fptr
0x1004099bd  mov     eax, [rbp+var_8]
0x1004099c0  cmp     eax, cs:dword_100450B88
0x1004099c6  jnz     loc_100409FEF
0x1004099cc  mov     rdx, cs:?version@CodeStringPtr@@2UStringPtr@@A; Buf2
0x1004099d3  mov     r8d, eax
0x1004099d6  mov     rcx, [rbp+Buf1]; Buf1
0x1004099da  add     r8, r8; Size
0x1004099dd  call    memcmp
0x1004099e2  test    eax, eax
0x1004099e4  jnz     loc_100409FEF
0x1004099ea  mov     dword ptr [rdi+134h], 7FFFFFFFh
0x1004099f4  lea     rcx, [rdi+28h]
0x1004099f8  mov     rax, [rdi+0D8h]
0x1004099ff  call    cs:__guard_dispatch_icall_fptr
0x100409a05  cmp     dword ptr [rdi+70h], 7
0x100409a09  jnz     loc_100409FEF
0x100409a0f  mov     rcx, [rdi+68h]
0x100409a13  mov     rax, [rcx]
0x100409a16  mov     rax, [rax+60h]
0x100409a1a  call    cs:__guard_dispatch_icall_fptr
0x100409a20  mov     rbx, [rdi+1B8h]
0x100409a27  mov     r14d, eax
0x100409a2a  mov     rdx, [rbx+10h]
0x100409a2e  mov     ecx, [rbx+18h]
0x100409a31  sub     ecx, edx
0x100409a33  cmp     ecx, eax
0x100409a35  jnb     short loc_100409A80
0x100409a37  mov     rcx, [rbx+8]
0x100409a3b  test    rcx, rcx
0x100409a3e  jz      short loc_100409A5D
0x100409a40  mov     eax, [rcx+18h]
0x100409a43  mov     rbx, rcx
0x100409a46  sub     eax, ecx
0x100409a48  sub     eax, 20h ; ' '
0x100409a4b  cmp     eax, r14d
0x100409a4e  jnb     loc_100409EBB
0x100409a54  mov     rcx, [rcx+8]
0x100409a58  test    rcx, rcx
0x100409a5b  jnz     short loc_100409A40
0x100409a5d  lfence
0x100409a60  mov     r8, rbx; struct BlockAlloc::Header *
0x100409a63  mov     edx, r14d; unsigned int
0x100409a66  mov     rcx, r12; this
0x100409a69  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x100409a6e  mov     [rbx+8], rax
0x100409a72  mov     rbx, rax
0x100409a75  mov     [rdi+1B8h], rbx
0x100409a7c  mov     rdx, [rbx+10h]
0x100409a80  add     [rbx+10h], r14
0x100409a84  mov     rcx, [rdi+68h]
0x100409a88  mov     [rbp+Buf1], rdx
0x100409a8c  lea     rdx, [rbp+Buf1]
0x100409a90  mov     rax, [rcx]
0x100409a93  mov     rax, [rax+68h]
0x100409a97  call    cs:__guard_dispatch_icall_fptr
0x100409a9d  mov     eax, [rbp+var_8]
0x100409aa0  cmp     eax, cs:dword_100450B98
0x100409aa6  jnz     loc_100409FEF
0x100409aac  mov     rdx, cs:?opz@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100409ab3  mov     r8d, eax
0x100409ab6  mov     rcx, [rbp+Buf1]; Buf1
0x100409aba  add     r8, r8; Size
0x100409abd  call    memcmp
0x100409ac2  test    eax, eax
0x100409ac4  jnz     loc_100409FEF
0x100409aca  mov     rdx, [rdi+8]; struct IMalloc *
0x100409ace  lea     rcx, [rdi+6D0h]; this
0x100409ad5  lea     r8, [rbp+Buf1]; struct StringPtr *
0x100409ad9  call    ?Assign@CloneStringPtr@@QEAAXPEAUIMalloc@@PEAUStringPtr@@@Z; CloneStringPtr::Assign(IMalloc *,StringPtr *)
0x100409ade  mov     rax, [rdi+0D8h]
0x100409ae5  lea     rcx, [rdi+28h]
0x100409ae9  call    cs:__guard_dispatch_icall_fptr
0x100409aef  cmp     dword ptr [rdi+70h], 0Ch
0x100409af3  jnz     loc_100409F2E
0x100409af9  mov     rcx, [rdi+68h]
0x100409afd  mov     rax, [rcx]
0x100409b00  mov     rax, [rax+60h]
0x100409b04  call    cs:__guard_dispatch_icall_fptr
0x100409b0a  mov     rbx, [rdi+1B8h]
0x100409b11  mov     r14d, eax
0x100409b14  mov     rdx, [rbx+10h]
0x100409b18  mov     ecx, [rbx+18h]
0x100409b1b  sub     ecx, edx
0x100409b1d  cmp     ecx, eax
0x100409b1f  jnb     short loc_100409B70
0x100409b21  mov     rcx, [rbx+8]
0x100409b25  test    rcx, rcx
0x100409b28  jz      short loc_100409B4D
0x100409b2a  nop     word ptr [rax+rax+00h]
0x100409b30  mov     eax, [rcx+18h]
0x100409b33  mov     rbx, rcx
0x100409b36  sub     eax, ecx
0x100409b38  sub     eax, 20h ; ' '
0x100409b3b  cmp     eax, r14d
0x100409b3e  jnb     loc_100409EC8
0x100409b44  mov     rcx, [rcx+8]
0x100409b48  test    rcx, rcx
0x100409b4b  jnz     short loc_100409B30
0x100409b4d  lfence
0x100409b50  mov     r8, rbx; struct BlockAlloc::Header *
0x100409b53  mov     edx, r14d; unsigned int
0x100409b56  mov     rcx, r12; this
0x100409b59  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x100409b5e  mov     [rbx+8], rax
0x100409b62  mov     rbx, rax
0x100409b65  mov     [rdi+1B8h], rbx
0x100409b6c  mov     rdx, [rbx+10h]
0x100409b70  add     [rbx+10h], r14
0x100409b74  mov     rcx, [rdi+68h]
0x100409b78  mov     [rbp+Buf1], rdx
0x100409b7c  lea     rdx, [rbp+Buf1]
0x100409b80  mov     rax, [rcx]
0x100409b83  mov     rax, [rax+68h]
0x100409b87  call    cs:__guard_dispatch_icall_fptr
0x100409b8d  mov     ebx, [rbp+var_8]
0x100409b90  cmp     ebx, cs:dword_100450BA8
0x100409b96  jnz     loc_100409DA0
0x100409b9c  mov     rdx, cs:?encoding@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100409ba3  mov     r8d, ebx
0x100409ba6  mov     rcx, [rbp+Buf1]; Buf1
0x100409baa  add     r8, r8; Size
0x100409bad  call    memcmp
0x100409bb2  test    eax, eax
0x100409bb4  jnz     loc_100409DA0
0x100409bba  mov     dword ptr [rdi+134h], 7FFFFFFFh
0x100409bc4  lea     rcx, [rdi+28h]
0x100409bc8  mov     rax, [rdi+0D8h]
0x100409bcf  call    cs:__guard_dispatch_icall_fptr
0x100409bd5  cmp     dword ptr [rdi+70h], 7
0x100409bd9  jnz     loc_100409FEF
0x100409bdf  mov     rcx, [rdi+68h]
0x100409be3  mov     rax, [rcx]
0x100409be6  mov     rax, [rax+60h]
0x100409bea  call    cs:__guard_dispatch_icall_fptr
0x100409bf0  mov     rbx, [rdi+1B8h]
0x100409bf7  mov     r14d, eax
0x100409bfa  mov     rdx, [rbx+10h]
0x100409bfe  mov     ecx, [rbx+18h]
0x100409c01  sub     ecx, edx
0x100409c03  cmp     ecx, eax
0x100409c05  jnb     short loc_100409C50
0x100409c07  mov     rcx, [rbx+8]
0x100409c0b  test    rcx, rcx
0x100409c0e  jz      short loc_100409C2D
0x100409c10  mov     eax, [rcx+18h]
0x100409c13  mov     rbx, rcx
0x100409c16  sub     eax, ecx
0x100409c18  sub     eax, 20h ; ' '
0x100409c1b  cmp     eax, r14d
0x100409c1e  jnb     loc_100409ED5
0x100409c24  mov     rcx, [rcx+8]
0x100409c28  test    rcx, rcx
0x100409c2b  jnz     short loc_100409C10
0x100409c2d  lfence
0x100409c30  mov     r8, rbx; struct BlockAlloc::Header *
0x100409c33  mov     edx, r14d; unsigned int
0x100409c36  mov     rcx, r12; this
0x100409c39  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x100409c3e  mov     [rbx+8], rax
0x100409c42  mov     rbx, rax
0x100409c45  mov     [rdi+1B8h], rbx
0x100409c4c  mov     rdx, [rbx+10h]
0x100409c50  add     [rbx+10h], r14
0x100409c54  mov     rcx, [rdi+68h]
0x100409c58  mov     [rbp+Buf1], rdx
0x100409c5c  lea     rdx, [rbp+Buf1]
0x100409c60  mov     rax, [rcx]
0x100409c63  mov     rax, [rax+68h]
0x100409c67  call    cs:__guard_dispatch_icall_fptr
0x100409c6d  mov     eax, [rbp+var_8]
0x100409c70  lea     r8d, [rax-1]
0x100409c74  test    eax, eax
0x100409c76  jz      loc_100409FFA
0x100409c7c  mov     rdx, [rbp+Buf1]
0x100409c80  movzx   ecx, word ptr [rdx]
0x100409c83  lea     eax, [rcx-41h]
0x100409c86  cmp     ax, 19h
0x100409c8a  jbe     short loc_100409C9A
0x100409c8c  sub     cx, 61h ; 'a'
0x100409c90  cmp     cx, 19h
0x100409c94  ja      loc_100409FFA
0x100409c9a  add     rdx, 2
0x100409c9e  test    r8d, r8d
0x100409ca1  jz      short loc_100409CDC
0x100409ca3  mov     r9, 43FFFFFF01FFBh
0x100409cad  nop     dword ptr [rax]
0x100409cb0  movzx   ecx, word ptr [rdx]
0x100409cb3  dec     r8d
0x100409cb6  lea     eax, [rcx-2Dh]
0x100409cb9  cmp     ax, 32h ; '2'
0x100409cbd  ja      short loc_100409CC5
0x100409cbf  bt      r9, rax
0x100409cc3  jb      short loc_100409CD3
0x100409cc5  sub     cx, 61h ; 'a'
0x100409cc9  cmp     cx, 19h
0x100409ccd  ja      loc_100409FFA
0x100409cd3  add     rdx, 2
0x100409cd7  test    r8d, r8d
0x100409cda  jnz     short loc_100409CB0
0x100409cdc  mov     rdx, [rdi+8]; struct IMalloc *
0x100409ce0  lea     rcx, [rdi+6E0h]; this
0x100409ce7  lea     r8, [rbp+Buf1]; struct StringPtr *
0x100409ceb  call    ?Assign@CloneStringPtr@@QEAAXPEAUIMalloc@@PEAUStringPtr@@@Z; CloneStringPtr::Assign(IMalloc *,StringPtr *)
0x100409cf0  mov     rax, [rdi+0D8h]
0x100409cf7  lea     rcx, [rdi+28h]
0x100409cfb  call    cs:__guard_dispatch_icall_fptr
0x100409d01  cmp     dword ptr [rdi+70h], 0Ch
0x100409d05  jnz     loc_100409F2E
0x100409d0b  mov     rcx, [rdi+68h]
0x100409d0f  mov     rax, [rcx]
0x100409d12  mov     rax, [rax+60h]
0x100409d16  call    cs:__guard_dispatch_icall_fptr
0x100409d1c  mov     rbx, [rdi+1B8h]
0x100409d23  mov     r14d, eax
0x100409d26  mov     rdx, [rbx+10h]
0x100409d2a  mov     ecx, [rbx+18h]
0x100409d2d  sub     ecx, edx
0x100409d2f  cmp     ecx, eax
0x100409d31  jnb     short loc_100409D80
0x100409d33  mov     rcx, [rbx+8]
0x100409d37  test    rcx, rcx
0x100409d3a  jz      short loc_100409D5D
0x100409d3c  nop     dword ptr [rax+00h]
0x100409d40  mov     eax, [rcx+18h]
0x100409d43  mov     rbx, rcx
0x100409d46  sub     eax, ecx
0x100409d48  sub     eax, 20h ; ' '
0x100409d4b  cmp     eax, r14d
0x100409d4e  jnb     loc_100409EE2
0x100409d54  mov     rcx, [rcx+8]
0x100409d58  test    rcx, rcx
0x100409d5b  jnz     short loc_100409D40
0x100409d5d  lfence
0x100409d60  mov     r8, rbx; struct BlockAlloc::Header *
0x100409d63  mov     edx, r14d; unsigned int
0x100409d66  mov     rcx, r12; this
0x100409d69  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x100409d6e  mov     [rbx+8], rax
0x100409d72  mov     rbx, rax
0x100409d75  mov     [rdi+1B8h], rbx
0x100409d7c  mov     rdx, [rbx+10h]
  ... truncated ...
```
