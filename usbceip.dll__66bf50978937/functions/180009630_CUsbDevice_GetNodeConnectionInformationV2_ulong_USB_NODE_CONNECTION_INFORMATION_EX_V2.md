# CUsbDevice::GetNodeConnectionInformationV2(ulong,_USB_NODE_CONNECTION_INFORMATION_EX_V2 *)

- ea: `0x180009630`
- end: `0x180009742`
- name: `?GetNodeConnectionInformationV2@CUsbDevice@@QEAAXKPEAU_USB_NODE_CONNECTION_INFORMATION_EX_V2@@@Z`
- size: `274`
- prototype: `void __fastcall(CDevNode **this, int, struct _USB_NODE_CONNECTION_INFORMATION_EX_V2 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path`

## callers

- `0x180009b24`

## callees

- `0x180003fec`
- `0x180008020`
- `0x180009630`
- `0x18000af94`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009701`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000970b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000970b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009715`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009692`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009692`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800096f6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800096f6`

## pseudocode

```c
void __fastcall CUsbDevice::GetNodeConnectionInformationV2(
        CDevNode **this,
        int a2,
        struct _USB_NODE_CONNECTION_INFORMATION_EX_V2 *a3)
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
  *((_DWORD *)a3 + 1) = 16;
  *(_DWORD *)a3 = a2;
  *((_DWORD *)a3 + 2) |= 7u;
  v8 = DeviceIoControl(FileW, 0x22045Cu, a3, 0x10u, a3, 0x10u, &BytesReturned, 0);
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
0x180009630  mov     rax, rsp
0x180009633  mov     [rax+10h], rbx
0x180009637  mov     [rax+18h], rsi
0x18000963b  push    rdi
0x18000963c  sub     rsp, 40h
0x180009640  mov     rbx, r8
0x180009643  mov     esi, edx
0x180009645  mov     dword ptr [rax+8], 0
0x18000964c  mov     qword ptr [rax+20h], 0
0x180009654  lea     rdx, [rax+20h]; struct _bstr_t *
0x180009658  mov     rcx, [rcx]; this
0x18000965b  call    ?GetSymbolicLink@CDevNode@@QEAAXAEAV_bstr_t@@@Z; CDevNode::GetSymbolicLink(_bstr_t &)
0x180009660  mov     rax, [rsp+48h+arg_18]
0x180009665  test    rax, rax
0x180009668  jz      short loc_18000966F
0x18000966a  mov     rcx, [rax]
0x18000966d  jmp     short loc_180009671
0x18000966f  xor     ecx, ecx; lpFileName
0x180009671  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000967a  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180009682  mov     r8d, 3; dwShareMode
0x180009688  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000968d  xor     r9d, r9d; lpSecurityAttributes
0x180009690  xor     edx, edx; dwDesiredAccess
0x180009692  call    cs:__imp_CreateFileW
0x180009698  mov     rdi, rax
0x18000969b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000969f  jnz     short loc_1800096BE
0x1800096a1  call    cs:__imp_GetLastError
0x1800096a7  test    eax, eax
0x1800096a9  jz      short loc_1800096BE
0x1800096ab  call    cs:__imp_GetLastError
0x1800096b1  mov     ecx, eax
0x1800096b3  xor     r8d, r8d
0x1800096b6  xor     edx, edx
0x1800096b8  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x1800096be  mov     r9d, 10h; nInBufferSize
0x1800096c4  mov     [rbx+4], r9d
0x1800096c8  mov     [rbx], esi
0x1800096ca  or      dword ptr [rbx+8], 7
0x1800096ce  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1800096d7  lea     rax, [rsp+48h+BytesReturned]
0x1800096dc  mov     [rsp+48h+hTemplateFile], rax; lpBytesReturned
0x1800096e1  mov     [rsp+48h+dwFlagsAndAttributes], r9d; nOutBufferSize
0x1800096e6  mov     qword ptr [rsp+48h+dwCreationDisposition], rbx; lpOutBuffer
0x1800096eb  mov     r8, rbx; lpInBuffer
0x1800096ee  mov     edx, 22045Ch; dwIoControlCode
0x1800096f3  mov     rcx, rdi; hDevice
0x1800096f6  call    cs:__imp_DeviceIoControl
0x1800096fc  mov     ebx, eax
0x1800096fe  mov     rcx, rdi; hObject
0x180009701  call    cs:__imp_CloseHandle
0x180009707  test    ebx, ebx
0x180009709  jnz     short loc_180009728
0x18000970b  call    cs:__imp_GetLastError
0x180009711  test    eax, eax
0x180009713  jz      short loc_180009728
0x180009715  call    cs:__imp_GetLastError
0x18000971b  mov     ecx, eax
0x18000971d  xor     r8d, r8d
0x180009720  xor     edx, edx
0x180009722  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x180009728  lea     rcx, [rsp+48h+arg_18]; this
0x18000972d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180009732  mov     rbx, [rsp+48h+arg_8]
0x180009737  mov     rsi, [rsp+48h+arg_10]
0x18000973c  add     rsp, 40h
0x180009740  pop     rdi
0x180009741  retn
```
