# SetStorageCardWriteBackCache(ushort const *,_GUID,bool)

- ea: `0x18001bb98`
- end: `0x18001bd8f`
- name: `?SetStorageCardWriteBackCache@@YAJPEBGU_GUID@@_N@Z`
- size: `503`
- prototype: `__int64 __fastcall(const unsigned __int16 *, GUID *rguid, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027858`
- `0x18002a3f8`

## callees

- `0x18000d030`
- `0x18000ddb0`
- `0x18001a0b8`
- `0x18001a70c`
- `0x18001b6cc`
- `0x18001b7d4`
- `0x18001bb98`
- `0x18003e95c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bd4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bd5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bd4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bd5c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001bc94`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001bceb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001bc94`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001bceb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bd0f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bd0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bd3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bd3e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001bc33`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001bc33`

## string_xrefs

- `0x18001bc00`: `WriteCachingSet`

## pseudocode

```c
__int64 __fastcall SetStorageCardWriteBackCache(const unsigned __int16 *a1, GUID *rguid)
{
  __int64 v4; // rdi
  __int64 v5; // rsi
  int v6; // ebx
  int LastHr; // eax
  void *v8; // rax
  __int64 OutBuffer; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR sz[264]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = -1;
  BytesReturned = 0;
  hKey = 0;
  v5 = -1;
  memset_0(sz, 0, 0x208u);
  OutBuffer = 8;
  v6 = OpenStorageRegKey(HKEY_LOCAL_MACHINE, (wchar_t *)L"WriteCachingSet", &hKey);
  if ( v6 >= 0 )
  {
    if ( StringFromGUID2(rguid, sz, 260) <= 0 )
    {
      v6 = -2147024809;
      goto LABEL_15;
    }
    v4 = (__int64)OpenDiskHandle(a1);
    if ( v4 == -1 )
      goto LABEL_5;
    if ( !DeviceIoControl((HANDLE)v4, 0x2D0C14u, 0, 0, &OutBuffer, 8u, &BytesReturned, 0) )
      goto LABEL_7;
    if ( (BYTE4(OutBuffer) || BYTE6(OutBuffer)) && !HIBYTE(OutBuffer) )
    {
      HIBYTE(OutBuffer) = 1;
      if ( DeviceIoControl((HANDLE)v4, 0x2DCC18u, &OutBuffer, 8u, 0, 0, &BytesReturned, 0) )
      {
        RegSetValueExW(hKey, sz, 0, 0, 0, 0);
        v8 = OpenVolumeHandle(a1);
        v5 = (__int64)v8;
        if ( v8 == (void *)-1LL )
        {
LABEL_5:
          v6 = -2147467259;
          goto LABEL_15;
        }
        LastHr = DismountVolume(v8);
        goto LABEL_14;
      }
LABEL_7:
      LastHr = GetLastHr();
LABEL_14:
      v6 = LastHr;
    }
  }
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 != -1 )
    CloseHandle((HANDLE)v4);
  if ( v5 != -1 )
    CloseHandle((HANDLE)v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001bb98  mov     [rsp-8+arg_10], rbx
0x18001bb9d  mov     [rsp-8+arg_18], rsi
0x18001bba2  push    rbp
0x18001bba3  push    rdi
0x18001bba4  push    r12
0x18001bba6  push    r14
0x18001bba8  push    r15
0x18001bbaa  lea     rbp, [rsp-180h]
0x18001bbb2  sub     rsp, 280h
0x18001bbb9  mov     rax, cs:__security_cookie
0x18001bbc0  xor     rax, rsp
0x18001bbc3  mov     [rbp+1A0h+var_30], rax
0x18001bbca  mov     r15, rdx
0x18001bbcd  mov     r14, rcx
0x18001bbd0  xor     r12d, r12d
0x18001bbd3  lea     rcx, [rsp+2A0h+sz]; void *
0x18001bbd8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001bbdc  mov     [rsp+2A0h+BytesReturned], r12d
0x18001bbe1  xor     edx, edx; Val
0x18001bbe3  mov     [rsp+2A0h+hKey], r12
0x18001bbe8  mov     r8d, 208h; Size
0x18001bbee  or      rsi, rdi
0x18001bbf1  call    memset_0
0x18001bbf6  mov     [rsp+2A0h+OutBuffer], r12
0x18001bbfb  lea     r8, [rsp+2A0h+hKey]; phkResult
0x18001bc00  lea     rdx, aWritecachingse; "WriteCachingSet"
0x18001bc07  mov     dword ptr [rsp+2A0h+OutBuffer], 8
0x18001bc0f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001bc16  call    ?OpenStorageRegKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z; OpenStorageRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18001bc1b  mov     ebx, eax
0x18001bc1d  test    eax, eax
0x18001bc1f  js      loc_18001BD34
0x18001bc25  mov     r8d, 104h; cchMax
0x18001bc2b  lea     rdx, [rsp+2A0h+sz]; lpsz
0x18001bc30  mov     rcx, r15; rguid
0x18001bc33  call    cs:__imp_StringFromGUID2
0x18001bc39  test    eax, eax
0x18001bc3b  jg      short loc_18001BC47
0x18001bc3d  mov     ebx, 80070057h
0x18001bc42  jmp     loc_18001BD34
0x18001bc47  mov     rcx, r14; unsigned __int16 *
0x18001bc4a  call    ?OpenDiskHandle@@YAPEAXPEBG@Z; OpenDiskHandle(ushort const *)
0x18001bc4f  mov     rdi, rax
0x18001bc52  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bc56  jnz     short loc_18001BC62
0x18001bc58  mov     ebx, 80004005h
0x18001bc5d  jmp     loc_18001BD34
0x18001bc62  mov     [rsp+2A0h+lpOverlapped], r12; lpOverlapped
0x18001bc67  lea     rax, [rsp+2A0h+BytesReturned]
0x18001bc6c  mov     [rsp+2A0h+lpBytesReturned], rax; lpBytesReturned
0x18001bc71  mov     r15d, 8
0x18001bc77  lea     rax, [rsp+2A0h+OutBuffer]
0x18001bc7c  mov     [rsp+2A0h+nOutBufferSize], r15d; nOutBufferSize
0x18001bc81  xor     r9d, r9d; nInBufferSize
0x18001bc84  mov     [rsp+2A0h+lpOutBuffer], rax; lpOutBuffer
0x18001bc89  xor     r8d, r8d; lpInBuffer
0x18001bc8c  mov     edx, 2D0C14h; dwIoControlCode
0x18001bc91  mov     rcx, rdi; hDevice
0x18001bc94  call    cs:__imp_DeviceIoControl
0x18001bc9a  test    eax, eax
0x18001bc9c  jnz     short loc_18001BCA8
0x18001bc9e  call    ?GetLastHr@@YAJXZ; GetLastHr(void)
0x18001bca3  jmp     loc_18001BD32
0x18001bca8  cmp     byte ptr [rsp+2A0h+OutBuffer+4], r12b
0x18001bcad  jnz     short loc_18001BCB6
0x18001bcaf  cmp     byte ptr [rsp+2A0h+OutBuffer+6], r12b
0x18001bcb4  jz      short loc_18001BD34
0x18001bcb6  cmp     byte ptr [rsp+2A0h+OutBuffer+7], r12b
0x18001bcbb  jnz     short loc_18001BD34
0x18001bcbd  mov     [rsp+2A0h+lpOverlapped], r12; lpOverlapped
0x18001bcc2  lea     rax, [rsp+2A0h+BytesReturned]
0x18001bcc7  mov     [rsp+2A0h+lpBytesReturned], rax; lpBytesReturned
0x18001bccc  lea     r8, [rsp+2A0h+OutBuffer]; lpInBuffer
0x18001bcd1  mov     [rsp+2A0h+nOutBufferSize], r12d; nOutBufferSize
0x18001bcd6  mov     r9d, r15d; nInBufferSize
0x18001bcd9  mov     edx, 2DCC18h; dwIoControlCode
0x18001bcde  mov     [rsp+2A0h+lpOutBuffer], r12; lpOutBuffer
0x18001bce3  mov     rcx, rdi; hDevice
0x18001bce6  mov     byte ptr [rsp+2A0h+OutBuffer+7], 1
0x18001bceb  call    cs:__imp_DeviceIoControl
0x18001bcf1  test    eax, eax
0x18001bcf3  jz      short loc_18001BC9E
0x18001bcf5  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001bcfa  lea     rdx, [rsp+2A0h+sz]; lpValueName
0x18001bcff  mov     [rsp+2A0h+nOutBufferSize], r12d; cbData
0x18001bd04  xor     r9d, r9d; dwType
0x18001bd07  xor     r8d, r8d; Reserved
0x18001bd0a  mov     [rsp+2A0h+lpOutBuffer], r12; lpData
0x18001bd0f  call    cs:__imp_RegSetValueExW
0x18001bd15  mov     rcx, r14; unsigned __int16 *
0x18001bd18  call    ?OpenVolumeHandle@@YAPEAXPEBG@Z; OpenVolumeHandle(ushort const *)
0x18001bd1d  mov     rsi, rax
0x18001bd20  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bd24  jz      loc_18001BC58
0x18001bd2a  mov     rcx, rax; void *
0x18001bd2d  call    ?DismountVolume@@YAJPEAX@Z; DismountVolume(void *)
0x18001bd32  mov     ebx, eax
0x18001bd34  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001bd39  test    rcx, rcx
0x18001bd3c  jz      short loc_18001BD44
0x18001bd3e  call    cs:__imp_RegCloseKey
0x18001bd44  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001bd48  jz      short loc_18001BD53
0x18001bd4a  mov     rcx, rdi; hObject
0x18001bd4d  call    cs:__imp_CloseHandle
0x18001bd53  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001bd57  jz      short loc_18001BD62
0x18001bd59  mov     rcx, rsi; hObject
0x18001bd5c  call    cs:__imp_CloseHandle
0x18001bd62  mov     eax, ebx
0x18001bd64  mov     rcx, [rbp+1A0h+var_30]
0x18001bd6b  xor     rcx, rsp; StackCookie
0x18001bd6e  call    __security_check_cookie
0x18001bd73  lea     r11, [rsp+2A0h+var_20]
0x18001bd7b  mov     rbx, [r11+40h]
0x18001bd7f  mov     rsi, [r11+48h]
0x18001bd83  mov     rsp, r11
0x18001bd86  pop     r15
0x18001bd88  pop     r14
0x18001bd8a  pop     r12
0x18001bd8c  pop     rdi
0x18001bd8d  pop     rbp
0x18001bd8e  retn
```
