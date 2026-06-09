# OSF_BINDING_HANDLE::AcquireCredentialsForTokenIfNecessary(void * *)

- ea: `0x1800927e8`
- end: `0x180092953`
- name: `?AcquireCredentialsForTokenIfNecessary@OSF_BINDING_HANDLE@@QEAAJPEAPEAX@Z`
- size: `363`
- prototype: `__int64 __fastcall(OSF_BINDING_HANDLE *__hidden this, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800af198`
- `0x1800afaf8`

## callees

- `0x1800295d8`
- `0x1800927e8`
- `0x18009295c`
- `0x1800ceda0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009291c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009291c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800928eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180092902`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800928eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180092902`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180092856`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180092856`

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
0x1800927e8  mov     [rsp-8+arg_10], rbx
0x1800927ed  push    rbp
0x1800927ee  push    rsi
0x1800927ef  push    rdi
0x1800927f0  lea     rbp, [rsp-47h]
0x1800927f5  sub     rsp, 90h
0x1800927fc  mov     rax, cs:__security_cookie
0x180092803  xor     rax, rsp
0x180092806  mov     [rbp+57h+var_18], rax
0x18009280a  xorps   xmm0, xmm0
0x18009280d  mov     [rbp+57h+var_70], 0
0x180092814  xor     eax, eax
0x180092816  mov     [rbp+57h+var_6C], 0
0x18009281d  mov     rdi, rcx
0x180092820  mov     [rbp+57h+var_20], rax
0x180092824  mov     rcx, [rdx]; TokenHandle
0x180092827  mov     rbx, rdx
0x18009282a  movups  [rbp+57h+TokenInformation], xmm0
0x18009282e  movups  [rbp+57h+var_40], xmm0
0x180092832  movups  [rbp+57h+var_30], xmm0
0x180092836  test    rcx, rcx
0x180092839  jz      loc_1800928BF
0x18009283f  mov     r9d, 38h ; '8'; TokenInformationLength
0x180092845  lea     rax, [rbp+57h+var_6C]
0x180092849  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18009284d  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x180092852  lea     edx, [r9-2Eh]; TokenInformationClass
0x180092856  call    cs:__imp_GetTokenInformation
0x18009285d  nop     dword ptr [rax+rax+00h]
0x180092862  mov     esi, 1
0x180092867  cmp     eax, esi
0x180092869  jnz     loc_1800928F9
0x18009286f  mov     rcx, [rdi+160h]; this
0x180092876  lea     rax, [rbp+57h+var_70]
0x18009287a  mov     dword ptr [rdi+0ACh], 0
0x180092884  lea     rsi, [rdi+1B0h]
0x18009288b  mov     rdx, [rbx]; void *
0x18009288e  lea     r8, [rbp+57h+TokenInformation+8]; struct _LUID *
0x180092892  mov     r9, rsi; struct RPC_TOKEN **
0x180092895  mov     [rsp+0A0h+ReturnLength], rax; int *
0x18009289a  call    ?FindOrCreateToken@OSF_CASSOCIATION@@QEAAJPEAXPEAU_LUID@@PEAPEAVRPC_TOKEN@@PEAH@Z; OSF_CASSOCIATION::FindOrCreateToken(void *,_LUID *,RPC_TOKEN * *,int *)
0x18009289f  test    eax, eax
0x1800928a1  jnz     short loc_1800928DF
0x1800928a3  cmp     [rbp+57h+var_70], eax
0x1800928a6  jnz     short loc_1800928E8
0x1800928a8  mov     qword ptr [rbx], 0
0x1800928af  mov     rax, [rsi]
0x1800928b2  mov     rcx, [rax+8]
0x1800928b6  xor     eax, eax
0x1800928b8  mov     [rdi+0B0h], rcx
0x1800928bf  mov     rcx, [rbp+57h+var_18]
0x1800928c3  xor     rcx, rsp; StackCookie
0x1800928c6  call    __security_check_cookie
0x1800928cb  mov     rbx, [rsp+0A0h+arg_10]
0x1800928d3  add     rsp, 90h
0x1800928da  pop     rdi
0x1800928db  pop     rsi
0x1800928dc  pop     rbp
0x1800928dd  retn
0x1800928df  mov     qword ptr [rbx], 0
0x1800928e6  jmp     short loc_1800928BF
0x1800928e8  mov     rcx, [rbx]; hObject
0x1800928eb  call    cs:__imp_CloseHandle
0x1800928f2  nop     dword ptr [rax+rax+00h]
0x1800928f7  jmp     short loc_1800928A8
0x1800928f9  mov     [rdi+0ACh], esi
0x1800928ff  mov     rcx, [rbx]; hObject
0x180092902  call    cs:__imp_CloseHandle
0x180092909  nop     dword ptr [rax+rax+00h]
0x18009290e  mov     qword ptr [rbx], 0
0x180092915  mov     [rbp+57h+var_68], 3
0x18009291c  call    cs:__imp_GetLastError
0x180092923  nop     dword ptr [rax+rax+00h]
0x180092928  mov     ebx, 5
0x18009292d  mov     [rbp+57h+var_60], eax
0x180092930  lea     rax, [rbp+57h+var_68]
0x180092934  mov     r8d, 335h; unsigned __int16
0x18009293a  mov     r9d, esi; int
0x18009293d  mov     [rsp+0A0h+ReturnLength], rax; struct tagParam *
0x180092942  mov     edx, ebx; int
0x180092944  lea     ecx, [rbx-3]; unsigned int
0x180092947  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18009294c  mov     eax, ebx
0x18009294e  jmp     loc_1800928BF
```
