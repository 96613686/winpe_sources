# CThemeCplCore::_UpdateWindowColorIconAndName(ITheme *)

- ea: `0x1800380d0`
- end: `0x180038587`
- name: `?_UpdateWindowColorIconAndName@CThemeCplCore@@AEAAJPEAUITheme@@@Z`
- size: `1207`
- prototype: `__int64 __fastcall(CThemeCplCore *__hidden this, struct ITheme *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180037f18`

## callees

- `0x180002280`
- `0x180002650`
- `0x18000268c`
- `0x18000fc18`
- `0x18000ff74`
- `0x180024238`
- `0x180035a44`
- `0x18003621c`
- `0x180037064`
- `0x180038020`
- `0x1800380d0`
- `0x180057010`

## import_xrefs

- `SHELL32!__imp_SHRestricted` at `0x180038137`
- `SHELL32!__imp_SHRestricted` at `0x1800381c6`
- `SHELL32!__imp_SHRestricted` at `0x1800384c9`
- `SHELL32!__imp_SHRestricted` at `0x180038137`
- `SHELL32!__imp_SHRestricted` at `0x1800381c6`
- `SHELL32!__imp_SHRestricted` at `0x1800384c9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800384fe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800384fe`
- `OLEAUT32!__imp_SysAllocString` at `0x1800383ac`
- `OLEAUT32!__imp_SysAllocString` at `0x1800383ac`
- `OLEAUT32!__imp_SysFreeString` at `0x180038398`
- `OLEAUT32!__imp_SysFreeString` at `0x18003854b`
- `OLEAUT32!__imp_SysFreeString` at `0x180038398`
- `OLEAUT32!__imp_SysFreeString` at `0x18003854b`
- `OLEAUT32!__imp_SysStringLen` at `0x18003831f`
- `OLEAUT32!__imp_SysStringLen` at `0x1800383e0`
- `OLEAUT32!__imp_SysStringLen` at `0x18003831f`
- `OLEAUT32!__imp_SysStringLen` at `0x1800383e0`
- `dwmapi!__imp_DwmpGetColorizationParameters` at `0x1800381e9`
- `dwmapi!__imp_DwmpGetColorizationParameters` at `0x1800381e9`
- `GDI32!DeleteObject` at `0x180038441`
- `GDI32!DeleteObject` at `0x180038441`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180038476`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180038476`
- `DUI70!StrToID` at `0x180038464`
- `DUI70!StrToID` at `0x180038464`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18003848f`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18003848f`

## string_xrefs

- `0x18003814a`: `WindowColorLink`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CThemeCplCore::_UpdateWindowColorIconAndName(struct DirectUI::Element **this, struct ITheme *a2)
{
  unsigned int v4; // r12d
  OLECHAR *v5; // rbx
  bool v6; // r13
  HINSTANCE v7; // rdx
  unsigned int v8; // r8d
  char v9; // al
  HRESULT Instance; // edi
  HINSTANCE v11; // rdx
  struct CColorSwatchConfig *v12; // rax
  struct CResourceCache *v13; // rdi
  struct CColorSwatchConfig *v14; // rax
  int Swatches; // r14d
  char v16; // r14
  int v17; // edi
  CColorSwatchStore *v18; // rcx
  int *v19; // rax
  int v20; // ecx
  const OLECHAR *v21; // r14
  int v22; // ecx
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v24; // rdi
  unsigned __int16 v25; // ax
  bool StringW; // al
  char v28; // [rsp+30h] [rbp-50h]
  HGDIOBJ ho; // [rsp+38h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-40h] BYREF
  struct CColorSwatchConfig *ppv; // [rsp+48h] [rbp-38h] BYREF
  int v32; // [rsp+50h] [rbp-30h] BYREF
  int v33; // [rsp+54h] [rbp-2Ch] BYREF
  _OWORD v34[2]; // [rsp+58h] [rbp-28h] BYREF

  v4 = 0;
  v5 = 0;
  bstrString = 0;
  v32 = 0;
  if ( (*(int (__fastcall **)(struct ITheme *, int *))(*(_QWORD *)a2 + 464LL))(a2, &v32) < 0 || (v6 = 1, v32 <= 0) )
    v6 = 0;
  if ( SHRestricted(REST_NODISPLAYAPPEARANCEPAGE) )
    CThemeCplCore::_EnableIconAndLink((CThemeCplCore *)this, this[24], L"WindowColorLink", v6);
  v33 = 0;
  if ( (*(int (__fastcall **)(struct ITheme *, int *))(*(_QWORD *)a2 + 416LL))(a2, &v33) >= 0 && v33 )
  {
    v8 = 26;
    goto LABEL_11;
  }
  if ( v6 )
  {
    v8 = 20;
LABEL_11:
    v9 = -ATL::CComBSTR::LoadStringW((ATL::CComBSTR *)&bstrString, v7, v8);
    Instance = v9 == 0 ? 0x80004005 : 0;
    v5 = bstrString;
    if ( !v9 )
      goto LABEL_59;
LABEL_44:
    ho = 0;
    if ( v6 )
      goto LABEL_45;
    goto LABEL_52;
  }
  LODWORD(ho) = 0;
  if ( SHRestricted(REST_NODISPLAYAPPEARANCEPAGE) )
  {
    memset(v34, 0, sizeof(v34));
    if ( (int)DwmpGetColorizationParameters(v34) < 0 )
      goto LABEL_50;
    if ( (v34[0] & 0xFF000000) == 0xFF000000 )
      LODWORD(ho) = v34[0] & 0xFFFFFF
                  | ((int)(((double)(DWORD2(v34[0]) - 10) * 0.75 / 100.0 + 0.1) * 255.0 + 0.5) << 24);
    else
      LODWORD(ho) = v34[0];
  }
  else if ( (*(int (__fastcall **)(struct ITheme *, HGDIOBJ *))(*(_QWORD *)a2 + 104LL))(a2, &ho) < 0 )
  {
    goto LABEL_50;
  }
  if ( this[32] )
    goto LABEL_63;
  v12 = (struct CColorSwatchConfig *)operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v12;
  ppv = v12;
  if ( v12 )
  {
    *(_QWORD *)v12 = 0;
    v14 = (struct CColorSwatchConfig *)operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
    ppv = v14;
    if ( v14 )
    {
      *(_QWORD *)v14 = 0;
      this[32] = v14;
      Swatches = CColorSwatchStore::LoadSwatches(v14, v13);
    }
    else
    {
      this[32] = 0;
      Swatches = -2147024882;
    }
    CResourceCache::~CResourceCache(v13);
    operator delete(v13, (const struct std::nothrow_t *)8);
    if ( Swatches >= 0 )
    {
LABEL_63:
      v16 = 1;
      v28 = 1;
      v17 = (int)ho;
      if ( !SysStringLen(0) )
      {
        while ( 1 )
        {
          v18 = this[32];
          if ( !*(_QWORD *)v18 || v4 >= (**(_DWORD **)v18 & 0xFFFFFFFu) )
            break;
          ppv = 0;
          if ( (int)CColorSwatchStore::GetSwatchPtrAtIndex(v18, v4, &ppv) >= 0 )
          {
            v19 = (int *)*((_QWORD *)ppv + 1);
            if ( v19 )
              v20 = *v19;
            else
              v20 = 0;
            if ( v20 != v17 || *((_WORD *)ppv + 12) == 28 )
            {
              v16 = v28;
            }
            else
            {
              v21 = *(const OLECHAR **)ppv;
              if ( *(OLECHAR **)ppv != v5 )
              {
                SysFreeString(v5);
                if ( v21 )
                {
                  v5 = SysAllocString(v21);
                  bstrString = v5;
                  if ( !v5 )
                    ATL::AtlThrowImpl(v22);
                }
                else
                {
                  v5 = 0;
                  bstrString = 0;
                }
              }
              v16 = 0;
              v28 = 0;
            }
          }
          if ( SysStringLen(v5) )
            break;
          ++v4;
        }
        if ( !v16 )
          goto LABEL_44;
      }
    }
  }
LABEL_50:
  StringW = ATL::CComBSTR::LoadStringW((ATL::CComBSTR *)&bstrString, v11, 0x12u);
  v5 = bstrString;
  if ( !StringW )
  {
    Instance = -2147467259;
    goto LABEL_59;
  }
  ho = 0;
LABEL_52:
  if ( SHRestricted(REST_NODISPLAYAPPEARANCEPAGE) )
  {
    ppv = 0;
    Instance = CoCreateInstance(
                 &CLSID_ThemeThumbnail,
                 0,
                 0x17u,
                 &GUID_b08ae63c_5aa0_445b_9452_feab335e45cb,
                 (LPVOID *)&ppv);
    if ( Instance >= 0 )
      Instance = (*(__int64 (__fastcall **)(struct CColorSwatchConfig *, _QWORD, HGDIOBJ *))(*(_QWORD *)ppv + 24LL))(
                   ppv,
                   0,
                   &ho);
    if ( ppv )
      (*(void (__fastcall **)(struct CColorSwatchConfig *))(*(_QWORD *)ppv + 16LL))(ppv);
    goto LABEL_46;
  }
LABEL_45:
  Instance = (*(__int64 (__fastcall **)(struct ITheme *, HGDIOBJ *))(*(_QWORD *)a2 + 512LL))(a2, &ho);
LABEL_46:
  if ( Instance >= 0 )
  {
    CThemeCplCore::_UpdateWindowColorIcon((CThemeCplCore *)this, (HBITMAP)ho);
    DeleteObject(ho);
    Descendent = this[25];
    if ( !Descendent )
    {
      v24 = this[3];
      v25 = StrToID(L"WindowColorName");
      Descendent = DirectUI::Element::FindDescendent(v24, v25);
      this[25] = Descendent;
    }
    Instance = DirectUI::Element::SetContentString(Descendent, v5);
  }
LABEL_59:
  SysFreeString(v5);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800380d0  mov     [rsp-38h+arg_10], rbx
0x1800380d5  push    rbp
0x1800380d6  push    rsi
0x1800380d7  push    rdi
0x1800380d8  push    r12
0x1800380da  push    r13
0x1800380dc  push    r14
0x1800380de  push    r15
0x1800380e0  mov     rbp, rsp
0x1800380e3  sub     rsp, 80h
0x1800380ea  mov     rax, cs:__security_cookie
0x1800380f1  xor     rax, rsp
0x1800380f4  mov     [rbp+var_8], rax
0x1800380f8  mov     r15, rdx
0x1800380fb  mov     rsi, rcx
0x1800380fe  xor     r12d, r12d
0x180038101  mov     ebx, r12d
0x180038104  mov     [rbp+bstrString], rbx
0x180038108  mov     [rbp+var_30], r12d
0x18003810c  mov     rax, [rdx]
0x18003810f  lea     rdx, [rbp+var_30]
0x180038113  mov     rcx, r15
0x180038116  mov     rax, [rax+1D0h]
0x18003811d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038122  test    eax, eax
0x180038124  js      short loc_18003812F
0x180038126  cmp     [rbp+var_30], r12d
0x18003812a  mov     r13b, 1
0x18003812d  jg      short loc_180038132
0x18003812f  mov     r13b, r12b
0x180038132  mov     ecx, 4000005Bh; rest
0x180038137  call    cs:__imp_SHRestricted
0x18003813e  nop     dword ptr [rax+rax+00h]
0x180038143  test    eax, eax
0x180038145  jz      short loc_180038160
0x180038147  mov     r9b, r13b; bool
0x18003814a  lea     r8, aWindowcolorlin; "WindowColorLink"
0x180038151  mov     rdx, [rsi+0C0h]; struct DirectUI::Element *
0x180038158  mov     rcx, rsi; this
0x18003815b  call    ?_EnableIconAndLink@CThemeCplCore@@AEAAXPEAVElement@DirectUI@@PEBG_N@Z; CThemeCplCore::_EnableIconAndLink(DirectUI::Element *,ushort const *,bool)
0x180038160  mov     [rbp+var_2C], r12d
0x180038164  mov     rax, [r15]
0x180038167  lea     rdx, [rbp+var_2C]
0x18003816b  mov     rcx, r15
0x18003816e  mov     rax, [rax+1A0h]
0x180038175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003817a  test    eax, eax
0x18003817c  js      short loc_18003818C
0x18003817e  cmp     [rbp+var_2C], r12d
0x180038182  jz      short loc_18003818C
0x180038184  mov     r8d, 1Ah
0x18003818a  jmp     short loc_180038197
0x18003818c  test    r13b, r13b
0x18003818f  jz      short loc_1800381BD
0x180038191  mov     r8d, 14h; unsigned int
0x180038197  lea     rcx, [rbp+bstrString]; this
0x18003819b  call    ?LoadStringW@CComBSTR@ATL@@QEAA_NPEAUHINSTANCE__@@I@Z; ATL::CComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x1800381a0  neg     al
0x1800381a2  sbb     edi, edi
0x1800381a4  not     edi
0x1800381a6  and     edi, 80004005h
0x1800381ac  mov     rbx, [rbp+bstrString]
0x1800381b0  test    edi, edi
0x1800381b2  jns     loc_180038404
0x1800381b8  jmp     loc_180038548
0x1800381bd  mov     dword ptr [rbp+ho], r12d
0x1800381c1  mov     ecx, 4000005Bh; rest
0x1800381c6  call    cs:__imp_SHRestricted
0x1800381cd  nop     dword ptr [rax+rax+00h]
0x1800381d2  test    eax, eax
0x1800381d4  jz      loc_18003825D
0x1800381da  xorps   xmm0, xmm0
0x1800381dd  movups  [rbp+var_28], xmm0
0x1800381e1  movups  [rbp+var_18], xmm0
0x1800381e5  lea     rcx, [rbp+var_28]
0x1800381e9  call    cs:__imp_DwmpGetColorizationParameters
0x1800381f0  nop     dword ptr [rax+rax+00h]
0x1800381f5  test    eax, eax
0x1800381f7  js      loc_1800384A5
0x1800381fd  mov     edx, dword ptr [rbp+var_28]
0x180038200  mov     eax, edx
0x180038202  mov     ecx, 0FF000000h
0x180038207  and     eax, ecx
0x180038209  cmp     eax, ecx
0x18003820b  jz      short loc_180038212
0x18003820d  mov     dword ptr [rbp+ho], edx
0x180038210  jmp     short loc_180038278
0x180038212  mov     ecx, dword ptr [rbp+var_28+8]
0x180038215  add     ecx, 0FFFFFFF6h
0x180038218  xorps   xmm0, xmm0
0x18003821b  cvtsi2sd xmm0, rcx
0x180038220  mulsd   xmm0, cs:__real@3fe8000000000000
0x180038228  divsd   xmm0, cs:__real@4059000000000000
0x180038230  addsd   xmm0, cs:__real@3fb999999999999a
0x180038238  mulsd   xmm0, cs:__real@406fe00000000000
0x180038240  addsd   xmm0, cs:__real@3fe0000000000000
0x180038248  cvttsd2si rax, xmm0
0x18003824d  shl     eax, 18h
0x180038250  and     edx, 0FFFFFFh
0x180038256  or      eax, edx
0x180038258  mov     dword ptr [rbp+ho], eax
0x18003825b  jmp     short loc_180038278
0x18003825d  mov     rax, [r15]
0x180038260  lea     rdx, [rbp+ho]
0x180038264  mov     rcx, r15
0x180038267  mov     rax, [rax+68h]
0x18003826b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038270  test    eax, eax
0x180038272  js      loc_1800384A5
0x180038278  cmp     [rsi+100h], r12
0x18003827f  jnz     loc_180038313
0x180038285  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003828c  mov     r14d, 8
0x180038292  mov     ecx, r14d; unsigned __int64
0x180038295  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003829a  mov     rdi, rax
0x18003829d  mov     [rbp+var_38], rax
0x1800382a1  test    rax, rax
0x1800382a4  jz      loc_1800384A5
0x1800382aa  mov     [rax], r12
0x1800382ad  test    rax, rax
0x1800382b0  jz      loc_1800384A5
0x1800382b6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800382bd  mov     ecx, r14d; unsigned __int64
0x1800382c0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800382c5  mov     [rbp+var_38], rax
0x1800382c9  test    rax, rax
0x1800382cc  jz      short loc_1800382E8
0x1800382ce  mov     [rax], r12
0x1800382d1  mov     [rsi+100h], rax
0x1800382d8  mov     rdx, rdi; struct CResourceCache *
0x1800382db  mov     rcx, rax; this
0x1800382de  call    ?LoadSwatches@CColorSwatchStore@@QEAAJPEAVCResourceCache@@@Z; CColorSwatchStore::LoadSwatches(CResourceCache *)
0x1800382e3  mov     r14d, eax
0x1800382e6  jmp     short loc_1800382F5
0x1800382e8  mov     [rsi+100h], r12
0x1800382ef  mov     r14d, 8007000Eh
0x1800382f5  mov     rcx, rdi; this
0x1800382f8  call    ??1CResourceCache@@QEAA@XZ; CResourceCache::~CResourceCache(void)
0x1800382fd  mov     edx, 8; struct std::nothrow_t *
0x180038302  mov     rcx, rdi; void *
0x180038305  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003830a  test    r14d, r14d
0x18003830d  js      loc_1800384A5
0x180038313  mov     r14b, 1
0x180038316  mov     [rbp+var_50], r14b
0x18003831a  mov     edi, dword ptr [rbp+ho]
0x18003831d  xor     ecx, ecx; pbstr
0x18003831f  call    cs:__imp_SysStringLen
0x180038326  nop     dword ptr [rax+rax+00h]
0x18003832b  test    eax, eax
0x18003832d  jnz     loc_1800384A2
0x180038333  mov     rcx, [rsi+100h]; this
0x18003833a  mov     rax, [rcx]
0x18003833d  test    rax, rax
0x180038340  jz      loc_1800383F8
0x180038346  mov     eax, [rax]
0x180038348  and     eax, 0FFFFFFFh
0x18003834d  cmp     r12d, eax
0x180038350  jnb     loc_1800383F8
0x180038356  mov     [rbp+var_38], 0
0x18003835e  lea     r8, [rbp+var_38]; struct CColorSwatchConfig **
0x180038362  mov     edx, r12d; unsigned int
0x180038365  call    ?GetSwatchPtrAtIndex@CColorSwatchStore@@QEAAJIPEAPEBVCColorSwatchConfig@@@Z; CColorSwatchStore::GetSwatchPtrAtIndex(uint,CColorSwatchConfig const * *)
0x18003836a  test    eax, eax
0x18003836c  js      short loc_1800383DD
0x18003836e  mov     r14, [rbp+var_38]
0x180038372  mov     rax, [r14+8]
0x180038376  test    rax, rax
0x180038379  jz      short loc_18003837F
0x18003837b  mov     ecx, [rax]
0x18003837d  jmp     short loc_180038381
0x18003837f  xor     ecx, ecx
0x180038381  cmp     ecx, edi
0x180038383  jnz     short loc_1800383D9
0x180038385  cmp     word ptr [r14+18h], 1Ch
0x18003838b  jz      short loc_1800383D9
0x18003838d  mov     r14, [r14]
0x180038390  cmp     r14, rbx
0x180038393  jz      short loc_1800383D0
0x180038395  mov     rcx, rbx; bstrString
0x180038398  call    cs:__imp_SysFreeString
0x18003839f  nop     dword ptr [rax+rax+00h]
0x1800383a4  test    r14, r14
0x1800383a7  jz      short loc_1800383CA
0x1800383a9  mov     rcx, r14; psz
0x1800383ac  call    cs:__imp_SysAllocString
0x1800383b3  nop     dword ptr [rax+rax+00h]
0x1800383b8  mov     rbx, rax
0x1800383bb  mov     [rbp+bstrString], rax
0x1800383bf  test    rax, rax
0x1800383c2  jz      loc_180038581
0x1800383c8  jmp     short loc_1800383D0
0x1800383ca  xor     ebx, ebx
0x1800383cc  mov     [rbp+bstrString], rbx
0x1800383d0  xor     r14b, r14b
0x1800383d3  mov     [rbp+var_50], r14b
0x1800383d7  jmp     short loc_1800383DD
0x1800383d9  mov     r14b, [rbp+var_50]
0x1800383dd  mov     rcx, rbx; pbstr
0x1800383e0  call    cs:__imp_SysStringLen
0x1800383e7  nop     dword ptr [rax+rax+00h]
0x1800383ec  test    eax, eax
0x1800383ee  jnz     short loc_1800383F8
0x1800383f0  inc     r12d
0x1800383f3  jmp     loc_180038333
0x1800383f8  xor     r12d, r12d
0x1800383fb  test    r14b, r14b
0x1800383fe  jnz     loc_1800384A5
0x180038404  mov     [rbp+ho], r12
0x180038408  test    r13b, r13b
0x18003840b  jz      loc_1800384C4
0x180038411  mov     rax, [r15]
0x180038414  lea     rdx, [rbp+ho]
0x180038418  mov     rcx, r15
0x18003841b  mov     rax, [rax+200h]
0x180038422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038427  mov     edi, eax
0x180038429  test    edi, edi
0x18003842b  js      loc_180038548
0x180038431  mov     rdx, [rbp+ho]; HBITMAP
0x180038435  mov     rcx, rsi; this
0x180038438  call    ?_UpdateWindowColorIcon@CThemeCplCore@@AEAAXPEAUHBITMAP__@@@Z; CThemeCplCore::_UpdateWindowColorIcon(HBITMAP__ *)
0x18003843d  mov     rcx, [rbp+ho]; ho
0x180038441  call    cs:__imp_DeleteObject
0x180038448  nop     dword ptr [rax+rax+00h]
0x18003844d  mov     rax, [rsi+0C8h]
0x180038454  test    rax, rax
0x180038457  jnz     short loc_180038489
0x180038459  mov     rdi, [rsi+18h]
0x18003845d  lea     rcx, aWindowcolornam; "WindowColorName"
0x180038464  call    cs:__imp_StrToID
0x18003846b  nop     dword ptr [rax+rax+00h]
0x180038470  movzx   edx, ax
0x180038473  mov     rcx, rdi
0x180038476  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003847d  nop     dword ptr [rax+rax+00h]
0x180038482  mov     [rsi+0C8h], rax
0x180038489  mov     rdx, rbx
0x18003848c  mov     rcx, rax
0x18003848f  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180038496  nop     dword ptr [rax+rax+00h]
0x18003849b  mov     edi, eax
0x18003849d  jmp     loc_180038548
0x1800384a2  xor     r12d, r12d
0x1800384a5  mov     r8d, 12h; unsigned int
0x1800384ab  lea     rcx, [rbp+bstrString]; this
0x1800384af  call    ?LoadStringW@CComBSTR@ATL@@QEAA_NPEAUHINSTANCE__@@I@Z; ATL::CComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x1800384b4  mov     rbx, [rbp+bstrString]
0x1800384b8  test    al, al
0x1800384ba  jz      loc_180038543
0x1800384c0  mov     [rbp+ho], r12
0x1800384c4  mov     ecx, 4000005Bh; rest
0x1800384c9  call    cs:__imp_SHRestricted
0x1800384d0  nop     dword ptr [rax+rax+00h]
0x1800384d5  test    eax, eax
0x1800384d7  jz      loc_180038411
0x1800384dd  mov     [rbp+var_38], r12
0x1800384e1  lea     rax, [rbp+var_38]
0x1800384e5  mov     [rsp+80h+ppv], rax; ppv
0x1800384ea  lea     r9, _GUID_b08ae63c_5aa0_445b_9452_feab335e45cb; riid
0x1800384f1  xor     edx, edx; pUnkOuter
0x1800384f3  lea     r8d, [rdx+17h]; dwClsContext
0x1800384f7  lea     rcx, CLSID_ThemeThumbnail; rclsid
0x1800384fe  call    cs:__imp_CoCreateInstance
0x180038505  nop     dword ptr [rax+rax+00h]
0x18003850a  mov     edi, eax
0x18003850c  test    eax, eax
0x18003850e  js      short loc_180038528
0x180038510  mov     rcx, [rbp+var_38]
0x180038514  mov     rax, [rcx]
0x180038517  lea     r8, [rbp+ho]
0x18003851b  xor     edx, edx
0x18003851d  mov     rax, [rax+18h]
0x180038521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038526  mov     edi, eax
0x180038528  mov     rcx, [rbp+var_38]
0x18003852c  test    rcx, rcx
0x18003852f  jz      short loc_18003853E
0x180038531  mov     rax, [rcx]
0x180038534  mov     rax, [rax+10h]
0x180038538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003853d  nop
0x18003853e  jmp     loc_180038429
0x180038543  mov     edi, 80004005h
0x180038548  mov     rcx, rbx; bstrString
0x18003854b  call    cs:__imp_SysFreeString
0x180038552  nop     dword ptr [rax+rax+00h]
0x180038557  mov     eax, edi
0x180038559  mov     rcx, [rbp+var_8]
0x18003855d  xor     rcx, rsp; StackCookie
0x180038560  call    __security_check_cookie
0x180038565  mov     rbx, [rsp+80h+arg_10]
0x18003856d  add     rsp, 80h
0x180038574  pop     r15
0x180038576  pop     r14
0x180038578  pop     r13
0x18003857a  pop     r12
0x18003857c  pop     rdi
0x18003857d  pop     rsi
  ... truncated ...
```
