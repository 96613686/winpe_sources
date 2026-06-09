# JsonUtil::GetNamedObject(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,ABI::Windows::Data::Json::IJsonObject * *)

- ea: `0x1400188c8`
- end: `0x1400189ed`
- name: `?GetNamedObject@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WPEAPEAU23456@@Z`
- size: `293`
- prototype: `__int64 __fastcall(JsonUtil *__hidden this, struct ABI::Windows::Data::Json::IJsonObject *, const wchar_t *, struct ABI::Windows::Data::Json::IJsonObject **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001593c`
- `0x1400170dc`
- `0x140017f58`

## callees

- `0x140002ac0`
- `0x1400182f0`
- `0x1400188c8`
- `0x14001aa60`
- `0x1400206e0`

## string_xrefs

- `0x140018968`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`
- `0x1400189bd`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall JsonUtil::GetNamedObject(
        JsonUtil *this,
        const WCHAR *a2,
        wchar_t *a3,
        struct ABI::Windows::Data::Json::IJsonObject **a4)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  __int64 (__fastcall *v8)(JsonUtil *, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v9; // rax
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  HSTRING_HEADER v14; // [rsp+20h] [rbp-58h] BYREF
  const WCHAR *v15; // [rsp+40h] [rbp-38h] BYREF
  __int64 v16; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v15 = a2;
  if ( !this )
  {
    v6 = 126;
LABEL_17:
    v7 = -2147024809;
    goto LABEL_18;
  }
  if ( !a2 || !*a2 )
  {
    v6 = 127;
    goto LABEL_17;
  }
  if ( !a3 )
  {
    v7 = -2147467261;
    v6 = 128;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\JsonUtil.cpp",
      (const char *)v7,
      (int)v14.Reserved.Reserved1);
    return v7;
  }
  v8 = *(__int64 (__fastcall **)(JsonUtil *, PVOID, __int64 *))(*(_QWORD *)this + 64LL);
  v16 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v14, &v15, (unsigned int)a3);
  v10 = v8(this, v9[1].Reserved.Reserved1, &v16);
  v7 = v10;
  if ( v10 >= 0 )
  {
    v12 = v16;
    v11 = 0;
    v16 = 0;
  }
  else
  {
    if ( v10 != -2089484279 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\JsonUtil.cpp",
        (const char *)(unsigned int)v10,
        (int)v14.Reserved.Reserved1);
      v11 = v16;
      goto LABEL_13;
    }
    v12 = 0;
    v11 = v16;
  }
  *(_QWORD *)a3 = v12;
  v7 = 0;
LABEL_13:
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return v7;
}

```

## disassembly

```asm
0x1400188c8  mov     [rsp+arg_18], rbx
0x1400188cd  push    rbp
0x1400188ce  push    rsi
0x1400188cf  push    rdi
0x1400188d0  sub     rsp, 60h
0x1400188d4  mov     rax, cs:__security_cookie
0x1400188db  xor     rax, rsp
0x1400188de  mov     [rsp+78h+var_28], rax
0x1400188e3  mov     rdi, r8
0x1400188e6  mov     rsi, rcx
0x1400188e9  mov     [rsp+78h+var_38], rdx
0x1400188ee  xor     ebp, ebp
0x1400188f0  test    rcx, rcx
0x1400188f3  jnz     short loc_1400188FD
0x1400188f5  lea     edx, [rcx+7Eh]
0x1400188f8  jmp     loc_1400189B5
0x1400188fd  test    rdx, rdx
0x140018900  jz      loc_1400189B0
0x140018906  cmp     [rdx], bp
0x140018909  jz      loc_1400189B0
0x14001890f  test    rdi, rdi
0x140018912  jnz     short loc_140018923
0x140018914  mov     ebx, 80004003h
0x140018919  mov     edx, 80h
0x14001891e  jmp     loc_1400189BA
0x140018923  mov     rax, [rcx]
0x140018926  mov     rbx, [rax+40h]
0x14001892a  mov     [rsp+78h+var_30], rbp
0x14001892f  lea     rdx, [rsp+78h+var_38]
0x140018934  lea     rcx, [rsp+78h+var_58]
0x140018939  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x14001893e  nop
0x14001893f  lea     r8, [rsp+78h+var_30]
0x140018944  mov     rdx, [rax+18h]
0x140018948  mov     rcx, rsi
0x14001894b  mov     rax, rbx
0x14001894e  call    _guard_dispatch_icall
0x140018953  mov     ebx, eax
0x140018955  test    eax, eax
0x140018957  jns     short loc_14001898A
0x140018959  cmp     eax, 83750009h
0x14001895e  jz      short loc_140018980
0x140018960  mov     rcx, [rsp+78h]; this
0x140018965  mov     r9d, eax; char *
0x140018968  lea     r8, aCW1SSrcClientL_8; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14001896f  mov     edx, 83h; void *
0x140018974  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018979  mov     rcx, [rsp+78h+var_30]
0x14001897e  jmp     short loc_14001899C
0x140018980  mov     rax, rbp
0x140018983  mov     rcx, [rsp+78h+var_30]
0x140018988  jmp     short loc_140018997
0x14001898a  mov     rax, [rsp+78h+var_30]
0x14001898f  mov     rcx, rbp
0x140018992  mov     [rsp+78h+var_30], rcx
0x140018997  mov     [rdi], rax
0x14001899a  mov     ebx, ebp
0x14001899c  test    rcx, rcx
0x14001899f  jz      short loc_1400189AE
0x1400189a1  mov     rdx, [rcx]
0x1400189a4  mov     rax, [rdx+10h]
0x1400189a8  call    _guard_dispatch_icall
0x1400189ad  nop
0x1400189ae  jmp     short loc_1400189CE
0x1400189b0  mov     edx, 7Fh; void *
0x1400189b5  mov     ebx, 80070057h
0x1400189ba  mov     r9d, ebx; char *
0x1400189bd  lea     r8, aCW1SSrcClientL_8; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400189c4  mov     rcx, [rsp+78h]; this
0x1400189c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400189ce  mov     eax, ebx
0x1400189d0  mov     rcx, [rsp+78h+var_28]
0x1400189d5  xor     rcx, rsp; StackCookie
0x1400189d8  call    __security_check_cookie
0x1400189dd  mov     rbx, [rsp+78h+arg_18]
0x1400189e5  add     rsp, 60h
0x1400189e9  pop     rdi
0x1400189ea  pop     rsi
0x1400189eb  pop     rbp
0x1400189ec  retn
```
