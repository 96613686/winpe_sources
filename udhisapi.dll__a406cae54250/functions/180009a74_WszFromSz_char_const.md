# WszFromSz(char const *)

- ea: `0x180009a74`
- end: `0x180009bc4`
- name: `?WszFromSz@@YAPEAGPEBD@Z`
- size: `336`
- prototype: `unsigned __int16 *__fastcall(LPCCH lpMultiByteStr)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180002dec`
- `0x180005674`
- `0x180006f64`
- `0x180007310`
- `0x180007734`
- `0x180007d5c`
- `0x1800080bc`
- `0x1800083f0`

## callees

- `0x1800024c4`
- `0x1800038ec`
- `0x180009a74`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009bad`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009bad`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180009afb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180009afb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b85`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180009a9f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180009b62`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180009a9f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180009b62`

## pseudocode

```c
unsigned __int16 *__fastcall WszFromSz(LPCCH lpMultiByteStr)
{
  __int64 v1; // rsi
  int v3; // eax
  int cchWideChar; // ebp
  DWORD v5; // eax
  WCHAR *lpWideCharStr; // rax
  WCHAR *v7; // rbx
  DWORD LastError; // eax

  v1 = 0;
  if ( lpMultiByteStr )
  {
    v3 = MultiByteToWideChar(0, 0, lpMultiByteStr, -1, 0, 0);
    cchWideChar = v3;
    if ( v3 )
    {
      lpWideCharStr = (WCHAR *)malloc(2LL * v3);
      v7 = lpWideCharStr;
      if ( lpWideCharStr )
      {
        if ( MultiByteToWideChar(0, 0, lpMultiByteStr, -1, lpWideCharStr, cchWideChar) )
        {
          return v7;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            LastError = GetLastError();
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              15,
              WPP_2a93b8cd1ba13cd6c891d054980ab5f0_Traceguids,
              LastError);
          }
          free(v7);
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_2a93b8cd1ba13cd6c891d054980ab5f0_Traceguids,
          (unsigned int)"WszFromSz: new",
          14);
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_2a93b8cd1ba13cd6c891d054980ab5f0_Traceguids, v5);
    }
  }
  return (unsigned __int16 *)v1;
}

```

## disassembly

```asm
0x180009a74  push    rbx
0x180009a76  push    rbp
0x180009a77  push    rsi
0x180009a78  push    rdi
0x180009a79  sub     rsp, 38h
0x180009a7d  xor     esi, esi
0x180009a7f  mov     rdi, rcx
0x180009a82  test    rcx, rcx
0x180009a85  jz      loc_180009BB8
0x180009a8b  mov     r8, rcx; lpMultiByteStr
0x180009a8e  mov     [rsp+58h+cchWideChar], esi; cchWideChar
0x180009a92  xor     ecx, ecx; CodePage
0x180009a94  mov     [rsp+58h+lpWideCharStr], rsi; lpWideCharStr
0x180009a99  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180009a9d  xor     edx, edx; dwFlags
0x180009a9f  call    cs:__imp_MultiByteToWideChar
0x180009aa5  movsxd  rbp, eax
0x180009aa8  test    eax, eax
0x180009aaa  jnz     short loc_180009AF5
0x180009aac  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ab3  lea     rax, WPP_GLOBAL_Control
0x180009aba  cmp     rcx, rax
0x180009abd  jz      loc_180009BB8
0x180009ac3  test    byte ptr [rcx+1Ch], 1
0x180009ac7  jz      loc_180009BB8
0x180009acd  call    cs:__imp_GetLastError
0x180009ad3  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ada  lea     edx, [rsi+0Dh]
0x180009add  mov     r9d, eax
0x180009ae0  lea     r8, WPP_2a93b8cd1ba13cd6c891d054980ab5f0_Traceguids
0x180009ae7  mov     rcx, [rcx+10h]
0x180009aeb  call    WPP_SF_d
0x180009af0  jmp     loc_180009BB8
0x180009af5  mov     rcx, rbp
0x180009af8  add     rcx, rcx; Size
0x180009afb  call    cs:__imp_malloc
0x180009b01  mov     rbx, rax
0x180009b04  test    rax, rax
0x180009b07  jnz     short loc_180009B4E
0x180009b09  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b10  lea     rax, WPP_GLOBAL_Control
0x180009b17  cmp     rcx, rax
0x180009b1a  jz      loc_180009BB8
0x180009b20  test    byte ptr [rcx+1Ch], 1
0x180009b24  jz      loc_180009BB8
0x180009b2a  mov     rcx, [rcx+10h]
0x180009b2e  lea     edx, [rbx+0Eh]
0x180009b31  lea     r9, aWszfromszNew; "WszFromSz: new"
0x180009b38  mov     dword ptr [rsp+58h+lpWideCharStr], 8007000Eh
0x180009b40  lea     r8, WPP_2a93b8cd1ba13cd6c891d054980ab5f0_Traceguids
0x180009b47  call    WPP_SF_sd
0x180009b4c  jmp     short loc_180009BB8
0x180009b4e  mov     [rsp+58h+cchWideChar], ebp; cchWideChar
0x180009b52  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180009b56  mov     r8, rdi; lpMultiByteStr
0x180009b59  mov     [rsp+58h+lpWideCharStr], rbx; lpWideCharStr
0x180009b5e  xor     edx, edx; dwFlags
0x180009b60  xor     ecx, ecx; CodePage
0x180009b62  call    cs:__imp_MultiByteToWideChar
0x180009b68  test    eax, eax
0x180009b6a  jnz     short loc_180009BB5
0x180009b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b73  lea     rax, WPP_GLOBAL_Control
0x180009b7a  cmp     rcx, rax
0x180009b7d  jz      short loc_180009BAA
0x180009b7f  test    byte ptr [rcx+1Ch], 1
0x180009b83  jz      short loc_180009BAA
0x180009b85  call    cs:__imp_GetLastError
0x180009b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b92  lea     r8, WPP_2a93b8cd1ba13cd6c891d054980ab5f0_Traceguids
0x180009b99  mov     edx, 0Fh
0x180009b9e  mov     r9d, eax
0x180009ba1  mov     rcx, [rcx+10h]
0x180009ba5  call    WPP_SF_d
0x180009baa  mov     rcx, rbx; Block
0x180009bad  call    cs:__imp_free
0x180009bb3  jmp     short loc_180009BB8
0x180009bb5  mov     rsi, rbx
0x180009bb8  mov     rax, rsi
0x180009bbb  add     rsp, 38h
0x180009bbf  pop     rdi
0x180009bc0  pop     rsi
0x180009bc1  pop     rbp
0x180009bc2  pop     rbx
0x180009bc3  retn
```
