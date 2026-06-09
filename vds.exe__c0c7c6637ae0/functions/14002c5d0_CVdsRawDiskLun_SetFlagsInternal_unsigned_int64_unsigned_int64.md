# CVdsRawDiskLun::SetFlagsInternal(unsigned __int64,unsigned __int64)

- ea: `0x14002c5d0`
- end: `0x14002c79a`
- name: `?SetFlagsInternal@CVdsRawDiskLun@@QEAAJ_K0@Z`
- size: `458`
- prototype: `__int64 __fastcall(CVdsRawDiskLun *__hidden this, unsigned __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140023320`
- `0x140025000`

## callees

- `0x14002c5d0`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c6dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c6dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c730`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c730`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002c6d2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002c6d2`
- `vdsutil!OpenDevice` at `0x14002c663`
- `vdsutil!OpenDevice` at `0x14002c663`
- `vdsutil!VdsTraceExW` at `0x14002c629`
- `vdsutil!VdsTraceExW` at `0x14002c71c`
- `vdsutil!VdsTraceExW` at `0x14002c76e`
- `vdsutil!VdsTraceExW` at `0x14002c629`
- `vdsutil!VdsTraceExW` at `0x14002c71c`
- `vdsutil!VdsTraceExW` at `0x14002c76e`

## pseudocode

```c
__int64 __fastcall CVdsRawDiskLun::SetFlagsInternal(CVdsRawDiskLun *this, __int64 a2)
{
  __int64 v4; // rcx
  const wchar_t *v5; // rsi
  const wchar_t *v6; // rax
  const wchar_t *v7; // r8
  unsigned int v8; // ebx
  int v9; // eax
  signed int LastError; // eax
  const wchar_t *v11; // r9
  LPVOID lpOutBuffer; // [rsp+20h] [rbp-60h]
  __int64 nOutBufferSize; // [rsp+28h] [rbp-58h]
  HANDLE hDevice; // [rsp+40h] [rbp-40h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-38h] BYREF
  _BYTE InBuffer[40]; // [rsp+50h] [rbp-30h] BYREF

  hDevice = 0;
  BytesReturned = 0;
  memset(InBuffer, 0, sizeof(InBuffer));
  VdsTraceExW(95, 2, L"CVdsRawDiskLun::SetFlagsInternal");
  v4 = *((_QWORD *)this + 30);
  v5 = L"UNKNOWN";
  if ( v4 )
  {
    v9 = OpenDevice(v4, 3221225472LL, &hDevice);
    v8 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
      v7 = L"CVdsRawDiskLun::SetFlagsInternal, 3 Name=%s, Number=%ld, hr=%lX";
    }
    else
    {
      *(_QWORD *)InBuffer = 0x100000028LL;
      v8 = 0;
      *(_QWORD *)&InBuffer[8] = a2;
      *(_OWORD *)&InBuffer[24] = 0;
      *(_QWORD *)&InBuffer[16] = 2;
      if ( DeviceIoControl(hDevice, 0x7C0F4u, InBuffer, 0x28u, 0, 0, &BytesReturned, 0) )
        goto LABEL_15;
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v7 = L"CVdsRawDiskLun::SetFlagsInternal, 4 Name=%s, Number=%ld, hr=%lX";
    }
    v6 = (const wchar_t *)*((_QWORD *)this + 30);
  }
  else
  {
    v6 = (const wchar_t *)*((_QWORD *)this + 27);
    v7 = L"CVdsRawDiskLun::SetFlagsInternal, 2 Name=%s, Number=%ld, hr=%lX";
    v8 = -2147211505;
  }
  v11 = L"UNKNOWN";
  LODWORD(nOutBufferSize) = v8;
  if ( v6 )
    v11 = v6;
  LODWORD(lpOutBuffer) = *((_DWORD *)this + 80);
  VdsTraceExW(94, 0, v7, v11, lpOutBuffer, nOutBufferSize);
LABEL_15:
  if ( (char *)hDevice - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hDevice);
    hDevice = (HANDLE)-1LL;
  }
  LODWORD(nOutBufferSize) = v8;
  if ( *((_QWORD *)this + 30) )
    v5 = (const wchar_t *)*((_QWORD *)this + 30);
  LODWORD(lpOutBuffer) = *((_DWORD *)this + 80);
  VdsTraceExW(
    94,
    2,
    L"EXIT CVdsRawDiskLun::SetFlagsInternal, Name=%s, Number=%ld, status=%lX",
    v5,
    lpOutBuffer,
    nOutBufferSize);
  return v8;
}

```

## disassembly

```asm
0x14002c5d0  mov     [rsp-18h+arg_10], rbx
0x14002c5d5  mov     [rsp-18h+arg_18], rsi
0x14002c5da  push    rbp
0x14002c5db  push    rdi
0x14002c5dc  push    r14
0x14002c5de  mov     rbp, rsp
0x14002c5e1  sub     rsp, 80h
0x14002c5e8  mov     rax, cs:__security_cookie
0x14002c5ef  xor     rax, rsp
0x14002c5f2  mov     [rbp+var_8], rax
0x14002c5f6  xor     eax, eax
0x14002c5f8  mov     [rbp+hDevice], 0
0x14002c600  xorps   xmm0, xmm0
0x14002c603  mov     [rbp+BytesReturned], 0
0x14002c60a  mov     r14, rdx
0x14002c60d  mov     [rbp+var_10], rax
0x14002c611  mov     rdi, rcx
0x14002c614  lea     r8, aCvdsrawdisklun_30; "CVdsRawDiskLun::SetFlagsInternal"
0x14002c61b  lea     edx, [rax+2]
0x14002c61e  lea     ecx, [rax+5Fh]
0x14002c621  movups  [rbp+InBuffer], xmm0
0x14002c625  movups  [rbp+var_20], xmm0
0x14002c629  call    cs:__imp_VdsTraceExW
0x14002c62f  mov     rcx, [rdi+0F0h]
0x14002c636  lea     rsi, aUnknown_0; "UNKNOWN"
0x14002c63d  test    rcx, rcx
0x14002c640  jnz     short loc_14002C65A
0x14002c642  mov     rax, [rdi+0D8h]
0x14002c649  lea     r8, aCvdsrawdisklun_59; "CVdsRawDiskLun::SetFlagsInternal, 2 Nam"...
0x14002c650  mov     ebx, 8004270Fh
0x14002c655  jmp     loc_14002C6FF
0x14002c65a  lea     r8, [rbp+hDevice]
0x14002c65e  mov     edx, 0C0000000h
0x14002c663  call    cs:__imp_OpenDevice
0x14002c669  mov     ebx, eax
0x14002c66b  test    eax, eax
0x14002c66d  jz      short loc_14002C683
0x14002c66f  jle     short loc_14002C67A
0x14002c671  movzx   ebx, ax
0x14002c674  or      ebx, 80070000h
0x14002c67a  lea     r8, aCvdsrawdisklun_8; "CVdsRawDiskLun::SetFlagsInternal, 3 Nam"...
0x14002c681  jmp     short loc_14002C6F8
0x14002c683  mov     rcx, [rbp+hDevice]; hDevice
0x14002c687  lea     r8, [rbp+InBuffer]; lpInBuffer
0x14002c68b  xor     eax, eax
0x14002c68d  mov     byte ptr [rbp+InBuffer+4], 1
0x14002c691  mov     [rsp+80h+lpOverlapped], rax; lpOverlapped
0x14002c696  xor     ebx, ebx
0x14002c698  mov     word ptr [rbp+InBuffer+5], ax
0x14002c69c  xorps   xmm0, xmm0
0x14002c69f  mov     byte ptr [rbp+InBuffer+7], al
0x14002c6a2  mov     edx, 7C0F4h; dwIoControlCode
0x14002c6a7  lea     rax, [rbp+BytesReturned]
0x14002c6ab  mov     qword ptr [rbp+InBuffer+8], r14
0x14002c6af  mov     [rsp+80h+lpBytesReturned], rax; lpBytesReturned
0x14002c6b4  lea     r9d, [rbx+28h]; nInBufferSize
0x14002c6b8  mov     dword ptr [rsp+80h+nOutBufferSize], ebx; nOutBufferSize
0x14002c6bc  mov     dword ptr [rbp+InBuffer], r9d
0x14002c6c0  mov     [rsp+80h+lpOutBuffer], rbx; lpOutBuffer
0x14002c6c5  movdqu  [rbp+var_20+8], xmm0
0x14002c6ca  mov     qword ptr [rbp+var_20], 2
0x14002c6d2  call    cs:__imp_DeviceIoControl
0x14002c6d8  test    eax, eax
0x14002c6da  jnz     short loc_14002C722
0x14002c6dc  call    cs:__imp_GetLastError
0x14002c6e2  mov     ebx, eax
0x14002c6e4  test    eax, eax
0x14002c6e6  jle     short loc_14002C6F1
0x14002c6e8  movzx   ebx, ax
0x14002c6eb  or      ebx, 80070000h
0x14002c6f1  lea     r8, aCvdsrawdisklun_71; "CVdsRawDiskLun::SetFlagsInternal, 4 Nam"...
0x14002c6f8  mov     rax, [rdi+0F0h]
0x14002c6ff  mov     ecx, [rdi+140h]
0x14002c705  test    rax, rax
0x14002c708  mov     r9, rsi
0x14002c70b  mov     dword ptr [rsp+80h+nOutBufferSize], ebx
0x14002c70f  cmovnz  r9, rax
0x14002c713  mov     dword ptr [rsp+80h+lpOutBuffer], ecx
0x14002c717  xor     edx, edx
0x14002c719  lea     ecx, [rdx+5Eh]
0x14002c71c  call    cs:__imp_VdsTraceExW
0x14002c722  mov     rcx, [rbp+hDevice]; hObject
0x14002c726  lea     rax, [rcx-1]
0x14002c72a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002c72e  ja      short loc_14002C73E
0x14002c730  call    cs:__imp_CloseHandle
0x14002c736  mov     [rbp+hDevice], 0FFFFFFFFFFFFFFFFh
0x14002c73e  mov     r8, [rdi+0F0h]
0x14002c745  mov     edx, 2
0x14002c74a  mov     r10d, [rdi+140h]
0x14002c751  test    r8, r8
0x14002c754  mov     dword ptr [rsp+80h+nOutBufferSize], ebx
0x14002c758  cmovnz  rsi, r8
0x14002c75c  mov     dword ptr [rsp+80h+lpOutBuffer], r10d
0x14002c761  mov     r9, rsi
0x14002c764  lea     r8, aExitCvdsrawdis_1; "EXIT CVdsRawDiskLun::SetFlagsInternal, "...
0x14002c76b  lea     ecx, [rdx+5Ch]
0x14002c76e  call    cs:__imp_VdsTraceExW
0x14002c774  mov     eax, ebx
0x14002c776  mov     rcx, [rbp+var_8]
0x14002c77a  xor     rcx, rsp; StackCookie
0x14002c77d  call    __security_check_cookie
0x14002c782  lea     r11, [rsp+80h+var_s0]
0x14002c78a  mov     rbx, [r11+30h]
0x14002c78e  mov     rsi, [r11+38h]
0x14002c792  mov     rsp, r11
0x14002c795  pop     r14
0x14002c797  pop     rdi
0x14002c798  pop     rbp
0x14002c799  retn
```
