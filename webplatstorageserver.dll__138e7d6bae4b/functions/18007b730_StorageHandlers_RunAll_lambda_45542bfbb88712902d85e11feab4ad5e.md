# StorageHandlers::RunAll__lambda_45542bfbb88712902d85e11feab4ad5e___

- ea: `0x18007b730`
- end: `0x18007b943`
- name: `StorageHandlers::RunAll__lambda_45542bfbb88712902d85e11feab4ad5e___`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a3bd0`

## callees

- `0x18000f2b0`
- `0x180061c90`
- `0x180066010`
- `0x18006bf64`
- `0x18007b730`
- `0x18007b94c`
- `0x180080fb0`
- `0x1800814bc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18007b8e0`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18007b8e0`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18007b839`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18007b839`

## string_xrefs

- `0x18007b762`: `RunAll DeleteOrigin`

## pseudocode

```c
unsigned __int64 __fastcall StorageHandlers::RunAll__lambda_45542bfbb88712902d85e11feab4ad5e___(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v3; // rdi
  __int64 v5; // rbx
  unsigned __int64 v6; // r15
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // rax
  __int64 v9; // rdi
  _QWORD *v10; // rbx
  BOOL v11; // edi
  const char *v12; // r9
  unsigned __int64 v13; // rdx
  unsigned __int64 result; // rax
  const char *v15; // r9
  int Address; // [rsp+20h] [rbp-88h] BYREF
  int CompareAddress; // [rsp+24h] [rbp-84h] BYREF
  _QWORD *v18; // [rsp+28h] [rbp-80h] BYREF
  __int64 v19; // [rsp+30h] [rbp-78h]
  __int64 v20; // [rsp+38h] [rbp-70h]
  _QWORD v21[5]; // [rsp+40h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v3 = a3;
  v20 = a3;
  v5 = a1;
  v19 = a1;
  v21[0] = L"RunAll DeleteOrigin";
  v6 = (__int64)(a2[1] - *a2) >> 2;
  if ( v6 > 5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\storagehandlers.cxx",
      (const char *)0x80070057LL,
      Address);
  if ( !v6 )
    v6 = 5;
  v21[1] = v6;
  Address = wil::safe_cast_failfast<unsigned int,unsigned __int64,0>(v6 - 1);
  v7 = 0;
  v18 = 0;
  if ( v6 != 1 )
  {
    do
    {
      *((_DWORD *)&v21[2] + v7) = 0;
      if ( *a2 == a2[1] )
        v8 = v7;
      else
        v8 = *(int *)(*a2 + 4 * v7);
      v9 = v5 + 16 * v8;
      v10 = operator new(0x30u);
      *v10 = (char *)&v21[2] + 4 * v7;
      v10[1] = v9;
      v10[2] = v7;
      v10[3] = v21;
      v10[4] = v20;
      v10[5] = &Address;
      v11 = TrySubmitThreadpoolCallback(
              ThreadpoolCallbackHelper__lambda_e101185310aeb88e5f232b9f624b242d___::s_Callback,
              v10,
              0);
      if ( v11 )
        v10 = 0;
      v18 = v10;
      std::unique_ptr_ThreadpoolCallbackHelper__lambda_e6d1bad9febbf826e25b795528038c48____std::default_delete_ThreadpoolCallbackHelper__lambda_e6d1bad9febbf826e25b795528038c48_______::_unique_ptr_ThreadpoolCallbackHelper__lambda_e6d1bad9febbf826e25b795528038c48____std::default_delete_ThreadpoolCallbackHelper__lambda_e6d1bad9febbf826e25b795528038c48_______(&v18);
      if ( !v11 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x6D,
          (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\storagehandlers.cxx",
          v12);
      v18 = (_QWORD *)++v7;
      v5 = v19;
    }
    while ( v7 < v6 - 1 );
    v3 = v20;
  }
  v13 = v7;
  if ( *a2 != a2[1] )
    v13 = *(int *)(*a2 + 4 * v7);
  *((_DWORD *)&v21[2] + v7) = 0;
  lambda_45542bfbb88712902d85e11feab4ad5e_::operator()(v3, v5 + 16 * v13, v7);
  while ( 1 )
  {
    CompareAddress = Address;
    if ( !Address )
      break;
    WaitOnAddress(&Address, &CompareAddress, 4u, 0xFFFFFFFF);
  }
  for ( result = 0; result < v6; ++result )
  {
    v15 = (const char *)*((unsigned int *)&v21[2] + result);
    if ( (int)v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\storagehandlers.cxx",
        v15,
        Address);
  }
  return result;
}

```

## disassembly

```asm
0x18007b730  push    rbx
0x18007b732  push    rsi
0x18007b733  push    rdi
0x18007b734  push    r12
0x18007b736  push    r13
0x18007b738  push    r14
0x18007b73a  push    r15
0x18007b73c  sub     rsp, 70h
0x18007b740  mov     rax, cs:__security_cookie
0x18007b747  xor     rax, rsp
0x18007b74a  mov     [rsp+0A8h+var_40], rax
0x18007b74f  mov     rdi, r8
0x18007b752  mov     [rsp+0A8h+var_70], r8
0x18007b757  mov     r12, rdx
0x18007b75a  mov     rbx, rcx
0x18007b75d  mov     [rsp+0A8h+var_78], rcx
0x18007b762  lea     rax, aRunallDeleteor; "RunAll DeleteOrigin"
0x18007b769  mov     [rsp+0A8h+var_68], rax
0x18007b76e  mov     r15, [rdx+8]
0x18007b772  sub     r15, [rdx]
0x18007b775  sar     r15, 2
0x18007b779  mov     rcx, [rsp+0A8h]; this
0x18007b781  mov     eax, 5
0x18007b786  cmp     r15, rax
0x18007b789  jbe     short loc_18007B7A1
0x18007b78b  mov     r9d, 80070057h; char *
0x18007b791  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\webplatstorageser"...
0x18007b798  lea     edx, [rax+44h]; void *
0x18007b79b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007b7a1  xor     esi, esi
0x18007b7a3  test    r15, r15
0x18007b7a6  cmovz   r15, rax
0x18007b7aa  mov     [rsp+0A8h+var_60], r15
0x18007b7af  lea     r13, [r15-1]
0x18007b7b3  mov     rcx, r13
0x18007b7b6  call    ??$safe_cast_failfast@I_K$0A@@wil@@YAI_K@Z; wil::safe_cast_failfast<uint,unsigned __int64,0>(unsigned __int64)
0x18007b7bb  mov     [rsp+0A8h+Address], eax
0x18007b7bf  mov     r14d, esi
0x18007b7c2  mov     [rsp+0A8h+var_80], rsi
0x18007b7c7  test    r13, r13
0x18007b7ca  jz      loc_18007B87E
0x18007b7d0  mov     dword ptr [rsp+r14*4+0A8h+var_58], esi
0x18007b7d5  mov     rax, [r12]
0x18007b7d9  cmp     rax, [r12+8]
0x18007b7de  jnz     short loc_18007B7E5
0x18007b7e0  mov     rax, r14
0x18007b7e3  jmp     short loc_18007B7E9
0x18007b7e5  movsxd  rax, dword ptr [rax+r14*4]
0x18007b7e9  add     rax, rax
0x18007b7ec  lea     rdi, [rbx+rax*8]
0x18007b7f0  mov     ecx, 30h ; '0'; Size
0x18007b7f5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007b7fa  mov     rbx, rax
0x18007b7fd  lea     rax, [rsp+0A8h+var_58]
0x18007b802  lea     rax, [rax+r14*4]
0x18007b806  mov     [rbx], rax
0x18007b809  mov     [rbx+8], rdi
0x18007b80d  mov     [rbx+10h], r14
0x18007b811  lea     rax, [rsp+0A8h+var_68]
0x18007b816  mov     [rbx+18h], rax
0x18007b81a  mov     rax, [rsp+0A8h+var_70]
0x18007b81f  mov     [rbx+20h], rax
0x18007b823  lea     rax, [rsp+0A8h+Address]
0x18007b828  mov     [rbx+28h], rax
0x18007b82c  xor     r8d, r8d; pcbe
0x18007b82f  mov     rdx, rbx; pv
0x18007b832  lea     rcx, ThreadpoolCallbackHelper__lambda_e101185310aeb88e5f232b9f624b242d_____s_Callback; pfns
0x18007b839  call    cs:__imp_TrySubmitThreadpoolCallback
0x18007b83f  mov     edi, eax
0x18007b841  test    eax, eax
0x18007b843  cmovnz  rbx, rsi
0x18007b847  mov     [rsp+0A8h+var_80], rbx
0x18007b84c  lea     rcx, [rsp+0A8h+var_80]
0x18007b851  call    std__unique_ptr_ThreadpoolCallbackHelper__lambda_e6d1bad9febbf826e25b795528038c48____std__default_delete_ThreadpoolCallbackHelper__lambda_e6d1bad9febbf826e25b795528038c48__________unique_ptr_ThreadpoolCallbackHelper__lambda_e6d1bad9febbf826e25b795528038c48____std__default_delete_ThreadpoolCallbackHelper__lambda_e6d1bad9febbf826e25b795528038c48_______
0x18007b856  nop
0x18007b857  mov     rcx, [rsp+0A8h]; this
0x18007b85f  test    edi, edi
0x18007b861  jz      short loc_18007B8B1
0x18007b863  inc     r14
0x18007b866  mov     [rsp+0A8h+var_80], r14
0x18007b86b  mov     rbx, [rsp+0A8h+var_78]
0x18007b870  cmp     r14, r13
0x18007b873  jb      loc_18007B7D0
0x18007b879  mov     rdi, [rsp+0A8h+var_70]
0x18007b87e  mov     rcx, [r12]
0x18007b882  lea     rax, ds:0[r14*4]
0x18007b88a  cmp     rcx, [r12+8]
0x18007b88f  mov     rdx, r14
0x18007b892  jz      short loc_18007B898
0x18007b894  movsxd  rdx, dword ptr [rcx+rax]
0x18007b898  mov     dword ptr [rsp+rax+0A8h+var_58], esi
0x18007b89c  shl     rdx, 4
0x18007b8a0  add     rdx, rbx
0x18007b8a3  mov     r8, r14
0x18007b8a6  mov     rcx, rdi
0x18007b8a9  call    _lambda_45542bfbb88712902d85e11feab4ad5e___operator__
0x18007b8ae  nop
0x18007b8af  jmp     short loc_18007B8E6
0x18007b8b1  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\webplatstorageser"...
0x18007b8b8  mov     edx, 6Dh ; 'm'; void *
0x18007b8bd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18007b8c3  xor     esi, esi
0x18007b8c5  mov     r15, [rsp+0A8h+var_60]
0x18007b8ca  jmp     short loc_18007B8E6
0x18007b8cc  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18007b8d0  mov     r8d, 4; AddressSize
0x18007b8d6  lea     rdx, [rsp+0A8h+CompareAddress]; CompareAddress
0x18007b8db  lea     rcx, [rsp+0A8h+Address]; Address
0x18007b8e0  call    cs:__imp_WaitOnAddress
0x18007b8e6  mov     eax, [rsp+0A8h+Address]
0x18007b8ea  test    eax, eax
0x18007b8ec  mov     [rsp+0A8h+CompareAddress], eax
0x18007b8f0  jnz     short loc_18007B8CC
0x18007b8f2  mov     rax, rsi
0x18007b8f5  test    r15, r15
0x18007b8f8  jz      short loc_18007B914
0x18007b8fa  mov     r9d, dword ptr [rsp+rax*4+0A8h+var_58]; char *
0x18007b8ff  mov     rcx, [rsp+0A8h]; this
0x18007b907  test    r9d, r9d
0x18007b90a  js      short loc_18007B931
0x18007b90c  inc     rax
0x18007b90f  cmp     rax, r15
0x18007b912  jb      short loc_18007B8FA
0x18007b914  mov     rcx, [rsp+0A8h+var_40]
0x18007b919  xor     rcx, rsp; StackCookie
0x18007b91c  call    __security_check_cookie
0x18007b921  add     rsp, 70h
0x18007b925  pop     r15
0x18007b927  pop     r14
0x18007b929  pop     r13
0x18007b92b  pop     r12
0x18007b92d  pop     rdi
0x18007b92e  pop     rsi
0x18007b92f  pop     rbx
0x18007b930  retn
0x18007b931  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\webplatstorageser"...
0x18007b938  mov     edx, 86h; void *
0x18007b93d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
