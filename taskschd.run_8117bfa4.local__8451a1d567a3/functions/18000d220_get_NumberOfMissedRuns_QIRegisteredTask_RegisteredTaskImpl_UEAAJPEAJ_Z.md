# ?get_NumberOfMissedRuns@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAJ@Z

- ea: `0x18000d220`
- end: `0x18000d6b7`
- name: `?get_NumberOfMissedRuns@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAJ@Z`
- size: `1175`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001880`
- `0x18000cd10`
- `0x18000d220`
- `0x18000deac`
- `0x18002e274`
- `0x1800391c0`
- `0x18003b208`
- `0x18003e88c`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d390`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d3f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d417`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d453`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d390`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d3f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d417`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d453`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d285`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d285`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000d2fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000d2fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d5aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall _get_NumberOfMissedRuns__QIRegisteredTask__RegisteredTaskImpl__UEAAJPEAJ_Z(__int64 a1, _DWORD *a2)
{
  __int64 v4; // rbx
  const unsigned __int16 **v5; // rsi
  const unsigned __int16 *v6; // rdx
  RpcSession *v7; // rcx
  int LastRunInfo; // edi
  __int64 v9; // rcx
  unsigned int v10; // eax
  int v11; // edi
  int v13; // eax
  bool v14; // zf
  void *v15; // rdx
  int v16; // r8d
  unsigned __int16 v17; // cx
  unsigned __int16 v18; // [rsp+44h] [rbp-D4h] BYREF
  __int64 v19; // [rsp+48h] [rbp-D0h] BYREF
  unsigned int v20; // [rsp+50h] [rbp-C8h] BYREF
  void *v21; // [rsp+58h] [rbp-C0h]
  int v22; // [rsp+60h] [rbp-B8h]
  __int64 v23; // [rsp+68h] [rbp-B0h] BYREF
  void **pExceptionObject; // [rsp+70h] [rbp-A8h] BYREF
  char v25; // [rsp+78h] [rbp-A0h]
  __int64 *v26; // [rsp+80h] [rbp-98h]
  __int64 v27; // [rsp+88h] [rbp-90h]
  __int64 v28; // [rsp+90h] [rbp-88h]
  int v29; // [rsp+98h] [rbp-80h]
  __int64 v30; // [rsp+9Ch] [rbp-7Ch]
  _BYTE v31[8]; // [rsp+A8h] [rbp-70h] BYREF
  void (__stdcall *v32)(LPVOID); // [rsp+B0h] [rbp-68h]
  __int64 v33; // [rsp+B8h] [rbp-60h]
  __int64 v34; // [rsp+C0h] [rbp-58h]
  struct _SYSTEMTIME v35; // [rsp+C8h] [rbp-50h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+D8h] [rbp-40h] BYREF

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v35 = 0;
  v20 = 0;
  v4 = (a1 + 16) & -(__int64)(a1 != 0);
  if ( v4 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  v34 = v4;
  v5 = (const unsigned __int16 **)(a1 + 80);
  if ( *(_QWORD *)(a1 + 104) < 8u )
    v6 = (const unsigned __int16 *)(a1 + 80);
  else
    v6 = *v5;
  if ( !*(_DWORD *)(a1 + 128) )
  {
    LastRunInfo = -2147023645;
    goto LABEL_24;
  }
  v7 = *(RpcSession **)(a1 + 136);
  if ( v7 )
  {
    LastRunInfo = RpcSession::GetLastRunInfo(v7, v6, &v35, &v20);
  }
  else
  {
    if ( v6 && *v6 == 92 )
      ++v6;
    v19 = 0;
    LastRunInfo = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, GUID *, __int64 *))(**(_QWORD **)(a1 + 144)
                                                                                                 + 48LL))(
                    *(_QWORD *)(a1 + 144),
                    v6,
                    &GUID_148bd524_a2ab_11ce_b11f_00aa00530503,
                    &v19);
    if ( LastRunInfo < 0
      || (LastRunInfo = (*(__int64 (__fastcall **)(__int64, struct _SYSTEMTIME *))(*(_QWORD *)v19 + 120LL))(v19, &v35),
          LastRunInfo < 0) )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
      goto LABEL_24;
    }
    v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 136LL))(v19, &v20);
    v14 = LastRunInfo == 267011;
    LastRunInfo = v13;
    if ( v14 && v13 < 0 )
    {
      v20 = (unsigned __int16)v13;
      LastRunInfo = 267011;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  }
  if ( LastRunInfo )
  {
LABEL_24:
    if ( v4 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
    return (unsigned int)LastRunInfo;
  }
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  v21 = 0;
  v22 = 0;
  if ( *(_QWORD *)(a1 + 104) >= 8u )
    v5 = (const unsigned __int16 **)*v5;
  if ( *(_DWORD *)(a1 + 128) )
  {
    v9 = *(_QWORD *)(a1 + 136);
    if ( v9 )
    {
      v10 = RpcSession::Runtimes(v9, (_DWORD)v5, (unsigned int)&v35, (unsigned int)&SystemTime);
      v11 = v10;
      if ( v10 == 267012 )
      {
        MIDL_user_free(v21);
        v21 = 0;
        v22 = 0;
        if ( v4 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
        return 0;
      }
      if ( v10 <= 1 )
        goto LABEL_28;
    }
    else
    {
      if ( v5 && *(_WORD *)v5 == 92 )
        v5 = (const unsigned __int16 **)((char *)v5 + 2);
      v19 = 0;
      v11 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 **, GUID *, __int64 *))(**(_QWORD **)(a1 + 144)
                                                                                            + 48LL))(
              *(_QWORD *)(a1 + 144),
              v5,
              &GUID_148bd524_a2ab_11ce_b11f_00aa00530503,
              &v19);
      if ( v11 >= 0 )
      {
        v23 = 0;
        v18 = -1;
        v11 = (*(__int64 (__fastcall **)(__int64, struct _SYSTEMTIME *, _SYSTEMTIME *, unsigned __int16 *, __int64 *))(*(_QWORD *)v19 + 64LL))(
                v19,
                &v35,
                &SystemTime,
                &v18,
                &v23);
        if ( v11 >= 0 )
        {
          v31[0] = 0;
          v32 = CoTaskMemFree;
          v33 = v23;
          v15 = MIDL_user_allocate(16LL * v18);
          v21 = v15;
          if ( !v15 )
          {
            v25 = 0;
            v26 = &qword_18007B2F0;
            v27 = 0;
            v28 = 0;
            v29 = 14;
            v30 = -1;
            pExceptionObject = &wmi::GenericException::`vftable';
            throw (wmi::OutOfMemoryException *)&pExceptionObject;
          }
          v16 = 0;
          v17 = v18;
          if ( v18 )
          {
            while ( 1 )
            {
              *((_OWORD *)v15 + v16) = *(_OWORD *)(v23 + 16LL * v16);
              ++v16;
              v17 = v18;
              if ( v16 >= v18 )
                break;
              v15 = v21;
            }
          }
          v22 = v17;
          wmi::ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>::~ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>(v31);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
          v11 = 0;
LABEL_28:
          *a2 = v22;
          MIDL_user_free(v21);
          v21 = 0;
          v22 = 0;
          if ( v4 )
            LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
          return (unsigned int)v11;
        }
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
    }
  }
  else
  {
    v11 = -2147023645;
  }
  MIDL_user_free(v21);
  v21 = 0;
  v22 = 0;
  if ( v4 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000d220  mov     r11, rsp
0x18000d223  mov     [r11+18h], rbx
0x18000d227  push    rsi
0x18000d228  push    rdi
0x18000d229  push    r12
0x18000d22b  push    r14
0x18000d22d  push    r15
0x18000d22f  sub     rsp, 0F0h
0x18000d236  mov     rax, cs:__security_cookie
0x18000d23d  xor     rax, rsp
0x18000d240  mov     [rsp+118h+var_30], rax
0x18000d248  mov     r15, rdx
0x18000d24b  mov     r14, rcx
0x18000d24e  xor     r12d, r12d
0x18000d251  test    rdx, rdx
0x18000d254  jz      loc_18000D467
0x18000d25a  mov     [rdx], r12d
0x18000d25d  mov     [rsp+118h+var_D8], r12d
0x18000d262  xorps   xmm0, xmm0
0x18000d265  movups  xmmword ptr [r11-50h], xmm0
0x18000d26a  mov     [rsp+118h+var_C8], r12d
0x18000d26f  mov     rax, rcx
0x18000d272  add     rcx, 10h
0x18000d276  neg     rax
0x18000d279  sbb     rbx, rbx
0x18000d27c  and     rbx, rcx
0x18000d27f  jz      short loc_18000D291
0x18000d281  lea     rcx, [rbx+8]; lpCriticalSection
0x18000d285  call    cs:__imp_EnterCriticalSection
0x18000d28c  nop     dword ptr [rax+rax+00h]
0x18000d291  mov     [rsp+118h+var_58], rbx
0x18000d299  lea     rsi, [r14+50h]
0x18000d29d  cmp     qword ptr [rsi+18h], 8
0x18000d2a2  jb      loc_18000D3C7
0x18000d2a8  mov     rdx, [rsi]; unsigned __int16 *
0x18000d2ab  cmp     [r14+80h], r12d
0x18000d2b2  jz      loc_18000D405
0x18000d2b8  mov     rcx, [r14+88h]; this
0x18000d2bf  test    rcx, rcx
0x18000d2c2  jz      loc_18000D471
0x18000d2c8  lea     r9, [rsp+118h+var_C8]; unsigned int *
0x18000d2cd  lea     r8, [rsp+118h+var_50]; struct _SYSTEMTIME *
0x18000d2d5  call    ?GetLastRunInfo@RpcSession@@QEBAJPEBGPEAU_SYSTEMTIME@@PEAK@Z; RpcSession::GetLastRunInfo(ushort const *,_SYSTEMTIME *,ulong *)
0x18000d2da  mov     edi, eax
0x18000d2dc  mov     [rsp+118h+var_D8], edi
0x18000d2e0  test    edi, edi
0x18000d2e2  jnz     loc_18000D40E
0x18000d2e8  xorps   xmm0, xmm0
0x18000d2eb  movups  xmmword ptr [rsp+118h+SystemTime.wYear], xmm0
0x18000d2f3  lea     rcx, [rsp+118h+SystemTime]; lpSystemTime
0x18000d2fb  call    cs:__imp_GetLocalTime
0x18000d302  nop     dword ptr [rax+rax+00h]
0x18000d307  mov     [rsp+118h+var_C0], r12
0x18000d30c  mov     [rsp+118h+var_B8], r12d
0x18000d311  cmp     qword ptr [rsi+18h], 8
0x18000d316  jb      short loc_18000D31B
0x18000d318  mov     rsi, [rsi]
0x18000d31b  cmp     [r14+80h], r12d
0x18000d322  jz      loc_18000D3CF
0x18000d328  mov     rcx, [r14+88h]
0x18000d32f  test    rcx, rcx
0x18000d332  jz      loc_18000D51C
0x18000d338  lea     rax, [rsp+118h+var_C0]
0x18000d33d  mov     [rsp+118h+var_E8], rax
0x18000d342  mov     [rsp+118h+var_F0], 0FFFFFFFFh
0x18000d34a  lea     r9, [rsp+118h+SystemTime]
0x18000d352  lea     r8, [rsp+118h+var_50]
0x18000d35a  mov     rdx, rsi
0x18000d35d  call    ?Runtimes@RpcSession@@QEBAJPEBGPEAU_SYSTEMTIME@@1KKAEAV?$RpcArray@U_SYSTEMTIME@@@@@Z; RpcSession::Runtimes(ushort const *,_SYSTEMTIME *,_SYSTEMTIME *,ulong,ulong,RpcArray<_SYSTEMTIME> &)
0x18000d362  mov     edi, eax
0x18000d364  mov     [rsp+118h+var_D8], eax
0x18000d368  cmp     eax, 41304h
0x18000d36d  jnz     loc_18000D42A
0x18000d373  mov     rcx, [rsp+118h+var_C0]; void *
0x18000d378  call    MIDL_user_free
0x18000d37d  mov     [rsp+118h+var_C0], r12
0x18000d382  mov     [rsp+118h+var_B8], r12d
0x18000d387  test    rbx, rbx
0x18000d38a  jz      short loc_18000D39C
0x18000d38c  lea     rcx, [rbx+8]; lpCriticalSection
0x18000d390  call    cs:__imp_LeaveCriticalSection
0x18000d397  nop     dword ptr [rax+rax+00h]
0x18000d39c  xor     eax, eax
0x18000d39e  mov     rcx, [rsp+118h+var_30]
0x18000d3a6  xor     rcx, rsp; StackCookie
0x18000d3a9  call    __security_check_cookie
0x18000d3ae  mov     rbx, [rsp+118h+arg_10]
0x18000d3b6  add     rsp, 0F0h
0x18000d3bd  pop     r15
0x18000d3bf  pop     r14
0x18000d3c1  pop     r12
0x18000d3c3  pop     rdi
0x18000d3c4  pop     rsi
0x18000d3c5  retn
0x18000d3c7  mov     rdx, rsi
0x18000d3ca  jmp     loc_18000D2AB
0x18000d3cf  mov     edi, 800704E3h
0x18000d3d4  mov     [rsp+118h+var_D8], edi
0x18000d3d8  mov     rcx, [rsp+118h+var_C0]; void *
0x18000d3dd  call    MIDL_user_free
0x18000d3e2  mov     [rsp+118h+var_C0], r12
0x18000d3e7  mov     [rsp+118h+var_B8], r12d
0x18000d3ec  test    rbx, rbx
0x18000d3ef  jz      short loc_18000D401
0x18000d3f1  lea     rcx, [rbx+8]; lpCriticalSection
0x18000d3f5  call    cs:__imp_LeaveCriticalSection
0x18000d3fc  nop     dword ptr [rax+rax+00h]
0x18000d401  mov     eax, edi
0x18000d403  jmp     short loc_18000D39E
0x18000d405  mov     edi, 800704E3h
0x18000d40a  mov     [rsp+118h+var_D8], edi
0x18000d40e  test    rbx, rbx
0x18000d411  jz      short loc_18000D423
0x18000d413  lea     rcx, [rbx+8]; lpCriticalSection
0x18000d417  call    cs:__imp_LeaveCriticalSection
0x18000d41e  nop     dword ptr [rax+rax+00h]
0x18000d423  mov     eax, edi
0x18000d425  jmp     loc_18000D39E
0x18000d42a  cmp     eax, 1
0x18000d42d  ja      short loc_18000D3D8
0x18000d42f  mov     eax, [rsp+118h+var_B8]
0x18000d433  mov     [r15], eax
0x18000d436  mov     rcx, [rsp+118h+var_C0]; void *
0x18000d43b  call    MIDL_user_free
0x18000d440  mov     [rsp+118h+var_C0], r12
0x18000d445  mov     [rsp+118h+var_B8], r12d
0x18000d44a  test    rbx, rbx
0x18000d44d  jz      short loc_18000D460
0x18000d44f  lea     rcx, [rbx+8]; lpCriticalSection
0x18000d453  call    cs:__imp_LeaveCriticalSection
0x18000d45a  nop     dword ptr [rax+rax+00h]
0x18000d45f  nop
0x18000d460  mov     eax, edi
0x18000d462  jmp     loc_18000D39E
0x18000d467  mov     eax, 80004003h
0x18000d46c  jmp     loc_18000D39E
0x18000d471  test    rdx, rdx
0x18000d474  jz      short loc_18000D480
0x18000d476  cmp     word ptr [rdx], 5Ch ; '\'
0x18000d47a  jnz     short loc_18000D480
0x18000d47c  add     rdx, 2
0x18000d480  mov     [rsp+118h+var_D0], r12
0x18000d485  mov     rcx, [r14+90h]
0x18000d48c  mov     rax, [rcx]
0x18000d48f  lea     r9, [rsp+118h+var_D0]
0x18000d494  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x18000d49b  mov     rax, [rax+30h]
0x18000d49f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4a4  mov     edi, eax
0x18000d4a6  test    eax, eax
0x18000d4a8  js      short loc_18000D4FE
0x18000d4aa  mov     rcx, [rsp+118h+var_D0]
0x18000d4af  mov     rax, [rcx]
0x18000d4b2  lea     rdx, [rsp+118h+var_50]
0x18000d4ba  mov     rax, [rax+78h]
0x18000d4be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4c3  mov     edi, eax
0x18000d4c5  test    eax, eax
0x18000d4c7  js      short loc_18000D4FE
0x18000d4c9  mov     rcx, [rsp+118h+var_D0]
0x18000d4ce  lea     rdx, [rsp+118h+var_C8]
0x18000d4d3  mov     rax, [rcx]
0x18000d4d6  mov     rax, [rax+88h]
0x18000d4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4e2  cmp     edi, 41303h
0x18000d4e8  mov     edi, eax
0x18000d4ea  jnz     short loc_18000D50D
0x18000d4ec  test    eax, eax
0x18000d4ee  jns     short loc_18000D50D
0x18000d4f0  movzx   eax, ax
0x18000d4f3  mov     [rsp+118h+var_C8], eax
0x18000d4f7  mov     edi, 41303h
0x18000d4fc  jmp     short loc_18000D50D
0x18000d4fe  lea     rcx, [rsp+118h+var_D0]
0x18000d503  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d508  jmp     loc_18000D40A
0x18000d50d  lea     rcx, [rsp+118h+var_D0]
0x18000d512  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d517  jmp     loc_18000D2DC
0x18000d51c  test    rsi, rsi
0x18000d51f  jz      short loc_18000D52B
0x18000d521  cmp     word ptr [rsi], 5Ch ; '\'
0x18000d525  jnz     short loc_18000D52B
0x18000d527  add     rsi, 2
0x18000d52b  mov     [rsp+118h+var_D0], r12
0x18000d530  mov     rcx, [r14+90h]
0x18000d537  mov     rax, [rcx]
0x18000d53a  lea     r9, [rsp+118h+var_D0]
0x18000d53f  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x18000d546  mov     rdx, rsi
0x18000d549  mov     rax, [rax+30h]
0x18000d54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d552  mov     edi, eax
0x18000d554  test    eax, eax
0x18000d556  js      loc_18000D63D
0x18000d55c  mov     [rsp+118h+var_B0], r12
0x18000d561  mov     eax, 0FFFFh
0x18000d566  mov     [rsp+118h+var_D4], ax
0x18000d56b  mov     rcx, [rsp+118h+var_D0]
0x18000d570  mov     rax, [rcx]
0x18000d573  lea     rdx, [rsp+118h+var_B0]
0x18000d578  mov     [rsp+118h+var_F8], rdx
0x18000d57d  lea     r9, [rsp+118h+var_D4]
0x18000d582  lea     r8, [rsp+118h+SystemTime]
0x18000d58a  lea     rdx, [rsp+118h+var_50]
0x18000d592  mov     rax, [rax+40h]
0x18000d596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d59b  mov     edi, eax
0x18000d59d  test    eax, eax
0x18000d59f  js      loc_18000D63D
0x18000d5a5  mov     rcx, [rsp+118h+var_B0]
0x18000d5aa  mov     rax, cs:__imp_CoTaskMemFree
0x18000d5b1  mov     [rsp+118h+var_70], r12b
0x18000d5b9  mov     [rsp+118h+var_68], rax
0x18000d5c1  mov     [rsp+118h+var_60], rcx
0x18000d5c9  movzx   ecx, [rsp+118h+var_D4]
0x18000d5ce  shl     rcx, 4; size
0x18000d5d2  call    MIDL_user_allocate
0x18000d5d7  mov     rdx, rax
0x18000d5da  mov     [rsp+118h+var_C0], rax
0x18000d5df  test    rax, rax
0x18000d5e2  jnz     short loc_18000D64C
0x18000d5e4  mov     [rsp+118h+var_A0], r12b
0x18000d5e9  lea     rax, qword_18007B2F0
0x18000d5f0  mov     [rsp+118h+var_98], rax
0x18000d5f8  mov     [rsp+118h+var_90], r12
0x18000d600  mov     [rsp+118h+var_88], r12
0x18000d608  mov     [rsp+118h+var_80], 0Eh
0x18000d613  mov     [rsp+118h+var_7C], 0FFFFFFFFFFFFFFFFh
0x18000d61f  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000d626  mov     [rsp+118h+pExceptionObject], rax
0x18000d62b  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18000d632  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18000d637  call    _CxxThrowException_0
0x18000d63d  lea     rcx, [rsp+118h+var_D0]
0x18000d642  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d647  jmp     loc_18000D3D4
0x18000d64c  mov     r8d, r12d
0x18000d64f  movzx   ecx, [rsp+118h+var_D4]
0x18000d654  cmp     r12w, cx
0x18000d658  jnb     short loc_18000D682
0x18000d65a  movsxd  rcx, r8d
0x18000d65d  add     rcx, rcx
0x18000d660  mov     rax, [rsp+118h+var_B0]
0x18000d665  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18000d669  movdqu  xmmword ptr [rdx+rcx*8], xmm0
0x18000d66e  inc     r8d
0x18000d671  movzx   ecx, [rsp+118h+var_D4]
0x18000d676  cmp     r8d, ecx
0x18000d679  jge     short loc_18000D682
0x18000d67b  mov     rdx, [rsp+118h+var_C0]
0x18000d680  jmp     short loc_18000D65A
0x18000d682  movzx   eax, cx
0x18000d685  mov     [rsp+118h+var_B8], eax
0x18000d689  lea     rcx, [rsp+118h+var_70]
0x18000d691  call    ??1?$ScopeGuardImpl1@P6AXPEAX@ZPEAU_SYSTEMTIME@@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>::~ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>(void)
0x18000d696  nop
0x18000d697  lea     rcx, [rsp+118h+var_D0]
0x18000d69c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d6a1  mov     edi, r12d
0x18000d6a4  mov     [rsp+118h+var_D8], r12d
0x18000d6a9  jmp     loc_18000D42F
0x18000d6ae  mov     edi, [rsp+118h+var_D8]
0x18000d6b2  jmp     loc_18000D460
```
