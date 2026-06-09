# CReverseConverterMTF::Initialize(void)

- ea: `0x1800e0e50`
- end: `0x1800e0f4d`
- name: `?Initialize@CReverseConverterMTF@@UEAAJXZ`
- size: `253`
- prototype: `__int64 __fastcall(CReverseConverterMTF *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800034b0`
- `0x1800040b8`
- `0x1800b36c4`
- `0x1800dca50`
- `0x1800e0e50`
- `0x180102010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800e0f20`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e0f20`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e0ecc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e0ecc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CReverseConverterMTF::Initialize(CReverseConverterMTF *this)
{
  __int64 v2; // r8
  __int64 v3; // rcx
  _QWORD *v4; // rsi
  HRESULT Instance; // edi
  OLECHAR *v6; // rbx
  BSTR bstrString[2]; // [rsp+30h] [rbp-78h] BYREF
  int v9; // [rsp+40h] [rbp-68h] BYREF
  __int16 v10; // [rsp+44h] [rbp-64h]
  OLECHAR *v11; // [rsp+80h] [rbp-28h]

  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"reg://JapanesePhonetic.dgml");
  v3 = *((_QWORD *)this + 1);
  if ( v3 && (*(_BYTE *)(*(_QWORD *)(v3 + 56) + 2LL) & 2) != 0 )
    McTemplateMofU0d(v3 + 8, MTFReverseConverterInitializedEvent, v2, 0);
  v4 = (_QWORD *)((char *)this + 24);
  Instance = CoCreateInstance(
               &CLSID_MtfSuggestionClient,
               0,
               0x17u,
               &GUID_f7445657_fc22_11e3_a6ad_b4b52fe06611,
               (LPVOID *)this + 3);
  v6 = bstrString[0];
  if ( Instance >= 0 )
  {
    memset_0(&v9, 0, 0x50u);
    v9 = 33;
    v10 = 1041;
    v11 = v6;
    Instance = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v4 + 48LL))(*v4, &v9);
  }
  SysFreeString(v6);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800e0e50  mov     [rsp+arg_8], rbx
0x1800e0e55  mov     [rsp+arg_10], rsi
0x1800e0e5a  push    rdi
0x1800e0e5b  sub     rsp, 0A0h
0x1800e0e62  mov     rax, cs:__security_cookie
0x1800e0e69  xor     rax, rsp
0x1800e0e6c  mov     [rsp+0A8h+var_18], rax
0x1800e0e74  mov     rbx, rcx
0x1800e0e77  lea     rdx, aRegJapanesepho; "reg://JapanesePhonetic.dgml"
0x1800e0e7e  lea     rcx, [rsp+0A8h+bstrString]; this
0x1800e0e83  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800e0e88  nop
0x1800e0e89  mov     rcx, [rbx+8]
0x1800e0e8d  test    rcx, rcx
0x1800e0e90  jz      short loc_1800E0EAF
0x1800e0e92  mov     rax, [rcx+38h]
0x1800e0e96  test    byte ptr [rax+2], 2
0x1800e0e9a  jz      short loc_1800E0EAF
0x1800e0e9c  add     rcx, 8
0x1800e0ea0  xor     r9d, r9d
0x1800e0ea3  lea     rdx, MTFReverseConverterInitializedEvent
0x1800e0eaa  call    McTemplateMofU0d
0x1800e0eaf  lea     rsi, [rbx+18h]
0x1800e0eb3  mov     [rsp+0A8h+ppv], rsi; ppv
0x1800e0eb8  lea     r9, _GUID_f7445657_fc22_11e3_a6ad_b4b52fe06611; riid
0x1800e0ebf  xor     edx, edx; pUnkOuter
0x1800e0ec1  lea     r8d, [rdx+17h]; dwClsContext
0x1800e0ec5  lea     rcx, CLSID_MtfSuggestionClient; rclsid
0x1800e0ecc  call    cs:__imp_CoCreateInstance
0x1800e0ed2  mov     edi, eax
0x1800e0ed4  mov     rbx, [rsp+0A8h+bstrString]
0x1800e0ed9  test    eax, eax
0x1800e0edb  js      short loc_1800E0F1D
0x1800e0edd  xor     edx, edx; Val
0x1800e0edf  lea     r8d, [rdx+50h]; Size
0x1800e0ee3  lea     rcx, [rsp+0A8h+var_68]; void *
0x1800e0ee8  call    memset_0
0x1800e0eed  mov     [rsp+0A8h+var_68], 21h ; '!'
0x1800e0ef5  mov     eax, 411h
0x1800e0efa  mov     [rsp+0A8h+var_64], ax
0x1800e0eff  mov     [rsp+0A8h+var_28], rbx
0x1800e0f07  mov     rcx, [rsi]
0x1800e0f0a  mov     rax, [rcx]
0x1800e0f0d  lea     rdx, [rsp+0A8h+var_68]
0x1800e0f12  mov     rax, [rax+30h]
0x1800e0f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0f1b  mov     edi, eax
0x1800e0f1d  mov     rcx, rbx; bstrString
0x1800e0f20  call    cs:__imp_SysFreeString
0x1800e0f26  mov     eax, edi
0x1800e0f28  mov     rcx, [rsp+0A8h+var_18]
0x1800e0f30  xor     rcx, rsp; StackCookie
0x1800e0f33  call    __security_check_cookie
0x1800e0f38  lea     r11, [rsp+0A8h+var_8]
0x1800e0f40  mov     rbx, [r11+18h]
0x1800e0f44  mov     rsi, [r11+20h]
0x1800e0f48  mov     rsp, r11
0x1800e0f4b  pop     rdi
0x1800e0f4c  retn
```
