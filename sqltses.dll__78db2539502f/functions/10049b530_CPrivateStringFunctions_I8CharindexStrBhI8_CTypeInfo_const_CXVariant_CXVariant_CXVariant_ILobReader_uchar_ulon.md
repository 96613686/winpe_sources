# CPrivateStringFunctions::I8CharindexStrBhI8(CTypeInfo const *,CXVariant *,CXVariant *,CXVariant *,ILobReader *,uchar *,ulong,uchar *,CXVariant *)

- ea: `0x10049b530`
- end: `0x10049bacf`
- name: `?I8CharindexStrBhI8@CPrivateStringFunctions@@SAXPEBVCTypeInfo@@PEAVCXVariant@@11PEAUILobReader@@PEAEK31@Z`
- size: `1439`
- prototype: `void __usercall(const struct CTypeInfo *@<rcx>, struct CXVariant *@<rdx>, struct CXVariant *@<r8>, struct CXVariant *@<r9>, struct ILobReader *, unsigned __int8 *, unsigned int, unsigned __int8 *, struct CXVariant *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x100498b70`
- `0x1007e02a0`

## callees

- `0x100401170`
- `0x1004024b0`
- `0x1004026b0`
- `0x100404c40`
- `0x10040ce20`
- `0x10046c450`
- `0x10049b530`

## import_xrefs

- `sqldk!SystemThread_TlsIndex` at `0x10049b915`
- `sqldk!SystemThread_TlsOffset` at `0x10049b91e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10049b939`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10049b939`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10049b5c3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10049b6cc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10049b5c3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10049b6cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CPrivateStringFunctions::I8CharindexStrBhI8(
        const struct CTypeInfo *a1,
        struct CXVariant *a2,
        wchar_t *a3,
        struct CXVariant *a4,
        struct ILobReader *a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned __int8 *a8,
        struct CXVariant *a9)
{
  __int64 v12; // rbx
  __int64 v13; // r14
  __int64 v14; // rax
  __int64 v15; // rsi
  char *v16; // r10
  unsigned int v17; // r12d
  __int64 v18; // rdi
  int v19; // ecx
  int v20; // edx
  int v21; // ecx
  __int64 *v22; // rax
  int v23; // edi
  int v24; // eax
  int v25; // esi
  __int64 v26; // rax
  unsigned __int64 v27; // rax
  __int64 v28; // rcx
  unsigned __int64 v29; // rcx
  void *v30; // rsp
  void *v31; // rsp
  int v32; // ecx
  unsigned int v33; // ecx
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // r8
  __int64 v37; // rbx
  __int64 v38; // rdx
  __int64 v39; // rdi
  void (__fastcall **v40)(__int64, __int64); // rbx
  __int64 v41; // rax
  void (__fastcall **v42)(__int64, __int64); // rbx
  __int64 v43; // rax
  __int64 v44; // rbx
  __int64 v45; // rax
  __int64 v46; // rcx
  void (__fastcall **v47)(__int64, __int64); // rbx
  __int64 v48; // rax
  __int64 v49; // rbx
  __int64 v50; // rax
  __int64 v51; // rdi
  __int64 v52; // rax
  __int64 v53; // rcx
  int v54; // [rsp+20h] [rbp-40h]
  wchar_t v55; // [rsp+60h] [rbp+0h] BYREF
  char *v56; // [rsp+68h] [rbp+8h]
  int v57; // [rsp+70h] [rbp+10h] BYREF
  int v58; // [rsp+74h] [rbp+14h] BYREF
  char v59[8]; // [rsp+78h] [rbp+18h] BYREF
  unsigned __int8 *v60; // [rsp+80h] [rbp+20h]
  __int64 v61; // [rsp+88h] [rbp+28h] BYREF
  wchar_t *v62; // [rsp+90h] [rbp+30h]
  __int64 v63; // [rsp+98h] [rbp+38h] BYREF
  __int64 v64; // [rsp+A0h] [rbp+40h]
  __int64 v65; // [rsp+A8h] [rbp+48h]
  struct CXVariant *v66; // [rsp+B0h] [rbp+50h]
  __int128 v67; // [rsp+B8h] [rbp+58h]
  __int64 v68; // [rsp+C8h] [rbp+68h]
  __int64 v69; // [rsp+D0h] [rbp+70h]
  _QWORD v70[2]; // [rsp+E0h] [rbp+80h] BYREF
  int v71; // [rsp+F0h] [rbp+90h]
  unsigned __int8 *v72; // [rsp+F8h] [rbp+98h]
  unsigned int v73; // [rsp+100h] [rbp+A0h]
  int v74; // [rsp+104h] [rbp+A4h]
  __int128 v75; // [rsp+108h] [rbp+A8h]
  __int64 v76; // [rsp+120h] [rbp+C0h]
  char v77[16]; // [rsp+130h] [rbp+D0h] BYREF
  __int64 v78; // [rsp+140h] [rbp+E0h]

  v68 = -2;
  v62 = a3;
  v66 = a9;
  v60 = a8;
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a3 + 1) + 8LL))(*((_QWORD *)a3 + 1), 0);
  v65 = v12;
  if ( (*(unsigned int (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 152LL))(v12, v59) )
    ex_raise(71, 2, 20, 99);
  if ( (v59[0] & 1) != 0 )
  {
    *(_BYTE *)a9 = 3;
  }
  else
  {
    (**(void (__fastcall ***)(struct ILobReader *, __int64))a5)(a5, v12);
    v13 = 0;
    if ( *(_BYTE *)a4 == 0xFF || (v14 = *((_QWORD *)a4 + 1), v15 = v14 - 1, v14 <= 0) )
      v15 = 0;
    v64 = v15;
    if ( (*(unsigned int (__fastcall **)(struct ILobReader *, __int64))(*(_QWORD *)a5 + 8LL))(a5, v15) )
    {
      v16 = (char *)*((_QWORD *)a2 + 1);
      v56 = v16;
      v17 = *((_DWORD *)a2 + 4);
      LOBYTE(v55) = *((_BYTE *)&CTypeInfo::sxm_rgfIsBinary
                    + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)a1));
      v18 = 0;
      if ( !(_BYTE)v55 )
      {
        v19 = *((_DWORD *)a1 + 5);
        if ( (v19 & 0x80) != 0 )
        {
          v20 = 65001;
        }
        else if ( HIBYTE(v19) )
        {
          v20 = *((_DWORD *)&x_uiCodePage + (unsigned __int8)byte_10085C9DC[40 * HIBYTE(v19)]);
        }
        else
        {
          v20 = qword_100856AB0[4 * (v19 & 0x7F)];
        }
        v21 = 0;
        v22 = (__int64 *)((char *)CSortCacheForSqlCollations::m_pSortCache + 1936);
        while ( 1 )
        {
          v18 = *v22;
          if ( *v22 )
          {
            if ( *(_DWORD *)(v18 + 16) == v20 )
              break;
          }
          ++v21;
          ++v22;
          if ( v21 >= 17 )
          {
            ex_raise(27, 75, 16, 1, v20);
            v18 = 0;
            v16 = v56;
            break;
          }
        }
        if ( v17 )
        {
          _mm_lfence();
          LOBYTE(v54) = 0;
          v17 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, _QWORD, int))(*(_QWORD *)(v18 + 32) + 80LL))(
                  v18 + 32,
                  v16,
                  v17,
                  v17,
                  v54);
          v12 = v65;
        }
        else
        {
          v17 = 0;
        }
      }
      v63 = 0;
      v57 = 0;
      if ( (*(unsigned int (__fastcall **)(_QWORD, __int64 *, int *))(**((_QWORD **)v62 + 1) + 24LL))(
             *((_QWORD *)v62 + 1),
             &v63,
             &v57) )
      {
        v58 = 0;
        v23 = *((unsigned __int8 *)&CTypeInfo::sxm_rgfIsBinary
              + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)a1));
        v24 = (*(__int64 (__fastcall **)(struct ILobReader *))(*(_QWORD *)a5 + 48LL))(a5);
        v25 = v57 - v24;
        v26 = (*(__int64 (__fastcall **)(struct ILobReader *))(*(_QWORD *)a5 + 48LL))(a5);
        if ( charindex(v23, a1, (unsigned __int8 *)v56, v17, (unsigned __int8 *)(v63 + v26), v25, v60, &v58, 0, 0, 0) )
          v13 = v64 + v58;
      }
      else
      {
        if ( !(_BYTE)v55 && CTypeInfo::FWindowsSort(a1) )
        {
          v27 = 2LL * (int)v17;
          v28 = v27 + 15;
          if ( v27 + 15 < v27 )
            v28 = 0xFFFFFFFFFFFFFF0LL;
          v29 = v28 & 0xFFFFFFFFFFFFFFF0uLL;
          v30 = alloca(v29);
          v31 = alloca(v29);
          v62 = &v55;
          v32 = *((_DWORD *)a1 + 5);
          if ( (v32 & 0x80) != 0 )
          {
            v33 = 65001;
          }
          else if ( HIBYTE(v32) )
          {
            v33 = *((_DWORD *)&x_uiCodePage + (unsigned __int8)byte_10085C9DC[40 * HIBYTE(v32)]);
          }
          else
          {
            v33 = qword_100856AB0[4 * (v32 & 0x7F)];
          }
          v34 = FastDBCSToUnicode(v33, v56, v17, &v55, v17);
          v56 = (char *)v62;
          v17 = 2 * v34;
        }
        v71 = 0;
        v74 = 0;
        v76 = 0;
        *((_QWORD *)&v67 + 1) = (*(__int64 (__fastcall **)(struct ILobReader *))(*(_QWORD *)a5 + 72LL))(a5);
        (*(void (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)&v67 + 1) + 72LL))(*((_QWORD *)&v67 + 1), v77, 0);
        *(_QWORD *)&v67 = v78;
        v35 = (*(__int64 (__fastcall **)(struct ILobReader *))(*(_QWORD *)a5 + 48LL))(a5);
        v75 = v67;
        v72 = a6;
        v73 = a7;
        v70[1] = v35;
        v70[0] = 0;
        if ( v18 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)(v18 + 32) + 104LL))(v18 + 32) )
        {
          v37 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v38 = *(_QWORD *)(v37 + 256);
          if ( !v38 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v38 = *(_QWORD *)(v37 + 256);
          }
          LOBYTE(v36) = 1;
          v39 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)(v18 + 32) + 88LL))(
                  v18 + 32,
                  *(_QWORD *)(v38 + 1000),
                  v36);
          v69 = v39;
          v40 = *(void (__fastcall ***)(__int64, __int64))v39;
          v41 = (*(__int64 (__fastcall **)(struct ILobReader *))(*(_QWORD *)a5 + 72LL))(a5);
          (*v40)(v39, v41);
          v42 = *(void (__fastcall ***)(__int64, __int64))v39;
          v43 = (*(__int64 (__fastcall **)(struct ILobReader *))(*(_QWORD *)a5 + 48LL))(a5);
          v42[2](v39, v43);
          v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 80LL))(v39);
          v45 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 56LL))(v39);
          LOBYTE(v46) = 1;
          if ( (unsigned __int8)FMatchStrTxt(v46, a1, v56, v17, v44 - v45, v70, 0, v60, &v61, 0) )
          {
            v47 = *(void (__fastcall ***)(__int64, __int64))v39;
            v48 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 56LL))(v39);
            v47[1](v39, v61 + v48);
            v49 = *(_QWORD *)a5;
            v50 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 48LL))(v39);
            (*(void (__fastcall **)(struct ILobReader *, __int64))(v49 + 16))(a5, v50);
            v13 = (*(__int64 (__fastcall **)(struct ILobReader *))(*(_QWORD *)a5 + 56LL))(a5) + 1;
          }
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 96LL))(v39, 1);
          v12 = v65;
        }
        else
        {
          v51 = (*(__int64 (__fastcall **)(struct ILobReader *))(*(_QWORD *)a5 + 80LL))(a5);
          v52 = (*(__int64 (__fastcall **)(struct ILobReader *))(*(_QWORD *)a5 + 56LL))(a5);
          LOBYTE(v53) = 1;
          if ( (unsigned __int8)FMatchStrTxt(v53, a1, v56, v17, v51 - v52, v70, 0, v60, &v61, 0) )
            v13 = v15 + v61 + 1;
        }
      }
    }
    *((_QWORD *)v66 + 1) = v13;
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
}

```

## disassembly

```asm
0x10049b530  push    rbp
0x10049b532  push    rbx
0x10049b533  push    rsi
0x10049b534  push    rdi
0x10049b535  push    r12
0x10049b537  push    r13
0x10049b539  push    r14
0x10049b53b  push    r15
0x10049b53d  sub     rsp, 198h
0x10049b544  lea     rbp, [rsp+60h]
0x10049b549  mov     [rbp+170h+var_108], 0FFFFFFFFFFFFFFFEh
0x10049b551  mov     rax, cs:__security_cookie
0x10049b558  xor     rax, rbp
0x10049b55b  mov     [rbp+170h+var_50], rax
0x10049b562  mov     rdi, r9
0x10049b565  mov     [rbp+170h+var_140], r8
0x10049b569  mov     r12, rdx
0x10049b56c  mov     r13, rcx
0x10049b56f  mov     rsi, [rbp+170h+arg_40]
0x10049b576  mov     [rbp+170h+var_120], rsi
0x10049b57a  mov     r15, [rbp+170h+arg_20]
0x10049b581  mov     rcx, [rbp+170h+arg_38]
0x10049b588  mov     [rbp+170h+var_150], rcx
0x10049b58c  mov     rcx, [r8+8]
0x10049b590  mov     rax, [rcx]
0x10049b593  xor     edx, edx
0x10049b595  call    qword ptr [rax+8]
0x10049b598  mov     rbx, rax
0x10049b59b  mov     [rbp+170h+var_128], rax
0x10049b59f  mov     rax, [rax]
0x10049b5a2  lea     rdx, [rbp+170h+var_158]
0x10049b5a6  mov     rcx, rbx
0x10049b5a9  call    qword ptr [rax+98h]
0x10049b5af  test    eax, eax
0x10049b5b1  jz      short loc_10049B5C9
0x10049b5b3  mov     edx, 2
0x10049b5b8  lea     ecx, [rdx+45h]
0x10049b5bb  lea     r9d, [rdx+61h]
0x10049b5bf  lea     r8d, [rdx+12h]
0x10049b5c3  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10049b5c9  test    [rbp+170h+var_158], 1
0x10049b5cd  jz      short loc_10049B5D7
0x10049b5cf  mov     byte ptr [rsi], 3
0x10049b5d2  jmp     loc_10049BA9E
0x10049b5d7  mov     rax, [r15]
0x10049b5da  mov     rdx, rbx
0x10049b5dd  mov     rcx, r15
0x10049b5e0  call    qword ptr [rax]
0x10049b5e2  xor     r14d, r14d
0x10049b5e5  cmp     byte ptr [rdi], 0FFh
0x10049b5e8  jz      short loc_10049B5F7
0x10049b5ea  mov     rax, [rdi+8]
0x10049b5ee  test    rax, rax
0x10049b5f1  lea     rsi, [rax-1]
0x10049b5f5  jg      short loc_10049B5FA
0x10049b5f7  mov     rsi, r14
0x10049b5fa  mov     [rbp+170h+var_130], rsi
0x10049b5fe  mov     rax, [r15]
0x10049b601  mov     rdx, rsi
0x10049b604  mov     rcx, r15
0x10049b607  call    qword ptr [rax+8]
0x10049b60a  test    eax, eax
0x10049b60c  jz      loc_10049BA96
0x10049b612  mov     r10, [r12+8]
0x10049b617  mov     [rbp+170h+var_168], r10
0x10049b61b  mov     r12d, [r12+10h]
0x10049b620  movzx   eax, byte ptr [r13+0]
0x10049b625  lea     rdx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10049b62c  movzx   eax, byte ptr [rax+rdx+45AE60h]
0x10049b634  movzx   eax, byte ptr [rax+rdx+45BE40h]
0x10049b63c  mov     byte ptr [rbp+170h+var_170], al
0x10049b63f  mov     rdi, r14
0x10049b642  test    al, al
0x10049b644  jnz     loc_10049B705
0x10049b64a  mov     ecx, [r13+14h]
0x10049b64e  mov     eax, ecx
0x10049b650  shr     eax, 7
0x10049b653  test    al, 1
0x10049b655  jz      short loc_10049B65E
0x10049b657  mov     edx, 0FDE9h
0x10049b65c  jmp     short loc_10049B690
0x10049b65e  mov     eax, ecx
0x10049b660  shr     eax, 18h
0x10049b663  test    al, al
0x10049b665  jnz     short loc_10049B67A
0x10049b667  movzx   eax, cl
0x10049b66a  and     eax, 7Fh
0x10049b66d  shl     rax, 5
0x10049b671  mov     edx, [rax+rdx+456AB0h]
0x10049b678  jmp     short loc_10049B690
0x10049b67a  movzx   eax, al
0x10049b67d  lea     rcx, [rax+rax*4]
0x10049b681  movzx   eax, ds:rva byte_10085C9DC[rdx+rcx*8]; CTypeInfo const CTypeInfo::tiBit ...
0x10049b689  mov     edx, ds:rva ?x_uiCodePage@@3QBIB[rdx+rax*4]; CTypeInfo const CTypeInfo::tiBit
0x10049b690  mov     rax, cs:?m_pSortCache@CSortCacheForSqlCollations@@0PEAV1@EA; CSortCacheForSqlCollations * CSortCacheForSqlCollations::m_pSortCache
0x10049b697  mov     ecx, r14d
0x10049b69a  add     rax, 790h
0x10049b6a0  mov     rdi, [rax]
0x10049b6a3  test    rdi, rdi
0x10049b6a6  jz      short loc_10049B6AD
0x10049b6a8  cmp     [rdi+10h], edx
0x10049b6ab  jz      short loc_10049B6D9
0x10049b6ad  inc     ecx
0x10049b6af  add     rax, 8
0x10049b6b3  cmp     ecx, 11h
0x10049b6b6  jl      short loc_10049B6A0
0x10049b6b8  mov     dword ptr [rsp+1D0h+var_1B0], edx
0x10049b6bc  mov     edx, 4Bh ; 'K'
0x10049b6c1  lea     ecx, [rdx-30h]
0x10049b6c4  lea     r9d, [rdx-4Ah]
0x10049b6c8  lea     r8d, [rdx-3Bh]
0x10049b6cc  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10049b6d2  mov     rdi, r14
0x10049b6d5  mov     r10, [rbp+170h+var_168]
0x10049b6d9  test    r12d, r12d
0x10049b6dc  jz      short loc_10049B702
0x10049b6de  lfence
0x10049b6e1  lea     rcx, [rdi+20h]
0x10049b6e5  mov     rax, [rcx]
0x10049b6e8  mov     byte ptr [rsp+1D0h+var_1B0], r14b
0x10049b6ed  mov     r9d, r12d
0x10049b6f0  mov     r8d, r12d
0x10049b6f3  mov     rdx, r10
0x10049b6f6  call    qword ptr [rax+50h]
0x10049b6f9  mov     r12d, eax
0x10049b6fc  mov     rbx, [rbp+170h+var_128]
0x10049b700  jmp     short loc_10049B705
0x10049b702  mov     r12d, r14d
0x10049b705  mov     [rbp+170h+var_138], r14
0x10049b709  mov     [rbp+170h+var_160], r14d
0x10049b70d  mov     rcx, [rbp+170h+var_140]
0x10049b711  mov     rcx, [rcx+8]
0x10049b715  mov     rax, [rcx]
0x10049b718  lea     r8, [rbp+170h+var_160]
0x10049b71c  lea     rdx, [rbp+170h+var_138]
0x10049b720  call    qword ptr [rax+18h]
0x10049b723  test    eax, eax
0x10049b725  jz      loc_10049B7B8
0x10049b72b  mov     [rbp+170h+var_15C], r14d
0x10049b72f  movzx   eax, byte ptr [r13+0]
0x10049b734  lea     r8, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10049b73b  movzx   edx, byte ptr [rax+r8+45AE60h]
0x10049b744  movzx   edi, byte ptr [rdx+r8+45BE40h]
0x10049b74d  mov     rax, [r15]
0x10049b750  mov     rcx, r15
0x10049b753  call    qword ptr [rax+30h]
0x10049b756  mov     esi, [rbp+170h+var_160]
0x10049b759  sub     esi, eax
0x10049b75b  mov     rax, [r15]
0x10049b75e  mov     rcx, r15
0x10049b761  call    qword ptr [rax+30h]
0x10049b764  add     rax, [rbp+170h+var_138]
0x10049b768  mov     ecx, edi; int
0x10049b76a  mov     [rsp+1D0h+var_180], r14; unsigned __int8 *
0x10049b76f  mov     [rsp+1D0h+var_188], r14b; bool
0x10049b774  mov     [rsp+1D0h+var_190], r14; int *
0x10049b779  lea     rdx, [rbp+170h+var_15C]
0x10049b77d  mov     [rsp+1D0h+var_198], rdx; int *
0x10049b782  mov     rdx, [rbp+170h+var_150]
0x10049b786  mov     [rsp+1D0h+var_1A0], rdx; unsigned __int8 *
0x10049b78b  mov     [rsp+1D0h+var_1A8], esi; int
0x10049b78f  mov     [rsp+1D0h+var_1B0], rax; unsigned __int8 *
0x10049b794  mov     r9d, r12d; int
0x10049b797  mov     r8, [rbp+170h+var_168]; unsigned __int8 *
0x10049b79b  mov     rdx, r13; struct CTypeInfo *
0x10049b79e  call    ?charindex@@YAHHPEBVCTypeInfo@@PEAEH1H1PEAJ2_NPEBE@Z; charindex(int,CTypeInfo const *,uchar *,int,uchar *,int,uchar *,long *,long *,bool,uchar const *)
0x10049b7a3  test    eax, eax
0x10049b7a5  jz      loc_10049BA96
0x10049b7ab  movsxd  r14, [rbp+170h+var_15C]
0x10049b7af  add     r14, [rbp+170h+var_130]
0x10049b7b3  jmp     loc_10049BA96
0x10049b7b8  cmp     byte ptr [rbp+170h+var_170], r14b
0x10049b7bc  jnz     loc_10049B873
0x10049b7c2  mov     rcx, r13; this
0x10049b7c5  call    ?FWindowsSort@CTypeInfo@@QEBA_NXZ; CTypeInfo::FWindowsSort(void)
0x10049b7ca  test    al, al
0x10049b7cc  jz      loc_10049B873
0x10049b7d2  movsxd  rax, r12d
0x10049b7d5  add     rax, rax
0x10049b7d8  lea     rcx, [rax+0Fh]
0x10049b7dc  cmp     rcx, rax
0x10049b7df  ja      short loc_10049B7EB
0x10049b7e1  mov     rcx, 0FFFFFFFFFFFFFF0h
0x10049b7eb  and     rcx, 0FFFFFFFFFFFFFFF0h
0x10049b7ef  mov     rax, rcx
0x10049b7f2  call    _alloca_probe
0x10049b7f7  sub     rsp, rcx
0x10049b7fa  lea     rdx, [rsp+1D0h+var_170]
0x10049b7ff  mov     [rbp+170h+var_140], rdx
0x10049b803  mov     ecx, [r13+14h]
0x10049b807  mov     eax, ecx
0x10049b809  shr     eax, 7
0x10049b80c  test    al, 1
0x10049b80e  jz      short loc_10049B817
0x10049b810  mov     ecx, 0FDE9h
0x10049b815  jmp     short loc_10049B853
0x10049b817  mov     eax, ecx
0x10049b819  shr     eax, 18h
0x10049b81c  lea     r8, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10049b823  test    al, al
0x10049b825  jnz     short loc_10049B83B
0x10049b827  movzx   eax, cl
0x10049b82a  and     eax, 7Fh
0x10049b82d  shl     rax, 5
0x10049b831  mov     ecx, [rax+r8+456AB0h]
0x10049b839  jmp     short loc_10049B853
0x10049b83b  movzx   eax, al
0x10049b83e  lea     rcx, [rax+rax*4]
0x10049b842  movzx   eax, ds:rva byte_10085C9DC[r8+rcx*8]; CTypeInfo const CTypeInfo::tiBit ...
0x10049b84b  mov     ecx, ds:rva ?x_uiCodePage@@3QBIB[r8+rax*4]; unsigned int
0x10049b853  mov     dword ptr [rsp+1D0h+var_1B0], r12d; int
0x10049b858  mov     r9, rdx; wchar_t *
0x10049b85b  mov     r8d, r12d; int
0x10049b85e  mov     rdx, [rbp+170h+var_168]; char *
0x10049b862  call    ?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z; FastDBCSToUnicode(uint,char const *,int,wchar_t *,int)
0x10049b867  mov     rcx, [rbp+170h+var_140]
0x10049b86b  mov     [rbp+170h+var_168], rcx
0x10049b86f  lea     r12d, [rax+rax]
0x10049b873  mov     [rbp+170h+var_E0], r14d
0x10049b87a  mov     [rbp+170h+var_CC], r14d
0x10049b881  mov     [rbp+170h+var_B0], r14
0x10049b888  mov     rax, [r15]
0x10049b88b  mov     rcx, r15
0x10049b88e  call    qword ptr [rax+48h]
0x10049b891  mov     qword ptr [rbp+170h+var_118+8], rax
0x10049b895  mov     r9, [rax]
0x10049b898  xor     r8d, r8d
0x10049b89b  lea     rdx, [rbp+170h+var_A0]
0x10049b8a2  mov     rcx, rax
0x10049b8a5  call    qword ptr [r9+48h]
0x10049b8a9  mov     rax, [rbp+170h+var_90]
0x10049b8b0  mov     qword ptr [rbp+170h+var_118], rax
0x10049b8b4  mov     rax, [r15]
0x10049b8b7  mov     rcx, r15
0x10049b8ba  call    qword ptr [rax+30h]
0x10049b8bd  movups  xmm0, [rbp+170h+var_118]
0x10049b8c1  movups  [rbp+170h+var_C8], xmm0
0x10049b8c8  mov     rcx, [rbp+170h+arg_28]
0x10049b8cf  mov     [rbp+170h+var_D8], rcx
0x10049b8d6  mov     ecx, [rbp+170h+arg_30]
0x10049b8dc  mov     [rbp+170h+var_D0], ecx
0x10049b8e2  mov     [rbp+170h+var_E8], rax
0x10049b8e9  mov     [rbp+170h+var_F0], r14
0x10049b8f0  test    rdi, rdi
0x10049b8f3  jz      loc_10049BA32
0x10049b8f9  mov     rax, [rdi+20h]
0x10049b8fd  lea     rcx, [rdi+20h]
0x10049b901  call    qword ptr [rax+68h]
0x10049b904  test    al, al
0x10049b906  jz      loc_10049BA32
0x10049b90c  mov     rdx, gs:58h
0x10049b915  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10049b91c  mov     ecx, [rax]
0x10049b91e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10049b925  mov     ebx, [rax]
0x10049b927  add     rbx, [rdx+rcx*8]
0x10049b92b  mov     rdx, [rbx+100h]
0x10049b932  test    rdx, rdx
0x10049b935  jnz     short loc_10049B946
0x10049b937  xor     ecx, ecx
0x10049b939  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049b93f  mov     rdx, [rbx+100h]
0x10049b946  mov     rax, [rdi+20h]
0x10049b94a  mov     r8b, 1
0x10049b94d  mov     rdx, [rdx+3E8h]
0x10049b954  lea     rcx, [rdi+20h]
0x10049b958  call    qword ptr [rax+58h]
0x10049b95b  mov     rdi, rax
0x10049b95e  mov     [rbp+170h+var_100], rax
0x10049b962  mov     rbx, [rax]
0x10049b965  mov     rdx, [r15]
0x10049b968  mov     rcx, r15
0x10049b96b  call    qword ptr [rdx+48h]
0x10049b96e  mov     rdx, rax
0x10049b971  mov     rcx, rdi
0x10049b974  call    qword ptr [rbx]
0x10049b976  mov     rbx, [rdi]
0x10049b979  mov     rdx, [r15]
0x10049b97c  mov     rcx, r15
0x10049b97f  call    qword ptr [rdx+30h]
0x10049b982  mov     rdx, rax
0x10049b985  mov     rcx, rdi
0x10049b988  call    qword ptr [rbx+10h]
0x10049b98b  mov     rax, [rdi]
0x10049b98e  mov     rcx, rdi
0x10049b991  call    qword ptr [rax+50h]
0x10049b994  mov     rbx, rax
0x10049b997  mov     rdx, [rdi]
0x10049b99a  mov     rcx, rdi
0x10049b99d  call    qword ptr [rdx+38h]
0x10049b9a0  sub     rbx, rax
0x10049b9a3  mov     qword ptr [rsp+1D0h+var_188], r14
0x10049b9a8  lea     rax, [rbp+170h+var_148]
0x10049b9ac  mov     [rsp+1D0h+var_190], rax
0x10049b9b1  mov     rdx, [rbp+170h+var_150]
0x10049b9b5  mov     [rsp+1D0h+var_198], rdx
0x10049b9ba  mov     [rsp+1D0h+var_1A0], r14
0x10049b9bf  lea     rax, [rbp+170h+var_F0]
0x10049b9c6  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x10049b9cb  mov     [rsp+1D0h+var_1B0], rbx
  ... truncated ...
```
