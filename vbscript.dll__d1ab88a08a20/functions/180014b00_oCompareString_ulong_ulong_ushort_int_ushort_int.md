# oCompareString(ulong,ulong,ushort *,int,ushort *,int)

- ea: `0x180014b00`
- end: `0x180014c86`
- name: `?oCompareString@@YAHKKPEAGH0H@Z`
- size: `390`
- prototype: `int(unsigned int, unsigned int, unsigned __int16 *, int, unsigned __int16 *, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014e50`
- `0x180016a60`
- `0x180018b50`
- `0x18001a970`
- `0x1800245a0`

## callees

- `0x180014b00`
- `0x1800439c8`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x180014c5d`
- `KERNEL32!CompareStringA` at `0x180014c5d`
- `KERNEL32!CompareStringW` at `0x180014b42`
- `KERNEL32!CompareStringW` at `0x180014b42`
- `KERNEL32!WideCharToMultiByte` at `0x180014bf7`
- `KERNEL32!WideCharToMultiByte` at `0x180014c30`
- `KERNEL32!WideCharToMultiByte` at `0x180014bf7`
- `KERNEL32!WideCharToMultiByte` at `0x180014c30`
- `KERNEL32!SetLastError` at `0x180014c73`
- `KERNEL32!SetLastError` at `0x180014c73`

## pseudocode

```c
int __fastcall oCompareString(
        LCID a1,
        DWORD a2,
        unsigned __int16 *a3,
        int a4,
        unsigned __int16 *lpWideCharStr,
        int cchWideChar)
{
  __int64 v7; // rbx
  int v10; // edi
  __int64 v11; // rax
  CHAR *v12; // rsi
  DWORD v13; // ecx
  int v14; // eax
  CHAR *lpString2; // rbx
  int v16; // ebp
  int cchCount2; // eax

  LODWORD(v7) = a4;
  if ( !g_fAnsiOs )
    return CompareStringW(a1, a2, a3, a4, lpWideCharStr, cchWideChar);
  if ( !a4 || (v10 = cchWideChar) == 0 )
  {
    v13 = 87;
    goto LABEL_17;
  }
  v11 = -1;
  if ( a4 == -1 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
  }
  if ( cchWideChar == -1 )
  {
    do
      ++v11;
    while ( lpWideCharStr[v11] );
    v10 = v11;
  }
  v12 = (CHAR *)MemAlloc(2 * v10 + 2 * (int)v7);
  if ( !v12 )
  {
    v13 = 14;
LABEL_17:
    SetLastError(v13);
    return 0;
  }
  v14 = WideCharToMultiByte(0, 0, a3, v7, v12, 2 * v7, 0, 0);
  lpString2 = &v12[2 * (int)v7];
  v16 = v14;
  cchCount2 = WideCharToMultiByte(0, 0, lpWideCharStr, v10, lpString2, 2 * v10, 0, 0);
  if ( v16 && cchCount2 )
    return CompareStringA(a1, a2, v12, v16, lpString2, cchCount2);
  return 0;
}

```

## disassembly

```asm
0x180014b00  mov     [rsp+Locale], ecx
0x180014b04  push    rbx
0x180014b05  push    rbp
0x180014b06  push    rsi
0x180014b07  push    rdi
0x180014b08  push    r12
0x180014b0a  push    r13
0x180014b0c  push    r14
0x180014b0e  push    r15
0x180014b10  sub     rsp, 58h
0x180014b14  mov     r13d, edx
0x180014b17  mov     ebx, r9d
0x180014b1a  xor     edx, edx
0x180014b1c  mov     rbp, r8
0x180014b1f  cmp     cs:?g_fAnsiOs@@3HA, edx; int g_fAnsiOs
0x180014b25  jnz     short loc_180014B60
0x180014b27  mov     eax, [rsp+98h+cchWideChar]
0x180014b2e  mov     edx, r13d; dwCmpFlags
0x180014b31  mov     [rsp+98h+cchCount2], eax; cchCount2
0x180014b35  mov     rax, [rsp+98h+lpWideCharStr]
0x180014b3d  mov     [rsp+98h+lpString2], rax; lpString2
0x180014b42  call    cs:__imp_CompareStringW
0x180014b49  nop     dword ptr [rax+rax+00h]
0x180014b4e  add     rsp, 58h
0x180014b52  pop     r15
0x180014b54  pop     r14
0x180014b56  pop     r13
0x180014b58  pop     r12
0x180014b5a  pop     rdi
0x180014b5b  pop     rsi
0x180014b5c  pop     rbp
0x180014b5d  pop     rbx
0x180014b5e  retn
0x180014b60  test    ebx, ebx
0x180014b62  jz      loc_180014C6E
0x180014b68  mov     edi, [rsp+98h+cchWideChar]
0x180014b6f  test    edi, edi
0x180014b71  jz      loc_180014C6E
0x180014b77  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014b7b  cmp     ebx, eax
0x180014b7d  jnz     short loc_180014B8C
0x180014b7f  mov     rbx, rax
0x180014b82  inc     rbx
0x180014b85  cmp     [r8+rbx*2], dx
0x180014b8a  jnz     short loc_180014B82
0x180014b8c  mov     r15, [rsp+98h+lpWideCharStr]
0x180014b94  cmp     edi, eax
0x180014b96  jnz     short loc_180014BA5
0x180014b98  inc     rax
0x180014b9b  cmp     [r15+rax*2], dx
0x180014ba0  jnz     short loc_180014B98
0x180014ba2  mov     rdi, rax
0x180014ba5  lea     r14d, [rbx+rbx]
0x180014ba9  lea     r12d, [rdi+rdi]
0x180014bad  lea     ecx, [r12+r14]; unsigned int
0x180014bb1  call    ?MemAlloc@@YAPEAXI@Z; MemAlloc(uint)
0x180014bb6  mov     rsi, rax
0x180014bb9  test    rax, rax
0x180014bbc  jnz     short loc_180014BC6
0x180014bbe  lea     ecx, [rax+0Eh]
0x180014bc1  jmp     loc_180014C73
0x180014bc6  mov     [rsp+98h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180014bcf  mov     r9d, ebx; cchWideChar
0x180014bd2  mov     [rsp+98h+lpDefaultChar], 0; lpDefaultChar
0x180014bdb  mov     r8, rbp; lpWideCharStr
0x180014bde  movsxd  rax, r14d
0x180014be1  xor     edx, edx; dwFlags
0x180014be3  add     rax, rsi
0x180014be6  mov     [rsp+98h+cchCount2], r14d; cbMultiByte
0x180014beb  xor     ecx, ecx; CodePage
0x180014bed  mov     [rsp+98h+lpMultiByteStr], rax
0x180014bf2  mov     [rsp+98h+lpString2], rsi; lpMultiByteStr
0x180014bf7  call    cs:__imp_WideCharToMultiByte
0x180014bfe  nop     dword ptr [rax+rax+00h]
0x180014c03  mov     rbx, [rsp+98h+lpMultiByteStr]
0x180014c08  mov     r9d, edi; cchWideChar
0x180014c0b  mov     [rsp+98h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180014c14  mov     r8, r15; lpWideCharStr
0x180014c17  mov     [rsp+98h+lpDefaultChar], 0; lpDefaultChar
0x180014c20  xor     edx, edx; dwFlags
0x180014c22  mov     [rsp+98h+cchCount2], r12d; cbMultiByte
0x180014c27  xor     ecx, ecx; CodePage
0x180014c29  mov     [rsp+98h+lpString2], rbx; lpMultiByteStr
0x180014c2e  mov     ebp, eax
0x180014c30  call    cs:__imp_WideCharToMultiByte
0x180014c37  nop     dword ptr [rax+rax+00h]
0x180014c3c  test    ebp, ebp
0x180014c3e  jz      short loc_180014C7F
0x180014c40  test    eax, eax
0x180014c42  jz      short loc_180014C7F
0x180014c44  mov     ecx, [rsp+98h+Locale]; Locale
0x180014c4b  mov     r9d, ebp; cchCount1
0x180014c4e  mov     [rsp+98h+cchCount2], eax; cchCount2
0x180014c52  mov     r8, rsi; lpString1
0x180014c55  mov     edx, r13d; dwCmpFlags
0x180014c58  mov     [rsp+98h+lpString2], rbx; lpString2
0x180014c5d  call    cs:__imp_CompareStringA
0x180014c64  nop     dword ptr [rax+rax+00h]
0x180014c69  jmp     loc_180014B4E
0x180014c6e  mov     ecx, 57h ; 'W'; dwErrCode
0x180014c73  call    cs:__imp_SetLastError
0x180014c7a  nop     dword ptr [rax+rax+00h]
0x180014c7f  xor     eax, eax
0x180014c81  jmp     loc_180014B4E
```
