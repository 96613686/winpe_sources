# _lambda_82aeda0eb981798ba1c51fd8a873b09e_::operator()

- ea: `0x1800774e4`
- end: `0x1800775fa`
- name: `_lambda_82aeda0eb981798ba1c51fd8a873b09e_::operator()`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180080480`

## callees

- `0x180006130`
- `0x180007920`
- `0x1800088e8`
- `0x180024828`
- `0x1800774e4`
- `0x1800ec010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800775b0`
- `msvcrt!_wcsicmp` at `0x1800775b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077595`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800775a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077595`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800775a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800775c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800775c4`

## string_xrefs

- `0x18007756e`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`

## pseudocode

```c
__int64 __fastcall lambda_82aeda0eb981798ba1c51fd8a873b09e_::operator()(
        __int64 a1,
        __int64 a2,
        __int64 (__fastcall ***a3)(_QWORD, GUID *, __int64 *),
        _BYTE *a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  const wchar_t *StringRawBuffer; // rbx
  const wchar_t *v12; // rax
  __int64 v14; // [rsp+20h] [rbp-10h] BYREF
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  int v17; // [rsp+5Ch] [rbp+2Ch]
  HSTRING string; // [rsp+60h] [rbp+30h] BYREF

  v17 = HIDWORD(a2);
  v15 = a3;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v15);
  v14 = 0;
  string = 0;
  v6 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
         &v15,
         &v14);
  v7 = v6;
  if ( v6 >= 0
    && (v8 = v14,
        v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v14 + 72LL),
        WindowsDeleteString(string),
        string = 0,
        v6 = v9(v8, &string),
        v7 = v6,
        v6 >= 0) )
  {
    v10 = *(_DWORD *)(a1 + 8);
    if ( v17 == v10 || !v10 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(**(HSTRING **)a1, 0);
      v12 = WindowsGetStringRawBuffer(string, 0);
      if ( !_wcsicmp(v12, StringRawBuffer) )
        *a4 = 1;
    }
    v7 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x651,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
      (const char *)(unsigned int)v6,
      v14);
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v14);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v15);
  return v7;
}

```

## disassembly

```asm
0x1800774e4  mov     [rsp-18h+arg_0], rbx
0x1800774e9  mov     [rsp-18h+arg_18], rsi
0x1800774ee  mov     [rsp-18h+arg_8], rdx
0x1800774f3  push    rbp
0x1800774f4  push    rdi
0x1800774f5  push    r14
0x1800774f7  mov     rbp, rsp
0x1800774fa  sub     rsp, 30h
0x1800774fe  mov     r14, r9
0x180077501  mov     rsi, rcx
0x180077504  mov     [rbp+var_8], r8
0x180077508  lea     rcx, [rbp+var_8]
0x18007750c  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180077511  nop
0x180077512  mov     [rbp+var_10], 0
0x18007751a  mov     [rbp+string], 0
0x180077522  lea     rdx, [rbp+var_10]
0x180077526  lea     rcx, [rbp+var_8]
0x18007752a  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x18007752f  mov     ebx, eax
0x180077531  test    eax, eax
0x180077533  js      short loc_180077567
0x180077535  mov     rdi, [rbp+var_10]
0x180077539  mov     rax, [rdi]
0x18007753c  mov     rbx, [rax+48h]
0x180077540  mov     rcx, [rbp+string]; string
0x180077544  call    cs:__imp_WindowsDeleteString
0x18007754a  mov     [rbp+string], 0
0x180077552  lea     rdx, [rbp+string]
0x180077556  mov     rcx, rdi
0x180077559  mov     rax, rbx
0x18007755c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077561  mov     ebx, eax
0x180077563  test    eax, eax
0x180077565  jns     short loc_180077581
0x180077567  mov     rcx, [rbp+18h]; this
0x18007756b  mov     r9d, eax; char *
0x18007756e  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180077575  mov     edx, 651h; void *
0x18007757a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007757f  jmp     short loc_1800775C0
0x180077581  mov     eax, [rsi+8]
0x180077584  cmp     dword ptr [rbp+arg_8+4], eax
0x180077587  jz      short loc_18007758D
0x180077589  test    eax, eax
0x18007758b  jnz     short loc_1800775BE
0x18007758d  mov     rcx, [rsi]
0x180077590  xor     edx, edx; length
0x180077592  mov     rcx, [rcx]; string
0x180077595  call    cs:__imp_WindowsGetStringRawBuffer
0x18007759b  mov     rbx, rax
0x18007759e  xor     edx, edx; length
0x1800775a0  mov     rcx, [rbp+string]; string
0x1800775a4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800775aa  mov     rdx, rbx; String2
0x1800775ad  mov     rcx, rax; String1
0x1800775b0  call    cs:__imp__wcsicmp
0x1800775b6  test    eax, eax
0x1800775b8  jnz     short loc_1800775BE
0x1800775ba  mov     byte ptr [r14], 1
0x1800775be  xor     ebx, ebx
0x1800775c0  mov     rcx, [rbp+string]; string
0x1800775c4  call    cs:__imp_WindowsDeleteString
0x1800775ca  mov     [rbp+string], 0
0x1800775d2  lea     rcx, [rbp+var_10]
0x1800775d6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800775db  nop
0x1800775dc  lea     rcx, [rbp+var_8]
0x1800775e0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800775e5  mov     eax, ebx
0x1800775e7  mov     rbx, [rsp+30h+arg_0]
0x1800775ec  mov     rsi, [rsp+30h+arg_18]
0x1800775f1  add     rsp, 30h
0x1800775f5  pop     r14
0x1800775f7  pop     rdi
0x1800775f8  pop     rbp
0x1800775f9  retn
```
