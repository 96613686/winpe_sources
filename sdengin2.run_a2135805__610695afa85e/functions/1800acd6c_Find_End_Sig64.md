# Find_End_Sig64

- ea: `0x1800acd6c`
- end: `0x1800ad0cf`
- name: `Find_End_Sig64`
- size: `867`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800aef84`

## callees

- `0x1800a8544`
- `0x1800ac3cc`
- `0x1800acd6c`
- `0x1800ae978`
- `0x1800aea0c`
- `0x1800b1448`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x1800acfae`
- `KERNEL32!GlobalUnlock` at `0x1800ad051`
- `KERNEL32!GlobalUnlock` at `0x1800ad07f`
- `KERNEL32!GlobalUnlock` at `0x1800acfae`
- `KERNEL32!GlobalUnlock` at `0x1800ad051`
- `KERNEL32!GlobalUnlock` at `0x1800ad07f`
- `KERNEL32!GlobalLock` at `0x1800aced9`
- `KERNEL32!GlobalLock` at `0x1800aced9`
- `KERNEL32!ReadFile` at `0x1800acf0c`
- `KERNEL32!ReadFile` at `0x1800ad012`
- `KERNEL32!ReadFile` at `0x1800acf0c`
- `KERNEL32!ReadFile` at `0x1800ad012`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800acd92`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800acd92`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800acebe`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800acebe`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800acfbd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800ad060`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800ad08e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800ad0ba`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800acfbd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800ad060`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800ad08e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800ad0ba`

## pseudocode

```c
__int64 Find_End_Sig64()
{
  char *Value; // rax
  char *v1; // rdi
  unsigned int v2; // eax
  int v3; // eax
  __int64 v4; // r14
  int v5; // r15d
  __int64 v6; // rbx
  char v7; // r13
  int v8; // r12d
  char v9; // r15
  char v10; // al
  __int64 v11; // rdx
  __int64 v12; // rsi
  HGLOBAL v13; // rax
  void *v14; // rbx
  _BYTE *v15; // rax
  _BYTE *v16; // r14
  __int64 v17; // rcx
  __int64 v18; // rdx
  int v19; // r15d
  char v20; // r10
  __int64 v21; // r12
  char v22; // r9
  int i; // eax
  char v24; // r8
  __int64 v25; // rbx
  __int64 v26; // rcx
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+8h] BYREF
  int v29; // [rsp+78h] [rbp+10h]
  int v30; // [rsp+80h] [rbp+18h]

  NumberOfBytesRead = 0;
  Value = (char *)TlsGetValue(dwUnZIPTlsIndex);
  v1 = Value;
  if ( !Value )
    return -1;
  v2 = DriveFromPath(Value + 71270);
  v3 = IsMediaRemovable(v2);
  if ( !*((_DWORD *)v1 + 8) && !v3 )
  {
    v4 = 16;
    v5 = 3;
    v6 = *(_QWORD *)(v1 + 72190) - 16LL;
    while ( v6 >= 0 && v4 <= 102400 )
    {
      DZSetFilePointer(*((_QWORD *)v1 + 571), v6, 0);
      v29 = fget_byte();
      v7 = fget_byte();
      v30 = fget_byte();
      v8 = 18 - v5;
      v9 = v30;
      while ( v8 > 0 )
      {
        v10 = fget_byte();
        if ( (_BYTE)v29 == 80 && v7 == 75 && v9 == 6 && v10 == 7 )
          goto LABEL_39;
        LOBYTE(v29) = v7;
        --v8;
        v7 = v9;
        v9 = v10;
      }
      if ( v6 <= 0 )
        break;
      v6 = 0;
      v4 += 16;
      v5 = 0;
      if ( *(_QWORD *)(v1 + 72190) - v4 >= 0 )
        v6 = *(_QWORD *)(v1 + 72190) - v4;
    }
    return -1;
  }
  v11 = *(_QWORD *)(v1 + 72190);
  v12 = 102400;
  if ( v11 < 102400 )
    v12 = *(_QWORD *)(v1 + 72190);
  DZSetFilePointer(*((_QWORD *)v1 + 571), v11 - v12, 0);
  v13 = GlobalAlloc(2u, (int)v12);
  v14 = v13;
  if ( !v13 )
    return -4;
  v15 = GlobalLock(v13);
  v16 = v15;
  if ( !v15 )
  {
    GlobalFree(v14);
    return -4;
  }
  if ( !ReadFile(*((HANDLE *)v1 + 571), v15, v12, &NumberOfBytesRead, 0) || NumberOfBytesRead != (_DWORD)v12 )
  {
LABEL_45:
    GlobalUnlock(v14);
    GlobalFree(v14);
    return -1;
  }
  v17 = v12 - 16;
  v18 = 16;
  v19 = 3;
  while ( v17 >= 0 && v18 <= v12 )
  {
    v20 = v16[v17];
    v21 = v17 + 2;
    v22 = v16[v17 + 1];
    for ( i = 16 - v19; i > 0; --i )
    {
      v24 = v16[v21++];
      if ( v20 == 80 && v22 == 75 && v24 == 6 && v16[v21] == 7 )
      {
        GlobalUnlock(v14);
        GlobalFree(v14);
        v25 = v21 + *(_QWORD *)(v1 + 72190) - v12 + 1;
        if ( DZSetFilePointer(*((_QWORD *)v1 + 571), v25, 0) == v25 )
        {
LABEL_39:
          if ( ReadFile(*((HANDLE *)v1 + 571), v1 + 5460, 0x10u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 16 )
          {
            v26 = *((_QWORD *)v1 + 683);
            *((_DWORD *)v1 + 1369) = *((_DWORD *)v1 + 1368);
            *((_DWORD *)v1 + 1370) = *((_DWORD *)v1 + 1365);
            return v26;
          }
        }
        return -1;
      }
      v20 = v22;
      v22 = v24;
    }
    if ( v17 <= 0 )
      goto LABEL_45;
    v17 = 0;
    v18 += 16;
    v19 = 0;
    if ( v12 - v18 >= 0 )
      v17 = v12 - v18;
  }
  GlobalUnlock(v14);
  GlobalFree(v14);
  return -(__int64)((unsigned int)IsCDPlacedFirst() != 0) - 2;
}

```

## disassembly

```asm
0x1800acd6c  mov     [rsp+arg_18], rbx
0x1800acd71  mov     [rsp+NumberOfBytesRead], ecx
0x1800acd75  push    rbp
0x1800acd76  push    rsi
0x1800acd77  push    rdi
0x1800acd78  push    r12
0x1800acd7a  push    r13
0x1800acd7c  push    r14
0x1800acd7e  push    r15
0x1800acd80  sub     rsp, 30h
0x1800acd84  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x1800acd8a  mov     [rsp+68h+NumberOfBytesRead], 0
0x1800acd92  call    cs:__imp_TlsGetValue
0x1800acd99  nop     dword ptr [rax+rax+00h]
0x1800acd9e  mov     rdi, rax
0x1800acda1  test    rax, rax
0x1800acda4  jz      loc_1800AD09A
0x1800acdaa  lea     rcx, [rax+11666h]; Str1
0x1800acdb1  call    DriveFromPath
0x1800acdb6  mov     ecx, eax
0x1800acdb8  call    IsMediaRemovable
0x1800acdbd  cmp     dword ptr [rdi+20h], 0
0x1800acdc1  jnz     loc_1800ACE91
0x1800acdc7  test    eax, eax
0x1800acdc9  jnz     loc_1800ACE91
0x1800acdcf  mov     rbx, [rdi+119FEh]
0x1800acdd6  lea     ebp, [rax+10h]
0x1800acdd9  mov     r14d, ebp
0x1800acddc  lea     r15d, [rax+3]
0x1800acde0  sub     rbx, rbp
0x1800acde3  mov     esi, 19000h
0x1800acde8  test    rbx, rbx
0x1800acdeb  js      loc_1800AD09A
0x1800acdf1  cmp     r14, rsi
0x1800acdf4  jg      loc_1800AD09A
0x1800acdfa  mov     rcx, [rdi+11D8h]
0x1800ace01  xor     r8d, r8d
0x1800ace04  mov     rdx, rbx
0x1800ace07  call    DZSetFilePointer
0x1800ace0c  call    fget_byte
0x1800ace11  mov     [rsp+68h+arg_8], eax
0x1800ace15  call    fget_byte
0x1800ace1a  mov     r13d, eax
0x1800ace1d  call    fget_byte
0x1800ace22  mov     r12d, 12h
0x1800ace28  mov     [rsp+68h+arg_10], eax
0x1800ace2f  sub     r12d, r15d
0x1800ace32  mov     r15d, eax
0x1800ace35  test    r12d, r12d
0x1800ace38  jle     short loc_1800ACE6A
0x1800ace3a  call    fget_byte
0x1800ace3f  cmp     byte ptr [rsp+68h+arg_8], 50h ; 'P'
0x1800ace44  jnz     short loc_1800ACE5A
0x1800ace46  cmp     r13b, 4Bh ; 'K'
0x1800ace4a  jnz     short loc_1800ACE5A
0x1800ace4c  cmp     r15b, 6
0x1800ace50  jnz     short loc_1800ACE5A
0x1800ace52  cmp     al, 7
0x1800ace54  jz      loc_1800ACFF0
0x1800ace5a  mov     byte ptr [rsp+68h+arg_8], r13b
0x1800ace5f  dec     r12d
0x1800ace62  mov     r13b, r15b
0x1800ace65  mov     r15b, al
0x1800ace68  jmp     short loc_1800ACE35
0x1800ace6a  test    rbx, rbx
0x1800ace6d  jle     loc_1800AD09A
0x1800ace73  mov     rax, [rdi+119FEh]
0x1800ace7a  mov     ebx, 0
0x1800ace7f  add     r14, rbp
0x1800ace82  mov     r15d, ebx
0x1800ace85  sub     rax, r14
0x1800ace88  cmovns  rbx, rax
0x1800ace8c  jmp     loc_1800ACDE8
0x1800ace91  mov     rdx, [rdi+119FEh]
0x1800ace98  mov     esi, 19000h
0x1800ace9d  mov     rcx, [rdi+11D8h]
0x1800acea4  cmp     rdx, rsi
0x1800acea7  cmovl   rsi, rdx
0x1800aceab  xor     r8d, r8d
0x1800aceae  sub     rdx, rsi
0x1800aceb1  call    DZSetFilePointer
0x1800aceb6  movsxd  rdx, esi; dwBytes
0x1800aceb9  mov     ecx, 2; uFlags
0x1800acebe  call    cs:__imp_GlobalAlloc
0x1800acec5  nop     dword ptr [rax+rax+00h]
0x1800aceca  mov     rbx, rax
0x1800acecd  test    rax, rax
0x1800aced0  jz      loc_1800AD0C6
0x1800aced6  mov     rcx, rax; hMem
0x1800aced9  call    cs:__imp_GlobalLock
0x1800acee0  nop     dword ptr [rax+rax+00h]
0x1800acee5  mov     r14, rax
0x1800acee8  test    rax, rax
0x1800aceeb  jz      loc_1800AD0B7
0x1800acef1  mov     rcx, [rdi+11D8h]; hFile
0x1800acef8  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800acefd  mov     r8d, esi; nNumberOfBytesToRead
0x1800acf00  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800acf09  mov     rdx, rax; lpBuffer
0x1800acf0c  call    cs:__imp_ReadFile
0x1800acf13  nop     dword ptr [rax+rax+00h]
0x1800acf18  test    eax, eax
0x1800acf1a  jz      loc_1800AD07C
0x1800acf20  cmp     [rsp+68h+NumberOfBytesRead], esi
0x1800acf24  jnz     loc_1800AD07C
0x1800acf2a  mov     ebp, 10h
0x1800acf2f  lea     rcx, [rsi-10h]
0x1800acf33  mov     edx, ebp
0x1800acf35  lea     r15d, [rbp-0Dh]
0x1800acf39  test    rcx, rcx
0x1800acf3c  js      loc_1800AD04E
0x1800acf42  cmp     rdx, rsi
0x1800acf45  jg      loc_1800AD04E
0x1800acf4b  mov     r10b, [r14+rcx]
0x1800acf4f  lea     r12, [rcx+2]
0x1800acf53  mov     r9b, [r14+rcx+1]
0x1800acf58  mov     eax, ebp
0x1800acf5a  sub     eax, r15d
0x1800acf5d  test    eax, eax
0x1800acf5f  jle     short loc_1800ACF8B
0x1800acf61  mov     r8b, [r14+r12]
0x1800acf65  inc     r12
0x1800acf68  cmp     r10b, 50h ; 'P'
0x1800acf6c  jnz     short loc_1800ACF81
0x1800acf6e  cmp     r9b, 4Bh ; 'K'
0x1800acf72  jnz     short loc_1800ACF81
0x1800acf74  cmp     r8b, 6
0x1800acf78  jnz     short loc_1800ACF81
0x1800acf7a  cmp     byte ptr [r14+r12], 7
0x1800acf7f  jz      short loc_1800ACFAB
0x1800acf81  mov     r10b, r9b
0x1800acf84  dec     eax
0x1800acf86  mov     r9b, r8b
0x1800acf89  jmp     short loc_1800ACF5D
0x1800acf8b  test    rcx, rcx
0x1800acf8e  jle     loc_1800AD07C
0x1800acf94  mov     ecx, 0
0x1800acf99  add     rdx, rbp
0x1800acf9c  mov     rax, rsi
0x1800acf9f  mov     r15d, ecx
0x1800acfa2  sub     rax, rdx
0x1800acfa5  cmovns  rcx, rax
0x1800acfa9  jmp     short loc_1800ACF39
0x1800acfab  mov     rcx, rbx; hMem
0x1800acfae  call    cs:__imp_GlobalUnlock
0x1800acfb5  nop     dword ptr [rax+rax+00h]
0x1800acfba  mov     rcx, rbx; hMem
0x1800acfbd  call    cs:__imp_GlobalFree
0x1800acfc4  nop     dword ptr [rax+rax+00h]
0x1800acfc9  mov     rbx, [rdi+119FEh]
0x1800acfd0  xor     r8d, r8d
0x1800acfd3  mov     rcx, [rdi+11D8h]
0x1800acfda  sub     rbx, rsi
0x1800acfdd  inc     rbx
0x1800acfe0  add     rbx, r12
0x1800acfe3  mov     rdx, rbx
0x1800acfe6  call    DZSetFilePointer
0x1800acfeb  cmp     rax, rbx
0x1800acfee  jnz     short loc_1800AD045
0x1800acff0  mov     rcx, [rdi+11D8h]; hFile
0x1800acff7  lea     rbx, [rdi+1554h]
0x1800acffe  mov     rdx, rbx; lpBuffer
0x1800ad001  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800ad00a  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800ad00f  mov     r8d, ebp; nNumberOfBytesToRead
0x1800ad012  call    cs:__imp_ReadFile
0x1800ad019  nop     dword ptr [rax+rax+00h]
0x1800ad01e  test    eax, eax
0x1800ad020  jz      short loc_1800AD045
0x1800ad022  cmp     [rsp+68h+NumberOfBytesRead], ebp
0x1800ad026  jnz     short loc_1800AD045
0x1800ad028  mov     eax, [rdi+1560h]
0x1800ad02e  mov     rcx, [rdi+1558h]
0x1800ad035  mov     [rdi+1564h], eax
0x1800ad03b  mov     eax, [rbx]
0x1800ad03d  mov     [rdi+1568h], eax
0x1800ad043  jmp     short loc_1800AD049
0x1800ad045  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800ad049  mov     rax, rcx
0x1800ad04c  jmp     short loc_1800AD09E
0x1800ad04e  mov     rcx, rbx; hMem
0x1800ad051  call    cs:__imp_GlobalUnlock
0x1800ad058  nop     dword ptr [rax+rax+00h]
0x1800ad05d  mov     rcx, rbx; hMem
0x1800ad060  call    cs:__imp_GlobalFree
0x1800ad067  nop     dword ptr [rax+rax+00h]
0x1800ad06c  call    IsCDPlacedFirst
0x1800ad071  neg     eax
0x1800ad073  sbb     rax, rax
0x1800ad076  add     rax, 0FFFFFFFFFFFFFFFEh
0x1800ad07a  jmp     short loc_1800AD09E
0x1800ad07c  mov     rcx, rbx; hMem
0x1800ad07f  call    cs:__imp_GlobalUnlock
0x1800ad086  nop     dword ptr [rax+rax+00h]
0x1800ad08b  mov     rcx, rbx; hMem
0x1800ad08e  call    cs:__imp_GlobalFree
0x1800ad095  nop     dword ptr [rax+rax+00h]
0x1800ad09a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ad09e  mov     rbx, [rsp+68h+arg_18]
0x1800ad0a6  add     rsp, 30h
0x1800ad0aa  pop     r15
0x1800ad0ac  pop     r14
0x1800ad0ae  pop     r13
0x1800ad0b0  pop     r12
0x1800ad0b2  pop     rdi
0x1800ad0b3  pop     rsi
0x1800ad0b4  pop     rbp
0x1800ad0b5  retn
0x1800ad0b7  mov     rcx, rbx; hMem
0x1800ad0ba  call    cs:__imp_GlobalFree
0x1800ad0c1  nop     dword ptr [rax+rax+00h]
0x1800ad0c6  mov     rax, 0FFFFFFFFFFFFFFFCh
0x1800ad0cd  jmp     short loc_1800AD09E
```
