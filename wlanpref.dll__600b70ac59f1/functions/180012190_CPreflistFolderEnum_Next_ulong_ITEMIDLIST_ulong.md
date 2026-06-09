# CPreflistFolderEnum::Next(ulong,_ITEMIDLIST * *,ulong *)

- ea: `0x180012190`
- end: `0x1800122ba`
- name: `?Next@CPreflistFolderEnum@@UEAAJKPEAPEFAU_ITEMIDLIST@@PEAK@Z`
- size: `298`
- prototype: `__int64 __fastcall(CPreflistFolderEnum *__hidden this, unsigned int, struct _ITEMIDLIST **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800054a0`
- `0x180011124`
- `0x18001215c`
- `0x180012190`
- `0x1800283a0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012230`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012230`

## pseudocode

```c
__int64 __fastcall CPreflistFolderEnum::Next(
        CPreflistFolderEnum *this,
        unsigned int a2,
        struct _ITEMIDLIST **a3,
        unsigned int *a4)
{
  unsigned __int64 v7; // r12
  unsigned __int64 v8; // rax
  unsigned int v9; // ebp
  __int64 v10; // rbx
  __int64 Index; // r14
  char *v12; // rax
  struct _ITEMIDLIST *v13; // rsi
  __int128 v15; // [rsp+20h] [rbp-78h] BYREF
  unsigned __int64 v16; // [rsp+30h] [rbp-68h]
  __int128 v17; // [rsp+38h] [rbp-60h]
  int v18; // [rsp+48h] [rbp-50h]

  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 10;
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 8LL))(
    CSingletonPtr<CWlanProfileStore>::s_pInstance,
    &v15);
  v7 = v16;
  v8 = *((unsigned int *)this + 25);
  v9 = 1;
  if ( v8 >= v16 )
  {
    if ( a4 )
      *a4 = 0;
LABEL_15:
    ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAll(&v15);
    return v9;
  }
  v10 = 0;
  while ( (unsigned int)v10 < a2 && (unsigned int)v8 < v7 )
  {
    Index = ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::FindIndex(&v15);
    if ( !Index )
      ATL::AtlThrowImpl(-2147467259);
    v12 = (char *)CoTaskMemAlloc(0x838u);
    v13 = (struct _ITEMIDLIST *)v12;
    if ( !v12 )
    {
      v9 = -2147024882;
      goto LABEL_15;
    }
    *(_WORD *)v12 = 2102;
    ProfileToStruct((const struct CProfile *)(Index + 16), (struct WPLDATA *)(v12 + 2));
    *(_WORD *)v13[700].mkid.abID = 0;
    a3[v10] = v13;
    v10 = (unsigned int)(v10 + 1);
    LODWORD(v8) = ++*((_DWORD *)this + 25);
  }
  if ( a4 )
    *a4 = v10;
  if ( (unsigned int)v10 < a2 )
    goto LABEL_15;
  ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAll(&v15);
  return 0;
}

```

## disassembly

```asm
0x180012190  mov     rax, rsp
0x180012193  mov     [rax+18h], r8
0x180012197  push    rbx
0x180012198  push    rbp
0x180012199  push    rsi
0x18001219a  push    rdi
0x18001219b  push    r12
0x18001219d  push    r13
0x18001219f  push    r14
0x1800121a1  push    r15
0x1800121a3  sub     rsp, 58h
0x1800121a7  mov     rdi, r9
0x1800121aa  mov     r15d, edx
0x1800121ad  mov     r13, rcx
0x1800121b0  xorps   xmm0, xmm0
0x1800121b3  movdqu  xmmword ptr [rax-78h], xmm0
0x1800121b8  mov     qword ptr [rax-68h], 0
0x1800121c0  movdqu  xmmword ptr [rax-60h], xmm0
0x1800121c5  mov     dword ptr [rax-50h], 0Ah
0x1800121cc  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x1800121d3  mov     rax, [rcx]
0x1800121d6  lea     rdx, [rsp+98h+var_78]
0x1800121db  mov     rax, [rax+8]
0x1800121df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121e4  mov     r12, [rsp+98h+var_68]
0x1800121e9  mov     eax, [r13+64h]
0x1800121ed  mov     ebp, 1
0x1800121f2  cmp     rax, r12
0x1800121f5  jb      short loc_18001220B
0x1800121f7  test    rdi, rdi
0x1800121fa  jz      loc_18001228F
0x180012200  mov     dword ptr [rdi], 0
0x180012206  jmp     loc_18001228F
0x18001220b  xor     ebx, ebx
0x18001220d  cmp     ebx, r15d
0x180012210  jnb     short loc_180012283
0x180012212  mov     edx, eax
0x180012214  cmp     rdx, r12
0x180012217  jnb     short loc_180012283
0x180012219  lea     rcx, [rsp+98h+var_78]
0x18001221e  call    ?FindIndex@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEBAPEAU__POSITION@@_K@Z; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::FindIndex(unsigned __int64)
0x180012223  mov     r14, rax
0x180012226  test    rax, rax
0x180012229  jz      short loc_180012278
0x18001222b  mov     ecx, 838h; cb
0x180012230  call    cs:__imp_CoTaskMemAlloc
0x180012236  mov     rsi, rax
0x180012239  test    rax, rax
0x18001223c  jz      short loc_180012271
0x18001223e  mov     word ptr [rax], 836h
0x180012243  lea     rdx, [rax+2]; struct WPLDATA *
0x180012247  lea     rcx, [r14+10h]; struct CProfile *
0x18001224b  call    ?ProfileToStruct@@YAXAEBVCProfile@@AEAUWPLDATA@@@Z; ProfileToStruct(CProfile const &,WPLDATA &)
0x180012250  xor     ecx, ecx
0x180012252  mov     [rsi+836h], cx
0x180012259  mov     rax, [rsp+98h+arg_10]
0x180012261  mov     [rax+rbx*8], rsi
0x180012265  add     ebx, ebp
0x180012267  add     [r13+64h], ebp
0x18001226b  mov     eax, [r13+64h]
0x18001226f  jmp     short loc_18001220D
0x180012271  mov     ebp, 8007000Eh
0x180012276  jmp     short loc_18001228F
0x180012278  mov     ecx, 80004005h; int
0x18001227d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180012283  test    rdi, rdi
0x180012286  jz      short loc_18001228A
0x180012288  mov     [rdi], ebx
0x18001228a  cmp     ebx, r15d
0x18001228d  jnb     short loc_18001229D
0x18001228f  lea     rcx, [rsp+98h+var_78]
0x180012294  call    ?RemoveAll@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAll(void)
0x180012299  mov     eax, ebp
0x18001229b  jmp     short loc_1800122A9
0x18001229d  lea     rcx, [rsp+98h+var_78]
0x1800122a2  call    ?RemoveAll@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAll(void)
0x1800122a7  xor     eax, eax
0x1800122a9  add     rsp, 58h
0x1800122ad  pop     r15
0x1800122af  pop     r14
0x1800122b1  pop     r13
0x1800122b3  pop     r12
0x1800122b5  pop     rdi
0x1800122b6  pop     rsi
0x1800122b7  pop     rbp
0x1800122b8  pop     rbx
0x1800122b9  retn
```
