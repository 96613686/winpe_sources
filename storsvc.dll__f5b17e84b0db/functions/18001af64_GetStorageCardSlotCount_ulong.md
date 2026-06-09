# GetStorageCardSlotCount(ulong *)

- ea: `0x18001af64`
- end: `0x18001b15c`
- name: `?GetStorageCardSlotCount@@YAJPEAK@Z`
- size: `504`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180026b60`

## callees

- `0x18000d030`
- `0x18000d400`
- `0x18000d5a4`
- `0x18001a128`
- `0x18001a70c`
- `0x18001af64`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b0df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b113`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b0df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b113`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001b035`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001b0a2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001b035`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001b0a2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001afe8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001afe8`

## pseudocode

```c
__int64 __fastcall GetStorageCardSlotCount(struct _GUID *a1)
{
  unsigned int v1; // edi
  unsigned int v2; // r14d
  int DevicePath; // eax
  HANDLE FileW; // rbp
  unsigned __int64 v6; // rax
  void *v7; // r15
  const struct std::nothrow_t *i; // rdx
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int LastHr; // ebx
  const struct std::nothrow_t *v12; // rdx
  unsigned int OutBuffer; // [rsp+40h] [rbp-258h] BYREF
  DWORD BytesReturned[3]; // [rsp+44h] [rbp-254h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-248h] BYREF

  v1 = 0;
  BytesReturned[0] = 0;
  v2 = 0;
  OutBuffer = 0;
  while ( 1 )
  {
    DevicePath = GetDevicePath(a1, v2, FileName);
    if ( DevicePath < 0 )
      break;
    FileW = CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastHr = GetLastHr();
      goto LABEL_22;
    }
    OutBuffer = 0;
    if ( !DeviceIoControl(FileW, 0x43074u, 0, 0, &OutBuffer, 4u, BytesReturned, 0) )
    {
      LastHr = GetLastHr();
LABEL_17:
      a1->Data1 = v1;
LABEL_18:
      CloseHandle(FileW);
      return LastHr;
    }
    v6 = 48LL * OutBuffer;
    if ( !is_mul_ok(OutBuffer, 0x30u) )
      v6 = -1;
    v7 = operator new[](v6, (const struct std::nothrow_t *)std::nothrow);
    if ( !v7 )
    {
      LastHr = -2147024882;
      goto LABEL_17;
    }
    if ( !DeviceIoControl(FileW, 0x43078u, 0, 0, v7, 48 * OutBuffer, BytesReturned, 0) )
    {
      v10 = GetLastHr();
      a1->Data1 = v1;
      LastHr = v10;
      operator delete(v7, v12);
      goto LABEL_18;
    }
    for ( i = 0; (unsigned int)i < OutBuffer; v1 = v9 )
    {
      v9 = v1 + 1;
      if ( *((_BYTE *)v7 + 48 * (_QWORD)i + 36) )
        v9 = v1;
      i = (const struct std::nothrow_t *)(unsigned int)((_DWORD)i + 1);
    }
    operator delete(v7, i);
    CloseHandle(FileW);
    ++v2;
  }
  LastHr = 0;
  if ( !v2 )
    LastHr = DevicePath;
LABEL_22:
  a1->Data1 = v1;
  return LastHr;
}

```

## disassembly

```asm
0x18001af64  mov     [rsp+arg_8], rbx
0x18001af69  mov     [rsp+arg_10], rbp
0x18001af6e  push    rsi
0x18001af6f  push    rdi
0x18001af70  push    r13
0x18001af72  push    r14
0x18001af74  push    r15
0x18001af76  sub     rsp, 270h
0x18001af7d  mov     rax, cs:__security_cookie
0x18001af84  xor     rax, rsp
0x18001af87  mov     [rsp+298h+var_38], rax
0x18001af8f  xor     edi, edi
0x18001af91  mov     [rsp+298h+BytesReturned], 0
0x18001af99  xor     r14d, r14d
0x18001af9c  mov     [rsp+298h+OutBuffer], 0
0x18001afa4  mov     rsi, rcx
0x18001afa7  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001afab  lea     ebx, [rdi+3]
0x18001afae  lea     r8, [rsp+298h+FileName]; unsigned __int16 *
0x18001afb3  mov     edx, r14d; unsigned int
0x18001afb6  call    ?GetDevicePath@@YAJQEBU_GUID@@KPEAG_K@Z; GetDevicePath(_GUID const * const,ulong,ushort *,unsigned __int64)
0x18001afbb  test    eax, eax
0x18001afbd  js      loc_18001B124
0x18001afc3  mov     [rsp+298h+hTemplateFile], 0; hTemplateFile
0x18001afcc  lea     rcx, [rsp+298h+FileName]; lpFileName
0x18001afd1  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001afd9  xor     r9d, r9d; lpSecurityAttributes
0x18001afdc  mov     r8d, ebx; dwShareMode
0x18001afdf  mov     [rsp+298h+dwCreationDisposition], ebx; dwCreationDisposition
0x18001afe3  mov     edx, 80000000h; dwDesiredAccess
0x18001afe8  call    cs:__imp_CreateFileW
0x18001afee  mov     rbp, rax
0x18001aff1  cmp     rax, r13
0x18001aff4  jz      loc_18001B11B
0x18001affa  mov     [rsp+298h+lpOverlapped], 0; lpOverlapped
0x18001b003  lea     rax, [rsp+298h+BytesReturned]
0x18001b008  mov     [rsp+298h+hTemplateFile], rax; lpBytesReturned
0x18001b00d  xor     r9d, r9d; nInBufferSize
0x18001b010  lea     rax, [rsp+298h+OutBuffer]
0x18001b015  mov     [rsp+298h+dwFlagsAndAttributes], 4; nOutBufferSize
0x18001b01d  xor     r8d, r8d; lpInBuffer
0x18001b020  mov     qword ptr [rsp+298h+dwCreationDisposition], rax; lpOutBuffer
0x18001b025  mov     edx, 43074h; dwIoControlCode
0x18001b02a  mov     [rsp+298h+OutBuffer], 0
0x18001b032  mov     rcx, rbp; hDevice
0x18001b035  call    cs:__imp_DeviceIoControl
0x18001b03b  test    eax, eax
0x18001b03d  jz      loc_18001B107
0x18001b043  mov     ecx, [rsp+298h+OutBuffer]
0x18001b047  mov     eax, 30h ; '0'
0x18001b04c  mul     rcx
0x18001b04f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b056  cmovb   rax, r13
0x18001b05a  mov     rcx, rax; unsigned __int64
0x18001b05d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001b062  mov     r15, rax
0x18001b065  test    rax, rax
0x18001b068  jz      loc_18001B100
0x18001b06e  mov     ecx, [rsp+298h+OutBuffer]
0x18001b072  lea     rax, [rsp+298h+BytesReturned]
0x18001b077  mov     [rsp+298h+lpOverlapped], 0; lpOverlapped
0x18001b080  xor     r9d, r9d; nInBufferSize
0x18001b083  mov     [rsp+298h+hTemplateFile], rax; lpBytesReturned
0x18001b088  xor     r8d, r8d; lpInBuffer
0x18001b08b  lea     edx, [rcx+rcx*2]
0x18001b08e  mov     rcx, rbp; hDevice
0x18001b091  shl     edx, 4
0x18001b094  mov     [rsp+298h+dwFlagsAndAttributes], edx; nOutBufferSize
0x18001b098  mov     edx, 43078h; dwIoControlCode
0x18001b09d  mov     qword ptr [rsp+298h+dwCreationDisposition], r15; lpOutBuffer
0x18001b0a2  call    cs:__imp_DeviceIoControl
0x18001b0a8  test    eax, eax
0x18001b0aa  jz      short loc_18001B0ED
0x18001b0ac  mov     r8d, [rsp+298h+OutBuffer]
0x18001b0b1  xor     edx, edx
0x18001b0b3  test    r8d, r8d
0x18001b0b6  jz      short loc_18001B0D4
0x18001b0b8  lea     rcx, [rdx+rdx*2]
0x18001b0bc  add     rcx, rcx
0x18001b0bf  lea     eax, [rdi+1]
0x18001b0c2  cmp     byte ptr [r15+rcx*8+24h], 0
0x18001b0c8  cmovnz  eax, edi
0x18001b0cb  inc     edx; struct std::nothrow_t *
0x18001b0cd  mov     edi, eax
0x18001b0cf  cmp     edx, r8d
0x18001b0d2  jb      short loc_18001B0B8
0x18001b0d4  mov     rcx, r15; void *
0x18001b0d7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b0dc  mov     rcx, rbp; hObject
0x18001b0df  call    cs:__imp_CloseHandle
0x18001b0e5  inc     r14d
0x18001b0e8  jmp     loc_18001AFAE
0x18001b0ed  call    ?GetLastHr@@YAJXZ; GetLastHr(void)
0x18001b0f2  mov     rcx, r15; void *
0x18001b0f5  mov     [rsi], edi
0x18001b0f7  mov     ebx, eax
0x18001b0f9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b0fe  jmp     short loc_18001B110
0x18001b100  mov     ebx, 8007000Eh
0x18001b105  jmp     short loc_18001B10E
0x18001b107  call    ?GetLastHr@@YAJXZ; GetLastHr(void)
0x18001b10c  mov     ebx, eax
0x18001b10e  mov     [rsi], edi
0x18001b110  mov     rcx, rbp; hObject
0x18001b113  call    cs:__imp_CloseHandle
0x18001b119  jmp     short loc_18001B12E
0x18001b11b  call    ?GetLastHr@@YAJXZ; GetLastHr(void)
0x18001b120  mov     ebx, eax
0x18001b122  jmp     short loc_18001B12C
0x18001b124  xor     ebx, ebx
0x18001b126  test    r14d, r14d
0x18001b129  cmovz   ebx, eax
0x18001b12c  mov     [rsi], edi
0x18001b12e  mov     eax, ebx
0x18001b130  mov     rcx, [rsp+298h+var_38]
0x18001b138  xor     rcx, rsp; StackCookie
0x18001b13b  call    __security_check_cookie
0x18001b140  lea     r11, [rsp+298h+var_28]
0x18001b148  mov     rbx, [r11+38h]
0x18001b14c  mov     rbp, [r11+40h]
0x18001b150  mov     rsp, r11
0x18001b153  pop     r15
0x18001b155  pop     r14
0x18001b157  pop     r13
0x18001b159  pop     rdi
0x18001b15a  pop     rsi
0x18001b15b  retn
```
