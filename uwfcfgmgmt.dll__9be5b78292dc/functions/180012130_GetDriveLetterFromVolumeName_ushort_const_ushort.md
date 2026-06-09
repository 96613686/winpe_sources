# GetDriveLetterFromVolumeName(ushort const *,ushort *)

- ea: `0x180012130`
- end: `0x1800122be`
- name: `?GetDriveLetterFromVolumeName@@YAJPEBGPEAG@Z`
- size: `398`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x18000fd10`
- `0x180012b00`

## callees

- `0x180001384`
- `0x180002686`
- `0x180012130`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001229e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001229e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012191`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001225e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012191`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001225e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012295`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012295`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180012254`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180012254`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001217c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001217c`

## string_xrefs

- `0x18001215a`: `\\.\MountPointManager`

## pseudocode

```c
__int64 __fastcall GetDriveLetterFromVolumeName(const unsigned __int16 *Src, unsigned __int16 *a2)
{
  __int64 v4; // rbx
  HANDLE FileW; // r15
  _WORD *v6; // rdi
  signed int LastError; // eax
  signed int v8; // ebx
  signed int v9; // eax
  __int16 OutBuffer; // [rsp+90h] [rbp+18h] BYREF
  DWORD BytesReturned; // [rsp+98h] [rbp+20h] BYREF

  OutBuffer = 0;
  BytesReturned = 0;
  v4 = -1;
  FileW = CreateFileW(L"\\\\.\\MountPointManager", 0xC0000000, 0, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v6 = 0;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147024890;
  }
  else
  {
    do
      ++v4;
    while ( Src[v4] );
    v6 = operator new[](2 * (unsigned int)(unsigned __int16)v4 + 4);
    if ( v6 )
    {
      *v6 = 2 * v4;
      memcpy_0(v6 + 1, Src, 2LL * (unsigned __int16)v4);
      if ( (_WORD)v4 )
      {
        if ( v6[(unsigned __int16)v4] == 92 )
        {
          v6[(unsigned __int16)v4] = 0;
          *v6 -= 2;
        }
        v6[2] = 63;
      }
      if ( DeviceIoControl(FileW, 0x6DC010u, v6, 2 * (unsigned __int16)v4 + 4, &OutBuffer, 2u, &BytesReturned, 0) )
      {
        if ( HIBYTE(OutBuffer) )
        {
          v8 = 0;
          *a2 = HIBYTE(OutBuffer);
        }
        else
        {
          *a2 = 0;
          v8 = 1;
        }
      }
      else
      {
        v9 = GetLastError();
        v8 = v9;
        if ( v9 > 0 )
          v8 = (unsigned __int16)v9 | 0x80070000;
      }
    }
    else
    {
      v8 = -2147024882;
    }
    CloseHandle(FileW);
  }
  operator delete[](v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180012130  mov     rax, rsp
0x180012133  mov     [rax+8], rbx
0x180012137  push    rbp
0x180012138  push    rsi
0x180012139  push    rdi
0x18001213a  push    r12
0x18001213c  push    r13
0x18001213e  push    r14
0x180012140  push    r15
0x180012142  sub     rsp, 40h
0x180012146  xor     r13d, r13d
0x180012149  mov     rsi, rdx
0x18001214c  mov     [rax-48h], r13
0x180012150  mov     r14, rcx
0x180012153  mov     dword ptr [rax-50h], 80h
0x18001215a  lea     rcx, aMountpointmana; "\\\\.\\MountPointManager"
0x180012161  xor     r9d, r9d; lpSecurityAttributes
0x180012164  mov     dword ptr [rax-58h], 3
0x18001216b  xor     r8d, r8d; dwShareMode
0x18001216e  mov     [rax+18h], r13w
0x180012173  mov     edx, 0C0000000h; dwDesiredAccess
0x180012178  mov     [rax+20h], r13d
0x18001217c  call    cs:__imp_CreateFileW
0x180012182  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012186  mov     r15, rax
0x180012189  cmp     rax, rbx
0x18001218c  jnz     short loc_1800121B5
0x18001218e  mov     edi, r13d
0x180012191  call    cs:__imp_GetLastError
0x180012197  mov     ebx, eax
0x180012199  test    eax, eax
0x18001219b  jle     short loc_1800121A6
0x18001219d  movzx   ebx, ax
0x1800121a0  or      ebx, 80070000h
0x1800121a6  test    ebx, ebx
0x1800121a8  mov     eax, 80070006h
0x1800121ad  cmovns  ebx, eax
0x1800121b0  jmp     loc_18001229B
0x1800121b5  inc     rbx
0x1800121b8  cmp     [r14+rbx*2], r13w
0x1800121bd  jnz     short loc_1800121B5
0x1800121bf  movzx   ebp, bx
0x1800121c2  lea     r12d, ds:4[rbp*2]
0x1800121ca  mov     ecx, r12d; unsigned __int64
0x1800121cd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800121d2  mov     rdi, rax
0x1800121d5  test    rax, rax
0x1800121d8  jnz     short loc_1800121E4
0x1800121da  mov     ebx, 8007000Eh
0x1800121df  jmp     loc_180012292
0x1800121e4  movzx   eax, bx
0x1800121e7  movzx   r8d, bx
0x1800121eb  add     ax, ax
0x1800121ee  lea     rcx, [rdi+2]; void *
0x1800121f2  add     r8, r8; Size
0x1800121f5  mov     [rdi], ax
0x1800121f8  mov     rdx, r14; Src
0x1800121fb  call    memcpy_0
0x180012200  test    bx, bx
0x180012203  jz      short loc_18001221F
0x180012205  cmp     word ptr [rdi+rbp*2], 5Ch ; '\'
0x18001220a  jnz     short loc_180012219
0x18001220c  mov     eax, 0FFFEh
0x180012211  mov     [rdi+rbp*2], r13w
0x180012216  add     [rdi], ax
0x180012219  mov     word ptr [rdi+4], 3Fh ; '?'
0x18001221f  mov     [rsp+78h+lpOverlapped], r13; lpOverlapped
0x180012224  lea     rax, [rsp+78h+BytesReturned]
0x18001222c  mov     [rsp+78h+lpBytesReturned], rax; lpBytesReturned
0x180012231  mov     r9d, r12d; nInBufferSize
0x180012234  lea     rax, [rsp+78h+OutBuffer]
0x18001223c  mov     [rsp+78h+nOutBufferSize], 2; nOutBufferSize
0x180012244  mov     r8, rdi; lpInBuffer
0x180012247  mov     [rsp+78h+lpOutBuffer], rax; lpOutBuffer
0x18001224c  mov     edx, 6DC010h; dwIoControlCode
0x180012251  mov     rcx, r15; hDevice
0x180012254  call    cs:__imp_DeviceIoControl
0x18001225a  test    eax, eax
0x18001225c  jnz     short loc_180012275
0x18001225e  call    cs:__imp_GetLastError
0x180012264  mov     ebx, eax
0x180012266  test    eax, eax
0x180012268  jle     short loc_180012292
0x18001226a  movzx   ebx, ax
0x18001226d  or      ebx, 80070000h
0x180012273  jmp     short loc_180012292
0x180012275  movzx   eax, [rsp+78h+arg_11]
0x18001227d  test    al, al
0x18001227f  jz      short loc_180012289
0x180012281  mov     ebx, r13d
0x180012284  mov     [rsi], ax
0x180012287  jmp     short loc_180012292
0x180012289  mov     [rsi], r13w
0x18001228d  mov     ebx, 1
0x180012292  mov     rcx, r15; hObject
0x180012295  call    cs:__imp_CloseHandle
0x18001229b  mov     rcx, rdi
0x18001229e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800122a4  mov     eax, ebx
0x1800122a6  mov     rbx, [rsp+78h+arg_0]
0x1800122ae  add     rsp, 40h
0x1800122b2  pop     r15
0x1800122b4  pop     r14
0x1800122b6  pop     r13
0x1800122b8  pop     r12
0x1800122ba  pop     rdi
0x1800122bb  pop     rsi
0x1800122bc  pop     rbp
0x1800122bd  retn
```
