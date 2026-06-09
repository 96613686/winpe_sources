# ParseBundlePrereqAloGroup

- ea: `0x180039040`
- end: `0x1800392e4`
- name: `ParseBundlePrereqAloGroup`
- size: `676`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800392ec`

## callees

- `0x180003950`
- `0x18000a9b4`
- `0x180038d00`
- `0x180038f2c`
- `0x180039040`
- `0x180042114`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800391b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003924b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800391b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003924b`

## string_xrefs

- `0x1800391ec`: `UpdateIdentity`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall ParseBundlePrereqAloGroup(
        __int64 a1,
        unsigned int a2,
        CDSArrayBuilder *a3,
        __int64 a4,
        unsigned int a5,
        int *a6,
        __int64 a7)
{
  int v9; // r14d
  int AttributeSet; // ebx
  __int64 v11; // rdx
  __int64 v12; // r9
  int v13; // eax
  int v14; // r8d
  unsigned int v15; // esi
  __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64 *); // rdi
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, BSTR *); // rdi
  __int64 v20; // r8
  __int64 v21; // r9
  unsigned int v23; // [rsp+20h] [rbp-71h]
  unsigned int v26; // [rsp+58h] [rbp-39h] BYREF
  __int64 v27; // [rsp+60h] [rbp-31h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-29h] BYREF
  __int64 v29; // [rsp+70h] [rbp-21h] BYREF
  int v30; // [rsp+78h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+47h]

  v29 = 0;
  v27 = 0;
  v26 = 0;
  bstrString = 0;
  v30 = 0;
  v9 = *a6;
  AttributeSet = GetAttributeSet(a1, &v30, &qword_180075930, a7);
  if ( AttributeSet < 0 )
  {
    v11 = 893;
LABEL_5:
    v12 = (unsigned int)AttributeSet;
    goto LABEL_35;
  }
  AttributeSet = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 96LL))(a1, &v29);
  if ( AttributeSet < 0 )
  {
    v11 = 895;
    goto LABEL_5;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v29 + 64LL))(v29, &v26);
  AttributeSet = v13;
  if ( v13 == 1 || !v26 )
  {
    AttributeSet = 0;
    goto LABEL_25;
  }
  if ( v13 >= 0 )
  {
    v13 = CDSArrayBuilder::put_MinimumSize(a3, v26, v14);
    AttributeSet = v13;
    if ( v13 >= 0 )
    {
      v15 = 0;
      if ( (int)v26 <= 0 )
      {
LABEL_24:
        *a6 = v9;
        AttributeSet = 0;
        goto LABEL_25;
      }
      while ( 1 )
      {
        v16 = v29;
        v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v29 + 56LL);
        if ( v27 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          v27 = 0;
        }
        v13 = v17(v16, v15, &v27);
        AttributeSet = v13;
        if ( v13 < 0 )
          break;
        v18 = v27;
        v19 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v27 + 328LL);
        SysFreeString(bstrString);
        bstrString = 0;
        v13 = v19(v18, &bstrString);
        AttributeSet = v13;
        if ( v13 != 1 )
        {
          if ( !bstrString )
          {
            AttributeSet = -2145124338;
            v12 = 2149842958LL;
            v11 = 919;
            goto LABEL_35;
          }
          if ( v13 < 0 )
          {
            v11 = 920;
            goto LABEL_34;
          }
          if ( !AsciiStringCompareI(bstrString, L"UpdateIdentity", v20, v21, v23) )
          {
            v23 = a5;
            v13 = ParseBundlePrereqIdentity(v27, a2, a3, a4);
            AttributeSet = v13;
            if ( v13 < 0 )
            {
              v11 = 925;
              goto LABEL_34;
            }
            ++v9;
          }
        }
        if ( (int)++v15 >= (int)v26 )
          goto LABEL_24;
      }
      v11 = 907;
    }
    else
    {
      v11 = 903;
    }
  }
  else
  {
    v11 = 901;
  }
LABEL_34:
  v12 = (unsigned int)v13;
LABEL_35:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
    (const char *)v12,
    v23);
LABEL_25:
  SysFreeString(bstrString);
  bstrString = 0;
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  return (unsigned int)AttributeSet;
}

```

## disassembly

```asm
0x180039040  push    rbp
0x180039042  push    rbx
0x180039043  push    rsi
0x180039044  push    rdi
0x180039045  push    r12
0x180039047  push    r13
0x180039049  push    r14
0x18003904b  push    r15
0x18003904d  lea     rbp, [rsp-7]
0x180039052  sub     rsp, 98h
0x180039059  mov     rax, cs:__security_cookie
0x180039060  xor     rax, rsp
0x180039063  mov     [rbp+3Fh+var_50], rax
0x180039067  mov     [rbp+3Fh+var_80], r9
0x18003906b  mov     r13, r8
0x18003906e  mov     [rbp+3Fh+var_90], edx
0x180039071  mov     rdi, rcx
0x180039074  mov     r12, [rbp+3Fh+arg_28]
0x180039078  mov     rax, [rbp+3Fh+arg_30]
0x18003907c  mov     [rbp+3Fh+var_88], rax
0x180039080  xor     r15d, r15d
0x180039083  mov     [rbp+3Fh+var_60], r15
0x180039087  mov     [rbp+3Fh+var_70], r15
0x18003908b  mov     [rbp+3Fh+var_78], r15d
0x18003908f  mov     [rbp+3Fh+bstrString], r15
0x180039093  mov     [rbp+3Fh+var_58], r15d
0x180039097  mov     r14d, [r12]
0x18003909b  mov     r9, rax
0x18003909e  lea     r8, qword_180075930
0x1800390a5  lea     rdx, [rbp+3Fh+var_58]
0x1800390a9  call    GetAttributeSet
0x1800390ae  mov     ebx, eax
0x1800390b0  test    eax, eax
0x1800390b2  jns     short loc_1800390BB
0x1800390b4  mov     edx, 37Dh
0x1800390b9  jmp     short loc_1800390F5
0x1800390bb  mov     rax, [rdi]
0x1800390be  mov     rbx, [rax+60h]
0x1800390c2  mov     rcx, [rbp+3Fh+var_60]
0x1800390c6  test    rcx, rcx
0x1800390c9  jz      short loc_1800390DB
0x1800390cb  mov     rax, [rcx]
0x1800390ce  mov     rax, [rax+10h]
0x1800390d2  call    _guard_dispatch_icall
0x1800390d7  mov     [rbp+3Fh+var_60], r15
0x1800390db  lea     rdx, [rbp+3Fh+var_60]
0x1800390df  mov     rcx, rdi
0x1800390e2  mov     rax, rbx
0x1800390e5  call    _guard_dispatch_icall
0x1800390ea  mov     ebx, eax
0x1800390ec  test    eax, eax
0x1800390ee  jns     short loc_1800390FD
0x1800390f0  mov     edx, 37Fh
0x1800390f5  mov     r9d, ebx
0x1800390f8  jmp     loc_1800392CB
0x1800390fd  mov     rcx, [rbp+3Fh+var_60]
0x180039101  mov     rax, [rcx]
0x180039104  lea     rdx, [rbp+3Fh+var_78]
0x180039108  mov     rax, [rax+40h]
0x18003910c  call    _guard_dispatch_icall
0x180039111  mov     ebx, eax
0x180039113  cmp     eax, 1
0x180039116  jz      short loc_18003911F
0x180039118  mov     edx, [rbp+3Fh+var_78]; unsigned int
0x18003911b  test    edx, edx
0x18003911d  jnz     short loc_180039127
0x18003911f  mov     ebx, r15d
0x180039122  jmp     loc_1800392DB
0x180039127  test    eax, eax
0x180039129  jns     short loc_180039135
0x18003912b  mov     edx, 385h
0x180039130  jmp     loc_1800392C8
0x180039135  mov     rcx, r13; this
0x180039138  call    ?put_MinimumSize@CDSArrayBuilder@@QEAAJKH@Z; CDSArrayBuilder::put_MinimumSize(ulong,int)
0x18003913d  mov     ebx, eax
0x18003913f  test    eax, eax
0x180039141  jns     short loc_18003914D
0x180039143  mov     edx, 387h
0x180039148  jmp     loc_1800392C8
0x18003914d  mov     esi, r15d
0x180039150  cmp     [rbp+3Fh+var_78], r15d
0x180039154  jle     loc_180039240
0x18003915a  mov     r15d, [rbp+3Fh+arg_20]
0x18003915e  mov     rbx, [rbp+3Fh+var_60]
0x180039162  mov     rax, [rbx]
0x180039165  mov     rdi, [rax+38h]
0x180039169  mov     rcx, [rbp+3Fh+var_70]
0x18003916d  test    rcx, rcx
0x180039170  jz      short loc_180039186
0x180039172  mov     rdx, [rcx]
0x180039175  mov     rax, [rdx+10h]
0x180039179  call    _guard_dispatch_icall
0x18003917e  mov     [rbp+3Fh+var_70], 0
0x180039186  lea     r8, [rbp+3Fh+var_70]
0x18003918a  mov     edx, esi
0x18003918c  mov     rcx, rbx
0x18003918f  mov     rax, rdi
0x180039192  call    _guard_dispatch_icall
0x180039197  mov     ebx, eax
0x180039199  test    eax, eax
0x18003919b  js      loc_1800392C3
0x1800391a1  mov     rbx, [rbp+3Fh+var_70]
0x1800391a5  mov     rax, [rbx]
0x1800391a8  mov     rdi, [rax+148h]
0x1800391af  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x1800391b3  call    cs:__imp_SysFreeString
0x1800391b9  mov     [rbp+3Fh+bstrString], 0
0x1800391c1  lea     rdx, [rbp+3Fh+bstrString]
0x1800391c5  mov     rcx, rbx
0x1800391c8  mov     rax, rdi
0x1800391cb  call    _guard_dispatch_icall
0x1800391d0  mov     ebx, eax
0x1800391d2  cmp     eax, 1
0x1800391d5  jz      short loc_180039232
0x1800391d7  mov     rcx, [rbp+3Fh+bstrString]; lpString1
0x1800391db  test    rcx, rcx
0x1800391de  jz      loc_1800392B4
0x1800391e4  test    eax, eax
0x1800391e6  js      loc_1800392AD
0x1800391ec  lea     rdx, String2; "UpdateIdentity"
0x1800391f3  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x1800391f8  test    eax, eax
0x1800391fa  jnz     short loc_180039232
0x1800391fc  mov     eax, [rbp+3Fh+var_58]
0x1800391ff  mov     rcx, [rbp+3Fh+var_88]
0x180039203  mov     [rsp+0D0h+var_98], rcx
0x180039208  mov     [rsp+0D0h+var_A0], eax
0x18003920c  mov     [rsp+0D0h+var_A8], r14d
0x180039211  mov     [rsp+0D0h+var_B0], r15d
0x180039216  mov     r9, [rbp+3Fh+var_80]
0x18003921a  mov     r8, r13
0x18003921d  mov     edx, [rbp+3Fh+var_90]
0x180039220  mov     rcx, [rbp+3Fh+var_70]
0x180039224  call    ParseBundlePrereqIdentity
0x180039229  mov     ebx, eax
0x18003922b  test    eax, eax
0x18003922d  js      short loc_1800392A6
0x18003922f  inc     r14d
0x180039232  inc     esi
0x180039234  cmp     esi, [rbp+3Fh+var_78]
0x180039237  jl      loc_18003915E
0x18003923d  xor     r15d, r15d
0x180039240  mov     [r12], r14d
0x180039244  mov     ebx, r15d
0x180039247  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x18003924b  call    cs:__imp_SysFreeString
0x180039251  mov     [rbp+3Fh+bstrString], r15
0x180039255  mov     rcx, [rbp+3Fh+var_70]
0x180039259  test    rcx, rcx
0x18003925c  jz      short loc_18003926E
0x18003925e  mov     rax, [rcx]
0x180039261  mov     rax, [rax+10h]
0x180039265  call    _guard_dispatch_icall
0x18003926a  mov     [rbp+3Fh+var_70], r15
0x18003926e  mov     rcx, [rbp+3Fh+var_60]
0x180039272  test    rcx, rcx
0x180039275  jz      short loc_180039284
0x180039277  mov     rdx, [rcx]
0x18003927a  mov     rax, [rdx+10h]
0x18003927e  call    _guard_dispatch_icall
0x180039283  nop
0x180039284  mov     eax, ebx
0x180039286  mov     rcx, [rbp+3Fh+var_50]
0x18003928a  xor     rcx, rsp; StackCookie
0x18003928d  call    __security_check_cookie
0x180039292  add     rsp, 98h
0x180039299  pop     r15
0x18003929b  pop     r14
0x18003929d  pop     r13
0x18003929f  pop     r12
0x1800392a1  pop     rdi
0x1800392a2  pop     rsi
0x1800392a3  pop     rbx
0x1800392a4  pop     rbp
0x1800392a5  retn
0x1800392a6  mov     edx, 39Dh
0x1800392ab  jmp     short loc_1800392C8
0x1800392ad  mov     edx, 398h
0x1800392b2  jmp     short loc_1800392C8
0x1800392b4  mov     ebx, 8024000Eh
0x1800392b9  mov     r9d, ebx
0x1800392bc  mov     edx, 397h
0x1800392c1  jmp     short loc_1800392CB
0x1800392c3  mov     edx, 38Bh; void *
0x1800392c8  mov     r9d, eax; char *
0x1800392cb  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x1800392d2  mov     rcx, [rbp+47h]; this
0x1800392d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800392db  xor     r15d, r15d
0x1800392de  jmp     loc_180039247
```
