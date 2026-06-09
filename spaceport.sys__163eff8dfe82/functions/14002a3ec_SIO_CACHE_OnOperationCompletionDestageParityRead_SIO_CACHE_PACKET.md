# SIO_CACHE::OnOperationCompletionDestageParityRead(SIO_CACHE_PACKET *)

- ea: `0x14002a3ec`
- end: `0x14002a7f7`
- name: `?OnOperationCompletionDestageParityRead@SIO_CACHE@@IEAAJPEAVSIO_CACHE_PACKET@@@Z`
- size: `1035`
- prototype: `int(SIO_CACHE *__hidden this, struct SIO_CACHE_PACKET *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400471dc`

## callees

- `0x14000aca0`
- `0x140016160`
- `0x140019650`
- `0x14001b090`
- `0x14002a3ec`
- `0x14002a800`
- `0x140068150`
- `0x140068600`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002a7d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a7d7`

## pseudocode

```c
__int64 __fastcall SIO_CACHE::OnOperationCompletionDestageParityRead(SIO_CACHE *this, struct SIO_CACHE_PACKET *a2)
{
  __int64 v3; // rcx
  struct SIO_CACHE_PACKET *v4; // r13
  __int64 v5; // rax
  int v6; // edi
  __int64 v7; // r14
  __int64 v8; // rcx
  SIO_RAID5 *v9; // rax
  unsigned __int64 v10; // rcx
  SIO_RAID5 *v11; // rsi
  _QWORD *v12; // r11
  unsigned __int64 v13; // rdx
  _QWORD *v14; // rbx
  _QWORD *v15; // rax
  _QWORD *v16; // rcx
  _QWORD *v17; // rcx
  _QWORD *v18; // rcx
  __int128 *v19; // rbx
  __int128 *v20; // r15
  _QWORD *v21; // rdi
  struct SP_RESILIENCY_INFO *v22; // rax
  unsigned int *v23; // rsi
  __int128 *v24; // r12
  __int64 v25; // rcx
  __int128 **v26; // rax
  unsigned int v27; // eax
  __int64 v28; // r11
  __int128 *v29; // rsi
  SIO_RAID5 *v30; // r13
  unsigned __int64 v31; // rdi
  __int64 v32; // rbx
  __int128 *v33; // rax
  struct SIO_CACHE_PACKET *v34; // rdx
  __int64 v35; // rcx
  __int128 **v36; // r8
  __int128 *v37; // r11
  __int128 *v38; // rax
  __int128 *v39; // rbx
  __int128 *v40; // rdx
  __int128 **v41; // r8
  unsigned __int64 v43; // [rsp+20h] [rbp-48h]
  __int64 v44; // [rsp+28h] [rbp-40h]
  _QWORD *v45; // [rsp+30h] [rbp-38h]
  __int64 v46; // [rsp+38h] [rbp-30h]
  __int128 v47; // [rsp+40h] [rbp-28h] BYREF
  __int128 v48; // [rsp+50h] [rbp-18h] BYREF
  unsigned int v49; // [rsp+B0h] [rbp+48h] BYREF
  struct SIO_CACHE_PACKET *v50; // [rsp+B8h] [rbp+50h]
  int v51; // [rsp+C0h] [rbp+58h]
  SIO_RAID5 *v52; // [rsp+C8h] [rbp+60h]

  v50 = a2;
  v49 = 0;
  v3 = *((_QWORD *)this + 1);
  v4 = a2;
  v48 = 0;
  v47 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 80LL))(v3);
  v6 = *((_DWORD *)v4 + 45);
  v7 = *((_QWORD *)v4 + 24);
  *((_QWORD *)v4 + 24) = 0;
  v46 = v5;
  v51 = v6;
  if ( v6 >= 0 )
  {
    v8 = *(_QWORD *)(v5 + 392);
    v44 = *((_QWORD *)v4 + 16);
    v9 = (SIO_RAID5 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 104LL))(v8, *(_QWORD *)(v44 + 32));
    v10 = *((unsigned int *)this + 118);
    v11 = v9;
    v52 = v9;
    v12 = (_QWORD *)*((_QWORD *)v4 + 5);
    v43 = (*(_QWORD *)(v44 + 32) - *((_QWORD *)v9 + 2)) / v10;
    v13 = v43;
    *((_QWORD *)&v48 + 1) = &v48;
    *(_QWORD *)&v48 = &v48;
    *((_QWORD *)&v47 + 1) = &v47;
    *(_QWORD *)&v47 = &v47;
    if ( v12 != (_QWORD *)((char *)v4 + 40) )
    {
      v14 = (_QWORD *)*v12;
      v15 = (_QWORD *)*v12;
      while ( (_QWORD *)v15[1] == v12 )
      {
        v16 = (_QWORD *)v12[1];
        if ( (_QWORD *)*v16 != v12 )
          break;
        *v16 = v15;
        v15[1] = v16;
        v12[1] = v12;
        *v12 = v12;
        if ( *((_BYTE *)v12 + 114) == 22
          || SIO_RAID5::UnRotate(v11, v13, *((_DWORD *)v12 + 23)) < *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v11 + 1) + 384LL)
                                                                              + 40LL) )
        {
          v18 = (_QWORD *)*((_QWORD *)&v48 + 1);
          if ( **((__int128 ***)&v48 + 1) != &v48 )
            break;
          v12[25] = *((_QWORD *)&v48 + 1);
          v12[24] = &v48;
          *v18 = v12 + 24;
          *((_QWORD *)&v48 + 1) = v12 + 24;
        }
        else
        {
          v17 = (_QWORD *)*((_QWORD *)&v47 + 1);
          if ( **((__int128 ***)&v47 + 1) != &v47 )
            break;
          v12[25] = *((_QWORD *)&v47 + 1);
          v12[24] = &v47;
          *v17 = v12 + 24;
          *((_QWORD *)&v47 + 1) = v12 + 24;
        }
        if ( v14 == (_QWORD *)((char *)v4 + 40) )
          goto LABEL_14;
        v15 = (_QWORD *)*v14;
        v12 = v14;
        v13 = v43;
        v14 = (_QWORD *)*v14;
      }
LABEL_38:
      __fastfail(3u);
    }
LABEL_14:
    v19 = (__int128 *)v48;
    v20 = *(__int128 **)v48;
    if ( (__int128 *)v48 != &v48 )
    {
      while ( 1 )
      {
        v21 = (_QWORD *)v19 - 31;
        v45 = (_QWORD *)v19 - 31;
        v22 = SIO_RAID::Resiliency(v11);
        memset((void *)(v7 + 16), 0, 8LL * *((unsigned int *)v22 + 4));
        v23 = (unsigned int *)v19 - 25;
        v24 = v19 - 7;
        if ( *((_BYTE *)v19 - 78) == 22 )
        {
          *(_QWORD *)v24 = SIO_RAID5::ObjectToColumn(
                             v52,
                             *(_QWORD *)v24 + *(_QWORD *)(v44 + 32) - *(_QWORD *)(v44 + 40) - *((_QWORD *)v52 + 2),
                             &v49);
          *v23 = v49;
          v21[30] = v52;
          *((_BYTE *)v21 + 168) = 4;
          *((_BYTE *)v21 + 170) = 1;
          v25 = *(_QWORD *)v19;
          if ( *(__int128 **)(*(_QWORD *)v19 + 8LL) != v19 )
            goto LABEL_38;
          v26 = (__int128 **)*((_QWORD *)v19 + 1);
          if ( *v26 != v19 )
            goto LABEL_38;
          *v26 = (__int128 *)v25;
          *(_QWORD *)(v25 + 8) = v26;
          *((_QWORD *)v19 + 1) = v19;
          *(_QWORD *)v19 = v19;
          SIO_CACHE_PACKET::AttachDestage(v4, (struct SIO_CACHE_PACKET *)((char *)v19 - 248));
        }
        v27 = SIO_RAID5::UnRotate(v52, v43, *v23);
        *(_QWORD *)(v7 + 8LL * v27 + 16) = v28;
        v29 = (__int128 *)v47;
        if ( (__int128 *)v47 != &v47 )
        {
          v30 = v52;
          v31 = v43;
          do
          {
            v32 = *(_QWORD *)v24
                + *(_QWORD *)(*((_QWORD *)v29 - 16) + 32LL)
                + *(unsigned int *)(*((_QWORD *)v29 - 16) + 44LL)
                - *((_QWORD *)v29 - 14);
            *(_QWORD *)(v7 + 8LL * SIO_RAID5::UnRotate(v30, v31, *((_DWORD *)v29 - 25)) + 16) = v32;
            v29 = *(__int128 **)v29;
          }
          while ( v29 != &v47 );
          v21 = v45;
          v4 = v50;
        }
        SC_PARITY::Execute(*(SC_PARITY **)(v46 + 384), (struct SC_PARITY_CONTEXT *)v7, *((_DWORD *)v21 + 36), 1u);
        if ( v20 == &v48 )
          break;
        v11 = v52;
        v19 = v20;
        v20 = *(__int128 **)v20;
      }
    }
    v33 = (__int128 *)v47;
    if ( (__int128 *)v47 != &v47 )
    {
      while ( 1 )
      {
        v34 = (struct SIO_CACHE_PACKET *)((char *)v33 - 248);
        *((_BYTE *)v34 + 168) = 4;
        *((_BYTE *)v34 + 170) = 1;
        v35 = *(_QWORD *)v33;
        if ( *(__int128 **)(*(_QWORD *)v33 + 8LL) != v33 )
          goto LABEL_38;
        v36 = (__int128 **)*((_QWORD *)v33 + 1);
        if ( *v36 != v33 )
          goto LABEL_38;
        *v36 = (__int128 *)v35;
        *(_QWORD *)(v35 + 8) = v36;
        *((_QWORD *)v33 + 1) = v33;
        *(_QWORD *)v33 = v33;
        SIO_CACHE_PACKET::AttachDestage(v4, v34);
        if ( v37 == &v47 )
          break;
        v33 = v37;
      }
    }
    v38 = (__int128 *)v48;
    if ( (__int128 *)v48 != &v48 )
    {
      v39 = *(__int128 **)v48;
      v40 = *(__int128 **)v48;
      while ( *((__int128 **)v40 + 1) == v38 )
      {
        v41 = (__int128 **)*((_QWORD *)v38 + 1);
        if ( *v41 != v38 )
          break;
        *v41 = v40;
        *((_QWORD *)v40 + 1) = v41;
        if ( v38 != (__int128 *)248 )
          (**((void (__fastcall ***)(__int64, __int64))v38 - 31))((__int64)v38 - 248, 1);
        if ( v39 == &v48 )
          goto LABEL_39;
        v40 = *(__int128 **)v39;
        v38 = v39;
        v39 = *(__int128 **)v39;
      }
      goto LABEL_38;
    }
LABEL_39:
    v6 = v51;
  }
  if ( v7 )
    ExFreePoolWithTag((PVOID)v7, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14002a3ec  mov     [rsp-40h+arg_8], rdx
0x14002a3f1  push    rbp
0x14002a3f2  push    rbx
0x14002a3f3  push    rsi
0x14002a3f4  push    rdi
0x14002a3f5  push    r12
0x14002a3f7  push    r13
0x14002a3f9  push    r14
0x14002a3fb  push    r15
0x14002a3fd  mov     rbp, rsp
0x14002a400  sub     rsp, 68h
0x14002a404  mov     rbx, rcx
0x14002a407  mov     [rbp+arg_0], 0
0x14002a40e  mov     rcx, [rcx+8]
0x14002a412  xorps   xmm0, xmm0
0x14002a415  xorps   xmm1, xmm1
0x14002a418  mov     r13, rdx
0x14002a41b  movups  [rbp+var_18], xmm0
0x14002a41f  movups  [rbp+var_28], xmm1
0x14002a423  mov     rax, [rcx]
0x14002a426  mov     rax, [rax+50h]
0x14002a42a  call    _guard_dispatch_icall
0x14002a42f  mov     edi, [r13+0B4h]
0x14002a436  mov     r14, [r13+0C0h]
0x14002a43d  mov     qword ptr [r13+0C0h], 0
0x14002a448  mov     [rbp+var_30], rax
0x14002a44c  mov     [rbp+arg_10], edi
0x14002a44f  test    edi, edi
0x14002a451  js      loc_14002A7CD
0x14002a457  mov     rcx, [rax+188h]
0x14002a45e  mov     rdi, [r13+80h]
0x14002a465  mov     [rbp+var_40], rdi
0x14002a469  mov     rdx, [rcx]
0x14002a46c  mov     rax, [rdx+68h]
0x14002a470  mov     rdx, [rdi+20h]
0x14002a474  call    _guard_dispatch_icall
0x14002a479  mov     ecx, [rbx+1D8h]
0x14002a47f  mov     rsi, rax
0x14002a482  mov     [rbp+arg_18], rax
0x14002a486  xor     edx, edx
0x14002a488  mov     rax, [rdi+20h]
0x14002a48c  lea     rdi, [r13+28h]
0x14002a490  mov     r11, [rdi]
0x14002a493  sub     rax, [rsi+10h]
0x14002a497  div     rcx
0x14002a49a  mov     [rbp+var_48], rax
0x14002a49e  mov     rdx, rax; unsigned __int64
0x14002a4a1  lea     rax, [rbp+var_18]
0x14002a4a5  mov     qword ptr [rbp+var_18+8], rax
0x14002a4a9  lea     rax, [rbp+var_18]
0x14002a4ad  mov     qword ptr [rbp+var_18], rax
0x14002a4b1  lea     rax, [rbp+var_28]
0x14002a4b5  mov     qword ptr [rbp+var_28+8], rax
0x14002a4b9  lea     rax, [rbp+var_28]
0x14002a4bd  mov     qword ptr [rbp+var_28], rax
0x14002a4c1  cmp     r11, rdi
0x14002a4c4  jz      loc_14002A58B
0x14002a4ca  mov     rbx, [r11]
0x14002a4cd  mov     rax, rbx
0x14002a4d0  cmp     [rax+8], r11
0x14002a4d4  jnz     loc_14002A7C3
0x14002a4da  mov     rcx, [r11+8]
0x14002a4de  cmp     [rcx], r11
0x14002a4e1  jnz     loc_14002A7C3
0x14002a4e7  mov     [rcx], rax
0x14002a4ea  mov     [rax+8], rcx
0x14002a4ee  mov     [r11+8], r11
0x14002a4f2  mov     [r11], r11
0x14002a4f5  cmp     byte ptr [r11+72h], 16h
0x14002a4fa  jz      short loc_14002A547
0x14002a4fc  mov     r8d, [r11+5Ch]; unsigned int
0x14002a500  mov     rcx, rsi; this
0x14002a503  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14002a508  mov     rcx, [rsi+8]
0x14002a50c  mov     rdx, [rcx+180h]
0x14002a513  cmp     eax, [rdx+28h]
0x14002a516  jb      short loc_14002A547
0x14002a518  mov     rcx, qword ptr [rbp+var_28+8]
0x14002a51c  lea     rax, [rbp+var_28]
0x14002a520  cmp     [rcx], rax
0x14002a523  jnz     loc_14002A7C3
0x14002a529  lea     rax, [r11+0C0h]
0x14002a530  mov     [r11+0C8h], rcx
0x14002a537  lea     rdx, [rbp+var_28]
0x14002a53b  mov     [rax], rdx
0x14002a53e  mov     [rcx], rax
0x14002a541  mov     qword ptr [rbp+var_28+8], rax
0x14002a545  jmp     short loc_14002A574
0x14002a547  mov     rcx, qword ptr [rbp+var_18+8]
0x14002a54b  lea     rax, [rbp+var_18]
0x14002a54f  cmp     [rcx], rax
0x14002a552  jnz     loc_14002A7C3
0x14002a558  lea     rax, [r11+0C0h]
0x14002a55f  mov     [r11+0C8h], rcx
0x14002a566  lea     rdx, [rbp+var_18]
0x14002a56a  mov     [rax], rdx
0x14002a56d  mov     [rcx], rax
0x14002a570  mov     qword ptr [rbp+var_18+8], rax
0x14002a574  cmp     rbx, rdi
0x14002a577  jz      short loc_14002A58B
0x14002a579  mov     rax, [rbx]
0x14002a57c  mov     r11, rbx
0x14002a57f  mov     rdx, [rbp+var_48]
0x14002a583  mov     rbx, rax
0x14002a586  jmp     loc_14002A4D0
0x14002a58b  mov     rbx, qword ptr [rbp+var_18]
0x14002a58f  lea     rax, [rbp+var_18]
0x14002a593  mov     r15, [rbx]
0x14002a596  cmp     rbx, rax
0x14002a599  jz      loc_14002A704
0x14002a59f  lea     rdi, [rbx-0F8h]
0x14002a5a6  mov     rcx, rsi; this
0x14002a5a9  mov     [rbp+var_38], rdi
0x14002a5ad  lea     r12, [r14+10h]
0x14002a5b1  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14002a5b6  xor     edx, edx; Val
0x14002a5b8  mov     rcx, r12; void *
0x14002a5bb  mov     r8d, [rax+10h]
0x14002a5bf  shl     r8, 3; Size
0x14002a5c3  call    memset
0x14002a5c8  cmp     byte ptr [rdi+0AAh], 16h
0x14002a5cf  lea     rsi, [rdi+94h]
0x14002a5d6  lea     r12, [rdi+88h]
0x14002a5dd  jnz     short loc_14002A658
0x14002a5df  mov     rcx, [rbp+var_40]
0x14002a5e3  lea     r8, [rbp+arg_0]; unsigned int *
0x14002a5e7  mov     rax, [rbp+arg_18]
0x14002a5eb  mov     rdx, [rcx+20h]
0x14002a5ef  sub     rdx, [rcx+28h]
0x14002a5f3  mov     rcx, rax; this
0x14002a5f6  sub     rdx, [rax+10h]
0x14002a5fa  add     rdx, [r12]; unsigned __int64
0x14002a5fe  call    ?ObjectToColumn@SIO_RAID5@@UEAA_K_KPEAK@Z; SIO_RAID5::ObjectToColumn(unsigned __int64,ulong *)
0x14002a603  mov     [r12], rax
0x14002a607  mov     eax, [rbp+arg_0]
0x14002a60a  mov     [rsi], eax
0x14002a60c  mov     rax, [rbp+arg_18]
0x14002a610  mov     [rdi+0F0h], rax
0x14002a617  mov     byte ptr [rdi+0A8h], 4
0x14002a61e  mov     byte ptr [rdi+0AAh], 1
0x14002a625  mov     rcx, [rbx]
0x14002a628  cmp     [rcx+8], rbx
0x14002a62c  jnz     loc_14002A7C3
0x14002a632  mov     rax, [rbx+8]
0x14002a636  cmp     [rax], rbx
0x14002a639  jnz     loc_14002A7C3
0x14002a63f  mov     [rax], rcx
0x14002a642  mov     rdx, rdi; struct SIO_CACHE_PACKET *
0x14002a645  mov     [rcx+8], rax
0x14002a649  mov     rcx, r13; this
0x14002a64c  mov     [rbx+8], rbx
0x14002a650  mov     [rbx], rbx
0x14002a653  call    ?AttachDestage@SIO_CACHE_PACKET@@QEAAXPEAV1@@Z; SIO_CACHE_PACKET::AttachDestage(SIO_CACHE_PACKET *)
0x14002a658  mov     rax, [rdi+78h]
0x14002a65c  mov     rdx, [rbp+var_48]; unsigned __int64
0x14002a660  mov     rcx, [rbp+arg_18]; this
0x14002a664  mov     r8d, [rsi]; unsigned int
0x14002a667  mov     r11d, [rax+2Ch]
0x14002a66b  add     r11, [rax+20h]
0x14002a66f  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14002a674  mov     r8d, eax
0x14002a677  lea     rax, [rbp+var_28]
0x14002a67b  mov     [r14+r8*8+10h], r11
0x14002a680  mov     rsi, qword ptr [rbp+var_28]
0x14002a684  cmp     rsi, rax
0x14002a687  jz      short loc_14002A6CF
0x14002a689  mov     r13, [rbp+arg_18]
0x14002a68d  mov     rdi, [rbp+var_48]
0x14002a691  mov     rax, [rsi-80h]
0x14002a695  mov     rdx, rdi; unsigned __int64
0x14002a698  mov     r8d, [rsi-64h]; unsigned int
0x14002a69c  mov     rcx, r13; this
0x14002a69f  mov     ebx, [rax+2Ch]
0x14002a6a2  sub     rbx, [rsi-70h]
0x14002a6a6  add     rbx, [rax+20h]
0x14002a6aa  add     rbx, [r12]
0x14002a6ae  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14002a6b3  mov     r11d, eax
0x14002a6b6  lea     rax, [rbp+var_28]
0x14002a6ba  mov     [r14+r11*8+10h], rbx
0x14002a6bf  mov     rsi, [rsi]
0x14002a6c2  cmp     rsi, rax
0x14002a6c5  jnz     short loc_14002A691
0x14002a6c7  mov     rdi, [rbp+var_38]
0x14002a6cb  mov     r13, [rbp+arg_8]
0x14002a6cf  mov     rax, [rbp+var_30]
0x14002a6d3  mov     r9b, 1; unsigned __int8
0x14002a6d6  mov     r8d, [rdi+90h]; unsigned int
0x14002a6dd  mov     rdx, r14; struct SC_PARITY_CONTEXT *
0x14002a6e0  mov     rcx, [rax+180h]; this
0x14002a6e7  call    ?Execute@SC_PARITY@@QEAAXPEAVSC_PARITY_CONTEXT@@KE@Z; SC_PARITY::Execute(SC_PARITY_CONTEXT *,ulong,uchar)
0x14002a6ec  lea     rax, [rbp+var_18]
0x14002a6f0  cmp     r15, rax
0x14002a6f3  jz      short loc_14002A704
0x14002a6f5  mov     rsi, [rbp+arg_18]
0x14002a6f9  mov     rbx, r15
0x14002a6fc  mov     r15, [r15]
0x14002a6ff  jmp     loc_14002A59F
0x14002a704  mov     rax, qword ptr [rbp+var_28]
0x14002a708  lea     rcx, [rbp+var_28]
0x14002a70c  mov     r11, [rax]
0x14002a70f  cmp     rax, rcx
0x14002a712  jz      short loc_14002A76A
0x14002a714  lea     rdx, [rax-0F8h]; struct SIO_CACHE_PACKET *
0x14002a71b  mov     byte ptr [rdx+0A8h], 4
0x14002a722  mov     byte ptr [rdx+0AAh], 1
0x14002a729  mov     rcx, [rax]
0x14002a72c  cmp     [rcx+8], rax
0x14002a730  jnz     loc_14002A7C3
0x14002a736  mov     r8, [rax+8]
0x14002a73a  cmp     [r8], rax
0x14002a73d  jnz     loc_14002A7C3
0x14002a743  mov     [r8], rcx
0x14002a746  mov     [rcx+8], r8
0x14002a74a  mov     rcx, r13; this
0x14002a74d  mov     [rax+8], rax
0x14002a751  mov     [rax], rax
0x14002a754  call    ?AttachDestage@SIO_CACHE_PACKET@@QEAAXPEAV1@@Z; SIO_CACHE_PACKET::AttachDestage(SIO_CACHE_PACKET *)
0x14002a759  lea     rax, [rbp+var_28]
0x14002a75d  cmp     r11, rax
0x14002a760  jz      short loc_14002A76A
0x14002a762  mov     rax, r11
0x14002a765  mov     r11, [r11]
0x14002a768  jmp     short loc_14002A714
0x14002a76a  mov     rax, qword ptr [rbp+var_18]
0x14002a76e  lea     rcx, [rbp+var_18]
0x14002a772  cmp     rax, rcx
0x14002a775  jz      short loc_14002A7CA
0x14002a777  mov     rbx, [rax]
0x14002a77a  mov     rdx, rbx
0x14002a77d  cmp     [rdx+8], rax
0x14002a781  jnz     short loc_14002A7C3
0x14002a783  mov     r8, [rax+8]
0x14002a787  cmp     [r8], rax
0x14002a78a  jnz     short loc_14002A7C3
0x14002a78c  lea     rcx, [rax-0F8h]
0x14002a793  mov     [r8], rdx
0x14002a796  mov     [rdx+8], r8
0x14002a79a  test    rcx, rcx
0x14002a79d  jz      short loc_14002A7AF
0x14002a79f  mov     rax, [rcx]
0x14002a7a2  mov     edx, 1
0x14002a7a7  mov     rax, [rax]
0x14002a7aa  call    _guard_dispatch_icall
0x14002a7af  lea     rax, [rbp+var_18]
0x14002a7b3  cmp     rbx, rax
0x14002a7b6  jz      short loc_14002A7CA
0x14002a7b8  mov     rdx, [rbx]
0x14002a7bb  mov     rax, rbx
0x14002a7be  mov     rbx, rdx
0x14002a7c1  jmp     short loc_14002A77D
0x14002a7c3  mov     ecx, 3
0x14002a7c8  int     29h; Win8: RtlFailFast(ecx)
0x14002a7ca  mov     edi, [rbp+arg_10]
0x14002a7cd  test    r14, r14
0x14002a7d0  jz      short loc_14002A7E3
0x14002a7d2  xor     edx, edx; Tag
0x14002a7d4  mov     rcx, r14; P
0x14002a7d7  call    cs:__imp_ExFreePoolWithTag
0x14002a7de  nop     dword ptr [rax+rax+00h]
0x14002a7e3  mov     eax, edi
0x14002a7e5  add     rsp, 68h
0x14002a7e9  pop     r15
0x14002a7eb  pop     r14
0x14002a7ed  pop     r13
0x14002a7ef  pop     r12
0x14002a7f1  pop     rdi
0x14002a7f2  pop     rsi
0x14002a7f3  pop     rbx
0x14002a7f4  pop     rbp
0x14002a7f5  retn
```
