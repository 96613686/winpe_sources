# file_read

- ea: `0x1800a08b0`
- end: `0x1800a0a0c`
- name: `file_read`
- size: `348`
- prototype: `__int64 __fastcall(LPVOID lpBuffer, DWORD nNumberOfBytesToRead)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800a06a0`
- `0x1800a0c30`

## callees

- `0x18009f910`
- `0x1800a08b0`
- `0x1800a19c8`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1800a08ee`
- `KERNEL32!ReadFile` at `0x1800a0943`
- `KERNEL32!ReadFile` at `0x1800a08ee`
- `KERNEL32!ReadFile` at `0x1800a0943`
- `USER32!CharNextA` at `0x1800a09a4`
- `USER32!CharNextA` at `0x1800a09a4`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x1800a097f`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x1800a097f`

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
0x1800a08b0  mov     r11, rsp
0x1800a08b3  push    rbx
0x1800a08b4  push    rbp
0x1800a08b5  push    rsi
0x1800a08b6  push    rdi
0x1800a08b7  push    r14
0x1800a08b9  push    r15
0x1800a08bb  sub     rsp, 38h
0x1800a08bf  mov     eax, [r8+0DDCh]
0x1800a08c6  mov     rsi, r8
0x1800a08c9  mov     dword ptr [r11+18h], 0
0x1800a08d1  mov     rdi, rcx
0x1800a08d4  test    eax, eax
0x1800a08d6  jnz     short loc_1800A091D
0x1800a08d8  mov     r8d, edx; nNumberOfBytesToRead
0x1800a08db  mov     qword ptr [r11-48h], 0
0x1800a08e3  mov     rdx, rcx; lpBuffer
0x1800a08e6  lea     r9, [r11+18h]; lpNumberOfBytesRead
0x1800a08ea  mov     rcx, [rsi+40h]; hFile
0x1800a08ee  call    cs:__imp_ReadFile
0x1800a08f5  nop     dword ptr [rax+rax+00h]
0x1800a08fa  test    eax, eax
0x1800a08fc  jz      short loc_1800A090D
0x1800a08fe  mov     ebx, [rsp+68h+NumberOfBytesRead]
0x1800a0905  test    ebx, ebx
0x1800a0907  jnz     loc_1800A09BD
0x1800a090d  xor     eax, eax
0x1800a090f  add     rsp, 38h
0x1800a0913  pop     r15
0x1800a0915  pop     r14
0x1800a0917  pop     rdi
0x1800a0918  pop     rsi
0x1800a0919  pop     rbp
0x1800a091a  pop     rbx
0x1800a091b  retn
0x1800a091d  cmp     eax, 1
0x1800a0920  jnz     short loc_1800A090D
0x1800a0922  shr     edx, 1
0x1800a0924  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800a092c  mov     r8d, edx; nNumberOfBytesToRead
0x1800a092f  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800a0938  lea     r14, [rcx+rdx]
0x1800a093c  mov     rcx, [rsi+40h]; hFile
0x1800a0940  mov     rdx, r14; lpBuffer
0x1800a0943  call    cs:__imp_ReadFile
0x1800a094a  nop     dword ptr [rax+rax+00h]
0x1800a094f  test    eax, eax
0x1800a0951  jz      short loc_1800A090D
0x1800a0953  mov     ebx, [rsp+68h+NumberOfBytesRead]
0x1800a095a  mov     ebp, ebx
0x1800a095c  test    ebx, ebx
0x1800a095e  jz      short loc_1800A090D
0x1800a0960  mov     al, [r14]
0x1800a0963  lea     r15, [rdi+1]
0x1800a0967  cmp     al, 0Ah
0x1800a0969  jnz     short loc_1800A0977
0x1800a096b  mov     byte ptr [rdi], 0Dh
0x1800a096e  add     rdi, 2
0x1800a0972  mov     [r15], al
0x1800a0975  jmp     short loc_1800A099F
0x1800a0977  mov     [rdi], al
0x1800a0979  mov     rdi, r15
0x1800a097c  mov     cl, [r14]; TestChar
0x1800a097f  call    cs:__imp_IsDBCSLeadByte
0x1800a0986  nop     dword ptr [rax+rax+00h]
0x1800a098b  test    eax, eax
0x1800a098d  jz      short loc_1800A09A1
0x1800a098f  cmp     ebp, 1
0x1800a0992  jbe     short loc_1800A09A1
0x1800a0994  mov     al, [r14+1]
0x1800a0998  lea     rdi, [r15+1]
0x1800a099c  mov     [r15], al
0x1800a099f  inc     ebx
0x1800a09a1  mov     rcx, r14; lpsz
0x1800a09a4  call    cs:__imp_CharNextA
0x1800a09ab  nop     dword ptr [rax+rax+00h]
0x1800a09b0  mov     r14, rax
0x1800a09b3  add     ebp, 0FFFFFFFFh
0x1800a09b6  jnz     short loc_1800A0960
0x1800a09b8  mov     eax, ebx
0x1800a09ba  sub     rdi, rax
0x1800a09bd  mov     r8, rsi
0x1800a09c0  mov     edx, ebx
0x1800a09c2  mov     rcx, rdi
0x1800a09c5  mov     r11d, ebx
0x1800a09c8  call    updcrc
0x1800a09cd  add     [rsi+50h], r11
0x1800a09d1  lea     rcx, [rsi+53D8h]; pszSrc
0x1800a09d8  mov     r8, [rsi+50h]
0x1800a09dc  mov     [rsi+54E0h], eax
0x1800a09e2  mov     eax, [rsi+54DCh]
0x1800a09e8  test    eax, eax
0x1800a09ea  jnz     short loc_1800A09F2
0x1800a09ec  mov     rdx, [rsi+58h]
0x1800a09f0  jmp     short loc_1800A09F7
0x1800a09f2  mov     edx, 64h ; 'd'
0x1800a09f7  xor     r9d, r9d
0x1800a09fa  test    eax, eax
0x1800a09fc  cmovnz  r8, r9
0x1800a0a00  call    SendMinorPercent
0x1800a0a05  mov     eax, ebx
0x1800a0a07  jmp     loc_1800A090F
```
