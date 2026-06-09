# _lambda_bafbfff051dad6ffb7db4d5ae30ee9fe_::operator()

- ea: `0x18001a484`
- end: `0x18001a5f6`
- name: `_lambda_bafbfff051dad6ffb7db4d5ae30ee9fe_::operator()`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180049520`

## callees

- `0x180002ad0`
- `0x180006914`
- `0x18001a484`
- `0x18005fa50`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001a536`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001a536`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a527`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a59f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a527`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a59f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a4ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a4ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_bafbfff051dad6ffb7db4d5ae30ee9fe_::operator()(_QWORD *a1, HSTRING *a2)
{
  PCWSTR StringRawBuffer; // rsi
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, HSTRING *); // rbx
  _QWORD *v7; // rax
  __int64 v8; // rcx
  HRESULT v9; // ebx
  __int64 v10; // r8
  HSTRING v11; // r14
  HSTRING *v12; // rdi
  __int64 v13; // rax
  int v14; // eax
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  PCWSTR v17; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v18[16]; // [rsp+40h] [rbp-30h] BYREF
  PCWSTR v19; // [rsp+50h] [rbp-20h]
  int v20; // [rsp+58h] [rbp-18h]
  int v21; // [rsp+5Ch] [rbp-14h]

  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(*a1 + 8LL), 0);
  v5 = (a1[1] + 64LL) & -(__int64)(a1[1] != 0);
  v17 = StringRawBuffer;
  string = 0;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v5 + 32LL);
  v7 = (_QWORD *)Windows::Internal::StringReference::StringReference(v18, &v17);
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
    {
      if ( StringRawBuffer )
      {
        v13 = -1;
        do
          ++v13;
        while ( StringRawBuffer[v13] );
        v14 = 2 * v13 + 2;
      }
      else
      {
        StringRawBuffer = L"NULL";
        v14 = 10;
      }
      v19 = StringRawBuffer;
      v20 = v14;
      v21 = 0;
      McGenEventWrite_EventWriteTransfer(v8, DataPackage_GetCustomText_Stop, v10, 2);
    }
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
0x18001a484  mov     [rsp-28h+arg_10], rbx
0x18001a489  mov     [rsp-28h+arg_18], rsi
0x18001a48e  push    rbp
0x18001a48f  push    rdi
0x18001a490  push    r12
0x18001a492  push    r14
0x18001a494  push    r15
0x18001a496  mov     rbp, rsp
0x18001a499  sub     rsp, 70h
0x18001a49d  mov     rax, cs:__security_cookie
0x18001a4a4  xor     rax, rsp
0x18001a4a7  mov     [rbp+var_10], rax
0x18001a4ab  mov     r15, rdx
0x18001a4ae  mov     rbx, rcx
0x18001a4b1  mov     rcx, [rcx]
0x18001a4b4  xor     edx, edx; length
0x18001a4b6  mov     rcx, [rcx+8]; string
0x18001a4ba  call    cs:__imp_WindowsGetStringRawBuffer
0x18001a4c0  mov     rsi, rax
0x18001a4c3  mov     rax, [rbx+8]
0x18001a4c7  lea     rcx, [rax+40h]
0x18001a4cb  neg     rax
0x18001a4ce  sbb     rdi, rdi
0x18001a4d1  and     rdi, rcx
0x18001a4d4  mov     [rbp+var_38], rsi
0x18001a4d8  xor     r12d, r12d
0x18001a4db  mov     [rbp+string], r12
0x18001a4df  mov     rax, [rdi]
0x18001a4e2  mov     rbx, [rax+20h]
0x18001a4e6  lea     rdx, [rbp+var_38]
0x18001a4ea  lea     rcx, [rbp+var_30]
0x18001a4ee  call    ??$?0PEBG@StringReference@Internal@Windows@@QEAA@AEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::StringReference::StringReference(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x18001a4f3  lea     r8, [rbp+string]
0x18001a4f7  mov     rdx, [rax]
0x18001a4fa  mov     rcx, rdi
0x18001a4fd  mov     rax, rbx
0x18001a500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a505  mov     ebx, eax
0x18001a507  test    eax, eax
0x18001a509  js      loc_18001A596
0x18001a50f  mov     r14, [rbp+string]
0x18001a513  lea     rdi, [r15+10h]
0x18001a517  test    r14, r14
0x18001a51a  jz      short loc_18001A524
0x18001a51c  mov     ebx, r12d
0x18001a51f  cmp     r14, [rdi]
0x18001a522  jz      short loc_18001A53E
0x18001a524  mov     rcx, [rdi]; string
0x18001a527  call    cs:__imp_WindowsDeleteString
0x18001a52d  mov     [rdi], r12
0x18001a530  mov     rdx, rdi; newString
0x18001a533  mov     rcx, r14; string
0x18001a536  call    cs:__imp_WindowsDuplicateString
0x18001a53c  mov     ebx, eax
0x18001a53e  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18001a545  jz      short loc_18001A596
0x18001a547  test    rsi, rsi
0x18001a54a  jz      short loc_18001A563
0x18001a54c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a550  inc     rax
0x18001a553  cmp     [rsi+rax*2], r12w
0x18001a558  jnz     short loc_18001A550
0x18001a55a  lea     eax, ds:2[rax*2]
0x18001a561  jmp     short loc_18001A56F
0x18001a563  lea     rsi, aNull; "NULL"
0x18001a56a  mov     eax, 0Ah
0x18001a56f  mov     [rbp+var_20], rsi
0x18001a573  mov     [rbp+var_18], eax
0x18001a576  mov     [rbp+var_14], r12d
0x18001a57a  lea     rax, [rbp+var_30]
0x18001a57e  mov     [rsp+70h+var_50], rax
0x18001a583  mov     r9d, 2
0x18001a589  lea     rdx, DataPackage_GetCustomText_Stop
0x18001a590  call    McGenEventWrite_EventWriteTransfer
0x18001a595  nop
0x18001a596  mov     rcx, [rbp+string]; string
0x18001a59a  test    rcx, rcx
0x18001a59d  jz      short loc_18001A5A5
0x18001a59f  call    cs:__imp_WindowsDeleteString
0x18001a5a5  test    ebx, ebx
0x18001a5a7  js      short loc_18001A5CF
0x18001a5a9  mov     dword ptr [rbp+string], r12d
0x18001a5ad  mov     rcx, [r15]
0x18001a5b0  mov     rax, [rcx]
0x18001a5b3  lea     rdx, [rbp+string]
0x18001a5b7  mov     rax, [rax+38h]
0x18001a5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5c0  test    eax, eax
0x18001a5c2  js      short loc_18001A5CF
0x18001a5c4  cmp     dword ptr [rbp+string], 2
0x18001a5c8  jnz     short loc_18001A5CF
0x18001a5ca  mov     ebx, 800704C7h
0x18001a5cf  mov     eax, ebx
0x18001a5d1  mov     rcx, [rbp+var_10]
0x18001a5d5  xor     rcx, rsp; StackCookie
0x18001a5d8  call    __security_check_cookie
0x18001a5dd  lea     r11, [rsp+70h+var_s0]
0x18001a5e2  mov     rbx, [r11+40h]
0x18001a5e6  mov     rsi, [r11+48h]
0x18001a5ea  mov     rsp, r11
0x18001a5ed  pop     r15
0x18001a5ef  pop     r14
0x18001a5f1  pop     r12
0x18001a5f3  pop     rdi
0x18001a5f4  pop     rbp
0x18001a5f5  retn
```
