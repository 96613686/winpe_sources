# CShareMediaPage::EnsureCustomCodeBehind(void)

- ea: `0x180013248`
- end: `0x18001342b`
- name: `?EnsureCustomCodeBehind@CShareMediaPage@@IEAAJXZ`
- size: `483`
- prototype: `__int64 __fastcall(CShareMediaPage *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x180013490`

## callees

- `0x180001914`
- `0x180003860`
- `0x180003888`
- `0x180007c34`
- `0x18000a85c`
- `0x180013248`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800132e0`
- `OLEAUT32!__imp_VariantInit` at `0x1800132e0`
- `OLEAUT32!__imp_VariantClear` at `0x1800133c6`
- `OLEAUT32!__imp_VariantClear` at `0x1800133c6`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800132bf`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800132bf`

## pseudocode

```c
__int64 __fastcall CShareMediaPage::EnsureCustomCodeBehind(CShareMediaPage *this)
{
  _QWORD *v2; // rcx
  HRESULT v3; // ebx
  char *v4; // rsi
  IUnknown *v5; // rcx
  CShareMediaCore *v6; // rax
  CShareMediaCore *v7; // rax
  CShareMediaCore *v8; // rdi
  __int64 (__fastcall ***v9)(_QWORD, GUID *, ULONG *); // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-38h] BYREF
  VARIANTARG v12; // [rsp+48h] [rbp-20h] BYREF
  void *ppvOut; // [rsp+A0h] [rbp+38h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_7279559f42d632541ba16c3c2e3c18dc_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = 0;
  v4 = (char *)this + 264;
  if ( !*((_QWORD *)this + 33) )
  {
    v5 = (IUnknown *)*((_QWORD *)this + 27);
    ppvOut = 0;
    v3 = IUnknown_QueryService(
           v5,
           (const GUID *const)&SID_PerNamespaceIDPropertyBag,
           &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
           &ppvOut);
    if ( v3 >= 0 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      pvarg.vt = 13;
      v3 = (*(__int64 (__fastcall **)(void *, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)ppvOut + 24LL))(
             ppvOut,
             L"ShareMediaCore",
             &pvarg,
             0);
      if ( v3 < 0 )
      {
        v6 = (CShareMediaCore *)operator new(0xF8u);
        if ( v6 && (v7 = CShareMediaCore::CShareMediaCore(v6), (v8 = v7) != 0) )
        {
          v3 = CShareMediaCore::Initialize(v7);
          if ( v3 >= 0 )
          {
            v3 = (**(__int64 (__fastcall ***)(CShareMediaCore *, GUID *, char *))v8)(
                   v8,
                   &GUID_00000000_0000_0000_c000_000000000046,
                   v4);
            if ( v3 >= 0 )
            {
              v9 = *(__int64 (__fastcall ****)(_QWORD, GUID *, ULONG *))v4;
              memset(&v12, 0, sizeof(v12));
              v12.vt = 13;
              v3 = (**v9)(v9, &GUID_00000000_0000_0000_c000_000000000046, (ULONG *)&v12.cyVal);
              if ( v3 >= 0 )
              {
                v3 = (*(__int64 (__fastcall **)(void *, const wchar_t *, VARIANTARG *))(*(_QWORD *)ppvOut + 32LL))(
                       ppvOut,
                       L"ShareMediaCore",
                       &v12);
                VariantClear(&v12);
              }
            }
          }
          (*(void (__fastcall **)(CShareMediaCore *))(*(_QWORD *)v8 + 16LL))(v8);
        }
        else
        {
          v3 = -2147024882;
        }
      }
      else
      {
        *(_QWORD *)v4 = pvarg.llVal;
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_d(v2[2], 23, WPP_7279559f42d632541ba16c3c2e3c18dc_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013248  push    rbp
0x18001324a  push    rbx
0x18001324b  push    rsi
0x18001324c  push    rdi
0x18001324d  push    r14
0x18001324f  push    r15
0x180013251  mov     rbp, rsp
0x180013254  sub     rsp, 68h
0x180013258  mov     rdi, rcx
0x18001325b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013262  lea     r14, WPP_GLOBAL_Control
0x180013269  cmp     rcx, r14
0x18001326c  jz      short loc_180013290
0x18001326e  test    byte ptr [rcx+1Ch], 20h
0x180013272  jz      short loc_180013290
0x180013274  mov     rcx, [rcx+10h]
0x180013278  lea     r8, WPP_7279559f42d632541ba16c3c2e3c18dc_Traceguids
0x18001327f  mov     edx, 16h
0x180013284  call    WPP_SF_
0x180013289  mov     rcx, cs:WPP_GLOBAL_Control
0x180013290  xor     ebx, ebx
0x180013292  lea     rsi, [rdi+108h]
0x180013299  cmp     [rsi], rbx
0x18001329c  jnz     loc_1800133F9
0x1800132a2  mov     rcx, [rdi+0D8h]; punk
0x1800132a9  lea     r9, [rbp+ppvOut]; ppvOut
0x1800132ad  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1800132b4  mov     [rbp+ppvOut], rbx
0x1800132b8  lea     rdx, SID_PerNamespaceIDPropertyBag; guidService
0x1800132bf  call    cs:__imp_IUnknown_QueryService
0x1800132c5  mov     ebx, eax
0x1800132c7  test    eax, eax
0x1800132c9  js      loc_1800133F2
0x1800132cf  xorps   xmm0, xmm0
0x1800132d2  lea     rcx, [rbp+pvarg]; pvarg
0x1800132d6  xor     eax, eax
0x1800132d8  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800132dc  mov     qword ptr [rbp+pvarg+10h], rax
0x1800132e0  call    cs:__imp_VariantInit
0x1800132e6  mov     rcx, [rbp+ppvOut]
0x1800132ea  lea     r8, [rbp+pvarg]
0x1800132ee  mov     r15d, 0Dh
0x1800132f4  lea     rdx, aSharemediacore; "ShareMediaCore"
0x1800132fb  mov     word ptr [rbp+pvarg], r15w
0x180013300  xor     r9d, r9d
0x180013303  mov     rax, [rcx]
0x180013306  mov     rax, [rax+18h]
0x18001330a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001330f  mov     ebx, eax
0x180013311  test    eax, eax
0x180013313  js      short loc_180013321
0x180013315  mov     rax, qword ptr [rbp+pvarg+8]
0x180013319  mov     [rsi], rax
0x18001331c  jmp     loc_1800133E2
0x180013321  mov     ecx, 0F8h; Size
0x180013326  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001332b  test    rax, rax
0x18001332e  jz      loc_1800133DD
0x180013334  mov     rcx, rax; this
0x180013337  call    ??0CShareMediaCore@@QEAA@XZ; CShareMediaCore::CShareMediaCore(void)
0x18001333c  mov     rdi, rax
0x18001333f  test    rax, rax
0x180013342  jz      loc_1800133DD
0x180013348  mov     rcx, rax; this
0x18001334b  call    ?Initialize@CShareMediaCore@@QEAAJXZ; CShareMediaCore::Initialize(void)
0x180013350  mov     ebx, eax
0x180013352  test    eax, eax
0x180013354  js      short loc_1800133CC
0x180013356  mov     rcx, [rdi]
0x180013359  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180013360  mov     r8, rsi
0x180013363  mov     rax, [rcx]
0x180013366  mov     rcx, rdi
0x180013369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001336e  mov     ebx, eax
0x180013370  test    eax, eax
0x180013372  js      short loc_1800133CC
0x180013374  mov     rcx, [rsi]
0x180013377  lea     r8, [rbp+var_20+8]
0x18001337b  xor     eax, eax
0x18001337d  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180013384  mov     qword ptr [rbp+var_20+10h], rax
0x180013388  xorps   xmm0, xmm0
0x18001338b  movups  xmmword ptr [rbp-20h], xmm0
0x18001338f  mov     word ptr [rbp+var_20], r15w
0x180013394  mov     rax, [rcx]
0x180013397  mov     rax, [rax]
0x18001339a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001339f  mov     ebx, eax
0x1800133a1  test    eax, eax
0x1800133a3  js      short loc_1800133CC
0x1800133a5  mov     rcx, [rbp+ppvOut]
0x1800133a9  lea     r8, [rbp+var_20]
0x1800133ad  lea     rdx, aSharemediacore; "ShareMediaCore"
0x1800133b4  mov     rax, [rcx]
0x1800133b7  mov     rax, [rax+20h]
0x1800133bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133c0  lea     rcx, [rbp+var_20]; pvarg
0x1800133c4  mov     ebx, eax
0x1800133c6  call    cs:__imp_VariantClear
0x1800133cc  mov     rax, [rdi]
0x1800133cf  mov     rcx, rdi
0x1800133d2  mov     rax, [rax+10h]
0x1800133d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133db  jmp     short loc_1800133E2
0x1800133dd  mov     ebx, 8007000Eh
0x1800133e2  mov     rcx, [rbp+ppvOut]
0x1800133e6  mov     rax, [rcx]
0x1800133e9  mov     rax, [rax+10h]
0x1800133ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800133f9  cmp     rcx, r14
0x1800133fc  jz      short loc_18001341C
0x1800133fe  test    byte ptr [rcx+1Ch], 20h
0x180013402  jz      short loc_18001341C
0x180013404  mov     rcx, [rcx+10h]
0x180013408  lea     r8, WPP_7279559f42d632541ba16c3c2e3c18dc_Traceguids
0x18001340f  mov     edx, 17h
0x180013414  mov     r9d, ebx
0x180013417  call    WPP_SF_d
0x18001341c  mov     eax, ebx
0x18001341e  add     rsp, 68h
0x180013422  pop     r15
0x180013424  pop     r14
0x180013426  pop     rdi
0x180013427  pop     rsi
0x180013428  pop     rbx
0x180013429  pop     rbp
0x18001342a  retn
```
