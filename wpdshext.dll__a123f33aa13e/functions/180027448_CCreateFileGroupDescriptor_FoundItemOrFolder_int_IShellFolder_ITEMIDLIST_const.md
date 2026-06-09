# CCreateFileGroupDescriptor::_FoundItemOrFolder(int,IShellFolder *,_ITEMIDLIST const *)

- ea: `0x180027448`
- end: `0x1800278d7`
- name: `?_FoundItemOrFolder@CCreateFileGroupDescriptor@@AEAAJHPEAUIShellFolder@@PEFBU_ITEMIDLIST@@@Z`
- size: `1167`
- prototype: `__int64 __fastcall(CCreateFileGroupDescriptor *__hidden this, int, struct IShellFolder *, const struct _ITEMIDLIST *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800157cc`
- `0x180054b60`
- `0x180054d50`

## callees

- `0x18000e760`
- `0x180027448`
- `0x1800287d0`
- `0x18002a1d8`
- `0x18002ff5c`
- `0x180035590`
- `0x1800551c4`
- `0x180062518`
- `0x18006260c`
- `0x180078010`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x18002781a`
- `KERNEL32!GlobalFree` at `0x18002781a`
- `KERNEL32!GlobalReAlloc` at `0x18002756f`
- `KERNEL32!GlobalReAlloc` at `0x18002756f`
- `KERNEL32!GlobalAlloc` at `0x180027554`
- `KERNEL32!GlobalAlloc` at `0x180027554`
- `SHLWAPI!PathCombineW` at `0x1800276a0`
- `SHLWAPI!PathCombineW` at `0x1800276a0`
- `OLEAUT32!__imp_VariantInit` at `0x1800274a3`
- `OLEAUT32!__imp_VariantInit` at `0x1800274a3`
- `OLEAUT32!__imp_VariantClear` at `0x180027863`
- `OLEAUT32!__imp_VariantClear` at `0x180027863`
- `SHELL32!__imp_ILFree` at `0x1800277f7`
- `SHELL32!__imp_ILFree` at `0x1800277f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCreateFileGroupDescriptor::_FoundItemOrFolder(
        CCreateFileGroupDescriptor *this,
        int a2,
        struct IShellFolder *a3,
        const struct _ITEMIDLIST *a4)
{
  unsigned int v8; // ebx
  int StringProperty; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned int v13; // eax
  unsigned int v14; // r8d
  SIZE_T v15; // rdx
  void *v16; // rcx
  HGLOBAL v17; // rax
  HGLOBAL v18; // rax
  unsigned int Lo; // ebx
  __int64 v20; // r8
  int LongProperty; // eax
  unsigned __int64 v22; // r8
  __int64 v23; // rdx
  ITEMIDLIST *v24; // rsi
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  LPITEMIDLIST pidl; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszFile[264]; // [rsp+60h] [rbp-A0h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  v27 = 0;
  pidl = 0;
  v26 = 0;
  VariantInit(&pvarg);
  if ( !a3 || !a4 )
  {
    v8 = -2147024809;
    goto LABEL_49;
  }
  StringProperty = ((__int64 (__fastcall *)(struct IShellFolder *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
                     a3,
                     &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                     &v26);
  v8 = StringProperty;
  if ( StringProperty < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v11 = 14;
LABEL_8:
      v12 = (unsigned int)StringProperty;
LABEL_48:
      WPP_SF_d(v10[2], v11, WPP_a2fc94d5d3ba31bfd9034d4d366261d7_Traceguids, v12);
      goto LABEL_49;
    }
    goto LABEL_49;
  }
  v13 = *((_DWORD *)this + 4);
  v14 = v13 + 1;
  if ( v13 + 1 < v13 || 592 * v14 / 0x250uLL != v14 )
  {
    v8 = -2147418113;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_49;
    v11 = 15;
    goto LABEL_47;
  }
  v15 = 592 * v14 + 4;
  v16 = (void *)*((_QWORD *)this + 1);
  if ( v16 )
  {
    v18 = GlobalReAlloc(v16, v15, 0x42u);
    if ( v18 )
    {
      *((_QWORD *)this + 1) = v18;
      goto LABEL_16;
    }
    GlobalFree(*((HGLOBAL *)this + 1));
    *((_QWORD *)this + 1) = 0;
LABEL_43:
    v8 = -2147024882;
    goto LABEL_49;
  }
  v17 = GlobalAlloc(0x40u, v15);
  *((_QWORD *)this + 1) = v17;
  if ( !v17 )
    goto LABEL_43;
LABEL_16:
  StringProperty = GetStringProperty(v26, a4, &PKEY_WPDNSE_Name, pszFile, 260);
  v8 = StringProperty;
  if ( StringProperty >= 0 )
  {
    Lo = 0;
    if ( (*(int (__fastcall **)(__int64, const struct _ITEMIDLIST *, __int64 *, VARIANTARG *))(*(_QWORD *)v26 + 136LL))(
           v26,
           a4,
           &PKEY_WPDNSE_Attributes,
           &pvarg) >= 0
      && pvarg.vt == 19 )
    {
      Lo = pvarg.cyVal.Lo;
    }
    *(_DWORD *)(592LL * *((unsigned int *)this + 4) + *((_QWORD *)this + 1) + 4) = 16388;
    *(_DWORD *)(592LL * *((unsigned int *)this + 4) + *((_QWORD *)this + 1) + 40) = a2 != 0 ? 16 : 128;
    *(_DWORD *)(592LL * *((unsigned int *)this + 4) + *((_QWORD *)this + 1) + 40) |= (Lo >> 7) & 2;
    *(_DWORD *)(592LL * *((unsigned int *)this + 4) + *((_QWORD *)this + 1) + 40) |= (Lo >> 9) & 1;
    *(_DWORD *)(592LL * *((unsigned int *)this + 4) + *((_QWORD *)this + 1) + 40) |= (Lo >> 8) & 4;
    PathCombineW(
      (LPWSTR)(*((_QWORD *)this + 1) + 76LL + 592LL * *((unsigned int *)this + 4)),
      (LPCWSTR)this + 16,
      pszFile);
    LongProperty = GetLongProperty(v26, a4, v20, &v27);
    v22 = v27;
    if ( LongProperty >= 0 )
    {
      *(_DWORD *)(592LL * *((unsigned int *)this + 4) + *((_QWORD *)this + 1) + 72) = v27;
      *(_DWORD *)(592LL * *((unsigned int *)this + 4) + *((_QWORD *)this + 1) + 68) = HIDWORD(v22);
      *(_DWORD *)(592LL * *((unsigned int *)this + 4) + *((_QWORD *)this + 1) + 4) |= 0x40u;
    }
    if ( *((_DWORD *)this + 5) == 1 && v22 <= 0x2DC6C0 )
      *(_DWORD *)(592LL * *((unsigned int *)this + 4) + *((_QWORD *)this + 1) + 4) &= ~0x4000u;
    GetDateProperty(v26, a4, v22, 592LL * *((unsigned int *)this + 4) + *((_QWORD *)this + 1) + 60LL);
    *(_DWORD *)(592LL * (unsigned int)(*((_DWORD *)this + 4))++ + *((_QWORD *)this + 1) + 4) |= 0x20u;
    **((_DWORD **)this + 1) = *((_DWORD *)this + 4);
    StringProperty = CCreateFileGroupDescriptor::_EnsureDPA(this);
    v8 = StringProperty;
    if ( StringProperty < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v11 = 17;
        goto LABEL_8;
      }
      goto LABEL_49;
    }
    StringProperty = SHILCombine(*((const ITEMIDLIST **)this + 69), a4, &pidl);
    v8 = StringProperty;
    if ( StringProperty < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v11 = 18;
        goto LABEL_8;
      }
      goto LABEL_49;
    }
    v24 = pidl;
    if ( (unsigned int)IsolationAwareDPA_InsertPtr(*((_QWORD *)this + 3), v23, pidl) != -1 )
      goto LABEL_49;
    v8 = -2147024882;
    if ( v24 )
      ILFree(v24);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_49;
    v11 = 19;
LABEL_47:
    v12 = v8;
    goto LABEL_48;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v11 = 16;
    goto LABEL_8;
  }
LABEL_49:
  VariantClear(&pvarg);
  if ( (v8 & 0x80000000) != 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_a2fc94d5d3ba31bfd9034d4d366261d7_Traceguids, v8);
  }
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return v8;
}

```

## disassembly

```asm
0x180027448  mov     [rsp-8+arg_8], rbx
0x18002744d  push    rbp
0x18002744e  push    rsi
0x18002744f  push    rdi
0x180027450  push    r13
0x180027452  push    r14
0x180027454  lea     rbp, [rsp-180h]
0x18002745c  sub     rsp, 280h
0x180027463  mov     rax, cs:__security_cookie
0x18002746a  xor     rax, rsp
0x18002746d  mov     [rbp+1A0h+var_30], rax
0x180027474  mov     rsi, r9
0x180027477  mov     rbx, r8
0x18002747a  mov     r14d, edx
0x18002747d  mov     rdi, rcx
0x180027480  xorps   xmm0, xmm0
0x180027483  xor     eax, eax
0x180027485  movups  xmmword ptr [rsp+2A0h+pvarg], xmm0
0x18002748a  mov     qword ptr [rsp+2A0h+pvarg+10h], rax
0x18002748f  mov     [rsp+2A0h+var_268], rax
0x180027494  mov     [rsp+2A0h+pidl], rax
0x180027499  mov     [rsp+2A0h+var_270], rax
0x18002749e  lea     rcx, [rsp+2A0h+pvarg]; pvarg
0x1800274a3  call    cs:__imp_VariantInit
0x1800274a9  lea     r13, WPP_GLOBAL_Control
0x1800274b0  test    rbx, rbx
0x1800274b3  jnz     short loc_1800274BF
0x1800274b5  mov     ebx, 80070057h
0x1800274ba  jmp     loc_18002785E
0x1800274bf  test    rsi, rsi
0x1800274c2  jz      short loc_1800274B5
0x1800274c4  mov     rax, [rbx]
0x1800274c7  lea     r8, [rsp+2A0h+var_270]
0x1800274cc  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x1800274d3  mov     rcx, rbx
0x1800274d6  mov     rax, [rax]
0x1800274d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274de  mov     ebx, eax
0x1800274e0  test    eax, eax
0x1800274e2  jns     short loc_18002750B
0x1800274e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800274eb  cmp     rcx, r13
0x1800274ee  jz      loc_18002785E
0x1800274f4  test    byte ptr [rcx+1Ch], 2
0x1800274f8  jz      loc_18002785E
0x1800274fe  mov     edx, 0Eh
0x180027503  mov     r9d, eax
0x180027506  jmp     loc_18002784E
0x18002750b  mov     eax, [rdi+10h]
0x18002750e  lea     r8d, [rax+1]
0x180027512  cmp     r8d, eax
0x180027515  jbe     loc_18002782F
0x18002751b  imul    r9d, r8d, 250h
0x180027522  mov     ecx, r9d
0x180027525  mov     rax, 0DD67C8A60DD67C8Bh
0x18002752f  mul     rcx
0x180027532  shr     rdx, 9
0x180027536  mov     eax, r8d
0x180027539  cmp     rdx, rax
0x18002753c  jnz     loc_18002782F
0x180027542  lea     edx, [r9+4]; dwBytes
0x180027546  mov     rcx, [rdi+8]; hMem
0x18002754a  test    rcx, rcx
0x18002754d  jnz     short loc_180027569
0x18002754f  mov     ecx, 40h ; '@'; uFlags
0x180027554  call    cs:__imp_GlobalAlloc
0x18002755a  mov     [rdi+8], rax
0x18002755e  test    rax, rax
0x180027561  jz      loc_180027828
0x180027567  jmp     short loc_180027582
0x180027569  mov     r8d, 42h ; 'B'; uFlags
0x18002756f  call    cs:__imp_GlobalReAlloc
0x180027575  test    rax, rax
0x180027578  jz      loc_180027816
0x18002757e  mov     [rdi+8], rax
0x180027582  mov     [rsp+2A0h+var_280], 104h
0x18002758a  lea     r9, [rsp+2A0h+pszFile]
0x18002758f  lea     r8, PKEY_WPDNSE_Name
0x180027596  mov     rdx, rsi
0x180027599  mov     rcx, [rsp+2A0h+var_270]
0x18002759e  call    GetStringProperty
0x1800275a3  mov     ebx, eax
0x1800275a5  test    eax, eax
0x1800275a7  jns     short loc_1800275CD
0x1800275a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275b0  cmp     rcx, r13
0x1800275b3  jz      loc_18002785E
0x1800275b9  test    byte ptr [rcx+1Ch], 2
0x1800275bd  jz      loc_18002785E
0x1800275c3  mov     edx, 10h
0x1800275c8  jmp     loc_180027503
0x1800275cd  xor     ebx, ebx
0x1800275cf  mov     rcx, [rsp+2A0h+var_270]
0x1800275d4  mov     rax, [rcx]
0x1800275d7  lea     r9, [rsp+2A0h+pvarg]
0x1800275dc  lea     r8, PKEY_WPDNSE_Attributes
0x1800275e3  mov     rdx, rsi
0x1800275e6  mov     rax, [rax+88h]
0x1800275ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275f2  lea     ecx, [rbx+13h]
0x1800275f5  test    eax, eax
0x1800275f7  js      short loc_180027603
0x1800275f9  cmp     word ptr [rsp+2A0h+pvarg], cx
0x1800275fe  cmovz   ebx, dword ptr [rsp+2A0h+pvarg+8]
0x180027603  mov     eax, [rdi+10h]
0x180027606  imul    rcx, rax, 250h
0x18002760d  mov     rax, [rdi+8]
0x180027611  mov     dword ptr [rcx+rax+4], 4004h
0x180027619  neg     r14d
0x18002761c  sbb     edx, edx
0x18002761e  and     edx, 0FFFFFF90h
0x180027621  sub     edx, 0FFFFFF80h
0x180027624  mov     eax, [rdi+10h]
0x180027627  imul    rcx, rax, 250h
0x18002762e  mov     rax, [rdi+8]
0x180027632  mov     [rcx+rax+28h], edx
0x180027636  mov     eax, [rdi+10h]
0x180027639  imul    rdx, rax, 250h
0x180027640  mov     rcx, [rdi+8]
0x180027644  mov     eax, ebx
0x180027646  shr     eax, 7
0x180027649  and     eax, 2
0x18002764c  or      [rdx+rcx+28h], eax
0x180027650  mov     eax, [rdi+10h]
0x180027653  imul    rdx, rax, 250h
0x18002765a  mov     rcx, [rdi+8]
0x18002765e  mov     eax, ebx
0x180027660  shr     eax, 9
0x180027663  and     eax, 1
0x180027666  or      [rdx+rcx+28h], eax
0x18002766a  mov     eax, [rdi+10h]
0x18002766d  imul    rcx, rax, 250h
0x180027674  mov     rax, [rdi+8]
0x180027678  shr     ebx, 8
0x18002767b  and     ebx, 4
0x18002767e  or      [rcx+rax+28h], ebx
0x180027682  lea     rdx, [rdi+20h]; pszDir
0x180027686  mov     eax, [rdi+10h]
0x180027689  imul    rcx, rax, 250h
0x180027690  mov     rax, [rdi+8]
0x180027694  add     rax, 4Ch ; 'L'
0x180027698  add     rcx, rax; pszDest
0x18002769b  lea     r8, [rsp+2A0h+pszFile]; pszFile
0x1800276a0  call    cs:__imp_PathCombineW
0x1800276a6  lea     r9, [rsp+2A0h+var_268]
0x1800276ab  mov     rdx, rsi
0x1800276ae  mov     rcx, [rsp+2A0h+var_270]
0x1800276b3  call    GetLongProperty
0x1800276b8  mov     r8, [rsp+2A0h+var_268]
0x1800276bd  test    eax, eax
0x1800276bf  js      short loc_180027700
0x1800276c1  mov     eax, [rdi+10h]
0x1800276c4  imul    rcx, rax, 250h
0x1800276cb  mov     rax, [rdi+8]
0x1800276cf  mov     [rcx+rax+48h], r8d
0x1800276d4  mov     rdx, r8
0x1800276d7  shr     rdx, 20h
0x1800276db  mov     eax, [rdi+10h]
0x1800276de  imul    rcx, rax, 250h
0x1800276e5  mov     rax, [rdi+8]
0x1800276e9  mov     [rcx+rax+44h], edx
0x1800276ed  mov     eax, [rdi+10h]
0x1800276f0  imul    rcx, rax, 250h
0x1800276f7  mov     rax, [rdi+8]
0x1800276fb  or      dword ptr [rcx+rax+4], 40h
0x180027700  cmp     dword ptr [rdi+14h], 1
0x180027704  jnz     short loc_180027723
0x180027706  cmp     r8, 2DC6C0h
0x18002770d  ja      short loc_180027723
0x18002770f  mov     eax, [rdi+10h]
0x180027712  imul    rcx, rax, 250h
0x180027719  mov     rax, [rdi+8]
0x18002771d  btr     dword ptr [rcx+rax+4], 0Eh
0x180027723  mov     eax, [rdi+10h]
0x180027726  imul    rcx, rax, 250h
0x18002772d  mov     r9, [rdi+8]
0x180027731  add     r9, 3Ch ; '<'
0x180027735  add     r9, rcx
0x180027738  mov     rdx, rsi
0x18002773b  mov     rcx, [rsp+2A0h+var_270]
0x180027740  call    GetDateProperty
0x180027745  mov     eax, [rdi+10h]
0x180027748  imul    rcx, rax, 250h
0x18002774f  mov     rax, [rdi+8]
0x180027753  or      dword ptr [rcx+rax+4], 20h
0x180027758  inc     dword ptr [rdi+10h]
0x18002775b  mov     ecx, [rdi+10h]
0x18002775e  mov     rax, [rdi+8]
0x180027762  mov     [rax], ecx
0x180027764  mov     rcx, rdi; this
0x180027767  call    ?_EnsureDPA@CCreateFileGroupDescriptor@@AEAAJXZ; CCreateFileGroupDescriptor::_EnsureDPA(void)
0x18002776c  mov     ebx, eax
0x18002776e  test    eax, eax
0x180027770  jns     short loc_180027796
0x180027772  mov     rcx, cs:WPP_GLOBAL_Control
0x180027779  cmp     rcx, r13
0x18002777c  jz      loc_18002785E
0x180027782  test    byte ptr [rcx+1Ch], 2
0x180027786  jz      loc_18002785E
0x18002778c  mov     edx, 11h
0x180027791  jmp     loc_180027503
0x180027796  lea     r8, [rsp+2A0h+pidl]
0x18002779b  mov     rdx, rsi
0x18002779e  mov     rcx, [rdi+228h]
0x1800277a5  call    SHILCombine
0x1800277aa  mov     ebx, eax
0x1800277ac  test    eax, eax
0x1800277ae  jns     short loc_1800277D4
0x1800277b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800277b7  cmp     rcx, r13
0x1800277ba  jz      loc_18002785E
0x1800277c0  test    byte ptr [rcx+1Ch], 2
0x1800277c4  jz      loc_18002785E
0x1800277ca  mov     edx, 12h
0x1800277cf  jmp     loc_180027503
0x1800277d4  mov     rsi, [rsp+2A0h+pidl]
0x1800277d9  mov     r8, rsi
0x1800277dc  mov     rcx, [rdi+18h]
0x1800277e0  call    IsolationAwareDPA_InsertPtr
0x1800277e5  cmp     eax, 0FFFFFFFFh
0x1800277e8  jnz     short loc_18002785E
0x1800277ea  mov     ebx, 8007000Eh
0x1800277ef  test    rsi, rsi
0x1800277f2  jz      short loc_1800277FD
0x1800277f4  mov     rcx, rsi; pidl
0x1800277f7  call    cs:__imp_ILFree
0x1800277fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180027804  cmp     rcx, r13
0x180027807  jz      short loc_18002785E
0x180027809  test    byte ptr [rcx+1Ch], 2
0x18002780d  jz      short loc_18002785E
0x18002780f  mov     edx, 13h
0x180027814  jmp     short loc_18002784B
0x180027816  mov     rcx, [rdi+8]; hMem
0x18002781a  call    cs:__imp_GlobalFree
0x180027820  mov     qword ptr [rdi+8], 0
0x180027828  mov     ebx, 8007000Eh
0x18002782d  jmp     short loc_18002785E
0x18002782f  mov     ebx, 8000FFFFh
0x180027834  mov     rcx, cs:WPP_GLOBAL_Control
0x18002783b  cmp     rcx, r13
0x18002783e  jz      short loc_18002785E
0x180027840  test    byte ptr [rcx+1Ch], 2
0x180027844  jz      short loc_18002785E
0x180027846  mov     edx, 0Fh
0x18002784b  mov     r9d, ebx
0x18002784e  lea     r8, WPP_a2fc94d5d3ba31bfd9034d4d366261d7_Traceguids
0x180027855  mov     rcx, [rcx+10h]
0x180027859  call    WPP_SF_d
0x18002785e  lea     rcx, [rsp+2A0h+pvarg]; pvarg
0x180027863  call    cs:__imp_VariantClear
0x180027869  test    ebx, ebx
0x18002786b  jns     short loc_180027898
0x18002786d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027874  cmp     rcx, r13
0x180027877  jz      short loc_180027898
0x180027879  test    byte ptr [rcx+1Ch], 2
0x18002787d  jz      short loc_180027898
0x18002787f  mov     edx, 14h
0x180027884  mov     r9d, ebx
0x180027887  lea     r8, WPP_a2fc94d5d3ba31bfd9034d4d366261d7_Traceguids
0x18002788e  mov     rcx, [rcx+10h]
0x180027892  call    WPP_SF_d
0x180027897  nop
0x180027898  mov     rcx, [rsp+2A0h+var_270]
0x18002789d  test    rcx, rcx
0x1800278a0  jz      short loc_1800278AF
0x1800278a2  mov     rax, [rcx]
0x1800278a5  mov     rax, [rax+10h]
0x1800278a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278ae  nop
0x1800278af  mov     eax, ebx
0x1800278b1  mov     rcx, [rbp+1A0h+var_30]
0x1800278b8  xor     rcx, rsp; StackCookie
0x1800278bb  call    __security_check_cookie
0x1800278c0  mov     rbx, [rsp+2A0h+arg_8]
0x1800278c8  add     rsp, 280h
0x1800278cf  pop     r14
0x1800278d1  pop     r13
0x1800278d3  pop     rdi
0x1800278d4  pop     rsi
0x1800278d5  pop     rbp
0x1800278d6  retn
```
