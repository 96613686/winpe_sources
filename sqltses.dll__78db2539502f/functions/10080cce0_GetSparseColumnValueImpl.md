# GetSparseColumnValueImpl

- ea: `0x10080cce0`
- end: `0x10080d17a`
- name: `GetSparseColumnValueImpl`
- size: `1178`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x10080ccc0`

## callees

- `0x100401170`
- `0x100401cc0`
- `0x1004024b0`
- `0x100403380`
- `0x10048cae0`
- `0x10080cce0`

## import_xrefs

- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10080ce84`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10080cf1e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10080cf45`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10080ce84`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10080cf1e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10080cf45`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10080d122`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10080d136`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10080d14a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10080d122`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10080d136`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10080d14a`
- `sqldk!SystemThread_TlsIndex` at `0x10080cd5c`
- `sqldk!SystemThread_TlsOffset` at `0x10080cd65`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10080cd80`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10080cd80`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10080d0b5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10080d0b5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10080ce25`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10080cec0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10080ce25`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10080cec0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall GetSparseColumnValueImpl(__int64 a1, __int64 a2)
{
  const struct CTypeInfo *v4; // rdi
  __int64 v5; // rbx
  __int64 v6; // rax
  struct IMemObj *v7; // rax
  __int64 v8; // r13
  unsigned int v9; // r15d
  BOOL v10; // r8d
  unsigned __int16 v11; // cx
  char *v12; // rdx
  unsigned int v13; // r12d
  _BYTE *v14; // rax
  struct ILockBytesSS *v15; // r15
  __int64 v16; // rdx
  __int64 v17; // rdi
  __int64 v18; // rbx
  __int64 v19; // rdx
  void *v20; // r15
  size_t v21; // rdi
  unsigned __int16 v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v23; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v24; // [rsp+48h] [rbp-B8h] BYREF
  BOOL v25; // [rsp+4Ch] [rbp-B4h]
  unsigned int v26; // [rsp+50h] [rbp-B0h]
  int v27[3]; // [rsp+54h] [rbp-ACh] BYREF
  void **v28; // [rsp+60h] [rbp-A0h] BYREF
  struct IMemObj *v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int128 v31; // [rsp+80h] [rbp-80h]
  _BYTE *v32; // [rsp+90h] [rbp-70h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 v34; // [rsp+A0h] [rbp-60h]
  int v35; // [rsp+A8h] [rbp-58h]
  __int16 v36; // [rsp+ACh] [rbp-54h]
  __int128 v37; // [rsp+B0h] [rbp-50h]
  char v38; // [rsp+C0h] [rbp-40h]
  _BYTE v39[8]; // [rsp+D0h] [rbp-30h] BYREF
  struct ILockBytesSS *v40; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  __int64 v43; // [rsp+F0h] [rbp-10h]
  struct ILockBytesSS *v44; // [rsp+F8h] [rbp-8h]
  _BYTE v45[2]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v46; // [rsp+102h] [rbp+2h]
  char v47; // [rsp+104h] [rbp+4h] BYREF
  unsigned __int8 Src[8016]; // [rsp+2040h] [rbp+1F40h] BYREF

  v42 = -2;
  v4 = (const struct CTypeInfo *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 168LL)
                                + 32LL * *(unsigned __int16 *)(*(_QWORD *)(a1 + 32) + 24LL));
  if ( *(_BYTE *)a2 == 3 )
  {
    *(_BYTE *)a2 = 3;
  }
  else
  {
    v26 = *(_DWORD *)(a2 + 40);
    v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v6 = *(_QWORD *)(v5 + 256);
    if ( !v6 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v6 = *(_QWORD *)(v5 + 256);
    }
    v7 = *(struct IMemObj **)(v6 + 1000);
    v28 = &CRESparseVectorReader::`vftable';
    v29 = v7;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v38 = 1;
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a2 + 8) + 8LL))(*(_QWORD *)(a2 + 8), 0);
    v43 = v8;
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _BYTE *, __int64, unsigned int *))(*(_QWORD *)v8 + 24LL))(
           v8,
           0,
           v45,
           8000,
           &v24) )
    {
      ex_raise(71, 2, 20, 99);
    }
    v9 = v24;
    v10 = v24 < 0x1F40;
    v25 = v10;
    *(_QWORD *)&v30 = v8;
    v11 = v46;
    HIWORD(v35) = v46;
    v36 = 0;
    v12 = &v47;
    v13 = 6 * (v46 + 1);
    if ( v24 < v13 )
    {
      _mm_lfence();
      *((_QWORD *)&v31 + 1) = operator new[](v13, v29, "sql\\ntdbms\\msql\\typesystem\\ReSparseVector.cpp", 637, 6u);
      if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _BYTE *))(*(_QWORD *)v30 + 24LL))(
             v30,
             0,
             *((_QWORD *)&v31 + 1),
             v13,
             v39) )
      {
        ex_raise(71, 2, 20, 99);
      }
      v12 = (char *)(*((_QWORD *)&v31 + 1) + 4LL);
      v11 = HIWORD(v35);
      v10 = v25;
    }
    *(_QWORD *)&v37 = v12;
    *((_QWORD *)&v37 + 1) = &v12[4 * v11];
    if ( v9 < 0x1F40 || v10 )
    {
      v38 = 1;
      v14 = v45;
      LODWORD(v33) = v9;
    }
    else
    {
      v38 = 0;
      v14 = (_BYTE *)*((_QWORD *)&v30 + 1);
      if ( !*((_QWORD *)&v30 + 1) )
      {
        *((_QWORD *)&v30 + 1) = operator new[](
                                  0x1000u,
                                  v29,
                                  "sql\\ntdbms\\msql\\typesystem\\ReSparseVector.cpp",
                                  671,
                                  6u);
        *(_QWORD *)&v31 = operator new[](0x1F40u, v29, "sql\\ntdbms\\msql\\typesystem\\ReSparseVector.cpp", 672, 6u);
        v14 = (_BYTE *)*((_QWORD *)&v30 + 1);
      }
      LODWORD(v33) = 4096;
      HIWORD(v33) = 0;
    }
    v32 = v14;
    if ( (unsigned int)CRESparseVectorReader::GetColumnDataWithColumnId(
                         (CRESparseVectorReader *)&v28,
                         v26,
                         v22,
                         v27,
                         0x1F50u,
                         Src,
                         &v40) )
    {
      if ( v27[0] )
      {
        v15 = v40;
        v44 = v40;
        v16 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 32) + 18LL);
        v17 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 8 * v16);
        v23 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 32LL) + 2 * v16);
        (*(void (__fastcall **)(_QWORD, __int64, unsigned int *, __int64, _DWORD))(**(_QWORD **)(a1 + 80) + 96LL))(
          *(_QWORD *)(a1 + 80),
          v17,
          &v23,
          a1,
          0);
        v41 = 0;
        v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 8LL))(v17, 0);
        v41 = v18;
        (*(void (__fastcall **)(struct ISqlTypeSystemExtender_ILobSupport *, __int64, struct ILockBytesSS *))(*(_QWORD *)x_pILobSupport + 32LL))(
          x_pILobSupport,
          v18,
          v15);
        *(_QWORD *)(a2 + 8) = v17;
        *(_QWORD *)(a2 + 16) = v23;
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        if ( v15 )
          (*(void (__fastcall **)(struct ILockBytesSS *))(*(_QWORD *)v15 + 16LL))(v15);
      }
      else if ( *((_BYTE *)&xsm_rgfIsDeepType + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)v4)) )
      {
        v19 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 32) + 18LL);
        v20 = *(void **)(*(_QWORD *)(a1 + 56) + 8 * v19);
        v21 = v22[0];
        if ( v22[0] > *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 32LL) + 2 * v19) )
          utassert_fail(1u, "columnSize <= pesx->CbCurDataLen()", "ReSparseVectorEsIntrinsic.cpp", 458, 0);
        memmove(v20, Src, v21);
        *(_QWORD *)(a2 + 8) = v20;
        *(_QWORD *)(a2 + 16) = v21;
      }
      else
      {
        CXVariant::CopyFromPbInternal((CXVariant *)a2, Src, v22[0], v4, 1);
      }
    }
    else
    {
      *(_BYTE *)a2 = 3;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v28 = &CRESparseVectorReader::`vftable';
    if ( *((_QWORD *)&v30 + 1) )
      operator delete(*((void **)&v30 + 1), 1u);
    if ( (_QWORD)v31 )
      operator delete((void *)v31, 1u);
    if ( *((_QWORD *)&v31 + 1) )
      operator delete(*((void **)&v31 + 1), 1u);
  }
}

```

## disassembly

```asm
0x10080cce0  push    rbp
0x10080cce2  push    rsi
0x10080cce3  push    rdi
0x10080cce4  push    r12
0x10080cce6  push    r13
0x10080cce8  push    r14
0x10080ccea  push    r15
0x10080ccec  lea     rbp, [rsp-3EA0h]
0x10080ccf4  mov     eax, 3FA0h
0x10080ccf9  call    _alloca_probe
0x10080ccfe  sub     rsp, rax
0x10080cd01  mov     [rbp+3ED0h+var_3EE8], 0FFFFFFFFFFFFFFFEh
0x10080cd09  mov     [rsp+3FD0h+arg_10], rbx
0x10080cd11  mov     rax, cs:__security_cookie
0x10080cd18  xor     rax, rsp
0x10080cd1b  mov     [rbp+3ED0h+var_40], rax
0x10080cd22  mov     rsi, rdx
0x10080cd25  mov     r14, rcx
0x10080cd28  mov     rax, [rcx+20h]
0x10080cd2c  movzx   edi, word ptr [rax+18h]
0x10080cd30  shl     rdi, 5
0x10080cd34  mov     rax, [rcx+10h]
0x10080cd38  add     rdi, [rax+0A8h]
0x10080cd3f  cmp     byte ptr [rdx], 3
0x10080cd42  jnz     short loc_10080CD4C
0x10080cd44  mov     byte ptr [rdx], 3
0x10080cd47  jmp     loc_10080D150
0x10080cd4c  mov     eax, [rdx+28h]
0x10080cd4f  mov     [rsp+3FD0h+var_3F80], eax
0x10080cd53  mov     rdx, gs:58h
0x10080cd5c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10080cd63  mov     ecx, [rax]
0x10080cd65  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10080cd6c  mov     ebx, [rax]
0x10080cd6e  add     rbx, [rdx+rcx*8]
0x10080cd72  mov     rax, [rbx+100h]
0x10080cd79  test    rax, rax
0x10080cd7c  jnz     short loc_10080CD8D
0x10080cd7e  xor     ecx, ecx
0x10080cd80  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10080cd86  mov     rax, [rbx+100h]
0x10080cd8d  mov     rax, [rax+3E8h]
0x10080cd94  lea     rcx, ??_7ISparseVector@@6B@; const ISparseVector::`vftable'
0x10080cd9b  mov     [rsp+3FD0h+var_3F70], rcx
0x10080cda0  lea     rcx, ??_7CRESparseVectorReader@@6B@; const CRESparseVectorReader::`vftable'
0x10080cda7  mov     [rsp+3FD0h+var_3F70], rcx
0x10080cdac  mov     [rsp+3FD0h+var_3F68], rax
0x10080cdb1  xorps   xmm0, xmm0
0x10080cdb4  movdqa  [rsp+3FD0h+var_3F60], xmm0
0x10080cdba  xorps   xmm1, xmm1
0x10080cdbd  movdqa  [rbp+3ED0h+var_3F50], xmm1
0x10080cdc2  xor     ebx, ebx
0x10080cdc4  mov     [rbp+3ED0h+var_3F40], rbx
0x10080cdc8  mov     [rbp+3ED0h+var_3F38], rbx
0x10080cdcc  mov     [rbp+3ED0h+var_3F30], rbx
0x10080cdd0  mov     [rbp+3ED0h+var_3F28], ebx
0x10080cdd3  mov     [rbp+3ED0h+var_3F24], bx
0x10080cdd7  movdqa  [rbp+3ED0h+var_3F20], xmm0
0x10080cddc  mov     [rbp+3ED0h+var_3F10], 1
0x10080cde0  mov     rcx, [rsi+8]
0x10080cde4  mov     rax, [rcx]
0x10080cde7  xor     edx, edx
0x10080cde9  call    qword ptr [rax+8]
0x10080cdec  mov     r13, rax
0x10080cdef  mov     [rbp+3ED0h+var_3EE0], rax
0x10080cdf3  mov     r10, [rax]
0x10080cdf6  lea     rax, [rsp+3FD0h+var_3F88]
0x10080cdfb  mov     qword ptr [rsp+3FD0h+var_3FB0], rax
0x10080ce00  mov     r9d, 1F40h
0x10080ce06  lea     r8, [rbp+3ED0h+var_3ED0]
0x10080ce0a  mov     edx, ebx
0x10080ce0c  mov     rcx, r13
0x10080ce0f  call    qword ptr [r10+18h]
0x10080ce13  test    eax, eax
0x10080ce15  jz      short loc_10080CE2B
0x10080ce17  lea     edx, [rbx+2]
0x10080ce1a  lea     ecx, [rbx+47h]
0x10080ce1d  lea     r9d, [rbx+63h]
0x10080ce21  lea     r8d, [rbx+14h]
0x10080ce25  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10080ce2b  mov     r8d, ebx
0x10080ce2e  mov     r15d, [rsp+3FD0h+var_3F88]
0x10080ce33  cmp     r15d, 1F40h
0x10080ce3a  setb    r8b
0x10080ce3e  mov     [rsp+3FD0h+var_3F84], r8d
0x10080ce43  mov     qword ptr [rsp+3FD0h+var_3F60], r13
0x10080ce48  movzx   ecx, [rbp+3ED0h+var_3ECE]
0x10080ce4c  mov     word ptr [rbp+3ED0h+var_3F28+2], cx
0x10080ce50  mov     [rbp+3ED0h+var_3F24], bx
0x10080ce54  lea     rdx, [rbp+3ED0h+var_3ECC]
0x10080ce58  lea     eax, [rcx+1]
0x10080ce5b  lea     r12d, [rax+rax*2]
0x10080ce5f  add     r12d, r12d
0x10080ce62  cmp     r15d, r12d
0x10080ce65  jnb     short loc_10080CED7
0x10080ce67  lfence
0x10080ce6a  mov     ecx, r12d
0x10080ce6d  mov     byte ptr [rsp+3FD0h+var_3FB0], 6
0x10080ce72  mov     r9d, 27Dh
0x10080ce78  lea     r8, aSqlNtdbmsMsqlT_2; "sql\\ntdbms\\msql\\typesystem\\ReSparse"...
0x10080ce7f  mov     rdx, [rsp+3FD0h+var_3F68]
0x10080ce84  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10080ce8a  mov     qword ptr [rbp+3ED0h+var_3F50+8], rax
0x10080ce8e  mov     rcx, qword ptr [rsp+3FD0h+var_3F60]
0x10080ce93  mov     r10, [rcx]
0x10080ce96  lea     rdx, [rbp+3ED0h+var_3F00]
0x10080ce9a  mov     qword ptr [rsp+3FD0h+var_3FB0], rdx
0x10080ce9f  mov     r9d, r12d
0x10080cea2  mov     r8, rax
0x10080cea5  mov     rdx, rbx
0x10080cea8  call    qword ptr [r10+18h]
0x10080ceac  test    eax, eax
0x10080ceae  jz      short loc_10080CEC6
0x10080ceb0  mov     edx, 2
0x10080ceb5  lea     ecx, [rdx+45h]
0x10080ceb8  lea     r9d, [rdx+61h]
0x10080cebc  lea     r8d, [rdx+12h]
0x10080cec0  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10080cec6  mov     rdx, qword ptr [rbp+3ED0h+var_3F50+8]
0x10080ceca  add     rdx, 4
0x10080cece  movzx   ecx, word ptr [rbp+3ED0h+var_3F28+2]
0x10080ced2  mov     r8d, [rsp+3FD0h+var_3F84]
0x10080ced7  mov     qword ptr [rbp+3ED0h+var_3F20], rdx
0x10080cedb  movzx   eax, cx
0x10080cede  lea     rcx, [rdx+rax*4]
0x10080cee2  mov     qword ptr [rbp+3ED0h+var_3F20+8], rcx
0x10080cee6  cmp     r15d, 1F40h
0x10080ceed  jb      short loc_10080CF61
0x10080ceef  test    r8d, r8d
0x10080cef2  jnz     short loc_10080CF61
0x10080cef4  mov     [rbp+3ED0h+var_3F10], r8b
0x10080cef8  mov     rax, qword ptr [rsp+3FD0h+var_3F60+8]
0x10080cefd  test    rax, rax
0x10080cf00  jnz     short loc_10080CF54
0x10080cf02  mov     byte ptr [rsp+3FD0h+var_3FB0], 6
0x10080cf07  mov     r9d, 29Fh
0x10080cf0d  lea     r8, aSqlNtdbmsMsqlT_2; "sql\\ntdbms\\msql\\typesystem\\ReSparse"...
0x10080cf14  mov     rdx, [rsp+3FD0h+var_3F68]
0x10080cf19  mov     ecx, 1000h
0x10080cf1e  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10080cf24  mov     qword ptr [rsp+3FD0h+var_3F60+8], rax
0x10080cf29  mov     byte ptr [rsp+3FD0h+var_3FB0], 6
0x10080cf2e  mov     r9d, 2A0h
0x10080cf34  lea     r8, aSqlNtdbmsMsqlT_2; "sql\\ntdbms\\msql\\typesystem\\ReSparse"...
0x10080cf3b  mov     rdx, [rsp+3FD0h+var_3F68]
0x10080cf40  mov     ecx, 1F40h
0x10080cf45  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10080cf4b  mov     qword ptr [rbp+3ED0h+var_3F50], rax
0x10080cf4f  mov     rax, qword ptr [rsp+3FD0h+var_3F60+8]
0x10080cf54  mov     dword ptr [rbp+3ED0h+var_3F38], 1000h
0x10080cf5b  mov     word ptr [rbp+3ED0h+var_3F38+6], bx
0x10080cf5f  jmp     short loc_10080CF6D
0x10080cf61  mov     [rbp+3ED0h+var_3F10], 1
0x10080cf65  lea     rax, [rbp+3ED0h+var_3ED0]
0x10080cf69  mov     dword ptr [rbp+3ED0h+var_3F38], r15d
0x10080cf6d  mov     [rbp+3ED0h+var_3F40], rax
0x10080cf71  mov     ecx, 1F50h
0x10080cf76  lea     rax, [rbp+3ED0h+var_3EF8]
0x10080cf7a  mov     [rsp+3FD0h+var_3FA0], rax; struct ILockBytesSS **
0x10080cf7f  lea     rax, [rbp+3ED0h+Src]
0x10080cf86  mov     [rsp+3FD0h+var_3FA8], rax; unsigned __int8 *
0x10080cf8b  mov     [rsp+3FD0h+var_3FB0], cx; unsigned __int16
0x10080cf90  lea     r9, [rsp+3FD0h+var_3F7C]; int *
0x10080cf95  lea     r8, [rsp+3FD0h+var_3F90]; unsigned __int16 *
0x10080cf9a  mov     edx, [rsp+3FD0h+var_3F80]; unsigned int
0x10080cf9e  lea     rcx, [rsp+3FD0h+var_3F70]; this
0x10080cfa3  call    ?GetColumnDataWithColumnId@CRESparseVectorReader@@QEAAHKAEAGAEAHGPEAEPEAPEAVILockBytesSS@@@Z; CRESparseVectorReader::GetColumnDataWithColumnId(ulong,ushort &,int &,ushort,uchar *,ILockBytesSS * *)
0x10080cfa8  test    eax, eax
0x10080cfaa  jz      loc_10080D0F9
0x10080cfb0  cmp     [rsp+3FD0h+var_3F7C], 0
0x10080cfb5  jz      loc_10080D058
0x10080cfbb  mov     r15, [rbp+3ED0h+var_3EF8]
0x10080cfbf  mov     [rbp+3ED0h+var_3ED8], r15
0x10080cfc3  mov     rax, [r14+20h]
0x10080cfc7  movzx   edx, word ptr [rax+12h]
0x10080cfcb  mov     rax, [r14+38h]
0x10080cfcf  mov     rdi, [rax+rdx*8]
0x10080cfd3  mov     rax, [r14+10h]
0x10080cfd7  mov     rcx, [rax+20h]
0x10080cfdb  movzx   eax, word ptr [rcx+rdx*2]
0x10080cfdf  mov     [rsp+3FD0h+var_3F8C], eax
0x10080cfe3  mov     rcx, [r14+50h]
0x10080cfe7  mov     rax, [rcx]
0x10080cfea  mov     dword ptr [rsp+3FD0h+var_3FB0], ebx
0x10080cfee  mov     r9, r14
0x10080cff1  lea     r8, [rsp+3FD0h+var_3F8C]
0x10080cff6  mov     rdx, rdi
0x10080cff9  call    qword ptr [rax+60h]
0x10080cffc  mov     [rbp+3ED0h+var_3EF0], rbx
0x10080d000  mov     rax, [rdi]
0x10080d003  xor     edx, edx
0x10080d005  mov     rcx, rdi
0x10080d008  call    qword ptr [rax+8]
0x10080d00b  mov     rbx, rax
0x10080d00e  mov     [rbp+3ED0h+var_3EF0], rax
0x10080d012  mov     rcx, cs:?x_pILobSupport@@3PEAUISqlTypeSystemExtender_ILobSupport@@EA; ISqlTypeSystemExtender_ILobSupport * x_pILobSupport
0x10080d019  mov     r9, [rcx]
0x10080d01c  mov     r8, r15
0x10080d01f  mov     rdx, rax
0x10080d022  call    qword ptr [r9+20h]
0x10080d026  mov     [rsi+8], rdi
0x10080d02a  mov     ecx, [rsp+3FD0h+var_3F8C]
0x10080d02e  mov     [rsi+10h], rcx
0x10080d032  test    rbx, rbx
0x10080d035  jz      short loc_10080D041
0x10080d037  mov     rax, [rbx]
0x10080d03a  mov     rcx, rbx
0x10080d03d  call    qword ptr [rax+10h]
0x10080d040  nop
0x10080d041  test    r15, r15
0x10080d044  jz      loc_10080D0FC
0x10080d04a  mov     rax, [r15]
0x10080d04d  mov     rcx, r15
0x10080d050  call    qword ptr [rax+10h]
0x10080d053  jmp     loc_10080D0FC
0x10080d058  movzx   eax, byte ptr [rdi]
0x10080d05b  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10080d062  movzx   eax, byte ptr [rax+rcx+45AE60h]
0x10080d06a  cmp     byte ptr [rax+rcx+45BE00h], 0
0x10080d072  jz      short loc_10080D0D7
0x10080d074  mov     rax, [r14+20h]
0x10080d078  movzx   edx, word ptr [rax+12h]
0x10080d07c  mov     rax, [r14+38h]
0x10080d080  mov     r15, [rax+rdx*8]
0x10080d084  mov     rax, [r14+10h]
0x10080d088  mov     rcx, [rax+20h]
0x10080d08c  movzx   edi, [rsp+3FD0h+var_3F90]
0x10080d091  cmp     di, [rcx+rdx*2]
0x10080d095  jbe     short loc_10080D0BB
0x10080d097  mov     qword ptr [rsp+3FD0h+var_3FB0], rbx
0x10080d09c  mov     r9d, 1CAh
0x10080d0a2  lea     r8, aResparsevector_0; "ReSparseVectorEsIntrinsic.cpp"
0x10080d0a9  lea     rdx, aColumnsizePesx; "columnSize <= pesx->CbCurDataLen()"
0x10080d0b0  mov     ecx, 1
0x10080d0b5  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10080d0bb  mov     r8, rdi; Size
0x10080d0be  lea     rdx, [rbp+3ED0h+Src]; Src
0x10080d0c5  mov     rcx, r15; void *
0x10080d0c8  call    memmove
0x10080d0cd  mov     [rsi+8], r15
0x10080d0d1  mov     [rsi+10h], rdi
0x10080d0d5  jmp     short loc_10080D0FC
0x10080d0d7  movzx   r8d, [rsp+3FD0h+var_3F90]; unsigned int
0x10080d0dd  mov     dword ptr [rsp+3FD0h+var_3FB0], 1; int
0x10080d0e5  mov     r9, rdi; struct CTypeInfo *
0x10080d0e8  lea     rdx, [rbp+3ED0h+Src]; unsigned __int8 *
0x10080d0ef  mov     rcx, rsi; this
0x10080d0f2  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x10080d0f7  jmp     short loc_10080D0FC
0x10080d0f9  mov     byte ptr [rsi], 3
0x10080d0fc  mov     rax, [r13+0]
0x10080d100  mov     rcx, r13
0x10080d103  call    qword ptr [rax+10h]
0x10080d106  nop
0x10080d107  lea     rax, ??_7CRESparseVectorReader@@6B@; const CRESparseVectorReader::`vftable'
0x10080d10e  mov     [rsp+3FD0h+var_3F70], rax
0x10080d113  mov     rcx, qword ptr [rsp+3FD0h+var_3F60+8]
0x10080d118  test    rcx, rcx
0x10080d11b  jz      short loc_10080D128
0x10080d11d  mov     edx, 1
0x10080d122  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10080d128  mov     rcx, qword ptr [rbp+3ED0h+var_3F50]
0x10080d12c  test    rcx, rcx
0x10080d12f  jz      short loc_10080D13C
0x10080d131  mov     edx, 1
0x10080d136  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10080d13c  mov     rcx, qword ptr [rbp+3ED0h+var_3F50+8]
0x10080d140  test    rcx, rcx
0x10080d143  jz      short loc_10080D150
0x10080d145  mov     edx, 1
0x10080d14a  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10080d150  mov     rcx, [rbp+3ED0h+var_40]
0x10080d157  xor     rcx, rsp; StackCookie
0x10080d15a  call    __security_check_cookie
0x10080d15f  mov     rbx, [rsp+3FD0h+arg_10]
0x10080d167  add     rsp, 3FA0h
0x10080d16e  pop     r15
0x10080d170  pop     r14
0x10080d172  pop     r13
0x10080d174  pop     r12
0x10080d176  pop     rdi
0x10080d177  pop     rsi
0x10080d178  pop     rbp
0x10080d179  retn
```
