# StorageHandlers::RunAll__lambda_e8d28ca750a9c9327fa99dce11873ad8___

- ea: `0x1800724a4`
- end: `0x1800726b2`
- name: `StorageHandlers::RunAll__lambda_e8d28ca750a9c9327fa99dce11873ad8___`
- size: `526`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800722f0`

## callees

- `0x18000f2b0`
- `0x180061c90`
- `0x180066010`
- `0x18006bf64`
- `0x1800724a4`
- `0x180080fb0`
- `0x1800814bc`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18007264f`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18007264f`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800725ad`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800725ad`

## string_xrefs

- `0x1800724d2`: `RunAll OnDeleteAllDatabases`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall StorageHandlers::RunAll__lambda_e8d28ca750a9c9327fa99dce11873ad8___(
        __int64 a1,
        _QWORD *a2,
        char a3)
{
  __int64 v4; // rbx
  unsigned __int64 v5; // r15
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rax
  __int64 v8; // rdi
  _QWORD *v9; // rbx
  BOOL v10; // edi
  const char *v11; // r9
  __int64 v12; // rax
  wil *v13; // rcx
  unsigned __int64 result; // rax
  const char *v15; // r9
  unsigned int v16; // eax
  int Address; // [rsp+20h] [rbp-88h] BYREF
  int CompareAddress; // [rsp+24h] [rbp-84h] BYREF
  unsigned __int64 v19; // [rsp+28h] [rbp-80h] BYREF
  __int64 v20; // [rsp+30h] [rbp-78h]
  const wchar_t *v21; // [rsp+38h] [rbp-70h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-68h]
  unsigned int v23[6]; // [rsp+48h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  char v25; // [rsp+C0h] [rbp+18h] BYREF

  v25 = a3;
  v4 = a1;
  v20 = a1;
  v21 = L"RunAll OnDeleteAllDatabases";
  v5 = (__int64)(a2[1] - *a2) >> 2;
  if ( v5 > 5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\storagehandlers.cxx",
      (const char *)0x80070057LL,
      Address);
  if ( !v5 )
    v5 = 5;
  v22 = v5;
  Address = wil::safe_cast_failfast<unsigned int,unsigned __int64,0>(v5 - 1);
  v6 = 0;
  v19 = 0;
  if ( v5 != 1 )
  {
    do
    {
      v23[v6] = 0;
      if ( *a2 == a2[1] )
        v7 = v6;
      else
        v7 = *(int *)(*a2 + 4 * v6);
      v8 = v4 + 16 * v7;
      v9 = operator new(0x30u);
      *v9 = &v23[v6];
      v9[1] = v8;
      v9[2] = v6;
      v9[3] = &v21;
      v9[4] = &v25;
      v9[5] = &Address;
      v10 = TrySubmitThreadpoolCallback(
              ThreadpoolCallbackHelper__lambda_3f14a2d1982b784bad8d1a0ea2306c39___::s_Callback,
              v9,
              0);
      if ( v10 )
        v9 = 0;
      v19 = (unsigned __int64)v9;
      std::unique_ptr_ThreadpoolCallbackHelper__lambda_e6d1bad9febbf826e25b795528038c48____std::default_delete_ThreadpoolCallbackHelper__lambda_e6d1bad9febbf826e25b795528038c48_______::_unique_ptr_ThreadpoolCallbackHelper__lambda_e6d1bad9febbf826e25b795528038c48____std::default_delete_ThreadpoolCallbackHelper__lambda_e6d1bad9febbf826e25b795528038c48_______(&v19);
      if ( !v10 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x6D,
          (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\storagehandlers.cxx",
          v11);
      v19 = ++v6;
      v4 = v20;
    }
    while ( v6 < v5 - 1 );
  }
  v12 = v6;
  if ( *a2 != a2[1] )
    v6 = *(int *)(*a2 + 4 * v6);
  try
  {
    v23[v12] = 0;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 16 * v6) + 40LL))(*(_QWORD *)(v4 + 16 * v6));
  }
  catch ( ... )
  {
    v16 = wil::ResultFromCaughtException(v13);
    v23[v19] = v16;
    v5 = v22;
  }
  while ( 1 )
  {
    CompareAddress = Address;
    if ( !Address )
      break;
    WaitOnAddress(&Address, &CompareAddress, 4u, 0xFFFFFFFF);
  }
  for ( result = 0; result < v5; ++result )
  {
    v15 = (const char *)v23[result];
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
0x1800724a4  mov     [rsp+arg_10], r8b
0x1800724a9  push    rbx
0x1800724aa  push    rsi
0x1800724ab  push    rdi
0x1800724ac  push    r12
0x1800724ae  push    r13
0x1800724b0  push    r14
0x1800724b2  push    r15
0x1800724b4  sub     rsp, 70h
0x1800724b8  mov     rax, cs:__security_cookie
0x1800724bf  xor     rax, rsp
0x1800724c2  mov     [rsp+0A8h+var_48], rax
0x1800724c7  mov     r12, rdx
0x1800724ca  mov     rbx, rcx
0x1800724cd  mov     [rsp+0A8h+var_78], rcx
0x1800724d2  lea     rax, aRunallOndelete; "RunAll OnDeleteAllDatabases"
0x1800724d9  mov     [rsp+0A8h+var_70], rax
0x1800724de  mov     r15, [rdx+8]
0x1800724e2  sub     r15, [rdx]
0x1800724e5  sar     r15, 2
0x1800724e9  mov     rcx, [rsp+0A8h]; this
0x1800724f1  mov     eax, 5
0x1800724f6  cmp     r15, rax
0x1800724f9  jbe     short loc_180072511
0x1800724fb  mov     r9d, 80070057h; char *
0x180072501  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\webplatstorageser"...
0x180072508  lea     edx, [rax+44h]; void *
0x18007250b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072511  xor     r14d, r14d
0x180072514  test    r15, r15
0x180072517  cmovz   r15, rax
0x18007251b  mov     [rsp+0A8h+var_68], r15
0x180072520  lea     r13, [r15-1]
0x180072524  mov     rcx, r13
0x180072527  call    ??$safe_cast_failfast@I_K$0A@@wil@@YAI_K@Z; wil::safe_cast_failfast<uint,unsigned __int64,0>(unsigned __int64)
0x18007252c  mov     [rsp+0A8h+Address], eax
0x180072530  mov     esi, r14d
0x180072533  mov     [rsp+0A8h+var_80], r14
0x180072538  test    r13, r13
0x18007253b  jz      loc_1800725ED
0x180072541  mov     [rsp+rsi*4+0A8h+var_60], r14d
0x180072546  mov     rax, [r12]
0x18007254a  cmp     rax, [r12+8]
0x18007254f  jnz     short loc_180072556
0x180072551  mov     rax, rsi
0x180072554  jmp     short loc_18007255A
0x180072556  movsxd  rax, dword ptr [rax+rsi*4]
0x18007255a  add     rax, rax
0x18007255d  lea     rdi, [rbx+rax*8]
0x180072561  mov     ecx, 30h ; '0'; Size
0x180072566  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007256b  mov     rbx, rax
0x18007256e  lea     rax, [rsp+0A8h+var_60]
0x180072573  lea     rax, [rax+rsi*4]
0x180072577  mov     [rbx], rax
0x18007257a  mov     [rbx+8], rdi
0x18007257e  mov     [rbx+10h], rsi
0x180072582  lea     rax, [rsp+0A8h+var_70]
0x180072587  mov     [rbx+18h], rax
0x18007258b  lea     rax, [rsp+0A8h+arg_10]
0x180072593  mov     [rbx+20h], rax
0x180072597  lea     rax, [rsp+0A8h+Address]
0x18007259c  mov     [rbx+28h], rax
0x1800725a0  xor     r8d, r8d; pcbe
0x1800725a3  mov     rdx, rbx; pv
0x1800725a6  lea     rcx, ThreadpoolCallbackHelper__lambda_3f14a2d1982b784bad8d1a0ea2306c39_____s_Callback; pfns
0x1800725ad  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800725b3  mov     edi, eax
0x1800725b5  test    eax, eax
0x1800725b7  cmovnz  rbx, r14
0x1800725bb  mov     [rsp+0A8h+var_80], rbx
0x1800725c0  lea     rcx, [rsp+0A8h+var_80]
0x1800725c5  call    std__unique_ptr_ThreadpoolCallbackHelper__lambda_e6d1bad9febbf826e25b795528038c48____std__default_delete_ThreadpoolCallbackHelper__lambda_e6d1bad9febbf826e25b795528038c48__________unique_ptr_ThreadpoolCallbackHelper__lambda_e6d1bad9febbf826e25b795528038c48____std__default_delete_ThreadpoolCallbackHelper__lambda_e6d1bad9febbf826e25b795528038c48_______
0x1800725ca  nop
0x1800725cb  mov     rcx, [rsp+0A8h]; this
0x1800725d3  test    edi, edi
0x1800725d5  jz      short loc_18007261F
0x1800725d7  inc     rsi
0x1800725da  mov     [rsp+0A8h+var_80], rsi
0x1800725df  mov     rbx, [rsp+0A8h+var_78]
0x1800725e4  cmp     rsi, r13
0x1800725e7  jb      loc_180072541
0x1800725ed  mov     rcx, [r12]
0x1800725f1  lea     rax, ds:0[rsi*4]
0x1800725f9  cmp     rcx, [r12+8]
0x1800725fe  jz      short loc_180072604
0x180072600  movsxd  rsi, dword ptr [rcx+rax]
0x180072604  mov     [rsp+rax+0A8h+var_60], r14d
0x180072609  add     rsi, rsi
0x18007260c  mov     rcx, [rbx+rsi*8]
0x180072610  mov     rax, [rcx]
0x180072613  mov     rax, [rax+28h]
0x180072617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007261c  nop
0x18007261d  jmp     short loc_180072655
0x18007261f  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\webplatstorageser"...
0x180072626  mov     edx, 6Dh ; 'm'; void *
0x18007262b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180072631  xor     r14d, r14d
0x180072634  mov     r15, [rsp+0A8h+var_68]
0x180072639  jmp     short loc_180072655
0x18007263b  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18007263f  mov     r8d, 4; AddressSize
0x180072645  lea     rdx, [rsp+0A8h+CompareAddress]; CompareAddress
0x18007264a  lea     rcx, [rsp+0A8h+Address]; Address
0x18007264f  call    cs:__imp_WaitOnAddress
0x180072655  mov     eax, [rsp+0A8h+Address]
0x180072659  test    eax, eax
0x18007265b  mov     [rsp+0A8h+CompareAddress], eax
0x18007265f  jnz     short loc_18007263B
0x180072661  mov     rax, r14
0x180072664  test    r15, r15
0x180072667  jz      short loc_180072683
0x180072669  mov     r9d, [rsp+rax*4+0A8h+var_60]; char *
0x18007266e  mov     rcx, [rsp+0A8h]; this
0x180072676  test    r9d, r9d
0x180072679  js      short loc_1800726A0
0x18007267b  inc     rax
0x18007267e  cmp     rax, r15
0x180072681  jb      short loc_180072669
0x180072683  mov     rcx, [rsp+0A8h+var_48]
0x180072688  xor     rcx, rsp; StackCookie
0x18007268b  call    __security_check_cookie
0x180072690  add     rsp, 70h
0x180072694  pop     r15
0x180072696  pop     r14
0x180072698  pop     r13
0x18007269a  pop     r12
0x18007269c  pop     rdi
0x18007269d  pop     rsi
0x18007269e  pop     rbx
0x18007269f  retn
0x1800726a0  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\webplatstorageser"...
0x1800726a7  mov     edx, 86h; void *
0x1800726ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
