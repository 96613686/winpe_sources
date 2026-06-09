# OverwriteRecordFragment(void)

- ea: `0x18002cbb0`
- end: `0x18002cd1e`
- name: `?OverwriteRecordFragment@@YAXXZ`
- size: `366`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002cd24`

## callees

- `0x18002cbb0`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002cc43`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002cc43`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002ccf0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002ccf0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002cc04`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002cca9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002cc04`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002cca9`

## pseudocode

```c
void OverwriteRecordFragment(void)
{
  int v0; // ebx
  __int16 v1; // di
  unsigned int v2; // ecx
  __int64 v3; // rdx
  _WORD *v4; // rdi
  __int64 i; // rcx
  DWORD v6; // r8d
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-D0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+34h] [rbp-CCh] BYREF
  LONG DistanceToMoveHigh[6]; // [rsp+38h] [rbp-C8h] BYREF
  _WORD Buffer[256]; // [rsp+50h] [rbp-B0h] BYREF

  NumberOfBytesRead = 0;
  if ( ghLog )
  {
    DistanceToMoveHigh[1] = 0;
    DistanceToMoveHigh[0] = SetFilePointer(ghLog, 0, &DistanceToMoveHigh[1], 1u);
    if ( DistanceToMoveHigh[0] != -1 )
    {
      v0 = 0;
      v1 = 10;
      while ( ReadFile(ghLog, Buffer, 0x200u, &NumberOfBytesRead, 0) && NumberOfBytesRead )
      {
        v2 = NumberOfBytesRead >> 1;
        v3 = 0;
        for ( NumberOfBytesRead = v2; (unsigned int)v3 < v2; v3 = (unsigned int)(v3 + 1) )
        {
          if ( v1 == 10 && Buffer[v3] == 34 && (unsigned int)v0 > 4 )
            break;
          v1 = Buffer[v3];
          v0 += 2;
        }
        if ( (unsigned int)v3 < v2 )
        {
          v0 -= 4;
          break;
        }
      }
      NumberOfBytesWritten = 0;
      if ( v0 > 0 && SetFilePointer(ghLog, DistanceToMoveHigh[0], &DistanceToMoveHigh[1], 0) != -1 )
      {
        v4 = Buffer;
        for ( i = 256; i; --i )
          *v4++ = 32;
        do
        {
          v6 = 512;
          if ( (unsigned int)v0 < 0x200 )
            v6 = v0;
          if ( !WriteFile(ghLog, Buffer, v6, &NumberOfBytesWritten, 0) )
            break;
          v0 -= NumberOfBytesWritten;
        }
        while ( v0 > 0 );
      }
    }
  }
}

```

## disassembly

```asm
0x18002cbb0  push    rbp
0x18002cbb2  push    rbx
0x18002cbb3  push    rdi
0x18002cbb4  push    r14
0x18002cbb6  lea     rbp, [rsp-168h]
0x18002cbbe  sub     rsp, 268h
0x18002cbc5  mov     rax, cs:__security_cookie
0x18002cbcc  xor     rax, rsp
0x18002cbcf  mov     [rbp+180h+var_30], rax
0x18002cbd6  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002cbdd  mov     [rsp+280h+NumberOfBytesRead], 0
0x18002cbe5  test    rcx, rcx
0x18002cbe8  jz      loc_18002CD02
0x18002cbee  mov     r9d, 1; dwMoveMethod
0x18002cbf4  mov     qword ptr [rsp+280h+DistanceToMoveHigh], 0
0x18002cbfd  lea     r8, [rsp+280h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18002cc02  xor     edx, edx; lDistanceToMove
0x18002cc04  call    cs:__imp_SetFilePointer
0x18002cc0a  mov     [rsp+280h+DistanceToMoveHigh], eax
0x18002cc0e  cmp     eax, 0FFFFFFFFh
0x18002cc11  jz      loc_18002CD02
0x18002cc17  mov     r14d, 0Ah
0x18002cc1d  xor     ebx, ebx
0x18002cc1f  movzx   edi, r14w
0x18002cc23  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002cc2a  lea     r9, [rsp+280h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002cc2f  mov     r8d, 200h; nNumberOfBytesToRead
0x18002cc35  mov     [rsp+280h+lpOverlapped], 0; lpOverlapped
0x18002cc3e  lea     rdx, [rsp+280h+Buffer]; lpBuffer
0x18002cc43  call    cs:__imp_ReadFile
0x18002cc49  test    eax, eax
0x18002cc4b  jz      short loc_18002CC8A
0x18002cc4d  mov     ecx, [rsp+280h+NumberOfBytesRead]
0x18002cc51  test    ecx, ecx
0x18002cc53  jz      short loc_18002CC8A
0x18002cc55  shr     ecx, 1
0x18002cc57  mov     edx, 0
0x18002cc5c  mov     [rsp+280h+NumberOfBytesRead], ecx
0x18002cc60  jz      short loc_18002CC83
0x18002cc62  cmp     di, r14w
0x18002cc66  jnz     short loc_18002CC75
0x18002cc68  cmp     [rsp+rdx*2+280h+Buffer], 22h ; '"'
0x18002cc6e  jnz     short loc_18002CC75
0x18002cc70  cmp     ebx, 4
0x18002cc73  ja      short loc_18002CC83
0x18002cc75  movzx   edi, [rsp+rdx*2+280h+Buffer]
0x18002cc7a  add     ebx, 2
0x18002cc7d  inc     edx
0x18002cc7f  cmp     edx, ecx
0x18002cc81  jb      short loc_18002CC62
0x18002cc83  cmp     edx, ecx
0x18002cc85  jnb     short loc_18002CC23
0x18002cc87  sub     ebx, 4
0x18002cc8a  mov     [rsp+280h+NumberOfBytesWritten], 0
0x18002cc92  test    ebx, ebx
0x18002cc94  jle     short loc_18002CD02
0x18002cc96  mov     edx, [rsp+280h+DistanceToMoveHigh]; lDistanceToMove
0x18002cc9a  lea     r8, [rsp+280h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18002cc9f  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002cca6  xor     r9d, r9d; dwMoveMethod
0x18002cca9  call    cs:__imp_SetFilePointer
0x18002ccaf  cmp     eax, 0FFFFFFFFh
0x18002ccb2  jz      short loc_18002CD02
0x18002ccb4  mov     eax, 20h ; ' '
0x18002ccb9  lea     rdi, [rsp+280h+Buffer]
0x18002ccbe  movzx   eax, ax
0x18002ccc1  mov     ecx, 100h
0x18002ccc6  rep stosw
0x18002ccc9  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002ccd0  lea     r9, [rsp+280h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002ccd5  mov     r8d, 200h
0x18002ccdb  mov     [rsp+280h+lpOverlapped], 0; lpOverlapped
0x18002cce4  cmp     ebx, r8d
0x18002cce7  lea     rdx, [rsp+280h+Buffer]; lpBuffer
0x18002ccec  cmovb   r8d, ebx; nNumberOfBytesToWrite
0x18002ccf0  call    cs:__imp_WriteFile
0x18002ccf6  test    eax, eax
0x18002ccf8  jz      short loc_18002CD02
0x18002ccfa  sub     ebx, [rsp+280h+NumberOfBytesWritten]
0x18002ccfe  test    ebx, ebx
0x18002cd00  jg      short loc_18002CCC9
0x18002cd02  mov     rcx, [rbp+180h+var_30]
0x18002cd09  xor     rcx, rsp; StackCookie
0x18002cd0c  call    __security_check_cookie
0x18002cd11  add     rsp, 268h
0x18002cd18  pop     r14
0x18002cd1a  pop     rdi
0x18002cd1b  pop     rbx
0x18002cd1c  pop     rbp
0x18002cd1d  retn
```
