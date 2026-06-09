# CPlugIn::CheckForWindowsSigning(void)

- ea: `0x180033e2c`
- end: `0x180033f56`
- name: `?CheckForWindowsSigning@CPlugIn@@QEAAJXZ`
- size: `298`
- prototype: `__int64 __fastcall(CPlugIn *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180040cf8`

## callees

- `0x180014894`
- `0x180033e2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033f43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033f43`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033e7f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033e7f`
- `api-ms-win-security-base-l1-2-0!GetCachedSigningLevel` at `0x180033eba`
- `api-ms-win-security-base-l1-2-0!GetCachedSigningLevel` at `0x180033f07`
- `api-ms-win-security-base-l1-2-0!GetCachedSigningLevel` at `0x180033eba`
- `api-ms-win-security-base-l1-2-0!GetCachedSigningLevel` at `0x180033f07`
- `api-ms-win-security-base-l1-2-0!SetCachedSigningLevel` at `0x180033edc`
- `api-ms-win-security-base-l1-2-0!SetCachedSigningLevel` at `0x180033edc`
- `ntdll!RtlNtStatusToDosError` at `0x180033f24`
- `ntdll!RtlNtStatusToDosError` at `0x180033f24`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPlugIn::CheckForWindowsSigning(CPlugIn *this)
{
  const WCHAR *v1; // rax
  HANDLE FileW; // rax
  signed int LastError; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int v7; // [rsp+50h] [rbp+10h] BYREF
  int v8; // [rsp+58h] [rbp+18h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp+20h] BYREF

  hObject = (HANDLE)-1LL;
  v8 = 0;
  v7 = 0;
  v1 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this);
  FileW = CreateFileW(v1, 0x80000000, 5u, 0, 3u, 0x80u, 0);
  hObject = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_2;
  if ( !(unsigned int)GetCachedSigningLevel(FileW, &v8, &v7, 0, 0, 0) || (v4 = v7, v7 < 0xC) )
  {
    if ( !(unsigned int)SetCachedSigningLevel(&hObject, 1, 5, hObject)
      || !(unsigned int)GetCachedSigningLevel(hObject, &v8, &v7, 0, 0, 0) )
    {
LABEL_2:
      LastError = GetLastError();
      goto LABEL_10;
    }
    v4 = v7;
  }
  v5 = 0;
  if ( v4 >= 0xC )
    goto LABEL_12;
  LastError = RtlNtStatusToDosError(-1073740760);
LABEL_10:
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  return v5;
}

```

## disassembly

```asm
0x180033e2c  mov     [rsp-8+arg_18], rbx
0x180033e31  push    rbp
0x180033e32  mov     rbp, rsp
0x180033e35  sub     rsp, 40h
0x180033e39  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x180033e41  mov     [rbp+arg_8], 0
0x180033e48  mov     [rbp+arg_0], 0
0x180033e4f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180033e54  xor     r9d, r9d; lpSecurityAttributes
0x180033e57  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x180033e60  mov     [rsp+40h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180033e68  mov     edx, 80000000h; dwDesiredAccess
0x180033e6d  mov     rcx, rax; lpFileName
0x180033e70  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x180033e78  lea     ebx, [r9+5]
0x180033e7c  mov     r8d, ebx; dwShareMode
0x180033e7f  call    cs:__imp_CreateFileW
0x180033e85  mov     [rbp+hObject], rax
0x180033e89  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180033e8d  jnz     short loc_180033E9A
0x180033e8f  call    cs:__imp_GetLastError
0x180033e95  jmp     loc_180033F2A
0x180033e9a  mov     qword ptr [rsp+40h+dwFlagsAndAttributes], 0
0x180033ea3  lea     r8, [rbp+arg_0]
0x180033ea7  xor     r9d, r9d
0x180033eaa  mov     qword ptr [rsp+40h+dwCreationDisposition], 0
0x180033eb3  lea     rdx, [rbp+arg_8]
0x180033eb7  mov     rcx, rax
0x180033eba  call    cs:__imp_GetCachedSigningLevel
0x180033ec0  test    eax, eax
0x180033ec2  jz      short loc_180033ECC
0x180033ec4  mov     eax, [rbp+arg_0]
0x180033ec7  cmp     eax, 0Ch
0x180033eca  jnb     short loc_180033F18
0x180033ecc  mov     r9, [rbp+hObject]
0x180033ed0  lea     rcx, [rbp+hObject]
0x180033ed4  mov     r8d, ebx
0x180033ed7  mov     edx, 1
0x180033edc  call    cs:__imp_SetCachedSigningLevel
0x180033ee2  test    eax, eax
0x180033ee4  jz      short loc_180033E8F
0x180033ee6  mov     rcx, [rbp+hObject]
0x180033eea  lea     r8, [rbp+arg_0]
0x180033eee  mov     qword ptr [rsp+40h+dwFlagsAndAttributes], 0
0x180033ef7  lea     rdx, [rbp+arg_8]
0x180033efb  xor     r9d, r9d
0x180033efe  mov     qword ptr [rsp+40h+dwCreationDisposition], 0
0x180033f07  call    cs:__imp_GetCachedSigningLevel
0x180033f0d  test    eax, eax
0x180033f0f  jz      loc_180033E8F
0x180033f15  mov     eax, [rbp+arg_0]
0x180033f18  xor     ebx, ebx
0x180033f1a  cmp     eax, 0Ch
0x180033f1d  jnb     short loc_180033F39
0x180033f1f  mov     ecx, 0C0000428h; Status
0x180033f24  call    cs:__imp_RtlNtStatusToDosError
0x180033f2a  mov     ebx, eax
0x180033f2c  test    eax, eax
0x180033f2e  jle     short loc_180033F39
0x180033f30  movzx   ebx, ax
0x180033f33  or      ebx, 80070000h
0x180033f39  mov     rcx, [rbp+hObject]; hObject
0x180033f3d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180033f41  jz      short loc_180033F49
0x180033f43  call    cs:__imp_CloseHandle
0x180033f49  mov     eax, ebx
0x180033f4b  mov     rbx, [rsp+40h+arg_18]
0x180033f50  add     rsp, 40h
0x180033f54  pop     rbp
0x180033f55  retn
```
