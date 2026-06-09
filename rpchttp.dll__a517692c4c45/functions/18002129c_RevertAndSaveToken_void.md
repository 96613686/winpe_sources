# RevertAndSaveToken(void * *)

- ea: `0x18002129c`
- end: `0x180021326`
- name: `?RevertAndSaveToken@@YAJPEAPEAX@Z`
- size: `138`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001fc58`

## callees

- `0x18001b930`
- `0x18002129c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800212db`
- `KERNEL32!GetLastError` at `0x1800212fe`
- `KERNEL32!GetLastError` at `0x1800212db`
- `KERNEL32!GetLastError` at `0x1800212fe`
- `KERNEL32!GetCurrentThread` at `0x1800212ae`
- `KERNEL32!GetCurrentThread` at `0x1800212ae`
- `ADVAPI32!RevertToSelf` at `0x1800212d1`
- `ADVAPI32!RevertToSelf` at `0x1800212d1`
- `ADVAPI32!OpenThreadToken` at `0x1800212c7`
- `ADVAPI32!OpenThreadToken` at `0x1800212c7`

## pseudocode

```c
__int64 __fastcall RevertAndSaveToken(void **a1)
{
  HANDLE CurrentThread; // rax
  void *v3; // rdx
  __int64 result; // rax
  DWORD LastError; // eax
  DWORD v6; // ecx
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    if ( !RevertToSelf() )
    {
      GetLastError();
      RpcpReportFatalError(21);
      __debugbreak();
    }
    v3 = TokenHandle;
    goto LABEL_5;
  }
  LastError = GetLastError();
  v3 = 0;
  v6 = LastError;
  result = 5;
  if ( v6 != 5 )
  {
    if ( v6 == 1008 )
    {
LABEL_5:
      *a1 = v3;
      return 0;
    }
    if ( v6 != 1347 )
      return 1450;
  }
  return result;
}

```

## disassembly

```asm
0x18002129c  push    rbx
0x18002129e  sub     rsp, 20h
0x1800212a2  mov     rbx, rcx
0x1800212a5  mov     [rsp+28h+TokenHandle], 0
0x1800212ae  call    cs:__imp_GetCurrentThread
0x1800212b4  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800212b9  mov     edx, 2000Ch; DesiredAccess
0x1800212be  mov     rcx, rax; ThreadHandle
0x1800212c1  mov     r8d, 1; OpenAsSelf
0x1800212c7  call    cs:__imp_OpenThreadToken
0x1800212cd  test    eax, eax
0x1800212cf  jz      short loc_1800212FE
0x1800212d1  call    cs:__imp_RevertToSelf
0x1800212d7  test    eax, eax
0x1800212d9  jnz     short loc_1800212EE
0x1800212db  call    cs:__imp_GetLastError
0x1800212e1  mov     edx, eax
0x1800212e3  mov     ecx, 15h
0x1800212e8  call    RpcpReportFatalError
0x1800212ed  int     3; Trap to Debugger
0x1800212ee  mov     rdx, [rsp+28h+TokenHandle]
0x1800212f3  mov     [rbx], rdx
0x1800212f6  xor     eax, eax
0x1800212f8  add     rsp, 20h
0x1800212fc  pop     rbx
0x1800212fd  retn
0x1800212fe  call    cs:__imp_GetLastError
0x180021304  xor     edx, edx
0x180021306  mov     ecx, eax
0x180021308  lea     eax, [rdx+5]
0x18002130b  cmp     ecx, eax
0x18002130d  jz      short loc_1800212F8
0x18002130f  cmp     ecx, 3F0h
0x180021315  jz      short loc_1800212F3
0x180021317  cmp     ecx, 543h
0x18002131d  jz      short loc_1800212F8
0x18002131f  mov     eax, 5AAh
0x180021324  jmp     short loc_1800212F8
```
