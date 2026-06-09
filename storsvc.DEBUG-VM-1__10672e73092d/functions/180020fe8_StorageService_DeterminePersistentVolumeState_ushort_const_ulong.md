# StorageService::DeterminePersistentVolumeState(ushort const *,ulong *)

- ea: `0x180020fe8`
- end: `0x180021133`
- name: `?DeterminePersistentVolumeState@StorageService@@IEAAJPEBGPEAK@Z`
- size: `331`
- prototype: `int(StorageService *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180026bfc`

## callees

- `0x18000d030`
- `0x180012714`
- `0x180019210`
- `0x180019d4c`
- `0x180020fe8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210d0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800210c6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800210c6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180021031`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180021031`

## string_xrefs

- `0x180021051`: `onecore\drivers\storage\storsvc\service\storageservice.cpp`
- `0x1800210ef`: `onecore\drivers\storage\storsvc\service\storageservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StorageService::DeterminePersistentVolumeState(
        StorageService *this,
        const unsigned __int16 *a2,
        unsigned int *a3)
{
  HANDLE FileW; // rax
  const char *v5; // r9
  unsigned int v6; // ebx
  DWORD LastError; // eax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-68h]
  DWORD BytesReturned; // [rsp+40h] [rbp-48h] BYREF
  HANDLE v11; // [rsp+48h] [rbp-40h] BYREF
  __int128 InBuffer; // [rsp+50h] [rbp-38h] BYREF
  __int128 OutBuffer; // [rsp+60h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *a3 = 0;
  FileW = CreateFileW(a2, 0x180u, 3u, 0, 3u, 0x2000000u, 0);
  v11 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    BytesReturned = 0;
    OutBuffer = 0;
    InBuffer = 0;
    *(_QWORD *)((char *)&InBuffer + 4) = 0x100006000LL;
    if ( DeviceIoControl(FileW, 0x9023Cu, &InBuffer, 0x10u, &OutBuffer, 0x10u, &BytesReturned, 0) )
    {
      *a3 = OutBuffer;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError != 87 && LastError >= 2 )
      {
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xCC6,
               (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageservice.cpp",
               (const char *)LastError,
               dwCreationDisposition);
        goto LABEL_10;
      }
    }
    v6 = 0;
    goto LABEL_10;
  }
  v6 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)0xCB0,
         (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageservice.cpp",
         v5);
LABEL_10:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
  return v6;
}

```

## disassembly

```asm
0x180020fe8  push    rbx
0x180020fea  sub     rsp, 80h
0x180020ff1  mov     rax, cs:__security_cookie
0x180020ff8  xor     rax, rsp
0x180020ffb  mov     [rsp+88h+var_18], rax
0x180021000  mov     rbx, r8
0x180021003  mov     rcx, rdx; lpFileName
0x180021006  mov     dword ptr [r8], 0
0x18002100d  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x180021016  mov     [rsp+88h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002101e  mov     r8d, 3; dwShareMode
0x180021024  mov     [rsp+88h+dwCreationDisposition], r8d; dwCreationDisposition
0x180021029  xor     r9d, r9d; lpSecurityAttributes
0x18002102c  mov     edx, 180h; dwDesiredAccess
0x180021031  call    cs:__imp_CreateFileW
0x180021037  mov     [rsp+88h+var_40], rax
0x18002103c  lea     rcx, [rax+1]
0x180021040  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180021047  jnz     short loc_180021069
0x180021049  mov     rcx, [rsp+88h]; this
0x180021051  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180021058  mov     edx, 0CB0h; void *
0x18002105d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021062  mov     ebx, eax
0x180021064  jmp     loc_180021111
0x180021069  mov     [rsp+88h+BytesReturned], 0
0x180021071  xorps   xmm0, xmm0
0x180021074  movups  [rsp+88h+OutBuffer], xmm0
0x180021079  xorps   xmm1, xmm1
0x18002107c  movups  [rsp+88h+InBuffer], xmm1
0x180021081  mov     dword ptr [rsp+88h+InBuffer+4], 6000h
0x180021089  mov     dword ptr [rsp+88h+InBuffer+8], 1
0x180021091  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x18002109a  lea     rcx, [rsp+88h+BytesReturned]
0x18002109f  mov     [rsp+88h+hTemplateFile], rcx; lpBytesReturned
0x1800210a4  mov     r9d, 10h; nInBufferSize
0x1800210aa  mov     [rsp+88h+dwFlagsAndAttributes], r9d; nOutBufferSize
0x1800210af  lea     rcx, [rsp+88h+OutBuffer]
0x1800210b4  mov     qword ptr [rsp+88h+dwCreationDisposition], rcx; unsigned int
0x1800210b9  lea     r8, [rsp+88h+InBuffer]; lpInBuffer
0x1800210be  mov     edx, 9023Ch; dwIoControlCode
0x1800210c3  mov     rcx, rax; hDevice
0x1800210c6  call    cs:__imp_DeviceIoControl
0x1800210cc  test    eax, eax
0x1800210ce  jnz     short loc_180021109
0x1800210d0  call    cs:__imp_GetLastError
0x1800210d6  cmp     eax, 57h ; 'W'
0x1800210d9  jz      short loc_180021107
0x1800210db  cmp     eax, 1
0x1800210de  jz      short loc_180021107
0x1800210e0  test    eax, eax
0x1800210e2  jz      short loc_180021105
0x1800210e4  mov     rcx, [rsp+88h]; this
0x1800210ec  mov     r9d, eax; char *
0x1800210ef  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\storage\\storsvc\\ser"...
0x1800210f6  mov     edx, 0CC6h; void *
0x1800210fb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180021100  nop
0x180021101  mov     ebx, eax
0x180021103  jmp     short loc_180021111
0x180021105  jmp     short loc_18002110F
0x180021107  jmp     short loc_18002110F
0x180021109  mov     eax, dword ptr [rsp+88h+OutBuffer]
0x18002110d  mov     [rbx], eax
0x18002110f  xor     ebx, ebx
0x180021111  lea     rcx, [rsp+88h+var_40]
0x180021116  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002111b  mov     eax, ebx
0x18002111d  mov     rcx, [rsp+88h+var_18]
0x180021122  xor     rcx, rsp; StackCookie
0x180021125  call    __security_check_cookie
0x18002112a  add     rsp, 80h
0x180021131  pop     rbx
0x180021132  retn
```
