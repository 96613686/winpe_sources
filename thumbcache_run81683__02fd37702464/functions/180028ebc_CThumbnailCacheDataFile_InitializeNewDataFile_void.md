# CThumbnailCacheDataFile::_InitializeNewDataFile(void *)

- ea: `0x180028ebc`
- end: `0x180028fb0`
- name: `?_InitializeNewDataFile@CThumbnailCacheDataFile@@AEAAJPEAX@Z`
- size: `244`
- prototype: `int(CThumbnailCacheDataFile *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028b90`

## callees

- `0x180028ebc`
- `0x1800346ec`
- `0x18003470c`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028f8b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028f8b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180028f07`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180028f07`

## string_xrefs

- `0x180028f1c`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbfile.cpp`

## pseudocode

```c
__int64 __fastcall CThumbnailCacheDataFile::_InitializeNewDataFile(CThumbnailCacheDataFile *this, void *a2)
{
  const char *v4; // r9
  __int64 v5; // rdx
  int v7; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-38h] BYREF
  _DWORD Buffer[6]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !*((_BYTE *)this + 16) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_QWORD *)this + 52) == -1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  NumberOfBytesWritten = 0;
  if ( SetFilePointer(a2, 0, 0, 0) == -1 )
  {
    v5 = 654;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v5,
             (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbfile.cpp",
             v4);
  }
  v7 = *((_DWORD *)this + 106);
  Buffer[3] = 0;
  Buffer[4] = 24;
  Buffer[5] = 24;
  Buffer[0] = 1296911683;
  Buffer[1] = 32;
  Buffer[2] = v7;
  if ( !WriteFile(a2, Buffer, 0x18u, &NumberOfBytesWritten, 0) )
  {
    v5 = 671;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v5,
             (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbfile.cpp",
             v4);
  }
  return 0;
}

```

## disassembly

```asm
0x180028ebc  mov     [rsp+arg_10], rbx
0x180028ec1  push    rdi
0x180028ec2  sub     rsp, 60h
0x180028ec6  mov     rax, cs:__security_cookie
0x180028ecd  xor     rax, rsp
0x180028ed0  mov     [rsp+68h+var_18], rax
0x180028ed5  cmp     byte ptr [rcx+10h], 0
0x180028ed9  mov     rdi, rdx
0x180028edc  mov     rbx, rcx
0x180028edf  jz      loc_180028F9F
0x180028ee5  cmp     qword ptr [rbx+1A0h], 0FFFFFFFFFFFFFFFFh
0x180028eed  jnz     short loc_180028EF4
0x180028eef  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "IsOpened()")
0x180028ef4  xor     r9d, r9d; dwMoveMethod
0x180028ef7  mov     [rsp+68h+NumberOfBytesWritten], 0
0x180028eff  xor     r8d, r8d; lpDistanceToMoveHigh
0x180028f02  xor     edx, edx; lDistanceToMove
0x180028f04  mov     rcx, rdi; hFile
0x180028f07  call    cs:__imp_SetFilePointer
0x180028f0d  cmp     eax, 0FFFFFFFFh
0x180028f10  jnz     short loc_180028F43
0x180028f12  mov     edx, 28Eh; void *
0x180028f17  mov     rcx, [rsp+68h]; this
0x180028f1c  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180028f23  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028f28  mov     rcx, [rsp+68h+var_18]
0x180028f2d  xor     rcx, rsp; StackCookie
0x180028f30  call    __security_check_cookie
0x180028f35  mov     rbx, [rsp+68h+arg_10]
0x180028f3d  add     rsp, 60h
0x180028f41  pop     rdi
0x180028f42  retn
0x180028f43  mov     eax, [rbx+1A8h]
0x180028f49  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180028f4e  mov     r8d, 18h; nNumberOfBytesToWrite
0x180028f54  mov     [rsp+68h+var_24], 0
0x180028f5c  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x180028f61  mov     [rsp+68h+var_20], r8d
0x180028f66  mov     rcx, rdi; hFile
0x180028f69  mov     [rsp+68h+var_1C], r8d
0x180028f6e  mov     [rsp+68h+Buffer], 4D4D4D43h
0x180028f76  mov     [rsp+68h+var_2C], 20h ; ' '
0x180028f7e  mov     [rsp+68h+var_28], eax
0x180028f82  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x180028f8b  call    cs:__imp_WriteFile
0x180028f91  test    eax, eax
0x180028f93  jnz     short loc_180028FA9
0x180028f95  mov     edx, 29Fh
0x180028f9a  jmp     loc_180028F17
0x180028f9f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "_mtxMaintainer.IsHeldLocally()")
0x180028fa4  jmp     loc_180028EE5
0x180028fa9  xor     eax, eax
0x180028fab  jmp     loc_180028F28
```
