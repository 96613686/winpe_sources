# FormatHResult(long,ushort * *)

- ea: `0x140009b54`
- end: `0x140009ce7`
- name: `?FormatHResult@@YAJJPEAPEAG@Z`
- size: `403`
- prototype: `__int64 __fastcall(DWORD dwMessageId, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140005990`
- `0x14000c130`
- `0x14000cf0c`
- `0x14000da90`
- `0x14000f2f0`
- `0x1400111d0`

## callees

- `0x140009b54`

## import_xrefs

- `msvcrt!swprintf_s` at `0x140009bf5`
- `msvcrt!swprintf_s` at `0x140009bf5`
- `msvcrt!sprintf_s` at `0x140009c38`
- `msvcrt!sprintf_s` at `0x140009c38`
- `OLEAUT32!__imp_SysAllocString` at `0x140009cb1`
- `OLEAUT32!__imp_SysAllocString` at `0x140009cb1`
- `KERNEL32!FormatMessageW` at `0x140009ba3`
- `KERNEL32!FormatMessageW` at `0x140009ba3`
- `KERNEL32!GetLastError` at `0x140009bc5`
- `KERNEL32!GetLastError` at `0x140009bc5`
- `KERNEL32!MultiByteToWideChar` at `0x140009c5d`
- `KERNEL32!MultiByteToWideChar` at `0x140009c9d`
- `KERNEL32!MultiByteToWideChar` at `0x140009c5d`
- `KERNEL32!MultiByteToWideChar` at `0x140009c9d`
- `KERNEL32!LocalAlloc` at `0x140009bb6`
- `KERNEL32!LocalAlloc` at `0x140009c1a`
- `KERNEL32!LocalAlloc` at `0x140009c76`
- `KERNEL32!LocalAlloc` at `0x140009bb6`
- `KERNEL32!LocalAlloc` at `0x140009c1a`
- `KERNEL32!LocalAlloc` at `0x140009c76`
- `KERNEL32!LocalFree` at `0x140009cc3`
- `KERNEL32!LocalFree` at `0x140009cd2`
- `KERNEL32!LocalFree` at `0x140009cc3`
- `KERNEL32!LocalFree` at `0x140009cd2`
- `KERNEL32!FormatMessageA` at `0x140009c09`
- `KERNEL32!FormatMessageA` at `0x140009c09`

## pseudocode

```c
__int64 __fastcall FormatHResult(DWORD dwMessageId, unsigned __int16 **a2)
{
  OLECHAR *v4; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  CHAR *v7; // rax
  int v8; // eax
  int v9; // ebx
  OLECHAR *v10; // rax
  CHAR *lpBuffer; // [rsp+70h] [rbp+30h] BYREF
  OLECHAR *Buffer; // [rsp+78h] [rbp+38h] BYREF

  Buffer = 0;
  lpBuffer = 0;
  if ( Global::g_fWindowsNT )
  {
    if ( !FormatMessageW(0x11FFu, 0, dwMessageId, 0, (LPWSTR)&Buffer, 0, 0) )
    {
      v4 = (OLECHAR *)LocalAlloc(0, 0x16u);
      Buffer = v4;
      if ( !v4 )
        goto LABEL_4;
      swprintf_s(v4, 0xBu, L"0x%8X", dwMessageId);
    }
LABEL_13:
    v6 = 0;
    *a2 = SysAllocString(Buffer);
    goto LABEL_14;
  }
  if ( !FormatMessageA(0x11FFu, 0, dwMessageId, 0, (LPSTR)&lpBuffer, 0, 0) )
  {
    v7 = (CHAR *)LocalAlloc(0, 0xBu);
    lpBuffer = v7;
    if ( !v7 )
      goto LABEL_4;
    sprintf_s(v7, 0xBu, "0x%8X", dwMessageId);
  }
  v8 = MultiByteToWideChar(0, 0, lpBuffer, -1, 0, 0);
  v9 = v8;
  if ( v8 )
  {
    v10 = (OLECHAR *)LocalAlloc(0, 2LL * v8);
    Buffer = v10;
    if ( v10 )
    {
      if ( MultiByteToWideChar(0, 0, lpBuffer, -1, v10, v9) )
        goto LABEL_13;
    }
  }
LABEL_4:
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
LABEL_14:
  if ( lpBuffer )
    LocalFree(lpBuffer);
  if ( Buffer )
    LocalFree(Buffer);
  return v6;
}

```

## disassembly

```asm
0x140009b54  mov     [rsp-18h+arg_0], rbx
0x140009b59  push    rbp
0x140009b5a  push    rsi
0x140009b5b  push    rdi
0x140009b5c  mov     rbp, rsp
0x140009b5f  sub     rsp, 40h
0x140009b63  mov     rsi, rdx
0x140009b66  mov     [rsp+40h+Arguments], 0; Arguments
0x140009b6f  xor     edx, edx; lpSource
0x140009b71  mov     [rbp+Buffer], 0
0x140009b79  xor     r9d, r9d; dwLanguageId
0x140009b7c  mov     [rbp+arg_10], 0
0x140009b84  cmp     cs:?g_fWindowsNT@Global@@2_NA, dl; bool Global::g_fWindowsNT
0x140009b8a  mov     edi, ecx
0x140009b8c  mov     r8d, ecx; dwMessageId
0x140009b8f  mov     [rsp+40h+nSize], edx; nSize
0x140009b93  mov     ecx, 11FFh; dwFlags
0x140009b98  jz      short loc_140009C00
0x140009b9a  lea     rax, [rbp+Buffer]
0x140009b9e  mov     [rsp+40h+lpBuffer], rax; lpBuffer
0x140009ba3  call    cs:__imp_FormatMessageW
0x140009ba9  test    eax, eax
0x140009bab  jnz     loc_140009CAB
0x140009bb1  lea     edx, [rax+16h]; uBytes
0x140009bb4  xor     ecx, ecx; uFlags
0x140009bb6  call    cs:__imp_LocalAlloc
0x140009bbc  mov     [rbp+Buffer], rax
0x140009bc0  test    rax, rax
0x140009bc3  jnz     short loc_140009BE3
0x140009bc5  call    cs:__imp_GetLastError
0x140009bcb  mov     ebx, eax
0x140009bcd  test    eax, eax
0x140009bcf  jle     loc_140009CBA
0x140009bd5  movzx   ebx, ax
0x140009bd8  or      ebx, 80070000h
0x140009bde  jmp     loc_140009CBA
0x140009be3  mov     r9d, edi
0x140009be6  lea     r8, a0x8x_0; "0x%8X"
0x140009bed  mov     edx, 0Bh; BufferCount
0x140009bf2  mov     rcx, rax; Buffer
0x140009bf5  call    cs:__imp_swprintf_s
0x140009bfb  jmp     loc_140009CAB
0x140009c00  lea     rax, [rbp+arg_10]
0x140009c04  mov     [rsp+40h+lpBuffer], rax; lpBuffer
0x140009c09  call    cs:__imp_FormatMessageA
0x140009c0f  test    eax, eax
0x140009c11  jnz     short loc_140009C3E
0x140009c13  lea     ebx, [rax+0Bh]
0x140009c16  xor     ecx, ecx; uFlags
0x140009c18  mov     edx, ebx; uBytes
0x140009c1a  call    cs:__imp_LocalAlloc
0x140009c20  mov     [rbp+arg_10], rax
0x140009c24  test    rax, rax
0x140009c27  jz      short loc_140009BC5
0x140009c29  mov     r9d, edi
0x140009c2c  lea     r8, a0x8x; "0x%8X"
0x140009c33  mov     edx, ebx; BufferCount
0x140009c35  mov     rcx, rax; Buffer
0x140009c38  call    cs:__imp_sprintf_s
0x140009c3e  mov     r8, [rbp+arg_10]; lpMultiByteStr
0x140009c42  or      edi, 0FFFFFFFFh
0x140009c45  mov     r9d, edi; cbMultiByte
0x140009c48  mov     [rsp+40h+nSize], 0; cchWideChar
0x140009c50  xor     edx, edx; dwFlags
0x140009c52  mov     [rsp+40h+lpBuffer], 0; lpWideCharStr
0x140009c5b  xor     ecx, ecx; CodePage
0x140009c5d  call    cs:__imp_MultiByteToWideChar
0x140009c63  movsxd  rbx, eax
0x140009c66  test    eax, eax
0x140009c68  jz      loc_140009BC5
0x140009c6e  mov     rdx, rbx
0x140009c71  xor     ecx, ecx; uFlags
0x140009c73  add     rdx, rdx; uBytes
0x140009c76  call    cs:__imp_LocalAlloc
0x140009c7c  mov     [rbp+Buffer], rax
0x140009c80  test    rax, rax
0x140009c83  jz      loc_140009BC5
0x140009c89  mov     r8, [rbp+arg_10]; lpMultiByteStr
0x140009c8d  mov     r9d, edi; cbMultiByte
0x140009c90  mov     [rsp+40h+nSize], ebx; cchWideChar
0x140009c94  xor     edx, edx; dwFlags
0x140009c96  xor     ecx, ecx; CodePage
0x140009c98  mov     [rsp+40h+lpBuffer], rax; lpWideCharStr
0x140009c9d  call    cs:__imp_MultiByteToWideChar
0x140009ca3  test    eax, eax
0x140009ca5  jz      loc_140009BC5
0x140009cab  mov     rcx, [rbp+Buffer]; psz
0x140009caf  xor     ebx, ebx
0x140009cb1  call    cs:__imp_SysAllocString
0x140009cb7  mov     [rsi], rax
0x140009cba  mov     rcx, [rbp+arg_10]; hMem
0x140009cbe  test    rcx, rcx
0x140009cc1  jz      short loc_140009CC9
0x140009cc3  call    cs:__imp_LocalFree
0x140009cc9  mov     rcx, [rbp+Buffer]; hMem
0x140009ccd  test    rcx, rcx
0x140009cd0  jz      short loc_140009CD8
0x140009cd2  call    cs:__imp_LocalFree
0x140009cd8  mov     eax, ebx
0x140009cda  mov     rbx, [rsp+40h+arg_0]
0x140009cdf  add     rsp, 40h
0x140009ce3  pop     rdi
0x140009ce4  pop     rsi
0x140009ce5  pop     rbp
0x140009ce6  retn
```
