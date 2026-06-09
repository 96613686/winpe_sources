# CDFGetLine(CRYPTCATCDF_ *,ushort *,ulong)

- ea: `0x18003ac7c`
- end: `0x18003ae45`
- name: `?CDFGetLine@@YAKPEAUCRYPTCATCDF_@@PEAGK@Z`
- size: `457`
- prototype: `unsigned int(struct CRYPTCATCDF_ *, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18003ae4c`
- `0x18003b10c`
- `0x18003b3d0`

## callees

- `0x1800077b0`
- `0x18003ac7c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003acab`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003ad89`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003ada7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003acab`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003ad89`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003ada7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003acf3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003acf3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003add5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003ae2d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003add5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003ae2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ad12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ade0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ae38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ad12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ade0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ae38`

## pseudocode

```c
__int64 __fastcall CDFGetLine(struct CRYPTCATCDF_ *a1, unsigned __int16 *a2)
{
  DWORD v4; // esi
  void *v5; // rax
  void *v6; // rdi
  HANDLE hFile; // rcx
  DWORD v9; // ecx
  __int64 i; // rdx
  __int64 v11; // r14
  int v12; // ebp
  DWORD v13; // eax
  int v14; // ebx
  __int64 v15; // rdx
  unsigned int v16; // ebx
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+18h] BYREF

  NumberOfBytesRead = 0;
  v4 = SetFilePointer(a1->hFile, 0, 0, 1u);
  if ( v4 == -1 )
    return 0;
  v5 = (void *)CatalogNew(0x802u);
  v6 = v5;
  if ( !v5 )
    return 0;
  hFile = a1->hFile;
  NumberOfBytesRead = 0;
  if ( !ReadFile(hFile, v5, 0x800u, &NumberOfBytesRead, 0) )
  {
LABEL_6:
    LocalFree(v6);
    return 0;
  }
  if ( !NumberOfBytesRead )
  {
    a1->fEOF = 1;
    goto LABEL_6;
  }
  *((_BYTE *)v6 + NumberOfBytesRead) = 0;
  v9 = NumberOfBytesRead;
  a1->fEOF = 0;
  if ( v9 )
  {
    for ( i = 0; (unsigned int)i < v9 - 1; i = (unsigned int)(i + 1) )
    {
      if ( *((_BYTE *)v6 + i) == 13 || *((_BYTE *)v6 + i) == 10 )
      {
        v11 = (unsigned int)(i + 1);
        v12 = (*((_BYTE *)v6 + v11) == 10) + 1;
        if ( *((_BYTE *)v6 + v11) != 10 )
          LODWORD(v11) = i;
        if ( SetFilePointer(a1->hFile, v11 + v4 + 1, 0, 0) == -1 )
          v13 = 0;
        else
          v13 = SetFilePointer(a1->hFile, 0, 0, 1u) - v12;
        a1->dwCurFilePos = v13;
        *((_BYTE *)v6 + (unsigned int)(v11 + 1)) = 0;
        v14 = MultiByteToWideChar(0xFDE9u, 0, (LPCCH)v6, -1, a2, 1024);
        LocalFree(v6);
        return (unsigned int)(v14 + 1);
      }
    }
  }
  v15 = v9 - 1;
  if ( *((_BYTE *)v6 + v15) == 26 )
  {
    --v9;
    NumberOfBytesRead = v15;
    a1->fEOF = 1;
    v4 = 0;
  }
  a1->dwCurFilePos = v4;
  *((_BYTE *)v6 + v9) = 0;
  v16 = MultiByteToWideChar(0xFDE9u, 0, (LPCCH)v6, -1, a2, 1024);
  LocalFree(v6);
  return v16;
}

```

## disassembly

```asm
0x18003ac7c  mov     rax, rsp
0x18003ac7f  mov     [rax+18h], r8d
0x18003ac83  push    rbx
0x18003ac84  push    rbp
0x18003ac85  push    rsi
0x18003ac86  push    rdi
0x18003ac87  push    r14
0x18003ac89  push    r15
0x18003ac8b  sub     rsp, 38h
0x18003ac8f  mov     r15, rdx
0x18003ac92  mov     dword ptr [rax+18h], 0
0x18003ac99  mov     rbx, rcx
0x18003ac9c  xor     edx, edx; lDistanceToMove
0x18003ac9e  mov     rcx, [rcx+8]; hFile
0x18003aca2  mov     r9d, 1; dwMoveMethod
0x18003aca8  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003acab  call    cs:__imp_SetFilePointer
0x18003acb1  mov     esi, eax
0x18003acb3  cmp     eax, 0FFFFFFFFh
0x18003acb6  jz      short loc_18003AD18
0x18003acb8  mov     ecx, 802h; uBytes
0x18003acbd  call    CatalogNew
0x18003acc2  mov     rdi, rax
0x18003acc5  test    rax, rax
0x18003acc8  jz      short loc_18003AD18
0x18003acca  mov     rcx, [rbx+8]; hFile
0x18003acce  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003acd6  mov     r8d, 800h; nNumberOfBytesToRead
0x18003acdc  mov     [rsp+68h+NumberOfBytesRead], 0
0x18003ace7  mov     rdx, rax; lpBuffer
0x18003acea  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18003acf3  call    cs:__imp_ReadFile
0x18003acf9  test    eax, eax
0x18003acfb  jz      short loc_18003AD0F
0x18003acfd  mov     eax, [rsp+68h+NumberOfBytesRead]
0x18003ad04  test    eax, eax
0x18003ad06  jnz     short loc_18003AD27
0x18003ad08  mov     dword ptr [rbx+18h], 1
0x18003ad0f  mov     rcx, rdi; hMem
0x18003ad12  call    cs:__imp_LocalFree
0x18003ad18  xor     eax, eax
0x18003ad1a  add     rsp, 38h
0x18003ad1e  pop     r15
0x18003ad20  pop     r14
0x18003ad22  pop     rdi
0x18003ad23  pop     rsi
0x18003ad24  pop     rbp
0x18003ad25  pop     rbx
0x18003ad26  retn
0x18003ad27  mov     byte ptr [rax+rdi], 0
0x18003ad2b  mov     ecx, [rsp+68h+NumberOfBytesRead]
0x18003ad32  mov     dword ptr [rbx+18h], 0
0x18003ad39  test    ecx, ecx
0x18003ad3b  jz      loc_18003ADEE
0x18003ad41  xor     edx, edx
0x18003ad43  mov     r8b, 0Ah
0x18003ad46  lea     eax, [rcx-1]
0x18003ad49  cmp     edx, eax
0x18003ad4b  jnb     loc_18003ADEE
0x18003ad51  cmp     byte ptr [rdx+rdi], 0Dh
0x18003ad55  jz      short loc_18003AD61
0x18003ad57  cmp     [rdx+rdi], r8b
0x18003ad5b  jz      short loc_18003AD61
0x18003ad5d  inc     edx
0x18003ad5f  jmp     short loc_18003AD46
0x18003ad61  mov     rcx, [rbx+8]; hFile
0x18003ad65  lea     r14d, [rdx+1]
0x18003ad69  xor     ebp, ebp
0x18003ad6b  cmp     [r14+rdi], r8b
0x18003ad6f  setz    bpl
0x18003ad73  inc     ebp
0x18003ad75  cmp     [r14+rdi], r8b
0x18003ad79  cmovnz  r14d, edx
0x18003ad7d  lea     edx, [rsi+1]
0x18003ad80  add     edx, r14d; lDistanceToMove
0x18003ad83  xor     r9d, r9d; dwMoveMethod
0x18003ad86  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003ad89  call    cs:__imp_SetFilePointer
0x18003ad8f  cmp     eax, 0FFFFFFFFh
0x18003ad92  jnz     short loc_18003AD98
0x18003ad94  xor     eax, eax
0x18003ad96  jmp     short loc_18003ADAF
0x18003ad98  mov     rcx, [rbx+8]; hFile
0x18003ad9c  mov     r9d, 1; dwMoveMethod
0x18003ada2  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003ada5  xor     edx, edx; lDistanceToMove
0x18003ada7  call    cs:__imp_SetFilePointer
0x18003adad  sub     eax, ebp
0x18003adaf  mov     [rbx+10h], eax
0x18003adb2  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18003adb6  lea     eax, [r14+1]
0x18003adba  mov     [rsp+68h+cchWideChar], 400h; cchWideChar
0x18003adc2  mov     r8, rdi; lpMultiByteStr
0x18003adc5  mov     byte ptr [rax+rdi], 0
0x18003adc9  xor     edx, edx; dwFlags
0x18003adcb  mov     [rsp+68h+lpOverlapped], r15; lpWideCharStr
0x18003add0  mov     ecx, 0FDE9h; CodePage
0x18003add5  call    cs:__imp_MultiByteToWideChar
0x18003addb  mov     rcx, rdi; hMem
0x18003adde  mov     ebx, eax
0x18003ade0  call    cs:__imp_LocalFree
0x18003ade6  lea     eax, [rbx+1]
0x18003ade9  jmp     loc_18003AD1A
0x18003adee  lea     edx, [rcx-1]
0x18003adf1  cmp     byte ptr [rdx+rdi], 1Ah
0x18003adf5  jnz     short loc_18003AE09
0x18003adf7  mov     ecx, edx
0x18003adf9  mov     [rsp+68h+NumberOfBytesRead], edx
0x18003ae00  mov     dword ptr [rbx+18h], 1
0x18003ae07  xor     esi, esi
0x18003ae09  mov     eax, ecx
0x18003ae0b  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18003ae0f  mov     [rbx+10h], esi
0x18003ae12  mov     r8, rdi; lpMultiByteStr
0x18003ae15  mov     [rsp+68h+cchWideChar], 400h; cchWideChar
0x18003ae1d  xor     edx, edx; dwFlags
0x18003ae1f  mov     ecx, 0FDE9h; CodePage
0x18003ae24  mov     [rsp+68h+lpOverlapped], r15; lpWideCharStr
0x18003ae29  mov     byte ptr [rax+rdi], 0
0x18003ae2d  call    cs:__imp_MultiByteToWideChar
0x18003ae33  mov     rcx, rdi; hMem
0x18003ae36  mov     ebx, eax
0x18003ae38  call    cs:__imp_LocalFree
0x18003ae3e  mov     eax, ebx
0x18003ae40  jmp     loc_18003AD1A
```
