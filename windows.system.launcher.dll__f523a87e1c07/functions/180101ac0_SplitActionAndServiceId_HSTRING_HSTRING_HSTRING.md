# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x180101ac0`
- end: `0x180101b94`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `212`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180102310`

## callees

- `0x180101ac0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180101b09`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180101b09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180101af9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180101af9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180101b39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180101b39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101b23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101b41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101b6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101b79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101b23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101b41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101b6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101b79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180101b52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180101b52`

## pseudocode

```c
__int64 __fastcall SplitActionAndServiceId(HSTRING string, HSTRING *a2, HSTRING *a3)
{
  unsigned int v5; // edi
  const wchar_t *StringRawBuffer; // rax
  size_t v7; // r14
  HRESULT v8; // eax
  HSTRING stringa; // [rsp+48h] [rbp+28h] BYREF
  HSTRING *length; // [rsp+50h] [rbp+30h] BYREF

  length = a3;
  if ( a2 )
    *a2 = 0;
  v5 = 0;
  stringa = 0;
  LODWORD(length) = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, (UINT32 *)&length);
  v7 = wcscspn(StringRawBuffer, L"+");
  if ( a2 )
  {
    if ( v7 >= (unsigned int)length )
    {
      WindowsDeleteString(stringa);
      stringa = 0;
      v8 = WindowsDuplicateString(string, &stringa);
    }
    else
    {
      WindowsDeleteString(stringa);
      stringa = 0;
      v8 = WindowsSubstringWithSpecifiedLength(string, 0, v7, &stringa);
    }
    v5 = v8;
    if ( v8 >= 0 )
    {
      *a2 = stringa;
      stringa = 0;
    }
  }
  WindowsDeleteString(0);
  WindowsDeleteString(stringa);
  return v5;
}

```

## disassembly

```asm
0x180101ac0  mov     [rsp-18h+arg_0], rbx
0x180101ac5  mov     [rsp-18h+arg_18], rsi
0x180101aca  mov     [rsp-18h+length], r8
0x180101acf  push    rbp
0x180101ad0  push    rdi
0x180101ad1  push    r14
0x180101ad3  mov     rbp, rsp
0x180101ad6  sub     rsp, 20h
0x180101ada  mov     rbx, rdx
0x180101add  mov     rsi, rcx
0x180101ae0  test    rdx, rdx
0x180101ae3  jz      short loc_180101AEC
0x180101ae5  mov     qword ptr [rdx], 0
0x180101aec  xor     edi, edi
0x180101aee  lea     rdx, [rbp+length]; length
0x180101af2  mov     [rbp+string], rdi
0x180101af6  mov     dword ptr [rbp+length], edi
0x180101af9  call    cs:__imp_WindowsGetStringRawBuffer
0x180101aff  mov     rcx, rax; String
0x180101b02  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; "+"
0x180101b09  call    cs:__imp_wcscspn
0x180101b0f  mov     r14, rax
0x180101b12  test    rbx, rbx
0x180101b15  jz      short loc_180101B6D
0x180101b17  mov     eax, dword ptr [rbp+length]
0x180101b1a  mov     rcx, [rbp+string]; string
0x180101b1e  cmp     r14, rax
0x180101b21  jnb     short loc_180101B41
0x180101b23  call    cs:__imp_WindowsDeleteString
0x180101b29  mov     r8d, r14d; length
0x180101b2c  mov     [rbp+string], rdi
0x180101b30  lea     r9, [rbp+string]; newString
0x180101b34  xor     edx, edx; startIndex
0x180101b36  mov     rcx, rsi; string
0x180101b39  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x180101b3f  jmp     short loc_180101B58
0x180101b41  call    cs:__imp_WindowsDeleteString
0x180101b47  lea     rdx, [rbp+string]; newString
0x180101b4b  mov     [rbp+string], rdi
0x180101b4f  mov     rcx, rsi; string
0x180101b52  call    cs:__imp_WindowsDuplicateString
0x180101b58  mov     edi, eax
0x180101b5a  test    eax, eax
0x180101b5c  js      short loc_180101B6D
0x180101b5e  mov     rax, [rbp+string]
0x180101b62  mov     [rbx], rax
0x180101b65  mov     [rbp+string], 0
0x180101b6d  xor     ecx, ecx; string
0x180101b6f  call    cs:__imp_WindowsDeleteString
0x180101b75  mov     rcx, [rbp+string]; string
0x180101b79  call    cs:__imp_WindowsDeleteString
0x180101b7f  mov     rbx, [rsp+20h+arg_0]
0x180101b84  mov     eax, edi
0x180101b86  mov     rsi, [rsp+20h+arg_18]
0x180101b8b  add     rsp, 20h
0x180101b8f  pop     r14
0x180101b91  pop     rdi
0x180101b92  pop     rbp
0x180101b93  retn
```
