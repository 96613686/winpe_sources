# StorageHandlers::RunAll__lambda_ef9085e9686c1e181023a007d8fadb80__std::shared_ptr_IWebPlatStorageSchemaCleanUpCallback__&_

- ea: `0x18006b324`
- end: `0x18006b565`
- name: `StorageHandlers::RunAll__lambda_ef9085e9686c1e181023a007d8fadb80__std::shared_ptr_IWebPlatStorageSchemaCleanUpCallback__&_`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006b1a8`

## callees

- `0x18000f2b0`
- `0x18002f680`
- `0x180061c90`
- `0x180066010`
- `0x18006b324`
- `0x18006b56c`
- `0x18006b60c`
- `0x180080fb0`
- `0x1800814bc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18006b4ff`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18006b4ff`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18006b446`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18006b446`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall StorageHandlers::RunAll__lambda_ef9085e9686c1e181023a007d8fadb80__std::shared_ptr_IWebPlatStorageSchemaCleanUpCallback____(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  __int64 v5; // rdi
  __int64 v7; // rbx
  unsigned __int64 v8; // r15
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // rax
  __int64 v11; // rdi
  _QWORD *v12; // rbx
  BOOL v13; // edi
  const char *v14; // r9
  _QWORD *v15; // rax
  __int64 v16; // r10
  wil *v17; // rcx
  unsigned __int64 result; // rax
  const char *v19; // r9
  unsigned int v20; // eax
  int Address; // [rsp+20h] [rbp-98h] BYREF
  int CompareAddress; // [rsp+24h] [rbp-94h] BYREF
  unsigned __int64 v23; // [rsp+28h] [rbp-90h] BYREF
  __int64 v24; // [rsp+30h] [rbp-88h]
  __int64 v25; // [rsp+38h] [rbp-80h] BYREF
  _QWORD *v26; // [rsp+48h] [rbp-70h]
  const wchar_t *v27; // [rsp+50h] [rbp-68h] BYREF
  unsigned __int64 v28; // [rsp+58h] [rbp-60h]
  unsigned int v29[6]; // [rsp+60h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v5 = a3;
  v25 = a3;
  v7 = a1;
  v24 = a1;
  v26 = a5;
  v27 = L"RunAll CleanUpOldSchemaVersions";
  v8 = (__int64)(a2[1] - *a2) >> 2;
  if ( v8 > 5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\storagehandlers.cxx",
      (const char *)0x80070057LL,
      Address);
  if ( !v8 )
    v8 = 5;
  v28 = v8;
  Address = wil::safe_cast_failfast<unsigned int,unsigned __int64,0>(v8 - 1);
  v9 = 0;
  v23 = 0;
  if ( v8 != 1 )
  {
    do
    {
      v29[v9] = 0;
      if ( *a2 == a2[1] )
        v10 = v9;
      else
        v10 = *(int *)(*a2 + 4 * v9);
      v11 = v7 + 16 * v10;
      v12 = operator new(0x38u);
      *v12 = &v29[v9];
      v12[1] = v11;
      v12[2] = v9;
      v12[3] = &v27;
      v12[4] = v25;
      v12[5] = v26;
      v12[6] = &Address;
      v13 = TrySubmitThreadpoolCallback(
              ThreadpoolCallbackHelper__lambda_a424e02ec6a047514c0e1e5458ad713d___::s_Callback,
              v12,
              0);
      if ( v13 )
        v12 = 0;
      v23 = (unsigned __int64)v12;
      std::unique_ptr_ThreadpoolCallbackHelper__lambda_a424e02ec6a047514c0e1e5458ad713d____std::default_delete_ThreadpoolCallbackHelper__lambda_a424e02ec6a047514c0e1e5458ad713d_______::_unique_ptr_ThreadpoolCallbackHelper__lambda_a424e02ec6a047514c0e1e5458ad713d____std::default_delete_ThreadpoolCallbackHelper__lambda_a424e02ec6a047514c0e1e5458ad713d_______(&v23);
      if ( !v13 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x6D,
          (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\storagehandlers.cxx",
          v14);
      v23 = ++v9;
      v7 = v24;
    }
    while ( v9 < v8 - 1 );
    v5 = v25;
  }
  v29[v9] = 0;
  v15 = std::shared_ptr<std::deque<__int64>>::shared_ptr<std::deque<__int64>>(&v25, v26);
  try
  {
    lambda_ef9085e9686c1e181023a007d8fadb80_::operator()(v5, v7 + 16 * v16, v9, v15);
  }
  catch ( ... )
  {
    v20 = wil::ResultFromCaughtException(v17);
    v29[v23] = v20;
    v8 = v28;
  }
  while ( 1 )
  {
    CompareAddress = Address;
    if ( !Address )
      break;
    WaitOnAddress(&Address, &CompareAddress, 4u, 0xFFFFFFFF);
  }
  for ( result = 0; result < v8; ++result )
  {
    v19 = (const char *)v29[result];
    if ( (int)v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\storagehandlers.cxx",
        v19,
        Address);
  }
  return result;
}

```

## disassembly

```asm
0x18006b324  push    rbx
0x18006b326  push    rsi
0x18006b327  push    rdi
0x18006b328  push    r12
0x18006b32a  push    r13
0x18006b32c  push    r14
0x18006b32e  push    r15
0x18006b330  sub     rsp, 80h
0x18006b337  mov     rax, cs:__security_cookie
0x18006b33e  xor     rax, rsp
0x18006b341  mov     [rsp+0B8h+var_40], rax
0x18006b346  mov     rdi, r8
0x18006b349  mov     [rsp+0B8h+var_80], r8
0x18006b34e  mov     r12, rdx
0x18006b351  mov     rbx, rcx
0x18006b354  mov     [rsp+0B8h+var_88], rcx
0x18006b359  mov     rax, [rsp+0B8h+arg_20]
0x18006b361  mov     [rsp+0B8h+var_70], rax
0x18006b366  lea     rax, aRunallCleanupo; "RunAll CleanUpOldSchemaVersions"
0x18006b36d  mov     [rsp+0B8h+var_68], rax
0x18006b372  mov     r15, [rdx+8]
0x18006b376  sub     r15, [rdx]
0x18006b379  sar     r15, 2
0x18006b37d  mov     rcx, [rsp+0B8h]; this
0x18006b385  mov     eax, 5
0x18006b38a  cmp     r15, rax
0x18006b38d  jbe     short loc_18006B3A5
0x18006b38f  mov     r9d, 80070057h; char *
0x18006b395  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\webplatstorageser"...
0x18006b39c  lea     edx, [rax+44h]; void *
0x18006b39f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006b3a5  xor     esi, esi
0x18006b3a7  test    r15, r15
0x18006b3aa  cmovz   r15, rax
0x18006b3ae  mov     [rsp+0B8h+var_60], r15
0x18006b3b3  lea     r13, [r15-1]
0x18006b3b7  mov     rcx, r13
0x18006b3ba  call    ??$safe_cast_failfast@I_K$0A@@wil@@YAI_K@Z; wil::safe_cast_failfast<uint,unsigned __int64,0>(unsigned __int64)
0x18006b3bf  mov     [rsp+0B8h+Address], eax
0x18006b3c3  mov     r14d, esi
0x18006b3c6  mov     [rsp+0B8h+var_90], rsi
0x18006b3cb  test    r13, r13
0x18006b3ce  jz      loc_18006B48B
0x18006b3d4  mov     [rsp+r14*4+0B8h+var_58], esi
0x18006b3d9  mov     rax, [r12]
0x18006b3dd  cmp     rax, [r12+8]
0x18006b3e2  jnz     short loc_18006B3E9
0x18006b3e4  mov     rax, r14
0x18006b3e7  jmp     short loc_18006B3ED
0x18006b3e9  movsxd  rax, dword ptr [rax+r14*4]
0x18006b3ed  add     rax, rax
0x18006b3f0  lea     rdi, [rbx+rax*8]
0x18006b3f4  mov     ecx, 38h ; '8'; Size
0x18006b3f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b3fe  mov     rbx, rax
0x18006b401  lea     rax, [rsp+0B8h+var_58]
0x18006b406  lea     rax, [rax+r14*4]
0x18006b40a  mov     [rbx], rax
0x18006b40d  mov     [rbx+8], rdi
0x18006b411  mov     [rbx+10h], r14
0x18006b415  lea     rax, [rsp+0B8h+var_68]
0x18006b41a  mov     [rbx+18h], rax
0x18006b41e  mov     rax, [rsp+0B8h+var_80]
0x18006b423  mov     [rbx+20h], rax
0x18006b427  mov     rax, [rsp+0B8h+var_70]
0x18006b42c  mov     [rbx+28h], rax
0x18006b430  lea     rax, [rsp+0B8h+Address]
0x18006b435  mov     [rbx+30h], rax
0x18006b439  xor     r8d, r8d; pcbe
0x18006b43c  mov     rdx, rbx; pv
0x18006b43f  lea     rcx, ThreadpoolCallbackHelper__lambda_a424e02ec6a047514c0e1e5458ad713d_____s_Callback; pfns
0x18006b446  call    cs:__imp_TrySubmitThreadpoolCallback
0x18006b44c  mov     edi, eax
0x18006b44e  test    eax, eax
0x18006b450  cmovnz  rbx, rsi
0x18006b454  mov     [rsp+0B8h+var_90], rbx
0x18006b459  lea     rcx, [rsp+0B8h+var_90]
0x18006b45e  call    std__unique_ptr_ThreadpoolCallbackHelper__lambda_a424e02ec6a047514c0e1e5458ad713d____std__default_delete_ThreadpoolCallbackHelper__lambda_a424e02ec6a047514c0e1e5458ad713d__________unique_ptr_ThreadpoolCallbackHelper__lambda_a424e02ec6a047514c0e1e5458ad713d____std__default_delete_ThreadpoolCallbackHelper__lambda_a424e02ec6a047514c0e1e5458ad713d_______
0x18006b463  nop
0x18006b464  mov     rcx, [rsp+0B8h]; this
0x18006b46c  test    edi, edi
0x18006b46e  jz      short loc_18006B4D0
0x18006b470  inc     r14
0x18006b473  mov     [rsp+0B8h+var_90], r14
0x18006b478  mov     rbx, [rsp+0B8h+var_88]
0x18006b47d  cmp     r14, r13
0x18006b480  jb      loc_18006B3D4
0x18006b486  mov     rdi, [rsp+0B8h+var_80]
0x18006b48b  mov     rcx, [r12]
0x18006b48f  lea     rax, ds:0[r14*4]
0x18006b497  cmp     rcx, [r12+8]
0x18006b49c  mov     r10, r14
0x18006b49f  jz      short loc_18006B4A5
0x18006b4a1  movsxd  r10, dword ptr [rcx+rax]
0x18006b4a5  mov     [rsp+rax+0B8h+var_58], esi
0x18006b4a9  mov     rdx, [rsp+0B8h+var_70]
0x18006b4ae  lea     rcx, [rsp+0B8h+var_80]
0x18006b4b3  call    ??0?$shared_ptr@V?$deque@_JV?$allocator@_J@std@@@std@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<std::deque<__int64>>::shared_ptr<std::deque<__int64>>(std::shared_ptr<std::deque<__int64>> const &)
0x18006b4b8  add     r10, r10
0x18006b4bb  lea     rdx, [rbx+r10*8]
0x18006b4bf  mov     r9, rax
0x18006b4c2  mov     r8, r14
0x18006b4c5  mov     rcx, rdi
0x18006b4c8  call    _lambda_ef9085e9686c1e181023a007d8fadb80___operator__
0x18006b4cd  nop
0x18006b4ce  jmp     short loc_18006B505
0x18006b4d0  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\webplatstorageser"...
0x18006b4d7  mov     edx, 6Dh ; 'm'; void *
0x18006b4dc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18006b4e2  xor     esi, esi
0x18006b4e4  mov     r15, [rsp+0B8h+var_60]
0x18006b4e9  jmp     short loc_18006B505
0x18006b4eb  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18006b4ef  mov     r8d, 4; AddressSize
0x18006b4f5  lea     rdx, [rsp+0B8h+CompareAddress]; CompareAddress
0x18006b4fa  lea     rcx, [rsp+0B8h+Address]; Address
0x18006b4ff  call    cs:__imp_WaitOnAddress
0x18006b505  mov     eax, [rsp+0B8h+Address]
0x18006b509  test    eax, eax
0x18006b50b  mov     [rsp+0B8h+CompareAddress], eax
0x18006b50f  jnz     short loc_18006B4EB
0x18006b511  mov     rax, rsi
0x18006b514  test    r15, r15
0x18006b517  jz      short loc_18006B533
0x18006b519  mov     r9d, [rsp+rax*4+0B8h+var_58]; char *
0x18006b51e  mov     rcx, [rsp+0B8h]; this
0x18006b526  test    r9d, r9d
0x18006b529  js      short loc_18006B553
0x18006b52b  inc     rax
0x18006b52e  cmp     rax, r15
0x18006b531  jb      short loc_18006B519
0x18006b533  mov     rcx, [rsp+0B8h+var_40]
0x18006b538  xor     rcx, rsp; StackCookie
0x18006b53b  call    __security_check_cookie
0x18006b540  add     rsp, 80h
0x18006b547  pop     r15
0x18006b549  pop     r14
0x18006b54b  pop     r13
0x18006b54d  pop     r12
0x18006b54f  pop     rdi
0x18006b550  pop     rsi
0x18006b551  pop     rbx
0x18006b552  retn
0x18006b553  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\webplatstorageser"...
0x18006b55a  mov     edx, 86h; void *
0x18006b55f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
