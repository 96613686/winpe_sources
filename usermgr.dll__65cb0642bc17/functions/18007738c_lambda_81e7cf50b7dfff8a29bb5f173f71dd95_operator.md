# _lambda_81e7cf50b7dfff8a29bb5f173f71dd95_::operator()

- ea: `0x18007738c`
- end: `0x1800774db`
- name: `_lambda_81e7cf50b7dfff8a29bb5f173f71dd95_::operator()`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180080460`

## callees

- `0x180006130`
- `0x180007920`
- `0x1800088e8`
- `0x180024828`
- `0x18007738c`
- `0x1800ec010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180077493`
- `msvcrt!_wcsicmp` at `0x180077493`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077478`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077487`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077478`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077487`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077446`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800774a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077446`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800774a7`

## string_xrefs

- `0x180077404`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_81e7cf50b7dfff8a29bb5f173f71dd95_::operator()(
        __int64 a1,
        __int64 a2,
        __int64 (__fastcall ***a3)(_QWORD, GUID *, __int64 *),
        _BYTE *a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  const wchar_t *StringRawBuffer; // rbx
  const wchar_t *v11; // rax
  __int64 v13; // [rsp+20h] [rbp-20h] BYREF
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-18h] BYREF
  __int64 v15; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  int v17; // [rsp+7Ch] [rbp+3Ch]
  HSTRING string; // [rsp+80h] [rbp+40h] BYREF

  v17 = HIDWORD(a2);
  v14 = a3;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v14);
  v13 = 0;
  v15 = 0;
  string = 0;
  v6 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
         &v14,
         &v13);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_3;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 80LL))(v13, &v15);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_3;
  if ( v17 == *(_DWORD *)(a1 + 8) && v15 == *(_QWORD *)a1 )
    *a4 = 1;
  if ( *a4 )
  {
LABEL_12:
    v7 = 0;
    goto LABEL_13;
  }
  v8 = v13;
  v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v13 + 72LL);
  WindowsDeleteString(string);
  string = 0;
  v6 = v9(v8, &string);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( v17 == *(_DWORD *)(a1 + 8) )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(**(HSTRING **)(a1 + 16), 0);
      v11 = WindowsGetStringRawBuffer(string, 0);
      if ( !_wcsicmp(v11, StringRawBuffer) )
        *a4 = 1;
    }
    goto LABEL_12;
  }
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x12B,
    (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
    (const char *)(unsigned int)v6,
    v13);
LABEL_13:
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v13);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v14);
  return v7;
}

```

## disassembly

```asm
0x18007738c  mov     [rsp-28h+arg_0], rbx
0x180077391  mov     [rsp-28h+arg_8], rdx
0x180077396  push    rbp
0x180077397  push    rsi
0x180077398  push    rdi
0x180077399  push    r14
0x18007739b  push    r15
0x18007739d  mov     rbp, rsp
0x1800773a0  sub     rsp, 40h
0x1800773a4  mov     r14, r9
0x1800773a7  mov     rsi, rcx
0x1800773aa  mov     [rbp+var_18], r8
0x1800773ae  lea     rcx, [rbp+var_18]
0x1800773b2  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800773b7  nop
0x1800773b8  mov     [rbp+var_20], 0
0x1800773c0  mov     [rbp+var_10], 0
0x1800773c8  mov     [rbp+string], 0
0x1800773d0  lea     rdx, [rbp+var_20]
0x1800773d4  lea     rcx, [rbp+var_18]
0x1800773d8  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x1800773dd  mov     ebx, eax
0x1800773df  test    eax, eax
0x1800773e1  js      short loc_1800773FD
0x1800773e3  mov     rcx, [rbp+var_20]
0x1800773e7  mov     rax, [rcx]
0x1800773ea  lea     rdx, [rbp+var_10]
0x1800773ee  mov     rax, [rax+50h]
0x1800773f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800773f7  mov     ebx, eax
0x1800773f9  test    eax, eax
0x1800773fb  jns     short loc_18007741A
0x1800773fd  mov     rcx, [rbp+28h]; this
0x180077401  mov     r9d, eax; char *
0x180077404  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x18007740b  mov     edx, 12Bh; void *
0x180077410  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077415  jmp     loc_1800774A3
0x18007741a  mov     r15d, dword ptr [rbp+arg_8+4]
0x18007741e  cmp     r15d, [rsi+8]
0x180077422  jnz     short loc_180077431
0x180077424  mov     rax, [rsi]
0x180077427  cmp     [rbp+var_10], rax
0x18007742b  jnz     short loc_180077431
0x18007742d  mov     byte ptr [r14], 1
0x180077431  cmp     byte ptr [r14], 0
0x180077435  jnz     short loc_1800774A1
0x180077437  mov     rdi, [rbp+var_20]
0x18007743b  mov     rax, [rdi]
0x18007743e  mov     rbx, [rax+48h]
0x180077442  mov     rcx, [rbp+string]; string
0x180077446  call    cs:__imp_WindowsDeleteString
0x18007744c  mov     [rbp+string], 0
0x180077454  lea     rdx, [rbp+string]
0x180077458  mov     rcx, rdi
0x18007745b  mov     rax, rbx
0x18007745e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077463  mov     ebx, eax
0x180077465  test    eax, eax
0x180077467  js      short loc_1800773FD
0x180077469  cmp     r15d, [rsi+8]
0x18007746d  jnz     short loc_1800774A1
0x18007746f  mov     rcx, [rsi+10h]
0x180077473  xor     edx, edx; length
0x180077475  mov     rcx, [rcx]; string
0x180077478  call    cs:__imp_WindowsGetStringRawBuffer
0x18007747e  mov     rbx, rax
0x180077481  xor     edx, edx; length
0x180077483  mov     rcx, [rbp+string]; string
0x180077487  call    cs:__imp_WindowsGetStringRawBuffer
0x18007748d  mov     rdx, rbx; String2
0x180077490  mov     rcx, rax; String1
0x180077493  call    cs:__imp__wcsicmp
0x180077499  test    eax, eax
0x18007749b  jnz     short loc_1800774A1
0x18007749d  mov     byte ptr [r14], 1
0x1800774a1  xor     ebx, ebx
0x1800774a3  mov     rcx, [rbp+string]; string
0x1800774a7  call    cs:__imp_WindowsDeleteString
0x1800774ad  mov     [rbp+string], 0
0x1800774b5  lea     rcx, [rbp+var_20]
0x1800774b9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800774be  nop
0x1800774bf  lea     rcx, [rbp+var_18]
0x1800774c3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800774c8  mov     eax, ebx
0x1800774ca  mov     rbx, [rsp+40h+arg_0]
0x1800774cf  add     rsp, 40h
0x1800774d3  pop     r15
0x1800774d5  pop     r14
0x1800774d7  pop     rdi
0x1800774d8  pop     rsi
0x1800774d9  pop     rbp
0x1800774da  retn
```
