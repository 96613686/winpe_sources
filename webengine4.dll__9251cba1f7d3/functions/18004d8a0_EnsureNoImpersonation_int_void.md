# EnsureNoImpersonation(int *,void * *)

- ea: `0x18004d8a0`
- end: `0x18004d93a`
- name: `?EnsureNoImpersonation@@YAJPEAHPEAPEAX@Z`
- size: `154`
- prototype: `__int64 __fastcall(int *, void **)`
- caller_count: `11`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180015c64`
- `0x180015ea0`
- `0x1800161d0`
- `0x1800162d0`
- `0x1800163b0`
- `0x180016480`
- `0x1800165a0`
- `0x180016650`
- `0x1800610c0`
- `0x180061d30`
- `0x180061dc4`

## callees

- `0x18004d350`
- `0x18004d8a0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18004d908`
- `KERNEL32!CloseHandle` at `0x18004d908`
- `KERNEL32!GetCurrentThread` at `0x18004d8c3`
- `KERNEL32!GetCurrentThread` at `0x18004d8c3`
- `ADVAPI32!OpenThreadToken` at `0x18004d8da`
- `ADVAPI32!OpenThreadToken` at `0x18004d8da`
- `ADVAPI32!RevertToSelf` at `0x18004d8ea`
- `ADVAPI32!RevertToSelf` at `0x18004d8ea`

## pseudocode

```c
__int64 __fastcall EnsureNoImpersonation(int *a1, void **a2)
{
  int v2; // ebx
  unsigned int LastWin32Error; // edi
  HANDLE CurrentThread; // rax
  void *v7; // rax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  LastWin32Error = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle);
  v7 = TokenHandle;
  if ( TokenHandle )
  {
    if ( RevertToSelf() )
    {
      v2 = 1;
      v7 = TokenHandle;
    }
    else
    {
      LastWin32Error = GetLastWin32Error();
      v7 = TokenHandle;
      if ( TokenHandle )
      {
        CloseHandle(TokenHandle);
        v7 = 0;
      }
    }
  }
  *a1 = v2;
  *a2 = v7;
  return LastWin32Error;
}

```

## disassembly

```asm
0x18004d8a0  mov     rax, rsp
0x18004d8a3  mov     [rax+10h], rbx
0x18004d8a7  mov     [rax+18h], rsi
0x18004d8ab  mov     [rax+20h], rdi
0x18004d8af  push    r14
0x18004d8b1  sub     rsp, 20h
0x18004d8b5  xor     ebx, ebx
0x18004d8b7  mov     rsi, rdx
0x18004d8ba  mov     edi, ebx
0x18004d8bc  mov     [rax+8], rbx
0x18004d8c0  mov     r14, rcx
0x18004d8c3  call    cs:__imp_GetCurrentThread
0x18004d8c9  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18004d8ce  mov     edx, 2000Ch; DesiredAccess
0x18004d8d3  mov     rcx, rax; ThreadHandle
0x18004d8d6  lea     r8d, [rbx+1]; OpenAsSelf
0x18004d8da  call    cs:__imp_OpenThreadToken
0x18004d8e0  mov     rax, [rsp+28h+TokenHandle]
0x18004d8e5  test    rax, rax
0x18004d8e8  jz      short loc_18004D91C
0x18004d8ea  call    cs:__imp_RevertToSelf
0x18004d8f0  test    eax, eax
0x18004d8f2  jnz     short loc_18004D912
0x18004d8f4  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18004d8f9  mov     edi, eax
0x18004d8fb  mov     rax, [rsp+28h+TokenHandle]
0x18004d900  test    rax, rax
0x18004d903  jz      short loc_18004D91C
0x18004d905  mov     rcx, rax; hObject
0x18004d908  call    cs:__imp_CloseHandle
0x18004d90e  mov     eax, ebx
0x18004d910  jmp     short loc_18004D91C
0x18004d912  mov     ebx, 1
0x18004d917  mov     rax, [rsp+28h+TokenHandle]
0x18004d91c  mov     [r14], ebx
0x18004d91f  mov     rbx, [rsp+28h+arg_8]
0x18004d924  mov     [rsi], rax
0x18004d927  mov     eax, edi
0x18004d929  mov     rdi, [rsp+28h+arg_18]
0x18004d92e  mov     rsi, [rsp+28h+arg_10]
0x18004d933  add     rsp, 20h
0x18004d937  pop     r14
0x18004d939  retn
```
