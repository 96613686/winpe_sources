# ParseBundlePrereq

- ea: `0x1800392ec`
- end: `0x1800396fc`
- name: `ParseBundlePrereq`
- size: `1040`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180039704`

## callees

- `0x180003950`
- `0x18000a9b4`
- `0x180038f2c`
- `0x180039040`
- `0x1800392ec`
- `0x180041fc4`
- `0x180042114`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800394fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180039633`
- `OLEAUT32!__imp_SysFreeString` at `0x1800394fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180039633`

## string_xrefs

- `0x18003953a`: `UpdateIdentity`

## pseudocode

```c
// Hidden C++ exception states: #wind=47
__int64 __fastcall ParseBundlePrereq(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        unsigned int *a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v6; // r14d
  int v7; // r12d
  int v8; // r15d
  unsigned int v9; // r8d
  __int64 v10; // rcx
  __int64 *v11; // rax
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rdi
  int v13; // esi
  __int64 v14; // rdx
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, __int64 *); // rdi
  int v17; // eax
  int v18; // r8d
  int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, _QWORD, __int64 *); // rdi
  int v23; // eax
  __int64 v24; // rbx
  __int64 (__fastcall *v25)(__int64, BSTR *); // rdi
  int v26; // eax
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned int v29; // ebx
  __int64 v30; // r8
  __int64 v31; // r9
  int v32; // edx
  __int64 v34; // rdx
  __int64 v35; // r9
  int v36; // [rsp+20h] [rbp-89h]
  unsigned int v37; // [rsp+20h] [rbp-89h]
  int v38; // [rsp+40h] [rbp-69h]
  unsigned int v39; // [rsp+44h] [rbp-65h]
  __int128 v40; // [rsp+48h] [rbp-61h] BYREF
  __int128 v41; // [rsp+58h] [rbp-51h]
  __int64 v42; // [rsp+68h] [rbp-41h]
  __int64 *v43; // [rsp+70h] [rbp-39h]
  __int64 v44; // [rsp+78h] [rbp-31h]
  __int64 v45; // [rsp+80h] [rbp-29h]
  unsigned int v46; // [rsp+88h] [rbp-21h] BYREF
  __int64 v47; // [rsp+90h] [rbp-19h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-11h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v50; // [rsp+A8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v42 = a4;
  v6 = 0;
  v50 = 0;
  v41 = 0;
  *(_QWORD *)((char *)&v41 + 4) = 0;
  v40 = 0u;
  v47 = 0;
  v7 = 0;
  v8 = 0;
  v38 = 0;
  v46 = 0;
  bstrString = 0;
  v39 = *a2;
  v9 = *a2;
  v49 = 0;
  v44 = a2[7];
  v10 = a2[10];
  v45 = v10;
  *(_QWORD *)(v44 + a3) = 0;
  *(_DWORD *)(v10 + a3) = 0;
  LODWORD(v41) = v9 != 0 ? 24 : 28;
  v11 = &qword_180075860;
  if ( !v9 )
    v11 = &qword_1800758B0;
  v43 = v11;
  v12 = **a1;
  if ( v49 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    v49 = 0;
  }
  v13 = v12(a1, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60, &v49);
  if ( v13 < 0 )
  {
    v14 = 974;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
      (const char *)(unsigned int)v13,
      v36);
LABEL_54:
    v29 = v13;
    goto LABEL_38;
  }
  v15 = v49;
  v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v49 + 96LL);
  if ( v50 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    v50 = 0;
  }
  v13 = v16(v15, &v50);
  if ( v13 < 0 )
  {
    v14 = 976;
    goto LABEL_11;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v50 + 64LL))(v50, &v46);
  v19 = v17;
  v13 = 1;
  if ( v17 == 1 )
    goto LABEL_54;
  if ( !v46 )
  {
    if ( v17 >= 0 )
    {
LABEL_53:
      v13 = v19;
      goto LABEL_54;
    }
    v20 = 981;
LABEL_52:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
      (const char *)(unsigned int)v19,
      v36);
    goto LABEL_53;
  }
  if ( v17 < 0 )
  {
    v20 = 982;
    goto LABEL_52;
  }
  v19 = CDSArrayBuilder::put_MinimumSize((CDSArrayBuilder *)&v40, v46, v18);
  if ( v19 < 0 )
  {
    v20 = 984;
    goto LABEL_52;
  }
  if ( (int)v46 > 0 )
  {
    while ( 1 )
    {
      v21 = v50;
      v22 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v50 + 56LL);
      if ( v47 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
        v47 = 0;
      }
      v23 = v22(v21, v6, &v47);
      v19 = v23;
      if ( v23 < 0 )
        break;
      if ( v23 == 1 )
        goto LABEL_37;
      v24 = v47;
      v25 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v47 + 328LL);
      SysFreeString(bstrString);
      bstrString = 0;
      v26 = v25(v24, &bstrString);
      v29 = v26;
      if ( v26 != 1 )
      {
        if ( !bstrString )
        {
          v29 = -2145124338;
          v35 = 2149842958LL;
          v34 = 1002;
          goto LABEL_48;
        }
        if ( v26 < 0 )
        {
          v34 = 1003;
LABEL_47:
          v35 = (unsigned int)v26;
LABEL_48:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v34,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
            (const char *)v35,
            v36);
          goto LABEL_38;
        }
        if ( AsciiStringCompareI(bstrString, L"UpdateIdentity", v27, v28, v36) )
        {
          if ( !AsciiStringCompareI(bstrString, L"AtLeastOne", v30, v31, v37) )
          {
            v36 = v7;
            v26 = ParseBundlePrereqAloGroup(v47, v39, &v40, v43);
            v29 = v26;
            if ( v26 < 0 )
            {
              v34 = 1013;
              goto LABEL_47;
            }
            v8 = v38;
          }
        }
        else
        {
          v36 = v7;
          v26 = ParseBundlePrereqIdentity(v47, v39, &v40, v43);
          v29 = v26;
          if ( v26 < 0 )
          {
            v34 = 1008;
            goto LABEL_47;
          }
          v38 = ++v8;
        }
        ++v7;
      }
      if ( (int)++v6 >= (int)v46 )
        goto LABEL_36;
    }
    v20 = 990;
    goto LABEL_52;
  }
LABEL_36:
  *(_QWORD *)(v44 + a3) = *((_QWORD *)&v40 + 1);
  *(_DWORD *)(v45 + a3) = DWORD2(v41);
  *((_QWORD *)&v40 + 1) = 0;
  *(_QWORD *)((char *)&v41 + 4) = 0;
LABEL_37:
  v29 = 0;
LABEL_38:
  if ( v49 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    v49 = 0;
  }
  SysFreeString(bstrString);
  bstrString = 0;
  if ( v47 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
  }
  CDSArrayBuilder::~CDSArrayBuilder((CDSArrayBuilder *)&v40, v32);
  if ( v50 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  return v29;
}

```

## disassembly

```asm
0x1800392ec  push    rbp
0x1800392ee  push    rbx
0x1800392ef  push    rsi
0x1800392f0  push    rdi
0x1800392f1  push    r12
0x1800392f3  push    r13
0x1800392f5  push    r14
0x1800392f7  push    r15
0x1800392f9  lea     rbp, [rsp-1Fh]
0x1800392fe  sub     rsp, 0C8h
0x180039305  mov     rax, cs:__security_cookie
0x18003930c  xor     rax, rsp
0x18003930f  mov     [rbp+57h+var_50], rax
0x180039313  mov     [rbp+57h+var_98], r9
0x180039317  mov     r13, r8
0x18003931a  mov     rbx, rcx
0x18003931d  xor     r14d, r14d
0x180039320  mov     [rbp+57h+var_58], r14
0x180039324  xorps   xmm0, xmm0
0x180039327  movups  [rbp+57h+var_B8], xmm0
0x18003932b  movups  [rbp+57h+var_A8], xmm0
0x18003932f  mov     qword ptr [rbp+57h+var_A8+4], r14
0x180039333  mov     qword ptr [rbp+57h+var_B8+8], r14
0x180039337  mov     qword ptr [rbp+57h+var_B8], r14
0x18003933b  mov     [rbp+57h+var_70], r14
0x18003933f  mov     r12d, r14d
0x180039342  mov     r15d, r14d
0x180039345  mov     [rbp+57h+var_C0], r14d
0x180039349  mov     [rbp+57h+var_78], r14d
0x18003934d  mov     [rbp+57h+bstrString], r14
0x180039351  mov     r8d, [rdx]
0x180039354  mov     [rbp+57h+var_BC], r8d
0x180039358  mov     [rbp+57h+var_60], r14
0x18003935c  mov     eax, [rdx+1Ch]
0x18003935f  mov     [rbp+57h+var_88], rax
0x180039363  mov     ecx, [rdx+28h]
0x180039366  mov     [rbp+57h+var_80], rcx
0x18003936a  mov     [rax+r13], r14
0x18003936e  mov     [rcx+r13], r14d
0x180039372  mov     eax, r8d
0x180039375  neg     eax
0x180039377  sbb     ecx, ecx
0x180039379  and     ecx, 0FFFFFFFCh
0x18003937c  add     ecx, 1Ch
0x18003937f  mov     dword ptr [rbp+57h+var_A8], ecx
0x180039382  lea     rcx, qword_1800758B0
0x180039389  lea     rax, qword_180075860
0x180039390  test    r8d, r8d
0x180039393  cmovz   rax, rcx
0x180039397  mov     [rbp+57h+var_90], rax
0x18003939b  mov     rax, [rbx]
0x18003939e  mov     rdi, [rax]
0x1800393a1  mov     rcx, [rbp+57h+var_60]
0x1800393a5  test    rcx, rcx
0x1800393a8  jz      short loc_1800393BA
0x1800393aa  mov     rax, [rcx]
0x1800393ad  mov     rax, [rax+10h]
0x1800393b1  call    _guard_dispatch_icall
0x1800393b6  mov     [rbp+57h+var_60], r14
0x1800393ba  lea     r8, [rbp+57h+var_60]
0x1800393be  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x1800393c5  mov     rcx, rbx
0x1800393c8  mov     rax, rdi
0x1800393cb  call    _guard_dispatch_icall
0x1800393d0  mov     esi, eax
0x1800393d2  test    eax, eax
0x1800393d4  jns     short loc_1800393DD
0x1800393d6  mov     edx, 3CEh
0x1800393db  jmp     short loc_18003941B
0x1800393dd  mov     rbx, [rbp+57h+var_60]
0x1800393e1  mov     rax, [rbx]
0x1800393e4  mov     rdi, [rax+60h]
0x1800393e8  mov     rcx, [rbp+57h+var_58]
0x1800393ec  test    rcx, rcx
0x1800393ef  jz      short loc_180039401
0x1800393f1  mov     rdx, [rcx]
0x1800393f4  mov     rax, [rdx+10h]
0x1800393f8  call    _guard_dispatch_icall
0x1800393fd  mov     [rbp+57h+var_58], r14
0x180039401  lea     rdx, [rbp+57h+var_58]
0x180039405  mov     rcx, rbx
0x180039408  mov     rax, rdi
0x18003940b  call    _guard_dispatch_icall
0x180039410  mov     esi, eax
0x180039412  test    eax, eax
0x180039414  jns     short loc_180039433
0x180039416  mov     edx, 3D0h; void *
0x18003941b  mov     rcx, [rbp+5Fh]; this
0x18003941f  mov     r9d, esi; char *
0x180039422  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x180039429  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003942e  jmp     loc_1800396F4
0x180039433  mov     rcx, [rbp+57h+var_58]
0x180039437  mov     rax, [rcx]
0x18003943a  lea     rdx, [rbp+57h+var_78]
0x18003943e  mov     rax, [rax+40h]
0x180039442  call    _guard_dispatch_icall
0x180039447  mov     ebx, eax
0x180039449  mov     esi, 1
0x18003944e  cmp     eax, esi
0x180039450  jz      loc_1800396F4
0x180039456  mov     edx, [rbp+57h+var_78]; unsigned int
0x180039459  test    edx, edx
0x18003945b  jnz     short loc_18003946F
0x18003945d  test    eax, eax
0x18003945f  jns     loc_1800396F2
0x180039465  mov     edx, 3D5h
0x18003946a  jmp     loc_1800396DF
0x18003946f  test    ebx, ebx
0x180039471  jns     short loc_18003947D
0x180039473  mov     edx, 3D6h
0x180039478  jmp     loc_1800396DF
0x18003947d  lea     rcx, [rbp+57h+var_B8]; this
0x180039481  call    ?put_MinimumSize@CDSArrayBuilder@@QEAAJKH@Z; CDSArrayBuilder::put_MinimumSize(ulong,int)
0x180039486  mov     ebx, eax
0x180039488  test    eax, eax
0x18003948a  jns     short loc_180039496
0x18003948c  mov     edx, 3D8h
0x180039491  jmp     loc_1800396DF
0x180039496  cmp     [rbp+57h+var_78], 0
0x18003949a  jle     loc_1800395E9
0x1800394a0  mov     rbx, [rbp+57h+var_58]
0x1800394a4  mov     rax, [rbx]
0x1800394a7  mov     rdi, [rax+38h]
0x1800394ab  mov     rcx, [rbp+57h+var_70]
0x1800394af  test    rcx, rcx
0x1800394b2  jz      short loc_1800394C8
0x1800394b4  mov     rdx, [rcx]
0x1800394b7  mov     rax, [rdx+10h]
0x1800394bb  call    _guard_dispatch_icall
0x1800394c0  mov     [rbp+57h+var_70], 0
0x1800394c8  lea     r8, [rbp+57h+var_70]
0x1800394cc  mov     edx, r14d
0x1800394cf  mov     rcx, rbx
0x1800394d2  mov     rax, rdi
0x1800394d5  call    _guard_dispatch_icall
0x1800394da  mov     ebx, eax
0x1800394dc  test    eax, eax
0x1800394de  js      loc_1800396DA
0x1800394e4  cmp     eax, esi
0x1800394e6  jz      loc_180039610
0x1800394ec  mov     rbx, [rbp+57h+var_70]
0x1800394f0  mov     rax, [rbx]
0x1800394f3  mov     rdi, [rax+148h]
0x1800394fa  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800394fe  call    cs:__imp_SysFreeString
0x180039504  mov     [rbp+57h+bstrString], 0
0x18003950c  lea     rdx, [rbp+57h+bstrString]
0x180039510  mov     rcx, rbx
0x180039513  mov     rax, rdi
0x180039516  call    _guard_dispatch_icall
0x18003951b  mov     ebx, eax
0x18003951d  cmp     eax, esi
0x18003951f  jz      loc_1800395DC
0x180039525  mov     rcx, [rbp+57h+bstrString]; lpString1
0x180039529  test    rcx, rcx
0x18003952c  jz      loc_1800396CB
0x180039532  test    eax, eax
0x180039534  js      loc_1800396C4
0x18003953a  lea     rdx, String2; "UpdateIdentity"
0x180039541  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x180039546  test    eax, eax
0x180039548  jnz     short loc_18003958C
0x18003954a  mov     rax, [rbp+57h+var_98]
0x18003954e  mov     [rsp+100h+var_C8], rax
0x180039553  mov     dword ptr [rsp+100h+var_D0], 0
0x18003955b  mov     dword ptr [rsp+100h+var_D8], r15d
0x180039560  mov     [rsp+100h+var_E0], r12d
0x180039565  mov     r9, [rbp+57h+var_90]
0x180039569  lea     r8, [rbp+57h+var_B8]
0x18003956d  mov     edx, [rbp+57h+var_BC]
0x180039570  mov     rcx, [rbp+57h+var_70]
0x180039574  call    ParseBundlePrereqIdentity
0x180039579  mov     ebx, eax
0x18003957b  test    eax, eax
0x18003957d  js      loc_1800396A0
0x180039583  add     r15d, esi
0x180039586  mov     [rbp+57h+var_C0], r15d
0x18003958a  jmp     short loc_1800395D9
0x18003958c  lea     rdx, aAtleastone; "AtLeastOne"
0x180039593  mov     rcx, [rbp+57h+bstrString]; lpString1
0x180039597  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x18003959c  test    eax, eax
0x18003959e  jnz     short loc_1800395D9
0x1800395a0  mov     rax, [rbp+57h+var_98]
0x1800395a4  mov     [rsp+100h+var_D0], rax
0x1800395a9  lea     rax, [rbp+57h+var_C0]
0x1800395ad  mov     [rsp+100h+var_D8], rax
0x1800395b2  mov     [rsp+100h+var_E0], r12d; int
0x1800395b7  mov     r9, [rbp+57h+var_90]
0x1800395bb  lea     r8, [rbp+57h+var_B8]
0x1800395bf  mov     edx, [rbp+57h+var_BC]
0x1800395c2  mov     rcx, [rbp+57h+var_70]
0x1800395c6  call    ParseBundlePrereqAloGroup
0x1800395cb  mov     ebx, eax
0x1800395cd  test    eax, eax
0x1800395cf  js      loc_1800396A7
0x1800395d5  mov     r15d, [rbp+57h+var_C0]
0x1800395d9  add     r12d, esi
0x1800395dc  add     r14d, esi
0x1800395df  cmp     r14d, [rbp+57h+var_78]
0x1800395e3  jl      loc_1800394A0
0x1800395e9  mov     rax, qword ptr [rbp+57h+var_B8+8]
0x1800395ed  mov     rcx, [rbp+57h+var_88]
0x1800395f1  mov     [rcx+r13], rax
0x1800395f5  mov     eax, dword ptr [rbp+57h+var_A8+8]
0x1800395f8  mov     rcx, [rbp+57h+var_80]
0x1800395fc  mov     [rcx+r13], eax
0x180039600  mov     qword ptr [rbp+57h+var_B8+8], 0
0x180039608  mov     qword ptr [rbp+57h+var_A8+4], 0
0x180039610  xor     ebx, ebx
0x180039612  mov     rcx, [rbp+57h+var_60]
0x180039616  test    rcx, rcx
0x180039619  jz      short loc_18003962F
0x18003961b  mov     rax, [rcx]
0x18003961e  mov     rax, [rax+10h]
0x180039622  call    _guard_dispatch_icall
0x180039627  mov     [rbp+57h+var_60], 0
0x18003962f  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180039633  call    cs:__imp_SysFreeString
0x180039639  mov     [rbp+57h+bstrString], 0
0x180039641  mov     rcx, [rbp+57h+var_70]
0x180039645  test    rcx, rcx
0x180039648  jz      short loc_18003965E
0x18003964a  mov     rax, [rcx]
0x18003964d  mov     rax, [rax+10h]
0x180039651  call    _guard_dispatch_icall
0x180039656  mov     [rbp+57h+var_70], 0
0x18003965e  lea     rcx, [rbp+57h+var_B8]; this
0x180039662  call    ??1CDSArrayBuilder@@QEAA@XZ; CDSArrayBuilder::~CDSArrayBuilder(void)
0x180039667  nop
0x180039668  mov     rcx, [rbp+57h+var_58]
0x18003966c  test    rcx, rcx
0x18003966f  jz      short loc_18003967E
0x180039671  mov     rdx, [rcx]
0x180039674  mov     rax, [rdx+10h]
0x180039678  call    _guard_dispatch_icall
0x18003967d  nop
0x18003967e  mov     eax, ebx
0x180039680  mov     rcx, [rbp+57h+var_50]
0x180039684  xor     rcx, rsp; StackCookie
0x180039687  call    __security_check_cookie
0x18003968c  add     rsp, 0C8h
0x180039693  pop     r15
0x180039695  pop     r14
0x180039697  pop     r13
0x180039699  pop     r12
0x18003969b  pop     rdi
0x18003969c  pop     rsi
0x18003969d  pop     rbx
0x18003969e  pop     rbp
0x18003969f  retn
0x1800396a0  mov     edx, 3F0h
0x1800396a5  jmp     short loc_1800396AC
0x1800396a7  mov     edx, 3F5h; void *
0x1800396ac  mov     r9d, eax; char *
0x1800396af  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x1800396b6  mov     rcx, [rbp+5Fh]; this
0x1800396ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800396bf  jmp     loc_180039612
0x1800396c4  mov     edx, 3EBh
0x1800396c9  jmp     short loc_1800396AC
0x1800396cb  mov     ebx, 8024000Eh
0x1800396d0  mov     r9d, ebx
0x1800396d3  mov     edx, 3EAh
0x1800396d8  jmp     short loc_1800396AF
0x1800396da  mov     edx, 3DEh; void *
0x1800396df  mov     r9d, ebx; char *
0x1800396e2  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x1800396e9  mov     rcx, [rbp+5Fh]; this
0x1800396ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800396f2  mov     esi, ebx
0x1800396f4  mov     ebx, esi
0x1800396f6  jmp     loc_180039612
```
