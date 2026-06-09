# ExtractResourceFile(ushort const *,ushort const *)

- ea: `0x14002ea9c`
- end: `0x14002eb7f`
- name: `?ExtractResourceFile@@YAKPEBG0@Z`
- size: `227`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14002ec00`

## callees

- `0x14002ea9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002eb52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002eb65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002eb52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002eb65`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14002ead4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14002ead4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14002eb48`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14002eb48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002eb5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002eb5d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x14002eb16`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x14002eb16`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x14002eb09`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x14002eb09`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x14002eb26`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x14002eb26`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x14002eaf6`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x14002eaf6`

## pseudocode

```c
__int64 __fastcall ExtractResourceFile(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  char *FileW; // rdi
  HRSRC ResourceW; // rax
  HRSRC v4; // rbx
  DWORD v5; // esi
  HGLOBAL Resource; // rax
  DWORD LastError; // ebx
  const void *v8; // rax
  const unsigned __int16 *NumberOfBytesWritten; // [rsp+50h] [rbp+8h] BYREF

  NumberOfBytesWritten = a1;
  FileW = (char *)CreateFileW(a2, 0x40000000u, 0, 0, 2u, 0x100u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    return GetLastError();
  }
  else
  {
    ResourceW = FindResourceW(0, L"XREPORT.XSL", (LPCWSTR)0x17);
    v4 = ResourceW;
    if ( !ResourceW
      || (v5 = SizeofResource(0, ResourceW), (Resource = LoadResource(0, v4)) == 0)
      || (LastError = 0, (v8 = LockResource(Resource)) != 0)
      && (LODWORD(NumberOfBytesWritten) = 0, !WriteFile(FileW, v8, v5, (LPDWORD)&NumberOfBytesWritten, 0)) )
    {
      LastError = GetLastError();
    }
    CloseHandle(FileW);
  }
  return LastError;
}

```

## disassembly

```asm
0x14002ea9c  mov     rax, rsp
0x14002ea9f  mov     [rax+10h], rbx
0x14002eaa3  mov     [rax+18h], rsi
0x14002eaa7  mov     [rax+8], rcx
0x14002eaab  push    rdi
0x14002eaac  sub     rsp, 40h
0x14002eab0  mov     qword ptr [rax-18h], 0
0x14002eab8  mov     rcx, rdx; lpFileName
0x14002eabb  mov     dword ptr [rax-20h], 100h
0x14002eac2  mov     edx, 40000000h; dwDesiredAccess
0x14002eac7  xor     r9d, r9d; lpSecurityAttributes
0x14002eaca  mov     dword ptr [rax-28h], 2
0x14002ead1  xor     r8d, r8d; dwShareMode
0x14002ead4  call    cs:__imp_CreateFileW
0x14002eada  mov     rdi, rax
0x14002eadd  lea     rcx, [rax-1]
0x14002eae1  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14002eae5  ja      short loc_14002EB65
0x14002eae7  mov     r8d, 17h; lpType
0x14002eaed  lea     rdx, Name; "XREPORT.XSL"
0x14002eaf4  xor     ecx, ecx; hModule
0x14002eaf6  call    cs:__imp_FindResourceW
0x14002eafc  mov     rbx, rax
0x14002eaff  test    rax, rax
0x14002eb02  jz      short loc_14002EB52
0x14002eb04  mov     rdx, rax; hResInfo
0x14002eb07  xor     ecx, ecx; hModule
0x14002eb09  call    cs:__imp_SizeofResource
0x14002eb0f  mov     rdx, rbx; hResInfo
0x14002eb12  xor     ecx, ecx; hModule
0x14002eb14  mov     esi, eax
0x14002eb16  call    cs:__imp_LoadResource
0x14002eb1c  test    rax, rax
0x14002eb1f  jz      short loc_14002EB52
0x14002eb21  mov     rcx, rax; hResData
0x14002eb24  xor     ebx, ebx
0x14002eb26  call    cs:__imp_LockResource
0x14002eb2c  test    rax, rax
0x14002eb2f  jz      short loc_14002EB5A
0x14002eb31  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14002eb36  mov     dword ptr [rsp+48h+NumberOfBytesWritten], ebx
0x14002eb3a  mov     r8d, esi; nNumberOfBytesToWrite
0x14002eb3d  mov     [rsp+48h+lpOverlapped], rbx; lpOverlapped
0x14002eb42  mov     rdx, rax; lpBuffer
0x14002eb45  mov     rcx, rdi; hFile
0x14002eb48  call    cs:__imp_WriteFile
0x14002eb4e  test    eax, eax
0x14002eb50  jnz     short loc_14002EB5A
0x14002eb52  call    cs:__imp_GetLastError
0x14002eb58  mov     ebx, eax
0x14002eb5a  mov     rcx, rdi; hObject
0x14002eb5d  call    cs:__imp_CloseHandle
0x14002eb63  jmp     short loc_14002EB6D
0x14002eb65  call    cs:__imp_GetLastError
0x14002eb6b  mov     ebx, eax
0x14002eb6d  mov     rsi, [rsp+48h+arg_10]
0x14002eb72  mov     eax, ebx
0x14002eb74  mov     rbx, [rsp+48h+arg_8]
0x14002eb79  add     rsp, 40h
0x14002eb7d  pop     rdi
0x14002eb7e  retn
```
