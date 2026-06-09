# EncodeUnicodeString

- ea: `0x180007aa0`
- end: `0x180007c8f`
- name: `EncodeUnicodeString`
- size: `495`
- prototype: `__int64 __fastcall(unsigned __int16 *, UINT, __int64, WINBOOL *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180003a50`
- `0x180004cb0`
- `0x18001e4b0`
- `0x1800206d0`
- `0x18002552c`
- `0x180026020`
- `0x180026ad0`
- `0x180029c98`
- `0x18002b934`

## callees

- `0x1800061a0`
- `0x180006de0`
- `0x180007aa0`
- `0x180011fec`
- `0x1800185b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c4b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180007b01`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180007b79`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180007b01`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180007b79`

## pseudocode

```c
__int64 __fastcall EncodeUnicodeString(unsigned __int16 *a1, UINT a2, __int64 a3, WINBOOL *a4)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  DWORD v10; // r15d
  int cbMultiByte; // r12d
  CHAR *lpMultiByteStr; // rax
  int v13; // eax
  __int64 result; // rax
  DWORD LastError; // eax
  DWORD v16; // eax

  v4 = *a1;
  v5 = 0;
  if ( (_WORD)v4 )
  {
    if ( a2 == 65001 )
      a4 = 0;
    v10 = 1024;
    if ( a2 == 65001 )
      v10 = 0;
    cbMultiByte = WideCharToMultiByte(a2, v10, *((LPCWCH *)a1 + 1), v4 >> 1, 0, 0, 0, 0);
    if ( cbMultiByte <= 0 )
    {
      v5 = -1073741470;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, LastError);
      return v5;
    }
    if ( (_WORD)cbMultiByte == 0xFFFF || !a3 )
    {
      v5 = -1073741811;
    }
    else
    {
      *(_WORD *)a3 = 0;
      lpMultiByteStr = (CHAR *)DigestAllocateMemory((unsigned __int16)(cbMultiByte + 1));
      *(_QWORD *)(a3 + 8) = lpMultiByteStr;
      if ( lpMultiByteStr )
      {
        *(_WORD *)(a3 + 2) = cbMultiByte + 1;
        v13 = WideCharToMultiByte(a2, v10, *((LPCWCH *)a1 + 1), *a1 >> 1, lpMultiByteStr, cbMultiByte, 0, a4);
        if ( v13 )
        {
          *(_WORD *)a3 = v13;
        }
        else
        {
          v5 = -1073741470;
          v16 = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v16);
          StringFree(a3);
        }
        return v5;
      }
      *(_WORD *)(a3 + 2) = 0;
      v5 = -2146893056;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_5a1eec0057703498b5d13460810c8614_Traceguids);
    return v5;
  }
  *(_DWORD *)a3 = 0;
  result = 0;
  *(_QWORD *)(a3 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x180007aa0  mov     r11, rsp
0x180007aa3  push    rbx
0x180007aa4  push    rbp
0x180007aa5  push    rsi
0x180007aa6  push    rdi
0x180007aa7  push    r14
0x180007aa9  sub     rsp, 40h
0x180007aad  movzx   eax, word ptr [rcx]
0x180007ab0  xor     ebx, ebx
0x180007ab2  mov     r14, r9
0x180007ab5  mov     rsi, r8
0x180007ab8  mov     ebp, edx
0x180007aba  mov     rdi, rcx
0x180007abd  test    ax, ax
0x180007ac0  jz      loc_180007BE7
0x180007ac6  mov     r8, [rcx+8]; lpWideCharStr
0x180007aca  cmp     edx, 0FDE9h
0x180007ad0  mov     [r11-30h], rbx
0x180007ad4  mov     r9d, eax
0x180007ad7  mov     [r11-38h], rbx
0x180007adb  cmovz   r14, rbx
0x180007adf  mov     [r11+8], r12
0x180007ae3  mov     ecx, ebp; CodePage
0x180007ae5  mov     [r11+18h], r15
0x180007ae9  mov     r15d, 400h
0x180007aef  cmovz   r15d, ebx
0x180007af3  mov     [rsp+68h+cbMultiByte], ebx; cbMultiByte
0x180007af7  mov     edx, r15d; dwFlags
0x180007afa  shr     r9d, 1; cchWideChar
0x180007afd  mov     [r11-48h], rbx
0x180007b01  call    cs:__imp_WideCharToMultiByte
0x180007b07  mov     r12d, eax
0x180007b0a  test    eax, eax
0x180007b0c  jle     loc_180007BA9
0x180007b12  mov     eax, 0FFFEh
0x180007b17  mov     [rsp+68h+arg_8], r13
0x180007b1c  cmp     r12w, ax
0x180007b20  ja      loc_180007BFB
0x180007b26  test    rsi, rsi
0x180007b29  jz      loc_180007BFB
0x180007b2f  lea     eax, [r12+1]
0x180007b34  mov     [rsi], bx
0x180007b37  movzx   r13d, ax
0x180007b3b  mov     ecx, r13d; Size
0x180007b3e  call    DigestAllocateMemory
0x180007b43  mov     [rsi+8], rax
0x180007b47  test    rax, rax
0x180007b4a  jz      loc_180007C3B
0x180007b50  mov     [rsi+2], r13w
0x180007b55  mov     edx, r15d; dwFlags
0x180007b58  movzx   r9d, word ptr [rdi]
0x180007b5c  mov     ecx, ebp; CodePage
0x180007b5e  mov     r8, [rdi+8]; lpWideCharStr
0x180007b62  mov     [rsp+68h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x180007b67  mov     [rsp+68h+lpDefaultChar], rbx; lpDefaultChar
0x180007b6c  shr     r9d, 1; cchWideChar
0x180007b6f  mov     [rsp+68h+cbMultiByte], r12d; cbMultiByte
0x180007b74  mov     [rsp+68h+lpMultiByteStr], rax; lpMultiByteStr
0x180007b79  call    cs:__imp_WideCharToMultiByte
0x180007b7f  test    eax, eax
0x180007b81  jz      loc_180007C46
0x180007b87  mov     [rsi], ax
0x180007b8a  mov     r13, [rsp+68h+arg_8]
0x180007b8f  mov     r12, [rsp+68h+arg_0]
0x180007b94  mov     r15, [rsp+68h+arg_10]
0x180007b9c  mov     eax, ebx
0x180007b9e  add     rsp, 40h
0x180007ba2  pop     r14
0x180007ba4  pop     rdi
0x180007ba5  pop     rsi
0x180007ba6  pop     rbp
0x180007ba7  pop     rbx
0x180007ba8  retn
0x180007ba9  mov     ebx, 0C0000162h
0x180007bae  call    cs:__imp_GetLastError
0x180007bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bbb  lea     rdx, WPP_GLOBAL_Control
0x180007bc2  cmp     rcx, rdx
0x180007bc5  jz      short loc_180007B8F
0x180007bc7  test    byte ptr [rcx+1Ch], 1
0x180007bcb  jz      short loc_180007B8F
0x180007bcd  mov     rcx, [rcx+10h]
0x180007bd1  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x180007bd8  mov     edx, 19h
0x180007bdd  mov     r9d, eax
0x180007be0  call    WPP_SF_d
0x180007be5  jmp     short loc_180007B8F
0x180007be7  mov     [r8], ebx
0x180007bea  mov     eax, ebx
0x180007bec  mov     [r8+8], rbx
0x180007bf0  add     rsp, 40h
0x180007bf4  pop     r14
0x180007bf6  pop     rdi
0x180007bf7  pop     rsi
0x180007bf8  pop     rbp
0x180007bf9  pop     rbx
0x180007bfa  retn
0x180007bfb  mov     ebx, 0C000000Dh
0x180007c00  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c07  lea     rdx, WPP_GLOBAL_Control
0x180007c0e  cmp     rcx, rdx
0x180007c11  jz      loc_180007B8A
0x180007c17  test    byte ptr [rcx+1Ch], 1
0x180007c1b  jz      loc_180007B8A
0x180007c21  mov     rcx, [rcx+10h]
0x180007c25  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x180007c2c  mov     edx, 1Ah
0x180007c31  call    WPP_SF_
0x180007c36  jmp     loc_180007B8A
0x180007c3b  mov     [rsi+2], bx
0x180007c3f  mov     ebx, 80090300h
0x180007c44  jmp     short loc_180007C00
0x180007c46  mov     ebx, 0C0000162h
0x180007c4b  call    cs:__imp_GetLastError
0x180007c51  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c58  lea     rdx, WPP_GLOBAL_Control
0x180007c5f  cmp     rcx, rdx
0x180007c62  jz      short loc_180007C82
0x180007c64  test    byte ptr [rcx+1Ch], 1
0x180007c68  jz      short loc_180007C82
0x180007c6a  mov     rcx, [rcx+10h]
0x180007c6e  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x180007c75  mov     edx, 1Bh
0x180007c7a  mov     r9d, eax
0x180007c7d  call    WPP_SF_d
0x180007c82  mov     rcx, rsi
0x180007c85  call    StringFree
0x180007c8a  jmp     loc_180007B8A
```
