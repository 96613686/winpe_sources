# WinStationOpenServerExA

- ea: `0x180024650`
- end: `0x18002474b`
- name: `WinStationOpenServerExA`
- size: `251`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180007890`
- `0x180013910`
- `0x180024650`
- `0x18002fe40`
- `0x18002ff00`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800246ce`
- `msvcrt!_resetstkoflw` at `0x1800246ce`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18002471d`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18002471d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024702`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024702`

## pseudocode

```c
CPublicBinding *__fastcall WinStationOpenServerExA(unsigned __int16 *a1)
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
  if ( !a1 )
    return WinStationOpenServerExW(a1);
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
  if ( UnicodeString )
  {
    BytesInUnicodeString = 0;
    RtlMultiByteToUnicodeN(UnicodeString, 2 * BytesInMultiByteString, &BytesInUnicodeString, v1, BytesInMultiByteString);
    a1 = UnicodeString;
    return WinStationOpenServerExW(a1);
  }
  SetLastError(8u);
  return (CPublicBinding *)v2;
}

```

## disassembly

```asm
0x180024650  mov     [rsp-8+MultiByteString], rcx
0x180024655  push    rbp
0x180024656  sub     rsp, 50h
0x18002465a  lea     rbp, [rsp+30h]
0x18002465f  mov     [rbp+20h+arg_8], rbx
0x180024663  mov     [rbp+20h+arg_10], rdi
0x180024667  mov     rax, cs:__security_cookie
0x18002466e  xor     rax, rbp
0x180024671  mov     [rbp+20h+var_8], rax
0x180024675  mov     r9, rcx
0x180024678  xor     ebx, ebx
0x18002467a  test    rcx, rcx
0x18002467d  jz      loc_180024726
0x180024683  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024687  inc     rax
0x18002468a  cmp     [rcx+rax], bl
0x18002468d  jnz     short loc_180024687
0x18002468f  lea     r8d, [rax+1]
0x180024693  mov     [rbp+20h+var_1C], r8d
0x180024697  mov     dword ptr [rbp+20h+UnicodeString], r8d
0x18002469b  mov     eax, r8d
0x18002469e  add     rax, rax
0x1800246a1  lea     rcx, [rax+0Fh]
0x1800246a5  cmp     rcx, rax
0x1800246a8  ja      short loc_1800246B4
0x1800246aa  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800246b4  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800246b8  mov     rax, rcx
0x1800246bb  call    _alloca_probe
0x1800246c0  sub     rsp, rcx
0x1800246c3  lea     rdi, [rsp+50h+UnicodeString]
0x1800246c8  mov     [rbp+20h+var_10], rdi
0x1800246cc  jmp     short loc_1800246FA
0x1800246ce  call    cs:__imp__resetstkoflw
0x1800246d4  xor     edi, edi
0x1800246d6  mov     [rbp+20h+var_10], rdi
0x1800246da  mov     r8d, dword ptr [rbp+20h+UnicodeString]
0x1800246de  add     r8, r8
0x1800246e1  lea     rdx, aAllocaFailedFo; "alloca failed for %d bytes"
0x1800246e8  lea     ecx, [rdi+8]; int
0x1800246eb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800246f0  xor     ebx, ebx
0x1800246f2  mov     r9, [rbp+20h+MultiByteString]; MultiByteString
0x1800246f6  mov     r8d, [rbp+20h+var_1C]
0x1800246fa  test    rdi, rdi
0x1800246fd  jnz     short loc_18002470A
0x1800246ff  lea     ecx, [rdi+8]; dwErrCode
0x180024702  call    cs:__imp_SetLastError
0x180024708  jmp     short loc_18002472E
0x18002470a  mov     [rbp+20h+BytesInUnicodeString], ebx
0x18002470d  lea     edx, [r8+r8]; MaxBytesInUnicodeString
0x180024711  mov     [rsp+50h+BytesInMultiByteString], r8d; BytesInMultiByteString
0x180024716  lea     r8, [rbp+20h+BytesInUnicodeString]; BytesInUnicodeString
0x18002471a  mov     rcx, rdi; UnicodeString
0x18002471d  call    cs:__imp_RtlMultiByteToUnicodeN
0x180024723  mov     rcx, rdi; unsigned __int16 *
0x180024726  call    WinStationOpenServerExW
0x18002472b  mov     rbx, rax
0x18002472e  mov     rax, rbx
0x180024731  mov     rcx, [rbp+20h+var_8]
0x180024735  xor     rcx, rbp; StackCookie
0x180024738  call    __security_check_cookie
0x18002473d  mov     rbx, [rbp+20h+arg_8]
0x180024741  mov     rdi, [rbp+20h+arg_10]
0x180024745  lea     rsp, [rbp+20h]
0x180024749  pop     rbp
0x18002474a  retn
0x180030c55  push    rbp
0x180030c57  sub     rsp, 30h
0x180030c5b  lea     rbp, [rdx+30h]
0x180030c5f  mov     rax, [rcx]
0x180030c62  xor     ecx, ecx
0x180030c64  cmp     dword ptr [rax], 0C00000FDh
0x180030c6a  setz    cl
0x180030c6d  mov     eax, ecx
0x180030c6f  add     rsp, 30h
0x180030c73  pop     rbp
0x180030c74  retn
```
