# YReader::ParseTextDecl(void)

- ea: `0x100409390`
- end: `0x1004098c6`
- name: `?ParseTextDecl@YReader@@AEAAXXZ`
- size: `1334`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x100407620`
- `0x100407ec0`
- `0x10040a020`
- `0x10040a270`
- `0x10040a4c0`

## callees

- `0x100401780`
- `0x100409390`
- `0x10040f160`
- `0x100415560`
- `0x1004394f0`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseTextDecl(YReader *this)
{
  __int64 v1; // rax
  unsigned __int64 v3; // rsi
  unsigned int v4; // eax
  struct BlockAlloc::Header *v5; // rbx
  __int64 v6; // r14
  void *v7; // rdx
  __int64 v8; // rcx
  struct BlockAlloc::Header *v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  unsigned int v12; // eax
  struct BlockAlloc::Header *v13; // rbx
  __int64 v14; // r14
  void *v15; // rdx
  __int64 v16; // rcx
  struct BlockAlloc::Header *v17; // rax
  __int64 v18; // rcx
  unsigned int v19; // eax
  struct BlockAlloc::Header *v20; // rbx
  __int64 v21; // r14
  void *v22; // rdx
  __int64 v23; // rcx
  struct BlockAlloc::Header *v24; // rax
  __int64 v25; // rcx
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
  char v37; // al
  _QWORD *v38; // rcx
  _QWORD *v39; // rax
  void *Buf1; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v41; // [rsp+28h] [rbp-20h]

  v1 = *((_QWORD *)this + 55);
  v41 = 0;
  v3 = *(_QWORD *)(v1 + 16);
  (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
  if ( *((_DWORD *)this + 28) != 12 )
    goto LABEL_61;
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
  v11 = v41;
  if ( v41 == dword_100450B88 && !memcmp(Buf1, CodeStringPtr::version, 2LL * v41) )
  {
    *((_DWORD *)this + 77) = 0x7FFFFFFF;
    (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
    if ( *((_DWORD *)this + 28) != 7 )
      goto LABEL_61;
    v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13));
    v13 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
    v14 = v12;
    v15 = (void *)*((_QWORD *)v13 + 2);
    if ( *((_DWORD *)v13 + 6) - (int)v15 < v12 )
    {
      v16 = *((_QWORD *)v13 + 1);
      if ( v16 )
      {
        while ( 1 )
        {
          v13 = (struct BlockAlloc::Header *)v16;
          if ( *(_DWORD *)(v16 + 24) - (int)v16 - 32 >= v12 )
            break;
          v16 = *(_QWORD *)(v16 + 8);
          if ( !v16 )
            goto LABEL_15;
        }
        *(_QWORD *)(v16 + 16) = v16 + 32;
      }
      else
      {
LABEL_15:
        _mm_lfence();
        v17 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v12, v13);
        *((_QWORD *)v13 + 1) = v17;
        v13 = v17;
      }
      *((_QWORD *)this + 55) = v13;
      v15 = (void *)*((_QWORD *)v13 + 2);
    }
    *((_QWORD *)v13 + 2) += v14;
    v18 = *((_QWORD *)this + 13);
    Buf1 = v15;
    (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v18 + 104LL))(v18, &Buf1);
    if ( v41 != dword_100450B98 )
      goto LABEL_61;
    if ( memcmp(Buf1, CodeStringPtr::opz, 2LL * v41) )
      goto LABEL_61;
    (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
    if ( *((_DWORD *)this + 28) != 12 )
      goto LABEL_61;
    v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13));
    v20 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
    v21 = v19;
    v22 = (void *)*((_QWORD *)v20 + 2);
    if ( *((_DWORD *)v20 + 6) - (int)v22 < v19 )
    {
      v23 = *((_QWORD *)v20 + 1);
      if ( v23 )
      {
        while ( 1 )
        {
          v20 = (struct BlockAlloc::Header *)v23;
          if ( *(_DWORD *)(v23 + 24) - (int)v23 - 32 >= v19 )
            break;
          v23 = *(_QWORD *)(v23 + 8);
          if ( !v23 )
            goto LABEL_24;
        }
        *(_QWORD *)(v23 + 16) = v23 + 32;
      }
      else
      {
LABEL_24:
        _mm_lfence();
        v24 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v19, v20);
        *((_QWORD *)v20 + 1) = v24;
        v20 = v24;
      }
      *((_QWORD *)this + 55) = v20;
      v22 = (void *)*((_QWORD *)v20 + 2);
    }
    *((_QWORD *)v20 + 2) += v21;
    v25 = *((_QWORD *)this + 13);
    Buf1 = v22;
    (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v25 + 104LL))(v25, &Buf1);
    v11 = v41;
  }
  if ( v11 != dword_100450BA8 )
    goto LABEL_61;
  if ( memcmp(Buf1, CodeStringPtr::encoding, 2LL * v11) )
    goto LABEL_61;
  *((_DWORD *)this + 77) = 0x7FFFFFFF;
  (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
  if ( *((_DWORD *)this + 28) != 7 )
    goto LABEL_61;
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
          goto LABEL_34;
      }
      *(_QWORD *)(v30 + 16) = v30 + 32;
    }
    else
    {
LABEL_34:
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
  v33 = v41 - 1;
  if ( !v41 || (unsigned __int16)(*(_WORD *)Buf1 - 65) > 0x19u && (unsigned __int16)(*(_WORD *)Buf1 - 97) > 0x19u )
  {
LABEL_63:
    MXRRaiseException(-1072894399);
    JUMPOUT(0x1004098C5LL);
  }
  v34 = (unsigned __int16 *)((char *)Buf1 + 2);
  if ( v41 != 1 )
  {
    v35 = 0x43FFFFFF01FFBLL;
    do
    {
      v36 = *v34;
      --v33;
      if ( ((unsigned __int16)(v36 - 45) > 0x32u || !_bittest64(&v35, (unsigned int)(v36 - 45)))
        && (unsigned __int16)(v36 - 97) > 0x19u )
      {
        goto LABEL_63;
      }
      ++v34;
    }
    while ( v33 );
  }
  (*((void (__fastcall **)(char *, unsigned __int16 *))this + 27))((char *)this + 40, v34);
  if ( *((_DWORD *)this + 28) != 2 )
  {
LABEL_61:
    MXRRaiseException(-1072894401);
    __debugbreak();
  }
  if ( v41 != dword_100450B38 || memcmp(Buf1, CodeStringPtr::empty, 2LL * v41) )
  {
    v37 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 24LL))(*((_QWORD *)this + 13));
    Scanner::SetEncoding((YReader *)((char *)this + 40), (struct StringPtr *)&Buf1, v37, 0);
  }
  v38 = (_QWORD *)*((_QWORD *)this + 55);
  if ( (unsigned __int64)v38 >= v3 || v3 > v38[2] )
  {
    v38 = (_QWORD *)*v38;
    *((_QWORD *)this + 55) = v38;
    if ( !v38 )
    {
LABEL_62:
      MXRRaiseException(-2147467259);
      __debugbreak();
    }
    while ( (unsigned __int64)v38 >= v3 || v3 > v38[3] )
    {
      v39 = (_QWORD *)*v38;
      *((_QWORD *)this + 55) = *v38;
      v38 = v39;
      if ( !v39 )
        goto LABEL_62;
    }
  }
  v38[2] = v3;
}

```

## disassembly

```asm
0x100409390  mov     [rsp+arg_0], rbx
0x100409395  mov     [rsp+arg_8], rbp
0x10040939a  mov     [rsp+arg_10], rsi
0x10040939f  push    rdi
0x1004093a0  push    r14
0x1004093a2  push    r15
0x1004093a4  sub     rsp, 30h
0x1004093a8  mov     rax, [rcx+1B8h]
0x1004093af  mov     rdi, rcx
0x1004093b2  mov     [rsp+48h+var_20], 0
0x1004093ba  add     rcx, 28h ; '('
0x1004093be  mov     rsi, [rax+10h]
0x1004093c2  mov     rax, [rdi+0D8h]
0x1004093c9  call    cs:__guard_dispatch_icall_fptr
0x1004093cf  cmp     dword ptr [rdi+70h], 0Ch
0x1004093d3  jnz     loc_1004098A5
0x1004093d9  mov     rcx, [rdi+68h]
0x1004093dd  mov     rax, [rcx]
0x1004093e0  mov     rax, [rax+60h]
0x1004093e4  call    cs:__guard_dispatch_icall_fptr
0x1004093ea  mov     rbx, [rdi+1B8h]
0x1004093f1  mov     r14d, eax
0x1004093f4  mov     rdx, [rbx+10h]
0x1004093f8  mov     ecx, [rbx+18h]
0x1004093fb  sub     ecx, edx
0x1004093fd  cmp     ecx, eax
0x1004093ff  jnb     short loc_100409454
0x100409401  mov     rcx, [rbx+8]
0x100409405  test    rcx, rcx
0x100409408  jz      short loc_10040942D
0x10040940a  nop     word ptr [rax+rax+00h]
0x100409410  mov     eax, [rcx+18h]
0x100409413  mov     rbx, rcx
0x100409416  sub     eax, ecx
0x100409418  sub     eax, 20h ; ' '
0x10040941b  cmp     eax, r14d
0x10040941e  jnb     loc_100409843
0x100409424  mov     rcx, [rcx+8]
0x100409428  test    rcx, rcx
0x10040942b  jnz     short loc_100409410
0x10040942d  lfence
0x100409430  mov     r8, rbx; struct BlockAlloc::Header *
0x100409433  lea     rcx, [rdi+1A0h]; this
0x10040943a  mov     edx, r14d; unsigned int
0x10040943d  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x100409442  mov     [rbx+8], rax
0x100409446  mov     rbx, rax
0x100409449  mov     [rdi+1B8h], rbx
0x100409450  mov     rdx, [rbx+10h]
0x100409454  add     [rbx+10h], r14
0x100409458  mov     rcx, [rdi+68h]
0x10040945c  mov     [rsp+48h+Buf1], rdx
0x100409461  lea     rdx, [rsp+48h+Buf1]
0x100409466  mov     rax, [rcx]
0x100409469  mov     rax, [rax+68h]
0x10040946d  call    cs:__guard_dispatch_icall_fptr
0x100409473  mov     ebx, [rsp+48h+var_20]
0x100409477  cmp     ebx, cs:dword_100450B88
0x10040947d  jnz     loc_100409647
0x100409483  mov     rdx, cs:?version@CodeStringPtr@@2UStringPtr@@A; Buf2
0x10040948a  mov     r8d, ebx
0x10040948d  mov     rcx, [rsp+48h+Buf1]; Buf1
0x100409492  add     r8, r8; Size
0x100409495  call    memcmp
0x10040949a  test    eax, eax
0x10040949c  jnz     loc_100409647
0x1004094a2  mov     dword ptr [rdi+134h], 7FFFFFFFh
0x1004094ac  lea     rcx, [rdi+28h]
0x1004094b0  mov     rax, [rdi+0D8h]
0x1004094b7  call    cs:__guard_dispatch_icall_fptr
0x1004094bd  cmp     dword ptr [rdi+70h], 7
0x1004094c1  jnz     loc_1004098A5
0x1004094c7  mov     rcx, [rdi+68h]
0x1004094cb  mov     rax, [rcx]
0x1004094ce  mov     rax, [rax+60h]
0x1004094d2  call    cs:__guard_dispatch_icall_fptr
0x1004094d8  mov     rbx, [rdi+1B8h]
0x1004094df  mov     r14d, eax
0x1004094e2  mov     rdx, [rbx+10h]
0x1004094e6  mov     ecx, [rbx+18h]
0x1004094e9  sub     ecx, edx
0x1004094eb  cmp     ecx, eax
0x1004094ed  jnb     short loc_100409544
0x1004094ef  mov     rcx, [rbx+8]
0x1004094f3  test    rcx, rcx
0x1004094f6  jz      short loc_10040951D
0x1004094f8  nop     dword ptr [rax+rax+00000000h]
0x100409500  mov     eax, [rcx+18h]
0x100409503  mov     rbx, rcx
0x100409506  sub     eax, ecx
0x100409508  sub     eax, 20h ; ' '
0x10040950b  cmp     eax, r14d
0x10040950e  jnb     loc_100409850
0x100409514  mov     rcx, [rcx+8]
0x100409518  test    rcx, rcx
0x10040951b  jnz     short loc_100409500
0x10040951d  lfence
0x100409520  mov     r8, rbx; struct BlockAlloc::Header *
0x100409523  lea     rcx, [rdi+1A0h]; this
0x10040952a  mov     edx, r14d; unsigned int
0x10040952d  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x100409532  mov     [rbx+8], rax
0x100409536  mov     rbx, rax
0x100409539  mov     [rdi+1B8h], rbx
0x100409540  mov     rdx, [rbx+10h]
0x100409544  add     [rbx+10h], r14
0x100409548  mov     rcx, [rdi+68h]
0x10040954c  mov     [rsp+48h+Buf1], rdx
0x100409551  lea     rdx, [rsp+48h+Buf1]
0x100409556  mov     rax, [rcx]
0x100409559  mov     rax, [rax+68h]
0x10040955d  call    cs:__guard_dispatch_icall_fptr
0x100409563  mov     eax, [rsp+48h+var_20]
0x100409567  cmp     eax, cs:dword_100450B98
0x10040956d  jnz     loc_1004098A5
0x100409573  mov     rdx, cs:?opz@CodeStringPtr@@2UStringPtr@@A; Buf2
0x10040957a  mov     r8d, eax
0x10040957d  mov     rcx, [rsp+48h+Buf1]; Buf1
0x100409582  add     r8, r8; Size
0x100409585  call    memcmp
0x10040958a  test    eax, eax
0x10040958c  jnz     loc_1004098A5
0x100409592  mov     rax, [rdi+0D8h]
0x100409599  lea     rcx, [rdi+28h]
0x10040959d  call    cs:__guard_dispatch_icall_fptr
0x1004095a3  cmp     dword ptr [rdi+70h], 0Ch
0x1004095a7  jnz     loc_1004098A5
0x1004095ad  mov     rcx, [rdi+68h]
0x1004095b1  mov     rax, [rcx]
0x1004095b4  mov     rax, [rax+60h]
0x1004095b8  call    cs:__guard_dispatch_icall_fptr
0x1004095be  mov     rbx, [rdi+1B8h]
0x1004095c5  mov     r14d, eax
0x1004095c8  mov     rdx, [rbx+10h]
0x1004095cc  mov     ecx, [rbx+18h]
0x1004095cf  sub     ecx, edx
0x1004095d1  cmp     ecx, eax
0x1004095d3  jnb     short loc_100409624
0x1004095d5  mov     rcx, [rbx+8]
0x1004095d9  test    rcx, rcx
0x1004095dc  jz      short loc_1004095FD
0x1004095de  xchg    ax, ax
0x1004095e0  mov     eax, [rcx+18h]
0x1004095e3  mov     rbx, rcx
0x1004095e6  sub     eax, ecx
0x1004095e8  sub     eax, 20h ; ' '
0x1004095eb  cmp     eax, r14d
0x1004095ee  jnb     loc_10040985D
0x1004095f4  mov     rcx, [rcx+8]
0x1004095f8  test    rcx, rcx
0x1004095fb  jnz     short loc_1004095E0
0x1004095fd  lfence
0x100409600  mov     r8, rbx; struct BlockAlloc::Header *
0x100409603  lea     rcx, [rdi+1A0h]; this
0x10040960a  mov     edx, r14d; unsigned int
0x10040960d  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x100409612  mov     [rbx+8], rax
0x100409616  mov     rbx, rax
0x100409619  mov     [rdi+1B8h], rbx
0x100409620  mov     rdx, [rbx+10h]
0x100409624  add     [rbx+10h], r14
0x100409628  mov     rcx, [rdi+68h]
0x10040962c  mov     [rsp+48h+Buf1], rdx
0x100409631  lea     rdx, [rsp+48h+Buf1]
0x100409636  mov     rax, [rcx]
0x100409639  mov     rax, [rax+68h]
0x10040963d  call    cs:__guard_dispatch_icall_fptr
0x100409643  mov     ebx, [rsp+48h+var_20]
0x100409647  cmp     ebx, cs:dword_100450BA8
0x10040964d  jnz     loc_1004098A5
0x100409653  mov     rdx, cs:?encoding@CodeStringPtr@@2UStringPtr@@A; Buf2
0x10040965a  mov     rcx, [rsp+48h+Buf1]; Buf1
0x10040965f  mov     r8d, ebx
0x100409662  add     r8, r8; Size
0x100409665  call    memcmp
0x10040966a  test    eax, eax
0x10040966c  jnz     loc_1004098A5
0x100409672  mov     dword ptr [rdi+134h], 7FFFFFFFh
0x10040967c  lea     rcx, [rdi+28h]
0x100409680  mov     rax, [rdi+0D8h]
0x100409687  call    cs:__guard_dispatch_icall_fptr
0x10040968d  cmp     dword ptr [rdi+70h], 7
0x100409691  jnz     loc_1004098A5
0x100409697  mov     rcx, [rdi+68h]
0x10040969b  mov     rax, [rcx]
0x10040969e  mov     rax, [rax+60h]
0x1004096a2  call    cs:__guard_dispatch_icall_fptr
0x1004096a8  mov     rbx, [rdi+1B8h]
0x1004096af  mov     r14d, eax
0x1004096b2  mov     rdx, [rbx+10h]
0x1004096b6  mov     ecx, [rbx+18h]
0x1004096b9  sub     ecx, edx
0x1004096bb  cmp     ecx, eax
0x1004096bd  jnb     short loc_100409714
0x1004096bf  mov     rcx, [rbx+8]
0x1004096c3  test    rcx, rcx
0x1004096c6  jz      short loc_1004096ED
0x1004096c8  nop     dword ptr [rax+rax+00000000h]
0x1004096d0  mov     eax, [rcx+18h]
0x1004096d3  mov     rbx, rcx
0x1004096d6  sub     eax, ecx
0x1004096d8  sub     eax, 20h ; ' '
0x1004096db  cmp     eax, r14d
0x1004096de  jnb     loc_10040986A
0x1004096e4  mov     rcx, [rcx+8]
0x1004096e8  test    rcx, rcx
0x1004096eb  jnz     short loc_1004096D0
0x1004096ed  lfence
0x1004096f0  mov     r8, rbx; struct BlockAlloc::Header *
0x1004096f3  lea     rcx, [rdi+1A0h]; this
0x1004096fa  mov     edx, r14d; unsigned int
0x1004096fd  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x100409702  mov     [rbx+8], rax
0x100409706  mov     rbx, rax
0x100409709  mov     [rdi+1B8h], rbx
0x100409710  mov     rdx, [rbx+10h]
0x100409714  add     [rbx+10h], r14
0x100409718  mov     rcx, [rdi+68h]
0x10040971c  mov     [rsp+48h+Buf1], rdx
0x100409721  lea     rdx, [rsp+48h+Buf1]
0x100409726  mov     rax, [rcx]
0x100409729  mov     rax, [rax+68h]
0x10040972d  call    cs:__guard_dispatch_icall_fptr
0x100409733  mov     eax, [rsp+48h+var_20]
0x100409737  lea     r8d, [rax-1]
0x10040973b  test    eax, eax
0x10040973d  jz      loc_1004098BB
0x100409743  mov     rdx, [rsp+48h+Buf1]
0x100409748  movzx   ecx, word ptr [rdx]
0x10040974b  lea     eax, [rcx-41h]
0x10040974e  cmp     ax, 19h
0x100409752  jbe     short loc_100409762
0x100409754  sub     cx, 61h ; 'a'
0x100409758  cmp     cx, 19h
0x10040975c  ja      loc_1004098BB
0x100409762  add     rdx, 2
0x100409766  test    r8d, r8d
0x100409769  jz      short loc_1004097AC
0x10040976b  mov     r9, 43FFFFFF01FFBh
0x100409775  nop     word ptr [rax+rax+00000000h]
0x100409780  movzx   ecx, word ptr [rdx]
0x100409783  dec     r8d
0x100409786  lea     eax, [rcx-2Dh]
0x100409789  cmp     ax, 32h ; '2'
0x10040978d  ja      short loc_100409795
0x10040978f  bt      r9, rax
0x100409793  jb      short loc_1004097A3
0x100409795  sub     cx, 61h ; 'a'
0x100409799  cmp     cx, 19h
0x10040979d  ja      loc_1004098BB
0x1004097a3  add     rdx, 2
0x1004097a7  test    r8d, r8d
0x1004097aa  jnz     short loc_100409780
0x1004097ac  mov     rax, [rdi+0D8h]
0x1004097b3  lea     rcx, [rdi+28h]
0x1004097b7  call    cs:__guard_dispatch_icall_fptr
0x1004097bd  cmp     dword ptr [rdi+70h], 2
0x1004097c1  jnz     loc_1004098A5
0x1004097c7  mov     eax, [rsp+48h+var_20]
0x1004097cb  cmp     eax, cs:dword_100450B38
0x1004097d1  jnz     short loc_1004097EE
0x1004097d3  mov     rdx, cs:?empty@CodeStringPtr@@2UStringPtr@@A; Buf2
0x1004097da  mov     r8d, eax
0x1004097dd  mov     rcx, [rsp+48h+Buf1]; Buf1
0x1004097e2  add     r8, r8; Size
0x1004097e5  call    memcmp
0x1004097ea  test    eax, eax
0x1004097ec  jz      short loc_100409814
0x1004097ee  mov     rcx, [rdi+68h]
0x1004097f2  mov     rax, [rcx]
0x1004097f5  mov     rax, [rax+18h]
0x1004097f9  call    cs:__guard_dispatch_icall_fptr
0x1004097ff  xor     r9d, r9d; bool
0x100409802  lea     rdx, [rsp+48h+Buf1]; struct StringPtr *
0x100409807  movzx   r8d, al; bool
0x10040980b  lea     rcx, [rdi+28h]; this
0x10040980f  call    ?SetEncoding@Scanner@@AEAAXPEAUStringPtr@@_N1@Z; Scanner::SetEncoding(StringPtr *,bool,bool)
0x100409814  mov     rcx, [rdi+1B8h]
0x10040981b  cmp     rcx, rsi
0x10040981e  jnb     short loc_100409877
0x100409820  cmp     rsi, [rcx+10h]
0x100409824  ja      short loc_100409877
0x100409826  mov     rbx, [rsp+48h+arg_0]
0x10040982b  mov     rbp, [rsp+48h+arg_8]
0x100409830  mov     [rcx+10h], rsi
0x100409834  mov     rsi, [rsp+48h+arg_10]
0x100409839  add     rsp, 30h
0x10040983d  pop     r15
0x10040983f  pop     r14
0x100409841  pop     rdi
0x100409842  retn
0x100409843  lea     rax, [rcx+20h]
0x100409847  mov     [rcx+10h], rax
0x10040984b  jmp     loc_100409449
0x100409850  lea     rax, [rcx+20h]
0x100409854  mov     [rcx+10h], rax
0x100409858  jmp     loc_100409539
0x10040985d  lea     rax, [rcx+20h]
0x100409861  mov     [rcx+10h], rax
0x100409865  jmp     loc_100409619
  ... truncated ...
```
