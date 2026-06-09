# KvpEncoderJson::RuntimeInitialize(KvpEncoderMethod)

- ea: `0x180050fb0`
- end: `0x18005110c`
- name: `?RuntimeInitialize@KvpEncoderJson@@UEAAJW4KvpEncoderMethod@@@Z`
- size: `348`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003110`
- `0x18000564b`
- `0x180005f50`
- `0x18000b0bc`
- `0x18000e5ac`
- `0x180050fb0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800510da`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800510da`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180051020`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180051020`

## string_xrefs

- `0x180050ff4`: `Windows.Data.Json.JsonObject`
- `0x1800510b9`: `Windows.Data.Json.JsonValue`
- `0x180051085`: `onecore\base\flighting\common\inc\KvpEncoder.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KvpEncoderJson::RuntimeInitialize(__int64 a1)
{
  _QWORD *v2; // rdi
  int ActivationFactory; // ebx
  __int64 v4; // rdx
  int v6[2]; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-30h] BYREF
  __int64 v8; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_BYTE *)(a1 + 8) = 1;
  v2 = (_QWORD *)(a1 + 16);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 16);
  v8 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  *v2 = 0;
  *(_QWORD *)v6 = 0;
  ActivationFactory = RoActivateInstance(v8, v6);
  if ( ActivationFactory >= 0 )
  {
    if ( !memcmp_0(&GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *v2 = *(_QWORD *)v6;
    }
    else
    {
      ActivationFactory = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))v6)(
                            *(_QWORD *)v6,
                            &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
                            v2);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v6 + 16LL))(*(_QWORD *)v6);
    }
  }
  if ( ActivationFactory < 0 )
  {
    v4 = 191;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
      (const char *)(unsigned int)ActivationFactory,
      v6[0]);
    return (unsigned int)ActivationFactory;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 24);
  v8 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  ActivationFactory = RoGetActivationFactory(v8, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, a1 + 24);
  if ( ActivationFactory < 0 )
  {
    v4 = 194;
    goto LABEL_7;
  }
  return 0;
}

```

## disassembly

```asm
0x180050fb0  mov     [rsp+arg_8], rbx
0x180050fb5  mov     [rsp+arg_10], rsi
0x180050fba  push    rdi
0x180050fbb  sub     rsp, 50h
0x180050fbf  mov     rax, cs:__security_cookie
0x180050fc6  xor     rax, rsp
0x180050fc9  mov     [rsp+58h+var_10], rax
0x180050fce  mov     rsi, rcx
0x180050fd1  mov     byte ptr [rcx+8], 1
0x180050fd5  lea     rdi, [rcx+10h]
0x180050fd9  mov     rcx, rdi
0x180050fdc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180050fe1  mov     [rsp+58h+var_18], 0
0x180050fea  mov     r9d, 1Ch; unsigned int
0x180050ff0  lea     r8d, [r9+1]; unsigned int
0x180050ff4  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180050ffb  lea     rcx, [rsp+58h+hstringHeader]; hstringHeader
0x180051000  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180051005  nop
0x180051006  mov     qword ptr [rdi], 0
0x18005100d  mov     qword ptr [rsp+58h+var_38], 0; int
0x180051016  lea     rdx, [rsp+58h+var_38]
0x18005101b  mov     rcx, [rsp+58h+var_18]
0x180051020  call    cs:__imp_RoActivateInstance
0x180051026  mov     ebx, eax
0x180051028  test    eax, eax
0x18005102a  js      short loc_18005107C
0x18005102c  mov     r8d, 10h; Size
0x180051032  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180051039  lea     rcx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3; Buf1
0x180051040  call    memcmp_0
0x180051045  mov     rcx, qword ptr [rsp+58h+var_38]
0x18005104a  test    eax, eax
0x18005104c  jnz     short loc_180051053
0x18005104e  mov     [rdi], rcx
0x180051051  jmp     short loc_18005107C
0x180051053  mov     rax, [rcx]
0x180051056  mov     r8, rdi
0x180051059  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x180051060  mov     rax, [rax]
0x180051063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051068  mov     ebx, eax
0x18005106a  mov     rcx, qword ptr [rsp+58h+var_38]
0x18005106f  mov     rax, [rcx]
0x180051072  mov     rax, [rax+10h]
0x180051076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005107b  nop
0x18005107c  test    ebx, ebx
0x18005107e  jns     short loc_18005109D
0x180051080  mov     edx, 0BFh; void *
0x180051085  lea     r8, aOnecoreBaseFli_7; "onecore\\base\\flighting\\common\\inc\\"...
0x18005108c  mov     r9d, ebx; char *
0x18005108f  mov     rcx, [rsp+58h]; this
0x180051094  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051099  mov     eax, ebx
0x18005109b  jmp     short loc_1800510EF
0x18005109d  lea     rcx, [rsi+18h]
0x1800510a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800510a6  mov     [rsp+58h+var_18], 0
0x1800510af  mov     r9d, 1Bh; unsigned int
0x1800510b5  lea     r8d, [r9+1]; unsigned int
0x1800510b9  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800510c0  lea     rcx, [rsp+58h+hstringHeader]; hstringHeader
0x1800510c5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800510ca  lea     r8, [rsi+18h]
0x1800510ce  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800510d5  mov     rcx, [rsp+58h+var_18]
0x1800510da  call    cs:__imp_RoGetActivationFactory
0x1800510e0  mov     ebx, eax
0x1800510e2  test    eax, eax
0x1800510e4  jns     short loc_1800510ED
0x1800510e6  mov     edx, 0C2h
0x1800510eb  jmp     short loc_180051085
0x1800510ed  xor     eax, eax
0x1800510ef  mov     rcx, [rsp+58h+var_10]
0x1800510f4  xor     rcx, rsp; StackCookie
0x1800510f7  call    __security_check_cookie
0x1800510fc  mov     rbx, [rsp+58h+arg_8]
0x180051101  mov     rsi, [rsp+58h+arg_10]
0x180051106  add     rsp, 50h
0x18005110a  pop     rdi
0x18005110b  retn
```
