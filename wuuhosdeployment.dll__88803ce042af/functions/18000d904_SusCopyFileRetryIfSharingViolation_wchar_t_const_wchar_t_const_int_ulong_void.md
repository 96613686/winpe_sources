# SusCopyFileRetryIfSharingViolation(wchar_t const *,wchar_t const *,int,ulong,void *)

- ea: `0x18000d904`
- end: `0x18000d9e2`
- name: `?SusCopyFileRetryIfSharingViolation@@YAJPEB_W0HKPEAX@Z`
- size: `222`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, LPCWSTR lpNewFileName, BOOL bFailIfExists, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000d28c`
- `0x18001a094`
- `0x18002a83c`
- `0x18003b800`

## callees

- `0x180003950`
- `0x18000d904`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d931`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d931`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d969`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d969`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18000d978`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18000d978`

## pseudocode

```c
__int64 __fastcall SusCopyFileRetryIfSharingViolation(
        LPCWSTR lpExistingFileName,
        LPCWSTR lpNewFileName,
        BOOL bFailIfExists,
        int a4)
{
  BOOL v5; // ebp
  const WCHAR *v6; // r14
  const WCHAR *v7; // r15
  int v8; // esi
  signed int LastError; // eax
  unsigned int v10; // ebx
  unsigned int v11; // edi
  int v12; // eax
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = bFailIfExists;
  v6 = lpNewFileName;
  v7 = lpExistingFileName;
  v8 = 0;
  while ( 1 )
  {
    if ( CopyFileW(lpExistingFileName, lpNewFileName, bFailIfExists) )
      return 0;
    LastError = GetLastError();
    v10 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v10 = LastError;
    if ( (v10 & 0x80000000) == 0 )
      break;
    v11 = v10;
    if ( v10 != -2147024891 && v10 != -2147024864 )
      goto LABEL_13;
    v12 = v8++;
    if ( a4 == v12 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x643,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
        (const char *)v10,
        v14);
      return v10;
    }
    Sleep(0x1F4u);
    bFailIfExists = v5;
    lpNewFileName = v6;
    lpExistingFileName = v7;
  }
  v11 = -2147418113;
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x633,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
    (const char *)v11,
    v14);
  return v11;
}

```

## disassembly

```asm
0x18000d904  mov     rax, rsp
0x18000d907  mov     [rax+8], rbx
0x18000d90b  mov     [rax+10h], rbp
0x18000d90f  mov     [rax+18h], rsi
0x18000d913  mov     [rax+20h], rdi
0x18000d917  push    r12
0x18000d919  push    r14
0x18000d91b  push    r15
0x18000d91d  sub     rsp, 20h
0x18000d921  mov     r12d, r9d
0x18000d924  mov     ebp, r8d
0x18000d927  mov     r14, rdx
0x18000d92a  mov     r15, rcx
0x18000d92d  xor     esi, esi
0x18000d92f  jmp     short loc_18000D978
0x18000d931  call    cs:__imp_GetLastError
0x18000d937  movzx   ebx, ax
0x18000d93a  or      ebx, 80070000h
0x18000d940  test    eax, eax
0x18000d942  cmovle  ebx, eax
0x18000d945  test    ebx, ebx
0x18000d947  jns     short loc_18000D9C0
0x18000d949  mov     edi, ebx
0x18000d94b  cmp     ebx, 80070005h
0x18000d951  jz      short loc_18000D95B
0x18000d953  cmp     ebx, 80070020h
0x18000d959  jnz     short loc_18000D9C5
0x18000d95b  mov     eax, esi
0x18000d95d  inc     esi
0x18000d95f  cmp     r12d, eax
0x18000d962  jz      short loc_18000D9A3
0x18000d964  mov     ecx, 1F4h; dwMilliseconds
0x18000d969  call    cs:__imp_Sleep
0x18000d96f  mov     r8d, ebp; bFailIfExists
0x18000d972  mov     rdx, r14; lpNewFileName
0x18000d975  mov     rcx, r15; lpExistingFileName
0x18000d978  call    cs:__imp_CopyFileW
0x18000d97e  test    eax, eax
0x18000d980  jz      short loc_18000D931
0x18000d982  xor     eax, eax
0x18000d984  mov     rbx, [rsp+38h+arg_0]
0x18000d989  mov     rbp, [rsp+38h+arg_8]
0x18000d98e  mov     rsi, [rsp+38h+arg_10]
0x18000d993  mov     rdi, [rsp+38h+arg_18]
0x18000d998  add     rsp, 20h
0x18000d99c  pop     r15
0x18000d99e  pop     r14
0x18000d9a0  pop     r12
0x18000d9a2  retn
0x18000d9a3  mov     rcx, [rsp+38h]; this
0x18000d9a8  lea     r8, aCW1SSrcClientL_25; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000d9af  mov     r9d, ebx; char *
0x18000d9b2  mov     edx, 643h; void *
0x18000d9b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d9bc  mov     eax, ebx
0x18000d9be  jmp     short loc_18000D984
0x18000d9c0  mov     edi, 8000FFFFh
0x18000d9c5  mov     rcx, [rsp+38h]; this
0x18000d9ca  lea     r8, aCW1SSrcClientL_25; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000d9d1  mov     r9d, edi; char *
0x18000d9d4  mov     edx, 633h; void *
0x18000d9d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d9de  mov     eax, edi
0x18000d9e0  jmp     short loc_18000D984
```
