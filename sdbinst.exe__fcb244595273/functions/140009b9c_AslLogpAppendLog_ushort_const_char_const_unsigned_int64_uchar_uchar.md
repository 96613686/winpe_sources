# AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)

- ea: `0x140009b9c`
- end: `0x140009cce`
- name: `?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z`
- size: `306`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const char *, DWORD, char, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140009e54`

## callees

- `0x14000164a`
- `0x14000167a`
- `0x140009b9c`
- `0x14000adb8`
- `0x14002e420`

## import_xrefs

- `KERNEL32!GetLocalTime` at `0x140009c25`
- `KERNEL32!GetLocalTime` at `0x140009c25`
- `KERNEL32!CreateFileW` at `0x140009bef`
- `KERNEL32!CreateFileW` at `0x140009bef`

## pseudocode

```c
__int64 __fastcall AslLogpAppendLog(const unsigned __int16 *a1, const char *a2, DWORD a3, char a4, unsigned __int8 a5)
{
  HANDLE FileW; // rdi
  unsigned int v8; // ebx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-30h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-28h] BYREF
  __int64 Buffer; // [rsp+58h] [rbp-18h] BYREF
  int v13; // [rsp+60h] [rbp-10h]
  char v14; // [rsp+64h] [rbp-Ch]

  NumberOfBytesWritten = 0;
  FileW = CreateFileW(a1, 4u, 1u, 0, 4u, a4 == 0 ? 0x80000000 : 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    return (unsigned int)-1073741790;
  }
  else
  {
    if ( a5 )
    {
      Buffer = 0;
      v13 = 0;
      v14 = 0;
      SystemTime = 0;
      GetLocalTime(&SystemTime);
      if ( (int)RtlStringCchPrintfA(
                  (char *)&Buffer,
                  0xDu,
                  "%02d:%02d:%02d.%03d",
                  SystemTime.wHour,
                  SystemTime.wMinute,
                  SystemTime.wSecond,
                  SystemTime.wMilliseconds) >= 0 )
        WriteFile_0(FileW, &Buffer, 0xDu, &NumberOfBytesWritten, 0);
    }
    v8 = !WriteFile_0(FileW, a2, a3, &NumberOfBytesWritten, 0) ? 0xC0000022 : 0;
    CloseHandle_0(FileW);
  }
  return v8;
}

```

## disassembly

```asm
0x140009b9c  mov     [rsp-18h+arg_18], rbx
0x140009ba1  push    rbp
0x140009ba2  push    rsi
0x140009ba3  push    rdi
0x140009ba4  mov     rbp, rsp
0x140009ba7  sub     rsp, 70h
0x140009bab  mov     rax, cs:__security_cookie
0x140009bb2  xor     rax, rsp
0x140009bb5  mov     [rbp+var_8], rax
0x140009bb9  neg     r9b
0x140009bbc  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x140009bc5  mov     rbx, rdx
0x140009bc8  mov     [rbp+NumberOfBytesWritten], 0
0x140009bcf  sbb     eax, eax
0x140009bd1  mov     edx, 4; dwDesiredAccess
0x140009bd6  not     eax
0x140009bd8  mov     rsi, r8
0x140009bdb  and     eax, 80000000h
0x140009be0  xor     r9d, r9d; lpSecurityAttributes
0x140009be3  mov     [rsp+70h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x140009be7  lea     r8d, [rdx-3]; dwShareMode
0x140009beb  mov     [rsp+70h+dwCreationDisposition], edx; dwCreationDisposition
0x140009bef  call    cs:__imp_CreateFileW
0x140009bf5  mov     rdi, rax
0x140009bf8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140009bfc  jnz     short loc_140009C08
0x140009bfe  mov     ebx, 0C0000022h
0x140009c03  jmp     loc_140009CB0
0x140009c08  cmp     [rbp+arg_20], 0
0x140009c0c  jz      short loc_140009C80
0x140009c0e  xor     eax, eax
0x140009c10  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x140009c14  xorps   xmm0, xmm0
0x140009c17  mov     [rbp+Buffer], rax
0x140009c1b  mov     [rbp+var_10], eax
0x140009c1e  mov     [rbp+var_C], al
0x140009c21  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x140009c25  call    cs:__imp_GetLocalTime
0x140009c2b  movzx   ecx, [rbp+SystemTime.wSecond]
0x140009c2f  lea     r8, a02d02d02d03d; "%02d:%02d:%02d.%03d"
0x140009c36  movzx   edx, [rbp+SystemTime.wMinute]
0x140009c3a  movzx   eax, [rbp+SystemTime.wMilliseconds]
0x140009c3e  movzx   r9d, [rbp+SystemTime.wHour]
0x140009c43  mov     dword ptr [rsp+70h+hTemplateFile], eax
0x140009c47  mov     [rsp+70h+dwFlagsAndAttributes], ecx
0x140009c4b  lea     rcx, [rbp+Buffer]; char *
0x140009c4f  mov     [rsp+70h+dwCreationDisposition], edx
0x140009c53  mov     edx, 0Dh; unsigned __int64
0x140009c58  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x140009c5d  test    eax, eax
0x140009c5f  js      short loc_140009C80
0x140009c61  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140009c65  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x140009c6e  mov     r8d, 0Dh; nNumberOfBytesToWrite
0x140009c74  lea     rdx, [rbp+Buffer]; lpBuffer
0x140009c78  mov     rcx, rdi; hFile
0x140009c7b  call    WriteFile_0
0x140009c80  mov     r8d, esi; nNumberOfBytesToWrite
0x140009c83  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x140009c8c  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140009c90  mov     rdx, rbx; lpBuffer
0x140009c93  mov     rcx, rdi; hFile
0x140009c96  call    WriteFile_0
0x140009c9b  neg     eax
0x140009c9d  mov     ebx, 0C0000022h
0x140009ca2  sbb     ecx, ecx
0x140009ca4  not     ecx
0x140009ca6  and     ebx, ecx
0x140009ca8  mov     rcx, rdi; hObject
0x140009cab  call    CloseHandle_0
0x140009cb0  mov     eax, ebx
0x140009cb2  mov     rcx, [rbp+var_8]
0x140009cb6  xor     rcx, rsp; StackCookie
0x140009cb9  call    __security_check_cookie
0x140009cbe  mov     rbx, [rsp+70h+arg_18]
0x140009cc6  add     rsp, 70h
0x140009cca  pop     rdi
0x140009ccb  pop     rsi
0x140009ccc  pop     rbp
0x140009ccd  retn
```
