# CreateNormalProcess(_ISOLATION_CONTAINER *,ushort const *,_ISO_ISOLATION_OPTIONS *,_ISO_PROCESS_CREATION_OPTIONS *,_PROCESS_INFORMATION *)

- ea: `0x180019c40`
- end: `0x180019d0b`
- name: `?CreateNormalProcess@@YAJPEAU_ISOLATION_CONTAINER@@PEBGPEAU_ISO_ISOLATION_OPTIONS@@PEAU_ISO_PROCESS_CREATION_OPTIONS@@PEAU_PROCESS_INFORMATION@@@Z`
- size: `203`
- prototype: `int(struct _ISOLATION_CONTAINER *, const unsigned __int16 *, struct _ISO_ISOLATION_OPTIONS *, struct _ISO_PROCESS_CREATION_OPTIONS *, struct _PROCESS_INFORMATION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a6d8`

## callees

- `0x180019c40`
- `0x180019d14`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x180019c77`
- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x180019c77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019cc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019cc8`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180019cbe`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180019cbe`

## pseudocode

```c
__int64 __fastcall CreateNormalProcess(
        struct _ISOLATION_CONTAINER *a1,
        const unsigned __int16 *a2,
        struct _ISO_ISOLATION_OPTIONS *a3,
        struct _ISO_PROCESS_CREATION_OPTIONS *a4,
        struct _PROCESS_INFORMATION *lpProcessInformation)
{
  signed int LastError; // eax
  unsigned int v7; // ebx
  wchar_t Destination[264]; // [rsp+50h] [rbp-228h] BYREF

  wcscpy_s(Destination, 0x104u, a2);
  if ( CreateProcessW(
         0,
         Destination,
         *((LPSECURITY_ATTRIBUTES *)a4 + 7),
         *((LPSECURITY_ATTRIBUTES *)a4 + 8),
         *((_DWORD *)a4 + 18),
         *((_DWORD *)a4 + 19) | 0x80000,
         *((LPVOID *)a4 + 10),
         *((LPCWSTR *)a4 + 11),
         (LPSTARTUPINFOW)((char *)a4 + 96),
         lpProcessInformation) )
  {
    return 0;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  IsolationApi::TelemetryHelper::LogCreateNormalProcessError(v7);
  return v7;
}

```

## disassembly

```asm
0x180019c40  mov     [rsp+arg_0], rbx
0x180019c45  push    rdi
0x180019c46  sub     rsp, 270h
0x180019c4d  mov     rax, cs:__security_cookie
0x180019c54  xor     rax, rsp
0x180019c57  mov     [rsp+278h+var_18], rax
0x180019c5f  mov     rbx, [rsp+278h+arg_20]
0x180019c67  lea     rcx, [rsp+278h+Destination]; Destination
0x180019c6c  mov     r8, rdx; Source
0x180019c6f  mov     rdi, r9
0x180019c72  mov     edx, 104h; SizeInWords
0x180019c77  call    cs:__imp_wcscpy_s
0x180019c7d  mov     ecx, [rdi+4Ch]
0x180019c80  lea     rax, [rdi+60h]
0x180019c84  mov     r9, [rdi+40h]; lpThreadAttributes
0x180019c88  lea     rdx, [rsp+278h+Destination]; lpCommandLine
0x180019c8d  mov     r8, [rdi+38h]; lpProcessAttributes
0x180019c91  bts     ecx, 13h
0x180019c95  mov     [rsp+278h+lpProcessInformation], rbx; lpProcessInformation
0x180019c9a  mov     [rsp+278h+lpStartupInfo], rax; lpStartupInfo
0x180019c9f  mov     rax, [rdi+58h]
0x180019ca3  mov     [rsp+278h+lpCurrentDirectory], rax; lpCurrentDirectory
0x180019ca8  mov     rax, [rdi+50h]
0x180019cac  mov     [rsp+278h+lpEnvironment], rax; lpEnvironment
0x180019cb1  mov     eax, [rdi+48h]
0x180019cb4  mov     [rsp+278h+dwCreationFlags], ecx; dwCreationFlags
0x180019cb8  xor     ecx, ecx; lpApplicationName
0x180019cba  mov     [rsp+278h+bInheritHandles], eax; bInheritHandles
0x180019cbe  call    cs:__imp_CreateProcessW
0x180019cc4  test    eax, eax
0x180019cc6  jnz     short loc_180019CE8
0x180019cc8  call    cs:__imp_GetLastError
0x180019cce  mov     ebx, eax
0x180019cd0  test    eax, eax
0x180019cd2  jle     short loc_180019CDD
0x180019cd4  movzx   ebx, ax
0x180019cd7  or      ebx, 80070000h
0x180019cdd  mov     ecx, ebx; int
0x180019cdf  call    ?LogCreateNormalProcessError@TelemetryHelper@IsolationApi@@SAXJ@Z; IsolationApi::TelemetryHelper::LogCreateNormalProcessError(long)
0x180019ce4  mov     eax, ebx
0x180019ce6  jmp     short loc_180019CEA
0x180019ce8  xor     eax, eax
0x180019cea  mov     rcx, [rsp+278h+var_18]
0x180019cf2  xor     rcx, rsp; StackCookie
0x180019cf5  call    __security_check_cookie
0x180019cfa  mov     rbx, [rsp+278h+arg_0]
0x180019d02  add     rsp, 270h
0x180019d09  pop     rdi
0x180019d0a  retn
```
