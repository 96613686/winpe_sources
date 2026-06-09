# CUsbHub::Initialize(void)

- ea: `0x18000b78c`
- end: `0x18000b966`
- name: `?Initialize@CUsbHub@@AEAAXXZ`
- size: `474`
- prototype: `void __fastcall(CUsbHub *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path`

## callers

- `0x180005314`

## callees

- `0x180002410`
- `0x180002e6e`
- `0x180003fec`
- `0x180008020`
- `0x18000af94`
- `0x18000b78c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b82a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b88b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b8f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b8ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b82a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b88b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b8f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b8ff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b81a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b81a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000b881`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000b8eb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000b881`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000b8eb`

## pseudocode

```c
void __fastcall CUsbHub::Initialize(CUsbHub *this)
{
  const WCHAR *v2; // rcx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  DWORD v5; // eax
  DWORD v6; // eax
  int InBuffer; // [rsp+40h] [rbp-19h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-15h] BYREF
  const WCHAR **v9; // [rsp+48h] [rbp-11h] BYREF
  _BYTE OutBuffer[4]; // [rsp+50h] [rbp-9h] BYREF
  __int128 v11; // [rsp+54h] [rbp-5h]
  __int128 v12; // [rsp+64h] [rbp+Bh]
  __int128 v13; // [rsp+74h] [rbp+1Bh]
  __int128 v14; // [rsp+84h] [rbp+2Bh]
  __int64 v15; // [rsp+94h] [rbp+3Bh]

  BytesReturned = 0;
  InBuffer = 0;
  memset_0(OutBuffer, 0, 0x4Cu);
  v9 = 0;
  CDevNode::GetSymbolicLink(*(CDevNode **)this, (struct _bstr_t *)&v9);
  if ( v9 )
    v2 = *v9;
  else
    v2 = 0;
  FileW = CreateFileW(v2, 0, 3u, 0, 3u, 0, 0);
  *((_QWORD *)this + 2) = FileW;
  if ( FileW == (HANDLE)-1LL && GetLastError() )
  {
    LastError = GetLastError();
    CException::ThrowException(LastError, 0, 0);
  }
  InBuffer = 0;
  if ( !DeviceIoControl(*((HANDLE *)this + 2), 0x220450u, &InBuffer, 4u, &InBuffer, 4u, &BytesReturned, 0)
    && GetLastError() )
  {
    v5 = GetLastError();
    CException::ThrowException(v5, 0, 0);
  }
  *((_DWORD *)this + 24) = InBuffer;
  memset_0(OutBuffer, 0, 0x4Cu);
  if ( !DeviceIoControl(*((HANDLE *)this + 2), 0x220408u, OutBuffer, 0x4Cu, OutBuffer, 0x4Cu, &BytesReturned, 0)
    && GetLastError() )
  {
    v6 = GetLastError();
    CException::ThrowException(v6, 0, 0);
  }
  *(_OWORD *)((char *)this + 24) = v11;
  *(_OWORD *)((char *)this + 40) = v12;
  *(_OWORD *)((char *)this + 56) = v13;
  *(_OWORD *)((char *)this + 72) = v14;
  *((_QWORD *)this + 11) = v15;
  _bstr_t::_Free((_bstr_t *)&v9);
}

```

## disassembly

```asm
0x18000b78c  mov     [rsp-8+arg_8], rbx
0x18000b791  mov     [rsp-8+arg_10], rsi
0x18000b796  push    rbp
0x18000b797  lea     rbp, [rsp-57h]
0x18000b79c  sub     rsp, 0B0h
0x18000b7a3  mov     rax, cs:__security_cookie
0x18000b7aa  xor     rax, rsp
0x18000b7ad  mov     [rbp+57h+var_10], rax
0x18000b7b1  mov     rbx, rcx
0x18000b7b4  mov     [rbp+57h+BytesReturned], 0
0x18000b7bb  mov     [rbp+57h+InBuffer], 0
0x18000b7c2  mov     esi, 4Ch ; 'L'
0x18000b7c7  mov     r8d, esi; Size
0x18000b7ca  xor     edx, edx; Val
0x18000b7cc  lea     rcx, [rbp+57h+OutBuffer]; void *
0x18000b7d0  call    memset_0
0x18000b7d5  mov     [rbp+57h+var_68], 0
0x18000b7dd  lea     rdx, [rbp+57h+var_68]; struct _bstr_t *
0x18000b7e1  mov     rcx, [rbx]; this
0x18000b7e4  call    ?GetSymbolicLink@CDevNode@@QEAAXAEAV_bstr_t@@@Z; CDevNode::GetSymbolicLink(_bstr_t &)
0x18000b7e9  mov     rax, [rbp+57h+var_68]
0x18000b7ed  test    rax, rax
0x18000b7f0  jz      short loc_18000B7F7
0x18000b7f2  mov     rcx, [rax]
0x18000b7f5  jmp     short loc_18000B7F9
0x18000b7f7  xor     ecx, ecx; lpFileName
0x18000b7f9  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18000b802  mov     [rsp+0B0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000b80a  mov     r8d, 3; dwShareMode
0x18000b810  mov     [rsp+0B0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000b815  xor     r9d, r9d; lpSecurityAttributes
0x18000b818  xor     edx, edx; dwDesiredAccess
0x18000b81a  call    cs:__imp_CreateFileW
0x18000b820  mov     [rbx+10h], rax
0x18000b824  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b828  jnz     short loc_18000B847
0x18000b82a  call    cs:__imp_GetLastError
0x18000b830  test    eax, eax
0x18000b832  jz      short loc_18000B847
0x18000b834  call    cs:__imp_GetLastError
0x18000b83a  mov     ecx, eax
0x18000b83c  xor     r8d, r8d
0x18000b83f  xor     edx, edx
0x18000b841  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000b847  mov     [rbp+57h+InBuffer], 0
0x18000b84e  mov     [rsp+0B0h+lpOverlapped], 0; lpOverlapped
0x18000b857  lea     rax, [rbp+57h+BytesReturned]
0x18000b85b  mov     [rsp+0B0h+hTemplateFile], rax; lpBytesReturned
0x18000b860  mov     r9d, 4; nInBufferSize
0x18000b866  mov     [rsp+0B0h+dwFlagsAndAttributes], r9d; nOutBufferSize
0x18000b86b  lea     rax, [rbp+57h+InBuffer]
0x18000b86f  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; lpOutBuffer
0x18000b874  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18000b878  mov     edx, 220450h; dwIoControlCode
0x18000b87d  mov     rcx, [rbx+10h]; hDevice
0x18000b881  call    cs:__imp_DeviceIoControl
0x18000b887  test    eax, eax
0x18000b889  jnz     short loc_18000B8A8
0x18000b88b  call    cs:__imp_GetLastError
0x18000b891  test    eax, eax
0x18000b893  jz      short loc_18000B8A8
0x18000b895  call    cs:__imp_GetLastError
0x18000b89b  mov     ecx, eax
0x18000b89d  xor     r8d, r8d
0x18000b8a0  xor     edx, edx
0x18000b8a2  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000b8a8  mov     eax, [rbp+57h+InBuffer]
0x18000b8ab  mov     [rbx+60h], eax
0x18000b8ae  mov     r8, rsi; Size
0x18000b8b1  xor     edx, edx; Val
0x18000b8b3  lea     rcx, [rbp+57h+OutBuffer]; void *
0x18000b8b7  call    memset_0
0x18000b8bc  mov     [rsp+0B0h+lpOverlapped], 0; lpOverlapped
0x18000b8c5  lea     rax, [rbp+57h+BytesReturned]
0x18000b8c9  mov     [rsp+0B0h+hTemplateFile], rax; lpBytesReturned
0x18000b8ce  mov     [rsp+0B0h+dwFlagsAndAttributes], esi; nOutBufferSize
0x18000b8d2  lea     rax, [rbp+57h+OutBuffer]
0x18000b8d6  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; lpOutBuffer
0x18000b8db  mov     r9d, esi; nInBufferSize
0x18000b8de  lea     r8, [rbp+57h+OutBuffer]; lpInBuffer
0x18000b8e2  mov     edx, 220408h; dwIoControlCode
0x18000b8e7  mov     rcx, [rbx+10h]; hDevice
0x18000b8eb  call    cs:__imp_DeviceIoControl
0x18000b8f1  test    eax, eax
0x18000b8f3  jnz     short loc_18000B912
0x18000b8f5  call    cs:__imp_GetLastError
0x18000b8fb  test    eax, eax
0x18000b8fd  jz      short loc_18000B912
0x18000b8ff  call    cs:__imp_GetLastError
0x18000b905  mov     ecx, eax
0x18000b907  xor     r8d, r8d
0x18000b90a  xor     edx, edx
0x18000b90c  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000b912  movups  xmm0, [rbp+57h+var_5C]
0x18000b916  movups  xmmword ptr [rbx+18h], xmm0
0x18000b91a  movups  xmm1, [rbp+57h+var_4C]
0x18000b91e  movups  xmmword ptr [rbx+28h], xmm1
0x18000b922  movups  xmm0, [rbp+57h+var_3C]
0x18000b926  movups  xmmword ptr [rbx+38h], xmm0
0x18000b92a  movups  xmm1, [rbp+57h+var_2C]
0x18000b92e  movups  xmmword ptr [rbx+48h], xmm1
0x18000b932  movsd   xmm0, [rbp+57h+var_1C]
0x18000b937  movsd   qword ptr [rbx+58h], xmm0
0x18000b93c  lea     rcx, [rbp+57h+var_68]; this
0x18000b940  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b945  mov     rcx, [rbp+57h+var_10]
0x18000b949  xor     rcx, rsp; StackCookie
0x18000b94c  call    __security_check_cookie
0x18000b951  lea     r11, [rsp+0B0h+var_s0]
0x18000b959  mov     rbx, [r11+18h]
0x18000b95d  mov     rsi, [r11+20h]
0x18000b961  mov     rsp, r11
0x18000b964  pop     rbp
0x18000b965  retn
```
