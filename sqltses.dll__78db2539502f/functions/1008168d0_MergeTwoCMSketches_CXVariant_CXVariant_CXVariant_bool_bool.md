# MergeTwoCMSketches(CXVariant *,CXVariant *,CXVariant *,bool,bool)

- ea: `0x1008168d0`
- end: `0x100816cbf`
- name: `?MergeTwoCMSketches@@YAXPEAVCXVariant@@00_N1@Z`
- size: `1007`
- prototype: `void __fastcall(struct CXVariant *, struct CXVariant *, struct CXVariant *, bool, bool)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x100584f30`
- `0x1005850c0`
- `0x100816e40`
- `0x100821770`
- `0x1008219e0`

## callees

- `0x100401170`
- `0x1004024b0`
- `0x100816700`
- `0x1008168d0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100816c27`
- `sqldk!??_V@YAXPEAX@Z` at `0x100816c27`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1008169fd`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1008169fd`
- `sqldk!SystemThread_TlsIndex` at `0x1008169ae`
- `sqldk!SystemThread_TlsIndex` at `0x100816b34`
- `sqldk!SystemThread_TlsOffset` at `0x1008169b7`
- `sqldk!SystemThread_TlsOffset` at `0x100816b3d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1008169d2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100816b58`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1008169d2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100816b58`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100816acb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100816acb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100816a47`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100816a91`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100816a47`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100816a91`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall MergeTwoCMSketches(struct CXVariant *a1, unsigned __int8 ***a2, struct CXVariant *a3, char a4, bool a5)
{
  unsigned __int8 *v6; // rdi
  __int64 v7; // r13
  __int64 v8; // rbx
  __int64 v9; // rdx
  _DWORD *v10; // r14
  _QWORD *v11; // rsi
  unsigned int v12; // ebx
  __int64 i; // r8
  __int64 v14; // rsi
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned __int8 *v18; // rcx
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  unsigned int v21; // [rsp+30h] [rbp-D0h] BYREF
  void **v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  int v26; // [rsp+58h] [rbp-A8h]
  __int64 v27; // [rsp+60h] [rbp-A0h]
  struct CXVariant *v28; // [rsp+68h] [rbp-98h]
  __int64 v29; // [rsp+70h] [rbp-90h]
  _DWORD *v30; // [rsp+78h] [rbp-88h]
  _QWORD v31[2]; // [rsp+80h] [rbp-80h] BYREF
  int v32; // [rsp+90h] [rbp-70h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  char v34[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  __int128 v37; // [rsp+B8h] [rbp-48h]
  void ***v38; // [rsp+C8h] [rbp-38h]
  __int64 v39; // [rsp+D0h] [rbp-30h]
  __int16 v40; // [rsp+2018h] [rbp+1F18h]
  int v41; // [rsp+2024h] [rbp+1F24h]
  void **v42; // [rsp+2028h] [rbp+1F28h]
  char v43[16]; // [rsp+2030h] [rbp+1F30h] BYREF
  __int64 v44; // [rsp+2040h] [rbp+1F40h]

  v29 = -2;
  v28 = (struct CXVariant *)a2;
  v6 = *a2[1];
  if ( a4 )
  {
    if ( *(_BYTE *)a1 != 3 )
    {
      v27 = 0;
      v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 1) + 8LL))(*((_QWORD *)a1 + 1), 0);
      v27 = v7;
      v22 = &CByteLobReader::`vftable';
      v23 = 0;
      v24 = 0;
      v25 = 0;
      (*(void (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)v7 + 72LL))(v7, v43, 0);
      v24 = v44;
      v23 = v7;
      v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v9 = *(_QWORD *)(v8 + 256);
      if ( !v9 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v9 = *(_QWORD *)(v8 + 256);
      }
      v10 = operator new[](
              0x3A11B8u,
              *(struct IMemObj **)(v9 + 1000),
              "sql\\ntdbms\\msql\\expr\\runtime\\ApproxAggEsIntrinsic.cpp",
              1442,
              3u);
      v30 = v10;
      v21 = 0;
      if ( (*(unsigned int (__fastcall **)(__int64, __int64, _DWORD *, __int64, unsigned int *))(*(_QWORD *)v23 + 24LL))(
             v23,
             v25,
             v10,
             32,
             &v21) )
      {
        ex_raise(71, 2, 20, 99);
      }
      v25 += v21;
      if ( (*(unsigned int (__fastcall **)(__int64, __int64, _DWORD *, __int64, unsigned int *))(*(_QWORD *)v23 + 24LL))(
             v23,
             v25,
             v10 + 8,
             3805592,
             &v21) )
      {
        ex_raise(71, 2, 20, 99);
      }
      v25 += v21;
      v11 = v6 + 32;
      v12 = 0;
      if ( v6 == (unsigned __int8 *)-32LL )
        utassert_fail(1u, "nullptr != pbCountMinSketch", "ApproxAggEsIntrinsic.cpp", 319, 0);
      for ( i = 0; i < 951398; i += 2 )
      {
        LODWORD(v11[v12]) += v10[i + 8];
        HIDWORD(v11[v12++]) += v10[i + 9];
      }
      *(_QWORD *)v6 += *(_QWORD *)v10;
      *((_QWORD *)v6 + 1) += *((_QWORD *)v10 + 1);
      if ( (v10[4] & 1) != 0 )
      {
        v14 = *(_QWORD *)v10 - *((_QWORD *)v10 + 1);
        v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v16 = *(_QWORD *)(v15 + 256);
        if ( !v16 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v16 = *(_QWORD *)(v15 + 256);
        }
        v17 = *(_QWORD *)(v16 + 1000);
        v31[0] = &CBlobSample::`vbtable';
        v42 = &CBlobSample::`vftable';
        v41 = 0;
        v31[1] = v14;
        v32 = 1;
        v33 = v17;
        v35 = 0;
        v36 = -1;
        v37 = 0u;
        v38 = &v22;
        v39 = 0;
        v26 = 0;
        ((void (__fastcall *)(void ***, char *, __int64))v22[5])(&v22, v34, 40);
        v40 = 0;
        *((_QWORD *)v6 + 3) = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)v6 + 3) + 56LL))(
                                *((_QWORD *)v6 + 3),
                                (char *)v31 + *(int *)(v31[0] + 4LL));
      }
      operator delete[](v10);
      v22 = &ILobReader::`vftable';
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  else
  {
    v18 = (unsigned __int8 *)**((_QWORD **)a1 + 1);
    if ( v6 != v18 )
      MergeTwoCMSketchBuffers(v18, *a2[1], a5);
  }
  v19 = (_QWORD *)*((_QWORD *)v28 + 1);
  *((_QWORD *)a3 + 2) = 8;
  v20 = (_QWORD *)*((_QWORD *)a3 + 1);
  if ( v20 != v19 )
    *v20 = *v19;
  *(_BYTE *)a3 = 0;
}

```

## disassembly

```asm
0x1008168d0  push    rbp
0x1008168d2  push    rsi
0x1008168d3  push    rdi
0x1008168d4  push    r12
0x1008168d6  push    r13
0x1008168d8  push    r14
0x1008168da  push    r15
0x1008168dc  lea     rbp, [rsp-1F90h]
0x1008168e4  mov     eax, 2090h
0x1008168e9  call    _alloca_probe
0x1008168ee  sub     rsp, rax
0x1008168f1  mov     [rsp+20C0h+var_2050], 0FFFFFFFFFFFFFFFEh
0x1008168fa  mov     [rsp+20C0h+arg_18], rbx
0x100816902  mov     rax, cs:__security_cookie
0x100816909  xor     rax, rsp
0x10081690c  mov     [rbp+1FC0h+var_40], rax
0x100816913  mov     r12, r8
0x100816916  mov     [rsp+20C0h+var_2058], rdx
0x10081691b  mov     rax, [rdx+8]
0x10081691f  mov     rdi, [rax]
0x100816922  test    r9b, r9b
0x100816925  jz      loc_100816C52
0x10081692b  cmp     byte ptr [rcx], 3
0x10081692e  jz      loc_100816C6E
0x100816934  xor     esi, esi
0x100816936  mov     [rsp+20C0h+var_2060], rsi
0x10081693b  mov     rcx, [rcx+8]
0x10081693f  mov     rax, [rcx]
0x100816942  xor     edx, edx
0x100816944  call    qword ptr [rax+8]
0x100816947  mov     r13, rax
0x10081694a  mov     [rsp+20C0h+var_2060], rax
0x10081694f  lea     rax, ??_7ILobReader@@6B@; const ILobReader::`vftable'
0x100816956  mov     [rsp+20C0h+var_2088], rax
0x10081695b  lea     rax, ??_7CByteLobReader@@6B@; const CByteLobReader::`vftable'
0x100816962  mov     [rsp+20C0h+var_2088], rax
0x100816967  mov     [rsp+20C0h+var_2080], rsi
0x10081696c  mov     [rsp+20C0h+var_2078], rsi
0x100816971  mov     [rsp+20C0h+var_2070], rsi
0x100816976  mov     [rsp+20C0h+var_2078], rsi
0x10081697b  mov     [rsp+20C0h+var_2070], rsi
0x100816980  mov     rax, [r13+0]
0x100816984  xor     r8d, r8d
0x100816987  lea     rdx, [rbp+1FC0h+var_90]
0x10081698e  mov     rcx, r13
0x100816991  call    qword ptr [rax+48h]
0x100816994  mov     rax, [rbp+1FC0h+var_80]
0x10081699b  mov     [rsp+20C0h+var_2078], rax
0x1008169a0  mov     [rsp+20C0h+var_2080], r13
0x1008169a5  mov     rdx, gs:58h
0x1008169ae  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1008169b5  mov     ecx, [rax]
0x1008169b7  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1008169be  mov     ebx, [rax]
0x1008169c0  add     rbx, [rdx+rcx*8]
0x1008169c4  mov     rdx, [rbx+100h]
0x1008169cb  test    rdx, rdx
0x1008169ce  jnz     short loc_1008169DF
0x1008169d0  xor     ecx, ecx
0x1008169d2  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1008169d8  mov     rdx, [rbx+100h]
0x1008169df  mov     byte ptr [rsp+20C0h+var_20A0], 3
0x1008169e4  mov     r9d, 5A2h
0x1008169ea  lea     r8, aSqlNtdbmsMsqlE_9; "sql\\ntdbms\\msql\\expr\\runtime\\Appro"...
0x1008169f1  mov     rdx, [rdx+3E8h]
0x1008169f8  mov     ecx, 3A11B8h
0x1008169fd  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100816a03  mov     r14, rax
0x100816a06  mov     [rsp+20C0h+var_2048], rax
0x100816a0b  mov     [rsp+20C0h+var_2090], esi
0x100816a0f  mov     rcx, [rsp+20C0h+var_2080]
0x100816a14  mov     r10, [rcx]
0x100816a17  lea     rax, [rsp+20C0h+var_2090]
0x100816a1c  mov     [rsp+20C0h+var_20A0], rax
0x100816a21  mov     r9d, 20h ; ' '
0x100816a27  mov     r8, r14
0x100816a2a  mov     rdx, [rsp+20C0h+var_2070]
0x100816a2f  call    qword ptr [r10+18h]
0x100816a33  test    eax, eax
0x100816a35  jz      short loc_100816A4D
0x100816a37  mov     edx, 2
0x100816a3c  lea     ecx, [rdx+45h]
0x100816a3f  lea     r9d, [rdx+61h]
0x100816a43  lea     r8d, [rdx+12h]
0x100816a47  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100816a4d  mov     eax, [rsp+20C0h+var_2090]
0x100816a51  mov     rdx, [rsp+20C0h+var_2070]
0x100816a56  add     rdx, rax
0x100816a59  mov     [rsp+20C0h+var_2070], rdx
0x100816a5e  mov     rcx, [rsp+20C0h+var_2080]
0x100816a63  mov     rax, [rcx]
0x100816a66  lea     r10, [rsp+20C0h+var_2090]
0x100816a6b  mov     [rsp+20C0h+var_20A0], r10
0x100816a70  mov     r9d, 3A1198h
0x100816a76  lea     r8, [r14+20h]
0x100816a7a  call    qword ptr [rax+18h]
0x100816a7d  test    eax, eax
0x100816a7f  jz      short loc_100816A97
0x100816a81  mov     edx, 2
0x100816a86  lea     ecx, [rdx+45h]
0x100816a89  lea     r9d, [rdx+61h]
0x100816a8d  lea     r8d, [rdx+12h]
0x100816a91  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100816a97  mov     eax, [rsp+20C0h+var_2090]
0x100816a9b  add     [rsp+20C0h+var_2070], rax
0x100816aa0  lea     rsi, [rdi+20h]
0x100816aa4  xor     r9d, r9d
0x100816aa7  mov     ebx, r9d
0x100816aaa  test    rsi, rsi
0x100816aad  jnz     short loc_100816AD4
0x100816aaf  mov     [rsp+20C0h+var_20A0], r9
0x100816ab4  mov     r9d, 13Fh
0x100816aba  lea     r8, aApproxaggesint; "ApproxAggEsIntrinsic.cpp"
0x100816ac1  lea     rdx, aNullptrPbcount; "nullptr != pbCountMinSketch"
0x100816ac8  lea     ecx, [rsi+1]
0x100816acb  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100816ad1  xor     r9d, r9d
0x100816ad4  mov     r8, r9
0x100816ad7  nop     word ptr [rax+rax+00000000h]
0x100816ae0  mov     eax, ebx
0x100816ae2  lea     rcx, [rsi+rax*4]
0x100816ae6  mov     eax, [r14+r8*4+20h]
0x100816aeb  add     [rcx], eax
0x100816aed  lea     edx, [rbx+1]
0x100816af0  lea     rcx, [rsi+rdx*4]
0x100816af4  mov     eax, [r14+r8*4+24h]
0x100816af9  add     [rcx], eax
0x100816afb  lea     ebx, [rdx+1]
0x100816afe  add     r8, 2
0x100816b02  cmp     r8, 0E8466h
0x100816b09  jl      short loc_100816AE0
0x100816b0b  mov     rax, [r14]
0x100816b0e  add     [rdi], rax
0x100816b11  mov     rax, [r14+8]
0x100816b15  add     [rdi+8], rax
0x100816b19  test    byte ptr [r14+10h], 1
0x100816b1e  jz      loc_100816C24
0x100816b24  mov     rsi, [r14]
0x100816b27  sub     rsi, [r14+8]
0x100816b2b  mov     rdx, gs:58h
0x100816b34  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100816b3b  mov     ecx, [rax]
0x100816b3d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100816b44  mov     ebx, [rax]
0x100816b46  add     rbx, [rdx+rcx*8]
0x100816b4a  mov     rax, [rbx+100h]
0x100816b51  test    rax, rax
0x100816b54  jnz     short loc_100816B68
0x100816b56  xor     ecx, ecx
0x100816b58  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100816b5e  mov     rax, [rbx+100h]
0x100816b65  xor     r9d, r9d
0x100816b68  mov     rax, [rax+3E8h]
0x100816b6f  lea     rcx, ??_8CBlobSample@@7B@; const CBlobSample::`vbtable'
0x100816b76  mov     [rbp+1FC0h+var_2040], rcx
0x100816b7a  lea     rcx, ??_7CBlobSample@@6B@; const CBlobSample::`vftable'
0x100816b81  mov     [rbp+1FC0h+var_98], rcx
0x100816b88  mov     [rbp+1FC0h+var_9C], r9d
0x100816b8f  mov     [rbp+1FC0h+var_2038], rsi
0x100816b93  mov     [rbp+1FC0h+var_2030], 1
0x100816b9a  mov     [rbp+1FC0h+var_2028], rax
0x100816b9e  xorps   xmm0, xmm0
0x100816ba1  movups  [rbp+1FC0h+var_2018], xmm0
0x100816ba5  movups  [rbp+1FC0h+var_2008], xmm0
0x100816ba9  mov     byte ptr [rbp+1FC0h+var_2018], 0
0x100816bad  mov     dword ptr [rbp+1FC0h+var_2018+4], r9d
0x100816bb1  mov     qword ptr [rbp+1FC0h+var_2018+8], 0FFFFFFFFFFFFFFFFh
0x100816bb9  mov     dword ptr [rbp+1FC0h+var_2008], 0
0x100816bc0  mov     qword ptr [rbp+1FC0h+var_2008+8], 0
0x100816bc8  lea     rax, [rsp+20C0h+var_2088]
0x100816bcd  mov     [rbp+1FC0h+var_1FF8], rax
0x100816bd1  mov     [rbp+1FC0h+var_1FF0], r9
0x100816bd5  mov     [rsp+20C0h+var_2068], r9d
0x100816bda  lea     rax, [rsp+20C0h+var_2068]
0x100816bdf  mov     [rsp+20C0h+var_20A0], rax
0x100816be4  mov     r9d, 28h ; '('
0x100816bea  mov     r8d, r9d
0x100816bed  lea     rdx, [rbp+1FC0h+var_2020]
0x100816bf1  lea     rcx, [rsp+20C0h+var_2088]
0x100816bf6  mov     rax, [rsp+20C0h+var_2088]
0x100816bfb  call    qword ptr [rax+28h]
0x100816bfe  xor     eax, eax
0x100816c00  mov     [rbp+1FC0h+var_A8], ax
0x100816c07  mov     rax, [rbp+1FC0h+var_2040]
0x100816c0b  movsxd  rcx, dword ptr [rax+4]
0x100816c0f  lea     rdx, [rbp+1FC0h+var_2040]
0x100816c13  add     rdx, rcx
0x100816c16  mov     rcx, [rdi+18h]
0x100816c1a  mov     rax, [rcx]
0x100816c1d  call    qword ptr [rax+38h]
0x100816c20  mov     [rdi+18h], rax
0x100816c24  mov     rcx, r14
0x100816c27  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100816c2d  nop
0x100816c2e  lea     rax, ??_7CByteLobReader@@6B@; const CByteLobReader::`vftable'
0x100816c35  mov     [rsp+20C0h+var_2088], rax
0x100816c3a  lea     rax, ??_7ILobReader@@6B@; const ILobReader::`vftable'
0x100816c41  mov     [rsp+20C0h+var_2088], rax
0x100816c46  mov     rax, [r13+0]
0x100816c4a  mov     rcx, r13
0x100816c4d  call    qword ptr [rax+10h]
0x100816c50  jmp     short loc_100816C6E
0x100816c52  mov     rax, [rcx+8]
0x100816c56  mov     rcx, [rax]; unsigned __int8 *
0x100816c59  cmp     rdi, rcx
0x100816c5c  jz      short loc_100816C6E
0x100816c5e  movzx   r8d, [rbp+1FC0h+arg_20]; bool
0x100816c66  mov     rdx, rdi; unsigned __int8 *
0x100816c69  call    ?MergeTwoCMSketchBuffers@@YAXPEAE0_N@Z; MergeTwoCMSketchBuffers(uchar *,uchar *,bool)
0x100816c6e  mov     rax, [rsp+20C0h+var_2058]
0x100816c73  mov     rax, [rax+8]
0x100816c77  mov     qword ptr [r12+10h], 8
0x100816c80  mov     rcx, [r12+8]
0x100816c85  cmp     rcx, rax
0x100816c88  jz      short loc_100816C90
0x100816c8a  mov     rax, [rax]
0x100816c8d  mov     [rcx], rax
0x100816c90  mov     byte ptr [r12], 0
0x100816c95  mov     rcx, [rbp+1FC0h+var_40]
0x100816c9c  xor     rcx, rsp; StackCookie
0x100816c9f  call    __security_check_cookie
0x100816ca4  mov     rbx, [rsp+20C0h+arg_18]
0x100816cac  add     rsp, 2090h
0x100816cb3  pop     r15
0x100816cb5  pop     r14
0x100816cb7  pop     r13
0x100816cb9  pop     r12
0x100816cbb  pop     rdi
0x100816cbc  pop     rsi
0x100816cbd  pop     rbp
0x100816cbe  retn
```
