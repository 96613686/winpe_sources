# DvcInfoVolumePathConvert

- ea: `0x180060434`
- end: `0x180060535`
- name: `DvcInfoVolumePathConvert`
- size: `257`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, STRSAFE_LPWSTR pszDest)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18006039c`
- `0x18009eb8c`

## callees

- `0x18003bafc`
- `0x180060434`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtQueryObject` at `0x1800604d2`
- `ntdll!NtQueryObject` at `0x1800604d2`
- `ntdll!RtlNtStatusToDosError` at `0x1800604de`
- `ntdll!RtlNtStatusToDosError` at `0x1800604de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800604ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800604ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060508`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060508`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006049c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006049c`

## pseudocode

```c
__int64 __fastcall DvcInfoVolumePathConvert(LPCWSTR lpFileName, STRSAFE_LPWSTR pszDest)
{
  HANDLE FileW; // rdi
  ULONG v5; // ebx
  int Object; // eax
  HRESULT v7; // eax
  ULONG ReturnLength[4]; // [rsp+40h] [rbp-428h] BYREF
  _BYTE ObjectInformation[8]; // [rsp+50h] [rbp-418h] BYREF
  STRSAFE_LPCWSTR pszSrc; // [rsp+58h] [rbp-410h]

  ReturnLength[0] = 0;
  memset_0(ObjectInformation, 0, 0x400u);
  FileW = CreateFileW(lpFileName, 0x80u, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    Object = NtQueryObject(FileW, ObjectNameInformation, ObjectInformation, 0x3FEu, ReturnLength);
    if ( Object >= 0 )
    {
      v7 = StringCbCopyW(pszDest, 0x208u, pszSrc);
      if ( v7 >= 0 )
        v5 = 0;
      else
        v5 = (unsigned __int16)v7;
    }
    else
    {
      v5 = RtlNtStatusToDosError(Object);
    }
    CloseHandle(FileW);
  }
  return v5;
}

```

## disassembly

```asm
0x180060434  mov     [rsp+arg_10], rbx
0x180060439  mov     [rsp+arg_18], rsi
0x18006043e  push    rdi
0x18006043f  sub     rsp, 460h
0x180060446  mov     rax, cs:__security_cookie
0x18006044d  xor     rax, rsp
0x180060450  mov     [rsp+468h+var_18], rax
0x180060458  mov     rsi, rdx
0x18006045b  mov     [rsp+468h+ReturnLength], 0
0x180060463  mov     rbx, rcx
0x180060466  xor     edx, edx; Val
0x180060468  lea     rcx, [rsp+468h+ObjectInformation]; void *
0x18006046d  mov     r8d, 400h; Size
0x180060473  call    memset_0
0x180060478  mov     edx, 80h; dwDesiredAccess
0x18006047d  mov     [rsp+468h+hTemplateFile], 0; hTemplateFile
0x180060486  mov     [rsp+468h+dwFlagsAndAttributes], edx; dwFlagsAndAttributes
0x18006048a  xor     r9d, r9d; lpSecurityAttributes
0x18006048d  mov     rcx, rbx; lpFileName
0x180060490  mov     [rsp+468h+dwCreationDisposition], 3; dwCreationDisposition
0x180060498  lea     r8d, [rdx-79h]; dwShareMode
0x18006049c  call    cs:__imp_CreateFileW
0x1800604a2  mov     rdi, rax
0x1800604a5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800604a9  jnz     short loc_1800604B5
0x1800604ab  call    cs:__imp_GetLastError
0x1800604b1  mov     ebx, eax
0x1800604b3  jmp     short loc_18006050E
0x1800604b5  lea     rax, [rsp+468h+ReturnLength]
0x1800604ba  mov     r9d, 3FEh; ObjectInformationLength
0x1800604c0  lea     r8, [rsp+468h+ObjectInformation]; ObjectInformation
0x1800604c5  mov     qword ptr [rsp+468h+dwCreationDisposition], rax; ReturnLength
0x1800604ca  mov     edx, 1; ObjectInformationClass
0x1800604cf  mov     rcx, rdi; Handle
0x1800604d2  call    cs:__imp_NtQueryObject
0x1800604d8  test    eax, eax
0x1800604da  jns     short loc_1800604E8
0x1800604dc  mov     ecx, eax; Status
0x1800604de  call    cs:__imp_RtlNtStatusToDosError
0x1800604e4  mov     ebx, eax
0x1800604e6  jmp     short loc_180060505
0x1800604e8  mov     r8, [rsp+468h+pszSrc]; pszSrc
0x1800604ed  mov     edx, 208h; cbDest
0x1800604f2  mov     rcx, rsi; pszDest
0x1800604f5  call    StringCbCopyW
0x1800604fa  test    eax, eax
0x1800604fc  jns     short loc_180060503
0x1800604fe  movzx   ebx, ax
0x180060501  jmp     short loc_180060505
0x180060503  xor     ebx, ebx
0x180060505  mov     rcx, rdi; hObject
0x180060508  call    cs:__imp_CloseHandle
0x18006050e  mov     eax, ebx
0x180060510  mov     rcx, [rsp+468h+var_18]
0x180060518  xor     rcx, rsp; StackCookie
0x18006051b  call    __security_check_cookie
0x180060520  lea     r11, [rsp+468h+var_8]
0x180060528  mov     rbx, [r11+20h]
0x18006052c  mov     rsi, [r11+28h]
0x180060530  mov     rsp, r11
0x180060533  pop     rdi
0x180060534  retn
```
