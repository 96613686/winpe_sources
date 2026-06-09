# InitExtractor(ICreateObject *,WTS_FLAGS,WTS_PRIV_FLAGS,IShellItem *,uint,uint,uint *,int *,IUnknown * *)

- ea: `0x180004614`
- end: `0x1800049ce`
- name: `?InitExtractor@@YAJPEAUICreateObject@@W4WTS_FLAGS@@W4WTS_PRIV_FLAGS@@PEAUIShellItem@@IIPEAIPEAHPEAPEAUIUnknown@@@Z`
- size: `954`
- prototype: `int __high(struct ICreateObject *, enum WTS_FLAGS, enum WTS_PRIV_FLAGS, struct IShellItem *, unsigned int, unsigned int, unsigned int *, int *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011c10`

## callees

- `0x180003624`
- `0x180004614`
- `0x1800049d4`
- `0x180004ad0`
- `0x180004c84`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1800048fd`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1800048fd`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180004695`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180004695`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall InitExtractor(
        __int64 a1,
        enum WTS_FLAGS a2,
        char a3,
        struct IUnknown *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int *a7,
        int *a8,
        struct IExtractImage *a9)
{
  int v12; // r13d
  bool v13; // si
  unsigned int v14; // edi
  const struct _GUID *v15; // rdx
  int Image; // ebx
  enum WTS_FLAGS v18; // r14d
  IUnknown **v19; // r15
  int v20; // r9d
  enum WTS_FLAGS v21; // [rsp+50h] [rbp-30h] BYREF
  struct IExtractImage *v22; // [rsp+58h] [rbp-28h] BYREF
  LPBC ppbc; // [rsp+60h] [rbp-20h] BYREF
  IUnknown *punkSite; // [rsp+68h] [rbp-18h] BYREF
  int v25; // [rsp+70h] [rbp-10h]
  int v26; // [rsp+74h] [rbp-Ch]

  v21 = a2;
  v22 = a9;
  *a7 = 0;
  a9->lpVtbl = 0;
  v12 = a2 & 0x800;
  v13 = v12 != 0;
  ppbc = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppbc);
  CreateBindCtx(0, &ppbc);
  v14 = -2147024882;
  if ( !a1 )
  {
    v18 = v21;
    goto LABEL_17;
  }
  punkSite = (IUnknown *)16;
  v25 = 0;
  v26 = -1;
  Image = ((__int64 (__fastcall *)(LPBC, IUnknown **))ppbc->lpVtbl->SetBindOptions)(ppbc, &punkSite);
  if ( Image >= 0 )
  {
    if ( !ppbc )
      goto LABEL_9;
    Image = ((__int64 (__fastcall *)(LPBC, const wchar_t *, __int64))ppbc->lpVtbl->RegisterObjectParam)(
              ppbc,
              L"Delegate Object Creation",
              a1);
    if ( Image >= 0 )
    {
      if ( (a3 & 1) == 0
        || (ppbc
          ? (Image = ((__int64 (__fastcall *)(LPBC, const wchar_t *, __int64))ppbc->lpVtbl->RegisterObjectParam)(
                       ppbc,
                       L"Request Default Thumbnail Provider",
                       a1))
          : (Image = -2147024882),
            Image >= 0) )
      {
        LOBYTE(v15) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudFileStabilization>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_CloudFileStabilization>::GetImpl'::`2'::impl,
          v15);
        v18 = v21;
        if ( (v21 & 0x8000000) == 0
          || (ppbc
            ? (Image = ((__int64 (__fastcall *)(LPBC, const wchar_t *, __int64))ppbc->lpVtbl->RegisterObjectParam)(
                         ppbc,
                         L"Request Local Thumbnail Provider",
                         a1))
            : (Image = -2147024882),
              Image >= 0) )
        {
LABEL_17:
          if ( v12 )
          {
            v21 = WTS_NONE;
            v13 = ((int (__fastcall *)(struct IUnknown *, __int64, enum WTS_FLAGS *))a4->lpVtbl[2].QueryInterface)(
                    a4,
                    536936448,
                    &v21) < 0
               || v21 == WTS_NONE;
          }
          punkSite = 0;
          Image = ((__int64 (__fastcall *)(struct IUnknown *, LPBC, const GUID *, GUID *, IUnknown **))a4->lpVtbl[1].QueryInterface)(
                    a4,
                    ppbc,
                    &BHID_ThumbnailHandler,
                    &GUID_e357fccd_a995_4576_b01f_234630154e96,
                    &punkSite);
          v19 = (IUnknown **)v22;
          if ( Image >= 0 )
          {
            Image = ((__int64 (__fastcall *)(IUnknown *, GUID *, struct IExtractImage *))punkSite->lpVtbl->QueryInterface)(
                      punkSite,
                      &GUID_00000000_0000_0000_c000_000000000046,
                      v22);
            if ( Image >= 0 )
            {
              *a7 = a5;
LABEL_21:
              v14 = -2147175936;
LABEL_22:
              if ( punkSite )
                ((void (__fastcall *)(IUnknown *))punkSite->lpVtbl->Release)(punkSite);
              goto LABEL_24;
            }
          }
          if ( Image != -2147467263 && Image != -2147467262 )
            goto LABEL_21;
          if ( v13 )
          {
            Image = -2147175934;
            goto LABEL_21;
          }
          v22 = 0;
          Image = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, const GUID *, GUID *, struct IExtractImage **))a4->lpVtbl[1].QueryInterface)(
                    a4,
                    0,
                    &BHID_ThumbnailHandler,
                    &GUID_bb2e617c_0920_11d1_9a0b_00c04fc2d6c1,
                    &v22);
          if ( Image >= 0 )
          {
            Image = InitExtractImage(v22, a5, a6, v20, a7, a8, v18);
            if ( Image < 0 )
            {
              if ( Image != -2147024882 )
              {
                v14 = -2147175936;
                if ( Image != -2144927486 )
                  Image = -2147175936;
                goto LABEL_31;
              }
            }
            else
            {
              Image = ((__int64 (__fastcall *)(struct IExtractImage *, GUID *, IUnknown **))v22->lpVtbl->QueryInterface)(
                        v22,
                        &GUID_00000000_0000_0000_c000_000000000046,
                        v19);
            }
          }
          v14 = -2147175936;
LABEL_31:
          if ( v22 )
            ((void (__fastcall *)(struct IExtractImage *))v22->lpVtbl->Release)(v22);
          goto LABEL_22;
        }
      }
    }
  }
  v14 = -2147175936;
  v19 = (IUnknown **)v22;
LABEL_24:
  if ( (unsigned int)(Image + 2147467263) > 1 )
  {
    v14 = Image;
    if ( Image >= 0 )
    {
      punkSite = 0;
      if ( (int)GetCachedItemFromShellItem(a4, v15, (void **)&punkSite) >= 0 )
      {
        IUnknown_SetSite(*v19, punkSite);
        ((void (__fastcall *)(IUnknown *))punkSite->lpVtbl->Release)(punkSite);
      }
    }
  }
LABEL_9:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppbc);
  return v14;
}

```

## disassembly

```asm
0x180004614  mov     [rsp-38h+arg_8], rbx
0x180004619  push    rbp
0x18000461a  push    rsi
0x18000461b  push    rdi
0x18000461c  push    r12
0x18000461e  push    r13
0x180004620  push    r14
0x180004622  push    r15
0x180004624  mov     rbp, rsp
0x180004627  sub     rsp, 80h
0x18000462e  mov     rax, cs:__security_cookie
0x180004635  xor     rax, rsp
0x180004638  mov     [rbp+var_8], rax
0x18000463c  mov     r12, r9
0x18000463f  mov     r14d, r8d
0x180004642  mov     [rbp+var_30], edx
0x180004645  mov     r15, rcx
0x180004648  mov     rax, [rbp+arg_30]
0x18000464c  mov     [rbp+var_40], rax
0x180004650  mov     rcx, [rbp+arg_38]
0x180004654  mov     [rbp+var_38], rcx
0x180004658  mov     rcx, [rbp+arg_40]
0x18000465f  mov     [rbp+var_28], rcx
0x180004663  mov     dword ptr [rax], 0
0x180004669  mov     qword ptr [rcx], 0
0x180004670  mov     r13d, edx
0x180004673  and     r13d, 800h
0x18000467a  setnz   sil
0x18000467e  mov     [rbp+ppbc], 0
0x180004686  lea     rcx, [rbp+ppbc]
0x18000468a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000468f  lea     rdx, [rbp+ppbc]; ppbc
0x180004693  xor     ecx, ecx; reserved
0x180004695  call    cs:__imp_CreateBindCtx
0x18000469b  nop
0x18000469c  mov     edi, 8007000Eh
0x1800046a1  test    r15, r15
0x1800046a4  jz      loc_180004997
0x1800046aa  mov     [rbp+punkSite], 10h
0x1800046b2  mov     [rbp+var_10], 0
0x1800046b9  mov     [rbp+var_C], 0FFFFFFFFh
0x1800046c0  mov     rcx, [rbp+ppbc]
0x1800046c4  mov     rax, [rcx]
0x1800046c7  lea     rdx, [rbp+punkSite]
0x1800046cb  mov     rax, [rax+30h]
0x1800046cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046d4  mov     ebx, eax
0x1800046d6  test    eax, eax
0x1800046d8  js      loc_180004859
0x1800046de  mov     rcx, [rbp+ppbc]
0x1800046e2  test    rcx, rcx
0x1800046e5  jz      short loc_180004724
0x1800046e7  mov     rax, [rcx]
0x1800046ea  mov     r8, r15
0x1800046ed  lea     rdx, aDelegateObject; "Delegate Object Creation"
0x1800046f4  mov     rax, [rax+48h]
0x1800046f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046fd  mov     ebx, eax
0x1800046ff  test    eax, eax
0x180004701  js      loc_180004859
0x180004707  test    r14b, 1
0x18000470b  jz      short loc_180004776
0x18000470d  mov     rcx, [rbp+ppbc]
0x180004711  test    rcx, rcx
0x180004714  jnz     short loc_180004756
0x180004716  mov     ebx, edi
0x180004718  jmp     short loc_18000476E
0x18000471a  mov     edi, ebx
0x18000471c  test    ebx, ebx
0x18000471e  jns     loc_1800048DA
0x180004724  lea     rcx, [rbp+ppbc]
0x180004728  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000472d  mov     eax, edi
0x18000472f  mov     rcx, [rbp+var_8]
0x180004733  xor     rcx, rsp; StackCookie
0x180004736  call    __security_check_cookie
0x18000473b  mov     rbx, [rsp+80h+arg_8]
0x180004743  add     rsp, 80h
0x18000474a  pop     r15
0x18000474c  pop     r14
0x18000474e  pop     r13
0x180004750  pop     r12
0x180004752  pop     rdi
0x180004753  pop     rsi
0x180004754  pop     rbp
0x180004755  retn
0x180004756  mov     rax, [rcx]
0x180004759  mov     r8, r15
0x18000475c  lea     rdx, aRequestDefault; "Request Default Thumbnail Provider"
0x180004763  mov     rax, [rax+48h]
0x180004767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000476c  mov     ebx, eax
0x18000476e  test    ebx, ebx
0x180004770  js      loc_180004859
0x180004776  mov     dl, 1
0x180004778  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudFileStabilization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudFileStabilization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudFileStabilization> `wil::Feature<__WilFeatureTraits_Feature_CloudFileStabilization>::GetImpl(void)'::`2'::impl
0x18000477f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudFileStabilization@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudFileStabilization>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180004784  mov     r14d, [rbp+var_30]
0x180004788  bt      r14d, 1Bh
0x18000478d  jnb     short loc_1800047BC
0x18000478f  mov     rcx, [rbp+ppbc]
0x180004793  test    rcx, rcx
0x180004796  jnz     short loc_18000479C
0x180004798  mov     ebx, edi
0x18000479a  jmp     short loc_1800047B4
0x18000479c  mov     rax, [rcx]
0x18000479f  mov     r8, r15
0x1800047a2  lea     rdx, aRequestLocalTh; "Request Local Thumbnail Provider"
0x1800047a9  mov     rax, [rax+48h]
0x1800047ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047b2  mov     ebx, eax
0x1800047b4  test    ebx, ebx
0x1800047b6  js      loc_180004859
0x1800047bc  test    r13d, r13d
0x1800047bf  jnz     loc_180004965
0x1800047c5  mov     [rbp+punkSite], 0
0x1800047cd  mov     rax, [r12]
0x1800047d1  lea     rcx, [rbp+punkSite]
0x1800047d5  mov     [rsp+80h+var_60], rcx
0x1800047da  lea     r9, _GUID_e357fccd_a995_4576_b01f_234630154e96
0x1800047e1  lea     r8, BHID_ThumbnailHandler
0x1800047e8  mov     rdx, [rbp+ppbc]
0x1800047ec  mov     rcx, r12
0x1800047ef  mov     rax, [rax+18h]
0x1800047f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047f8  mov     ebx, eax
0x1800047fa  mov     r15, [rbp+var_28]
0x1800047fe  test    eax, eax
0x180004800  js      short loc_180004864
0x180004802  mov     rcx, [rbp+punkSite]
0x180004806  mov     rax, [rcx]
0x180004809  mov     r8, r15
0x18000480c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180004813  mov     rax, [rax]
0x180004816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000481b  mov     ebx, eax
0x18000481d  test    eax, eax
0x18000481f  js      short loc_180004864
0x180004821  mov     eax, [rbp+arg_20]
0x180004824  mov     rcx, [rbp+var_40]
0x180004828  mov     [rcx], eax
0x18000482a  mov     edi, 8004B200h
0x18000482f  mov     rcx, [rbp+punkSite]
0x180004833  test    rcx, rcx
0x180004836  jz      short loc_180004845
0x180004838  mov     rax, [rcx]
0x18000483b  mov     rax, [rax+10h]
0x18000483f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004844  nop
0x180004845  lea     eax, [rbx+7FFFBFFFh]
0x18000484b  cmp     eax, 1
0x18000484e  jbe     loc_180004724
0x180004854  jmp     loc_18000471A
0x180004859  mov     edi, 8004B200h
0x18000485e  mov     r15, [rbp+var_28]
0x180004862  jmp     short loc_180004845
0x180004864  cmp     ebx, 80004001h
0x18000486a  jnz     short loc_1800048CC
0x18000486c  test    sil, sil
0x18000486f  jnz     loc_1800049A8
0x180004875  mov     [rbp+var_28], 0
0x18000487d  mov     rax, [r12]
0x180004881  lea     rcx, [rbp+var_28]
0x180004885  mov     [rsp+80h+var_60], rcx
0x18000488a  lea     r9, _GUID_bb2e617c_0920_11d1_9a0b_00c04fc2d6c1
0x180004891  lea     r8, BHID_ThumbnailHandler
0x180004898  xor     edx, edx
0x18000489a  mov     rcx, r12
0x18000489d  mov     rax, [rax+18h]
0x1800048a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048a6  mov     ebx, eax
0x1800048a8  test    eax, eax
0x1800048aa  jns     short loc_180004918
0x1800048ac  mov     edi, 8004B200h
0x1800048b1  mov     rcx, [rbp+var_28]
0x1800048b5  test    rcx, rcx
0x1800048b8  jz      short loc_1800048C7
0x1800048ba  mov     rax, [rcx]
0x1800048bd  mov     rax, [rax+10h]
0x1800048c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048c6  nop
0x1800048c7  jmp     loc_18000482F
0x1800048cc  cmp     ebx, 80004002h
0x1800048d2  jnz     loc_18000482A
0x1800048d8  jmp     short loc_18000486C
0x1800048da  mov     [rbp+punkSite], 0
0x1800048e2  lea     r8, [rbp+punkSite]; void **
0x1800048e6  mov     rcx, r12; struct IUnknown *
0x1800048e9  call    ?GetCachedItemFromShellItem@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; GetCachedItemFromShellItem(IUnknown *,_GUID const &,void * *)
0x1800048ee  test    eax, eax
0x1800048f0  js      loc_180004724
0x1800048f6  mov     rdx, [rbp+punkSite]; punkSite
0x1800048fa  mov     rcx, [r15]; punk
0x1800048fd  call    cs:__imp_IUnknown_SetSite
0x180004903  mov     rcx, [rbp+punkSite]
0x180004907  mov     rax, [rcx]
0x18000490a  mov     rax, [rax+10h]
0x18000490e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004913  jmp     loc_180004724
0x180004918  mov     [rsp+80h+var_50], r14d; enum WTS_FLAGS
0x18000491d  mov     rax, [rbp+var_38]
0x180004921  mov     [rsp+80h+var_58], rax; int *
0x180004926  mov     rcx, [rbp+var_40]
0x18000492a  mov     [rsp+80h+var_60], rcx; unsigned int *
0x18000492f  mov     r8d, [rbp+arg_28]; unsigned int
0x180004933  mov     edx, [rbp+arg_20]; unsigned int
0x180004936  mov     rcx, [rbp+var_28]; struct IExtractImage *
0x18000493a  call    ?InitExtractImage@@YAJPEAUIExtractImage@@IIHPEAIPEAHW4WTS_FLAGS@@@Z; InitExtractImage(IExtractImage *,uint,uint,int,uint *,int *,WTS_FLAGS)
0x18000493f  mov     ebx, eax
0x180004941  test    eax, eax
0x180004943  js      short loc_1800049B2
0x180004945  mov     rcx, [rbp+var_28]
0x180004949  mov     rax, [rcx]
0x18000494c  mov     r8, r15
0x18000494f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180004956  mov     rax, [rax]
0x180004959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000495e  mov     ebx, eax
0x180004960  jmp     loc_1800048AC
0x180004965  mov     [rbp+var_30], 0
0x18000496c  mov     rax, [r12]
0x180004970  lea     r8, [rbp+var_30]
0x180004974  mov     edx, 20010000h
0x180004979  mov     rcx, r12
0x18000497c  mov     rax, [rax+30h]
0x180004980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004985  test    eax, eax
0x180004987  js      short loc_1800049A0
0x180004989  cmp     [rbp+var_30], 0
0x18000498d  jz      short loc_1800049A0
0x18000498f  xor     sil, sil
0x180004992  jmp     loc_1800047C5
0x180004997  mov     r14d, [rbp+var_30]
0x18000499b  jmp     loc_1800047BC
0x1800049a0  mov     sil, 1
0x1800049a3  jmp     loc_1800047C5
0x1800049a8  mov     ebx, 8004B202h
0x1800049ad  jmp     loc_18000482A
0x1800049b2  cmp     ebx, edi
0x1800049b4  jz      loc_1800048AC
0x1800049ba  cmp     ebx, 80270102h
0x1800049c0  mov     edi, 8004B200h
0x1800049c5  cmovnz  ebx, edi
0x1800049c8  jmp     loc_1800048B1
```
