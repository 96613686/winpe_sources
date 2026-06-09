# JsonUtil::GetBooleanPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,uchar,uchar *)

- ea: `0x1400187e4`
- end: `0x1400188bf`
- name: `?GetBooleanPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WEPEAE@Z`
- size: `219`
- prototype: `__int64 __fastcall(JsonUtil *__hidden this, struct ABI::Windows::Data::Json::IJsonObject *, const wchar_t *, unsigned __int8, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400170dc`

## callees

- `0x140002ac0`
- `0x1400182f0`
- `0x1400187e4`
- `0x14001aa60`
- `0x1400206e0`

## string_xrefs

- `0x140018891`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JsonUtil::GetBooleanPropertyWithDefault(
        JsonUtil *this,
        const WCHAR *a2,
        const wchar_t *a3,
        _BYTE *a4)
{
  char v5; // si
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 (__fastcall *v9)(JsonUtil *, PVOID, _BYTE *); // rbx
  HSTRING_HEADER *v10; // rax
  int v11; // eax
  HSTRING_HEADER v13; // [rsp+20h] [rbp-68h] BYREF
  const WCHAR *v14; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v15[8]; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v5 = (char)a3;
  v14 = a2;
  if ( !this )
  {
    v7 = 107;
LABEL_14:
    v8 = -2147024809;
    goto LABEL_15;
  }
  if ( !a2 || !*a2 )
  {
    v7 = 108;
    goto LABEL_14;
  }
  if ( a4 )
  {
    v15[0] = 0;
    v9 = *(__int64 (__fastcall **)(JsonUtil *, PVOID, _BYTE *))(*(_QWORD *)this + 96LL);
    v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v13, &v14, (unsigned __int8)a3);
    v11 = v9(this, v10[1].Reserved.Reserved1, v15);
    v8 = v11;
    if ( v11 >= 0 )
    {
      *a4 = v15[0];
    }
    else
    {
      if ( v11 != -2089484279 )
      {
        v7 = 112;
        goto LABEL_15;
      }
      *a4 = v5;
    }
    return 0;
  }
  v8 = -2147467261;
  v7 = 109;
LABEL_15:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\JsonUtil.cpp",
    (const char *)v8,
    (int)v13.Reserved.Reserved1);
  return v8;
}

```

## disassembly

```asm
0x1400187e4  push    rbx
0x1400187e6  push    rbp
0x1400187e7  push    rsi
0x1400187e8  push    rdi
0x1400187e9  push    r14
0x1400187eb  sub     rsp, 60h
0x1400187ef  mov     rax, cs:__security_cookie
0x1400187f6  xor     rax, rsp
0x1400187f9  mov     [rsp+88h+var_38], rax
0x1400187fe  mov     rdi, r9
0x140018801  mov     sil, r8b
0x140018804  mov     r14, rcx
0x140018807  mov     [rsp+88h+var_48], rdx
0x14001880c  xor     ebp, ebp
0x14001880e  test    rcx, rcx
0x140018811  jnz     short loc_140018818
0x140018813  lea     edx, [rcx+6Bh]
0x140018816  jmp     short loc_140018889
0x140018818  test    rdx, rdx
0x14001881b  jz      short loc_140018884
0x14001881d  cmp     [rdx], bp
0x140018820  jz      short loc_140018884
0x140018822  test    rdi, rdi
0x140018825  jnz     short loc_140018831
0x140018827  mov     ebx, 80004003h
0x14001882c  lea     edx, [rdi+6Dh]
0x14001882f  jmp     short loc_14001888E
0x140018831  mov     [rsp+88h+var_40], bpl
0x140018836  mov     rax, [rcx]
0x140018839  mov     rbx, [rax+60h]
0x14001883d  lea     rdx, [rsp+88h+var_48]
0x140018842  lea     rcx, [rsp+88h+var_68]
0x140018847  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x14001884c  nop
0x14001884d  lea     r8, [rsp+88h+var_40]
0x140018852  mov     rdx, [rax+18h]
0x140018856  mov     rcx, r14
0x140018859  mov     rax, rbx
0x14001885c  call    _guard_dispatch_icall
0x140018861  mov     ebx, eax
0x140018863  test    eax, eax
0x140018865  jns     short loc_14001887A
0x140018867  cmp     eax, 83750009h
0x14001886c  jz      short loc_140018875
0x14001886e  mov     edx, 70h ; 'p'
0x140018873  jmp     short loc_14001888E
0x140018875  mov     [rdi], sil
0x140018878  jmp     short loc_140018880
0x14001887a  mov     al, [rsp+88h+var_40]
0x14001887e  mov     [rdi], al
0x140018880  xor     eax, eax
0x140018882  jmp     short loc_1400188A7
0x140018884  mov     edx, 6Ch ; 'l'; void *
0x140018889  mov     ebx, 80070057h
0x14001888e  mov     r9d, ebx; char *
0x140018891  lea     r8, aCW1SSrcClientL_8; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140018898  mov     rcx, [rsp+88h]; this
0x1400188a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400188a5  mov     eax, ebx
0x1400188a7  mov     rcx, [rsp+88h+var_38]
0x1400188ac  xor     rcx, rsp; StackCookie
0x1400188af  call    __security_check_cookie
0x1400188b4  add     rsp, 60h
0x1400188b8  pop     r14
0x1400188ba  pop     rdi
0x1400188bb  pop     rsi
0x1400188bc  pop     rbp
0x1400188bd  pop     rbx
0x1400188be  retn
```
