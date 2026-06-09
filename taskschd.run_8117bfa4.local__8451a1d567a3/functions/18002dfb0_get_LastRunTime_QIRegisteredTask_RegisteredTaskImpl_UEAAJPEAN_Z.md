# ?get_LastRunTime@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAN@Z

- ea: `0x18002dfb0`
- end: `0x18002e19f`
- name: `?get_LastRunTime@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAN@Z`
- size: `495`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001880`
- `0x18002dfb0`
- `0x18002e1a8`
- `0x18002e274`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e045`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e0cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e045`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e0cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e00b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e00b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall _get_LastRunTime__QIRegisteredTask__RegisteredTaskImpl__UEAAJPEAN_Z(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rdi
  const unsigned __int16 *v5; // rdx
  int LastRunInfo; // ebx
  RpcSession *v8; // rcx
  int v9; // eax
  bool v10; // zf
  unsigned int v11; // [rsp+34h] [rbp-44h] BYREF
  __int64 v12; // [rsp+38h] [rbp-40h] BYREF
  int v13; // [rsp+40h] [rbp-38h]
  __int64 v14; // [rsp+48h] [rbp-30h]
  struct _SYSTEMTIME v15; // [rsp+50h] [rbp-28h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v15 = 0;
  v11 = 0;
  v4 = (a1 + 16) & -(__int64)(a1 != 0);
  if ( v4 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  v14 = v4;
  v5 = (const unsigned __int16 *)(a1 + 80);
  if ( *(_QWORD *)(a1 + 104) >= 8u )
    v5 = *(const unsigned __int16 **)v5;
  if ( !*(_DWORD *)(a1 + 128) )
  {
    LastRunInfo = -2147023645;
    goto LABEL_8;
  }
  v8 = *(RpcSession **)(a1 + 136);
  if ( v8 )
  {
    LastRunInfo = RpcSession::GetLastRunInfo(v8, v5, &v15, &v11);
  }
  else
  {
    if ( v5 && *v5 == 92 )
      ++v5;
    v12 = 0;
    LastRunInfo = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, GUID *, __int64 *))(**(_QWORD **)(a1 + 144)
                                                                                                 + 48LL))(
                    *(_QWORD *)(a1 + 144),
                    v5,
                    &GUID_148bd524_a2ab_11ce_b11f_00aa00530503,
                    &v12);
    if ( LastRunInfo < 0
      || (LastRunInfo = (*(__int64 (__fastcall **)(__int64, struct _SYSTEMTIME *))(*(_QWORD *)v12 + 120LL))(v12, &v15),
          LastRunInfo < 0) )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
      goto LABEL_8;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v12 + 136LL))(v12, &v11);
    v10 = LastRunInfo == 267011;
    LastRunInfo = v9;
    if ( v10 && v9 < 0 )
    {
      v11 = (unsigned __int16)v9;
      LastRunInfo = 267011;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  }
  if ( LastRunInfo < 0 )
  {
LABEL_8:
    if ( v4 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
    return (unsigned int)LastRunInfo;
  }
  v12 = 0;
  v13 = 0;
  ATL::AtlConvertSystemTimeToVariantTime(&v15, (double *)&v12);
  *a2 = v12;
  if ( v4 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  return (unsigned int)LastRunInfo;
}

```

## disassembly

```asm
0x18002dfb0  mov     [rsp+arg_10], rbx
0x18002dfb5  mov     [rsp+arg_18], rsi
0x18002dfba  push    rdi
0x18002dfbb  sub     rsp, 70h
0x18002dfbf  mov     rax, cs:__security_cookie
0x18002dfc6  xor     rax, rsp
0x18002dfc9  mov     [rsp+78h+var_18], rax
0x18002dfce  mov     rsi, rdx
0x18002dfd1  mov     rbx, rcx
0x18002dfd4  test    rdx, rdx
0x18002dfd7  jz      loc_18002E0E0
0x18002dfdd  mov     [rsp+78h+var_48], 0
0x18002dfe5  xorps   xmm0, xmm0
0x18002dfe8  movups  xmmword ptr [rsp+78h+var_28.wYear], xmm0
0x18002dfed  mov     [rsp+78h+var_44], 0
0x18002dff5  mov     rax, rcx
0x18002dff8  add     rcx, 10h
0x18002dffc  neg     rax
0x18002dfff  sbb     rdi, rdi
0x18002e002  and     rdi, rcx
0x18002e005  jz      short loc_18002E017
0x18002e007  lea     rcx, [rdi+8]; lpCriticalSection
0x18002e00b  call    cs:__imp_EnterCriticalSection
0x18002e012  nop     dword ptr [rax+rax+00h]
0x18002e017  mov     [rsp+78h+var_30], rdi
0x18002e01c  lea     rdx, [rbx+50h]
0x18002e020  cmp     qword ptr [rdx+18h], 8
0x18002e025  jb      short loc_18002E02A
0x18002e027  mov     rdx, [rdx]; unsigned __int16 *
0x18002e02a  cmp     dword ptr [rbx+80h], 0
0x18002e031  jnz     short loc_18002E073
0x18002e033  mov     ebx, 800704E3h
0x18002e038  mov     [rsp+78h+var_48], ebx
0x18002e03c  test    rdi, rdi
0x18002e03f  jz      short loc_18002E051
0x18002e041  lea     rcx, [rdi+8]; lpCriticalSection
0x18002e045  call    cs:__imp_LeaveCriticalSection
0x18002e04c  nop     dword ptr [rax+rax+00h]
0x18002e051  mov     eax, ebx
0x18002e053  mov     rcx, [rsp+78h+var_18]
0x18002e058  xor     rcx, rsp; StackCookie
0x18002e05b  call    __security_check_cookie
0x18002e060  lea     r11, [rsp+78h+var_8]
0x18002e065  mov     rbx, [r11+20h]
0x18002e069  mov     rsi, [r11+28h]
0x18002e06d  mov     rsp, r11
0x18002e070  pop     rdi
0x18002e071  retn
0x18002e073  mov     rcx, [rbx+88h]; this
0x18002e07a  test    rcx, rcx
0x18002e07d  jz      short loc_18002E0EA
0x18002e07f  lea     r9, [rsp+78h+var_44]; unsigned int *
0x18002e084  lea     r8, [rsp+78h+var_28]; struct _SYSTEMTIME *
0x18002e089  call    ?GetLastRunInfo@RpcSession@@QEBAJPEBGPEAU_SYSTEMTIME@@PEAK@Z; RpcSession::GetLastRunInfo(ushort const *,_SYSTEMTIME *,ulong *)
0x18002e08e  mov     ebx, eax
0x18002e090  mov     [rsp+78h+var_48], ebx
0x18002e094  test    ebx, ebx
0x18002e096  js      short loc_18002E03C
0x18002e098  xorps   xmm0, xmm0
0x18002e09b  movsd   [rsp+78h+var_40], xmm0
0x18002e0a1  mov     [rsp+78h+var_38], 0
0x18002e0a9  lea     rdx, [rsp+78h+var_40]; double *
0x18002e0ae  lea     rcx, [rsp+78h+var_28]; struct _SYSTEMTIME *
0x18002e0b3  call    ?AtlConvertSystemTimeToVariantTime@ATL@@YAHAEBU_SYSTEMTIME@@PEAN@Z; ATL::AtlConvertSystemTimeToVariantTime(_SYSTEMTIME const &,double *)
0x18002e0b8  nop
0x18002e0b9  movsd   xmm0, [rsp+78h+var_40]
0x18002e0bf  movsd   qword ptr [rsi], xmm0
0x18002e0c3  test    rdi, rdi
0x18002e0c6  jz      short loc_18002E0D9
0x18002e0c8  lea     rcx, [rdi+8]; lpCriticalSection
0x18002e0cc  call    cs:__imp_LeaveCriticalSection
0x18002e0d3  nop     dword ptr [rax+rax+00h]
0x18002e0d8  nop
0x18002e0d9  mov     eax, ebx
0x18002e0db  jmp     loc_18002E053
0x18002e0e0  mov     eax, 80004003h
0x18002e0e5  jmp     loc_18002E053
0x18002e0ea  test    rdx, rdx
0x18002e0ed  jz      short loc_18002E0F9
0x18002e0ef  cmp     word ptr [rdx], 5Ch ; '\'
0x18002e0f3  jnz     short loc_18002E0F9
0x18002e0f5  add     rdx, 2
0x18002e0f9  mov     [rsp+78h+var_40], 0
0x18002e102  mov     rcx, [rbx+90h]
0x18002e109  mov     rax, [rcx]
0x18002e10c  lea     r9, [rsp+78h+var_40]
0x18002e111  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x18002e118  mov     rax, [rax+30h]
0x18002e11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e121  mov     ebx, eax
0x18002e123  test    eax, eax
0x18002e125  js      short loc_18002E178
0x18002e127  mov     rcx, [rsp+78h+var_40]
0x18002e12c  mov     rax, [rcx]
0x18002e12f  lea     rdx, [rsp+78h+var_28]
0x18002e134  mov     rax, [rax+78h]
0x18002e138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e13d  mov     ebx, eax
0x18002e13f  test    eax, eax
0x18002e141  js      short loc_18002E178
0x18002e143  mov     rcx, [rsp+78h+var_40]
0x18002e148  lea     rdx, [rsp+78h+var_44]
0x18002e14d  mov     rax, [rcx]
0x18002e150  mov     rax, [rax+88h]
0x18002e157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e15c  cmp     ebx, 41303h
0x18002e162  mov     ebx, eax
0x18002e164  jnz     short loc_18002E187
0x18002e166  test    eax, eax
0x18002e168  jns     short loc_18002E187
0x18002e16a  movzx   eax, ax
0x18002e16d  mov     [rsp+78h+var_44], eax
0x18002e171  mov     ebx, 41303h
0x18002e176  jmp     short loc_18002E187
0x18002e178  lea     rcx, [rsp+78h+var_40]
0x18002e17d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e182  jmp     loc_18002E038
0x18002e187  lea     rcx, [rsp+78h+var_40]
0x18002e18c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e191  jmp     loc_18002E090
0x18002e196  mov     ebx, [rsp+78h+var_48]
0x18002e19a  jmp     loc_18002E0D9
```
