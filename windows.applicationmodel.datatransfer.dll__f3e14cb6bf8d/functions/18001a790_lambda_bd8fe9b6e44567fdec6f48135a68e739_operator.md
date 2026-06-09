# _lambda_bd8fe9b6e44567fdec6f48135a68e739_::operator()

- ea: `0x18001a790`
- end: `0x18001a8c8`
- name: `_lambda_bd8fe9b6e44567fdec6f48135a68e739_::operator()`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180049560`

## callees

- `0x180002ad0`
- `0x180006914`
- `0x18001a790`
- `0x18005fa50`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001a83a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001a83a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a872`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a872`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a7bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a7bb`

## pseudocode

```c
__int64 __fastcall lambda_bd8fe9b6e44567fdec6f48135a68e739_::operator()(_QWORD *a1, HSTRING *a2)
{
  PCWSTR StringRawBuffer; // rax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, HSTRING *); // rbx
  _QWORD *v7; // rax
  __int64 v8; // rcx
  HRESULT v9; // ebx
  __int64 v10; // r8
  HSTRING v11; // rsi
  HSTRING *v12; // rdi
  HSTRING string; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v15[32]; // [rsp+38h] [rbp-50h] BYREF
  PCWSTR v16[2]; // [rsp+58h] [rbp-30h] BYREF

  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(*a1 + 8LL), 0);
  v5 = (a1[1] + 64LL) & -(__int64)(a1[1] != 0);
  v16[0] = StringRawBuffer;
  string = 0;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v5 + 32LL);
  v7 = (_QWORD *)Windows::Internal::StringReference::StringReference(v15, v16);
  v9 = v6(v5, *v7, &string);
  if ( v9 >= 0 )
  {
    v11 = string;
    v12 = a2 + 2;
    if ( !string || (v9 = 0, string != *v12) )
    {
      WindowsDeleteString(*v12);
      *v12 = 0;
      v9 = WindowsDuplicateString(v11, a2 + 2);
    }
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v8, DataPackage_GetRtf_Stop, v10, 1);
  }
  if ( string )
    WindowsDeleteString(string);
  if ( v9 >= 0 )
  {
    LODWORD(string) = 0;
    if ( (*(int (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)*a2 + 56LL))(*a2, &string) >= 0 && (_DWORD)string == 2 )
      return (unsigned int)-2147023673;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001a790  mov     [rsp+arg_10], rbx
0x18001a795  push    rsi
0x18001a796  push    rdi
0x18001a797  push    r14
0x18001a799  sub     rsp, 70h
0x18001a79d  mov     rax, cs:__security_cookie
0x18001a7a4  xor     rax, rsp
0x18001a7a7  mov     [rsp+88h+var_20], rax
0x18001a7ac  mov     r14, rdx
0x18001a7af  mov     rbx, rcx
0x18001a7b2  mov     rcx, [rcx]
0x18001a7b5  xor     edx, edx; length
0x18001a7b7  mov     rcx, [rcx+8]; string
0x18001a7bb  call    cs:__imp_WindowsGetStringRawBuffer
0x18001a7c1  mov     rcx, [rbx+8]
0x18001a7c5  lea     rdx, [rcx+40h]
0x18001a7c9  neg     rcx
0x18001a7cc  sbb     rdi, rdi
0x18001a7cf  and     rdi, rdx
0x18001a7d2  mov     [rsp+88h+var_30], rax
0x18001a7d7  mov     [rsp+88h+string], 0
0x18001a7e0  mov     rax, [rdi]
0x18001a7e3  mov     rbx, [rax+20h]
0x18001a7e7  lea     rdx, [rsp+88h+var_30]
0x18001a7ec  lea     rcx, [rsp+88h+var_50]
0x18001a7f1  call    ??$?0PEBG@StringReference@Internal@Windows@@QEAA@AEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::StringReference::StringReference(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x18001a7f6  lea     r8, [rsp+88h+string]
0x18001a7fb  mov     rdx, [rax]
0x18001a7fe  mov     rcx, rdi
0x18001a801  mov     rax, rbx
0x18001a804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a809  mov     ebx, eax
0x18001a80b  test    eax, eax
0x18001a80d  js      short loc_18001A868
0x18001a80f  mov     rsi, [rsp+88h+string]
0x18001a814  lea     rdi, [r14+10h]
0x18001a818  test    rsi, rsi
0x18001a81b  jz      short loc_18001A824
0x18001a81d  xor     ebx, ebx
0x18001a81f  cmp     rsi, [rdi]
0x18001a822  jz      short loc_18001A842
0x18001a824  mov     rcx, [rdi]; string
0x18001a827  call    cs:__imp_WindowsDeleteString
0x18001a82d  mov     qword ptr [rdi], 0
0x18001a834  mov     rdx, rdi; newString
0x18001a837  mov     rcx, rsi; string
0x18001a83a  call    cs:__imp_WindowsDuplicateString
0x18001a840  mov     ebx, eax
0x18001a842  mov     r9d, 1
0x18001a848  test    cs:Microsoft_Windows_Shell_CoreEnableBits, r9b
0x18001a84f  jz      short loc_18001A868
0x18001a851  lea     rax, [rsp+88h+var_30]
0x18001a856  mov     [rsp+88h+var_68], rax
0x18001a85b  lea     rdx, DataPackage_GetRtf_Stop
0x18001a862  call    McGenEventWrite_EventWriteTransfer
0x18001a867  nop
0x18001a868  mov     rcx, [rsp+88h+string]; string
0x18001a86d  test    rcx, rcx
0x18001a870  jz      short loc_18001A878
0x18001a872  call    cs:__imp_WindowsDeleteString
0x18001a878  test    ebx, ebx
0x18001a87a  js      short loc_18001A8A8
0x18001a87c  mov     dword ptr [rsp+88h+string], 0
0x18001a884  mov     rcx, [r14]
0x18001a887  mov     rax, [rcx]
0x18001a88a  lea     rdx, [rsp+88h+string]
0x18001a88f  mov     rax, [rax+38h]
0x18001a893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a898  test    eax, eax
0x18001a89a  js      short loc_18001A8A8
0x18001a89c  cmp     dword ptr [rsp+88h+string], 2
0x18001a8a1  jnz     short loc_18001A8A8
0x18001a8a3  mov     ebx, 800704C7h
0x18001a8a8  mov     eax, ebx
0x18001a8aa  mov     rcx, [rsp+88h+var_20]
0x18001a8af  xor     rcx, rsp; StackCookie
0x18001a8b2  call    __security_check_cookie
0x18001a8b7  mov     rbx, [rsp+88h+arg_10]
0x18001a8bf  add     rsp, 70h
0x18001a8c3  pop     r14
0x18001a8c5  pop     rdi
0x18001a8c6  pop     rsi
0x18001a8c7  retn
```
