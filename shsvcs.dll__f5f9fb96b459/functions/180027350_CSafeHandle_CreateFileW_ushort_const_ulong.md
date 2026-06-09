# CSafeHandle::CreateFileW(ushort const *,ulong)

- ea: `0x180027350`
- end: `0x180027418`
- name: `?CreateFileW@CSafeHandle@@QEAAJPEBGK@Z`
- size: `200`
- prototype: `__int64 __fastcall(CSafeHandle *__hidden this, LPCWSTR lpFileName, DWORD dwDesiredAccess)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800179c0`
- `0x180019028`
- `0x1800285a4`

## callees

- `0x180018a74`
- `0x18002557c`
- `0x180027350`
- `0x180028238`
- `0x180028988`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800273a8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800273a8`

## pseudocode

```c
__int64 __fastcall CSafeHandle::CreateFileW(CSafeHandle *this, LPCWSTR lpFileName, DWORD dwDesiredAccess)
{
  int v6; // ecx
  int v7; // r8d
  int v8; // ebx
  _BYTE v10[16]; // [rsp+40h] [rbp-38h] BYREF

  if ( (Microsoft_Windows_ShsvcsEnableBits & 1) != 0 )
    McTemplateU0zq_EtwEventWriteTransfer(this, lpFileName, lpFileName, dwDesiredAccess);
  *(_QWORD *)this = CreateFileW(lpFileName, dwDesiredAccess, 3u, 0, 3u, 0, 0);
  if ( (Microsoft_Windows_ShsvcsEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v6,
      (unsigned int)ShellTraceId_HDSrv_CreateSafeFileHandle_Stop,
      v7,
      1,
      (__int64)v10);
  if ( *(_QWORD *)this == -1 )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    *((_QWORD *)this + 5) = *(_QWORD *)this;
    v8 = CRegisterNotificationOnHandle::Register((CSafeHandle *)((char *)this + 8));
    if ( v8 < 0 )
      CSafeHandle::_CloseHandle(this);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180027350  push    rbx
0x180027352  push    rsi
0x180027353  push    rdi
0x180027354  sub     rsp, 60h
0x180027358  mov     rax, cs:__security_cookie
0x18002735f  xor     rax, rsp
0x180027362  mov     [rsp+78h+var_28], rax
0x180027367  test    cs:Microsoft_Windows_ShsvcsEnableBits, 1
0x18002736e  mov     esi, r8d
0x180027371  mov     rbx, rdx
0x180027374  mov     rdi, rcx
0x180027377  jz      short loc_180027384
0x180027379  mov     r9d, r8d
0x18002737c  mov     r8, rdx
0x18002737f  call    McTemplateU0zq_EtwEventWriteTransfer
0x180027384  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18002738d  mov     r8d, 3; dwShareMode
0x180027393  mov     [rsp+78h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18002739b  xor     r9d, r9d; lpSecurityAttributes
0x18002739e  mov     edx, esi; dwDesiredAccess
0x1800273a0  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800273a5  mov     rcx, rbx; lpFileName
0x1800273a8  call    cs:__imp_CreateFileW
0x1800273ae  mov     [rdi], rax
0x1800273b1  test    cs:Microsoft_Windows_ShsvcsEnableBits, 1
0x1800273b8  jz      short loc_1800273D6
0x1800273ba  lea     rax, [rsp+78h+var_38]
0x1800273bf  mov     r9d, 1
0x1800273c5  lea     rdx, ShellTraceId_HDSrv_CreateSafeFileHandle_Stop
0x1800273cc  mov     qword ptr [rsp+78h+dwCreationDisposition], rax
0x1800273d1  call    McGenEventWrite_EtwEventWriteTransfer
0x1800273d6  mov     rax, [rdi]
0x1800273d9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800273dd  jz      short loc_1800273FC
0x1800273df  lea     rcx, [rdi+8]; this
0x1800273e3  mov     [rcx+20h], rax
0x1800273e7  call    ?Register@CRegisterNotificationOnHandle@@QEAAJXZ; CRegisterNotificationOnHandle::Register(void)
0x1800273ec  mov     ebx, eax
0x1800273ee  test    eax, eax
0x1800273f0  jns     short loc_180027401
0x1800273f2  mov     rcx, rdi; this
0x1800273f5  call    ?_CloseHandle@CSafeHandle@@AEAAJXZ; CSafeHandle::_CloseHandle(void)
0x1800273fa  jmp     short loc_180027401
0x1800273fc  mov     ebx, 80004005h
0x180027401  mov     eax, ebx
0x180027403  mov     rcx, [rsp+78h+var_28]
0x180027408  xor     rcx, rsp; StackCookie
0x18002740b  call    __security_check_cookie
0x180027410  add     rsp, 60h
0x180027414  pop     rdi
0x180027415  pop     rsi
0x180027416  pop     rbx
0x180027417  retn
```
