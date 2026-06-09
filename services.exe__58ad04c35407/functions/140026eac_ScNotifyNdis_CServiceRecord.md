# ScNotifyNdis(CServiceRecord *)

- ea: `0x140026eac`
- end: `0x140026ff3`
- name: `?ScNotifyNdis@@YAXPEAVCServiceRecord@@@Z`
- size: `327`
- prototype: `void __fastcall(struct CServiceRecord *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x14003d5f0`
- `0x1400735a0`

## callees

- `0x140004c58`
- `0x140026eac`
- `0x140073884`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026f80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026fc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026f80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026fc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140026f51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140026f51`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140026efa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140026efa`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140026f46`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140026f46`

## pseudocode

```c
void __fastcall ScNotifyNdis(struct CServiceRecord *a1)
{
  HANDLE FileW; // rax
  __int64 v3; // r9
  void *v4; // rsi
  _WORD *v5; // r8
  BOOL v6; // ebx
  char v7; // al
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  DWORD LastError; // eax
  DWORD BytesReturned; // [rsp+70h] [rbp+8h] BYREF

  BytesReturned = 0;
  if ( *((struct CNameEntry **)a1 + 16) == ScGlobalTDIGroup )
  {
    FileW = CreateFileW(L"\\\\.\\NDIS", 0xC0000000, 0, 0, 3u, 0, 0);
    v3 = -1;
    v4 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 16, WPP_1034a0789af238a5c33ce0a92ac054ae_Traceguids, LastError);
      }
    }
    else
    {
      v5 = (_WORD *)*((_QWORD *)a1 + 7);
      do
        ++v3;
      while ( v5[v3] );
      v6 = DeviceIoControl(FileW, 0x170014u, v5, 2 * v3 + 2, 0, 0, &BytesReturned, 0);
      CloseHandle(v4);
      if ( !v6
        && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
      {
        v7 = GetLastError();
        WPP_SF_LSL(WPP_GLOBAL_Control->StubInfo, v8, v9, v10, *((_QWORD *)a1 + 7), v7);
      }
    }
  }
}

```

## disassembly

```asm
0x140026eac  push    rbx
0x140026eae  push    rbp
0x140026eaf  push    rsi
0x140026eb0  push    rdi
0x140026eb1  sub     rsp, 48h
0x140026eb5  mov     rax, cs:?ScGlobalTDIGroup@@3PEAVCNameEntry@@EA; CNameEntry * ScGlobalTDIGroup
0x140026ebc  xor     ebp, ebp
0x140026ebe  mov     rdi, rcx
0x140026ec1  mov     [rsp+68h+BytesReturned], ebp
0x140026ec5  cmp     [rcx+80h], rax
0x140026ecc  jz      short loc_140026ED7
0x140026ece  add     rsp, 48h
0x140026ed2  pop     rdi
0x140026ed3  pop     rsi
0x140026ed4  pop     rbp
0x140026ed5  pop     rbx
0x140026ed6  retn
0x140026ed7  mov     [rsp+68h+hTemplateFile], rbp; hTemplateFile
0x140026edc  lea     rcx, FileName; "\\\\.\\NDIS"
0x140026ee3  mov     [rsp+68h+dwFlagsAndAttributes], ebp; dwFlagsAndAttributes
0x140026ee7  xor     r9d, r9d; lpSecurityAttributes
0x140026eea  xor     r8d, r8d; dwShareMode
0x140026eed  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x140026ef5  mov     edx, 0C0000000h; dwDesiredAccess
0x140026efa  call    cs:__imp_CreateFileW
0x140026f00  or      r9, 0FFFFFFFFFFFFFFFFh
0x140026f04  mov     rsi, rax
0x140026f07  cmp     rax, r9
0x140026f0a  jz      loc_140026FA8
0x140026f10  mov     r8, [rdi+38h]; lpInBuffer
0x140026f14  inc     r9
0x140026f17  cmp     [r8+r9*2], bp
0x140026f1c  jnz     short loc_140026F14
0x140026f1e  mov     [rsp+68h+lpOverlapped], rbp; lpOverlapped
0x140026f23  lea     rax, [rsp+68h+BytesReturned]
0x140026f28  mov     [rsp+68h+hTemplateFile], rax; lpBytesReturned
0x140026f2d  lea     r9d, ds:2[r9*2]; nInBufferSize
0x140026f35  mov     [rsp+68h+dwFlagsAndAttributes], ebp; nOutBufferSize
0x140026f39  mov     edx, 170014h; dwIoControlCode
0x140026f3e  mov     rcx, rsi; hDevice
0x140026f41  mov     qword ptr [rsp+68h+dwCreationDisposition], rbp; lpOutBuffer
0x140026f46  call    cs:__imp_DeviceIoControl
0x140026f4c  mov     rcx, rsi; hObject
0x140026f4f  mov     ebx, eax
0x140026f51  call    cs:__imp_CloseHandle
0x140026f57  test    ebx, ebx
0x140026f59  jnz     loc_140026ECE
0x140026f5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140026f66  lea     rax, WPP_GLOBAL_Control
0x140026f6d  cmp     rcx, rax
0x140026f70  jz      loc_140026ECE
0x140026f76  test    byte ptr [rcx+1Ch], 2
0x140026f7a  jz      loc_140026ECE
0x140026f80  call    cs:__imp_GetLastError
0x140026f86  mov     rcx, cs:WPP_GLOBAL_Control
0x140026f8d  mov     [rsp+68h+dwFlagsAndAttributes], eax
0x140026f91  mov     rax, [rdi+38h]
0x140026f95  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x140026f9a  mov     rcx, [rcx+10h]
0x140026f9e  call    WPP_SF_LSL
0x140026fa3  jmp     loc_140026ECE
0x140026fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x140026faf  lea     rax, WPP_GLOBAL_Control
0x140026fb6  cmp     rcx, rax
0x140026fb9  jz      loc_140026ECE
0x140026fbf  test    byte ptr [rcx+1Ch], 2
0x140026fc3  jz      loc_140026ECE
0x140026fc9  call    cs:__imp_GetLastError
0x140026fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x140026fd6  lea     r8, WPP_1034a0789af238a5c33ce0a92ac054ae_Traceguids
0x140026fdd  mov     edx, 10h
0x140026fe2  mov     r9d, eax
0x140026fe5  mov     rcx, [rcx+10h]
0x140026fe9  call    WPP_SF_d
0x140026fee  jmp     loc_140026ECE
```
