# pGetFullUserNameFromRequest(void *,ushort * *)

- ea: `0x18000b9bc`
- end: `0x18000baef`
- name: `?pGetFullUserNameFromRequest@@YAKPEAXPEAPEAG@Z`
- size: `307`
- prototype: `unsigned int __fastcall(void *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180003dc4`
- `0x18000bee0`

## callees

- `0x18000b9bc`
- `0x18000ccf8`
- `0x18000cdc8`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000bac7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000bac7`
- `KERNEL32!HeapFree` at `0x18000ba97`
- `KERNEL32!HeapFree` at `0x18000ba97`
- `KERNEL32!GetProcessHeap` at `0x18000ba83`
- `KERNEL32!GetProcessHeap` at `0x18000ba83`
- `WDSSRV!WdsImpersonateClient` at `0x18000b9f4`
- `WDSSRV!WdsImpersonateClient` at `0x18000b9f4`
- `WDSSRV!WdsRevertToSelf` at `0x18000ba3f`
- `WDSSRV!WdsRevertToSelf` at `0x18000baaa`
- `WDSSRV!WdsRevertToSelf` at `0x18000ba3f`
- `WDSSRV!WdsRevertToSelf` at `0x18000baaa`
- `WdsCommonLib!?GetCurrentUser@@YAKPEAPEAGPEBG@Z` at `0x18000ba1d`
- `WdsCommonLib!?GetCurrentUser@@YAKPEAPEAGPEBG@Z` at `0x18000ba1d`

## pseudocode

```c
__int64 __fastcall pGetFullUserNameFromRequest(void *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rsi
  int v3; // edi
  unsigned int CurrentUser; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned __int16 *v13; // rax
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v16; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  v3 = 0;
  v16 = 0;
  if ( a1 && a2 )
  {
    CurrentUser = WdsImpersonateClient(a1);
    if ( !(unsigned int)ElValidateWin32_1(CurrentUser, v7, v8, 1127) )
    {
      v3 = 1;
      CurrentUser = GetCurrentUser(&v16, 0);
      if ( !(unsigned int)ElValidateWin32_1(CurrentUser, v9, v10, 1132) )
      {
        CurrentUser = WdsRevertToSelf(a1);
        if ( !(unsigned int)ElValidateWin32_1(CurrentUser, v11, v12, 1137) )
        {
          v3 = 0;
          v13 = (unsigned __int16 *)StrDupe(v16);
          v2 = v13;
          if ( !v13 )
          {
            CurrentUser = 8;
            goto LABEL_15;
          }
          *a2 = v13;
        }
      }
    }
    if ( CurrentUser && v2 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    if ( v3 )
      WdsRevertToSelf(a1);
  }
  else
  {
    CurrentUser = 87;
  }
LABEL_15:
  if ( v16 )
    operator delete[](v16);
  return CurrentUser;
}

```

## disassembly

```asm
0x18000b9bc  mov     rax, rsp
0x18000b9bf  mov     [rax+10h], rbx
0x18000b9c3  mov     [rax+18h], rbp
0x18000b9c7  mov     [rax+20h], rsi
0x18000b9cb  push    rdi
0x18000b9cc  push    r14
0x18000b9ce  push    r15
0x18000b9d0  sub     rsp, 20h
0x18000b9d4  xor     esi, esi
0x18000b9d6  xor     edi, edi
0x18000b9d8  and     [rax+8], rsi
0x18000b9dc  mov     r14, rdx
0x18000b9df  mov     rbp, rcx
0x18000b9e2  test    rcx, rcx
0x18000b9e5  jz      loc_18000BAB8
0x18000b9eb  test    rdx, rdx
0x18000b9ee  jz      loc_18000BAB8
0x18000b9f4  call    cs:__imp_WdsImpersonateClient
0x18000b9fb  nop     dword ptr [rax+rax+00h]
0x18000ba00  mov     ecx, eax
0x18000ba02  mov     r9d, 467h
0x18000ba08  mov     ebx, eax
0x18000ba0a  call    ElValidateWin32_1
0x18000ba0f  test    eax, eax
0x18000ba11  jnz     short loc_18000BA7A
0x18000ba13  xor     edx, edx
0x18000ba15  lea     rcx, [rsp+38h+arg_0]
0x18000ba1a  lea     edi, [rsi+1]
0x18000ba1d  call    cs:__imp_?GetCurrentUser@@YAKPEAPEAGPEBG@Z; GetCurrentUser(ushort * *,ushort const *)
0x18000ba24  nop     dword ptr [rax+rax+00h]
0x18000ba29  mov     ecx, eax
0x18000ba2b  mov     r9d, 46Ch
0x18000ba31  mov     ebx, eax
0x18000ba33  call    ElValidateWin32_1
0x18000ba38  test    eax, eax
0x18000ba3a  jnz     short loc_18000BA7A
0x18000ba3c  mov     rcx, rbp
0x18000ba3f  call    cs:__imp_WdsRevertToSelf
0x18000ba46  nop     dword ptr [rax+rax+00h]
0x18000ba4b  mov     ecx, eax
0x18000ba4d  mov     r9d, 471h
0x18000ba53  mov     ebx, eax
0x18000ba55  call    ElValidateWin32_1
0x18000ba5a  test    eax, eax
0x18000ba5c  jnz     short loc_18000BA7A
0x18000ba5e  mov     rcx, [rsp+38h+arg_0]; unsigned __int16 *
0x18000ba63  xor     edi, edi
0x18000ba65  call    StrDupe
0x18000ba6a  mov     rsi, rax
0x18000ba6d  test    rax, rax
0x18000ba70  jnz     short loc_18000BA77
0x18000ba72  lea     ebx, [rdi+8]
0x18000ba75  jmp     short loc_18000BABD
0x18000ba77  mov     [r14], rax
0x18000ba7a  test    ebx, ebx
0x18000ba7c  jz      short loc_18000BAA3
0x18000ba7e  test    rsi, rsi
0x18000ba81  jz      short loc_18000BAA3
0x18000ba83  call    cs:__imp_GetProcessHeap
0x18000ba8a  nop     dword ptr [rax+rax+00h]
0x18000ba8f  mov     r8, rsi; lpMem
0x18000ba92  xor     edx, edx; dwFlags
0x18000ba94  mov     rcx, rax; hHeap
0x18000ba97  call    cs:__imp_HeapFree
0x18000ba9e  nop     dword ptr [rax+rax+00h]
0x18000baa3  test    edi, edi
0x18000baa5  jz      short loc_18000BABD
0x18000baa7  mov     rcx, rbp
0x18000baaa  call    cs:__imp_WdsRevertToSelf
0x18000bab1  nop     dword ptr [rax+rax+00h]
0x18000bab6  jmp     short loc_18000BABD
0x18000bab8  mov     ebx, 57h ; 'W'
0x18000babd  mov     rcx, [rsp+38h+arg_0]
0x18000bac2  test    rcx, rcx
0x18000bac5  jz      short loc_18000BAD3
0x18000bac7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000bace  nop     dword ptr [rax+rax+00h]
0x18000bad3  mov     rbp, [rsp+38h+arg_10]
0x18000bad8  mov     eax, ebx
0x18000bada  mov     rbx, [rsp+38h+arg_8]
0x18000badf  mov     rsi, [rsp+38h+arg_18]
0x18000bae4  add     rsp, 20h
0x18000bae8  pop     r15
0x18000baea  pop     r14
0x18000baec  pop     rdi
0x18000baed  retn
```
