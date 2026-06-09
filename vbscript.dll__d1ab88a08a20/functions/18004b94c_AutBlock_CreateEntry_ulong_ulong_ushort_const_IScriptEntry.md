# AutBlock::CreateEntry(ulong,ulong,ushort const *,IScriptEntry * *)

- ea: `0x18004b94c`
- end: `0x18004bd17`
- name: `?CreateEntry@AutBlock@@IEAAJKKPEBGPEAPEAUIScriptEntry@@@Z`
- size: `971`
- prototype: `__int64 __usercall@<rax>(AutBlock *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, struct IScriptEntry **)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18004b680`
- `0x18004b770`

## callees

- `0x180011870`
- `0x180011a58`
- `0x18003d310`
- `0x180040a9c`
- `0x180042108`
- `0x180046884`
- `0x18004ac54`
- `0x18004b3e0`
- `0x18004b94c`
- `0x18007941e`
- `0x18007942a`
- `0x18007a010`

## import_xrefs

- `msvcrt!wcschr` at `0x18004bb8e`
- `msvcrt!wcschr` at `0x18004bb8e`
- `msvcrt!free` at `0x18004bc7f`
- `msvcrt!free` at `0x18004bc7f`

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
0x18004b94c  mov     [rsp-38h+arg_8], rbx
0x18004b951  mov     [rsp-38h+Str], r9
0x18004b956  mov     [rsp-38h+arg_10], r8d
0x18004b95b  push    rbp
0x18004b95c  push    rsi
0x18004b95d  push    rdi
0x18004b95e  push    r12
0x18004b960  push    r13
0x18004b962  push    r14
0x18004b964  push    r15
0x18004b966  mov     rbp, rsp
0x18004b969  sub     rsp, 60h
0x18004b96d  mov     rax, [rbp+arg_20]
0x18004b971  xor     r12d, r12d
0x18004b974  mov     r15, r9
0x18004b977  mov     [rbp+var_20], r12
0x18004b97b  mov     esi, edx
0x18004b97d  mov     [rbp+var_18], r12
0x18004b981  mov     rdi, rcx
0x18004b984  mov     [rbp+var_40], r12d
0x18004b988  mov     [rax], r12
0x18004b98b  mov     r13d, r12d
0x18004b98e  mov     r9, [rcx+20h]
0x18004b992  mov     [rbp+var_10], r12d
0x18004b996  mov     [rbp+Src], r12
0x18004b99a  mov     [rbp+var_28], r12
0x18004b99e  test    r9, r9
0x18004b9a1  jnz     short loc_18004B9DB
0x18004b9a3  lea     ecx, [r12+20h]; Size
0x18004b9a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004b9ad  mov     r9, rax
0x18004b9b0  test    rax, rax
0x18004b9b3  jz      short loc_18004B9EB
0x18004b9b5  lea     rax, ??_7GL@@6B@; const GL::`vftable'
0x18004b9bc  mov     dword ptr [r9+8], 1
0x18004b9c4  mov     [r9], rax
0x18004b9c7  mov     dword ptr [r9+0Ch], 8
0x18004b9cf  mov     [r9+10h], r12
0x18004b9d3  mov     [r9+18h], r12
0x18004b9d7  mov     [rdi+20h], r9
0x18004b9db  mov     eax, [r9+1Ch]
0x18004b9df  cmp     esi, eax
0x18004b9e1  jb      short loc_18004B9F4
0x18004b9e3  mov     r14d, [rdi+48h]
0x18004b9e7  mov     esi, eax
0x18004b9e9  jmp     short loc_18004BA25
0x18004b9eb  mov     [rdi+20h], r12
0x18004b9ef  jmp     loc_18004BB46
0x18004b9f4  movsxd  rax, dword ptr [r9+0Ch]
0x18004b9f8  lea     rcx, [rbp+Src]; void *
0x18004b9fc  mov     r8, rax; Size
0x18004b9ff  imul    eax, esi
0x18004ba02  movsxd  rdx, eax
0x18004ba05  add     rdx, [r9+10h]; Src
0x18004ba09  call    memcpy_0
0x18004ba0e  mov     r14, [rbp+Src]
0x18004ba12  test    r14, r14
0x18004ba15  jnz     short loc_18004BA21
0x18004ba17  mov     ebx, 80004005h
0x18004ba1c  jmp     loc_18004BCF3
0x18004ba21  mov     r14d, [r14+20h]
0x18004ba25  test    r14d, r14d
0x18004ba28  jle     short loc_18004BA4C
0x18004ba2a  mov     rdx, [rdi+40h]; unsigned __int16 *
0x18004ba2e  lea     rcx, [rbp+var_20]; this
0x18004ba32  mov     r8d, r14d; int
0x18004ba35  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004ba3a  mov     ebx, eax
0x18004ba3c  test    eax, eax
0x18004ba3e  js      loc_18004BCF3
0x18004ba44  mov     r13d, dword ptr [rbp+var_18+4]
0x18004ba48  mov     [rbp+var_40], r13d
0x18004ba4c  or      r8d, 0FFFFFFFFh; int
0x18004ba50  lea     rdx, aSub_0; "Sub "
0x18004ba57  lea     rcx, [rbp+var_20]; this
0x18004ba5b  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004ba60  mov     ebx, eax
0x18004ba62  test    eax, eax
0x18004ba64  js      loc_18004BCF3
0x18004ba6a  mov     eax, dword ptr [rbp+var_18+4]
0x18004ba6d  lea     rcx, [rbp+var_20]; this
0x18004ba71  or      r8d, 0FFFFFFFFh; int
0x18004ba75  mov     dword ptr [rbp+arg_0], eax
0x18004ba78  mov     rdx, r15; unsigned __int16 *
0x18004ba7b  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004ba80  mov     ebx, eax
0x18004ba82  test    eax, eax
0x18004ba84  js      loc_18004BCF3
0x18004ba8a  mov     r15d, dword ptr [rbp+var_18+4]
0x18004ba8e  lea     rdx, asc_18007FF34; "\n"
0x18004ba95  or      r8d, 0FFFFFFFFh; int
0x18004ba99  lea     rcx, [rbp+var_20]; this
0x18004ba9d  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004baa2  mov     ebx, eax
0x18004baa4  test    eax, eax
0x18004baa6  js      loc_18004BCF3
0x18004baac  mov     eax, dword ptr [rbp+var_18+4]
0x18004baaf  lea     rdx, asc_18007FF34; "\n"
0x18004bab6  or      r8d, 0FFFFFFFFh; int
0x18004baba  mov     [rbp+var_3C], eax
0x18004babd  lea     rcx, [rbp+var_20]; this
0x18004bac1  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004bac6  mov     ebx, eax
0x18004bac8  test    eax, eax
0x18004baca  js      loc_18004BCF3
0x18004bad0  mov     eax, dword ptr [rbp+var_18+4]
0x18004bad3  lea     rdx, aEndSub; "End Sub\n"
0x18004bada  or      r8d, 0FFFFFFFFh; int
0x18004bade  mov     [rbp+var_38], eax
0x18004bae1  lea     rcx, [rbp+var_20]; this
0x18004bae5  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004baea  mov     ebx, eax
0x18004baec  test    eax, eax
0x18004baee  js      loc_18004BCF3
0x18004baf4  mov     r12d, dword ptr [rbp+var_18+4]
0x18004baf8  lea     rdx, asc_18007FF34; "\n"
0x18004baff  or      r8d, 0FFFFFFFFh; int
0x18004bb03  lea     rcx, [rbp+var_20]; this
0x18004bb07  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004bb0c  mov     ebx, eax
0x18004bb0e  test    eax, eax
0x18004bb10  js      loc_18004BCF3
0x18004bb16  mov     r8d, [rdi+48h]
0x18004bb1a  cmp     r14d, r8d
0x18004bb1d  jge     short loc_18004BB40
0x18004bb1f  mov     rax, [rdi+40h]
0x18004bb23  sub     r8d, r14d; int
0x18004bb26  movsxd  rcx, r14d
0x18004bb29  lea     rdx, [rax+rcx*2]; unsigned __int16 *
0x18004bb2d  lea     rcx, [rbp+var_20]; this
0x18004bb31  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004bb36  mov     ebx, eax
0x18004bb38  test    eax, eax
0x18004bb3a  js      loc_18004BCF3
0x18004bb40  cmp     [rbp+var_10], 0
0x18004bb44  jz      short loc_18004BB50
0x18004bb46  mov     ebx, 8007000Eh
0x18004bb4b  jmp     loc_18004BCF3
0x18004bb50  mov     r8d, [rbp+arg_10]; unsigned int
0x18004bb54  lea     rcx, [rbp+Src]; struct AutEntry **
0x18004bb58  mov     rdx, rdi; struct AutBlock *
0x18004bb5b  call    ?Create@AutEntry@@SAJPEAPEAV1@PEAVAutBlock@@K@Z; AutEntry::Create(AutEntry * *,AutBlock *,ulong)
0x18004bb60  mov     ebx, eax
0x18004bb62  test    eax, eax
0x18004bb64  js      loc_18004BCF3
0x18004bb6a  mov     rbx, [rbp+Src]
0x18004bb6e  mov     edx, 28h ; '('; Ch
0x18004bb73  mov     eax, [rbp+var_3C]
0x18004bb76  mov     r14, [rbp+Str]
0x18004bb7a  mov     rcx, r14; Str
0x18004bb7d  mov     [rbx+20h], r13d
0x18004bb81  mov     [rbx+24h], r12d
0x18004bb85  mov     [rbx+48h], eax
0x18004bb88  mov     eax, [rbp+var_38]
0x18004bb8b  mov     [rbx+4Ch], eax
0x18004bb8e  call    cs:__imp_wcschr
0x18004bb95  nop     dword ptr [rax+rax+00h]
0x18004bb9a  test    rax, rax
0x18004bb9d  jz      short loc_18004BBB0
0x18004bb9f  sub     rax, r14
0x18004bba2  mov     r15, rax
0x18004bba5  mov     eax, dword ptr [rbp+arg_0]
0x18004bba8  sar     r15, 1
0x18004bbab  add     r15d, eax
0x18004bbae  jmp     short loc_18004BBB3
0x18004bbb0  mov     eax, dword ptr [rbp+arg_0]
0x18004bbb3  mov     [rbx+28h], eax
0x18004bbb6  mov     [rbx+2Ch], r15d
0x18004bbba  mov     r15, [rdi+20h]
0x18004bbbe  mov     r14d, [r15+1Ch]
0x18004bbc2  movsxd  r13, dword ptr [r15+0Ch]
0x18004bbc6  inc     r14d
0x18004bbc9  imul    r14d, r13d
0x18004bbcd  cmp     r14d, [r15+18h]
0x18004bbd1  jle     short loc_18004BC08
0x18004bbd3  mov     edx, r14d; int
0x18004bbd6  mov     rcx, r15; this
0x18004bbd9  call    ?FEnsureSize@GL@@AEAAHJ@Z; GL::FEnsureSize(long)
0x18004bbde  test    eax, eax
0x18004bbe0  jnz     short loc_18004BC08
0x18004bbe2  mov     rax, [rbx]
0x18004bbe5  mov     rcx, rbx
0x18004bbe8  mov     rax, [rax+0C0h]
0x18004bbef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bbf4  mov     rax, [rbx]
0x18004bbf7  mov     rcx, rbx
0x18004bbfa  mov     rax, [rax+10h]
0x18004bbfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc03  jmp     loc_18004BB46
0x18004bc08  mov     rax, [r15+10h]
0x18004bc0c  mov     edx, r13d
0x18004bc0f  imul    edx, esi
0x18004bc12  movsxd  rcx, edx
0x18004bc15  add     rax, rcx
0x18004bc18  mov     [rbp+arg_0], rax
0x18004bc1c  cmp     esi, [r15+1Ch]
0x18004bc20  jge     short loc_18004BC3B
0x18004bc22  sub     r14d, r13d
0x18004bc25  lea     rcx, [rax+r13]; void *
0x18004bc29  sub     r14d, edx
0x18004bc2c  mov     rdx, rax; Src
0x18004bc2f  movsxd  r8, r14d; Size
0x18004bc32  call    memmove_0
0x18004bc37  mov     rax, [rbp+arg_0]
0x18004bc3b  mov     r8, r13; Size
0x18004bc3e  lea     rdx, [rbp+Src]; Src
0x18004bc42  mov     rcx, rax; void *
0x18004bc45  call    memcpy_0
0x18004bc4a  inc     dword ptr [r15+1Ch]
0x18004bc4e  lea     rcx, [rbp+var_20]; this
0x18004bc52  mov     r15d, dword ptr [rbp+var_18+4]
0x18004bc56  mov     [rbx+1Ch], esi
0x18004bc59  call    ?PszReset@BuildString@@QEAAPEAGXZ; BuildString::PszReset(void)
0x18004bc5e  mov     r14, rax
0x18004bc61  test    rax, rax
0x18004bc64  jnz     short loc_18004BC76
0x18004bc66  mov     rcx, [rdi+20h]; this
0x18004bc6a  mov     edx, esi; int
0x18004bc6c  call    ?Delete@GL@@QEAAXJJ@Z; GL::Delete(long,long)
0x18004bc71  jmp     loc_18004BBE2
0x18004bc76  mov     rcx, [rdi+40h]; Block
0x18004bc7a  test    rcx, rcx
0x18004bc7d  jz      short loc_18004BC8B
0x18004bc7f  call    cs:__imp_free
0x18004bc86  nop     dword ptr [rax+rax+00h]
0x18004bc8b  mov     rcx, [rdi+20h]
0x18004bc8f  inc     esi
0x18004bc91  mov     [rdi+40h], r14
0x18004bc95  mov     [rdi+48h], r15d
0x18004bc99  cmp     esi, [rcx+1Ch]
0x18004bc9c  jnb     short loc_18004BCD8
0x18004bc9e  sub     r12d, [rbp+var_40]
0x18004bca2  movsxd  rax, dword ptr [rcx+0Ch]
0x18004bca6  mov     r8, rax; Size
0x18004bca9  imul    eax, esi
0x18004bcac  movsxd  rdx, eax
0x18004bcaf  add     rdx, [rcx+10h]; Src
0x18004bcb3  lea     rcx, [rbp+var_28]; void *
0x18004bcb7  call    memcpy_0
0x18004bcbc  mov     rcx, [rbp+var_28]; this
0x18004bcc0  lea     edx, [r12+1]; int
0x18004bcc5  mov     [rcx+1Ch], esi
0x18004bcc8  call    ?AdjustOffsets@AutEntry@@QEAAXJ@Z; AutEntry::AdjustOffsets(long)
0x18004bccd  mov     rcx, [rdi+20h]
0x18004bcd1  inc     esi
0x18004bcd3  cmp     esi, [rcx+1Ch]
0x18004bcd6  jb      short loc_18004BCA2
0x18004bcd8  mov     rax, [rbx]
0x18004bcdb  lea     rdx, IID_IScriptEntry
0x18004bce2  mov     r8, [rbp+arg_20]
0x18004bce6  mov     rcx, rbx
0x18004bce9  mov     rax, [rax]
0x18004bcec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bcf1  mov     ebx, eax
0x18004bcf3  lea     rcx, [rbp+var_20]; this
0x18004bcf7  call    ?Reset@BuildString@@QEAAXXZ; BuildString::Reset(void)
0x18004bcfc  mov     eax, ebx
0x18004bcfe  mov     rbx, [rsp+60h+arg_8]
0x18004bd06  add     rsp, 60h
0x18004bd0a  pop     r15
0x18004bd0c  pop     r14
0x18004bd0e  pop     r13
0x18004bd10  pop     r12
0x18004bd12  pop     rdi
0x18004bd13  pop     rsi
0x18004bd14  pop     rbp
0x18004bd15  retn
```
