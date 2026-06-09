# WinStationOpenServerExA

- ea: `0x180025fb0`
- end: `0x1800260be`
- name: `WinStationOpenServerExA`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180005b40`
- `0x180014880`
- `0x180025fb0`
- `0x180032c20`
- `0x180032ce0`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18002602e`
- `msvcrt!_resetstkoflw` at `0x18002602e`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180026089`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180026089`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026068`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026068`

## pseudocode

```c
__int64 __fastcall WinStationOpenServerExA(unsigned __int16 *a1)
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
  return v2;
}

```

## disassembly

```asm
0x180025fb0  mov     [rsp-8+MultiByteString], rcx
0x180025fb5  push    rbp
0x180025fb6  sub     rsp, 50h
0x180025fba  lea     rbp, [rsp+30h]
0x180025fbf  mov     [rbp+20h+arg_8], rbx
0x180025fc3  mov     [rbp+20h+arg_10], rdi
0x180025fc7  mov     rax, cs:__security_cookie
0x180025fce  xor     rax, rbp
0x180025fd1  mov     [rbp+20h+var_8], rax
0x180025fd5  mov     r9, rcx
0x180025fd8  xor     ebx, ebx
0x180025fda  test    rcx, rcx
0x180025fdd  jz      loc_180026098
0x180025fe3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025fe7  inc     rax
0x180025fea  cmp     [rcx+rax], bl
0x180025fed  jnz     short loc_180025FE7
0x180025fef  lea     r8d, [rax+1]
0x180025ff3  mov     [rbp+20h+var_1C], r8d
0x180025ff7  mov     dword ptr [rbp+20h+UnicodeString], r8d
0x180025ffb  mov     eax, r8d
0x180025ffe  add     rax, rax
0x180026001  lea     rcx, [rax+0Fh]
0x180026005  cmp     rcx, rax
0x180026008  ja      short loc_180026014
0x18002600a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180026014  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180026018  mov     rax, rcx
0x18002601b  call    _alloca_probe
0x180026020  sub     rsp, rcx
0x180026023  lea     rdi, [rsp+50h+UnicodeString]
0x180026028  mov     [rbp+20h+var_10], rdi
0x18002602c  jmp     short loc_180026060
0x18002602e  call    cs:__imp__resetstkoflw
0x180026035  nop     dword ptr [rax+rax+00h]
0x18002603a  xor     edi, edi
0x18002603c  mov     [rbp+20h+var_10], rdi
0x180026040  mov     r8d, dword ptr [rbp+20h+UnicodeString]
0x180026044  add     r8, r8
0x180026047  lea     rdx, aAllocaFailedFo; "alloca failed for %d bytes"
0x18002604e  lea     ecx, [rdi+8]; int
0x180026051  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180026056  xor     ebx, ebx
0x180026058  mov     r9, [rbp+20h+MultiByteString]; MultiByteString
0x18002605c  mov     r8d, [rbp+20h+var_1C]
0x180026060  test    rdi, rdi
0x180026063  jnz     short loc_180026076
0x180026065  lea     ecx, [rdi+8]; dwErrCode
0x180026068  call    cs:__imp_SetLastError
0x18002606f  nop     dword ptr [rax+rax+00h]
0x180026074  jmp     short loc_1800260A0
0x180026076  mov     [rbp+20h+BytesInUnicodeString], ebx
0x180026079  lea     edx, [r8+r8]; MaxBytesInUnicodeString
0x18002607d  mov     [rsp+50h+BytesInMultiByteString], r8d; BytesInMultiByteString
0x180026082  lea     r8, [rbp+20h+BytesInUnicodeString]; BytesInUnicodeString
0x180026086  mov     rcx, rdi; UnicodeString
0x180026089  call    cs:__imp_RtlMultiByteToUnicodeN
0x180026090  nop     dword ptr [rax+rax+00h]
0x180026095  mov     rcx, rdi; unsigned __int16 *
0x180026098  call    WinStationOpenServerExW
0x18002609d  mov     rbx, rax
0x1800260a0  mov     rax, rbx
0x1800260a3  mov     rcx, [rbp+20h+var_8]
0x1800260a7  xor     rcx, rbp; StackCookie
0x1800260aa  call    __security_check_cookie
0x1800260af  mov     rbx, [rbp+20h+arg_8]
0x1800260b3  mov     rdi, [rbp+20h+arg_10]
0x1800260b7  lea     rsp, [rbp+20h]
0x1800260bb  pop     rbp
0x1800260bc  retn
0x180033b65  push    rbp
0x180033b67  sub     rsp, 30h
0x180033b6b  lea     rbp, [rdx+30h]
0x180033b6f  mov     rax, [rcx]
0x180033b72  xor     ecx, ecx
0x180033b74  cmp     dword ptr [rax], 0C00000FDh
0x180033b7a  setz    cl
0x180033b7d  mov     eax, ecx
0x180033b7f  add     rsp, 30h
0x180033b83  pop     rbp
0x180033b84  retn
```
