# file_read

- ea: `0x18009c0a0`
- end: `0x18009c1e3`
- name: `file_read`
- size: `323`
- prototype: `__int64 __fastcall(LPVOID lpBuffer, DWORD nNumberOfBytesToRead)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18009beac`
- `0x18009c3e4`

## callees

- `0x18009b1bc`
- `0x18009c0a0`
- `0x18009d0d8`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18009c0de`
- `KERNEL32!ReadFile` at `0x18009c12c`
- `KERNEL32!ReadFile` at `0x18009c0de`
- `KERNEL32!ReadFile` at `0x18009c12c`
- `USER32!CharNextA` at `0x18009c181`
- `USER32!CharNextA` at `0x18009c181`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x18009c162`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x18009c162`

## pseudocode

```c
__int64 __fastcall file_read(CHAR *lpBuffer, DWORD nNumberOfBytesToRead, __int64 a3)
{
  int v3; // eax
  CHAR *v5; // rdi
  DWORD v6; // ebx
  LPSTR v8; // r14
  DWORD v9; // ebp
  _BYTE *v10; // r15
  int v11; // eax
  __int64 v12; // r11
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+18h] BYREF

  v3 = *(_DWORD *)(a3 + 3548);
  NumberOfBytesRead = 0;
  v5 = lpBuffer;
  if ( v3 )
  {
    if ( v3 != 1 )
      return 0;
    v8 = &lpBuffer[nNumberOfBytesToRead >> 1];
    if ( !ReadFile(*(HANDLE *)(a3 + 64), v8, nNumberOfBytesToRead >> 1, &NumberOfBytesRead, 0) )
      return 0;
    v6 = NumberOfBytesRead;
    v9 = NumberOfBytesRead;
    if ( !NumberOfBytesRead )
      return 0;
    while ( 1 )
    {
      v10 = v5 + 1;
      if ( *v8 == 10 )
      {
        *v5 = 13;
        v5 += 2;
        *v10 = 10;
      }
      else
      {
        *v5++ = *v8;
        if ( !IsDBCSLeadByte(*v8) || v9 <= 1 )
          goto LABEL_14;
        v5 = v10 + 1;
        *v10 = v8[1];
      }
      ++v6;
LABEL_14:
      v8 = CharNextA(v8);
      if ( !--v9 )
      {
        v5 -= v6;
        goto LABEL_16;
      }
    }
  }
  if ( !ReadFile(*(HANDLE *)(a3 + 64), lpBuffer, nNumberOfBytesToRead, &NumberOfBytesRead, 0) )
    return 0;
  v6 = NumberOfBytesRead;
  if ( !NumberOfBytesRead )
    return 0;
LABEL_16:
  v11 = updcrc(v5, v6, a3);
  *(_QWORD *)(a3 + 80) += v12;
  *(_DWORD *)(a3 + 21728) = v11;
  SendMinorPercent((STRSAFE_LPCSTR)(a3 + 21464));
  return v6;
}

```

## disassembly

```asm
0x18009c0a0  mov     r11, rsp
0x18009c0a3  push    rbx
0x18009c0a4  push    rbp
0x18009c0a5  push    rsi
0x18009c0a6  push    rdi
0x18009c0a7  push    r14
0x18009c0a9  push    r15
0x18009c0ab  sub     rsp, 38h
0x18009c0af  mov     eax, [r8+0DDCh]
0x18009c0b6  mov     rsi, r8
0x18009c0b9  mov     dword ptr [r11+18h], 0
0x18009c0c1  mov     rdi, rcx
0x18009c0c4  test    eax, eax
0x18009c0c6  jnz     short loc_18009C106
0x18009c0c8  mov     r8d, edx; nNumberOfBytesToRead
0x18009c0cb  mov     qword ptr [r11-48h], 0
0x18009c0d3  mov     rdx, rcx; lpBuffer
0x18009c0d6  lea     r9, [r11+18h]; lpNumberOfBytesRead
0x18009c0da  mov     rcx, [rsi+40h]; hFile
0x18009c0de  call    cs:__imp_ReadFile
0x18009c0e4  test    eax, eax
0x18009c0e6  jz      short loc_18009C0F7
0x18009c0e8  mov     ebx, [rsp+68h+NumberOfBytesRead]
0x18009c0ef  test    ebx, ebx
0x18009c0f1  jnz     loc_18009C194
0x18009c0f7  xor     eax, eax
0x18009c0f9  add     rsp, 38h
0x18009c0fd  pop     r15
0x18009c0ff  pop     r14
0x18009c101  pop     rdi
0x18009c102  pop     rsi
0x18009c103  pop     rbp
0x18009c104  pop     rbx
0x18009c105  retn
0x18009c106  cmp     eax, 1
0x18009c109  jnz     short loc_18009C0F7
0x18009c10b  shr     edx, 1
0x18009c10d  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18009c115  mov     r8d, edx; nNumberOfBytesToRead
0x18009c118  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18009c121  lea     r14, [rcx+rdx]
0x18009c125  mov     rcx, [rsi+40h]; hFile
0x18009c129  mov     rdx, r14; lpBuffer
0x18009c12c  call    cs:__imp_ReadFile
0x18009c132  test    eax, eax
0x18009c134  jz      short loc_18009C0F7
0x18009c136  mov     ebx, [rsp+68h+NumberOfBytesRead]
0x18009c13d  mov     ebp, ebx
0x18009c13f  test    ebx, ebx
0x18009c141  jz      short loc_18009C0F7
0x18009c143  mov     al, [r14]
0x18009c146  lea     r15, [rdi+1]
0x18009c14a  cmp     al, 0Ah
0x18009c14c  jnz     short loc_18009C15A
0x18009c14e  mov     byte ptr [rdi], 0Dh
0x18009c151  add     rdi, 2
0x18009c155  mov     [r15], al
0x18009c158  jmp     short loc_18009C17C
0x18009c15a  mov     [rdi], al
0x18009c15c  mov     rdi, r15
0x18009c15f  mov     cl, [r14]; TestChar
0x18009c162  call    cs:__imp_IsDBCSLeadByte
0x18009c168  test    eax, eax
0x18009c16a  jz      short loc_18009C17E
0x18009c16c  cmp     ebp, 1
0x18009c16f  jbe     short loc_18009C17E
0x18009c171  mov     al, [r14+1]
0x18009c175  lea     rdi, [r15+1]
0x18009c179  mov     [r15], al
0x18009c17c  inc     ebx
0x18009c17e  mov     rcx, r14; lpsz
0x18009c181  call    cs:__imp_CharNextA
0x18009c187  mov     r14, rax
0x18009c18a  add     ebp, 0FFFFFFFFh
0x18009c18d  jnz     short loc_18009C143
0x18009c18f  mov     eax, ebx
0x18009c191  sub     rdi, rax
0x18009c194  mov     r8, rsi
0x18009c197  mov     edx, ebx
0x18009c199  mov     rcx, rdi
0x18009c19c  mov     r11d, ebx
0x18009c19f  call    updcrc
0x18009c1a4  add     [rsi+50h], r11
0x18009c1a8  lea     rcx, [rsi+53D8h]; pszSrc
0x18009c1af  mov     r8, [rsi+50h]
0x18009c1b3  mov     [rsi+54E0h], eax
0x18009c1b9  mov     eax, [rsi+54DCh]
0x18009c1bf  test    eax, eax
0x18009c1c1  jnz     short loc_18009C1C9
0x18009c1c3  mov     rdx, [rsi+58h]
0x18009c1c7  jmp     short loc_18009C1CE
0x18009c1c9  mov     edx, 64h ; 'd'
0x18009c1ce  xor     r9d, r9d
0x18009c1d1  test    eax, eax
0x18009c1d3  cmovnz  r8, r9
0x18009c1d7  call    SendMinorPercent
0x18009c1dc  mov     eax, ebx
0x18009c1de  jmp     loc_18009C0F9
```
