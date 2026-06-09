# CLocalAccounts::Advise(IComputerAccountNotify *,ulong *)

- ea: `0x18000f410`
- end: `0x18000f5bb`
- name: `?Advise@CLocalAccounts@@UEAAJPEAUIComputerAccountNotify@@PEAK@Z`
- size: `427`
- prototype: `__int64 __fastcall(CLocalAccounts *__hidden this, struct IComputerAccountNotify *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000f410`
- `0x180011948`
- `0x180012ee8`
- `0x180012f18`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f4b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f56a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f4b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f56a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f54a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f58a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f54a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f58a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f4a1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f4a1`

## pseudocode

```c
__int64 __fastcall CLocalAccounts::Advise(CLocalAccounts *this, struct IComputerAccountNotify *a2, unsigned int *a3)
{
  HRESULT Instance; // ebx
  _QWORD *v7; // r15
  bool v8; // zf
  unsigned int *v9; // rsi
  __int64 v10; // rax
  int v12; // [rsp+70h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21);
  if ( !a3 || !a2 )
    return (unsigned int)-2147467261;
  if ( *((_DWORD *)this + 11) )
    return (unsigned int)-2147220991;
  v7 = (_QWORD *)((char *)this + 88);
  v8 = *((_QWORD *)this + 11) == 0;
  *((_DWORD *)this + 11) = 1;
  if ( v8 )
  {
    Instance = CoCreateInstance(
                 &CLSID_StdGlobalInterfaceTable,
                 0,
                 1u,
                 &GUID_00000146_0000_0000_c000_000000000046,
                 (LPVOID *)this + 11);
    if ( Instance < 0 )
    {
LABEL_22:
      *((_DWORD *)this + 11) = 0;
      return (unsigned int)Instance;
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v9 = (unsigned int *)((char *)this + 96);
  Instance = (*(__int64 (__fastcall **)(_QWORD, struct IComputerAccountNotify *, GUID *, char *))(*(_QWORD *)*v7 + 24LL))(
               *v7,
               a2,
               &IID_IComputerAccountNotify,
               (char *)this + 96);
  if ( Instance >= 0 )
  {
    v10 = *(_QWORD *)a2;
    v12 = 0;
    Instance = (*(__int64 (__fastcall **)(struct IComputerAccountNotify *, int *))(v10 + 32))(a2, &v12);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
          (unsigned int)Instance);
      Instance = 0;
    }
    else
    {
      *((_DWORD *)this + 10) = v12;
    }
    *a3 = *v9;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( Instance < 0 || (Instance = CLocalAccounts::_RegisterSAMEvent(this), Instance < 0) )
  {
    if ( *v9 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v7 + 32LL))(*v7, *v9);
      *v9 = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    }
    goto LABEL_22;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000f410  mov     [rsp+arg_0], rbx
0x18000f415  mov     [rsp+arg_8], rbp
0x18000f41a  push    rsi
0x18000f41b  push    rdi
0x18000f41c  push    r12
0x18000f41e  push    r14
0x18000f420  push    r15
0x18000f422  sub     rsp, 30h
0x18000f426  mov     rbp, r8
0x18000f429  mov     r14, rdx
0x18000f42c  mov     rdi, rcx
0x18000f42f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f436  lea     rax, WPP_GLOBAL_Control
0x18000f43d  cmp     rcx, rax
0x18000f440  jz      short loc_18000F456
0x18000f442  test    byte ptr [rcx+1Ch], 8
0x18000f446  jz      short loc_18000F456
0x18000f448  mov     rcx, [rcx+10h]
0x18000f44c  mov     edx, 15h
0x18000f451  call    WPP_SF_
0x18000f456  test    rbp, rbp
0x18000f459  jz      loc_18000F59D
0x18000f45f  test    r14, r14
0x18000f462  jz      loc_18000F59D
0x18000f468  cmp     dword ptr [rdi+2Ch], 0
0x18000f46c  jz      short loc_18000F478
0x18000f46e  mov     ebx, 80040201h
0x18000f473  jmp     loc_18000F5A2
0x18000f478  lea     r15, [rdi+58h]
0x18000f47c  mov     r8d, 1; dwClsContext
0x18000f482  cmp     qword ptr [r15], 0
0x18000f486  mov     [rdi+2Ch], r8d
0x18000f48a  jnz     short loc_18000F4B1
0x18000f48c  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000f493  mov     [rsp+58h+ppv], r15; ppv
0x18000f498  xor     edx, edx; pUnkOuter
0x18000f49a  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000f4a1  call    cs:__imp_CoCreateInstance
0x18000f4a7  mov     ebx, eax
0x18000f4a9  test    eax, eax
0x18000f4ab  js      loc_18000F594
0x18000f4b1  lea     r12, [rdi+30h]
0x18000f4b5  mov     rcx, r12; lpCriticalSection
0x18000f4b8  call    cs:__imp_EnterCriticalSection
0x18000f4be  mov     rcx, [r15]
0x18000f4c1  lea     rsi, [rdi+60h]
0x18000f4c5  mov     r9, rsi
0x18000f4c8  lea     r8, IID_IComputerAccountNotify
0x18000f4cf  mov     rdx, r14
0x18000f4d2  mov     rax, [rcx]
0x18000f4d5  mov     rax, [rax+18h]
0x18000f4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4de  mov     ebx, eax
0x18000f4e0  test    eax, eax
0x18000f4e2  js      short loc_18000F547
0x18000f4e4  mov     rax, [r14]
0x18000f4e7  lea     rdx, [rsp+58h+arg_10]
0x18000f4ec  mov     rcx, r14
0x18000f4ef  mov     [rsp+58h+arg_10], 0
0x18000f4f7  mov     rax, [rax+20h]
0x18000f4fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f500  mov     ebx, eax
0x18000f502  test    eax, eax
0x18000f504  js      short loc_18000F50F
0x18000f506  mov     eax, [rsp+58h+arg_10]
0x18000f50a  mov     [rdi+28h], eax
0x18000f50d  jmp     short loc_18000F542
0x18000f50f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f516  lea     rax, WPP_GLOBAL_Control
0x18000f51d  cmp     rcx, rax
0x18000f520  jz      short loc_18000F540
0x18000f522  test    byte ptr [rcx+1Ch], 4
0x18000f526  jz      short loc_18000F540
0x18000f528  mov     rcx, [rcx+10h]
0x18000f52c  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x18000f533  mov     edx, 16h
0x18000f538  mov     r9d, ebx
0x18000f53b  call    WPP_SF_d
0x18000f540  xor     ebx, ebx
0x18000f542  mov     eax, [rsi]
0x18000f544  mov     [rbp+0], eax
0x18000f547  mov     rcx, r12; lpCriticalSection
0x18000f54a  call    cs:__imp_LeaveCriticalSection
0x18000f550  test    ebx, ebx
0x18000f552  js      short loc_18000F562
0x18000f554  mov     rcx, rdi; this
0x18000f557  call    ?_RegisterSAMEvent@CLocalAccounts@@IEAAJXZ; CLocalAccounts::_RegisterSAMEvent(void)
0x18000f55c  mov     ebx, eax
0x18000f55e  test    eax, eax
0x18000f560  jns     short loc_18000F5A2
0x18000f562  cmp     dword ptr [rsi], 0
0x18000f565  jz      short loc_18000F594
0x18000f567  mov     rcx, r12; lpCriticalSection
0x18000f56a  call    cs:__imp_EnterCriticalSection
0x18000f570  mov     rcx, [r15]
0x18000f573  mov     edx, [rsi]
0x18000f575  mov     rax, [rcx]
0x18000f578  mov     rax, [rax+20h]
0x18000f57c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f581  mov     rcx, r12; lpCriticalSection
0x18000f584  mov     dword ptr [rsi], 0
0x18000f58a  call    cs:__imp_LeaveCriticalSection
0x18000f590  test    ebx, ebx
0x18000f592  jns     short loc_18000F5A2
0x18000f594  mov     dword ptr [rdi+2Ch], 0
0x18000f59b  jmp     short loc_18000F5A2
0x18000f59d  mov     ebx, 80004003h
0x18000f5a2  mov     rbp, [rsp+58h+arg_8]
0x18000f5a7  mov     eax, ebx
0x18000f5a9  mov     rbx, [rsp+58h+arg_0]
0x18000f5ae  add     rsp, 30h
0x18000f5b2  pop     r15
0x18000f5b4  pop     r14
0x18000f5b6  pop     r12
0x18000f5b8  pop     rdi
0x18000f5b9  pop     rsi
0x18000f5ba  retn
```
