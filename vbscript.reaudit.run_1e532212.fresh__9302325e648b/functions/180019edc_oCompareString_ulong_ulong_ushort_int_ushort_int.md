# oCompareString(ulong,ulong,ushort *,int,ushort *,int)

- ea: `0x180019edc`
- end: `0x18001a043`
- name: `?oCompareString@@YAHKKPEAGH0H@Z`
- size: `359`
- prototype: `int(unsigned int, unsigned int, unsigned __int16 *, int, unsigned __int16 *, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002b70`
- `0x18001a050`
- `0x18001b960`
- `0x18001c950`
- `0x18001e850`

## callees

- `0x180019edc`
- `0x180042360`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x18001a026`
- `KERNEL32!CompareStringA` at `0x18001a026`
- `KERNEL32!CompareStringW` at `0x180019f1e`
- `KERNEL32!CompareStringW` at `0x180019f1e`
- `KERNEL32!WideCharToMultiByte` at `0x180019fcc`
- `KERNEL32!WideCharToMultiByte` at `0x180019fff`
- `KERNEL32!WideCharToMultiByte` at `0x180019fcc`
- `KERNEL32!WideCharToMultiByte` at `0x180019fff`
- `KERNEL32!SetLastError` at `0x18001a036`
- `KERNEL32!SetLastError` at `0x18001a036`

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
0x180019edc  mov     [rsp+Locale], ecx
0x180019ee0  push    rbx
0x180019ee1  push    rbp
0x180019ee2  push    rsi
0x180019ee3  push    rdi
0x180019ee4  push    r12
0x180019ee6  push    r13
0x180019ee8  push    r14
0x180019eea  push    r15
0x180019eec  sub     rsp, 58h
0x180019ef0  mov     r13d, edx
0x180019ef3  mov     ebx, r9d
0x180019ef6  xor     edx, edx
0x180019ef8  mov     rbp, r8
0x180019efb  cmp     cs:?g_fAnsiOs@@3HA, edx; int g_fAnsiOs
0x180019f01  jnz     short loc_180019F35
0x180019f03  mov     eax, [rsp+98h+cchWideChar]
0x180019f0a  mov     edx, r13d; dwCmpFlags
0x180019f0d  mov     [rsp+98h+cchCount2], eax; cchCount2
0x180019f11  mov     rax, [rsp+98h+lpWideCharStr]
0x180019f19  mov     [rsp+98h+lpString2], rax; lpString2
0x180019f1e  call    cs:__imp_CompareStringW
0x180019f24  add     rsp, 58h
0x180019f28  pop     r15
0x180019f2a  pop     r14
0x180019f2c  pop     r13
0x180019f2e  pop     r12
0x180019f30  pop     rdi
0x180019f31  pop     rsi
0x180019f32  pop     rbp
0x180019f33  pop     rbx
0x180019f34  retn
0x180019f35  test    ebx, ebx
0x180019f37  jz      loc_18001A031
0x180019f3d  mov     edi, [rsp+98h+cchWideChar]
0x180019f44  test    edi, edi
0x180019f46  jz      loc_18001A031
0x180019f4c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019f50  cmp     ebx, eax
0x180019f52  jnz     short loc_180019F61
0x180019f54  mov     rbx, rax
0x180019f57  inc     rbx
0x180019f5a  cmp     [r8+rbx*2], dx
0x180019f5f  jnz     short loc_180019F57
0x180019f61  mov     r15, [rsp+98h+lpWideCharStr]
0x180019f69  cmp     edi, eax
0x180019f6b  jnz     short loc_180019F7A
0x180019f6d  inc     rax
0x180019f70  cmp     [r15+rax*2], dx
0x180019f75  jnz     short loc_180019F6D
0x180019f77  mov     rdi, rax
0x180019f7a  lea     r14d, [rbx+rbx]
0x180019f7e  lea     r12d, [rdi+rdi]
0x180019f82  lea     ecx, [r12+r14]; unsigned int
0x180019f86  call    ?MemAlloc@@YAPEAXI@Z; MemAlloc(uint)
0x180019f8b  mov     rsi, rax
0x180019f8e  test    rax, rax
0x180019f91  jnz     short loc_180019F9B
0x180019f93  lea     ecx, [rax+0Eh]
0x180019f96  jmp     loc_18001A036
0x180019f9b  mov     [rsp+98h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180019fa4  mov     r9d, ebx; cchWideChar
0x180019fa7  mov     [rsp+98h+lpDefaultChar], 0; lpDefaultChar
0x180019fb0  mov     r8, rbp; lpWideCharStr
0x180019fb3  movsxd  rax, r14d
0x180019fb6  xor     edx, edx; dwFlags
0x180019fb8  add     rax, rsi
0x180019fbb  mov     [rsp+98h+cchCount2], r14d; cbMultiByte
0x180019fc0  xor     ecx, ecx; CodePage
0x180019fc2  mov     [rsp+98h+lpMultiByteStr], rax
0x180019fc7  mov     [rsp+98h+lpString2], rsi; lpMultiByteStr
0x180019fcc  call    cs:__imp_WideCharToMultiByte
0x180019fd2  mov     rbx, [rsp+98h+lpMultiByteStr]
0x180019fd7  mov     r9d, edi; cchWideChar
0x180019fda  mov     [rsp+98h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180019fe3  mov     r8, r15; lpWideCharStr
0x180019fe6  mov     [rsp+98h+lpDefaultChar], 0; lpDefaultChar
0x180019fef  xor     edx, edx; dwFlags
0x180019ff1  mov     [rsp+98h+cchCount2], r12d; cbMultiByte
0x180019ff6  xor     ecx, ecx; CodePage
0x180019ff8  mov     [rsp+98h+lpString2], rbx; lpMultiByteStr
0x180019ffd  mov     ebp, eax
0x180019fff  call    cs:__imp_WideCharToMultiByte
0x18001a005  test    ebp, ebp
0x18001a007  jz      short loc_18001A03C
0x18001a009  test    eax, eax
0x18001a00b  jz      short loc_18001A03C
0x18001a00d  mov     ecx, [rsp+98h+Locale]; Locale
0x18001a014  mov     r9d, ebp; cchCount1
0x18001a017  mov     [rsp+98h+cchCount2], eax; cchCount2
0x18001a01b  mov     r8, rsi; lpString1
0x18001a01e  mov     edx, r13d; dwCmpFlags
0x18001a021  mov     [rsp+98h+lpString2], rbx; lpString2
0x18001a026  call    cs:__imp_CompareStringA
0x18001a02c  jmp     loc_180019F24
0x18001a031  mov     ecx, 57h ; 'W'; dwErrCode
0x18001a036  call    cs:__imp_SetLastError
0x18001a03c  xor     eax, eax
0x18001a03e  jmp     loc_180019F24
```
