# WusaLoadMessage(int,ushort * *,...)

- ea: `0x14000eb0c`
- end: `0x14000ec51`
- name: `?WusaLoadMessage@@YAJHPEAPEAGZZ`
- size: `325`
- prototype: `__int64(DWORD dwMessageId, unsigned __int16 **, ...)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f8f0`
- `0x14001150c`
- `0x140013a90`

## callees

- `0x14000e280`
- `0x14000eb0c`
- `0x140013490`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000eb41`
- `KERNEL32!GetModuleHandleW` at `0x14000eb41`
- `KERNEL32!LocalFree` at `0x14000ebf0`
- `KERNEL32!LocalFree` at `0x14000ec41`
- `KERNEL32!LocalFree` at `0x14000ebf0`
- `KERNEL32!LocalFree` at `0x14000ec41`
- `KERNEL32!GetLastError` at `0x14000eb81`
- `KERNEL32!GetLastError` at `0x14000eb81`
- `KERNEL32!FormatMessageW` at `0x14000eb6f`
- `KERNEL32!FormatMessageW` at `0x14000eb6f`
- `msvcrt!wcsrchr` at `0x14000ebca`
- `msvcrt!wcsrchr` at `0x14000ebca`

## pseudocode

```c
__int64 WusaLoadMessage(DWORD dwMessageId, unsigned __int16 **a2, ...)
{
  HMODULE ModuleHandleW; // rax
  DWORD v4; // eax
  signed int LastError; // eax
  signed int v6; // ebx
  wchar_t *v7; // rcx
  wchar_t *v8; // rax
  HLOCAL v9; // rdi
  WCHAR Buffer[4]; // [rsp+40h] [rbp-20h] BYREF
  va_list Arguments; // [rsp+48h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-10h] BYREF
  va_list va; // [rsp+90h] [rbp+30h] BYREF

  va_start(va, a2);
  *(_QWORD *)Buffer = 0;
  va_copy(Arguments, va);
  ModuleHandleW = GetModuleHandleW(0);
  v4 = FormatMessageW(0x900u, ModuleHandleW, dwMessageId, 0, Buffer, 0, &Arguments);
  Arguments = 0;
  if ( v4 )
  {
    v6 = 0;
    v8 = wcsrchr(*(const wchar_t **)Buffer, 0xDu);
    if ( v8 )
      *v8 = 0;
    *a2 = *(unsigned __int16 **)Buffer;
    v7 = 0;
    *(_QWORD *)Buffer = 0;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    WusaLogDebugEventA((__int64)L"WusaLoadMessage", 151, "Failed to get message text for id %u", dwMessageId);
    v7 = *(wchar_t **)Buffer;
  }
  if ( v7 )
  {
    LocalFree(v7);
    *(_QWORD *)Buffer = 0;
  }
  if ( v6 < 0 )
  {
    hMem = 0;
    WusaGetErrorMessage(v6, (unsigned __int16 **)&hMem);
    v9 = hMem;
    WusaLogDebugEventA((__int64)L"WusaLoadMessage", 170, "Exit with error code 0X%x (%ls)", v6, (const wchar_t *)hMem);
    if ( v9 )
      LocalFree(v9);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000eb0c  mov     [rsp-18h+arg_8], rdx
0x14000eb11  mov     [rsp-18h+arg_10], r8
0x14000eb16  mov     [rsp-18h+arg_18], r9
0x14000eb1b  push    rbp
0x14000eb1c  push    rbx
0x14000eb1d  push    rdi
0x14000eb1e  mov     rbp, rsp
0x14000eb21  sub     rsp, 60h
0x14000eb25  mov     edi, ecx
0x14000eb27  mov     [rbp+var_18], 0
0x14000eb2f  lea     rax, [rbp+arg_10]
0x14000eb33  mov     qword ptr [rbp+Buffer], 0
0x14000eb3b  xor     ecx, ecx; lpModuleName
0x14000eb3d  mov     [rbp+var_18], rax
0x14000eb41  call    cs:__imp_GetModuleHandleW
0x14000eb47  xor     r9d, r9d; dwLanguageId
0x14000eb4a  mov     r8d, edi; dwMessageId
0x14000eb4d  mov     rdx, rax; lpSource
0x14000eb50  mov     ecx, 900h; dwFlags
0x14000eb55  lea     rax, [rbp+var_18]
0x14000eb59  mov     [rsp+60h+Arguments], rax; Arguments
0x14000eb5e  lea     rax, [rbp+Buffer]
0x14000eb62  mov     [rsp+60h+nSize], 0; nSize
0x14000eb6a  mov     [rsp+60h+lpBuffer], rax; lpBuffer
0x14000eb6f  call    cs:__imp_FormatMessageW
0x14000eb75  mov     [rbp+var_18], 0
0x14000eb7d  test    eax, eax
0x14000eb7f  jnz     short loc_14000EBC1
0x14000eb81  call    cs:__imp_GetLastError
0x14000eb87  mov     ebx, eax
0x14000eb89  test    eax, eax
0x14000eb8b  jle     short loc_14000EB96
0x14000eb8d  movzx   ebx, ax
0x14000eb90  or      ebx, 80070000h
0x14000eb96  test    ebx, ebx
0x14000eb98  lea     r8, aFailedToGetMes_0; "Failed to get message text for id %u"
0x14000eb9f  mov     eax, 80004005h
0x14000eba4  lea     rcx, aWusaloadmessag; "WusaLoadMessage"
0x14000ebab  mov     r9d, edi
0x14000ebae  mov     edx, 97h
0x14000ebb3  cmovns  ebx, eax
0x14000ebb6  call    WusaLogDebugEventA
0x14000ebbb  mov     rcx, qword ptr [rbp+Buffer]
0x14000ebbf  jmp     short loc_14000EBEB
0x14000ebc1  mov     rcx, qword ptr [rbp+Buffer]; Str
0x14000ebc5  xor     ebx, ebx
0x14000ebc7  lea     edx, [rbx+0Dh]; Ch
0x14000ebca  call    cs:__imp_wcsrchr
0x14000ebd0  test    rax, rax
0x14000ebd3  jz      short loc_14000EBDA
0x14000ebd5  xor     ecx, ecx
0x14000ebd7  mov     [rax], cx
0x14000ebda  mov     rcx, qword ptr [rbp+Buffer]
0x14000ebde  mov     rax, [rbp+arg_8]
0x14000ebe2  mov     [rax], rcx
0x14000ebe5  xor     ecx, ecx; hMem
0x14000ebe7  mov     qword ptr [rbp+Buffer], rcx
0x14000ebeb  test    rcx, rcx
0x14000ebee  jz      short loc_14000EBFE
0x14000ebf0  call    cs:__imp_LocalFree
0x14000ebf6  mov     qword ptr [rbp+Buffer], 0
0x14000ebfe  test    ebx, ebx
0x14000ec00  jns     short loc_14000EC47
0x14000ec02  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x14000ec06  mov     [rbp+hMem], 0
0x14000ec0e  mov     ecx, ebx; dwMessageId
0x14000ec10  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x14000ec15  mov     rdi, [rbp+hMem]
0x14000ec19  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x14000ec20  mov     r9d, ebx
0x14000ec23  mov     [rsp+60h+lpBuffer], rdi
0x14000ec28  mov     edx, 0AAh
0x14000ec2d  lea     rcx, aWusaloadmessag; "WusaLoadMessage"
0x14000ec34  call    WusaLogDebugEventA
0x14000ec39  test    rdi, rdi
0x14000ec3c  jz      short loc_14000EC47
0x14000ec3e  mov     rcx, rdi; hMem
0x14000ec41  call    cs:__imp_LocalFree
0x14000ec47  mov     eax, ebx
0x14000ec49  add     rsp, 60h
0x14000ec4d  pop     rdi
0x14000ec4e  pop     rbx
0x14000ec4f  pop     rbp
0x14000ec50  retn
```
