# _lambda_1e912cdb49b6b44d8b45e99cacd4fa77_::operator()

- ea: `0x18001871c`
- end: `0x180018854`
- name: `_lambda_1e912cdb49b6b44d8b45e99cacd4fa77_::operator()`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180049150`

## callees

- `0x180002ad0`
- `0x180006914`
- `0x18001871c`
- `0x18005fa50`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800187c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800187c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800187b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800187fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800187b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800187fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018747`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_1e912cdb49b6b44d8b45e99cacd4fa77_::operator()(_QWORD *a1, HSTRING *a2)
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
      McGenEventWrite_EventWriteTransfer(v8, DataPackage_GetText_Stop, v10, 1);
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
0x18001871c  mov     [rsp+arg_10], rbx
0x180018721  push    rsi
0x180018722  push    rdi
0x180018723  push    r14
0x180018725  sub     rsp, 70h
0x180018729  mov     rax, cs:__security_cookie
0x180018730  xor     rax, rsp
0x180018733  mov     [rsp+88h+var_20], rax
0x180018738  mov     r14, rdx
0x18001873b  mov     rbx, rcx
0x18001873e  mov     rcx, [rcx]
0x180018741  xor     edx, edx; length
0x180018743  mov     rcx, [rcx+8]; string
0x180018747  call    cs:__imp_WindowsGetStringRawBuffer
0x18001874d  mov     rcx, [rbx+8]
0x180018751  lea     rdx, [rcx+40h]
0x180018755  neg     rcx
0x180018758  sbb     rdi, rdi
0x18001875b  and     rdi, rdx
0x18001875e  mov     [rsp+88h+var_30], rax
0x180018763  mov     [rsp+88h+string], 0
0x18001876c  mov     rax, [rdi]
0x18001876f  mov     rbx, [rax+20h]
0x180018773  lea     rdx, [rsp+88h+var_30]
0x180018778  lea     rcx, [rsp+88h+var_50]
0x18001877d  call    ??$?0PEBG@StringReference@Internal@Windows@@QEAA@AEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::StringReference::StringReference(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x180018782  lea     r8, [rsp+88h+string]
0x180018787  mov     rdx, [rax]
0x18001878a  mov     rcx, rdi
0x18001878d  mov     rax, rbx
0x180018790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018795  mov     ebx, eax
0x180018797  test    eax, eax
0x180018799  js      short loc_1800187F4
0x18001879b  mov     rsi, [rsp+88h+string]
0x1800187a0  lea     rdi, [r14+10h]
0x1800187a4  test    rsi, rsi
0x1800187a7  jz      short loc_1800187B0
0x1800187a9  xor     ebx, ebx
0x1800187ab  cmp     rsi, [rdi]
0x1800187ae  jz      short loc_1800187CE
0x1800187b0  mov     rcx, [rdi]; string
0x1800187b3  call    cs:__imp_WindowsDeleteString
0x1800187b9  mov     qword ptr [rdi], 0
0x1800187c0  mov     rdx, rdi; newString
0x1800187c3  mov     rcx, rsi; string
0x1800187c6  call    cs:__imp_WindowsDuplicateString
0x1800187cc  mov     ebx, eax
0x1800187ce  mov     r9d, 1
0x1800187d4  test    cs:Microsoft_Windows_Shell_CoreEnableBits, r9b
0x1800187db  jz      short loc_1800187F4
0x1800187dd  lea     rax, [rsp+88h+var_30]
0x1800187e2  mov     [rsp+88h+var_68], rax
0x1800187e7  lea     rdx, DataPackage_GetText_Stop
0x1800187ee  call    McGenEventWrite_EventWriteTransfer
0x1800187f3  nop
0x1800187f4  mov     rcx, [rsp+88h+string]; string
0x1800187f9  test    rcx, rcx
0x1800187fc  jz      short loc_180018804
0x1800187fe  call    cs:__imp_WindowsDeleteString
0x180018804  test    ebx, ebx
0x180018806  js      short loc_180018834
0x180018808  mov     dword ptr [rsp+88h+string], 0
0x180018810  mov     rcx, [r14]
0x180018813  mov     rax, [rcx]
0x180018816  lea     rdx, [rsp+88h+string]
0x18001881b  mov     rax, [rax+38h]
0x18001881f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018824  test    eax, eax
0x180018826  js      short loc_180018834
0x180018828  cmp     dword ptr [rsp+88h+string], 2
0x18001882d  jnz     short loc_180018834
0x18001882f  mov     ebx, 800704C7h
0x180018834  mov     eax, ebx
0x180018836  mov     rcx, [rsp+88h+var_20]
0x18001883b  xor     rcx, rsp; StackCookie
0x18001883e  call    __security_check_cookie
0x180018843  mov     rbx, [rsp+88h+arg_10]
0x18001884b  add     rsp, 70h
0x18001884f  pop     r14
0x180018851  pop     rdi
0x180018852  pop     rsi
0x180018853  retn
```
