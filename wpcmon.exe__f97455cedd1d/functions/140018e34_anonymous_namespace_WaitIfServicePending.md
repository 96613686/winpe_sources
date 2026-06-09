# _anonymous_namespace_::WaitIfServicePending

- ea: `0x140018e34`
- end: `0x140019010`
- name: `_anonymous_namespace_::WaitIfServicePending`
- size: `476`
- prototype: `__int64 __fastcall(SC_HANDLE hService, LPBYTE lpBuffer)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x14001797c`

## callees

- `0x140005530`
- `0x140006338`
- `0x140018e34`
- `0x14001f6b4`
- `0x140060f58`

## import_xrefs

- `ADVAPI32!QueryServiceStatusEx` at `0x140018f56`
- `ADVAPI32!QueryServiceStatusEx` at `0x140018f56`
- `KERNEL32!SleepEx` at `0x140018f2f`
- `KERNEL32!SleepEx` at `0x140018f2f`
- `KERNEL32!GetTickCount` at `0x140018e6c`
- `KERNEL32!GetTickCount` at `0x140018f65`
- `KERNEL32!GetTickCount` at `0x140018f73`
- `KERNEL32!GetTickCount` at `0x140018e6c`
- `KERNEL32!GetTickCount` at `0x140018f65`
- `KERNEL32!GetTickCount` at `0x140018f73`
- `KERNEL32!GetLastError` at `0x140018fb3`
- `KERNEL32!GetLastError` at `0x140018fb3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall anonymous_namespace_::WaitIfServicePending(SC_HANDLE hService, BYTE *lpBuffer, int a3)
{
  DWORD TickCount; // r14d
  unsigned int i; // ebp
  __int64 v8; // rcx
  unsigned int v9; // edi
  signed int LastError; // eax
  unsigned int v11; // ebx
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-68h] BYREF
  _BYTE pExceptionObject[8]; // [rsp+38h] [rbp-60h] BYREF
  _QWORD v14[4]; // [rsp+40h] [rbp-58h] BYREF

  if ( *((_DWORD *)lpBuffer + 1) == a3 )
  {
    TickCount = GetTickCount();
    for ( i = *((_DWORD *)lpBuffer + 5); *((_DWORD *)lpBuffer + 1) == a3; i = *((_DWORD *)lpBuffer + 5) )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          10,
          &WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids,
          *((unsigned int *)lpBuffer + 6));
        v8 = WPP_GLOBAL_Control;
      }
      v9 = *((_DWORD *)lpBuffer + 6);
      if ( v9 <= 0x2710 )
      {
        if ( v9 < 0x3E8 )
          v9 = 1000;
      }
      else
      {
        v9 = 10000;
      }
      if ( (_UNKNOWN *)v8 != &WPP_GLOBAL_Control && (*(_BYTE *)(v8 + 28) & 8) != 0 )
        WPP_SF_d(*(_QWORD *)(v8 + 16), 11, &WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids, v9);
      v14[0] = 10000LL * v9;
      v14[1] = v14;
      SleepEx(v14[0] / 0x2710uLL, 1);
      pcbBytesNeeded = 0;
      if ( !QueryServiceStatusEx(hService, SC_STATUS_PROCESS_INFO, lpBuffer, 0x24u, &pcbBytesNeeded) )
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, &WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids, v11);
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v11);
        throw (ErrorCodeException *)pExceptionObject;
      }
      if ( *((_DWORD *)lpBuffer + 5) <= i && GetTickCount() - TickCount > *((_DWORD *)lpBuffer + 6) )
        break;
      TickCount = GetTickCount();
    }
  }
}

```

## disassembly

```asm
0x140018e34  mov     [rsp+arg_10], rbx
0x140018e39  mov     [rsp+arg_18], rbp
0x140018e3e  push    rsi
0x140018e3f  push    rdi
0x140018e40  push    r12
0x140018e42  push    r14
0x140018e44  push    r15
0x140018e46  sub     rsp, 70h
0x140018e4a  mov     rax, cs:__security_cookie
0x140018e51  xor     rax, rsp
0x140018e54  mov     [rsp+98h+var_38], rax
0x140018e59  mov     esi, r8d
0x140018e5c  mov     rbx, rdx
0x140018e5f  mov     r15, rcx
0x140018e62  cmp     [rdx+4], r8d
0x140018e66  jnz     loc_140018F8D
0x140018e6c  call    cs:__imp_GetTickCount
0x140018e72  mov     r14d, eax
0x140018e75  mov     ebp, [rbx+14h]
0x140018e78  cmp     [rbx+4], esi
0x140018e7b  jnz     loc_140018F8D
0x140018e81  lea     r12, WPP_GLOBAL_Control
0x140018e88  mov     eax, 3E8h
0x140018e8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140018e94  cmp     rcx, r12
0x140018e97  jz      short loc_140018EC4
0x140018e99  test    byte ptr [rcx+1Ch], 8
0x140018e9d  jz      short loc_140018EC4
0x140018e9f  mov     edx, 0Ah
0x140018ea4  mov     r9d, [rbx+18h]
0x140018ea8  lea     r8, WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids
0x140018eaf  mov     rcx, [rcx+10h]
0x140018eb3  call    WPP_SF_d
0x140018eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140018ebf  mov     eax, 3E8h
0x140018ec4  mov     edi, [rbx+18h]
0x140018ec7  cmp     edi, 2710h
0x140018ecd  jbe     short loc_140018ED6
0x140018ecf  mov     edi, 2710h
0x140018ed4  jmp     short loc_140018EDB
0x140018ed6  cmp     edi, eax
0x140018ed8  cmovb   edi, eax
0x140018edb  cmp     rcx, r12
0x140018ede  jz      short loc_140018EFE
0x140018ee0  test    byte ptr [rcx+1Ch], 8
0x140018ee4  jz      short loc_140018EFE
0x140018ee6  mov     edx, 0Bh
0x140018eeb  mov     r9d, edi
0x140018eee  lea     r8, WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids
0x140018ef5  mov     rcx, [rcx+10h]
0x140018ef9  call    WPP_SF_d
0x140018efe  mov     eax, edi
0x140018f00  imul    rcx, rax, 2710h
0x140018f07  mov     [rsp+98h+var_58], rcx
0x140018f0c  lea     rax, [rsp+98h+var_58]
0x140018f11  mov     [rsp+98h+var_50], rax
0x140018f16  mov     rax, 346DC5D63886594Bh
0x140018f20  mul     rcx
0x140018f23  mov     rcx, rdx
0x140018f26  shr     rcx, 0Bh; dwMilliseconds
0x140018f2a  mov     edx, 1; bAlertable
0x140018f2f  call    cs:__imp_SleepEx
0x140018f35  nop
0x140018f36  mov     [rsp+98h+var_68], 0
0x140018f3e  lea     rax, [rsp+98h+var_68]
0x140018f43  mov     [rsp+98h+pcbBytesNeeded], rax; pcbBytesNeeded
0x140018f48  mov     r9d, 24h ; '$'; cbBufSize
0x140018f4e  mov     r8, rbx; lpBuffer
0x140018f51  xor     edx, edx; InfoLevel
0x140018f53  mov     rcx, r15; hService
0x140018f56  call    cs:__imp_QueryServiceStatusEx
0x140018f5c  test    eax, eax
0x140018f5e  jz      short loc_140018FB3
0x140018f60  cmp     [rbx+14h], ebp
0x140018f63  ja      short loc_140018F73
0x140018f65  call    cs:__imp_GetTickCount
0x140018f6b  sub     eax, r14d
0x140018f6e  cmp     eax, [rbx+18h]
0x140018f71  ja      short loc_140018F8D
0x140018f73  call    cs:__imp_GetTickCount
0x140018f79  mov     r14d, eax
0x140018f7c  mov     ebp, [rbx+14h]
0x140018f7f  cmp     [rbx+4], esi
0x140018f82  mov     eax, 3E8h
0x140018f87  jz      loc_140018E8D
0x140018f8d  mov     rcx, [rsp+98h+var_38]
0x140018f92  xor     rcx, rsp; StackCookie
0x140018f95  call    __security_check_cookie
0x140018f9a  lea     r11, [rsp+98h+var_28]
0x140018f9f  mov     rbx, [r11+40h]
0x140018fa3  mov     rbp, [r11+48h]
0x140018fa7  mov     rsp, r11
0x140018faa  pop     r15
0x140018fac  pop     r14
0x140018fae  pop     r12
0x140018fb0  pop     rdi
0x140018fb1  pop     rsi
0x140018fb2  retn
0x140018fb3  call    cs:__imp_GetLastError
0x140018fb9  mov     ebx, eax
0x140018fbb  test    eax, eax
0x140018fbd  jle     short loc_140018FC8
0x140018fbf  movzx   ebx, ax
0x140018fc2  or      ebx, 80070000h
0x140018fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140018fcf  cmp     rcx, r12
0x140018fd2  jz      short loc_140018FF2
0x140018fd4  test    byte ptr [rcx+1Ch], 1
0x140018fd8  jz      short loc_140018FF2
0x140018fda  mov     edx, 0Ch
0x140018fdf  mov     r9d, ebx
0x140018fe2  lea     r8, WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids
0x140018fe9  mov     rcx, [rcx+10h]
0x140018fed  call    WPP_SF_d
0x140018ff2  mov     edx, ebx; int
0x140018ff4  lea     rcx, [rsp+98h+pExceptionObject]; this
0x140018ff9  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140018ffe  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140019005  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x14001900a  call    _CxxThrowException_0
```
