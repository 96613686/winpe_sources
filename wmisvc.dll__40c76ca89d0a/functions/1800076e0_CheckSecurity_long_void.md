# CheckSecurity(long,void * *)

- ea: `0x1800076e0`
- end: `0x18000777c`
- name: `?CheckSecurity@@YAHJPEAPEAX@Z`
- size: `156`
- prototype: `_BOOL8 __fastcall(int, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007120`
- `0x18000dcdc`
- `0x1800136e4`

## callees

- `0x1800076e0`
- `0x180007784`
- `0x1800077e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000774f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000774f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000770d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000770d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007724`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007724`
- `wbemcomn!IsPrivilegePresent` at `0x18000773c`
- `wbemcomn!IsPrivilegePresent` at `0x18000773c`

## pseudocode

```c
_BOOL8 __fastcall CheckSecurity(int a1, void **a2)
{
  int v4; // eax
  HANDLE CurrentThread; // rax
  BOOL v6; // ebx
  BOOL v7; // ebx
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  v4 = WbemCoImpersonateClient();
  if ( v4 == -2147417833 )
    return 1;
  if ( v4 < 0 )
    return 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v6 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
  WbemCoRevertToSelf();
  if ( !v6 )
    return 0;
  v7 = IsPrivilegePresent(TokenHandle, a1);
  if ( a2 )
    *a2 = TokenHandle;
  else
    CloseHandle(TokenHandle);
  return v7;
}

```

## disassembly

```asm
0x1800076e0  mov     [rsp+arg_0], rbx
0x1800076e5  mov     [rsp+arg_8], rsi
0x1800076ea  push    rdi
0x1800076eb  sub     rsp, 20h
0x1800076ef  mov     rdi, rdx
0x1800076f2  mov     esi, ecx
0x1800076f4  call    ?WbemCoImpersonateClient@@YAJXZ; WbemCoImpersonateClient(void)
0x1800076f9  cmp     eax, 80010117h
0x1800076fe  jz      short loc_180007767
0x180007700  test    eax, eax
0x180007702  js      short loc_18000776E
0x180007704  mov     [rsp+28h+TokenHandle], 0
0x18000770d  call    cs:__imp_GetCurrentThread
0x180007713  mov     edx, 8; DesiredAccess
0x180007718  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18000771d  mov     rcx, rax; ThreadHandle
0x180007720  lea     r8d, [rdx-7]; OpenAsSelf
0x180007724  call    cs:__imp_OpenThreadToken
0x18000772a  mov     ebx, eax
0x18000772c  call    ?WbemCoRevertToSelf@@YAJXZ; WbemCoRevertToSelf(void)
0x180007731  test    ebx, ebx
0x180007733  jz      short loc_18000776E
0x180007735  mov     rcx, [rsp+28h+TokenHandle]
0x18000773a  mov     edx, esi
0x18000773c  call    cs:__imp_?IsPrivilegePresent@@YA_NPEAXJ@Z; IsPrivilegePresent(void *,long)
0x180007742  movzx   ebx, al
0x180007745  test    rdi, rdi
0x180007748  jnz     short loc_180007772
0x18000774a  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18000774f  call    cs:__imp_CloseHandle
0x180007755  mov     eax, ebx
0x180007757  mov     rbx, [rsp+28h+arg_0]
0x18000775c  mov     rsi, [rsp+28h+arg_8]
0x180007761  add     rsp, 20h
0x180007765  pop     rdi
0x180007766  retn
0x180007767  mov     eax, 1
0x18000776c  jmp     short loc_180007757
0x18000776e  xor     eax, eax
0x180007770  jmp     short loc_180007757
0x180007772  mov     rax, [rsp+28h+TokenHandle]
0x180007777  mov     [rdi], rax
0x18000777a  jmp     short loc_180007755
```
