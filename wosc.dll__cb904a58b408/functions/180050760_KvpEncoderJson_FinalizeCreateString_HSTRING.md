# KvpEncoderJson::FinalizeCreateString(HSTRING__ * *)

- ea: `0x180050760`
- end: `0x18005084a`
- name: `?FinalizeCreateString@KvpEncoderJson@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `234`
- prototype: `int(KvpEncoderJson *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005f50`
- `0x18000e5ac`
- `0x180050760`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800507c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050809`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050822`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800507c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050809`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050822`

## string_xrefs

- `0x1800507a1`: `onecore\base\flighting\common\inc\KvpEncoder.h`
- `0x1800507f3`: `onecore\base\flighting\common\inc\KvpEncoder.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall KvpEncoderJson::FinalizeCreateString(KvpEncoderJson *this, HSTRING *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  int v7; // eax
  HSTRING v8; // rax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HSTRING string; // [rsp+40h] [rbp+20h] BYREF
  __int64 v13; // [rsp+50h] [rbp+30h] BYREF

  v13 = 0;
  v3 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 2))(
         *((_QWORD *)this + 2),
         &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e,
         &v13);
  v4 = v3;
  if ( v3 >= 0 )
  {
    string = 0;
    v5 = v13;
    v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v13 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v7 = v6(v5, &string);
    v4 = v7;
    if ( v7 >= 0 )
    {
      v8 = string;
      string = 0;
      *a2 = v8;
      WindowsDeleteString(0);
      v4 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF8,
        (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
        (const char *)(unsigned int)v7,
        savedregs);
      WindowsDeleteString(string);
    }
    string = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF4,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
      (const char *)(unsigned int)v3,
      savedregs);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  return v4;
}

```

## disassembly

```asm
0x180050760  mov     [rsp-18h+arg_8], rbx
0x180050765  push    rbp
0x180050766  push    rsi
0x180050767  push    rdi; int
0x180050768  mov     rbp, rsp
0x18005076b  sub     rsp, 20h
0x18005076f  mov     rsi, rdx
0x180050772  mov     [rbp+arg_10], 0
0x18005077a  mov     rcx, [rcx+10h]
0x18005077e  mov     rax, [rcx]
0x180050781  lea     r8, [rbp+arg_10]
0x180050785  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18005078c  mov     rax, [rax]
0x18005078f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050794  mov     ebx, eax
0x180050796  test    eax, eax
0x180050798  jns     short loc_1800507B4
0x18005079a  mov     rcx, [rbp+18h]; this
0x18005079e  mov     r9d, eax; char *
0x1800507a1  lea     r8, aOnecoreBaseFli_7; "onecore\\base\\flighting\\common\\inc\\"...
0x1800507a8  mov     edx, 0F4h; void *
0x1800507ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800507b2  jmp     short loc_180050832
0x1800507b4  mov     [rbp+string], 0
0x1800507bc  mov     rdi, [rbp+arg_10]
0x1800507c0  mov     rax, [rdi]
0x1800507c3  mov     rbx, [rax+38h]
0x1800507c7  xor     ecx, ecx; string
0x1800507c9  call    cs:__imp_WindowsDeleteString
0x1800507cf  mov     [rbp+string], 0
0x1800507d7  lea     rdx, [rbp+string]
0x1800507db  mov     rcx, rdi
0x1800507de  mov     rax, rbx
0x1800507e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800507e6  mov     ebx, eax
0x1800507e8  test    eax, eax
0x1800507ea  jns     short loc_180050811
0x1800507ec  mov     rcx, [rbp+18h]; this
0x1800507f0  mov     r9d, eax; char *
0x1800507f3  lea     r8, aOnecoreBaseFli_7; "onecore\\base\\flighting\\common\\inc\\"...
0x1800507fa  mov     edx, 0F8h; void *
0x1800507ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050804  nop
0x180050805  mov     rcx, [rbp+string]; string
0x180050809  call    cs:__imp_WindowsDeleteString
0x18005080f  jmp     short loc_18005082A
0x180050811  mov     rax, [rbp+string]
0x180050815  mov     [rbp+string], 0
0x18005081d  mov     [rsi], rax
0x180050820  xor     ecx, ecx; string
0x180050822  call    cs:__imp_WindowsDeleteString
0x180050828  xor     ebx, ebx
0x18005082a  mov     [rbp+string], 0
0x180050832  lea     rcx, [rbp+arg_10]
0x180050836  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005083b  mov     eax, ebx
0x18005083d  mov     rbx, [rsp+20h+arg_8]
0x180050842  add     rsp, 20h
0x180050846  pop     rdi
0x180050847  pop     rsi
0x180050848  pop     rbp
0x180050849  retn
```
