# SwapTokenOnThread(RPC_TOKEN *,void * *)

- ea: `0x18005b7d8`
- end: `0x18005b863`
- name: `?SwapTokenOnThread@@YAHPEAVRPC_TOKEN@@PEAPEAX@Z`
- size: `139`
- prototype: `__int64 __fastcall(struct RPC_TOKEN *, void **)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18005b73c`
- `0x18005d568`
- `0x18005e20c`
- `0x180061bd0`
- `0x18009deb0`
- `0x1800a82f0`

## callees

- `0x18005b7d8`
- `0x18005b86c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b855`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b855`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005b813`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005b813`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005b7f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005b7f6`

## pseudocode

```c
__int64 __fastcall SwapTokenOnThread(void **a1, void **a2)
{
  void *v3; // rbx
  HANDLE CurrentThread; // rax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  if ( a1 )
    v3 = *a1;
  else
    v3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    if ( (unsigned int)ReplaceToken(v3) )
    {
      *a2 = TokenHandle;
      return 1;
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
  }
  return 0;
}

```

## disassembly

```asm
0x18005b7d8  mov     [rsp+arg_8], rbx
0x18005b7dd  push    rdi
0x18005b7de  sub     rsp, 20h
0x18005b7e2  mov     [rsp+28h+TokenHandle], 0
0x18005b7eb  mov     rdi, rdx
0x18005b7ee  test    rcx, rcx
0x18005b7f1  jz      short loc_18005B851
0x18005b7f3  mov     rbx, [rcx]
0x18005b7f6  call    cs:__imp_GetCurrentThread
0x18005b7fd  nop     dword ptr [rax+rax+00h]
0x18005b802  mov     edx, 0Ch; DesiredAccess
0x18005b807  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18005b80c  mov     rcx, rax; ThreadHandle
0x18005b80f  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18005b813  call    cs:__imp_OpenThreadToken
0x18005b81a  nop     dword ptr [rax+rax+00h]
0x18005b81f  test    eax, eax
0x18005b821  jz      short loc_18005B84D
0x18005b823  mov     rcx, rbx; void *
0x18005b826  call    ?ReplaceToken@@YAHPEAX@Z; ReplaceToken(void *)
0x18005b82b  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18005b830  test    eax, eax
0x18005b832  jz      short loc_18005B848
0x18005b834  mov     [rdi], rcx
0x18005b837  mov     eax, 1
0x18005b83c  mov     rbx, [rsp+28h+arg_8]
0x18005b841  add     rsp, 20h
0x18005b845  pop     rdi
0x18005b846  retn
0x18005b848  test    rcx, rcx
0x18005b84b  jnz     short loc_18005B855
0x18005b84d  xor     eax, eax
0x18005b84f  jmp     short loc_18005B83C
0x18005b851  xor     ebx, ebx
0x18005b853  jmp     short loc_18005B7F6
0x18005b855  call    cs:__imp_CloseHandle
0x18005b85c  nop     dword ptr [rax+rax+00h]
0x18005b861  jmp     short loc_18005B84D
```
