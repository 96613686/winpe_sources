# readzipfile

- ea: `0x18001b920`
- end: `0x18001c828`
- name: `readzipfile`
- size: `3848`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x18001a6cc`

## callees

- `0x180005464`
- `0x180015950`
- `0x180019af4`
- `0x18001a4c8`
- `0x18001b920`
- `0x18001d80c`
- `0x18001e070`
- `0x1800242c4`
- `0x180036f50`
- `0x18003791c`
- `0x180037928`
- `0x180037934`
- `0x180037958`
- `0x1800390f1`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001beeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c6c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001beeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c6c9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001bad3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001bedd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001bf53`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001c5b2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001c6bc`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001bad3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001bedd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001bf53`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001c5b2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001c6bc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001ba3f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001bb81`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001be63`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001bfc1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c07d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c138`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c47f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c530`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c63e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001ba3f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001bb81`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001be63`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001bfc1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c07d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c138`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c47f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c530`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c63e`
- `KERNEL32!lstrlenA` at `0x18001bddd`
- `KERNEL32!lstrlenA` at `0x18001bddd`
- `USER32!OemToCharBuffA` at `0x18001bdd0`
- `USER32!OemToCharBuffA` at `0x18001c32f`
- `USER32!OemToCharBuffA` at `0x18001bdd0`
- `USER32!OemToCharBuffA` at `0x18001c32f`

## pseudocode

```c
__int64 __fastcall readzipfile(__int64 a1)
{
  __int64 v1; // rdx
  __int64 result; // rax
  __int64 v4; // [rsp+40h] [rbp-39h]
  char Buffer; // [rsp+58h] [rbp-21h]
  DWORD v6[2]; // [rsp+60h] [rbp-19h] BYREF

  v1 = *(_QWORD *)(a1 + 5056);
  *(_QWORD *)(a1 + 5064) = 0;
  v6[0] = 0;
  Buffer = 0;
  *(_QWORD *)(a1 + 5080) = 0;
  v4 = 0;
  if ( (unsigned int)filetime(0, v1, v6)
    || (result = ValidZIPTestUTF8(*(const CHAR **)(a1 + 5056), a1), !(_DWORD)result) )
  {
    result = MakeZipFileDirUTF8(*(_QWORD *)(a1 + 5056));
    if ( !(_DWORD)result )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001b920  push    rbp
0x18001b922  push    rbx
0x18001b923  push    rdi
0x18001b924  push    r12
0x18001b926  push    r14
0x18001b928  lea     rbp, [rsp-37h]
0x18001b92d  sub     rsp, 0B0h
0x18001b934  mov     rax, cs:__security_cookie
0x18001b93b  xor     rax, rsp
0x18001b93e  mov     [rbp+57h+var_30], rax
0x18001b942  mov     rdx, [rcx+13C0h]
0x18001b949  lea     r14, [rcx+13D8h]
0x18001b950  xor     r12d, r12d
0x18001b953  mov     [rsp+0D0h+lpOverlapped], rcx
0x18001b958  mov     [rcx+13C8h], r12
0x18001b95f  lea     r9, [rbp+57h+var_90]
0x18001b963  mov     rbx, rcx
0x18001b966  mov     [rbp+57h+var_70], r12d
0x18001b96a  xor     ecx, ecx
0x18001b96c  mov     [rbp+57h+Buffer], r12b
0x18001b970  lea     r8, [rbp+57h+var_70]
0x18001b974  mov     [r14], r12
0x18001b977  mov     [rbp+57h+var_90], r12
0x18001b97b  call    filetime
0x18001b980  mov     rdi, [rbp+57h+var_90]
0x18001b984  test    eax, eax
0x18001b986  jz      short loc_18001B98D
0x18001b988  test    rdi, rdi
0x18001b98b  jz      short loc_18001B9A4
0x18001b98d  mov     rcx, [rbx+13C0h]
0x18001b994  mov     rdx, rbx
0x18001b997  call    ValidZIPTestUTF8
0x18001b99c  test    eax, eax
0x18001b99e  jnz     loc_18001C80D
0x18001b9a4  mov     rcx, [rbx+13C0h]
0x18001b9ab  call    MakeZipFileDirUTF8
0x18001b9b0  test    eax, eax
0x18001b9b2  jnz     loc_18001C80D
0x18001b9b8  mov     rax, [rbx+13C0h]
0x18001b9bf  mov     [rsp+0D0h+arg_8], rsi
0x18001b9c7  mov     [rsp+0D0h+arg_10], r13
0x18001b9cf  mov     [rsp+0D0h+arg_18], r15
0x18001b9d7  test    rax, rax
0x18001b9da  jz      loc_18001C7F3
0x18001b9e0  cmp     [rax], r12b
0x18001b9e3  jz      loc_18001C7F3
0x18001b9e9  mov     rcx, [rbx+5418h]
0x18001b9f0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001b9f4  jz      loc_18001C7F3
0x18001b9fa  test    rdi, rdi
0x18001b9fd  jz      loc_18001C7F3
0x18001ba03  xor     r8d, r8d
0x18001ba06  xor     edx, edx
0x18001ba08  call    DZSetFilePointer
0x18001ba0d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ba11  jz      loc_18001C616
0x18001ba17  mov     rsi, r12
0x18001ba1a  mov     [rbx+13E0h], r12
0x18001ba21  mov     rcx, [rbx+5418h]; hFile
0x18001ba28  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001ba2c  mov     r8d, 1; nNumberOfBytesToRead
0x18001ba32  mov     [rbp+57h+NumberOfBytesRead], r12d
0x18001ba36  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x18001ba3a  mov     [rsp+0D0h+lpOverlapped], r12; lpOverlapped
0x18001ba3f  call    cs:__imp_ReadFile
0x18001ba45  movzx   ecx, [rbp+57h+Buffer]
0x18001ba49  test    eax, eax
0x18001ba4b  jz      short loc_18001BA5D
0x18001ba4d  cmp     [rbp+57h+NumberOfBytesRead], 1
0x18001ba51  jnz     short loc_18001BA5D
0x18001ba53  cmp     cl, 50h ; 'P'
0x18001ba56  jz      short loc_18001BA5D
0x18001ba58  inc     rsi
0x18001ba5b  jmp     short loc_18001BA21
0x18001ba5d  mov     byte ptr [rbp+57h+var_68], cl
0x18001ba60  lea     rdx, [rbp+57h+var_68+1]
0x18001ba64  mov     rcx, [rbx+5418h]; hFile
0x18001ba6b  mov     r8d, 3
0x18001ba71  call    GetSomeBytes
0x18001ba76  movzx   edx, byte ptr [rbp+57h+var_66+1]
0x18001ba7a  movzx   r8d, byte ptr [rbp+57h+var_66]
0x18001ba7f  movzx   r9d, byte ptr [rbp+57h+var_68+1]
0x18001ba84  movzx   r10d, byte ptr [rbp+57h+var_68]
0x18001ba89  test    eax, eax
0x18001ba8b  jz      short loc_18001BB0B
0x18001ba8d  mov     ecx, edx
0x18001ba8f  shl     rcx, 8
0x18001ba93  or      rcx, r8
0x18001ba96  shl     rcx, 8
0x18001ba9a  or      rcx, r9
0x18001ba9d  shl     rcx, 8
0x18001baa1  or      rcx, r10
0x18001baa4  cmp     rcx, 4034B50h
0x18001baab  jz      short loc_18001BB0B
0x18001baad  cmp     rcx, 6054B50h
0x18001bab4  jz      short loc_18001BB0B
0x18001bab6  mov     rcx, [rbx+5418h]; hFile
0x18001babd  lea     r8, [rbp+57h+NumberOfBytesRead]; lpDistanceToMoveHigh
0x18001bac1  mov     r9d, 1; dwMoveMethod
0x18001bac7  mov     [rbp+57h+NumberOfBytesRead], 0FFFFFFFFh
0x18001bace  mov     edx, 0FFFFFFFDh; lDistanceToMove
0x18001bad3  call    cs:__imp_SetFilePointer
0x18001bad9  mov     edi, eax
0x18001badb  cmp     eax, 0FFFFFFFFh
0x18001bade  jnz     short loc_18001BAEE
0x18001bae0  call    cs:__imp_GetLastError
0x18001bae6  test    eax, eax
0x18001bae8  jnz     loc_18001C616
0x18001baee  movsxd  rcx, [rbp+57h+NumberOfBytesRead]
0x18001baf2  shl     rcx, 20h
0x18001baf6  add     rcx, rdi
0x18001baf9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001bafd  jz      loc_18001C616
0x18001bb03  inc     rsi
0x18001bb06  jmp     loc_18001BA21
0x18001bb0b  mov     ecx, edx
0x18001bb0d  mov     [rbx+13C8h], rsi
0x18001bb14  shl     ecx, 8
0x18001bb17  mov     eax, r9d
0x18001bb1a  or      ecx, r8d
0x18001bb1d  shl     eax, 8
0x18001bb20  shl     ecx, 10h
0x18001bb23  mov     r13, r14
0x18001bb26  or      ecx, eax
0x18001bb28  or      ecx, r10d
0x18001bb2b  cmp     ecx, 4034B50h
0x18001bb31  jnz     loc_18001C0E4
0x18001bb37  mov     ecx, 0A0h; Size
0x18001bb3c  mov     r14d, 14h
0x18001bb42  call    _o_malloc_0
0x18001bb47  mov     rdi, rax
0x18001bb4a  test    rax, rax
0x18001bb4d  jz      loc_18001C7A6
0x18001bb53  xor     edx, edx; Val
0x18001bb55  mov     r8d, 0A0h; Size
0x18001bb5b  mov     rcx, rax; void *
0x18001bb5e  call    memset_0
0x18001bb63  mov     rcx, [rbx+5418h]; hFile
0x18001bb6a  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001bb6e  mov     r8d, 1Ah; nNumberOfBytesToRead
0x18001bb74  mov     [rbp+57h+NumberOfBytesRead], r12d
0x18001bb78  lea     rdx, [rbp+57h+var_68]; lpBuffer
0x18001bb7c  mov     [rsp+0D0h+lpOverlapped], r12; lpOverlapped
0x18001bb81  call    cs:__imp_ReadFile
0x18001bb87  test    eax, eax
0x18001bb89  jz      loc_18001C616
0x18001bb8f  cmp     [rbp+57h+NumberOfBytesRead], 1Ah
0x18001bb93  jnz     loc_18001C616
0x18001bb99  movzx   ecx, byte ptr [rbp+57h+var_68+1]
0x18001bb9d  movzx   eax, byte ptr [rbp+57h+var_68]
0x18001bba1  mov     [rdi], r14w
0x18001bba5  shl     cx, 8
0x18001bba9  or      cx, ax
0x18001bbac  mov     [rdi+2], cx
0x18001bbb0  movzx   ecx, byte ptr [rbp+57h+var_66+1]
0x18001bbb4  movzx   eax, byte ptr [rbp+57h+var_66]
0x18001bbb8  shl     cx, 8
0x18001bbbc  or      cx, ax
0x18001bbbf  mov     [rdi+46h], cx
0x18001bbc3  mov     [rdi+4], cx
0x18001bbc7  movzx   eax, byte ptr [rbp+57h+var_64]
0x18001bbcb  mov     word ptr [rbp+57h+NumberOfBytesRead], cx
0x18001bbcf  movzx   ecx, byte ptr [rbp+57h+var_64+1]
0x18001bbd3  shl     cx, 8
0x18001bbd7  or      cx, ax
0x18001bbda  mov     [rdi+6], cx
0x18001bbde  movzx   eax, byte ptr [rbp+57h+var_60]
0x18001bbe2  movzx   ecx, byte ptr [rbp+57h+var_60+1]
0x18001bbe6  shl     ecx, 8
0x18001bbe9  or      ecx, eax
0x18001bbeb  movzx   eax, byte ptr [rbp+57h+var_62+1]
0x18001bbef  shl     ecx, 10h
0x18001bbf2  shl     eax, 8
0x18001bbf5  or      ecx, eax
0x18001bbf7  movzx   eax, byte ptr [rbp+57h+var_62]
0x18001bbfb  or      ecx, eax
0x18001bbfd  mov     [rdi+8], ecx
0x18001bc00  movzx   eax, byte ptr [rbp+57h+var_5C]
0x18001bc04  movzx   ecx, byte ptr [rbp+57h+var_5C+1]
0x18001bc08  shl     ecx, 8
0x18001bc0b  or      ecx, eax
0x18001bc0d  movzx   eax, byte ptr [rbp+57h+var_5E+1]
0x18001bc11  shl     eax, 8
0x18001bc14  shl     ecx, 10h
0x18001bc17  or      ecx, eax
0x18001bc19  movzx   eax, byte ptr [rbp+57h+var_5E]
0x18001bc1d  or      ecx, eax
0x18001bc1f  mov     [rdi+0Ch], ecx
0x18001bc22  movzx   eax, byte ptr [rbp+57h+var_58]
0x18001bc26  movzx   r14d, byte ptr [rbp+57h+var_58+1]
0x18001bc2b  shl     r14, 8
0x18001bc2f  or      r14, rax
0x18001bc32  movzx   eax, byte ptr [rbp+57h+var_5A+1]
0x18001bc36  shl     r14, 8
0x18001bc3a  or      r14, rax
0x18001bc3d  movzx   eax, byte ptr [rbp+57h+var_5A]
0x18001bc41  shl     r14, 8
0x18001bc45  or      r14, rax
0x18001bc48  mov     [rdi+10h], r14
0x18001bc4c  movzx   eax, byte ptr [rbp+57h+var_54]
0x18001bc50  movzx   ecx, byte ptr [rbp+57h+var_54+1]
0x18001bc54  shl     rcx, 8
0x18001bc58  or      rcx, rax
0x18001bc5b  movzx   eax, byte ptr [rbp+57h+var_56+1]
0x18001bc5f  shl     rcx, 8
0x18001bc63  or      rcx, rax
0x18001bc66  movzx   eax, byte ptr [rbp+57h+var_56]
0x18001bc6a  shl     rcx, 8
0x18001bc6e  or      rcx, rax
0x18001bc71  mov     [rdi+18h], rcx
0x18001bc75  movzx   eax, byte ptr [rbp+57h+var_52]
0x18001bc79  movzx   r15d, byte ptr [rbp+57h+var_52+1]
0x18001bc7e  shl     r15, 8
0x18001bc82  or      r15, rax
0x18001bc85  mov     [rdi+20h], r15
0x18001bc89  movzx   eax, byte ptr [rbp+57h+var_50]
0x18001bc8d  movzx   ecx, byte ptr [rbp+57h+var_50+1]
0x18001bc91  shl     rcx, 8
0x18001bc95  or      rcx, rax
0x18001bc98  mov     eax, [rbp+57h+var_70]
0x18001bc9b  mov     [rdi+28h], rcx
0x18001bc9f  xor     ecx, ecx
0x18001bca1  mov     [rdi+48h], eax
0x18001bca4  lea     rax, [rdi+98h]
0x18001bcab  mov     [rdi+38h], rcx
0x18001bcaf  mov     [rdi+40h], ecx
0x18001bcb2  mov     [rdi+44h], cx
0x18001bcb6  mov     [rdi+80h], cx
0x18001bcbd  mov     [r13+0], rdi
0x18001bcc1  mov     [rbp+57h+var_80], rax
0x18001bcc5  mov     [rax], rcx
0x18001bcc8  test    r15, r15
0x18001bccb  jz      loc_18001C604
0x18001bcd1  lea     rcx, [r15+1]; Size
0x18001bcd5  call    _o_malloc_0
0x18001bcda  mov     [rdi+78h], rax
0x18001bcde  mov     r13, rax
0x18001bce1  test    rax, rax
0x18001bce4  jz      loc_18001C7A6
0x18001bcea  mov     rcx, [rdi+28h]; Size
0x18001bcee  test    rcx, rcx
0x18001bcf1  jz      short loc_18001BD05
0x18001bcf3  call    _o_malloc_0
0x18001bcf8  mov     [rdi+60h], rax
0x18001bcfc  test    rax, rax
0x18001bcff  jz      loc_18001C7A6
0x18001bd05  mov     byte ptr [r13+0], 0
0x18001bd0a  mov     r8, r15
0x18001bd0d  mov     rdx, [rdi+78h]
0x18001bd11  mov     rcx, [rbx+5418h]; hFile
0x18001bd18  call    GetSomeBytes
0x18001bd1d  test    eax, eax
0x18001bd1f  jz      loc_18001C616
0x18001bd25  mov     rax, [rdi+78h]
0x18001bd29  mov     byte ptr [r15+rax], 0
0x18001bd2e  mov     r8, [rdi+28h]
0x18001bd32  test    r8, r8
0x18001bd35  jz      short loc_18001BD4F
0x18001bd37  mov     rdx, [rdi+60h]
0x18001bd3b  mov     rcx, [rbx+5418h]; hFile
0x18001bd42  call    GetSomeBytes
0x18001bd47  test    eax, eax
0x18001bd49  jz      loc_18001C616
0x18001bd4f  xor     ecx, ecx
0x18001bd51  lea     rax, [rbp+57h+var_90]
0x18001bd55  mov     [rsp+0D0h+var_A0], rax; __int64
0x18001bd5a  lea     r9, [rdi+10h]
0x18001bd5e  mov     [rsp+0D0h+var_A8], rcx; __int64
0x18001bd63  lea     r8, [rdi+18h]
0x18001bd67  mov     [rsp+0D0h+lpOverlapped], rcx; __int64
0x18001bd6c  lea     rdx, [rdi+28h]
0x18001bd70  mov     [rbp+57h+var_90], rcx
0x18001bd74  mov     [rdi+88h], rcx
0x18001bd7b  mov     rcx, [rdi+60h]; Src
0x18001bd7f  call    ParseExtra64
0x18001bd84  test    eax, eax
0x18001bd86  jz      short loc_18001BD97
0x18001bd88  mov     rax, [rbp+57h+var_90]
0x18001bd8c  mov     r14, [rdi+10h]
0x18001bd90  mov     [rdi+88h], rax
0x18001bd97  test    r14, r14
0x18001bd9a  jz      short loc_18001BDBB
0x18001bd9c  mov     rcx, [rbx+5418h]
0x18001bda3  mov     r8d, 1
0x18001bda9  mov     rdx, r14
0x18001bdac  call    DZSetFilePointer
0x18001bdb1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bdb5  jz      loc_18001BF0A
0x18001bdbb  mov     eax, 800h
0x18001bdc0  test    [rdi+4], ax
0x18001bdc4  jnz     short loc_18001BDD6
0x18001bdc6  mov     rcx, [rdi+78h]; lpszSrc
0x18001bdca  mov     r8d, r15d; cchDstLength
0x18001bdcd  mov     rdx, rcx; lpszDst
0x18001bdd0  call    cs:__imp_OemToCharBuffA
0x18001bdd6  mov     r13, [rdi+78h]
0x18001bdda  mov     rcx, r13; lpString
0x18001bddd  call    cs:__imp_lstrlenA
0x18001bde3  inc     eax
0x18001bde5  mov     ecx, eax; Size
  ... truncated ...
```
