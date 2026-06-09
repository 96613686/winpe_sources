# CUwfConfiguration::commitRegKeyValue(ushort const *,ushort const *)

- ea: `0x18000a8c8`
- end: `0x18000aa71`
- name: `?commitRegKeyValue@CUwfConfiguration@@AEAAJPEBG0@Z`
- size: `425`
- prototype: `__int64 __fastcall(CUwfConfiguration *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800079a0`
- `0x18000a824`
- `0x18000c030`
- `0x18000c140`
- `0x18000c4f0`
- `0x18000d0e0`

## callees

- `0x18000a8c8`
- `0x18001afe2`
- `0x18001b020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa41`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000a9f0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000a9f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a9b8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a9b8`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::commitRegKeyValue(
        CUwfConfiguration *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v5; // r10
  _WORD *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r9
  _WORD *v9; // rcx
  __int64 v10; // rdx
  char *v11; // rax
  char *v12; // rcx
  char *FileW; // rbx
  _BYTE InBuffer[2048]; // [rsp+40h] [rbp-A18h] BYREF
  char v16; // [rsp+840h] [rbp-218h] BYREF

  memset_0(InBuffer, 0, 0xA00u);
  v5 = 2147483646;
  v6 = InBuffer;
  v7 = 2147483646;
  v8 = 1024;
  do
  {
    if ( !v7 )
      break;
    if ( !*a2 )
      break;
    *v6++ = *a2++;
    --v7;
    --v8;
  }
  while ( v8 );
  v9 = v6 - 1;
  if ( v8 )
    v9 = v6;
  *v9 = 0;
  if ( !v8 )
    return 2147500037LL;
  v10 = 256;
  v11 = &v16;
  do
  {
    if ( !v5 )
      break;
    if ( !*a3 )
      break;
    *(_WORD *)v11 = *a3++;
    v11 += 2;
    --v5;
    --v10;
  }
  while ( v10 );
  v12 = v11 - 2;
  if ( v10 )
    v12 = v11;
  *(_WORD *)v12 = 0;
  if ( !v10 )
    return 2147500037LL;
  FileW = (char *)CreateFileW(L"\\\\.\\UwfregControl", 0xC0000000, 3u, 0, 3u, 0x80u, 0);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( DeviceIoControl(FileW, 0x2289E4u, InBuffer, 0xA00u, 0, 0, 0, 0) )
    {
      CloseHandle(FileW);
      return 0;
    }
    GetLastError();
    goto LABEL_24;
  }
  if ( GetLastError() != 2 )
  {
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return 2147500037LL;
LABEL_24:
    CloseHandle(FileW);
    return 2147500037LL;
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return 1;
}

```

## disassembly

```asm
0x18000a8c8  mov     [rsp+arg_0], rbx
0x18000a8cd  mov     [rsp+arg_8], rsi
0x18000a8d2  push    rdi
0x18000a8d3  sub     rsp, 0A50h
0x18000a8da  mov     rax, cs:__security_cookie
0x18000a8e1  xor     rax, rsp
0x18000a8e4  mov     [rsp+0A58h+var_18], rax
0x18000a8ec  mov     rdi, r8
0x18000a8ef  lea     rcx, [rsp+0A58h+InBuffer]; void *
0x18000a8f4  mov     rbx, rdx
0x18000a8f7  mov     r8d, 0A00h; Size
0x18000a8fd  xor     edx, edx; Val
0x18000a8ff  call    memset_0
0x18000a904  mov     r10d, 7FFFFFFEh
0x18000a90a  lea     rax, [rsp+0A58h+InBuffer]
0x18000a90f  mov     ecx, r10d
0x18000a912  mov     r9d, 400h
0x18000a918  xor     esi, esi
0x18000a91a  test    rcx, rcx
0x18000a91d  jz      short loc_18000A93B
0x18000a91f  movzx   edx, word ptr [rbx]
0x18000a922  test    dx, dx
0x18000a925  jz      short loc_18000A93B
0x18000a927  mov     [rax], dx
0x18000a92a  add     rbx, 2
0x18000a92e  add     rax, 2
0x18000a932  dec     rcx
0x18000a935  sub     r9, 1
0x18000a939  jnz     short loc_18000A91A
0x18000a93b  test    r9, r9
0x18000a93e  lea     rcx, [rax-2]
0x18000a942  cmovnz  rcx, rax
0x18000a946  mov     [rcx], si
0x18000a949  jz      loc_18000AA47
0x18000a94f  mov     edx, 100h
0x18000a954  lea     rax, [rsp+0A58h+var_218]
0x18000a95c  test    r10, r10
0x18000a95f  jz      short loc_18000A97D
0x18000a961  movzx   ecx, word ptr [rdi]
0x18000a964  test    cx, cx
0x18000a967  jz      short loc_18000A97D
0x18000a969  mov     [rax], cx
0x18000a96c  add     rdi, 2
0x18000a970  add     rax, 2
0x18000a974  dec     r10
0x18000a977  sub     rdx, 1
0x18000a97b  jnz     short loc_18000A95C
0x18000a97d  test    rdx, rdx
0x18000a980  lea     rcx, [rax-2]
0x18000a984  cmovnz  rcx, rax
0x18000a988  mov     [rcx], si
0x18000a98b  jz      loc_18000AA47
0x18000a991  mov     [rsp+0A58h+hTemplateFile], rsi; hTemplateFile
0x18000a996  lea     rcx, FileName; "\\\\.\\UwfregControl"
0x18000a99d  mov     r8d, 3; dwShareMode
0x18000a9a3  mov     [rsp+0A58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000a9ab  xor     r9d, r9d; lpSecurityAttributes
0x18000a9ae  mov     [rsp+0A58h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000a9b3  mov     edx, 0C0000000h; dwDesiredAccess
0x18000a9b8  call    cs:__imp_CreateFileW
0x18000a9be  mov     rbx, rax
0x18000a9c1  dec     rax
0x18000a9c4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a9c8  ja      short loc_18000AA0F
0x18000a9ca  mov     [rsp+0A58h+lpOverlapped], rsi; lpOverlapped
0x18000a9cf  lea     r8, [rsp+0A58h+InBuffer]; lpInBuffer
0x18000a9d4  mov     [rsp+0A58h+hTemplateFile], rsi; lpBytesReturned
0x18000a9d9  mov     r9d, 0A00h; nInBufferSize
0x18000a9df  mov     [rsp+0A58h+dwFlagsAndAttributes], esi; nOutBufferSize
0x18000a9e3  mov     edx, 2289E4h; dwIoControlCode
0x18000a9e8  mov     rcx, rbx; hDevice
0x18000a9eb  mov     qword ptr [rsp+0A58h+dwCreationDisposition], rsi; lpOutBuffer
0x18000a9f0  call    cs:__imp_DeviceIoControl
0x18000a9f6  test    eax, eax
0x18000a9f8  jnz     short loc_18000AA02
0x18000a9fa  call    cs:__imp_GetLastError
0x18000aa00  jmp     short loc_18000AA3E
0x18000aa02  mov     rcx, rbx; hObject
0x18000aa05  call    cs:__imp_CloseHandle
0x18000aa0b  xor     eax, eax
0x18000aa0d  jmp     short loc_18000AA4C
0x18000aa0f  call    cs:__imp_GetLastError
0x18000aa15  cmp     eax, 2
0x18000aa18  jnz     short loc_18000AA34
0x18000aa1a  lea     rcx, [rbx-1]
0x18000aa1e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000aa22  ja      short loc_18000AA2D
0x18000aa24  mov     rcx, rbx; hObject
0x18000aa27  call    cs:__imp_CloseHandle
0x18000aa2d  mov     eax, 1
0x18000aa32  jmp     short loc_18000AA4C
0x18000aa34  lea     rax, [rbx-1]
0x18000aa38  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000aa3c  ja      short loc_18000AA47
0x18000aa3e  mov     rcx, rbx; hObject
0x18000aa41  call    cs:__imp_CloseHandle
0x18000aa47  mov     eax, 80004005h
0x18000aa4c  mov     rcx, [rsp+0A58h+var_18]
0x18000aa54  xor     rcx, rsp; StackCookie
0x18000aa57  call    __security_check_cookie
0x18000aa5c  lea     r11, [rsp+0A58h+var_8]
0x18000aa64  mov     rbx, [r11+10h]
0x18000aa68  mov     rsi, [r11+18h]
0x18000aa6c  mov     rsp, r11
0x18000aa6f  pop     rdi
0x18000aa70  retn
```
