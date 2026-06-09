# KvpEncoderJson::FinalizeCoTaskMemAlloc(ushort * *)

- ea: `0x1800505d0`
- end: `0x1800506cf`
- name: `?FinalizeCoTaskMemAlloc@KvpEncoderJson@@UEAAJPEAPEAG@Z`
- size: `255`
- prototype: `__int64 __fastcall(KvpEncoderJson *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000e5ac`
- `0x180010130`
- `0x180019d84`
- `0x1800505d0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800505f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800506be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800505f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800506be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050651`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050651`

## string_xrefs

- `0x18005061d`: `onecore\base\flighting\common\inc\KvpEncoder.h`
- `0x180050674`: `onecore\base\flighting\common\inc\KvpEncoder.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KvpEncoderJson::FinalizeCoTaskMemAlloc(KvpEncoderJson *this, unsigned __int16 **a2)
{
  __int64 (__fastcall *v4)(KvpEncoderJson *, HSTRING *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  PCWSTR StringRawBuffer; // rax
  int v8; // eax
  unsigned __int16 *v9; // rax
  unsigned __int16 *v11; // [rsp+20h] [rbp-28h] BYREF
  __int64 v12; // [rsp+28h] [rbp-20h]
  __int64 v13; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  HSTRING string; // [rsp+70h] [rbp+28h] BYREF

  string = 0;
  v4 = *(__int64 (__fastcall **)(KvpEncoderJson *, HSTRING *))(*(_QWORD *)this + 40LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(this, &string);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v11 = 0;
    v12 = 0;
    v13 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
           &v11,
           StringRawBuffer,
           -1);
    v6 = v8;
    if ( v8 >= 0 )
    {
      v9 = v11;
      v11 = 0;
      v13 = 0;
      v12 = 0;
      *a2 = v9;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v11);
      v6 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
        (const char *)(unsigned int)v8,
        (int)v11);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v11);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE3,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
      (const char *)(unsigned int)v5,
      (int)v11);
  }
  WindowsDeleteString(string);
  return v6;
}

```

## disassembly

```asm
0x1800505d0  push    rbp
0x1800505d2  push    rbx
0x1800505d3  push    rsi
0x1800505d4  push    rdi
0x1800505d5  mov     rbp, rsp
0x1800505d8  sub     rsp, 48h
0x1800505dc  mov     rsi, rdx
0x1800505df  mov     rdi, rcx
0x1800505e2  mov     [rbp+string], 0
0x1800505ea  mov     rax, [rcx]
0x1800505ed  mov     rbx, [rax+28h]
0x1800505f1  xor     ecx, ecx; string
0x1800505f3  call    cs:__imp_WindowsDeleteString
0x1800505f9  mov     [rbp+string], 0
0x180050601  lea     rdx, [rbp+string]
0x180050605  mov     rcx, rdi
0x180050608  mov     rax, rbx
0x18005060b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050610  mov     ebx, eax
0x180050612  test    eax, eax
0x180050614  jns     short loc_180050633
0x180050616  mov     rcx, [rbp+20h]; this
0x18005061a  mov     r9d, eax; char *
0x18005061d  lea     r8, aOnecoreBaseFli_7; "onecore\\base\\flighting\\common\\inc\\"...
0x180050624  mov     edx, 0E3h; void *
0x180050629  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005062e  jmp     loc_1800506BA
0x180050633  mov     [rbp+var_28], 0
0x18005063b  mov     [rbp+var_20], 0
0x180050643  mov     [rbp+var_18], 0
0x18005064b  xor     edx, edx; length
0x18005064d  mov     rcx, [rbp+string]; string
0x180050651  call    cs:__imp_WindowsGetStringRawBuffer
0x180050657  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005065b  mov     rdx, rax
0x18005065e  lea     rcx, [rbp+var_28]
0x180050662  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180050667  mov     ebx, eax
0x180050669  test    eax, eax
0x18005066b  jns     short loc_180050690
0x18005066d  mov     rcx, [rbp+20h]; this
0x180050671  mov     r9d, eax; char *
0x180050674  lea     r8, aOnecoreBaseFli_7; "onecore\\base\\flighting\\common\\inc\\"...
0x18005067b  mov     edx, 0E7h; void *
0x180050680  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050685  lea     rcx, [rbp+var_28]
0x180050689  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005068e  jmp     short loc_1800506BA
0x180050690  mov     rax, [rbp+var_28]
0x180050694  mov     [rbp+var_28], 0
0x18005069c  mov     [rbp+var_18], 0
0x1800506a4  mov     [rbp+var_20], 0
0x1800506ac  mov     [rsi], rax
0x1800506af  lea     rcx, [rbp+var_28]
0x1800506b3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800506b8  xor     ebx, ebx
0x1800506ba  mov     rcx, [rbp+string]; string
0x1800506be  call    cs:__imp_WindowsDeleteString
0x1800506c4  mov     eax, ebx
0x1800506c6  add     rsp, 48h
0x1800506ca  pop     rdi
0x1800506cb  pop     rsi
0x1800506cc  pop     rbx
0x1800506cd  pop     rbp
0x1800506ce  retn
```
