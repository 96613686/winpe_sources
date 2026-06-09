# CGroupPolicy::IsHotPluggableBus(void *)

- ea: `0x180010464`
- end: `0x1800105dc`
- name: `?IsHotPluggableBus@CGroupPolicy@@IEAAHPEAX@Z`
- size: `376`
- prototype: `_BOOL8 __fastcall(CGroupPolicy *this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800101cc`

## callees

- `0x180002fa0`
- `0x1800097d0`
- `0x180010464`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104e3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800104d9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001056e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800104d9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001056e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010527`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010527`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001057b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010589`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001057b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010589`

## string_xrefs

- `0x180010509`: `Invalid descriptor size\n`

## pseudocode

```c
_BOOL8 __fastcall CGroupPolicy::IsHotPluggableBus(CGroupPolicy *this, void *a2)
{
  DWORD LastError; // eax
  _DWORD *lpOutBuffer; // rdi
  int v5; // ebx
  DWORD BytesReturned; // [rsp+48h] [rbp+7h] BYREF
  SIZE_T uBytes[2]; // [rsp+50h] [rbp+Fh] BYREF
  __int128 v9; // [rsp+60h] [rbp+1Fh]
  __int64 v10; // [rsp+70h] [rbp+2Fh]
  int InBuffer; // [rsp+78h] [rbp+37h] BYREF
  __int64 v12; // [rsp+7Ch] [rbp+3Bh]

  v12 = 0;
  v10 = 0;
  BytesReturned = 0;
  InBuffer = 0;
  *(_OWORD *)uBytes = 0;
  v9 = 0;
  if ( !DeviceIoControl(a2, 0x2D1400u, &InBuffer, 0xCu, uBytes, 0x28u, &BytesReturned, 0) )
    goto LABEL_2;
  if ( !HIDWORD(uBytes[0]) )
  {
    GPDebugPrintX(2, "Invalid descriptor size\n");
    return 0;
  }
  lpOutBuffer = LocalAlloc(0x40u, HIDWORD(uBytes[0]));
  if ( !lpOutBuffer )
  {
    GPDebugPrintX(2, "Failed to allocate buffer\n");
    return 0;
  }
  if ( !DeviceIoControl(a2, 0x2D1400u, &InBuffer, 0xCu, lpOutBuffer, HIDWORD(uBytes[0]), &BytesReturned, 0) )
  {
    LocalFree(lpOutBuffer);
LABEL_2:
    LastError = GetLastError();
    GPDebugPrintX(2, "Ioctl STORAGE_QUERY_PROPERTY failed (%d)\n", LastError);
    return 0;
  }
  v5 = lpOutBuffer[7];
  LocalFree(lpOutBuffer);
  GPDebugPrintX(8, "Bus Type %d\n", v5);
  return v5 == 4 || v5 == 7 || v5 == 12;
}

```

## disassembly

```asm
0x180010464  mov     r11, rsp
0x180010467  mov     [r11+8], rbx
0x18001046b  mov     [r11+18h], rdi
0x18001046f  push    rbp
0x180010470  lea     rbp, [r11-5Fh]
0x180010474  sub     rsp, 90h
0x18001047b  mov     rax, cs:__security_cookie
0x180010482  xor     rax, rsp
0x180010485  mov     [rbp+57h+var_10], rax
0x180010489  xor     eax, eax
0x18001048b  mov     [rbp+57h+var_1C], 0
0x180010493  mov     [r11-60h], rax
0x180010497  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18001049b  mov     [rbp+57h+var_28], rax
0x18001049f  mov     rbx, rdx
0x1800104a2  mov     [rbp+57h+BytesReturned], eax
0x1800104a5  xorps   xmm0, xmm0
0x1800104a8  mov     [rbp+57h+InBuffer], eax
0x1800104ab  mov     r9d, 0Ch; nInBufferSize
0x1800104b1  lea     rax, [rbp+57h+BytesReturned]
0x1800104b5  mov     edx, 2D1400h; dwIoControlCode
0x1800104ba  mov     [r11-68h], rax
0x1800104be  mov     rcx, rbx; hDevice
0x1800104c1  lea     rax, [rbp+57h+uBytes]
0x1800104c5  mov     [rsp+90h+nOutBufferSize], 28h ; '('; nOutBufferSize
0x1800104cd  mov     [r11-78h], rax
0x1800104d1  movups  xmmword ptr [rbp+57h+uBytes], xmm0
0x1800104d5  movups  [rbp+57h+var_38], xmm0
0x1800104d9  call    cs:__imp_DeviceIoControl
0x1800104df  test    eax, eax
0x1800104e1  jnz     short loc_180010502
0x1800104e3  call    cs:__imp_GetLastError
0x1800104e9  lea     rdx, aIoctlStorageQu; "Ioctl STORAGE_QUERY_PROPERTY failed (%d"...
0x1800104f0  mov     ecx, 2; unsigned int
0x1800104f5  mov     r8d, eax
0x1800104f8  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x1800104fd  jmp     loc_1800105B2
0x180010502  mov     eax, dword ptr [rbp+57h+uBytes+4]
0x180010505  test    eax, eax
0x180010507  jnz     short loc_18001051F
0x180010509  lea     rdx, aInvalidDescrip; "Invalid descriptor size\n"
0x180010510  mov     ecx, 2; unsigned int
0x180010515  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18001051a  jmp     loc_1800105B2
0x18001051f  mov     rdx, rax; uBytes
0x180010522  mov     ecx, 40h ; '@'; uFlags
0x180010527  call    cs:__imp_LocalAlloc
0x18001052d  mov     rdi, rax
0x180010530  test    rax, rax
0x180010533  jnz     short loc_18001053E
0x180010535  lea     rdx, aFailedToAlloca; "Failed to allocate buffer\n"
0x18001053c  jmp     short loc_180010510
0x18001053e  lea     rax, [rbp+57h+BytesReturned]
0x180010542  mov     [rsp+90h+lpOverlapped], 0; lpOverlapped
0x18001054b  mov     [rsp+90h+lpBytesReturned], rax; lpBytesReturned
0x180010550  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x180010554  mov     eax, dword ptr [rbp+57h+uBytes+4]
0x180010557  mov     r9d, 0Ch; nInBufferSize
0x18001055d  mov     [rsp+90h+nOutBufferSize], eax; nOutBufferSize
0x180010561  mov     edx, 2D1400h; dwIoControlCode
0x180010566  mov     rcx, rbx; hDevice
0x180010569  mov     [rsp+90h+lpOutBuffer], rdi; lpOutBuffer
0x18001056e  call    cs:__imp_DeviceIoControl
0x180010574  mov     rcx, rdi; hMem
0x180010577  test    eax, eax
0x180010579  jnz     short loc_180010586
0x18001057b  call    cs:__imp_LocalFree
0x180010581  jmp     loc_1800104E3
0x180010586  mov     ebx, [rdi+1Ch]
0x180010589  call    cs:__imp_LocalFree
0x18001058f  mov     r8d, ebx
0x180010592  lea     rdx, aBusTypeD; "Bus Type %d\n"
0x180010599  mov     ecx, 8; unsigned int
0x18001059e  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x1800105a3  cmp     ebx, 4
0x1800105a6  jz      short loc_1800105B6
0x1800105a8  cmp     ebx, 7
0x1800105ab  jz      short loc_1800105B6
0x1800105ad  cmp     ebx, 0Ch
0x1800105b0  jz      short loc_1800105B6
0x1800105b2  xor     eax, eax
0x1800105b4  jmp     short loc_1800105BB
0x1800105b6  mov     eax, 1
0x1800105bb  mov     rcx, [rbp+57h+var_10]
0x1800105bf  xor     rcx, rsp; StackCookie
0x1800105c2  call    __security_check_cookie
0x1800105c7  lea     r11, [rsp+90h+var_s0]
0x1800105cf  mov     rbx, [r11+10h]
0x1800105d3  mov     rdi, [r11+20h]
0x1800105d7  mov     rsp, r11
0x1800105da  pop     rbp
0x1800105db  retn
```
