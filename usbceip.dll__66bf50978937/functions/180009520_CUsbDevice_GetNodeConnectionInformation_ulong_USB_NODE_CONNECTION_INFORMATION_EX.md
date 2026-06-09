# CUsbDevice::GetNodeConnectionInformation(ulong,_USB_NODE_CONNECTION_INFORMATION_EX *)

- ea: `0x180009520`
- end: `0x18000962a`
- name: `?GetNodeConnectionInformation@CUsbDevice@@QEAAXKPEAU_USB_NODE_CONNECTION_INFORMATION_EX@@@Z`
- size: `266`
- prototype: `void __fastcall(CDevNode **this, ULONG, struct _USB_NODE_CONNECTION_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path`

## callers

- `0x180009b24`

## callees

- `0x180003fec`
- `0x180008020`
- `0x180009520`
- `0x18000af94`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800095e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800095e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000959b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000959b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095fd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009582`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009582`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800095de`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800095de`

## pseudocode

```c
void __fastcall CUsbDevice::GetNodeConnectionInformation(
        CDevNode **this,
        ULONG a2,
        struct _USB_NODE_CONNECTION_INFORMATION_EX *a3)
{
  const WCHAR *v5; // rcx
  HANDLE FileW; // rdi
  DWORD LastError; // eax
  BOOL v8; // ebx
  DWORD v9; // eax
  DWORD BytesReturned; // [rsp+50h] [rbp+8h] BYREF
  const WCHAR **v11; // [rsp+68h] [rbp+20h] BYREF

  BytesReturned = 0;
  v11 = 0;
  CDevNode::GetSymbolicLink(*this, (struct _bstr_t *)&v11);
  if ( v11 )
    v5 = *v11;
  else
    v5 = 0;
  FileW = CreateFileW(v5, 0, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL && GetLastError() )
  {
    LastError = GetLastError();
    CException::ThrowException(LastError, 0, 0);
  }
  a3->ConnectionIndex = a2;
  v8 = DeviceIoControl(FileW, 0x220448u, a3, 0x23u, a3, 0x23u, &BytesReturned, 0);
  CloseHandle(FileW);
  if ( !v8 && GetLastError() )
  {
    v9 = GetLastError();
    CException::ThrowException(v9, 0, 0);
  }
  _bstr_t::_Free((_bstr_t *)&v11);
}

```

## disassembly

```asm
0x180009520  mov     rax, rsp
0x180009523  mov     [rax+10h], rbx
0x180009527  mov     [rax+18h], rsi
0x18000952b  push    rdi
0x18000952c  sub     rsp, 40h
0x180009530  mov     rbx, r8
0x180009533  mov     esi, edx
0x180009535  mov     dword ptr [rax+8], 0
0x18000953c  mov     qword ptr [rax+20h], 0
0x180009544  lea     rdx, [rax+20h]; struct _bstr_t *
0x180009548  mov     rcx, [rcx]; this
0x18000954b  call    ?GetSymbolicLink@CDevNode@@QEAAXAEAV_bstr_t@@@Z; CDevNode::GetSymbolicLink(_bstr_t &)
0x180009550  mov     rax, [rsp+48h+arg_18]
0x180009555  test    rax, rax
0x180009558  jz      short loc_18000955F
0x18000955a  mov     rcx, [rax]
0x18000955d  jmp     short loc_180009561
0x18000955f  xor     ecx, ecx; lpFileName
0x180009561  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000956a  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180009572  mov     r8d, 3; dwShareMode
0x180009578  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000957d  xor     r9d, r9d; lpSecurityAttributes
0x180009580  xor     edx, edx; dwDesiredAccess
0x180009582  call    cs:__imp_CreateFileW
0x180009588  mov     rdi, rax
0x18000958b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000958f  jnz     short loc_1800095AE
0x180009591  call    cs:__imp_GetLastError
0x180009597  test    eax, eax
0x180009599  jz      short loc_1800095AE
0x18000959b  call    cs:__imp_GetLastError
0x1800095a1  mov     ecx, eax
0x1800095a3  xor     r8d, r8d
0x1800095a6  xor     edx, edx
0x1800095a8  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x1800095ae  mov     [rbx], esi
0x1800095b0  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1800095b9  lea     rax, [rsp+48h+BytesReturned]
0x1800095be  mov     [rsp+48h+hTemplateFile], rax; lpBytesReturned
0x1800095c3  mov     r9d, 23h ; '#'; nInBufferSize
0x1800095c9  mov     [rsp+48h+dwFlagsAndAttributes], r9d; nOutBufferSize
0x1800095ce  mov     qword ptr [rsp+48h+dwCreationDisposition], rbx; lpOutBuffer
0x1800095d3  mov     r8, rbx; lpInBuffer
0x1800095d6  mov     edx, 220448h; dwIoControlCode
0x1800095db  mov     rcx, rdi; hDevice
0x1800095de  call    cs:__imp_DeviceIoControl
0x1800095e4  mov     ebx, eax
0x1800095e6  mov     rcx, rdi; hObject
0x1800095e9  call    cs:__imp_CloseHandle
0x1800095ef  test    ebx, ebx
0x1800095f1  jnz     short loc_180009610
0x1800095f3  call    cs:__imp_GetLastError
0x1800095f9  test    eax, eax
0x1800095fb  jz      short loc_180009610
0x1800095fd  call    cs:__imp_GetLastError
0x180009603  mov     ecx, eax
0x180009605  xor     r8d, r8d
0x180009608  xor     edx, edx
0x18000960a  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x180009610  lea     rcx, [rsp+48h+arg_18]; this
0x180009615  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000961a  mov     rbx, [rsp+48h+arg_8]
0x18000961f  mov     rsi, [rsp+48h+arg_10]
0x180009624  add     rsp, 40h
0x180009628  pop     rdi
0x180009629  retn
```
