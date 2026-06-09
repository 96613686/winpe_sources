# CurrentThread::GetToken(ulong)

- ea: `0x140085230`
- end: `0x14008531f`
- name: `?GetToken@CurrentThread@@YA?AVToken@@K@Z`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140082fe8`

## callees

- `0x140006338`
- `0x14001f6b4`
- `0x140060f58`
- `0x140080ef8`
- `0x140085230`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x140085276`
- `ADVAPI32!OpenProcessToken` at `0x140085276`
- `ADVAPI32!OpenThreadToken` at `0x140085259`
- `ADVAPI32!OpenThreadToken` at `0x140085259`
- `KERNEL32!GetCurrentProcess` at `0x140085263`
- `KERNEL32!GetCurrentProcess` at `0x140085263`
- `KERNEL32!GetCurrentThread` at `0x140085242`
- `KERNEL32!GetCurrentThread` at `0x140085242`
- `KERNEL32!CloseHandle` at `0x1400852ac`
- `KERNEL32!CloseHandle` at `0x1400852ac`
- `KERNEL32!GetLastError` at `0x1400852bb`
- `KERNEL32!GetLastError` at `0x1400852bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall CurrentThread::GetToken(_QWORD *a1)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  _BYTE pExceptionObject[48]; // [rsp+28h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+18h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp+20h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_921fc3043960359be1fe4e548f998926_Traceguids, v6);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v6);
      throw (ErrorCodeException *)pExceptionObject;
    }
  }
  hObject = TokenHandle;
  Token::Token(a1, (__int64 *)&hObject);
  if ( hObject && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return a1;
}

```

## disassembly

```asm
0x140085230  push    rbx
0x140085232  sub     rsp, 50h
0x140085236  mov     rbx, rcx
0x140085239  mov     [rsp+58h+TokenHandle], 0
0x140085242  call    cs:__imp_GetCurrentThread
0x140085248  mov     rcx, rax; ThreadHandle
0x14008524b  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x140085250  mov     edx, 8; DesiredAccess
0x140085255  lea     r8d, [rdx-7]; OpenAsSelf
0x140085259  call    cs:__imp_OpenThreadToken
0x14008525f  test    eax, eax
0x140085261  jnz     short loc_140085280
0x140085263  call    cs:__imp_GetCurrentProcess
0x140085269  mov     rcx, rax; ProcessHandle
0x14008526c  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x140085271  mov     edx, 8; DesiredAccess
0x140085276  call    cs:__imp_OpenProcessToken
0x14008527c  test    eax, eax
0x14008527e  jz      short loc_1400852BB
0x140085280  mov     rax, [rsp+58h+TokenHandle]
0x140085285  mov     [rsp+58h+hObject], rax
0x14008528a  lea     rdx, [rsp+58h+hObject]
0x14008528f  mov     rcx, rbx
0x140085292  call    ??0Token@@QEAA@$$QEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; Token::Token(std::unique_ptr<void,Private::HandleClose> &&)
0x140085297  nop
0x140085298  mov     rcx, [rsp+58h+hObject]; hObject
0x14008529d  test    rcx, rcx
0x1400852a0  jz      short loc_1400852B2
0x1400852a2  lea     rax, [rcx-1]
0x1400852a6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400852aa  ja      short loc_1400852B2
0x1400852ac  call    cs:__imp_CloseHandle
0x1400852b2  mov     rax, rbx
0x1400852b5  add     rsp, 50h
0x1400852b9  pop     rbx
0x1400852ba  retn
0x1400852bb  call    cs:__imp_GetLastError
0x1400852c1  mov     ebx, eax
0x1400852c3  test    eax, eax
0x1400852c5  jle     short loc_1400852D0
0x1400852c7  movzx   ebx, ax
0x1400852ca  or      ebx, 80070000h
0x1400852d0  lea     rax, WPP_GLOBAL_Control
0x1400852d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400852de  cmp     rcx, rax
0x1400852e1  jz      short loc_140085301
0x1400852e3  test    byte ptr [rcx+1Ch], 1
0x1400852e7  jz      short loc_140085301
0x1400852e9  mov     edx, 0Ah
0x1400852ee  mov     r9d, ebx
0x1400852f1  lea     r8, WPP_921fc3043960359be1fe4e548f998926_Traceguids
0x1400852f8  mov     rcx, [rcx+10h]
0x1400852fc  call    WPP_SF_d
0x140085301  mov     edx, ebx; int
0x140085303  lea     rcx, [rsp+58h+pExceptionObject]; this
0x140085308  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14008530d  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140085314  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x140085319  call    _CxxThrowException_0
```
