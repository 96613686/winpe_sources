# CUpdateSession::CreateUpdateDownloader(IUpdateDownloader * *)

- ea: `0x18003aab0`
- end: `0x18003af2f`
- name: `?CreateUpdateDownloader@CUpdateSession@@UEAAJPEAPEAUIUpdateDownloader@@@Z`
- size: `1151`
- prototype: `__int64 __fastcall(CUpdateSession *__hidden this, struct IUpdateDownloader **)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006ac4`
- `0x18003aab0`
- `0x18003d1c0`
- `0x18003da48`
- `0x18008d284`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003ae19`
- `OLEAUT32!__imp_VariantInit` at `0x18003ae19`
- `OLEAUT32!__imp_VariantClear` at `0x18003ae7c`
- `OLEAUT32!__imp_VariantClear` at `0x18003aea3`
- `OLEAUT32!__imp_VariantClear` at `0x18003ae7c`
- `OLEAUT32!__imp_VariantClear` at `0x18003aea3`

## string_xrefs

- `0x18003ab5c`: `C:\__w\1\s\src\Client\comapi\Session.cpp`
- `0x18003abfc`: `C:\__w\1\s\src\Client\comapi\Session.cpp`
- `0x18003ac48`: `C:\__w\1\s\src\Client\comapi\Session.cpp`
- `0x18003ac92`: `C:\__w\1\s\src\Client\comapi\Session.cpp`
- `0x18003ada1`: `C:\__w\1\s\src\Client\comapi\Session.cpp`
- `0x18003ae02`: `C:\__w\1\s\src\Client\comapi\Session.cpp`
- `0x18003ae67`: `C:\__w\1\s\src\Client\comapi\Session.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall CUpdateSession::CreateUpdateDownloader(
        CUpdateSession *this,
        struct IUpdateDownloader **a2,
        void *a3)
{
  int v5; // ebx
  __int64 v6; // rdx
  char *v7; // r13
  int v8; // eax
  _QWORD *v9; // rbx
  _QWORD *v10; // rdi
  unsigned int v11; // r15d
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v17; // rdx
  int v18; // eax
  int v19; // eax
  __int64 (__fastcall ***v20)(_QWORD, GUID *, _QWORD *); // rcx
  struct IUpdateDownloader *v21; // rax
  VARIANTARG v23; // [rsp+20h] [rbp-60h] BYREF
  __int64 (__fastcall ***v24)(_QWORD, GUID *, _QWORD *); // [rsp+40h] [rbp-40h] BYREF
  __int64 v25; // [rsp+48h] [rbp-38h] BYREF
  _QWORD *v26; // [rsp+50h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v24 = 0;
  v25 = 0;
  if ( !a2 )
  {
    v5 = -2147467261;
    v6 = 199;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
      (const char *)(unsigned int)v5,
      *(int *)&v23.vt);
LABEL_40:
    v20 = v24;
    goto LABEL_44;
  }
  *a2 = 0;
  v5 = SecurityCheck(1, (__int64)a2, a3);
  if ( v5 < 0 )
  {
    v6 = 204;
    goto LABEL_31;
  }
  v7 = (char *)this - 48;
  if ( v24 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v24)[2])(v24);
  v26 = 0;
  v8 = ATL::CComObject<CUpdateDownloader>::CreateInstance(&v26);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
      (const char *)(unsigned int)v8,
      *(int *)&v23.vt);
    if ( v26 )
      (*(void (__fastcall **)(_QWORD *))(v26[1] + 16LL))(v26 + 1);
    goto LABEL_20;
  }
  v9 = v26;
  v10 = v26 + 1;
  (*(void (__fastcall **)(_QWORD *))(v26[1] + 8LL))(v26 + 1);
  v11 = *((_DWORD *)v7 + 8);
  v12 = v9[16];
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v12 + 24) + 16LL))(v12 + 24);
  v9[16] = v7;
  (*(void (__fastcall **)(char *))(*((_QWORD *)v7 + 3) + 8LL))(v7 + 24);
  v13 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(v9[3] + 64LL))(v9 + 3, *((_QWORD *)v7 + 15));
  v5 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
      (const char *)(unsigned int)v13,
      *(int *)&v23.vt);
    (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
LABEL_20:
    v6 = 205;
    goto LABEL_31;
  }
  if ( v11 != -1 )
  {
    v14 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v10 + 24LL))(v10, v11);
    v5 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
        (const char *)(unsigned int)v14,
        *(int *)&v23.vt);
      (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
      goto LABEL_20;
    }
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD *))*v10)(
          v10,
          &GUID_68f1c6f9_7ecc_4666_a464_247fe12496c3,
          &v24);
  v5 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
      (const char *)(unsigned int)v15,
      *(int *)&v23.vt);
    (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
    goto LABEL_20;
  }
  (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
  v16 = v24;
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  v5 = (**v16)(v16, &GUID_829a2abf_33f9_4e74_aa7a_395a1e77dc5d, &v25);
  if ( v5 < 0 )
  {
    v6 = 206;
    goto LABEL_31;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v25 + 168LL))(v25, 1, *((_QWORD *)this + 34));
  if ( v5 < 0 )
  {
    v6 = 207;
    goto LABEL_31;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v25 + 168LL))(v25, 2, *((_QWORD *)this + 35));
  if ( v5 < 0 )
  {
    v6 = 208;
    goto LABEL_31;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v25 + 168LL))(v25, 3, *((_QWORD *)this + 36));
  if ( v5 < 0 )
  {
    v6 = 209;
    goto LABEL_31;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::GetImpl'::`2'::impl,
                          v17)
    && *((_BYTE *)this + 296) )
  {
    v26 = 0;
    v18 = (**v24)(v24, &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b, &v26);
    v5 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD8,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
        (const char *)(unsigned int)v18,
        *(int *)&v23.vt);
      goto LABEL_38;
    }
    VariantInit(&pvarg);
    pvarg.vt = 11;
    pvarg.iVal = -1;
    v23 = pvarg;
    v19 = (*(__int64 (__fastcall **)(_QWORD *, __int64, VARIANTARG *))(*v26 + 32LL))(v26, 196626, &v23);
    v5 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDF,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
        (const char *)(unsigned int)v19,
        *(int *)&v23.vt);
      VariantClear(&pvarg);
LABEL_38:
      if ( v26 )
        (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
      goto LABEL_40;
    }
    VariantClear(&pvarg);
    if ( v26 )
      (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
  }
  v21 = (struct IUpdateDownloader *)v24;
  v20 = 0;
  v24 = 0;
  *a2 = v21;
  v5 = 0;
LABEL_44:
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
    v20 = v24;
  }
  if ( v20 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v20)[2])(v20);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003aab0  mov     [rsp-28h+arg_10], rbx
0x18003aab5  mov     [rsp-28h+arg_18], rsi
0x18003aaba  push    rbp
0x18003aabb  push    rdi
0x18003aabc  push    r13
0x18003aabe  push    r14
0x18003aac0  push    r15
0x18003aac2  mov     rbp, rsp
0x18003aac5  sub     rsp, 80h
0x18003aacc  mov     rax, cs:__security_cookie
0x18003aad3  xor     rax, rsp
0x18003aad6  mov     [rbp+var_10], rax
0x18003aada  mov     r14, rdx
0x18003aadd  mov     rsi, rcx
0x18003aae0  mov     [rbp+var_40], 0
0x18003aae8  mov     [rbp+var_38], 0
0x18003aaf0  test    rdx, rdx
0x18003aaf3  jnz     short loc_18003AB04
0x18003aaf5  mov     ebx, 80004003h
0x18003aafa  mov     edx, 0C7h
0x18003aaff  jmp     loc_18003AD9A
0x18003ab04  mov     qword ptr [rdx], 0
0x18003ab0b  mov     ecx, 1; unsigned int
0x18003ab10  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x18003ab15  mov     ebx, eax
0x18003ab17  test    eax, eax
0x18003ab19  jns     short loc_18003AB25
0x18003ab1b  mov     edx, 0CCh
0x18003ab20  jmp     loc_18003AD9A
0x18003ab25  lea     r13, [rsi-30h]
0x18003ab29  mov     rcx, [rbp+var_40]
0x18003ab2d  test    rcx, rcx
0x18003ab30  jz      short loc_18003AB3E
0x18003ab32  mov     rax, [rcx]
0x18003ab35  mov     rax, [rax+10h]
0x18003ab39  call    _guard_dispatch_icall
0x18003ab3e  mov     [rbp+var_30], 0
0x18003ab46  lea     rcx, [rbp+var_30]
0x18003ab4a  call    ?CreateInstance@?$CComObject@VCUpdateDownloader@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CUpdateDownloader>::CreateInstance(ATL::CComObject<CUpdateDownloader> * *)
0x18003ab4f  mov     ebx, eax
0x18003ab51  test    eax, eax
0x18003ab53  jns     short loc_18003AB8D
0x18003ab55  mov     rcx, [rbp+28h]; this
0x18003ab59  mov     r9d, eax; char *
0x18003ab5c  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003ab63  mov     edx, 1Fh; void *
0x18003ab68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ab6d  nop
0x18003ab6e  mov     rax, [rbp+var_30]
0x18003ab72  test    rax, rax
0x18003ab75  jz      short loc_18003AB88
0x18003ab77  lea     rcx, [rax+8]
0x18003ab7b  mov     rax, [rcx]
0x18003ab7e  mov     rax, [rax+10h]
0x18003ab82  call    _guard_dispatch_icall
0x18003ab87  nop
0x18003ab88  jmp     loc_18003ACB4
0x18003ab8d  mov     rbx, [rbp+var_30]
0x18003ab91  lea     rdi, [rbx+8]
0x18003ab95  mov     rax, [rdi]
0x18003ab98  mov     rcx, rdi
0x18003ab9b  mov     rax, [rax+8]
0x18003ab9f  call    _guard_dispatch_icall
0x18003aba4  mov     r15d, [r13+20h]
0x18003aba8  mov     rcx, [rbx+80h]
0x18003abaf  test    rcx, rcx
0x18003abb2  jz      short loc_18003ABC4
0x18003abb4  add     rcx, 18h
0x18003abb8  mov     rax, [rcx]
0x18003abbb  mov     rax, [rax+10h]
0x18003abbf  call    _guard_dispatch_icall
0x18003abc4  mov     [rbx+80h], r13
0x18003abcb  lea     rcx, [r13+18h]
0x18003abcf  mov     rax, [rcx]
0x18003abd2  mov     rax, [rax+8]
0x18003abd6  call    _guard_dispatch_icall
0x18003abdb  lea     rcx, [rbx+18h]
0x18003abdf  mov     rax, [rcx]
0x18003abe2  mov     rdx, [r13+78h]
0x18003abe6  mov     rax, [rax+40h]
0x18003abea  call    _guard_dispatch_icall
0x18003abef  mov     ebx, eax
0x18003abf1  test    eax, eax
0x18003abf3  jns     short loc_18003AC23
0x18003abf5  mov     rcx, [rbp+28h]; this
0x18003abf9  mov     r9d, eax; char *
0x18003abfc  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003ac03  mov     edx, 26h ; '&'; void *
0x18003ac08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ac0d  nop
0x18003ac0e  mov     rax, [rdi]
0x18003ac11  mov     rcx, rdi
0x18003ac14  mov     rax, [rax+10h]
0x18003ac18  call    _guard_dispatch_icall
0x18003ac1d  nop
0x18003ac1e  jmp     loc_18003ACB4
0x18003ac23  cmp     r15d, 0FFFFFFFFh
0x18003ac27  jz      short loc_18003AC6C
0x18003ac29  mov     rax, [rdi]
0x18003ac2c  mov     edx, r15d
0x18003ac2f  mov     rcx, rdi
0x18003ac32  mov     rax, [rax+18h]
0x18003ac36  call    _guard_dispatch_icall
0x18003ac3b  mov     ebx, eax
0x18003ac3d  test    eax, eax
0x18003ac3f  jns     short loc_18003AC6C
0x18003ac41  mov     rcx, [rbp+28h]; this
0x18003ac45  mov     r9d, eax; char *
0x18003ac48  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003ac4f  mov     edx, 2Ah ; '*'; void *
0x18003ac54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ac59  nop
0x18003ac5a  mov     rax, [rdi]
0x18003ac5d  mov     rcx, rdi
0x18003ac60  mov     rax, [rax+10h]
0x18003ac64  call    _guard_dispatch_icall
0x18003ac69  nop
0x18003ac6a  jmp     short loc_18003ACB4
0x18003ac6c  mov     rax, [rdi]
0x18003ac6f  lea     r8, [rbp+var_40]
0x18003ac73  lea     rdx, _GUID_68f1c6f9_7ecc_4666_a464_247fe12496c3
0x18003ac7a  mov     rcx, rdi
0x18003ac7d  mov     rax, [rax]
0x18003ac80  call    _guard_dispatch_icall
0x18003ac85  mov     ebx, eax
0x18003ac87  test    eax, eax
0x18003ac89  jns     short loc_18003ACBE
0x18003ac8b  mov     rcx, [rbp+28h]; this
0x18003ac8f  mov     r9d, eax; char *
0x18003ac92  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003ac99  mov     edx, 2Dh ; '-'; void *
0x18003ac9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aca3  nop
0x18003aca4  mov     rax, [rdi]
0x18003aca7  mov     rcx, rdi
0x18003acaa  mov     rax, [rax+10h]
0x18003acae  call    _guard_dispatch_icall
0x18003acb3  nop
0x18003acb4  mov     edx, 0CDh
0x18003acb9  jmp     loc_18003AD9A
0x18003acbe  mov     rax, [rdi]
0x18003acc1  mov     rcx, rdi
0x18003acc4  mov     rax, [rax+10h]
0x18003acc8  call    _guard_dispatch_icall
0x18003accd  nop
0x18003acce  mov     rbx, [rbp+var_40]
0x18003acd2  mov     rcx, [rbp+var_38]
0x18003acd6  test    rcx, rcx
0x18003acd9  jz      short loc_18003ACEF
0x18003acdb  mov     rax, [rcx]
0x18003acde  mov     rax, [rax+10h]
0x18003ace2  call    _guard_dispatch_icall
0x18003ace7  mov     [rbp+var_38], 0
0x18003acef  mov     rax, [rbx]
0x18003acf2  lea     r8, [rbp+var_38]
0x18003acf6  lea     rdx, _GUID_829a2abf_33f9_4e74_aa7a_395a1e77dc5d
0x18003acfd  mov     rcx, rbx
0x18003ad00  mov     rax, [rax]
0x18003ad03  call    _guard_dispatch_icall
0x18003ad08  mov     ebx, eax
0x18003ad0a  test    eax, eax
0x18003ad0c  jns     short loc_18003AD18
0x18003ad0e  mov     edx, 0CEh
0x18003ad13  jmp     loc_18003AD9A
0x18003ad18  mov     rcx, [rbp+var_38]
0x18003ad1c  mov     rax, [rcx]
0x18003ad1f  mov     r8, [rsi+110h]
0x18003ad26  mov     edx, 1
0x18003ad2b  mov     rax, [rax+0A8h]
0x18003ad32  call    _guard_dispatch_icall
0x18003ad37  mov     ebx, eax
0x18003ad39  test    eax, eax
0x18003ad3b  jns     short loc_18003AD44
0x18003ad3d  mov     edx, 0CFh
0x18003ad42  jmp     short loc_18003AD9A
0x18003ad44  mov     rcx, [rbp+var_38]
0x18003ad48  mov     rax, [rcx]
0x18003ad4b  mov     r8, [rsi+118h]
0x18003ad52  mov     edx, 2
0x18003ad57  mov     rax, [rax+0A8h]
0x18003ad5e  call    _guard_dispatch_icall
0x18003ad63  mov     ebx, eax
0x18003ad65  test    eax, eax
0x18003ad67  jns     short loc_18003AD70
0x18003ad69  mov     edx, 0D0h
0x18003ad6e  jmp     short loc_18003AD9A
0x18003ad70  mov     rcx, [rbp+var_38]
0x18003ad74  mov     rax, [rcx]
0x18003ad77  mov     r8, [rsi+120h]
0x18003ad7e  mov     edx, 3
0x18003ad83  mov     rax, [rax+0A8h]
0x18003ad8a  call    _guard_dispatch_icall
0x18003ad8f  mov     ebx, eax
0x18003ad91  test    eax, eax
0x18003ad93  jns     short loc_18003ADB2
0x18003ad95  mov     edx, 0D1h; void *
0x18003ad9a  mov     rcx, [rbp+28h]; this
0x18003ad9e  mov     r9d, ebx; char *
0x18003ada1  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003ada8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003adad  jmp     loc_18003AE99
0x18003adb2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_ModernStandby@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_ModernStandby@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::GetImpl(void)'::`2'::impl
0x18003adb9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_ModernStandby@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::__private_IsEnabled(void)
0x18003adbe  test    al, al
0x18003adc0  jz      loc_18003AEC0
0x18003adc6  cmp     byte ptr [rsi+128h], 0
0x18003adcd  jz      loc_18003AEC0
0x18003add3  mov     [rbp+var_30], 0
0x18003addb  mov     rcx, [rbp+var_40]
0x18003addf  mov     rax, [rcx]
0x18003ade2  lea     r8, [rbp+var_30]
0x18003ade6  lea     rdx, _GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b
0x18003aded  mov     rax, [rax]
0x18003adf0  call    _guard_dispatch_icall
0x18003adf5  mov     ebx, eax
0x18003adf7  test    eax, eax
0x18003adf9  jns     short loc_18003AE15
0x18003adfb  mov     rcx, [rbp+28h]; this
0x18003adff  mov     r9d, eax; char *
0x18003ae02  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003ae09  mov     edx, 0D8h; void *
0x18003ae0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ae13  jmp     short loc_18003AE83
0x18003ae15  lea     rcx, [rbp+pvarg]; pvarg
0x18003ae19  call    cs:__imp_VariantInit
0x18003ae1f  mov     eax, 0Bh
0x18003ae24  mov     word ptr [rbp+pvarg], ax
0x18003ae28  or      eax, 0FFFFFFFFh
0x18003ae2b  mov     word ptr [rbp+pvarg+8], ax
0x18003ae2f  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18003ae33  movaps  [rbp+var_60], xmm0
0x18003ae37  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18003ae3c  movsd   [rbp+var_50], xmm1
0x18003ae41  mov     rcx, [rbp+var_30]
0x18003ae45  mov     rax, [rcx]
0x18003ae48  lea     r8, [rbp+var_60]
0x18003ae4c  mov     edx, 30012h
0x18003ae51  mov     rax, [rax+20h]
0x18003ae55  call    _guard_dispatch_icall
0x18003ae5a  mov     ebx, eax
0x18003ae5c  test    eax, eax
0x18003ae5e  jns     short loc_18003AE9F
0x18003ae60  mov     rcx, [rbp+28h]; this
0x18003ae64  mov     r9d, eax; char *
0x18003ae67  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003ae6e  mov     edx, 0DFh; void *
0x18003ae73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ae78  lea     rcx, [rbp+pvarg]; pvarg
0x18003ae7c  call    cs:__imp_VariantClear
0x18003ae82  nop
0x18003ae83  mov     rcx, [rbp+var_30]
0x18003ae87  test    rcx, rcx
0x18003ae8a  jz      short loc_18003AE99
0x18003ae8c  mov     rax, [rcx]
0x18003ae8f  mov     rax, [rax+10h]
0x18003ae93  call    _guard_dispatch_icall
0x18003ae98  nop
0x18003ae99  mov     rcx, [rbp+var_40]
0x18003ae9d  jmp     short loc_18003AECF
0x18003ae9f  lea     rcx, [rbp+pvarg]; pvarg
0x18003aea3  call    cs:__imp_VariantClear
0x18003aea9  nop
0x18003aeaa  mov     rcx, [rbp+var_30]
0x18003aeae  test    rcx, rcx
0x18003aeb1  jz      short loc_18003AEC0
0x18003aeb3  mov     rax, [rcx]
0x18003aeb6  mov     rax, [rax+10h]
0x18003aeba  call    _guard_dispatch_icall
0x18003aebf  nop
0x18003aec0  mov     rax, [rbp+var_40]
0x18003aec4  xor     ecx, ecx
0x18003aec6  mov     [rbp+var_40], rcx
0x18003aeca  mov     [r14], rax
0x18003aecd  xor     ebx, ebx
0x18003aecf  mov     rdx, [rbp+var_38]
0x18003aed3  test    rdx, rdx
0x18003aed6  jz      short loc_18003AEF3
0x18003aed8  mov     rax, [rdx]
0x18003aedb  mov     rcx, rdx
0x18003aede  mov     rax, [rax+10h]
0x18003aee2  call    _guard_dispatch_icall
0x18003aee7  mov     [rbp+var_38], 0
0x18003aeef  mov     rcx, [rbp+var_40]
0x18003aef3  test    rcx, rcx
0x18003aef6  jz      short loc_18003AF05
0x18003aef8  mov     rdx, [rcx]
0x18003aefb  mov     rax, [rdx+10h]
0x18003aeff  call    _guard_dispatch_icall
0x18003af04  nop
0x18003af05  mov     eax, ebx
0x18003af07  mov     rcx, [rbp+var_10]
0x18003af0b  xor     rcx, rsp; StackCookie
0x18003af0e  call    __security_check_cookie
0x18003af13  lea     r11, [rsp+80h+var_s0]
0x18003af1b  mov     rbx, [r11+40h]
0x18003af1f  mov     rsi, [r11+48h]
0x18003af23  mov     rsp, r11
0x18003af26  pop     r15
0x18003af28  pop     r14
0x18003af2a  pop     r13
  ... truncated ...
```
