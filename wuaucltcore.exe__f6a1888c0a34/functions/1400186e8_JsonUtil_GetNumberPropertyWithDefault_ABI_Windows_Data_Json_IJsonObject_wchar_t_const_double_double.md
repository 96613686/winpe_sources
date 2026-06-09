# JsonUtil::GetNumberPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,double,double *)

- ea: `0x1400186e8`
- end: `0x1400187dc`
- name: `?GetNumberPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WNPEAN@Z`
- size: `244`
- prototype: `__int64 __fastcall(JsonUtil *__hidden this, struct ABI::Windows::Data::Json::IJsonObject *, const wchar_t *, double, double *)`
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400151b8`
- `0x140016cd4`
- `0x1400170dc`
- `0x140017624`
- `0x1400178a0`
- `0x140017f58`

## callees

- `0x140002ac0`
- `0x1400182f0`
- `0x1400186e8`
- `0x14001aa60`
- `0x1400206e0`

## string_xrefs

- `0x1400187a4`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JsonUtil::GetNumberPropertyWithDefault(
        JsonUtil *this,
        const WCHAR *a2,
        const wchar_t *a3,
        double a4)
{
  _QWORD *v4; // r9
  __int64 v5; // xmm2_8
  _QWORD *v6; // rdi
  __int64 v8; // rdx
  unsigned int v9; // ebx
  __int64 (__fastcall *v10)(JsonUtil *, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v11; // rax
  int v12; // eax
  HSTRING_HEADER v14; // [rsp+20h] [rbp-68h] BYREF
  const WCHAR *v15; // [rsp+40h] [rbp-48h] BYREF
  __int64 v16; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v6 = v4;
  v15 = a2;
  if ( !this )
  {
    v8 = 85;
LABEL_14:
    v9 = -2147024809;
    goto LABEL_15;
  }
  if ( !a2 || !*a2 )
  {
    v8 = 86;
    goto LABEL_14;
  }
  if ( v4 )
  {
    v16 = 0;
    v10 = *(__int64 (__fastcall **)(JsonUtil *, PVOID, __int64 *))(*(_QWORD *)this + 88LL);
    v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v14, &v15, (unsigned int)a3);
    v12 = v10(this, v11[1].Reserved.Reserved1, &v16);
    v9 = v12;
    if ( v12 >= 0 )
    {
      *v6 = v16;
    }
    else
    {
      if ( v12 != -2089484279 )
      {
        v8 = 90;
        goto LABEL_15;
      }
      *v6 = v5;
    }
    return 0;
  }
  v9 = -2147467261;
  v8 = 87;
LABEL_15:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\JsonUtil.cpp",
    (const char *)v9,
    (int)v14.Reserved.Reserved1);
  return v9;
}

```

## disassembly

```asm
0x1400186e8  mov     [rsp+arg_10], rbx
0x1400186ed  push    rbp
0x1400186ee  push    rsi
0x1400186ef  push    rdi
0x1400186f0  sub     rsp, 70h
0x1400186f4  movaps  [rsp+88h+var_28], xmm6
0x1400186f9  mov     rax, cs:__security_cookie
0x140018700  xor     rax, rsp
0x140018703  mov     [rsp+88h+var_38], rax
0x140018708  mov     rdi, r9
0x14001870b  movaps  xmm6, xmm2
0x14001870e  mov     rsi, rcx
0x140018711  mov     [rsp+88h+var_48], rdx
0x140018716  xor     ebp, ebp
0x140018718  test    rcx, rcx
0x14001871b  jnz     short loc_140018722
0x14001871d  lea     edx, [rcx+55h]
0x140018720  jmp     short loc_14001879C
0x140018722  test    rdx, rdx
0x140018725  jz      short loc_140018797
0x140018727  cmp     [rdx], bp
0x14001872a  jz      short loc_140018797
0x14001872c  test    rdi, rdi
0x14001872f  jnz     short loc_14001873B
0x140018731  mov     ebx, 80004003h
0x140018736  lea     edx, [rdi+57h]
0x140018739  jmp     short loc_1400187A1
0x14001873b  xorps   xmm0, xmm0
0x14001873e  movsd   [rsp+88h+var_40], xmm0
0x140018744  mov     rax, [rcx]
0x140018747  mov     rbx, [rax+58h]
0x14001874b  lea     rdx, [rsp+88h+var_48]
0x140018750  lea     rcx, [rsp+88h+var_68]
0x140018755  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x14001875a  nop
0x14001875b  lea     r8, [rsp+88h+var_40]
0x140018760  mov     rdx, [rax+18h]
0x140018764  mov     rcx, rsi
0x140018767  mov     rax, rbx
0x14001876a  call    _guard_dispatch_icall
0x14001876f  mov     ebx, eax
0x140018771  test    eax, eax
0x140018773  jns     short loc_140018789
0x140018775  cmp     eax, 83750009h
0x14001877a  jz      short loc_140018783
0x14001877c  mov     edx, 5Ah ; 'Z'
0x140018781  jmp     short loc_1400187A1
0x140018783  movsd   qword ptr [rdi], xmm6
0x140018787  jmp     short loc_140018793
0x140018789  movsd   xmm0, [rsp+88h+var_40]
0x14001878f  movsd   qword ptr [rdi], xmm0
0x140018793  xor     eax, eax
0x140018795  jmp     short loc_1400187BA
0x140018797  mov     edx, 56h ; 'V'; void *
0x14001879c  mov     ebx, 80070057h
0x1400187a1  mov     r9d, ebx; char *
0x1400187a4  lea     r8, aCW1SSrcClientL_8; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400187ab  mov     rcx, [rsp+88h]; this
0x1400187b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400187b8  mov     eax, ebx
0x1400187ba  mov     rcx, [rsp+88h+var_38]
0x1400187bf  xor     rcx, rsp; StackCookie
0x1400187c2  call    __security_check_cookie
0x1400187c7  mov     rbx, [rsp+88h+arg_10]
0x1400187cf  movaps  xmm6, [rsp+88h+var_28]
0x1400187d4  add     rsp, 70h
0x1400187d8  pop     rdi
0x1400187d9  pop     rsi
0x1400187da  pop     rbp
0x1400187db  retn
```
