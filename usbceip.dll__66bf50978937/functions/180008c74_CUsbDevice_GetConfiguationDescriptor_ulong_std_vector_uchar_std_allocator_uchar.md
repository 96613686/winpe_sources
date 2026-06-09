# CUsbDevice::GetConfiguationDescriptor(ulong,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x180008c74`
- end: `0x180008f41`
- name: `?GetConfiguationDescriptor@CUsbDevice@@QEAAEKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `717`
- prototype: `bool __fastcall(CDevNode **, int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x1800097ec`

## callees

- `0x180002e6e`
- `0x180003fec`
- `0x180008020`
- `0x1800080c8`
- `0x180008c74`
- `0x18000af94`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008da3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008da3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ed7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180008cd5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180008cd5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008d96`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008eb3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008d96`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008eb3`

## pseudocode

```c
bool __fastcall CUsbDevice::GetConfiguationDescriptor(CDevNode **a1, int a2, __int64 a3)
{
  const WCHAR *v5; // rcx
  HANDLE FileW; // r12
  DWORD LastError; // eax
  unsigned __int16 *v8; // rdx
  __int64 v9; // rsi
  unsigned __int64 v10; // rcx
  char *v11; // rax
  unsigned __int64 v12; // rbx
  unsigned __int16 *v13; // rbx
  BOOL v14; // r14d
  __int64 v15; // rcx
  unsigned __int16 v16; // r13
  unsigned __int16 v17; // r15
  char *v18; // r14
  unsigned __int16 *v19; // rcx
  char *v20; // rax
  size_t v21; // rbx
  unsigned __int16 *v22; // rbx
  __int64 v23; // rcx
  DWORD BytesReturned; // [rsp+90h] [rbp+8h] BYREF
  int v26; // [rsp+98h] [rbp+10h]
  const WCHAR **v27; // [rsp+A8h] [rbp+20h] BYREF

  v26 = a2;
  BytesReturned = 0;
  v27 = 0;
  CDevNode::GetSymbolicLink(*a1, (struct _bstr_t *)&v27);
  if ( v27 )
    v5 = *v27;
  else
    v5 = 0;
  FileW = CreateFileW(v5, 0, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL && GetLastError() )
  {
    LastError = GetLastError();
    CException::ThrowException(LastError, 0, 0);
  }
  v8 = *(unsigned __int16 **)a3;
  v9 = *(_QWORD *)(a3 + 8);
  v10 = v9 - *(_QWORD *)a3;
  if ( v10 <= 0x15 )
  {
    if ( v10 >= 0x15 )
      goto LABEL_14;
    if ( *(_QWORD *)(a3 + 16) - (_QWORD)v8 < 0x15u )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a3, 21);
      goto LABEL_14;
    }
    v12 = 21 - v10;
    memset_0(*(void **)(a3 + 8), 0, 21 - v10);
    v11 = (char *)(v12 + v9);
  }
  else
  {
    v11 = (char *)v8 + 21;
  }
  *(_QWORD *)(a3 + 8) = v11;
LABEL_14:
  v13 = *(unsigned __int16 **)a3;
  *(_DWORD *)v13 = a2;
  v13[3] = 512;
  v13[5] = 9;
  v14 = DeviceIoControl(FileW, 0x220410u, v13, 0x15u, v13, 0x15u, &BytesReturned, 0);
  if ( !v14 )
  {
    if ( GetLastError() == 31 )
      goto LABEL_37;
    if ( GetLastError() )
    {
      v15 = GetLastError();
      CException::ThrowException(v15, 0, 0);
    }
  }
  if ( BytesReturned != 21 )
    CException::ThrowException(2147500037LL, 1, 0);
  v16 = v13[7];
  v17 = v16 + 12;
  v18 = *(char **)(a3 + 8);
  v19 = *(unsigned __int16 **)a3;
  if ( *(char **)a3 != v18 )
  {
    *(_QWORD *)(a3 + 8) = v19;
    v18 = (char *)v19;
  }
  if ( v17 < 0x15u )
    CException::ThrowException(2147500037LL, 1, 0);
  if ( v17 < (unsigned __int64)(v18 - (char *)v19) )
  {
    v20 = (char *)v19 + v17;
LABEL_30:
    *(_QWORD *)(a3 + 8) = v20;
    goto LABEL_31;
  }
  if ( v17 > (unsigned __int64)(v18 - (char *)v19) )
  {
    if ( (unsigned __int64)v17 <= *(_QWORD *)(a3 + 16) - (_QWORD)v19 )
    {
      v21 = v17 - (v18 - (char *)v19);
      memset_0(v18, 0, v21);
      v20 = &v18[v21];
      goto LABEL_30;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a3, v17);
  }
LABEL_31:
  v22 = *(unsigned __int16 **)a3;
  *(_DWORD *)v22 = v26;
  v22[3] = 512;
  v22[5] = v16;
  v14 = DeviceIoControl(FileW, 0x220410u, v22, v17, v22, v17, &BytesReturned, 0);
  if ( !v14 )
  {
    if ( GetLastError() == 31 )
      goto LABEL_37;
    if ( GetLastError() )
    {
      v23 = GetLastError();
      CException::ThrowException(v23, 0, 0);
    }
  }
  if ( BytesReturned != v17 || v22[7] > (unsigned __int64)v17 - 12 )
    CException::ThrowException(2147500037LL, 1, 0);
LABEL_37:
  CloseHandle(FileW);
  _bstr_t::_Free((_bstr_t *)&v27);
  return v14;
}

```

## disassembly

```asm
0x180008c74  mov     rax, rsp
0x180008c77  mov     [rax+10h], edx
0x180008c7a  push    rbx
0x180008c7b  push    rsi
0x180008c7c  push    rdi
0x180008c7d  push    r12
0x180008c7f  push    r13
0x180008c81  push    r14
0x180008c83  push    r15
0x180008c85  sub     rsp, 50h
0x180008c89  mov     rdi, r8
0x180008c8c  mov     r14d, edx
0x180008c8f  xor     r15d, r15d
0x180008c92  mov     [rax+8], r15d
0x180008c96  mov     [rax+20h], r15
0x180008c9a  lea     rdx, [rax+20h]; struct _bstr_t *
0x180008c9e  mov     rcx, [rcx]; this
0x180008ca1  call    ?GetSymbolicLink@CDevNode@@QEAAXAEAV_bstr_t@@@Z; CDevNode::GetSymbolicLink(_bstr_t &)
0x180008ca6  mov     rax, [rsp+88h+arg_18]
0x180008cae  test    rax, rax
0x180008cb1  jz      short loc_180008CB8
0x180008cb3  mov     rcx, [rax]
0x180008cb6  jmp     short loc_180008CBB
0x180008cb8  mov     rcx, r15; lpFileName
0x180008cbb  mov     [rsp+88h+hTemplateFile], r15; hTemplateFile
0x180008cc0  mov     [rsp+88h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x180008cc5  mov     r8d, 3; dwShareMode
0x180008ccb  mov     [rsp+88h+dwCreationDisposition], r8d; dwCreationDisposition
0x180008cd0  xor     r9d, r9d; lpSecurityAttributes
0x180008cd3  xor     edx, edx; dwDesiredAccess
0x180008cd5  call    cs:__imp_CreateFileW
0x180008cdb  mov     r12, rax
0x180008cde  mov     [rsp+88h+var_48], rax
0x180008ce3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008ce7  jnz     short loc_180008D06
0x180008ce9  call    cs:__imp_GetLastError
0x180008cef  test    eax, eax
0x180008cf1  jz      short loc_180008D06
0x180008cf3  call    cs:__imp_GetLastError
0x180008cf9  mov     ecx, eax
0x180008cfb  xor     r8d, r8d
0x180008cfe  xor     edx, edx
0x180008d00  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x180008d06  mov     rdx, [rdi]
0x180008d09  mov     rsi, [rdi+8]
0x180008d0d  mov     rcx, rsi
0x180008d10  sub     rcx, rdx
0x180008d13  mov     r13d, 15h
0x180008d19  cmp     rcx, r13
0x180008d1c  jbe     short loc_180008D24
0x180008d1e  lea     rax, [rdx+15h]
0x180008d22  jmp     short loc_180008D56
0x180008d24  jnb     short loc_180008D5A
0x180008d26  mov     rax, [rdi+10h]
0x180008d2a  sub     rax, rdx
0x180008d2d  cmp     rax, r13
0x180008d30  jnb     short loc_180008D3F
0x180008d32  mov     rdx, r13
0x180008d35  mov     rcx, rdi
0x180008d38  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180008d3d  jmp     short loc_180008D5A
0x180008d3f  mov     rbx, r13
0x180008d42  sub     rbx, rcx
0x180008d45  mov     r8, rbx; Size
0x180008d48  xor     edx, edx; Val
0x180008d4a  mov     rcx, rsi; void *
0x180008d4d  call    memset_0
0x180008d52  lea     rax, [rbx+rsi]
0x180008d56  mov     [rdi+8], rax
0x180008d5a  mov     rbx, [rdi]
0x180008d5d  mov     [rbx], r14d
0x180008d60  mov     word ptr [rbx+6], 200h
0x180008d66  mov     word ptr [rbx+0Ah], 9
0x180008d6c  mov     [rsp+88h+lpOverlapped], r15; lpOverlapped
0x180008d71  lea     rax, [rsp+88h+BytesReturned]
0x180008d79  mov     [rsp+88h+hTemplateFile], rax; lpBytesReturned
0x180008d7e  mov     [rsp+88h+dwFlagsAndAttributes], r13d; nOutBufferSize
0x180008d83  mov     qword ptr [rsp+88h+dwCreationDisposition], rbx; lpOutBuffer
0x180008d88  mov     r9d, r13d; nInBufferSize
0x180008d8b  mov     r8, rbx; lpInBuffer
0x180008d8e  mov     edx, 220410h; dwIoControlCode
0x180008d93  mov     rcx, r12; hDevice
0x180008d96  call    cs:__imp_DeviceIoControl
0x180008d9c  mov     r14d, eax
0x180008d9f  test    eax, eax
0x180008da1  jnz     short loc_180008DCF
0x180008da3  call    cs:__imp_GetLastError
0x180008da9  cmp     eax, 1Fh
0x180008dac  jnz     short loc_180008DB3
0x180008dae  jmp     loc_180008EFF
0x180008db3  call    cs:__imp_GetLastError
0x180008db9  test    eax, eax
0x180008dbb  jz      short loc_180008DCF
0x180008dbd  call    cs:__imp_GetLastError
0x180008dc3  mov     ecx, eax
0x180008dc5  xor     r8d, r8d
0x180008dc8  xor     edx, edx
0x180008dca  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x180008dcf  cmp     [rsp+88h+BytesReturned], r13d
0x180008dd7  jz      short loc_180008DEA
0x180008dd9  xor     r8d, r8d
0x180008ddc  lea     edx, [r8+1]
0x180008de0  mov     ecx, 80004005h
0x180008de5  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x180008dea  movzx   r13d, word ptr [rbx+0Eh]
0x180008def  lea     r15d, [r13+0Ch]
0x180008df3  mov     r14, [rdi+8]
0x180008df7  mov     rcx, [rdi]
0x180008dfa  cmp     rcx, r14
0x180008dfd  jz      short loc_180008E06
0x180008dff  mov     [rdi+8], rcx
0x180008e03  mov     r14, rcx
0x180008e06  mov     eax, 15h
0x180008e0b  cmp     r15w, ax
0x180008e0f  jnb     short loc_180008E21
0x180008e11  xor     r8d, r8d
0x180008e14  lea     edx, [rax-14h]
0x180008e17  mov     ecx, 80004005h
0x180008e1c  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x180008e21  movzx   esi, r15w
0x180008e25  mov     rdx, r14
0x180008e28  sub     rdx, rcx
0x180008e2b  cmp     rsi, rdx
0x180008e2e  jnb     short loc_180008E36
0x180008e30  lea     rax, [rsi+rcx]
0x180008e34  jmp     short loc_180008E68
0x180008e36  jbe     short loc_180008E6C
0x180008e38  mov     rax, [rdi+10h]
0x180008e3c  sub     rax, rcx
0x180008e3f  cmp     rsi, rax
0x180008e42  jbe     short loc_180008E51
0x180008e44  mov     rdx, rsi
0x180008e47  mov     rcx, rdi
0x180008e4a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180008e4f  jmp     short loc_180008E6C
0x180008e51  mov     rbx, rsi
0x180008e54  sub     rbx, rdx
0x180008e57  mov     r8, rbx; Size
0x180008e5a  xor     edx, edx; Val
0x180008e5c  mov     rcx, r14; void *
0x180008e5f  call    memset_0
0x180008e64  lea     rax, [rbx+r14]
0x180008e68  mov     [rdi+8], rax
0x180008e6c  mov     rbx, [rdi]
0x180008e6f  mov     eax, [rsp+88h+arg_8]
0x180008e76  mov     [rbx], eax
0x180008e78  mov     word ptr [rbx+6], 200h
0x180008e7e  mov     [rbx+0Ah], r13w
0x180008e83  movzx   edi, r15w
0x180008e87  xor     r15d, r15d
0x180008e8a  mov     [rsp+88h+lpOverlapped], r15; lpOverlapped
0x180008e8f  lea     rax, [rsp+88h+BytesReturned]
0x180008e97  mov     [rsp+88h+hTemplateFile], rax; lpBytesReturned
0x180008e9c  mov     [rsp+88h+dwFlagsAndAttributes], edi; nOutBufferSize
0x180008ea0  mov     qword ptr [rsp+88h+dwCreationDisposition], rbx; lpOutBuffer
0x180008ea5  mov     r9d, edi; nInBufferSize
0x180008ea8  mov     r8, rbx; lpInBuffer
0x180008eab  mov     edx, 220410h; dwIoControlCode
0x180008eb0  mov     rcx, r12; hDevice
0x180008eb3  call    cs:__imp_DeviceIoControl
0x180008eb9  mov     r14d, eax
0x180008ebc  test    eax, eax
0x180008ebe  jnz     short loc_180008EE9
0x180008ec0  call    cs:__imp_GetLastError
0x180008ec6  cmp     eax, 1Fh
0x180008ec9  jnz     short loc_180008ECD
0x180008ecb  jmp     short loc_180008EFF
0x180008ecd  call    cs:__imp_GetLastError
0x180008ed3  test    eax, eax
0x180008ed5  jz      short loc_180008EE9
0x180008ed7  call    cs:__imp_GetLastError
0x180008edd  mov     ecx, eax
0x180008edf  xor     r8d, r8d
0x180008ee2  xor     edx, edx
0x180008ee4  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x180008ee9  cmp     [rsp+88h+BytesReturned], edi
0x180008ef0  jnz     short loc_180008F2E
0x180008ef2  movzx   ecx, word ptr [rbx+0Eh]
0x180008ef6  lea     rax, [rsi-0Ch]
0x180008efa  cmp     rcx, rax
0x180008efd  ja      short loc_180008F2E
0x180008eff  mov     rcx, r12; hObject
0x180008f02  call    cs:__imp_CloseHandle
0x180008f08  nop
0x180008f09  test    r14d, r14d
0x180008f0c  setnz   bl
0x180008f0f  lea     rcx, [rsp+88h+arg_18]; this
0x180008f17  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008f1c  mov     al, bl
0x180008f1e  add     rsp, 50h
0x180008f22  pop     r15
0x180008f24  pop     r14
0x180008f26  pop     r13
0x180008f28  pop     r12
0x180008f2a  pop     rdi
0x180008f2b  pop     rsi
0x180008f2c  pop     rbx
0x180008f2d  retn
0x180008f2e  xor     r8d, r8d
0x180008f31  lea     edx, [r8+1]
0x180008f35  mov     ecx, 80004005h
0x180008f3a  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
```
