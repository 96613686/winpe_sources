# CreateNewProcessA

- ea: `0x18000ce3c`
- end: `0x18000cf68`
- name: `CreateNewProcessA`
- size: `300`
- prototype: `__int64 __usercall@<rax>(CWshExec *this@<rcx>, LPCWCH lpWideCharStr@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000d070`

## callees

- `0x1800059f8`
- `0x180006124`
- `0x180006ecc`
- `0x18000ce3c`
- `0x180010250`

## import_xrefs

- `KERNEL32!CreateProcessA` at `0x18000cf1f`
- `KERNEL32!CreateProcessA` at `0x18000cf1f`
- `KERNEL32!GetLastError` at `0x18000cf29`
- `KERNEL32!GetLastError` at `0x18000cf29`

## pseudocode

```c
__int64 __fastcall CreateNewProcessA(CWshExec *this, LPCWCH lpWideCharStr, void *a3, void *a4, void *a5)
{
  LPSTR lpCommandLine; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  struct _STARTUPINFOA StartupInfo; // [rsp+60h] [rbp-A0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+D0h] [rbp-30h] BYREF
  char v11[512]; // [rsp+F0h] [rbp-10h] BYREF

  StartupInfo.hStdInput = a4;
  StartupInfo.hStdOutput = a3;
  StartupInfo.hStdError = a5;
  lpCommandLine = 0;
  *(_QWORD *)&StartupInfo.cb = 104;
  memset(&StartupInfo.lpReserved, 0, 52);
  StartupInfo.dwFlags = 256;
  *(_QWORD *)&StartupInfo.wShowWindow = 0;
  StartupInfo.lpReserved2 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  Block = 0;
  if ( (int)PWSZToPSZ(lpWideCharStr, v11, 512, (char **)&Block, &lpCommandLine) >= 0 )
  {
    if ( CreateProcessA(0, lpCommandLine, 0, 0, 1, 0, 0, 0, &StartupInfo, &ProcessInformation) )
      CWshExec::SetProcessInfo(this, &ProcessInformation);
    else
      GetLastError();
  }
  if ( Block )
    operator delete(Block);
  return 0;
}

```

## disassembly

```asm
0x18000ce3c  push    rbp
0x18000ce3e  push    rbx
0x18000ce3f  push    rdi
0x18000ce40  lea     rbp, [rsp-200h]
0x18000ce48  sub     rsp, 300h
0x18000ce4f  mov     rax, cs:__security_cookie
0x18000ce56  xor     rax, rsp
0x18000ce59  mov     [rbp+210h+var_20], rax
0x18000ce60  xor     edi, edi
0x18000ce62  mov     [rbp+210h+StartupInfo.hStdInput], r9
0x18000ce66  mov     rbx, rcx
0x18000ce69  mov     [rbp+210h+StartupInfo.hStdOutput], r8
0x18000ce6d  mov     rcx, [rbp+210h+arg_20]
0x18000ce74  lea     r9, [rsp+310h+Block]; char **
0x18000ce79  xor     eax, eax
0x18000ce7b  mov     [rbp+210h+StartupInfo.hStdError], rcx
0x18000ce7f  mov     r10, rdx
0x18000ce82  mov     qword ptr [rbp+210h+ProcessInformation.dwProcessId], rax
0x18000ce86  xorps   xmm0, xmm0
0x18000ce89  mov     [rsp+310h+lpCommandLine], rdi
0x18000ce8e  lea     rax, [rsp+310h+lpCommandLine]
0x18000ce93  mov     qword ptr [rsp+310h+StartupInfo.cb], 68h ; 'h'
0x18000ce9c  mov     rcx, r10; lpWideCharStr
0x18000ce9f  mov     qword ptr [rsp+310h+bInheritHandles], rax; char **
0x18000cea4  mov     r8d, 200h; int
0x18000ceaa  mov     [rsp+310h+StartupInfo.lpReserved], rdi
0x18000ceaf  lea     rdx, [rbp+210h+var_220]; char *
0x18000ceb3  movdqa  xmmword ptr [rsp+310h+StartupInfo.lpDesktop], xmm0
0x18000ceb9  mov     qword ptr [rbp+210h+StartupInfo.dwX], rdi
0x18000cebd  mov     qword ptr [rbp+210h+StartupInfo.dwXSize], rdi
0x18000cec1  mov     qword ptr [rbp+210h+StartupInfo.dwXCountChars], rdi
0x18000cec5  mov     [rbp+210h+StartupInfo.dwFillAttribute], edi
0x18000cec8  mov     [rbp+210h+StartupInfo.dwFlags], 100h
0x18000cecf  mov     qword ptr [rbp+210h+StartupInfo.wShowWindow], rdi
0x18000ced3  mov     [rbp+210h+StartupInfo.lpReserved2], rdi
0x18000ced7  movups  xmmword ptr [rbp+210h+ProcessInformation.hProcess], xmm0
0x18000cedb  mov     [rsp+310h+Block], rdi
0x18000cee0  call    ?PWSZToPSZ@@YAJPEBGPEADJPEAPEAD2@Z; PWSZToPSZ(ushort const *,char *,long,char * *,char * *)
0x18000cee5  test    eax, eax
0x18000cee7  js      short loc_18000CF3D
0x18000cee9  mov     rdx, [rsp+310h+lpCommandLine]; lpCommandLine
0x18000ceee  lea     rax, [rbp+210h+ProcessInformation]
0x18000cef2  mov     [rsp+310h+lpProcessInformation], rax; lpProcessInformation
0x18000cef7  xor     r9d, r9d; lpThreadAttributes
0x18000cefa  lea     rax, [rsp+310h+StartupInfo]
0x18000ceff  xor     r8d, r8d; lpProcessAttributes
0x18000cf02  mov     [rsp+310h+lpStartupInfo], rax; lpStartupInfo
0x18000cf07  xor     ecx, ecx; lpApplicationName
0x18000cf09  mov     [rsp+310h+lpCurrentDirectory], rdi; lpCurrentDirectory
0x18000cf0e  mov     [rsp+310h+lpEnvironment], rdi; lpEnvironment
0x18000cf13  mov     [rsp+310h+dwCreationFlags], edi; dwCreationFlags
0x18000cf17  mov     [rsp+310h+bInheritHandles], 1; bInheritHandles
0x18000cf1f  call    cs:__imp_CreateProcessA
0x18000cf25  test    eax, eax
0x18000cf27  jnz     short loc_18000CF31
0x18000cf29  call    cs:__imp_GetLastError
0x18000cf2f  jmp     short loc_18000CF3D
0x18000cf31  lea     rdx, [rbp+210h+ProcessInformation]; struct _PROCESS_INFORMATION *
0x18000cf35  mov     rcx, rbx; this
0x18000cf38  call    ?SetProcessInfo@CWshExec@@QEAAJPEAU_PROCESS_INFORMATION@@@Z; CWshExec::SetProcessInfo(_PROCESS_INFORMATION *)
0x18000cf3d  mov     rcx, [rsp+310h+Block]; Block
0x18000cf42  test    rcx, rcx
0x18000cf45  jz      short loc_18000CF4C
0x18000cf47  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cf4c  xor     eax, eax
0x18000cf4e  mov     rcx, [rbp+210h+var_20]
0x18000cf55  xor     rcx, rsp; StackCookie
0x18000cf58  call    __security_check_cookie
0x18000cf5d  add     rsp, 300h
0x18000cf64  pop     rdi
0x18000cf65  pop     rbx
0x18000cf66  pop     rbp
0x18000cf67  retn
```
