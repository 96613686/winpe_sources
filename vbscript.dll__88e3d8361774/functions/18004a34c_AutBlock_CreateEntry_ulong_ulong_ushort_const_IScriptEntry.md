# AutBlock::CreateEntry(ulong,ulong,ushort const *,IScriptEntry * *)

- ea: `0x18004a34c`
- end: `0x18004a70a`
- name: `?CreateEntry@AutBlock@@IEAAJKKPEBGPEAPEAUIScriptEntry@@@Z`
- size: `958`
- prototype: `__int64 __usercall@<rax>(AutBlock *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, struct IScriptEntry **)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18004a080`
- `0x18004a170`

## callees

- `0x18002bc28`
- `0x18003bc44`
- `0x18003c750`
- `0x18003f1fc`
- `0x180040a6c`
- `0x180045490`
- `0x180049678`
- `0x180049ddc`
- `0x18004a34c`
- `0x18007672e`
- `0x18007673a`
- `0x180077010`

## import_xrefs

- `msvcrt!wcschr` at `0x18004a58e`
- `msvcrt!wcschr` at `0x18004a58e`
- `msvcrt!free` at `0x18004a679`
- `msvcrt!free` at `0x18004a679`

## pseudocode

```c
__int64 __fastcall AutBlock::CreateEntry(
        AutBlock *this,
        int a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        struct IScriptEntry **a5)
{
  int v8; // r13d
  int *v9; // r9
  int v10; // r14d
  int appended; // ebx
  int v12; // r15d
  int v13; // r12d
  int v14; // r8d
  struct AutEntry *v15; // rbx
  wchar_t *v16; // rax
  __int64 v17; // r15
  int v18; // eax
  __int64 v19; // r15
  size_t v20; // r13
  int v21; // r14d
  char *v22; // rax
  int v23; // r15d
  int v24; // r8d
  unsigned __int16 *v25; // r14
  void *v26; // rcx
  __int64 v27; // rcx
  unsigned int v28; // esi
  int v29; // r12d
  AutEntry *v30; // rcx
  int v32; // [rsp+20h] [rbp-40h]
  int v33; // [rsp+24h] [rbp-3Ch]
  int v34; // [rsp+28h] [rbp-38h]
  struct AutEntry *Src; // [rsp+30h] [rbp-30h] BYREF
  AutEntry *v36; // [rsp+38h] [rbp-28h] BYREF
  __int64 v37; // [rsp+40h] [rbp-20h] BYREF
  __int64 v38; // [rsp+48h] [rbp-18h]
  int v39; // [rsp+50h] [rbp-10h]
  int v40; // [rsp+A0h] [rbp+40h]
  char *v41; // [rsp+A0h] [rbp+40h]

  v37 = 0;
  v38 = 0;
  v32 = 0;
  *a5 = 0;
  v8 = 0;
  v9 = (int *)*((_QWORD *)this + 4);
  v39 = 0;
  Src = 0;
  v36 = 0;
  if ( !v9 )
  {
    v9 = (int *)operator new(0x20u);
    if ( !v9 )
    {
      *((_QWORD *)this + 4) = 0;
LABEL_22:
      appended = -2147024882;
      goto LABEL_40;
    }
    v9[2] = 1;
    *(_QWORD *)v9 = &GL::`vftable';
    v9[3] = 8;
    *((_QWORD *)v9 + 2) = 0;
    *((_QWORD *)v9 + 3) = 0;
    *((_QWORD *)this + 4) = v9;
  }
  if ( a2 < (unsigned int)v9[7] )
  {
    memcpy_0(&Src, (const void *)(*((_QWORD *)v9 + 2) + a2 * v9[3]), v9[3]);
    if ( !Src )
    {
      appended = -2147467259;
      goto LABEL_40;
    }
    v10 = *((_DWORD *)Src + 8);
  }
  else
  {
    v10 = *((_DWORD *)this + 18);
    a2 = v9[7];
  }
  if ( v10 > 0 )
  {
    appended = BuildString::AppendSz((BuildString *)&v37, *((const unsigned __int16 **)this + 8), v10);
    if ( appended < 0 )
      goto LABEL_40;
    v8 = HIDWORD(v38);
    v32 = HIDWORD(v38);
  }
  appended = BuildString::AppendSz((BuildString *)&v37, L"Sub ", -1);
  if ( appended >= 0 )
  {
    v40 = HIDWORD(v38);
    appended = BuildString::AppendSz((BuildString *)&v37, a4, -1);
    if ( appended >= 0 )
    {
      v12 = HIDWORD(v38);
      appended = BuildString::AppendSz((BuildString *)&v37, L"\n", -1);
      if ( appended >= 0 )
      {
        v33 = HIDWORD(v38);
        appended = BuildString::AppendSz((BuildString *)&v37, L"\n", -1);
        if ( appended >= 0 )
        {
          v34 = HIDWORD(v38);
          appended = BuildString::AppendSz((BuildString *)&v37, L"End Sub\n", -1);
          if ( appended >= 0 )
          {
            v13 = HIDWORD(v38);
            appended = BuildString::AppendSz((BuildString *)&v37, L"\n", -1);
            if ( appended >= 0 )
            {
              v14 = *((_DWORD *)this + 18);
              if ( v10 >= v14
                || (appended = BuildString::AppendSz(
                                 (BuildString *)&v37,
                                 (const unsigned __int16 *)(*((_QWORD *)this + 8) + 2LL * v10),
                                 v14 - v10),
                    appended >= 0) )
              {
                if ( v39 )
                  goto LABEL_22;
                appended = AutEntry::Create(&Src, this, a3);
                if ( appended < 0 )
                  goto LABEL_40;
                v15 = Src;
                *((_DWORD *)Src + 8) = v8;
                *((_DWORD *)v15 + 9) = v13;
                *((_DWORD *)v15 + 18) = v33;
                *((_DWORD *)v15 + 19) = v34;
                v16 = wcschr(a4, 0x28u);
                if ( v16 )
                {
                  v17 = (char *)v16 - (char *)a4;
                  v18 = v40;
                  v12 = v40 + (v17 >> 1);
                }
                else
                {
                  v18 = v40;
                }
                *((_DWORD *)v15 + 10) = v18;
                *((_DWORD *)v15 + 11) = v12;
                v19 = *((_QWORD *)this + 4);
                v20 = *(int *)(v19 + 12);
                v21 = v20 * (*(_DWORD *)(v19 + 28) + 1);
                if ( v21 > *(_DWORD *)(v19 + 24) && !(unsigned int)GL::FEnsureSize(*((GL **)this + 4), v21) )
                {
LABEL_29:
                  (*(void (__fastcall **)(struct AutEntry *))(*(_QWORD *)v15 + 192LL))(v15);
                  (*(void (__fastcall **)(struct AutEntry *))(*(_QWORD *)v15 + 16LL))(v15);
                  goto LABEL_22;
                }
                v22 = (char *)(a2 * (int)v20 + *(_QWORD *)(v19 + 16));
                v41 = v22;
                if ( a2 < *(_DWORD *)(v19 + 28) )
                {
                  memmove_0(&v22[v20], v22, v21 - (int)v20 - a2 * (int)v20);
                  v22 = v41;
                }
                memcpy_0(v22, &Src, v20);
                ++*(_DWORD *)(v19 + 28);
                v23 = HIDWORD(v38);
                *((_DWORD *)v15 + 7) = a2;
                v25 = BuildString::PszReset((BuildString *)&v37);
                if ( !v25 )
                {
                  GL::Delete(*((GL **)this + 4), a2, v24);
                  goto LABEL_29;
                }
                v26 = (void *)*((_QWORD *)this + 8);
                if ( v26 )
                  free(v26);
                v27 = *((_QWORD *)this + 4);
                v28 = a2 + 1;
                *((_QWORD *)this + 8) = v25;
                *((_DWORD *)this + 18) = v23;
                if ( v28 < *(_DWORD *)(v27 + 28) )
                {
                  v29 = v13 - v32;
                  do
                  {
                    memcpy_0(
                      &v36,
                      (const void *)(*(_QWORD *)(v27 + 16) + (int)(v28 * *(_DWORD *)(v27 + 12))),
                      *(int *)(v27 + 12));
                    v30 = v36;
                    *((_DWORD *)v36 + 7) = v28;
                    AutEntry::AdjustOffsets(v30, v29 + 1);
                    v27 = *((_QWORD *)this + 4);
                    ++v28;
                  }
                  while ( v28 < *(_DWORD *)(v27 + 28) );
                }
                appended = (**(__int64 (__fastcall ***)(struct AutEntry *, GUID *, struct IScriptEntry **))v15)(
                             v15,
                             &IID_IScriptEntry,
                             a5);
              }
            }
          }
        }
      }
    }
  }
LABEL_40:
  BuildString::Reset((BuildString *)&v37);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18004a34c  mov     [rsp-38h+arg_8], rbx
0x18004a351  mov     [rsp-38h+Str], r9
0x18004a356  mov     [rsp-38h+arg_10], r8d
0x18004a35b  push    rbp
0x18004a35c  push    rsi
0x18004a35d  push    rdi
0x18004a35e  push    r12
0x18004a360  push    r13
0x18004a362  push    r14
0x18004a364  push    r15
0x18004a366  mov     rbp, rsp
0x18004a369  sub     rsp, 60h
0x18004a36d  mov     rax, [rbp+arg_20]
0x18004a371  xor     r12d, r12d
0x18004a374  mov     r15, r9
0x18004a377  mov     [rbp+var_20], r12
0x18004a37b  mov     esi, edx
0x18004a37d  mov     [rbp+var_18], r12
0x18004a381  mov     rdi, rcx
0x18004a384  mov     [rbp+var_40], r12d
0x18004a388  mov     [rax], r12
0x18004a38b  mov     r13d, r12d
0x18004a38e  mov     r9, [rcx+20h]
0x18004a392  mov     [rbp+var_10], r12d
0x18004a396  mov     [rbp+Src], r12
0x18004a39a  mov     [rbp+var_28], r12
0x18004a39e  test    r9, r9
0x18004a3a1  jnz     short loc_18004A3DB
0x18004a3a3  lea     ecx, [r12+20h]; Size
0x18004a3a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004a3ad  mov     r9, rax
0x18004a3b0  test    rax, rax
0x18004a3b3  jz      short loc_18004A3EB
0x18004a3b5  lea     rax, ??_7GL@@6B@; const GL::`vftable'
0x18004a3bc  mov     dword ptr [r9+8], 1
0x18004a3c4  mov     [r9], rax
0x18004a3c7  mov     dword ptr [r9+0Ch], 8
0x18004a3cf  mov     [r9+10h], r12
0x18004a3d3  mov     [r9+18h], r12
0x18004a3d7  mov     [rdi+20h], r9
0x18004a3db  mov     eax, [r9+1Ch]
0x18004a3df  cmp     esi, eax
0x18004a3e1  jb      short loc_18004A3F4
0x18004a3e3  mov     r14d, [rdi+48h]
0x18004a3e7  mov     esi, eax
0x18004a3e9  jmp     short loc_18004A425
0x18004a3eb  mov     [rdi+20h], r12
0x18004a3ef  jmp     loc_18004A546
0x18004a3f4  movsxd  rax, dword ptr [r9+0Ch]
0x18004a3f8  lea     rcx, [rbp+Src]; void *
0x18004a3fc  mov     r8, rax; Size
0x18004a3ff  imul    eax, esi
0x18004a402  movsxd  rdx, eax
0x18004a405  add     rdx, [r9+10h]; Src
0x18004a409  call    memcpy_0
0x18004a40e  mov     r14, [rbp+Src]
0x18004a412  test    r14, r14
0x18004a415  jnz     short loc_18004A421
0x18004a417  mov     ebx, 80004005h
0x18004a41c  jmp     loc_18004A6E7
0x18004a421  mov     r14d, [r14+20h]
0x18004a425  test    r14d, r14d
0x18004a428  jle     short loc_18004A44C
0x18004a42a  mov     rdx, [rdi+40h]; unsigned __int16 *
0x18004a42e  lea     rcx, [rbp+var_20]; this
0x18004a432  mov     r8d, r14d; int
0x18004a435  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004a43a  mov     ebx, eax
0x18004a43c  test    eax, eax
0x18004a43e  js      loc_18004A6E7
0x18004a444  mov     r13d, dword ptr [rbp+var_18+4]
0x18004a448  mov     [rbp+var_40], r13d
0x18004a44c  or      r8d, 0FFFFFFFFh; int
0x18004a450  lea     rdx, aSub_0; "Sub "
0x18004a457  lea     rcx, [rbp+var_20]; this
0x18004a45b  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004a460  mov     ebx, eax
0x18004a462  test    eax, eax
0x18004a464  js      loc_18004A6E7
0x18004a46a  mov     eax, dword ptr [rbp+var_18+4]
0x18004a46d  lea     rcx, [rbp+var_20]; this
0x18004a471  or      r8d, 0FFFFFFFFh; int
0x18004a475  mov     dword ptr [rbp+arg_0], eax
0x18004a478  mov     rdx, r15; unsigned __int16 *
0x18004a47b  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004a480  mov     ebx, eax
0x18004a482  test    eax, eax
0x18004a484  js      loc_18004A6E7
0x18004a48a  mov     r15d, dword ptr [rbp+var_18+4]
0x18004a48e  lea     rdx, strIn; "\n"
0x18004a495  or      r8d, 0FFFFFFFFh; int
0x18004a499  lea     rcx, [rbp+var_20]; this
0x18004a49d  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004a4a2  mov     ebx, eax
0x18004a4a4  test    eax, eax
0x18004a4a6  js      loc_18004A6E7
0x18004a4ac  mov     eax, dword ptr [rbp+var_18+4]
0x18004a4af  lea     rdx, strIn; "\n"
0x18004a4b6  or      r8d, 0FFFFFFFFh; int
0x18004a4ba  mov     [rbp+var_3C], eax
0x18004a4bd  lea     rcx, [rbp+var_20]; this
0x18004a4c1  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004a4c6  mov     ebx, eax
0x18004a4c8  test    eax, eax
0x18004a4ca  js      loc_18004A6E7
0x18004a4d0  mov     eax, dword ptr [rbp+var_18+4]
0x18004a4d3  lea     rdx, aEndSub; "End Sub\n"
0x18004a4da  or      r8d, 0FFFFFFFFh; int
0x18004a4de  mov     [rbp+var_38], eax
0x18004a4e1  lea     rcx, [rbp+var_20]; this
0x18004a4e5  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004a4ea  mov     ebx, eax
0x18004a4ec  test    eax, eax
0x18004a4ee  js      loc_18004A6E7
0x18004a4f4  mov     r12d, dword ptr [rbp+var_18+4]
0x18004a4f8  lea     rdx, strIn; "\n"
0x18004a4ff  or      r8d, 0FFFFFFFFh; int
0x18004a503  lea     rcx, [rbp+var_20]; this
0x18004a507  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004a50c  mov     ebx, eax
0x18004a50e  test    eax, eax
0x18004a510  js      loc_18004A6E7
0x18004a516  mov     r8d, [rdi+48h]
0x18004a51a  cmp     r14d, r8d
0x18004a51d  jge     short loc_18004A540
0x18004a51f  mov     rax, [rdi+40h]
0x18004a523  sub     r8d, r14d; int
0x18004a526  movsxd  rcx, r14d
0x18004a529  lea     rdx, [rax+rcx*2]; unsigned __int16 *
0x18004a52d  lea     rcx, [rbp+var_20]; this
0x18004a531  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004a536  mov     ebx, eax
0x18004a538  test    eax, eax
0x18004a53a  js      loc_18004A6E7
0x18004a540  cmp     [rbp+var_10], 0
0x18004a544  jz      short loc_18004A550
0x18004a546  mov     ebx, 8007000Eh
0x18004a54b  jmp     loc_18004A6E7
0x18004a550  mov     r8d, [rbp+arg_10]; unsigned int
0x18004a554  lea     rcx, [rbp+Src]; struct AutEntry **
0x18004a558  mov     rdx, rdi; struct AutBlock *
0x18004a55b  call    ?Create@AutEntry@@SAJPEAPEAV1@PEAVAutBlock@@K@Z; AutEntry::Create(AutEntry * *,AutBlock *,ulong)
0x18004a560  mov     ebx, eax
0x18004a562  test    eax, eax
0x18004a564  js      loc_18004A6E7
0x18004a56a  mov     rbx, [rbp+Src]
0x18004a56e  mov     edx, 28h ; '('; Ch
0x18004a573  mov     eax, [rbp+var_3C]
0x18004a576  mov     r14, [rbp+Str]
0x18004a57a  mov     rcx, r14; Str
0x18004a57d  mov     [rbx+20h], r13d
0x18004a581  mov     [rbx+24h], r12d
0x18004a585  mov     [rbx+48h], eax
0x18004a588  mov     eax, [rbp+var_38]
0x18004a58b  mov     [rbx+4Ch], eax
0x18004a58e  call    cs:__imp_wcschr
0x18004a594  test    rax, rax
0x18004a597  jz      short loc_18004A5AA
0x18004a599  sub     rax, r14
0x18004a59c  mov     r15, rax
0x18004a59f  mov     eax, dword ptr [rbp+arg_0]
0x18004a5a2  sar     r15, 1
0x18004a5a5  add     r15d, eax
0x18004a5a8  jmp     short loc_18004A5AD
0x18004a5aa  mov     eax, dword ptr [rbp+arg_0]
0x18004a5ad  mov     [rbx+28h], eax
0x18004a5b0  mov     [rbx+2Ch], r15d
0x18004a5b4  mov     r15, [rdi+20h]
0x18004a5b8  mov     r14d, [r15+1Ch]
0x18004a5bc  movsxd  r13, dword ptr [r15+0Ch]
0x18004a5c0  inc     r14d
0x18004a5c3  imul    r14d, r13d
0x18004a5c7  cmp     r14d, [r15+18h]
0x18004a5cb  jle     short loc_18004A602
0x18004a5cd  mov     edx, r14d; int
0x18004a5d0  mov     rcx, r15; this
0x18004a5d3  call    ?FEnsureSize@GL@@AEAAHJ@Z; GL::FEnsureSize(long)
0x18004a5d8  test    eax, eax
0x18004a5da  jnz     short loc_18004A602
0x18004a5dc  mov     rax, [rbx]
0x18004a5df  mov     rcx, rbx
0x18004a5e2  mov     rax, [rax+0C0h]
0x18004a5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a5ee  mov     rax, [rbx]
0x18004a5f1  mov     rcx, rbx
0x18004a5f4  mov     rax, [rax+10h]
0x18004a5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a5fd  jmp     loc_18004A546
0x18004a602  mov     rax, [r15+10h]
0x18004a606  mov     edx, r13d
0x18004a609  imul    edx, esi
0x18004a60c  movsxd  rcx, edx
0x18004a60f  add     rax, rcx
0x18004a612  mov     [rbp+arg_0], rax
0x18004a616  cmp     esi, [r15+1Ch]
0x18004a61a  jge     short loc_18004A635
0x18004a61c  sub     r14d, r13d
0x18004a61f  lea     rcx, [rax+r13]; void *
0x18004a623  sub     r14d, edx
0x18004a626  mov     rdx, rax; Src
0x18004a629  movsxd  r8, r14d; Size
0x18004a62c  call    memmove_0
0x18004a631  mov     rax, [rbp+arg_0]
0x18004a635  mov     r8, r13; Size
0x18004a638  lea     rdx, [rbp+Src]; Src
0x18004a63c  mov     rcx, rax; void *
0x18004a63f  call    memcpy_0
0x18004a644  inc     dword ptr [r15+1Ch]
0x18004a648  lea     rcx, [rbp+var_20]; this
0x18004a64c  mov     r15d, dword ptr [rbp+var_18+4]
0x18004a650  mov     [rbx+1Ch], esi
0x18004a653  call    ?PszReset@BuildString@@QEAAPEAGXZ; BuildString::PszReset(void)
0x18004a658  mov     r14, rax
0x18004a65b  test    rax, rax
0x18004a65e  jnz     short loc_18004A670
0x18004a660  mov     rcx, [rdi+20h]; this
0x18004a664  mov     edx, esi; int
0x18004a666  call    ?Delete@GL@@QEAAXJJ@Z; GL::Delete(long,long)
0x18004a66b  jmp     loc_18004A5DC
0x18004a670  mov     rcx, [rdi+40h]; Block
0x18004a674  test    rcx, rcx
0x18004a677  jz      short loc_18004A67F
0x18004a679  call    cs:__imp_free
0x18004a67f  mov     rcx, [rdi+20h]
0x18004a683  inc     esi
0x18004a685  mov     [rdi+40h], r14
0x18004a689  mov     [rdi+48h], r15d
0x18004a68d  cmp     esi, [rcx+1Ch]
0x18004a690  jnb     short loc_18004A6CC
0x18004a692  sub     r12d, [rbp+var_40]
0x18004a696  movsxd  rax, dword ptr [rcx+0Ch]
0x18004a69a  mov     r8, rax; Size
0x18004a69d  imul    eax, esi
0x18004a6a0  movsxd  rdx, eax
0x18004a6a3  add     rdx, [rcx+10h]; Src
0x18004a6a7  lea     rcx, [rbp+var_28]; void *
0x18004a6ab  call    memcpy_0
0x18004a6b0  mov     rcx, [rbp+var_28]; this
0x18004a6b4  lea     edx, [r12+1]; int
0x18004a6b9  mov     [rcx+1Ch], esi
0x18004a6bc  call    ?AdjustOffsets@AutEntry@@QEAAXJ@Z; AutEntry::AdjustOffsets(long)
0x18004a6c1  mov     rcx, [rdi+20h]
0x18004a6c5  inc     esi
0x18004a6c7  cmp     esi, [rcx+1Ch]
0x18004a6ca  jb      short loc_18004A696
0x18004a6cc  mov     rax, [rbx]
0x18004a6cf  lea     rdx, IID_IScriptEntry
0x18004a6d6  mov     r8, [rbp+arg_20]
0x18004a6da  mov     rcx, rbx
0x18004a6dd  mov     rax, [rax]
0x18004a6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6e5  mov     ebx, eax
0x18004a6e7  lea     rcx, [rbp+var_20]; this
0x18004a6eb  call    ?Reset@BuildString@@QEAAXXZ; BuildString::Reset(void)
0x18004a6f0  mov     eax, ebx
0x18004a6f2  mov     rbx, [rsp+60h+arg_8]
0x18004a6fa  add     rsp, 60h
0x18004a6fe  pop     r15
0x18004a700  pop     r14
0x18004a702  pop     r13
0x18004a704  pop     r12
0x18004a706  pop     rdi
0x18004a707  pop     rsi
0x18004a708  pop     rbp
0x18004a709  retn
```
