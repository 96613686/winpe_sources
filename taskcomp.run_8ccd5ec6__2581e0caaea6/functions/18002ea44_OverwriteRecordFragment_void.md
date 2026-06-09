# OverwriteRecordFragment(void)

- ea: `0x18002ea44`
- end: `0x18002ebcb`
- name: `?OverwriteRecordFragment@@YAXXZ`
- size: `391`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002ebd4`

## callees

- `0x18002ea44`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002eadd`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002eadd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002eb96`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002eb96`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ea98`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002eb49`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ea98`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002eb49`

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
0x18002ea44  push    rbp
0x18002ea46  push    rbx
0x18002ea47  push    rdi
0x18002ea48  push    r14
0x18002ea4a  lea     rbp, [rsp-168h]
0x18002ea52  sub     rsp, 268h
0x18002ea59  mov     rax, cs:__security_cookie
0x18002ea60  xor     rax, rsp
0x18002ea63  mov     [rbp+180h+var_30], rax
0x18002ea6a  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002ea71  mov     [rsp+280h+NumberOfBytesRead], 0
0x18002ea79  test    rcx, rcx
0x18002ea7c  jz      loc_18002EBAE
0x18002ea82  mov     r9d, 1; dwMoveMethod
0x18002ea88  mov     qword ptr [rsp+280h+DistanceToMoveHigh], 0
0x18002ea91  lea     r8, [rsp+280h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18002ea96  xor     edx, edx; lDistanceToMove
0x18002ea98  call    cs:__imp_SetFilePointer
0x18002ea9f  nop     dword ptr [rax+rax+00h]
0x18002eaa4  mov     [rsp+280h+DistanceToMoveHigh], eax
0x18002eaa8  cmp     eax, 0FFFFFFFFh
0x18002eaab  jz      loc_18002EBAE
0x18002eab1  mov     r14d, 0Ah
0x18002eab7  xor     ebx, ebx
0x18002eab9  movzx   edi, r14w
0x18002eabd  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002eac4  lea     r9, [rsp+280h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002eac9  mov     r8d, 200h; nNumberOfBytesToRead
0x18002eacf  mov     [rsp+280h+lpOverlapped], 0; lpOverlapped
0x18002ead8  lea     rdx, [rsp+280h+Buffer]; lpBuffer
0x18002eadd  call    cs:__imp_ReadFile
0x18002eae4  nop     dword ptr [rax+rax+00h]
0x18002eae9  test    eax, eax
0x18002eaeb  jz      short loc_18002EB2A
0x18002eaed  mov     ecx, [rsp+280h+NumberOfBytesRead]
0x18002eaf1  test    ecx, ecx
0x18002eaf3  jz      short loc_18002EB2A
0x18002eaf5  shr     ecx, 1
0x18002eaf7  mov     edx, 0
0x18002eafc  mov     [rsp+280h+NumberOfBytesRead], ecx
0x18002eb00  jz      short loc_18002EB23
0x18002eb02  cmp     di, r14w
0x18002eb06  jnz     short loc_18002EB15
0x18002eb08  cmp     [rsp+rdx*2+280h+Buffer], 22h ; '"'
0x18002eb0e  jnz     short loc_18002EB15
0x18002eb10  cmp     ebx, 4
0x18002eb13  ja      short loc_18002EB23
0x18002eb15  movzx   edi, [rsp+rdx*2+280h+Buffer]
0x18002eb1a  add     ebx, 2
0x18002eb1d  inc     edx
0x18002eb1f  cmp     edx, ecx
0x18002eb21  jb      short loc_18002EB02
0x18002eb23  cmp     edx, ecx
0x18002eb25  jnb     short loc_18002EABD
0x18002eb27  sub     ebx, 4
0x18002eb2a  mov     [rsp+280h+NumberOfBytesWritten], 0
0x18002eb32  test    ebx, ebx
0x18002eb34  jle     short loc_18002EBAE
0x18002eb36  mov     edx, [rsp+280h+DistanceToMoveHigh]; lDistanceToMove
0x18002eb3a  lea     r8, [rsp+280h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18002eb3f  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002eb46  xor     r9d, r9d; dwMoveMethod
0x18002eb49  call    cs:__imp_SetFilePointer
0x18002eb50  nop     dword ptr [rax+rax+00h]
0x18002eb55  cmp     eax, 0FFFFFFFFh
0x18002eb58  jz      short loc_18002EBAE
0x18002eb5a  mov     eax, 20h ; ' '
0x18002eb5f  lea     rdi, [rsp+280h+Buffer]
0x18002eb64  movzx   eax, ax
0x18002eb67  mov     ecx, 100h
0x18002eb6c  rep stosw
0x18002eb6f  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002eb76  lea     r9, [rsp+280h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002eb7b  mov     r8d, 200h
0x18002eb81  mov     [rsp+280h+lpOverlapped], 0; lpOverlapped
0x18002eb8a  cmp     ebx, r8d
0x18002eb8d  lea     rdx, [rsp+280h+Buffer]; lpBuffer
0x18002eb92  cmovb   r8d, ebx; nNumberOfBytesToWrite
0x18002eb96  call    cs:__imp_WriteFile
0x18002eb9d  nop     dword ptr [rax+rax+00h]
0x18002eba2  test    eax, eax
0x18002eba4  jz      short loc_18002EBAE
0x18002eba6  sub     ebx, [rsp+280h+NumberOfBytesWritten]
0x18002ebaa  test    ebx, ebx
0x18002ebac  jg      short loc_18002EB6F
0x18002ebae  mov     rcx, [rbp+180h+var_30]
0x18002ebb5  xor     rcx, rsp; StackCookie
0x18002ebb8  call    __security_check_cookie
0x18002ebbd  add     rsp, 268h
0x18002ebc4  pop     r14
0x18002ebc6  pop     rdi
0x18002ebc7  pop     rbx
0x18002ebc8  pop     rbp
0x18002ebc9  retn
```
