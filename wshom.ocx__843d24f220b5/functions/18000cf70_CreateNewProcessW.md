# CreateNewProcessW

- ea: `0x18000cf70`
- end: `0x18000d04c`
- name: `CreateNewProcessW`
- size: `220`
- prototype: `__int64 __usercall@<rax>(CWshExec *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d070`

## callees

- `0x180006ecc`
- `0x18000cf70`

## import_xrefs

- `KERNEL32!CreateProcessW` at `0x18000d008`
- `KERNEL32!CreateProcessW` at `0x18000d008`
- `KERNEL32!GetLastError` at `0x18000d012`
- `KERNEL32!GetLastError` at `0x18000d012`

## pseudocode

```c
signed int __fastcall CreateNewProcessW(CWshExec *this, WCHAR *a2, void *a3, void *a4, void *a5)
{
  signed int result; // eax
  struct _STARTUPINFOW StartupInfo; // [rsp+50h] [rbp-41h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+C0h] [rbp+2Fh] BYREF

  StartupInfo.hStdError = a5;
  StartupInfo.hStdInput = a4;
  StartupInfo.hStdOutput = a3;
  *(_QWORD *)&StartupInfo.cb = 104;
  memset(&StartupInfo.lpReserved, 0, 52);
  StartupInfo.dwFlags = 256;
  *(_QWORD *)&StartupInfo.wShowWindow = 0;
  StartupInfo.lpReserved2 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( CreateProcessW(0, a2, 0, 0, 1, 0, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    result = CWshExec::SetProcessInfo(this, &ProcessInformation);
    if ( result >= 0 )
      return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000cf70  mov     [rsp-8+arg_0], rbx
0x18000cf75  mov     [rsp-8+arg_8], rdi
0x18000cf7a  push    rbp
0x18000cf7b  lea     rbp, [rsp-4Fh]
0x18000cf80  sub     rsp, 0E0h
0x18000cf87  mov     rax, [rbp+4Fh+arg_20]
0x18000cf8b  xor     edi, edi
0x18000cf8d  mov     [rbp+4Fh+StartupInfo.hStdError], rax
0x18000cf91  xorps   xmm0, xmm0
0x18000cf94  xor     eax, eax
0x18000cf96  mov     [rbp+4Fh+StartupInfo.hStdInput], r9
0x18000cf9a  mov     qword ptr [rbp+4Fh+ProcessInformation.dwProcessId], rax
0x18000cf9e  mov     rbx, rcx
0x18000cfa1  lea     rax, [rbp+4Fh+ProcessInformation]
0x18000cfa5  mov     [rbp+4Fh+StartupInfo.hStdOutput], r8
0x18000cfa9  mov     [rsp+0E0h+lpProcessInformation], rax; lpProcessInformation
0x18000cfae  xor     r9d, r9d; lpThreadAttributes
0x18000cfb1  lea     rax, [rbp+4Fh+StartupInfo]
0x18000cfb5  mov     qword ptr [rbp+4Fh+StartupInfo.cb], 68h ; 'h'
0x18000cfbd  mov     [rsp+0E0h+lpStartupInfo], rax; lpStartupInfo
0x18000cfc2  xor     r8d, r8d; lpProcessAttributes
0x18000cfc5  mov     [rsp+0E0h+lpCurrentDirectory], rdi; lpCurrentDirectory
0x18000cfca  xor     ecx, ecx; lpApplicationName
0x18000cfcc  mov     [rsp+0E0h+lpEnvironment], rdi; lpEnvironment
0x18000cfd1  mov     [rsp+0E0h+dwCreationFlags], edi; dwCreationFlags
0x18000cfd5  mov     [rsp+0E0h+bInheritHandles], 1; bInheritHandles
0x18000cfdd  mov     [rbp+4Fh+StartupInfo.lpReserved], rdi
0x18000cfe1  movdqa  xmmword ptr [rbp+4Fh+StartupInfo.lpDesktop], xmm0
0x18000cfe6  mov     qword ptr [rbp+4Fh+StartupInfo.dwX], rdi
0x18000cfea  mov     qword ptr [rbp+4Fh+StartupInfo.dwXSize], rdi
0x18000cfee  mov     qword ptr [rbp+4Fh+StartupInfo.dwXCountChars], rdi
0x18000cff2  mov     [rbp+4Fh+StartupInfo.dwFillAttribute], edi
0x18000cff5  mov     [rbp+4Fh+StartupInfo.dwFlags], 100h
0x18000cffc  mov     qword ptr [rbp+4Fh+StartupInfo.wShowWindow], rdi
0x18000d000  mov     [rbp+4Fh+StartupInfo.lpReserved2], rdi
0x18000d004  movups  xmmword ptr [rbp+4Fh+ProcessInformation.hProcess], xmm0
0x18000d008  call    cs:__imp_CreateProcessW
0x18000d00e  test    eax, eax
0x18000d010  jnz     short loc_18000D026
0x18000d012  call    cs:__imp_GetLastError
0x18000d018  test    eax, eax
0x18000d01a  jle     short loc_18000D037
0x18000d01c  movzx   eax, ax
0x18000d01f  or      eax, 80070000h
0x18000d024  jmp     short loc_18000D037
0x18000d026  lea     rdx, [rbp+4Fh+ProcessInformation]; struct _PROCESS_INFORMATION *
0x18000d02a  mov     rcx, rbx; this
0x18000d02d  call    ?SetProcessInfo@CWshExec@@QEAAJPEAU_PROCESS_INFORMATION@@@Z; CWshExec::SetProcessInfo(_PROCESS_INFORMATION *)
0x18000d032  test    eax, eax
0x18000d034  cmovns  eax, edi
0x18000d037  lea     r11, [rsp+0E0h+var_s0]
0x18000d03f  mov     rbx, [r11+10h]
0x18000d043  mov     rdi, [r11+18h]
0x18000d047  mov     rsp, r11
0x18000d04a  pop     rbp
0x18000d04b  retn
```
