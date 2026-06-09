# CTextTemplate::HandleEmbeddedObjectProperties(ushort *,IWbemClassObject *)

- ea: `0x180038c20`
- end: `0x180038fe0`
- name: `?HandleEmbeddedObjectProperties@CTextTemplate@@AEAAPEAGPEAGPEAUIWbemClassObject@@@Z`
- size: `960`
- prototype: `unsigned __int16 *__fastcall(CTextTemplate *__hidden this, unsigned __int16 *, struct IWbemClassObject *)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x1800016f0`
- `0x1800388a0`

## callees

- `0x1800029a0`
- `0x18000a290`
- `0x180013564`
- `0x180014120`
- `0x1800154d0`
- `0x18001d970`
- `0x180022e40`
- `0x1800254d0`
- `0x180028484`
- `0x18002a1ac`
- `0x1800388a0`
- `0x180038c20`
- `0x180044310`
- `0x180047010`

## import_xrefs

- `msvcrt!wcschr` at `0x180038c82`
- `msvcrt!wcschr` at `0x180038dc6`
- `msvcrt!wcschr` at `0x180038c82`
- `msvcrt!wcschr` at `0x180038dc6`
- `OLEAUT32!__imp_SysAllocString` at `0x180038ccd`
- `OLEAUT32!__imp_SysAllocString` at `0x180038f92`
- `OLEAUT32!__imp_SysAllocString` at `0x180038ccd`
- `OLEAUT32!__imp_SysAllocString` at `0x180038f92`
- `OLEAUT32!__imp_VariantInit` at `0x180038d4f`
- `OLEAUT32!__imp_VariantInit` at `0x180038d4f`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180038eb2`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180038eb2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180038ed8`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180038ed8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180038ec5`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180038ec5`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180038f10`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180038f10`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
BSTR __fastcall CTextTemplate::HandleEmbeddedObjectProperties(
        CTextTemplate *this,
        unsigned __int16 *a2,
        struct IWbemClassObject *a3)
{
  wchar_t *v6; // rax
  const OLECHAR *v7; // rcx
  unsigned __int64 v8; // rbx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rsi
  BSTR v11; // rbx
  signed int v12; // eax
  unsigned int v13; // edi
  int v14; // eax
  const OLECHAR *v15; // rcx
  wchar_t *v16; // rax
  signed int v17; // eax
  unsigned int v18; // ebx
  struct IUnknown *PropertyFromIUnknown; // rax
  LONG v20; // eax
  bool i; // cc
  unsigned __int16 *v22; // rax
  LONG v23; // eax
  LONG v24; // ecx
  const unsigned __int16 *v25; // rdx
  LONG plUbound; // [rsp+40h] [rbp-C0h] BYREF
  LONG rgIndices[2]; // [rsp+48h] [rbp-B8h] BYREF
  LONG plLbound; // [rsp+50h] [rbp-B0h] BYREF
  struct IUnknown *pv; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v32[2]; // [rsp+78h] [rbp-88h] BYREF
  OLECHAR *psz[5]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v34; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v35[1024]; // [rsp+C0h] [rbp-40h] BYREF

  psz[0] = (OLECHAR *)&unk_180070020;
  psz[1] = 0;
  psz[2] = 0;
  psz[3] = (OLECHAR *)50;
  psz[4] = (OLECHAR *)50;
  v6 = wcschr(a2, 0x2Eu);
  if ( !v6 )
  {
    v7 = L"<error>";
LABEL_5:
    v11 = SysAllocString(v7);
    goto LABEL_38;
  }
  v8 = v6 - a2;
  v9 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v8 + 1, 2u));
  v10 = v9;
  if ( !v9 )
  {
    v7 = L"<failed>";
    goto LABEL_5;
  }
  v32[0] = v9;
  v32[1] = 0;
  v12 = StringCchCopyNW(v9, v8 + 1, a2, v8);
  v13 = v12;
  if ( v12 < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v12);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_caa7cf28e9283147a4c859e60103ff52_Traceguids, v13);
    }
  }
  v10[v8] = 0;
  VariantInit(&pvarg);
  v14 = ((__int64 (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
          a3,
          v10,
          0,
          &pvarg,
          0,
          0);
  if ( v14 == -2147217406 )
  {
    v15 = L"<unknown>";
  }
  else if ( v14 >= 0 )
  {
    if ( pvarg.vt == 1 )
    {
      v15 = L"<null>";
    }
    else
    {
      v16 = wcschr(a2, 0x2Eu);
      v17 = StringCchCopyW(v35, 0x400u, v16 + 1);
      v18 = v17;
      if ( v17 < 0 )
      {
        CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v17);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_caa7cf28e9283147a4c859e60103ff52_Traceguids, v18);
        }
      }
      if ( pvarg.vt == 13 )
      {
        PropertyFromIUnknown = (struct IUnknown *)CTextTemplate::GetPropertyFromIUnknown(this, v35, pvarg.punkVal);
        if ( PropertyFromIUnknown )
        {
          pv = PropertyFromIUnknown;
          WString2::operator+=(psz, PropertyFromIUnknown);
          CSysFreeMe::~CSysFreeMe((CSysFreeMe *)&pv);
        }
      }
      else
      {
        if ( (pvarg.vt & 0xD) != 0 && (pvarg.vt & 0x2000) != 0 )
        {
          *(_QWORD *)rgIndices = 0;
          plLbound = 0;
          plUbound = 0;
          SafeArrayGetDim(pvarg.parray);
          SafeArrayGetLBound(pvarg.parray, 1u, &plLbound);
          SafeArrayGetUBound(pvarg.parray, 1u, &plUbound);
          WString2::operator+=(psz, L"{");
          v20 = plLbound;
          for ( i = plLbound <= plUbound; ; i = v20 <= v24 )
          {
            rgIndices[0] = v20;
            if ( !i )
              break;
            pv = 0;
            SafeArrayGetElement(pvarg.parray, rgIndices, &pv);
            v22 = CTextTemplate::GetPropertyFromIUnknown(this, v35, pv);
            if ( v22 )
            {
              v34 = v22;
              WString2::operator+=(psz, v22);
              CSysFreeMe::~CSysFreeMe((CSysFreeMe *)&v34);
            }
            v23 = rgIndices[0];
            v24 = plUbound;
            if ( rgIndices[0] < plUbound )
            {
              WString2::operator+=(psz, L", ");
              v23 = rgIndices[0];
              v24 = plUbound;
            }
            v20 = v23 + 1;
          }
          v25 = L"}";
        }
        else
        {
          v25 = L"<error>";
        }
        WString2::operator+=(psz, v25);
      }
      v15 = psz[0];
    }
  }
  else
  {
    v15 = L"<failed>";
  }
  v11 = SysAllocString(v15);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v32);
LABEL_38:
  WString2::DeleteString((WString2 *)psz, 1);
  return v11;
}

```

## disassembly

```asm
0x180038c20  push    rbp
0x180038c22  push    rbx
0x180038c23  push    rsi
0x180038c24  push    rdi
0x180038c25  push    r12
0x180038c27  push    r14
0x180038c29  push    r15
0x180038c2b  lea     rbp, [rsp-7D0h]
0x180038c33  sub     rsp, 8D0h
0x180038c3a  mov     rax, cs:__security_cookie
0x180038c41  xor     rax, rsp
0x180038c44  mov     [rbp+800h+var_40], rax
0x180038c4b  mov     r12, r8
0x180038c4e  mov     r14, rdx
0x180038c51  mov     r15, rcx
0x180038c54  lea     rax, unk_180070020
0x180038c5b  mov     [rbp+800h+psz], rax
0x180038c5f  mov     [rbp+800h+var_870], 0
0x180038c67  mov     [rbp+800h+var_868], 0
0x180038c6f  mov     eax, 32h ; '2'
0x180038c74  mov     [rbp+800h+var_860], rax
0x180038c78  mov     [rbp+800h+var_858], rax
0x180038c7c  lea     edx, [rax-4]; Ch
0x180038c7f  mov     rcx, r14; Str
0x180038c82  call    cs:__imp_wcschr
0x180038c88  mov     rbx, rax
0x180038c8b  test    rax, rax
0x180038c8e  jnz     short loc_180038C99
0x180038c90  lea     rcx, aError; "<error>"
0x180038c97  jmp     short loc_180038CCD
0x180038c99  sub     rbx, r14
0x180038c9c  sar     rbx, 1
0x180038c9f  lea     rdi, [rbx+1]
0x180038ca3  mov     eax, 2
0x180038ca8  mul     rdi
0x180038cab  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180038cb2  cmovb   rax, rcx
0x180038cb6  mov     rcx, rax; unsigned __int64
0x180038cb9  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180038cbe  mov     rsi, rax
0x180038cc1  test    rax, rax
0x180038cc4  jnz     short loc_180038CDB
0x180038cc6  lea     rcx, aFailed; "<failed>"
0x180038ccd  call    cs:__imp_SysAllocString
0x180038cd3  mov     rbx, rax
0x180038cd6  jmp     loc_180038FB1
0x180038cdb  mov     [rsp+900h+var_888], rsi
0x180038ce0  mov     [rbp+800h+var_880], 0
0x180038ce8  mov     r9, rbx; unsigned __int64
0x180038ceb  mov     r8, r14; unsigned __int16 *
0x180038cee  mov     rdx, rdi; unsigned __int64
0x180038cf1  mov     rcx, rsi; unsigned __int16 *
0x180038cf4  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180038cf9  mov     edi, eax
0x180038cfb  test    eax, eax
0x180038cfd  jns     short loc_180038D44
0x180038cff  mov     edx, eax; int
0x180038d01  lea     rcx, unk_18006A9C0; this
0x180038d08  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180038d0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180038d14  lea     rax, WPP_GLOBAL_Control
0x180038d1b  cmp     rcx, rax
0x180038d1e  jz      short loc_180038D44
0x180038d20  test    byte ptr [rcx+1Ch], 1
0x180038d24  jz      short loc_180038D44
0x180038d26  cmp     byte ptr [rcx+19h], 2
0x180038d2a  jb      short loc_180038D44
0x180038d2c  mov     edx, 0Bh
0x180038d31  mov     r9d, edi
0x180038d34  lea     r8, WPP_caa7cf28e9283147a4c859e60103ff52_Traceguids
0x180038d3b  mov     rcx, [rcx+10h]
0x180038d3f  call    WPP_SF_D
0x180038d44  xor     eax, eax
0x180038d46  mov     [rsi+rbx*2], ax
0x180038d4a  lea     rcx, [rsp+900h+pvarg]; pvarg
0x180038d4f  call    cs:__imp_VariantInit
0x180038d55  nop
0x180038d56  mov     rax, [r12]
0x180038d5a  mov     [rsp+900h+var_8D8], 0
0x180038d63  mov     [rsp+900h+var_8E0], 0
0x180038d6c  lea     r9, [rsp+900h+pvarg]
0x180038d71  xor     r8d, r8d
0x180038d74  mov     rdx, rsi
0x180038d77  mov     rcx, r12
0x180038d7a  mov     rax, [rax+20h]
0x180038d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d83  cmp     eax, 80041002h
0x180038d88  jnz     short loc_180038D96
0x180038d8a  lea     rcx, psz; "<unknown>"
0x180038d91  jmp     loc_180038F92
0x180038d96  test    eax, eax
0x180038d98  jns     short loc_180038DA6
0x180038d9a  lea     rcx, aFailed; "<failed>"
0x180038da1  jmp     loc_180038F92
0x180038da6  mov     eax, 1
0x180038dab  cmp     word ptr [rsp+900h+pvarg], ax
0x180038db0  jnz     short loc_180038DBE
0x180038db2  lea     rcx, aNull; "<null>"
0x180038db9  jmp     loc_180038F92
0x180038dbe  mov     edx, 2Eh ; '.'; Ch
0x180038dc3  mov     rcx, r14; Str
0x180038dc6  call    cs:__imp_wcschr
0x180038dcc  lea     r8, [rax+2]; unsigned __int16 *
0x180038dd0  mov     edx, 400h; unsigned __int64
0x180038dd5  lea     rcx, [rbp+800h+var_840]; unsigned __int16 *
0x180038dd9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180038dde  mov     ebx, eax
0x180038de0  test    eax, eax
0x180038de2  jns     short loc_180038E30
0x180038de4  mov     edx, eax; int
0x180038de6  lea     rcx, unk_18006A9C0; this
0x180038ded  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180038df2  mov     rcx, cs:WPP_GLOBAL_Control
0x180038df9  lea     rax, WPP_GLOBAL_Control
0x180038e00  mov     r14d, 1
0x180038e06  cmp     rcx, rax
0x180038e09  jz      short loc_180038E36
0x180038e0b  test    [rcx+1Ch], r14b
0x180038e0f  jz      short loc_180038E36
0x180038e11  cmp     byte ptr [rcx+19h], 2
0x180038e15  jb      short loc_180038E36
0x180038e17  lea     edx, [r14+0Bh]
0x180038e1b  mov     r9d, ebx
0x180038e1e  lea     r8, WPP_caa7cf28e9283147a4c859e60103ff52_Traceguids
0x180038e25  mov     rcx, [rcx+10h]
0x180038e29  call    WPP_SF_D
0x180038e2e  jmp     short loc_180038E36
0x180038e30  mov     r14d, 1
0x180038e36  movzx   eax, word ptr [rsp+900h+pvarg]
0x180038e3b  mov     edx, 0Dh
0x180038e40  cmp     ax, dx
0x180038e43  jnz     short loc_180038E80
0x180038e45  mov     r8, qword ptr [rsp+900h+pvarg+8]; struct IUnknown *
0x180038e4a  lea     rdx, [rbp+800h+var_840]; unsigned __int16 *
0x180038e4e  mov     rcx, r15; this
0x180038e51  call    ?GetPropertyFromIUnknown@CTextTemplate@@AEAAPEAGPEAGPEAUIUnknown@@@Z; CTextTemplate::GetPropertyFromIUnknown(ushort *,IUnknown *)
0x180038e56  test    rax, rax
0x180038e59  jz      loc_180038F8E
0x180038e5f  mov     [rsp+900h+pv], rax
0x180038e64  mov     rdx, rax
0x180038e67  lea     rcx, [rbp+800h+psz]
0x180038e6b  call    ??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x180038e70  nop
0x180038e71  lea     rcx, [rsp+900h+pv]; this
0x180038e76  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x180038e7b  jmp     loc_180038F8E
0x180038e80  test    dl, al
0x180038e82  setnz   cl
0x180038e85  bt      ax, dx
0x180038e89  setb    al
0x180038e8c  test    al, cl
0x180038e8e  jz      loc_180038F7E
0x180038e94  mov     qword ptr [rsp+900h+rgIndices], 0
0x180038e9d  mov     [rsp+900h+plLbound], 0
0x180038ea5  mov     [rsp+900h+plUbound], 0
0x180038ead  mov     rcx, qword ptr [rsp+900h+pvarg+8]; psa
0x180038eb2  call    cs:__imp_SafeArrayGetDim
0x180038eb8  lea     r8, [rsp+900h+plLbound]; plLbound
0x180038ebd  mov     edx, r14d; nDim
0x180038ec0  mov     rcx, qword ptr [rsp+900h+pvarg+8]; psa
0x180038ec5  call    cs:__imp_SafeArrayGetLBound
0x180038ecb  lea     r8, [rsp+900h+plUbound]; plUbound
0x180038ed0  mov     edx, r14d; nDim
0x180038ed3  mov     rcx, qword ptr [rsp+900h+pvarg+8]; psa
0x180038ed8  call    cs:__imp_SafeArrayGetUBound
0x180038ede  lea     rdx, asc_18004B7F0; "{"
0x180038ee5  lea     rcx, [rbp+800h+psz]
0x180038ee9  call    ??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x180038eee  mov     eax, [rsp+900h+plLbound]
0x180038ef2  cmp     eax, [rsp+900h+plUbound]
0x180038ef6  jmp     short loc_180038F6F
0x180038ef8  mov     [rsp+900h+pv], 0
0x180038f01  lea     r8, [rsp+900h+pv]; pv
0x180038f06  lea     rdx, [rsp+900h+rgIndices]; rgIndices
0x180038f0b  mov     rcx, qword ptr [rsp+900h+pvarg+8]; psa
0x180038f10  call    cs:__imp_SafeArrayGetElement
0x180038f16  mov     r8, [rsp+900h+pv]; struct IUnknown *
0x180038f1b  lea     rdx, [rbp+800h+var_840]; unsigned __int16 *
0x180038f1f  mov     rcx, r15; this
0x180038f22  call    ?GetPropertyFromIUnknown@CTextTemplate@@AEAAPEAGPEAGPEAUIUnknown@@@Z; CTextTemplate::GetPropertyFromIUnknown(ushort *,IUnknown *)
0x180038f27  test    rax, rax
0x180038f2a  jz      short loc_180038F46
0x180038f2c  mov     [rbp+800h+var_850], rax
0x180038f30  mov     rdx, rax
0x180038f33  lea     rcx, [rbp+800h+psz]
0x180038f37  call    ??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x180038f3c  nop
0x180038f3d  lea     rcx, [rbp+800h+var_850]; this
0x180038f41  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x180038f46  mov     eax, [rsp+900h+rgIndices]
0x180038f4a  mov     ecx, [rsp+900h+plUbound]
0x180038f4e  cmp     eax, ecx
0x180038f50  jge     short loc_180038F6A
0x180038f52  lea     rdx, asc_18004B1DC; ", "
0x180038f59  lea     rcx, [rbp+800h+psz]
0x180038f5d  call    ??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x180038f62  mov     eax, [rsp+900h+rgIndices]
0x180038f66  mov     ecx, [rsp+900h+plUbound]
0x180038f6a  add     eax, r14d
0x180038f6d  cmp     eax, ecx
0x180038f6f  mov     [rsp+900h+rgIndices], eax
0x180038f73  jle     short loc_180038EF8
0x180038f75  lea     rdx, asc_18004B7F4; "}"
0x180038f7c  jmp     short loc_180038F85
0x180038f7e  lea     rdx, aError; "<error>"
0x180038f85  lea     rcx, [rbp+800h+psz]
0x180038f89  call    ??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x180038f8e  mov     rcx, [rbp+800h+psz]; psz
0x180038f92  call    cs:__imp_SysAllocString
0x180038f98  mov     rbx, rax
0x180038f9b  lea     rcx, [rsp+900h+pvarg]; this
0x180038fa0  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180038fa5  nop
0x180038fa6  lea     rcx, [rsp+900h+var_888]
0x180038fab  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x180038fb0  nop
0x180038fb1  mov     dl, 1; bool
0x180038fb3  lea     rcx, [rbp+800h+psz]; this
0x180038fb7  call    ?DeleteString@WString2@@AEAAX_N@Z; WString2::DeleteString(bool)
0x180038fbc  mov     rax, rbx
0x180038fbf  mov     rcx, [rbp+800h+var_40]
0x180038fc6  xor     rcx, rsp; StackCookie
0x180038fc9  call    __security_check_cookie
0x180038fce  add     rsp, 8D0h
0x180038fd5  pop     r15
0x180038fd7  pop     r14
0x180038fd9  pop     r12
0x180038fdb  pop     rdi
0x180038fdc  pop     rsi
0x180038fdd  pop     rbx
0x180038fde  pop     rbp
0x180038fdf  retn
```
