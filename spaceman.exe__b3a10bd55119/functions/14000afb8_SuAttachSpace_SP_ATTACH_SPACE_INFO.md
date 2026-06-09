# SuAttachSpace(_SP_ATTACH_SPACE_INFO *)

- ea: `0x14000afb8`
- end: `0x14000b1f9`
- name: `?SuAttachSpace@@YAHPEAU_SP_ATTACH_SPACE_INFO@@@Z`
- size: `577`
- prototype: `__int64 __fastcall(struct _SP_ATTACH_SPACE_INFO *lpInBuffer)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140002c1c`

## callees

- `0x140004d1c`
- `0x14000a7a8`
- `0x14000afb8`
- `0x14000b5d8`
- `0x14000b704`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b1d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b1d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b0a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b10c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b0a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b10c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000b0c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000b0c1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000b04a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000b04a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000b005`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000b119`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000b005`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000b119`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x14000b0f9`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x14000b0f9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000b096`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000b096`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b1cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b1cc`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x14000b0d2`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x14000b0d2`

## string_xrefs

- `0x14000b05b`: `CreateEvents`

## pseudocode

```c
__int64 __fastcall SuAttachSpace(struct _SP_ATTACH_SPACE_INFO *lpInBuffer)
{
  __int128 v2; // xmm0
  __int128 v3; // xmm1
  unsigned int refreshed; // ebx
  const char *v5; // rdi
  DWORD LastError; // r14d
  int v7; // r8d
  int v8; // r9d
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-19h] BYREF
  LARGE_INTEGER v11; // [rsp+58h] [rbp-11h] BYREF
  __int64 v12; // [rsp+60h] [rbp-9h]
  struct _OVERLAPPED Overlapped; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v14[40]; // [rsp+88h] [rbp+1Fh] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+D0h] [rbp+67h] BYREF

  NumberOfBytesTransferred = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  memset(v14, 0, sizeof(v14));
  SI_TIMER::SI_TIMER((SI_TIMER *)&PerformanceCount);
  QueryPerformanceCounter(&PerformanceCount);
  v2 = *(_OWORD *)lpInBuffer;
  *(_DWORD *)v14 = 40;
  v3 = *((_OWORD *)lpInBuffer + 1);
  v14[36] = 0;
  *(_OWORD *)&v14[4] = v2;
  *(_OWORD *)&v14[20] = v3;
  refreshed = SuRefreshPool((struct _SP_REFRESH_INFO *)v14);
  if ( refreshed )
  {
    Overlapped.hEvent = CreateEventW(0, 0, 0, 0);
    if ( Overlapped.hEvent )
    {
      v5 = 0;
      LastError = 0;
      refreshed = DeviceIoControl(Spaceport, 0xE7C820u, lpInBuffer, 0x34u, 0, 0, 0, &Overlapped);
      if ( refreshed )
        goto LABEL_14;
      if ( GetLastError() == 997 )
      {
        if ( !WaitForSingleObject(Overlapped.hEvent, 0x7530u) || (refreshed = CancelIo(Spaceport)) != 0 )
        {
          refreshed = GetOverlappedResult(Spaceport, &Overlapped, &NumberOfBytesTransferred, 0);
          if ( refreshed )
            goto LABEL_14;
          v5 = "GetOverlappedResult";
        }
        else
        {
          v5 = "CancelIo";
        }
      }
      else
      {
        v5 = "DeviceIoControl - IOCTL_SPACEPORT_ATTACH_SPACE";
      }
    }
    else
    {
      refreshed = 0;
      v5 = "CreateEvents";
    }
  }
  else
  {
    v5 = "SuRefreshPool";
  }
  LastError = GetLastError();
LABEL_14:
  QueryPerformanceCounter(&v11);
  if ( refreshed )
  {
    if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 2) != 0 )
      McTemplateK0zsjjtx_EventWriteTransfer(
        *((unsigned __int8 *)lpInBuffer + 48),
        (unsigned int)AttachSpaceSucceeded,
        (_DWORD)lpInBuffer + 16,
        v8,
        (__int64)"SuAttachSpace",
        (__int64)lpInBuffer + 16,
        (__int64)lpInBuffer + 32,
        *((_BYTE *)lpInBuffer + 48),
        1000000 * (v11.QuadPart - PerformanceCount.QuadPart) / v12);
  }
  else if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
  {
    McTemplateK0zsjjtsq_EventWriteTransfer(
      (_DWORD)lpInBuffer + 32,
      (unsigned int)AttachSpaceFailed,
      v7,
      v8,
      (__int64)"SuAttachSpace",
      (__int64)lpInBuffer + 16,
      (__int64)lpInBuffer + 32,
      *((_BYTE *)lpInBuffer + 48),
      (__int64)v5,
      LastError);
  }
  if ( Overlapped.hEvent )
    CloseHandle(Overlapped.hEvent);
  if ( !refreshed )
    SetLastError(LastError);
  return refreshed;
}

```

## disassembly

```asm
0x14000afb8  mov     [rsp-8+arg_8], rbx
0x14000afbd  mov     [rsp-8+arg_10], rsi
0x14000afc2  push    rbp
0x14000afc3  push    rdi
0x14000afc4  push    r14
0x14000afc6  lea     rbp, [rsp-47h]
0x14000afcb  sub     rsp, 0B0h
0x14000afd2  xorps   xmm0, xmm0
0x14000afd5  mov     [rbp+57h+NumberOfBytesTransferred], 0
0x14000afdc  xorps   xmm1, xmm1
0x14000afdf  mov     rsi, rcx
0x14000afe2  xor     eax, eax
0x14000afe4  lea     rcx, [rbp+57h+PerformanceCount]; this
0x14000afe8  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x14000afec  mov     [rbp+57h+var_18], rax
0x14000aff0  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x14000aff4  movups  [rbp+57h+var_38], xmm1
0x14000aff8  movups  [rbp+57h+var_28], xmm1
0x14000affc  call    ??0SI_TIMER@@QEAA@XZ; SI_TIMER::SI_TIMER(void)
0x14000b001  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x14000b005  call    cs:__imp_QueryPerformanceCounter
0x14000b00b  movups  xmm0, xmmword ptr [rsi]
0x14000b00e  lea     rcx, [rbp+57h+var_38]; struct _SP_REFRESH_INFO *
0x14000b012  mov     dword ptr [rbp+57h+var_38], 28h ; '('
0x14000b019  movups  xmm1, xmmword ptr [rsi+10h]
0x14000b01d  mov     byte ptr [rbp+57h+var_18+4], 0
0x14000b021  movups  [rbp+57h+var_38+4], xmm0
0x14000b025  movups  [rbp+57h+var_28+4], xmm1
0x14000b029  call    ?SuRefreshPool@@YAHPEAU_SP_REFRESH_INFO@@@Z; SuRefreshPool(_SP_REFRESH_INFO *)
0x14000b02e  mov     ebx, eax
0x14000b030  test    eax, eax
0x14000b032  jnz     short loc_14000B040
0x14000b034  lea     rdi, aSurefreshpool; "SuRefreshPool"
0x14000b03b  jmp     loc_14000B10C
0x14000b040  xor     r9d, r9d; lpName
0x14000b043  xor     r8d, r8d; bInitialState
0x14000b046  xor     edx, edx; bManualReset
0x14000b048  xor     ecx, ecx; lpEventAttributes
0x14000b04a  call    cs:__imp_CreateEventW
0x14000b050  mov     [rbp+57h+Overlapped.hEvent], rax
0x14000b054  test    rax, rax
0x14000b057  jnz     short loc_14000B067
0x14000b059  xor     ebx, ebx
0x14000b05b  lea     rdi, aCreateevents; "CreateEvents"
0x14000b062  jmp     loc_14000B10C
0x14000b067  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x14000b06e  lea     rax, [rbp+57h+Overlapped]
0x14000b072  mov     [rsp+0C0h+lpOverlapped], rax; lpOverlapped
0x14000b077  xor     edi, edi
0x14000b079  mov     [rsp+0C0h+lpBytesReturned], rdi; lpBytesReturned
0x14000b07e  xor     r14d, r14d
0x14000b081  mov     [rsp+0C0h+nOutBufferSize], edi; nOutBufferSize
0x14000b085  mov     r8, rsi; lpInBuffer
0x14000b088  mov     edx, 0E7C820h; dwIoControlCode
0x14000b08d  mov     [rsp+0C0h+lpOutBuffer], rdi; lpOutBuffer
0x14000b092  lea     r9d, [r14+34h]; nInBufferSize
0x14000b096  call    cs:__imp_DeviceIoControl
0x14000b09c  mov     ebx, eax
0x14000b09e  test    eax, eax
0x14000b0a0  jnz     short loc_14000B115
0x14000b0a2  call    cs:__imp_GetLastError
0x14000b0a8  cmp     eax, 3E5h
0x14000b0ad  jz      short loc_14000B0B8
0x14000b0af  lea     rdi, aDeviceiocontro_1; "DeviceIoControl - IOCTL_SPACEPORT_ATTAC"...
0x14000b0b6  jmp     short loc_14000B10C
0x14000b0b8  mov     rcx, [rbp+57h+Overlapped.hEvent]; hHandle
0x14000b0bc  mov     edx, 7530h; dwMilliseconds
0x14000b0c1  call    cs:__imp_WaitForSingleObject
0x14000b0c7  test    eax, eax
0x14000b0c9  jz      short loc_14000B0E7
0x14000b0cb  mov     rcx, cs:?Spaceport@@3PEAXEA; hFile
0x14000b0d2  call    cs:__imp_CancelIo
0x14000b0d8  mov     ebx, eax
0x14000b0da  test    eax, eax
0x14000b0dc  jnz     short loc_14000B0E7
0x14000b0de  lea     rdi, aCancelio; "CancelIo"
0x14000b0e5  jmp     short loc_14000B10C
0x14000b0e7  mov     rcx, cs:?Spaceport@@3PEAXEA; hFile
0x14000b0ee  lea     r8, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x14000b0f2  xor     r9d, r9d; bWait
0x14000b0f5  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x14000b0f9  call    cs:__imp_GetOverlappedResult
0x14000b0ff  mov     ebx, eax
0x14000b101  test    eax, eax
0x14000b103  jnz     short loc_14000B115
0x14000b105  lea     rdi, aGetoverlappedr; "GetOverlappedResult"
0x14000b10c  call    cs:__imp_GetLastError
0x14000b112  mov     r14d, eax
0x14000b115  lea     rcx, [rbp+57h+var_68]; lpPerformanceCount
0x14000b119  call    cs:__imp_QueryPerformanceCounter
0x14000b11f  test    ebx, ebx
0x14000b121  jz      short loc_14000B17E
0x14000b123  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 2
0x14000b12a  jz      loc_14000B1C3
0x14000b130  mov     rcx, qword ptr [rbp+57h+var_68]
0x14000b134  lea     r8, [rsi+10h]
0x14000b138  sub     rcx, qword ptr [rbp+57h+PerformanceCount]
0x14000b13c  imul    rax, rcx, 0F4240h
0x14000b143  movzx   ecx, byte ptr [rsi+30h]
0x14000b147  cqo
0x14000b149  idiv    [rbp+57h+var_60]
0x14000b14d  lea     rdx, [rsi+20h]
0x14000b151  mov     [rsp+0C0h+var_80], rax
0x14000b156  lea     rax, aSuattachspace; "SuAttachSpace"
0x14000b15d  mov     dword ptr [rsp+0C0h+lpOverlapped], ecx
0x14000b161  mov     [rsp+0C0h+lpBytesReturned], rdx
0x14000b166  lea     rdx, AttachSpaceSucceeded
0x14000b16d  mov     qword ptr [rsp+0C0h+nOutBufferSize], r8
0x14000b172  mov     [rsp+0C0h+lpOutBuffer], rax
0x14000b177  call    McTemplateK0zsjjtx_EventWriteTransfer
0x14000b17c  jmp     short loc_14000B1C3
0x14000b17e  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x14000b185  jz      short loc_14000B1C3
0x14000b187  movzx   eax, byte ptr [rsi+30h]
0x14000b18b  lea     rcx, [rsi+20h]
0x14000b18f  mov     [rsp+0C0h+var_78], r14d
0x14000b194  lea     rdx, [rsi+10h]
0x14000b198  mov     [rsp+0C0h+var_80], rdi
0x14000b19d  mov     dword ptr [rsp+0C0h+lpOverlapped], eax
0x14000b1a1  lea     rax, aSuattachspace; "SuAttachSpace"
0x14000b1a8  mov     [rsp+0C0h+lpBytesReturned], rcx
0x14000b1ad  mov     qword ptr [rsp+0C0h+nOutBufferSize], rdx
0x14000b1b2  lea     rdx, AttachSpaceFailed
0x14000b1b9  mov     [rsp+0C0h+lpOutBuffer], rax
0x14000b1be  call    McTemplateK0zsjjtsq_EventWriteTransfer
0x14000b1c3  mov     rcx, [rbp+57h+Overlapped.hEvent]; hObject
0x14000b1c7  test    rcx, rcx
0x14000b1ca  jz      short loc_14000B1D2
0x14000b1cc  call    cs:__imp_CloseHandle
0x14000b1d2  test    ebx, ebx
0x14000b1d4  jnz     short loc_14000B1DF
0x14000b1d6  mov     ecx, r14d; dwErrCode
0x14000b1d9  call    cs:__imp_SetLastError
0x14000b1df  lea     r11, [rsp+0C0h+var_10]
0x14000b1e7  mov     eax, ebx
0x14000b1e9  mov     rbx, [r11+28h]
0x14000b1ed  mov     rsi, [r11+30h]
0x14000b1f1  mov     rsp, r11
0x14000b1f4  pop     r14
0x14000b1f6  pop     rdi
0x14000b1f7  pop     rbp
0x14000b1f8  retn
```
