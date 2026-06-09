# UtilEnableCompression(ushort const *)

- ea: `0x180011720`
- end: `0x1800117f5`
- name: `?UtilEnableCompression@@YAJPEBG@Z`
- size: `213`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f834`

## callees

- `0x180005ddc`
- `0x18000983c`
- `0x180011720`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18001177c`
- `KERNEL32!CreateFileW` at `0x18001177c`
- `KERNEL32!DeviceIoControl` at `0x1800117d1`
- `KERNEL32!DeviceIoControl` at `0x1800117d1`

## pseudocode

```c
__int64 __fastcall UtilEnableCompression(const unsigned __int16 *a1)
{
  unsigned int v1; // ebx
  HANDLE FileW; // rax
  __int16 InBuffer; // [rsp+50h] [rbp+8h] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp+10h] BYREF
  HANDLE hDevice; // [rsp+60h] [rbp+18h] BYREF

  hDevice = 0;
  InBuffer = 1;
  BytesReturned = 0;
  if ( a1 )
  {
    v1 = -2147467259;
    FileW = CreateFileW(a1, 0xC0000000, 1u, 0, 3u, 0x2000000u, 0);
    tlx::unique_any<tlx::file_handle_traits>::reset(&hDevice, FileW);
    if ( (unsigned __int64)hDevice + 1 > 1 && DeviceIoControl(hDevice, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
      v1 = 0;
  }
  else
  {
    v1 = -2147024809;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hDevice);
  return v1;
}

```

## disassembly

```asm
0x180011720  mov     rax, rsp
0x180011723  mov     [rax+20h], rbx
0x180011727  push    rsi
0x180011728  sub     rsp, 40h
0x18001172c  mov     qword ptr [rax+18h], 0
0x180011734  mov     esi, 1
0x180011739  mov     [rax+8], si
0x18001173d  mov     dword ptr [rax+10h], 0
0x180011744  test    rcx, rcx
0x180011747  jnz     short loc_180011753
0x180011749  mov     ebx, 80070057h
0x18001174e  jmp     loc_1800117DE
0x180011753  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18001175c  xor     r9d, r9d; lpSecurityAttributes
0x18001175f  mov     [rsp+48h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180011767  mov     r8d, esi; dwShareMode
0x18001176a  mov     edx, 0C0000000h; dwDesiredAccess
0x18001176f  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180011777  mov     ebx, 80004005h
0x18001177c  call    cs:__imp_CreateFileW
0x180011782  mov     rdx, rax
0x180011785  lea     rcx, [rsp+48h+hDevice]
0x18001178a  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18001178f  mov     rcx, [rsp+48h+hDevice]; hDevice
0x180011794  lea     rax, [rcx+1]
0x180011798  cmp     rax, rsi
0x18001179b  jbe     short loc_1800117DE
0x18001179d  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1800117a6  lea     rax, [rsp+48h+BytesReturned]
0x1800117ab  mov     [rsp+48h+hTemplateFile], rax; lpBytesReturned
0x1800117b0  lea     r8, [rsp+48h+InBuffer]; lpInBuffer
0x1800117b5  mov     [rsp+48h+dwFlagsAndAttributes], 0; nOutBufferSize
0x1800117bd  mov     r9d, 2; nInBufferSize
0x1800117c3  mov     edx, 9C040h; dwIoControlCode
0x1800117c8  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOutBuffer
0x1800117d1  call    cs:__imp_DeviceIoControl
0x1800117d7  xor     ecx, ecx
0x1800117d9  test    eax, eax
0x1800117db  cmovnz  ebx, ecx
0x1800117de  lea     rcx, [rsp+48h+hDevice]
0x1800117e3  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800117e8  mov     eax, ebx
0x1800117ea  mov     rbx, [rsp+48h+arg_18]
0x1800117ef  add     rsp, 40h
0x1800117f3  pop     rsi
0x1800117f4  retn
```
