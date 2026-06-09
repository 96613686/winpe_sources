# WinStationOpenServerA

- ea: `0x180011950`
- end: `0x180011a62`
- name: `WinStationOpenServerA`
- size: `274`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180005b40`
- `0x180011950`
- `0x180011a7c`
- `0x180032c20`
- `0x180032ce0`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800119ce`
- `msvcrt!_resetstkoflw` at `0x1800119ce`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180011a18`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180011a18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011a54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011a54`

## pseudocode

```c
CPublicBinding *__fastcall WinStationOpenServerA(unsigned __int16 *a1)
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
0x180011950  mov     [rsp-8+MultiByteString], rcx
0x180011955  push    rbp
0x180011956  sub     rsp, 50h
0x18001195a  lea     rbp, [rsp+30h]
0x18001195f  mov     [rbp+20h+arg_8], rbx
0x180011963  mov     [rbp+20h+arg_10], rdi
0x180011967  mov     rax, cs:__security_cookie
0x18001196e  xor     rax, rbp
0x180011971  mov     [rbp+20h+var_8], rax
0x180011975  mov     r9, rcx
0x180011978  xor     ebx, ebx
0x18001197a  test    rcx, rcx
0x18001197d  jz      loc_180011A27
0x180011983  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011987  inc     rax
0x18001198a  cmp     [rcx+rax], bl
0x18001198d  jnz     short loc_180011987
0x18001198f  lea     r8d, [rax+1]
0x180011993  mov     [rbp+20h+var_1C], r8d
0x180011997  mov     dword ptr [rbp+20h+UnicodeString], r8d
0x18001199b  mov     eax, r8d
0x18001199e  add     rax, rax
0x1800119a1  lea     rcx, [rax+0Fh]
0x1800119a5  cmp     rcx, rax
0x1800119a8  ja      short loc_1800119B4
0x1800119aa  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800119b4  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800119b8  mov     rax, rcx
0x1800119bb  call    _alloca_probe
0x1800119c0  sub     rsp, rcx
0x1800119c3  lea     rdi, [rsp+50h+UnicodeString]
0x1800119c8  mov     [rbp+20h+var_10], rdi
0x1800119cc  jmp     short loc_180011A00
0x1800119ce  call    cs:__imp__resetstkoflw
0x1800119d5  nop     dword ptr [rax+rax+00h]
0x1800119da  xor     edi, edi
0x1800119dc  mov     [rbp+20h+var_10], rdi
0x1800119e0  mov     r8d, dword ptr [rbp+20h+UnicodeString]
0x1800119e4  add     r8, r8
0x1800119e7  lea     rdx, aAllocaFailedFo; "alloca failed for %d bytes"
0x1800119ee  lea     ecx, [rdi+8]; int
0x1800119f1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800119f6  xor     ebx, ebx
0x1800119f8  mov     r9, [rbp+20h+MultiByteString]; MultiByteString
0x1800119fc  mov     r8d, [rbp+20h+var_1C]
0x180011a00  test    rdi, rdi
0x180011a03  jz      short loc_180011A4F
0x180011a05  mov     [rbp+20h+BytesInUnicodeString], ebx
0x180011a08  lea     edx, [r8+r8]; MaxBytesInUnicodeString
0x180011a0c  mov     [rsp+50h+BytesInMultiByteString], r8d; BytesInMultiByteString
0x180011a11  lea     r8, [rbp+20h+BytesInUnicodeString]; BytesInUnicodeString
0x180011a15  mov     rcx, rdi; UnicodeString
0x180011a18  call    cs:__imp_RtlMultiByteToUnicodeN
0x180011a1f  nop     dword ptr [rax+rax+00h]
0x180011a24  mov     rcx, rdi; unsigned __int16 *
0x180011a27  call    ?_tsrpcOpenServer@@YAPEAXPEBG@Z; _tsrpcOpenServer(ushort const *)
0x180011a2c  mov     rbx, rax
0x180011a2f  mov     rax, rbx
0x180011a32  mov     rcx, [rbp+20h+var_8]
0x180011a36  xor     rcx, rbp; StackCookie
0x180011a39  call    __security_check_cookie
0x180011a3e  mov     rbx, [rbp+20h+arg_8]
0x180011a42  mov     rdi, [rbp+20h+arg_10]
0x180011a46  lea     rsp, [rbp+20h]
0x180011a4a  pop     rbp
0x180011a4b  retn
0x180011a4d  jmp     short loc_180011A27
0x180011a4f  mov     ecx, 8; dwErrCode
0x180011a54  call    cs:__imp_SetLastError
0x180011a5b  nop     dword ptr [rax+rax+00h]
0x180011a60  jmp     short loc_180011A2F
0x180033500  push    rbp
0x180033502  sub     rsp, 30h
0x180033506  lea     rbp, [rdx+30h]
0x18003350a  mov     rax, [rcx]
0x18003350d  xor     ecx, ecx
0x18003350f  cmp     dword ptr [rax], 0C00000FDh
0x180033515  setz    cl
0x180033518  mov     eax, ecx
0x18003351a  add     rsp, 30h
0x18003351e  pop     rbp
0x18003351f  retn
```
