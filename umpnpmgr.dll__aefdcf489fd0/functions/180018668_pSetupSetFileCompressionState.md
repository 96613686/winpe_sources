# pSetupSetFileCompressionState

- ea: `0x180018668`
- end: `0x180018728`
- name: `pSetupSetFileCompressionState`
- size: `192`
- prototype: `_BOOL8 __fastcall(const WCHAR *, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18001725c`

## callees

- `0x18000f360`
- `0x180018668`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018715`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001870d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001870d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800186ee`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800186ee`

## pseudocode

```c
_BOOL8 __fastcall pSetupSetFileCompressionState(const WCHAR *a1, int a2, __int64 a3)
{
  DWORD LastError; // ebx
  HANDLE hDevice; // [rsp+40h] [rbp-18h] BYREF
  __int16 InBuffer; // [rsp+68h] [rbp+10h] BYREF
  __int16 InBuffer_2; // [rsp+6Ah] [rbp+12h]
  LONG v8; // [rsp+70h] [rbp+18h] BYREF
  DWORD BytesReturned; // [rsp+78h] [rbp+20h] BYREF

  InBuffer_2 = HIWORD(a2);
  hDevice = (HANDLE)-1LL;
  InBuffer = 0;
  v8 = 0;
  BytesReturned = 0;
  LastError = pSetupOpenFileForWrite(a1, 0, a3, 0, &hDevice, &v8);
  if ( !LastError )
  {
    InBuffer = 1;
    if ( !DeviceIoControl(hDevice, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
      LastError = GetLastError();
  }
  if ( hDevice != (HANDLE)-1LL )
    CloseHandle(hDevice);
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180018668  mov     [rsp+InBuffer], edx
0x18001866c  mov     r11, rsp
0x18001866f  push    rbx
0x180018670  sub     rsp, 50h
0x180018674  xor     eax, eax
0x180018676  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFFh
0x18001867e  mov     word ptr [rsp+58h+InBuffer], ax
0x180018683  xor     r9d, r9d
0x180018686  lea     rax, [r11+18h]
0x18001868a  mov     [rsp+58h+arg_10], 0
0x180018692  mov     [r11-30h], rax
0x180018696  xor     edx, edx
0x180018698  lea     rax, [r11-18h]
0x18001869c  mov     [rsp+58h+BytesReturned], 0
0x1800186a4  mov     [r11-38h], rax
0x1800186a8  call    pSetupOpenFileForWrite
0x1800186ad  mov     ebx, eax
0x1800186af  test    eax, eax
0x1800186b1  jnz     short loc_180018700
0x1800186b3  mov     rcx, [rsp+58h+hDevice]; hDevice
0x1800186b8  lea     eax, [rbx+1]
0x1800186bb  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1800186c4  lea     r9d, [rbx+2]; nInBufferSize
0x1800186c8  mov     word ptr [rsp+58h+InBuffer], ax
0x1800186cd  lea     r8, [rsp+58h+InBuffer]; lpInBuffer
0x1800186d2  lea     rax, [rsp+58h+BytesReturned]
0x1800186d7  mov     edx, 9C040h; dwIoControlCode
0x1800186dc  mov     [rsp+58h+lpBytesReturned], rax; lpBytesReturned
0x1800186e1  mov     [rsp+58h+nOutBufferSize], ebx; nOutBufferSize
0x1800186e5  mov     [rsp+58h+lpOutBuffer], 0; lpOutBuffer
0x1800186ee  call    cs:__imp_DeviceIoControl
0x1800186f4  test    eax, eax
0x1800186f6  jnz     short loc_180018700
0x1800186f8  call    cs:__imp_GetLastError
0x1800186fe  mov     ebx, eax
0x180018700  cmp     [rsp+58h+hDevice], 0FFFFFFFFFFFFFFFFh
0x180018706  jz      short loc_180018713
0x180018708  mov     rcx, [rsp+58h+hDevice]; hObject
0x18001870d  call    cs:__imp_CloseHandle
0x180018713  mov     ecx, ebx; dwErrCode
0x180018715  call    cs:__imp_SetLastError
0x18001871b  xor     eax, eax
0x18001871d  test    ebx, ebx
0x18001871f  setz    al
0x180018722  add     rsp, 50h
0x180018726  pop     rbx
0x180018727  retn
```
