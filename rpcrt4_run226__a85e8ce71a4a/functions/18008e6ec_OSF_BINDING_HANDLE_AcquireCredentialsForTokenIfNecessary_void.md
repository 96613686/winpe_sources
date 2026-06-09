# OSF_BINDING_HANDLE::AcquireCredentialsForTokenIfNecessary(void * *)

- ea: `0x18008e6ec`
- end: `0x18008e837`
- name: `?AcquireCredentialsForTokenIfNecessary@OSF_BINDING_HANDLE@@QEAAJPEAPEAX@Z`
- size: `331`
- prototype: `__int64 __fastcall(OSF_BINDING_HANDLE *__hidden this, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800ab758`
- `0x1800ac06c`

## callees

- `0x1800283bc`
- `0x18008e6ec`
- `0x18008e840`
- `0x1800ca140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e809`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e809`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008e7e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008e7f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008e7e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008e7f5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008e756`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008e756`

## pseudocode

```c
int __fastcall OSF_BINDING_HANDLE::AcquireCredentialsForTokenIfNecessary(OSF_BINDING_HANDLE *this, void **a2)
{
  int result; // eax
  void *v4; // rcx
  OSF_CASSOCIATION *v6; // rcx
  int v7; // [rsp+30h] [rbp-19h] BYREF
  DWORD ReturnLength; // [rsp+34h] [rbp-15h] BYREF
  _DWORD v9[6]; // [rsp+38h] [rbp-11h] BYREF
  _OWORD TokenInformation[3]; // [rsp+50h] [rbp+7h] BYREF
  __int64 v11; // [rsp+80h] [rbp+37h]

  v7 = 0;
  result = 0;
  ReturnLength = 0;
  v11 = 0;
  v4 = *a2;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( v4 )
  {
    if ( GetTokenInformation(v4, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
    {
      v6 = (OSF_CASSOCIATION *)*((_QWORD *)this + 44);
      *((_DWORD *)this + 43) = 0;
      result = OSF_CASSOCIATION::FindOrCreateToken(
                 v6,
                 *a2,
                 (struct _LUID *)TokenInformation + 1,
                 (struct RPC_TOKEN **)this + 54,
                 &v7);
      if ( result )
      {
        *a2 = 0;
      }
      else
      {
        if ( v7 )
          CloseHandle(*a2);
        *a2 = 0;
        result = 0;
        *((_QWORD *)this + 22) = *(_QWORD *)(*((_QWORD *)this + 54) + 8LL);
      }
    }
    else
    {
      *((_DWORD *)this + 43) = 1;
      CloseHandle(*a2);
      *a2 = 0;
      v9[0] = 3;
      v9[2] = GetLastError();
      RpcpErrorAddRecord(2u, 5, 0x335u, 1, (struct tagParam *)v9);
      return 5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18008e6ec  mov     [rsp-8+arg_10], rbx
0x18008e6f1  push    rbp
0x18008e6f2  push    rsi
0x18008e6f3  push    rdi
0x18008e6f4  lea     rbp, [rsp-47h]
0x18008e6f9  sub     rsp, 90h
0x18008e700  mov     rax, cs:__security_cookie
0x18008e707  xor     rax, rsp
0x18008e70a  mov     [rbp+57h+var_18], rax
0x18008e70e  xorps   xmm0, xmm0
0x18008e711  mov     [rbp+57h+var_70], 0
0x18008e718  xor     eax, eax
0x18008e71a  mov     [rbp+57h+var_6C], 0
0x18008e721  mov     rdi, rcx
0x18008e724  mov     [rbp+57h+var_20], rax
0x18008e728  mov     rcx, [rdx]; TokenHandle
0x18008e72b  mov     rbx, rdx
0x18008e72e  movups  [rbp+57h+TokenInformation], xmm0
0x18008e732  movups  [rbp+57h+var_40], xmm0
0x18008e736  movups  [rbp+57h+var_30], xmm0
0x18008e73a  test    rcx, rcx
0x18008e73d  jz      short loc_18008E7B9
0x18008e73f  mov     r9d, 38h ; '8'; TokenInformationLength
0x18008e745  lea     rax, [rbp+57h+var_6C]
0x18008e749  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18008e74d  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x18008e752  lea     edx, [r9-2Eh]; TokenInformationClass
0x18008e756  call    cs:__imp_GetTokenInformation
0x18008e75c  mov     esi, 1
0x18008e761  cmp     eax, esi
0x18008e763  jnz     loc_18008E7EC
0x18008e769  mov     rcx, [rdi+160h]; this
0x18008e770  lea     rax, [rbp+57h+var_70]
0x18008e774  mov     dword ptr [rdi+0ACh], 0
0x18008e77e  lea     rsi, [rdi+1B0h]
0x18008e785  mov     rdx, [rbx]; void *
0x18008e788  lea     r8, [rbp+57h+TokenInformation+8]; struct _LUID *
0x18008e78c  mov     r9, rsi; struct RPC_TOKEN **
0x18008e78f  mov     [rsp+0A0h+ReturnLength], rax; int *
0x18008e794  call    ?FindOrCreateToken@OSF_CASSOCIATION@@QEAAJPEAXPEAU_LUID@@PEAPEAVRPC_TOKEN@@PEAH@Z; OSF_CASSOCIATION::FindOrCreateToken(void *,_LUID *,RPC_TOKEN * *,int *)
0x18008e799  test    eax, eax
0x18008e79b  jnz     short loc_18008E7D8
0x18008e79d  cmp     [rbp+57h+var_70], eax
0x18008e7a0  jnz     short loc_18008E7E1
0x18008e7a2  mov     qword ptr [rbx], 0
0x18008e7a9  mov     rax, [rsi]
0x18008e7ac  mov     rcx, [rax+8]
0x18008e7b0  xor     eax, eax
0x18008e7b2  mov     [rdi+0B0h], rcx
0x18008e7b9  mov     rcx, [rbp+57h+var_18]
0x18008e7bd  xor     rcx, rsp; StackCookie
0x18008e7c0  call    __security_check_cookie
0x18008e7c5  mov     rbx, [rsp+0A0h+arg_10]
0x18008e7cd  add     rsp, 90h
0x18008e7d4  pop     rdi
0x18008e7d5  pop     rsi
0x18008e7d6  pop     rbp
0x18008e7d7  retn
0x18008e7d8  mov     qword ptr [rbx], 0
0x18008e7df  jmp     short loc_18008E7B9
0x18008e7e1  mov     rcx, [rbx]; hObject
0x18008e7e4  call    cs:__imp_CloseHandle
0x18008e7ea  jmp     short loc_18008E7A2
0x18008e7ec  mov     [rdi+0ACh], esi
0x18008e7f2  mov     rcx, [rbx]; hObject
0x18008e7f5  call    cs:__imp_CloseHandle
0x18008e7fb  mov     qword ptr [rbx], 0
0x18008e802  mov     [rbp+57h+var_68], 3
0x18008e809  call    cs:__imp_GetLastError
0x18008e80f  mov     ebx, 5
0x18008e814  mov     [rbp+57h+var_60], eax
0x18008e817  lea     rax, [rbp+57h+var_68]
0x18008e81b  mov     r8d, 335h; unsigned __int16
0x18008e821  mov     r9d, esi; int
0x18008e824  mov     [rsp+0A0h+ReturnLength], rax; struct tagParam *
0x18008e829  mov     edx, ebx; int
0x18008e82b  lea     ecx, [rbx-3]; unsigned int
0x18008e82e  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18008e833  mov     eax, ebx
0x18008e835  jmp     short loc_18008E7B9
```
