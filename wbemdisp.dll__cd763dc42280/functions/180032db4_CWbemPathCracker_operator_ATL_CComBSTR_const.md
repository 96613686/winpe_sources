# CWbemPathCracker::operator==(ATL::CComBSTR const &)

- ea: `0x180032db4`
- end: `0x18003320d`
- name: `??8CWbemPathCracker@@QEAA_NAEBVCComBSTR@ATL@@@Z`
- size: `1113`
- prototype: `__int64 __fastcall(CWbemPathCracker *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18002e210`

## callees

- `0x1800109cc`
- `0x1800109fc`
- `0x180010a4c`
- `0x18001148c`
- `0x18001643c`
- `0x180032db4`
- `0x1800333f4`
- `0x1800334ec`
- `0x180033630`
- `0x180033748`
- `0x18003379c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180032e5d`
- `msvcrt!_wcsicmp` at `0x180032fbe`
- `msvcrt!_wcsicmp` at `0x180033111`
- `msvcrt!_wcsicmp` at `0x180032e5d`
- `msvcrt!_wcsicmp` at `0x180032fbe`
- `msvcrt!_wcsicmp` at `0x180033111`
- `OLEAUT32!__imp_SysFreeString` at `0x18003301b`
- `OLEAUT32!__imp_SysFreeString` at `0x180033025`
- `OLEAUT32!__imp_SysFreeString` at `0x180033158`
- `OLEAUT32!__imp_SysFreeString` at `0x180033179`
- `OLEAUT32!__imp_SysFreeString` at `0x1800331a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800331c7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800331d4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800331df`
- `OLEAUT32!__imp_SysFreeString` at `0x18003301b`
- `OLEAUT32!__imp_SysFreeString` at `0x180033025`
- `OLEAUT32!__imp_SysFreeString` at `0x180033158`
- `OLEAUT32!__imp_SysFreeString` at `0x180033179`
- `OLEAUT32!__imp_SysFreeString` at `0x1800331a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800331c7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800331d4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800331df`
- `OLEAUT32!__imp_SysStringLen` at `0x180032f9c`
- `OLEAUT32!__imp_SysStringLen` at `0x180032fae`
- `OLEAUT32!__imp_SysStringLen` at `0x180033096`
- `OLEAUT32!__imp_SysStringLen` at `0x1800330fd`
- `OLEAUT32!__imp_SysStringLen` at `0x180032f9c`
- `OLEAUT32!__imp_SysStringLen` at `0x180032fae`
- `OLEAUT32!__imp_SysStringLen` at `0x180033096`
- `OLEAUT32!__imp_SysStringLen` at `0x1800330fd`
- `OLEAUT32!__imp_VariantClear` at `0x180032ffa`
- `OLEAUT32!__imp_VariantClear` at `0x180033011`
- `OLEAUT32!__imp_VariantClear` at `0x18003314e`
- `OLEAUT32!__imp_VariantClear` at `0x18003316f`
- `OLEAUT32!__imp_VariantClear` at `0x18003319c`
- `OLEAUT32!__imp_VariantClear` at `0x1800331bd`
- `OLEAUT32!__imp_VariantClear` at `0x180032ffa`
- `OLEAUT32!__imp_VariantClear` at `0x180033011`
- `OLEAUT32!__imp_VariantClear` at `0x18003314e`
- `OLEAUT32!__imp_VariantClear` at `0x18003316f`
- `OLEAUT32!__imp_VariantClear` at `0x18003319c`
- `OLEAUT32!__imp_VariantClear` at `0x1800331bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
char __fastcall CWbemPathCracker::operator==(CWbemPathCracker *this, const struct ATL::CComBSTR *a2)
{
  char v3; // r14
  int v4; // ecx
  OLECHAR *v5; // rsi
  bool Class; // al
  bool IsSingleton; // bl
  unsigned int v8; // eax
  OLECHAR *v9; // rbx
  bool Key; // al
  OLECHAR *v11; // rdi
  bool v12; // al
  unsigned int v13; // ecx
  bool v14; // al
  OLECHAR *v15; // rdi
  OLECHAR *v16; // rbx
  unsigned int v17; // eax
  bool v18; // al
  BSTR pbstr; // [rsp+30h] [rbp-59h] BYREF
  VARIANTARG v21; // [rsp+38h] [rbp-51h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v23; // [rsp+68h] [rbp-21h] BYREF
  unsigned int v24; // [rsp+6Ch] [rbp-1Dh]
  BSTR bstrString; // [rsp+70h] [rbp-19h] BYREF
  wchar_t *String2; // [rsp+78h] [rbp-11h] BYREF
  wchar_t *String1; // [rsp+80h] [rbp-9h] BYREF
  BSTR v28; // [rsp+88h] [rbp-1h] BYREF
  BSTR v29[3]; // [rsp+90h] [rbp+7h] BYREF
  int v30; // [rsp+ACh] [rbp+23h]
  unsigned int v31; // [rsp+100h] [rbp+77h] BYREF
  enum WbemCimtypeEnum v32; // [rsp+108h] [rbp+7Fh] BYREF

  v3 = 0;
  CWbemPathCracker::CWbemPathCracker((CWbemPathCracker *)v29, a2);
  v4 = *((_DWORD *)this + 7);
  if ( v4 == v30
    && v4 == 1
    && CWbemPathCracker::IsClassOrInstance(this)
    && CWbemPathCracker::IsClassOrInstance((CWbemPathCracker *)v29) )
  {
    String1 = 0;
    v5 = 0;
    String2 = 0;
    if ( CWbemPathCracker::GetClass(this, (struct ATL::CComBSTR *)&String1) )
    {
      Class = CWbemPathCracker::GetClass((CWbemPathCracker *)v29, (struct ATL::CComBSTR *)&String2);
      v5 = String2;
      if ( Class && !_wcsicmp(String1, String2) )
      {
        IsSingleton = CWbemPathCracker::IsSingleton(this);
        if ( IsSingleton == CWbemPathCracker::IsSingleton((CWbemPathCracker *)v29) )
        {
          if ( CWbemPathCracker::IsSingleton(this)
            || CWbemPathCracker::IsClass(this) && CWbemPathCracker::IsClass((CWbemPathCracker *)v29) )
          {
            v3 = 1;
          }
          else if ( CWbemPathCracker::IsInstance(this) && CWbemPathCracker::IsInstance((CWbemPathCracker *)v29) )
          {
            v31 = 0;
            v23 = 0;
            if ( CWbemPathCracker::GetKeyCount(this, &v31)
              && CWbemPathCracker::GetKeyCount((CWbemPathCracker *)v29, &v23) )
            {
              v8 = v31;
              if ( v31 == v23 )
              {
                v3 = 1;
                if ( v31 == 1 )
                {
                  pbstr = 0;
                  v9 = 0;
                  bstrString = 0;
                  memset(&v21, 0, sizeof(v21));
                  v21.vt = 0;
                  memset(&pvarg, 0, sizeof(pvarg));
                  pvarg.vt = 0;
                  Key = CWbemPathCracker::GetKey(this, 0, (struct ATL::CComBSTR *)&pbstr, &v21, &v32);
                  v11 = pbstr;
                  if ( !Key
                    || (v12 = CWbemPathCracker::GetKey(
                                (CWbemPathCracker *)v29,
                                0,
                                (struct ATL::CComBSTR *)&bstrString,
                                &pvarg,
                                &v32),
                        v9 = bstrString,
                        !v12)
                    || v11 && SysStringLen(v11) && v9 && SysStringLen(v9) && _wcsicmp(v11, v9) )
                  {
                    v3 = 0;
                  }
                  else
                  {
                    v3 = KeyMatch(&v21, &pvarg);
                  }
                  if ( pvarg.vt == 4095 )
                    pvarg.vt = 8;
                  VariantClear(&pvarg);
                  if ( v21.vt == 4095 )
                    v21.vt = 8;
                  VariantClear(&v21);
                  SysFreeString(v9);
                  SysFreeString(v11);
                }
                else
                {
                  v13 = 0;
LABEL_34:
                  v24 = v13;
                  if ( v13 < v8 )
                  {
                    v28 = 0;
                    memset(&pvarg, 0, sizeof(pvarg));
                    pvarg.vt = 0;
                    v14 = CWbemPathCracker::GetKey(this, v13, (struct ATL::CComBSTR *)&v28, &pvarg, &v32);
                    v15 = v28;
                    if ( v14 && v28 && SysStringLen(v28) )
                    {
                      v16 = 0;
                      pbstr = 0;
                      v17 = 0;
                      memset(&v21, 0, sizeof(v21));
                      v21.vt = 0;
                      while ( 1 )
                      {
                        v32 = v17;
                        if ( v17 >= v31 )
                          break;
                        v18 = CWbemPathCracker::GetKey(
                                (CWbemPathCracker *)v29,
                                v17,
                                (struct ATL::CComBSTR *)&pbstr,
                                &v21,
                                (enum WbemCimtypeEnum *)&bstrString);
                        v16 = pbstr;
                        if ( !v18 || !pbstr || !SysStringLen(pbstr) )
                          break;
                        if ( !_wcsicmp(v15, v16) && (unsigned __int8)KeyMatch(&pvarg, &v21) )
                        {
                          if ( v32 < v31 )
                          {
                            if ( v21.vt == 4095 )
                              v21.vt = 8;
                            VariantClear(&v21);
                            SysFreeString(v16);
                            if ( pvarg.vt == 4095 )
                              pvarg.vt = 8;
                            VariantClear(&pvarg);
                            SysFreeString(v15);
                            v13 = v24 + 1;
                            v8 = v31;
                            goto LABEL_34;
                          }
                          break;
                        }
                        v17 = v32 + 1;
                      }
                      if ( v21.vt == 4095 )
                        v21.vt = 8;
                      VariantClear(&v21);
                      SysFreeString(v16);
                    }
                    if ( pvarg.vt == 4095 )
                      pvarg.vt = 8;
                    VariantClear(&pvarg);
                    SysFreeString(v15);
                    v3 = 0;
                  }
                }
              }
            }
          }
        }
      }
    }
    SysFreeString(v5);
    SysFreeString(String1);
  }
  CWbemPathCracker::~CWbemPathCracker(v29);
  return v3;
}

```

## disassembly

```asm
0x180032db4  mov     [rsp-8+arg_8], rbx
0x180032db9  push    rbp
0x180032dba  push    rsi
0x180032dbb  push    rdi
0x180032dbc  push    r12
0x180032dbe  push    r13
0x180032dc0  push    r14
0x180032dc2  push    r15
0x180032dc4  lea     rbp, [rsp-27h]
0x180032dc9  sub     rsp, 0B0h
0x180032dd0  mov     r15, rcx
0x180032dd3  xor     r12d, r12d
0x180032dd6  mov     r14b, r12b
0x180032dd9  mov     [rbp+57h+arg_0], r12b
0x180032ddd  lea     rcx, [rbp+57h+var_50]; this
0x180032de1  call    ??0CWbemPathCracker@@QEAA@AEBVCComBSTR@ATL@@@Z; CWbemPathCracker::CWbemPathCracker(ATL::CComBSTR const &)
0x180032de6  nop
0x180032de7  mov     ecx, [r15+1Ch]
0x180032deb  cmp     ecx, [rbp+57h+var_34]
0x180032dee  jnz     loc_1800331E6
0x180032df4  cmp     ecx, 1
0x180032df7  jnz     loc_1800331E6
0x180032dfd  mov     rcx, r15; this
0x180032e00  call    ?IsClassOrInstance@CWbemPathCracker@@QEAA_NXZ; CWbemPathCracker::IsClassOrInstance(void)
0x180032e05  test    al, al
0x180032e07  jz      loc_1800331E6
0x180032e0d  lea     rcx, [rbp+57h+var_50]; this
0x180032e11  call    ?IsClassOrInstance@CWbemPathCracker@@QEAA_NXZ; CWbemPathCracker::IsClassOrInstance(void)
0x180032e16  test    al, al
0x180032e18  jz      loc_1800331E6
0x180032e1e  mov     [rbp+57h+String1], r12
0x180032e22  mov     esi, r12d
0x180032e25  mov     [rbp+57h+String2], r12
0x180032e29  lea     rdx, [rbp+57h+String1]; struct ATL::CComBSTR *
0x180032e2d  mov     rcx, r15; this
0x180032e30  call    ?GetClass@CWbemPathCracker@@QEAA_NAEAVCComBSTR@ATL@@@Z; CWbemPathCracker::GetClass(ATL::CComBSTR &)
0x180032e35  test    al, al
0x180032e37  jz      loc_1800331D1
0x180032e3d  lea     rdx, [rbp+57h+String2]; struct ATL::CComBSTR *
0x180032e41  lea     rcx, [rbp+57h+var_50]; this
0x180032e45  call    ?GetClass@CWbemPathCracker@@QEAA_NAEAVCComBSTR@ATL@@@Z; CWbemPathCracker::GetClass(ATL::CComBSTR &)
0x180032e4a  mov     rsi, [rbp+57h+String2]
0x180032e4e  test    al, al
0x180032e50  jz      loc_1800331D1
0x180032e56  mov     rdx, rsi; String2
0x180032e59  mov     rcx, [rbp+57h+String1]; String1
0x180032e5d  call    cs:__imp__wcsicmp
0x180032e63  test    eax, eax
0x180032e65  jnz     loc_1800331D1
0x180032e6b  mov     rcx, r15; this
0x180032e6e  call    ?IsSingleton@CWbemPathCracker@@QEAA_NXZ; CWbemPathCracker::IsSingleton(void)
0x180032e73  mov     bl, al
0x180032e75  lea     rcx, [rbp+57h+var_50]; this
0x180032e79  call    ?IsSingleton@CWbemPathCracker@@QEAA_NXZ; CWbemPathCracker::IsSingleton(void)
0x180032e7e  cmp     bl, al
0x180032e80  jnz     loc_1800331D1
0x180032e86  mov     rcx, r15; this
0x180032e89  call    ?IsSingleton@CWbemPathCracker@@QEAA_NXZ; CWbemPathCracker::IsSingleton(void)
0x180032e8e  test    al, al
0x180032e90  jnz     short loc_180032EAB
0x180032e92  mov     rcx, r15; this
0x180032e95  call    ?IsClass@CWbemPathCracker@@QEAA_NXZ; CWbemPathCracker::IsClass(void)
0x180032e9a  test    al, al
0x180032e9c  jz      short loc_180032EB6
0x180032e9e  lea     rcx, [rbp+57h+var_50]; this
0x180032ea2  call    ?IsClass@CWbemPathCracker@@QEAA_NXZ; CWbemPathCracker::IsClass(void)
0x180032ea7  test    al, al
0x180032ea9  jz      short loc_180032EB6
0x180032eab  mov     r14d, 1
0x180032eb1  jmp     loc_1800331D1
0x180032eb6  mov     rcx, r15; this
0x180032eb9  call    ?IsInstance@CWbemPathCracker@@QEAA_NXZ; CWbemPathCracker::IsInstance(void)
0x180032ebe  test    al, al
0x180032ec0  jz      loc_1800331D1
0x180032ec6  lea     rcx, [rbp+57h+var_50]; this
0x180032eca  call    ?IsInstance@CWbemPathCracker@@QEAA_NXZ; CWbemPathCracker::IsInstance(void)
0x180032ecf  test    al, al
0x180032ed1  jz      loc_1800331D1
0x180032ed7  mov     [rbp+57h+arg_10], r12d
0x180032edb  mov     [rbp+57h+var_78], r12d
0x180032edf  lea     rdx, [rbp+57h+arg_10]; unsigned int *
0x180032ee3  mov     rcx, r15; this
0x180032ee6  call    ?GetKeyCount@CWbemPathCracker@@QEAA_NAEAK@Z; CWbemPathCracker::GetKeyCount(ulong &)
0x180032eeb  test    al, al
0x180032eed  jz      loc_1800331D1
0x180032ef3  lea     rdx, [rbp+57h+var_78]; unsigned int *
0x180032ef7  lea     rcx, [rbp+57h+var_50]; this
0x180032efb  call    ?GetKeyCount@CWbemPathCracker@@QEAA_NAEAK@Z; CWbemPathCracker::GetKeyCount(ulong &)
0x180032f00  test    al, al
0x180032f02  jz      loc_1800331D1
0x180032f08  mov     eax, [rbp+57h+arg_10]
0x180032f0b  cmp     eax, [rbp+57h+var_78]
0x180032f0e  jnz     loc_1800331D1
0x180032f14  mov     r14d, 1
0x180032f1a  cmp     eax, r14d
0x180032f1d  jnz     loc_180033030
0x180032f23  mov     [rbp+57h+pbstr], r12
0x180032f27  mov     rbx, r12
0x180032f2a  mov     [rbp+57h+bstrString], rbx
0x180032f2e  xorps   xmm0, xmm0
0x180032f31  xor     eax, eax
0x180032f33  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x180032f37  mov     qword ptr [rbp+57h+var_A8+10h], rax
0x180032f3b  mov     word ptr [rbp+57h+var_A8], r12w
0x180032f40  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180032f44  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180032f48  mov     word ptr [rbp+57h+pvarg], r12w
0x180032f4d  lea     rax, [rbp+57h+arg_18]
0x180032f51  mov     [rsp+0E0h+var_C0], rax; enum WbemCimtypeEnum *
0x180032f56  lea     r9, [rbp+57h+var_A8]; struct tagVARIANT *
0x180032f5a  lea     r8, [rbp+57h+pbstr]; struct ATL::CComBSTR *
0x180032f5e  xor     edx, edx; unsigned int
0x180032f60  mov     rcx, r15; this
0x180032f63  call    ?GetKey@CWbemPathCracker@@QEAA_NKAEAVCComBSTR@ATL@@AEAUtagVARIANT@@AEAW4WbemCimtypeEnum@@@Z; CWbemPathCracker::GetKey(ulong,ATL::CComBSTR &,tagVARIANT &,WbemCimtypeEnum &)
0x180032f68  mov     rdi, [rbp+57h+pbstr]
0x180032f6c  test    al, al
0x180032f6e  jz      short loc_180032FDA
0x180032f70  lea     rax, [rbp+57h+arg_18]
0x180032f74  mov     [rsp+0E0h+var_C0], rax; enum WbemCimtypeEnum *
0x180032f79  lea     r9, [rbp+57h+pvarg]; struct tagVARIANT *
0x180032f7d  lea     r8, [rbp+57h+bstrString]; struct ATL::CComBSTR *
0x180032f81  xor     edx, edx; unsigned int
0x180032f83  lea     rcx, [rbp+57h+var_50]; this
0x180032f87  call    ?GetKey@CWbemPathCracker@@QEAA_NKAEAVCComBSTR@ATL@@AEAUtagVARIANT@@AEAW4WbemCimtypeEnum@@@Z; CWbemPathCracker::GetKey(ulong,ATL::CComBSTR &,tagVARIANT &,WbemCimtypeEnum &)
0x180032f8c  mov     rbx, [rbp+57h+bstrString]
0x180032f90  test    al, al
0x180032f92  jz      short loc_180032FDA
0x180032f94  test    rdi, rdi
0x180032f97  jz      short loc_180032FC8
0x180032f99  mov     rcx, rdi; pbstr
0x180032f9c  call    cs:__imp_SysStringLen
0x180032fa2  test    eax, eax
0x180032fa4  jz      short loc_180032FC8
0x180032fa6  test    rbx, rbx
0x180032fa9  jz      short loc_180032FC8
0x180032fab  mov     rcx, rbx; pbstr
0x180032fae  call    cs:__imp_SysStringLen
0x180032fb4  test    eax, eax
0x180032fb6  jz      short loc_180032FC8
0x180032fb8  mov     rdx, rbx; String2
0x180032fbb  mov     rcx, rdi; String1
0x180032fbe  call    cs:__imp__wcsicmp
0x180032fc4  test    eax, eax
0x180032fc6  jnz     short loc_180032FDA
0x180032fc8  lea     rdx, [rbp+57h+pvarg]
0x180032fcc  lea     rcx, [rbp+57h+var_A8]
0x180032fd0  call    KeyMatch
0x180032fd5  mov     r14b, al
0x180032fd8  jmp     short loc_180032FDE
0x180032fda  mov     r14b, [rbp+57h+arg_0]
0x180032fde  mov     r13d, 0FFFh
0x180032fe4  mov     r12d, 8
0x180032fea  cmp     word ptr [rbp+57h+pvarg], r13w
0x180032fef  jnz     short loc_180032FF6
0x180032ff1  mov     word ptr [rbp+57h+pvarg], r12w
0x180032ff6  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180032ffa  call    cs:__imp_VariantClear
0x180033000  nop
0x180033001  cmp     word ptr [rbp+57h+var_A8], r13w
0x180033006  jnz     short loc_18003300D
0x180033008  mov     word ptr [rbp+57h+var_A8], r12w
0x18003300d  lea     rcx, [rbp+57h+var_A8]; pvarg
0x180033011  call    cs:__imp_VariantClear
0x180033017  nop
0x180033018  mov     rcx, rbx; bstrString
0x18003301b  call    cs:__imp_SysFreeString
0x180033021  nop
0x180033022  mov     rcx, rdi; bstrString
0x180033025  call    cs:__imp_SysFreeString
0x18003302b  jmp     loc_1800331D1
0x180033030  mov     ecx, r12d
0x180033033  mov     r13d, 0FFFh
0x180033039  mov     r12d, 8
0x18003303f  mov     [rbp+57h+var_74], ecx
0x180033042  cmp     ecx, eax
0x180033044  jnb     loc_1800331D1
0x18003304a  mov     [rbp+57h+var_58], 0
0x180033052  xorps   xmm0, xmm0
0x180033055  xor     eax, eax
0x180033057  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18003305b  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18003305f  mov     word ptr [rbp+57h+pvarg], ax
0x180033063  lea     rax, [rbp+57h+arg_18]
0x180033067  mov     [rsp+0E0h+var_C0], rax; enum WbemCimtypeEnum *
0x18003306c  lea     r9, [rbp+57h+pvarg]; struct tagVARIANT *
0x180033070  lea     r8, [rbp+57h+var_58]; struct ATL::CComBSTR *
0x180033074  mov     edx, ecx; unsigned int
0x180033076  mov     rcx, r15; this
0x180033079  call    ?GetKey@CWbemPathCracker@@QEAA_NKAEAVCComBSTR@ATL@@AEAUtagVARIANT@@AEAW4WbemCimtypeEnum@@@Z; CWbemPathCracker::GetKey(ulong,ATL::CComBSTR &,tagVARIANT &,WbemCimtypeEnum &)
0x18003307e  mov     rdi, [rbp+57h+var_58]
0x180033082  test    al, al
0x180033084  jz      loc_1800331AD
0x18003308a  test    rdi, rdi
0x18003308d  jz      loc_1800331AD
0x180033093  mov     rcx, rdi; pbstr
0x180033096  call    cs:__imp_SysStringLen
0x18003309c  test    eax, eax
0x18003309e  jz      loc_1800331AD
0x1800330a4  xor     ebx, ebx
0x1800330a6  mov     [rbp+57h+pbstr], rbx
0x1800330aa  xorps   xmm0, xmm0
0x1800330ad  xor     eax, eax
0x1800330af  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x1800330b3  mov     qword ptr [rbp+57h+var_A8+10h], rax
0x1800330b7  mov     word ptr [rbp+57h+var_A8], ax
0x1800330bb  mov     [rbp+57h+arg_18], eax
0x1800330be  mov     ecx, [rbp+57h+arg_10]
0x1800330c1  cmp     eax, ecx
0x1800330c3  jnb     loc_18003318C
0x1800330c9  lea     rcx, [rbp+57h+bstrString]
0x1800330cd  mov     [rsp+0E0h+var_C0], rcx; enum WbemCimtypeEnum *
0x1800330d2  lea     r9, [rbp+57h+var_A8]; struct tagVARIANT *
0x1800330d6  lea     r8, [rbp+57h+pbstr]; struct ATL::CComBSTR *
0x1800330da  mov     edx, eax; unsigned int
0x1800330dc  lea     rcx, [rbp+57h+var_50]; this
0x1800330e0  call    ?GetKey@CWbemPathCracker@@QEAA_NKAEAVCComBSTR@ATL@@AEAUtagVARIANT@@AEAW4WbemCimtypeEnum@@@Z; CWbemPathCracker::GetKey(ulong,ATL::CComBSTR &,tagVARIANT &,WbemCimtypeEnum &)
0x1800330e5  mov     rbx, [rbp+57h+pbstr]
0x1800330e9  test    al, al
0x1800330eb  jz      loc_18003318C
0x1800330f1  test    rbx, rbx
0x1800330f4  jz      loc_18003318C
0x1800330fa  mov     rcx, rbx; pbstr
0x1800330fd  call    cs:__imp_SysStringLen
0x180033103  test    eax, eax
0x180033105  jz      loc_18003318C
0x18003310b  mov     rdx, rbx; String2
0x18003310e  mov     rcx, rdi; String1
0x180033111  call    cs:__imp__wcsicmp
0x180033117  test    eax, eax
0x180033119  jnz     short loc_18003312C
0x18003311b  lea     rdx, [rbp+57h+var_A8]
0x18003311f  lea     rcx, [rbp+57h+pvarg]
0x180033123  call    KeyMatch
0x180033128  test    al, al
0x18003312a  jnz     short loc_180033134
0x18003312c  mov     eax, [rbp+57h+arg_18]
0x18003312f  add     eax, r14d
0x180033132  jmp     short loc_1800330BB
0x180033134  mov     ecx, [rbp+57h+arg_10]
0x180033137  mov     eax, [rbp+57h+arg_18]
0x18003313a  cmp     eax, ecx
0x18003313c  jnb     short loc_18003318C
0x18003313e  cmp     word ptr [rbp+57h+var_A8], r13w
0x180033143  jnz     short loc_18003314A
0x180033145  mov     word ptr [rbp+57h+var_A8], r12w
0x18003314a  lea     rcx, [rbp+57h+var_A8]; pvarg
0x18003314e  call    cs:__imp_VariantClear
0x180033154  nop
0x180033155  mov     rcx, rbx; bstrString
0x180033158  call    cs:__imp_SysFreeString
0x18003315e  nop
0x18003315f  cmp     word ptr [rbp+57h+pvarg], r13w
0x180033164  jnz     short loc_18003316B
0x180033166  mov     word ptr [rbp+57h+pvarg], r12w
0x18003316b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003316f  call    cs:__imp_VariantClear
0x180033175  nop
0x180033176  mov     rcx, rdi; bstrString
0x180033179  call    cs:__imp_SysFreeString
0x18003317f  mov     ecx, [rbp+57h+var_74]
0x180033182  inc     ecx
0x180033184  mov     eax, [rbp+57h+arg_10]
0x180033187  jmp     loc_18003303F
0x18003318c  cmp     word ptr [rbp+57h+var_A8], r13w
0x180033191  jnz     short loc_180033198
0x180033193  mov     word ptr [rbp+57h+var_A8], r12w
0x180033198  lea     rcx, [rbp+57h+var_A8]; pvarg
0x18003319c  call    cs:__imp_VariantClear
0x1800331a2  nop
0x1800331a3  mov     rcx, rbx; bstrString
0x1800331a6  call    cs:__imp_SysFreeString
0x1800331ac  nop
0x1800331ad  cmp     word ptr [rbp+57h+pvarg], r13w
0x1800331b2  jnz     short loc_1800331B9
0x1800331b4  mov     word ptr [rbp+57h+pvarg], r12w
0x1800331b9  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800331bd  call    cs:__imp_VariantClear
0x1800331c3  nop
0x1800331c4  mov     rcx, rdi; bstrString
0x1800331c7  call    cs:__imp_SysFreeString
0x1800331cd  mov     r14b, [rbp+57h+arg_0]
0x1800331d1  mov     rcx, rsi; bstrString
0x1800331d4  call    cs:__imp_SysFreeString
0x1800331da  nop
0x1800331db  mov     rcx, [rbp+57h+String1]; bstrString
0x1800331df  call    cs:__imp_SysFreeString
0x1800331e5  nop
0x1800331e6  lea     rcx, [rbp+57h+var_50]; this
0x1800331ea  call    ??1CWbemPathCracker@@UEAA@XZ; CWbemPathCracker::~CWbemPathCracker(void)
0x1800331ef  mov     al, r14b
0x1800331f2  mov     rbx, [rsp+0E0h+arg_8]
0x1800331fa  add     rsp, 0B0h
0x180033201  pop     r15
0x180033203  pop     r14
0x180033205  pop     r13
0x180033207  pop     r12
0x180033209  pop     rdi
0x18003320a  pop     rsi
0x18003320b  pop     rbp
0x18003320c  retn
  ... truncated ...
```
