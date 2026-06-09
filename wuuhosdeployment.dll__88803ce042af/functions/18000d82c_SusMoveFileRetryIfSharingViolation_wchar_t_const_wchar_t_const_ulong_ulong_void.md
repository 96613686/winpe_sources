# SusMoveFileRetryIfSharingViolation(wchar_t const *,wchar_t const *,ulong,ulong,void *)

- ea: `0x18000d82c`
- end: `0x18000d8fc`
- name: `?SusMoveFileRetryIfSharingViolation@@YAJPEB_W0KKPEAX@Z`
- size: `208`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, LPCWSTR lpNewFileName, DWORD dwFlags, unsigned int, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000d28c`

## callees

- `0x180003950`
- `0x18000d82c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d851`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d851`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d889`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d889`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000d898`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000d898`

## pseudocode

```c
__int64 __fastcall SusMoveFileRetryIfSharingViolation(LPCWSTR lpExistingFileName, LPCWSTR lpNewFileName, DWORD dwFlags)
{
  DWORD v3; // ebp
  const WCHAR *v4; // r14
  const WCHAR *v5; // r15
  int v6; // esi
  signed int LastError; // eax
  unsigned int v8; // ebx
  unsigned int v9; // edi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = dwFlags;
  v4 = lpNewFileName;
  v5 = lpExistingFileName;
  v6 = 0;
  while ( 1 )
  {
    if ( MoveFileExW(lpExistingFileName, lpNewFileName, dwFlags) )
      return 0;
    LastError = GetLastError();
    v8 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v8 = LastError;
    if ( (v8 & 0x80000000) == 0 )
      break;
    v9 = v8;
    if ( v8 != -2147024891 && v8 != -2147024864 )
      goto LABEL_13;
    v10 = v6++;
    if ( v10 == 10 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F1,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
        (const char *)v8,
        v12);
      return v8;
    }
    Sleep(0x1F4u);
    dwFlags = v3;
    lpNewFileName = v4;
    lpExistingFileName = v5;
  }
  v9 = -2147418113;
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E1,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
    (const char *)v9,
    v12);
  return v9;
}

```

## disassembly

```asm
0x18000d82c  mov     [rsp+arg_0], rbx
0x18000d831  mov     [rsp+arg_8], rbp
0x18000d836  mov     [rsp+arg_10], rsi
0x18000d83b  push    rdi
0x18000d83c  push    r14
0x18000d83e  push    r15
0x18000d840  sub     rsp, 20h
0x18000d844  mov     ebp, r8d
0x18000d847  mov     r14, rdx
0x18000d84a  mov     r15, rcx
0x18000d84d  xor     esi, esi
0x18000d84f  jmp     short loc_18000D898
0x18000d851  call    cs:__imp_GetLastError
0x18000d857  movzx   ebx, ax
0x18000d85a  or      ebx, 80070000h
0x18000d860  test    eax, eax
0x18000d862  cmovle  ebx, eax
0x18000d865  test    ebx, ebx
0x18000d867  jns     short loc_18000D8DA
0x18000d869  mov     edi, ebx
0x18000d86b  cmp     ebx, 80070005h
0x18000d871  jz      short loc_18000D87B
0x18000d873  cmp     ebx, 80070020h
0x18000d879  jnz     short loc_18000D8DF
0x18000d87b  mov     eax, esi
0x18000d87d  inc     esi
0x18000d87f  cmp     eax, 0Ah
0x18000d882  jz      short loc_18000D8BD
0x18000d884  mov     ecx, 1F4h; dwMilliseconds
0x18000d889  call    cs:__imp_Sleep
0x18000d88f  mov     r8d, ebp; dwFlags
0x18000d892  mov     rdx, r14; lpNewFileName
0x18000d895  mov     rcx, r15; lpExistingFileName
0x18000d898  call    cs:__imp_MoveFileExW
0x18000d89e  test    eax, eax
0x18000d8a0  jz      short loc_18000D851
0x18000d8a2  xor     eax, eax
0x18000d8a4  mov     rbx, [rsp+38h+arg_0]
0x18000d8a9  mov     rbp, [rsp+38h+arg_8]
0x18000d8ae  mov     rsi, [rsp+38h+arg_10]
0x18000d8b3  add     rsp, 20h
0x18000d8b7  pop     r15
0x18000d8b9  pop     r14
0x18000d8bb  pop     rdi
0x18000d8bc  retn
0x18000d8bd  mov     rcx, [rsp+38h]; this
0x18000d8c2  lea     r8, aCW1SSrcClientL_25; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000d8c9  mov     r9d, ebx; char *
0x18000d8cc  mov     edx, 5F1h; void *
0x18000d8d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d8d6  mov     eax, ebx
0x18000d8d8  jmp     short loc_18000D8A4
0x18000d8da  mov     edi, 8000FFFFh
0x18000d8df  mov     rcx, [rsp+38h]; this
0x18000d8e4  lea     r8, aCW1SSrcClientL_25; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000d8eb  mov     r9d, edi; char *
0x18000d8ee  mov     edx, 5E1h; void *
0x18000d8f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d8f8  mov     eax, edi
0x18000d8fa  jmp     short loc_18000D8A4
```
