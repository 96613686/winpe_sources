# WinStationOpenServerA

- ea: `0x1800109d0`
- end: `0x180010acf`
- name: `WinStationOpenServerA`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180007890`
- `0x1800109d0`
- `0x180010aec`
- `0x18002fe40`
- `0x18002ff00`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180010a4e`
- `msvcrt!_resetstkoflw` at `0x180010a4e`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180010a92`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180010a92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010ac7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010ac7`

## pseudocode

```c
CPublicBinding *__fastcall WinStationOpenServerA(WCHAR *a1)
{
  const CHAR *v1; // r9
  __int64 v2; // rbx
  __int64 v3; // rax
  ULONG BytesInMultiByteString; // r8d
  unsigned __int64 v5; // rax
  __int64 v6; // rcx
  unsigned __int64 v7; // rcx
  void *v8; // rsp
  void *v9; // rsp
  WCHAR UnicodeString[2]; // [rsp+30h] [rbp+0h] BYREF
  int v12; // [rsp+34h] [rbp+4h]
  ULONG BytesInUnicodeString; // [rsp+38h] [rbp+8h] BYREF
  WCHAR *v14; // [rsp+40h] [rbp+10h]

  v1 = (const CHAR *)a1;
  v2 = 0;
  if ( a1 )
  {
    v3 = -1;
    do
      ++v3;
    while ( *((_BYTE *)a1 + v3) );
    BytesInMultiByteString = v3 + 1;
    v12 = v3 + 1;
    *(_DWORD *)UnicodeString = v3 + 1;
    v5 = 2LL * (unsigned int)(v3 + 1);
    v6 = v5 + 15;
    if ( v5 + 15 < v5 )
      v6 = 0xFFFFFFFFFFFFFF0LL;
    v7 = v6 & 0xFFFFFFFFFFFFFFF0uLL;
    v8 = alloca(v7);
    v9 = alloca(v7);
    v14 = UnicodeString;
    if ( !UnicodeString )
    {
      SetLastError(8u);
      return (CPublicBinding *)v2;
    }
    BytesInUnicodeString = 0;
    RtlMultiByteToUnicodeN(UnicodeString, 2 * BytesInMultiByteString, &BytesInUnicodeString, v1, BytesInMultiByteString);
    a1 = UnicodeString;
  }
  return _tsrpcOpenServer(a1);
}

```

## disassembly

```asm
0x1800109d0  mov     [rsp-8+MultiByteString], rcx
0x1800109d5  push    rbp
0x1800109d6  sub     rsp, 50h
0x1800109da  lea     rbp, [rsp+30h]
0x1800109df  mov     [rbp+20h+arg_8], rbx
0x1800109e3  mov     [rbp+20h+arg_10], rdi
0x1800109e7  mov     rax, cs:__security_cookie
0x1800109ee  xor     rax, rbp
0x1800109f1  mov     [rbp+20h+var_8], rax
0x1800109f5  mov     r9, rcx
0x1800109f8  xor     ebx, ebx
0x1800109fa  test    rcx, rcx
0x1800109fd  jz      loc_180010A9B
0x180010a03  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010a07  inc     rax
0x180010a0a  cmp     [rcx+rax], bl
0x180010a0d  jnz     short loc_180010A07
0x180010a0f  lea     r8d, [rax+1]
0x180010a13  mov     [rbp+20h+var_1C], r8d
0x180010a17  mov     dword ptr [rbp+20h+UnicodeString], r8d
0x180010a1b  mov     eax, r8d
0x180010a1e  add     rax, rax
0x180010a21  lea     rcx, [rax+0Fh]
0x180010a25  cmp     rcx, rax
0x180010a28  ja      short loc_180010A34
0x180010a2a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180010a34  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180010a38  mov     rax, rcx
0x180010a3b  call    _alloca_probe
0x180010a40  sub     rsp, rcx
0x180010a43  lea     rdi, [rsp+50h+UnicodeString]
0x180010a48  mov     [rbp+20h+var_10], rdi
0x180010a4c  jmp     short loc_180010A7A
0x180010a4e  call    cs:__imp__resetstkoflw
0x180010a54  xor     edi, edi
0x180010a56  mov     [rbp+20h+var_10], rdi
0x180010a5a  mov     r8d, dword ptr [rbp+20h+UnicodeString]
0x180010a5e  add     r8, r8
0x180010a61  lea     rdx, aAllocaFailedFo; "alloca failed for %d bytes"
0x180010a68  lea     ecx, [rdi+8]; int
0x180010a6b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180010a70  xor     ebx, ebx
0x180010a72  mov     r9, [rbp+20h+MultiByteString]; MultiByteString
0x180010a76  mov     r8d, [rbp+20h+var_1C]
0x180010a7a  test    rdi, rdi
0x180010a7d  jz      short loc_180010AC2
0x180010a7f  mov     [rbp+20h+BytesInUnicodeString], ebx
0x180010a82  lea     edx, [r8+r8]; MaxBytesInUnicodeString
0x180010a86  mov     [rsp+50h+BytesInMultiByteString], r8d; BytesInMultiByteString
0x180010a8b  lea     r8, [rbp+20h+BytesInUnicodeString]; BytesInUnicodeString
0x180010a8f  mov     rcx, rdi; UnicodeString
0x180010a92  call    cs:__imp_RtlMultiByteToUnicodeN
0x180010a98  mov     rcx, rdi; unsigned __int16 *
0x180010a9b  call    ?_tsrpcOpenServer@@YAPEAXPEBG@Z; _tsrpcOpenServer(ushort const *)
0x180010aa0  mov     rbx, rax
0x180010aa3  mov     rax, rbx
0x180010aa6  mov     rcx, [rbp+20h+var_8]
0x180010aaa  xor     rcx, rbp; StackCookie
0x180010aad  call    __security_check_cookie
0x180010ab2  mov     rbx, [rbp+20h+arg_8]
0x180010ab6  mov     rdi, [rbp+20h+arg_10]
0x180010aba  lea     rsp, [rbp+20h]
0x180010abe  pop     rbp
0x180010abf  retn
0x180010ac0  jmp     short loc_180010A9B
0x180010ac2  mov     ecx, 8; dwErrCode
0x180010ac7  call    cs:__imp_SetLastError
0x180010acd  jmp     short loc_180010AA3
0x18003062c  push    rbp
0x18003062e  sub     rsp, 30h
0x180030632  lea     rbp, [rdx+30h]
0x180030636  mov     rax, [rcx]
0x180030639  xor     ecx, ecx
0x18003063b  cmp     dword ptr [rax], 0C00000FDh
0x180030641  setz    cl
0x180030644  mov     eax, ecx
0x180030646  add     rsp, 30h
0x18003064a  pop     rbp
0x18003064b  retn
```
