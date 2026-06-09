# ?get_NextRunTime@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAN@Z

- ea: `0x18000d0a0`
- end: `0x18000d42f`
- name: `?get_NextRunTime@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAN@Z`
- size: `911`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800017f0`
- `0x18000c750`
- `0x18000d0a0`
- `0x18000d7e8`
- `0x18002c214`
- `0x1800351ec`
- `0x180036290`
- `0x1800381f8`
- `0x18003b51c`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d22d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d22d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d118`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d118`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000d0f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000d0f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d2f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall _get_NextRunTime__QIRegisteredTask__RegisteredTaskImpl__UEAAJPEAN_Z(__int64 a1, _QWORD *a2)
{
  unsigned int v4; // edi
  __int64 v5; // rbx
  _QWORD *v6; // rdx
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // esi
  int v11; // esi
  void *v12; // rdx
  int v13; // r8d
  unsigned __int16 v14; // cx
  unsigned __int16 v15[2]; // [rsp+40h] [rbp-108h] BYREF
  int v16; // [rsp+44h] [rbp-104h]
  void *v17; // [rsp+48h] [rbp-100h]
  int v18; // [rsp+50h] [rbp-F8h]
  double v19; // [rsp+58h] [rbp-F0h] BYREF
  int v20; // [rsp+60h] [rbp-E8h]
  __int64 v21; // [rsp+68h] [rbp-E0h] BYREF
  void **pExceptionObject; // [rsp+70h] [rbp-D8h] BYREF
  char v23; // [rsp+78h] [rbp-D0h]
  __int64 *v24; // [rsp+80h] [rbp-C8h]
  __int64 v25; // [rsp+88h] [rbp-C0h]
  __int64 v26; // [rsp+90h] [rbp-B8h]
  int v27; // [rsp+98h] [rbp-B0h]
  __int64 v28; // [rsp+9Ch] [rbp-ACh]
  _BYTE v29[8]; // [rsp+E0h] [rbp-68h] BYREF
  void (__stdcall *v30)(LPVOID); // [rsp+E8h] [rbp-60h]
  double v31; // [rsp+F0h] [rbp-58h]
  struct _SYSTEMTIME v32; // [rsp+F8h] [rbp-50h] BYREF
  struct _SYSTEMTIME v33; // [rsp+108h] [rbp-40h] BYREF

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v4 = 0;
  v16 = 0;
  v33 = 0;
  GetLocalTime(&v33);
  v17 = 0;
  v18 = 0;
  v5 = (a1 + 16) & -(__int64)(a1 != 0);
  if ( v5 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  v21 = (a1 + 16) & -(__int64)(a1 != 0);
  v6 = (_QWORD *)(a1 + 80);
  if ( *(_QWORD *)(a1 + 104) >= 8u )
    v6 = (_QWORD *)*v6;
  if ( !*(_DWORD *)(a1 + 128) )
  {
    v4 = -2147023645;
    v16 = -2147023645;
    goto LABEL_31;
  }
  v7 = *(_QWORD *)(a1 + 136);
  if ( !v7 )
  {
    if ( v6 && *(_WORD *)v6 == 92 )
      v6 = (_QWORD *)((char *)v6 + 2);
    *(_QWORD *)&v32.wYear = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, GUID *, struct _SYSTEMTIME *))(**(_QWORD **)(a1 + 144) + 48LL))(
            *(_QWORD *)(a1 + 144),
            v6,
            &GUID_148bd524_a2ab_11ce_b11f_00aa00530503,
            &v32);
    if ( v11 >= 0 )
    {
      v15[0] = 1;
      v19 = 0.0;
      v11 = (*(__int64 (__fastcall **)(_QWORD, struct _SYSTEMTIME *, _QWORD, unsigned __int16 *, double *))(**(_QWORD **)&v32.wYear + 64LL))(
              *(_QWORD *)&v32.wYear,
              &v33,
              0,
              v15,
              &v19);
      if ( v11 >= 0 )
      {
        v29[0] = 0;
        v30 = CoTaskMemFree;
        v31 = v19;
        v12 = MIDL_user_allocate(16LL * v15[0]);
        v17 = v12;
        if ( !v12 )
        {
          v23 = 0;
          v24 = &qword_180077320;
          v25 = 0;
          v26 = 0;
          v27 = 14;
          v28 = -1;
          pExceptionObject = &wmi::GenericException::`vftable';
          throw (wmi::OutOfMemoryException *)&pExceptionObject;
        }
        v13 = 0;
        v14 = v15[0];
        if ( v15[0] )
        {
          while ( 1 )
          {
            *((_OWORD *)v12 + v13) = *(_OWORD *)(*(_QWORD *)&v19 + 16LL * v13);
            ++v13;
            v14 = v15[0];
            if ( v13 >= v15[0] )
              break;
            v12 = v17;
          }
        }
        v18 = v14;
        wmi::ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>::~ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>(v29);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
        goto LABEL_36;
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
    v16 = v11;
    v4 = v11;
LABEL_31:
    ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(&v21);
    MIDL_user_free(v17);
    return v4;
  }
  v8 = RpcSession::Runtimes(v7, (_DWORD)v6, (unsigned int)&v33, 0);
  v4 = v8;
  v16 = v8;
  if ( v8 < 0 )
    goto LABEL_31;
  if ( v8 != 1 )
  {
    v9 = v8;
    goto LABEL_11;
  }
  v4 = 0;
  v16 = 0;
LABEL_36:
  v9 = 0;
LABEL_11:
  if ( v18 )
  {
    v32 = *(struct _SYSTEMTIME *)v17;
    v19 = 0.0;
    v20 = 0;
    ATL::AtlConvertSystemTimeToVariantTime(&v32, &v19);
    *a2 = *(_QWORD *)&v19;
    if ( v5 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
    MIDL_user_free(v17);
    return v4;
  }
  else
  {
    if ( !v9 )
    {
      v9 = 267012;
      v16 = 267012;
    }
    if ( v5 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
    MIDL_user_free(v17);
    return v9;
  }
}

```

## disassembly

```asm
0x18000d0a0  mov     r11, rsp
0x18000d0a3  mov     [r11+18h], rbx
0x18000d0a7  push    rsi
0x18000d0a8  push    rdi
0x18000d0a9  push    r12
0x18000d0ab  push    r14
0x18000d0ad  push    r15
0x18000d0af  sub     rsp, 120h
0x18000d0b6  mov     rax, cs:__security_cookie
0x18000d0bd  xor     rax, rsp
0x18000d0c0  mov     [rsp+148h+var_30], rax
0x18000d0c8  mov     r15, rdx
0x18000d0cb  mov     rsi, rcx
0x18000d0ce  xor     r12d, r12d
0x18000d0d1  test    rdx, rdx
0x18000d0d4  jz      loc_18000D1E0
0x18000d0da  mov     [rdx], r12
0x18000d0dd  mov     edi, r12d
0x18000d0e0  mov     [rsp+148h+var_104], r12d
0x18000d0e5  xorps   xmm0, xmm0
0x18000d0e8  movups  xmmword ptr [r11-40h], xmm0
0x18000d0ed  lea     rcx, [r11-40h]; lpSystemTime
0x18000d0f1  call    cs:__imp_GetLocalTime
0x18000d0f7  nop
0x18000d0f8  mov     [rsp+148h+var_100], r12
0x18000d0fd  mov     [rsp+148h+var_F8], r12d
0x18000d102  mov     rax, rsi
0x18000d105  lea     rcx, [rsi+10h]
0x18000d109  neg     rax
0x18000d10c  sbb     rbx, rbx
0x18000d10f  and     rbx, rcx
0x18000d112  jz      short loc_18000D11E
0x18000d114  lea     rcx, [rbx+8]; lpCriticalSection
0x18000d118  call    cs:__imp_EnterCriticalSection
0x18000d11e  mov     [rsp+148h+var_E0], rbx
0x18000d123  lea     rdx, [rsi+50h]
0x18000d127  cmp     qword ptr [rdx+18h], 8
0x18000d12c  jb      short loc_18000D131
0x18000d12e  mov     rdx, [rdx]
0x18000d131  cmp     [rsi+80h], r12d
0x18000d138  jz      loc_18000D246
0x18000d13e  mov     rcx, [rsi+88h]
0x18000d145  test    rcx, rcx
0x18000d148  jz      loc_18000D261
0x18000d14e  lea     rax, [rsp+148h+var_100]
0x18000d153  mov     [rsp+148h+var_118], rax
0x18000d158  mov     r14d, 1
0x18000d15e  mov     [rsp+148h+var_120], r14d
0x18000d163  xor     r9d, r9d
0x18000d166  lea     r8, [rsp+148h+var_40]
0x18000d16e  call    ?Runtimes@RpcSession@@QEBAJPEBGPEAU_SYSTEMTIME@@1KKAEAV?$RpcArray@U_SYSTEMTIME@@@@@Z; RpcSession::Runtimes(ushort const *,_SYSTEMTIME *,_SYSTEMTIME *,ulong,ulong,RpcArray<_SYSTEMTIME> &)
0x18000d173  mov     edi, eax
0x18000d175  mov     [rsp+148h+var_104], eax
0x18000d179  test    eax, eax
0x18000d17b  js      loc_18000D39C
0x18000d181  cmp     eax, r14d
0x18000d184  jz      loc_18000D254
0x18000d18a  mov     esi, eax
0x18000d18c  mov     eax, [rsp+148h+var_F8]
0x18000d190  test    eax, eax
0x18000d192  jnz     short loc_18000D1E7
0x18000d194  test    esi, esi
0x18000d196  jz      loc_18000D418
0x18000d19c  test    rbx, rbx
0x18000d19f  jz      short loc_18000D1AC
0x18000d1a1  lea     rcx, [rbx+8]; lpCriticalSection
0x18000d1a5  call    cs:__imp_LeaveCriticalSection
0x18000d1ab  nop
0x18000d1ac  mov     rcx, [rsp+148h+var_100]; void *
0x18000d1b1  call    MIDL_user_free
0x18000d1b6  mov     eax, esi
0x18000d1b8  mov     rcx, [rsp+148h+var_30]
0x18000d1c0  xor     rcx, rsp; StackCookie
0x18000d1c3  call    __security_check_cookie
0x18000d1c8  mov     rbx, [rsp+148h+arg_10]
0x18000d1d0  add     rsp, 120h
0x18000d1d7  pop     r15
0x18000d1d9  pop     r14
0x18000d1db  pop     r12
0x18000d1dd  pop     rdi
0x18000d1de  pop     rsi
0x18000d1df  retn
0x18000d1e0  mov     eax, 80004003h
0x18000d1e5  jmp     short loc_18000D1B8
0x18000d1e7  mov     rax, [rsp+148h+var_100]
0x18000d1ec  movups  xmm0, xmmword ptr [rax]
0x18000d1ef  movdqu  xmmword ptr [rsp+148h+var_50.wYear], xmm0
0x18000d1f8  xorps   xmm1, xmm1
0x18000d1fb  movsd   [rsp+148h+var_F0], xmm1
0x18000d201  mov     [rsp+148h+var_E8], r12d
0x18000d206  lea     rdx, [rsp+148h+var_F0]; double *
0x18000d20b  lea     rcx, [rsp+148h+var_50]; struct _SYSTEMTIME *
0x18000d213  call    ?AtlConvertSystemTimeToVariantTime@ATL@@YAHAEBU_SYSTEMTIME@@PEAN@Z; ATL::AtlConvertSystemTimeToVariantTime(_SYSTEMTIME const &,double *)
0x18000d218  nop
0x18000d219  movsd   xmm0, [rsp+148h+var_F0]
0x18000d21f  movsd   qword ptr [r15], xmm0
0x18000d224  test    rbx, rbx
0x18000d227  jz      short loc_18000D234
0x18000d229  lea     rcx, [rbx+8]; lpCriticalSection
0x18000d22d  call    cs:__imp_LeaveCriticalSection
0x18000d233  nop
0x18000d234  mov     rcx, [rsp+148h+var_100]; void *
0x18000d239  call    MIDL_user_free
0x18000d23e  nop
0x18000d23f  mov     eax, edi
0x18000d241  jmp     loc_18000D1B8
0x18000d246  mov     edi, 800704E3h
0x18000d24b  mov     [rsp+148h+var_104], edi
0x18000d24f  jmp     loc_18000D39C
0x18000d254  mov     edi, r12d
0x18000d257  mov     [rsp+148h+var_104], r12d
0x18000d25c  jmp     loc_18000D410
0x18000d261  test    rdx, rdx
0x18000d264  jz      short loc_18000D270
0x18000d266  cmp     word ptr [rdx], 5Ch ; '\'
0x18000d26a  jnz     short loc_18000D270
0x18000d26c  add     rdx, 2
0x18000d270  mov     qword ptr [rsp+148h+var_50.wYear], r12
0x18000d278  mov     rcx, [rsi+90h]
0x18000d27f  mov     rax, [rcx]
0x18000d282  lea     r9, [rsp+148h+var_50]
0x18000d28a  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x18000d291  mov     rax, [rax+30h]
0x18000d295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d29a  mov     esi, eax
0x18000d29c  test    eax, eax
0x18000d29e  js      loc_18000D389
0x18000d2a4  mov     r14d, 1
0x18000d2aa  mov     [rsp+148h+var_108], r14w
0x18000d2b0  mov     [rsp+148h+var_F0], r12
0x18000d2b5  mov     rcx, qword ptr [rsp+148h+var_50.wYear]
0x18000d2bd  mov     rax, [rcx]
0x18000d2c0  lea     rdx, [rsp+148h+var_F0]
0x18000d2c5  mov     [rsp+148h+var_128], rdx
0x18000d2ca  lea     r9, [rsp+148h+var_108]
0x18000d2cf  xor     r8d, r8d
0x18000d2d2  lea     rdx, [rsp+148h+var_40]
0x18000d2da  mov     rax, [rax+40h]
0x18000d2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2e3  mov     esi, eax
0x18000d2e5  test    eax, eax
0x18000d2e7  js      loc_18000D389
0x18000d2ed  mov     rcx, [rsp+148h+var_F0]
0x18000d2f2  mov     rax, cs:__imp_CoTaskMemFree
0x18000d2f9  mov     [rsp+148h+var_68], r12b
0x18000d301  mov     [rsp+148h+var_60], rax
0x18000d309  mov     [rsp+148h+var_58], rcx
0x18000d311  movzx   ecx, [rsp+148h+var_108]
0x18000d316  shl     rcx, 4; size
0x18000d31a  call    MIDL_user_allocate
0x18000d31f  mov     rdx, rax
0x18000d322  mov     [rsp+148h+var_100], rax
0x18000d327  test    rax, rax
0x18000d32a  jnz     loc_18000D3B8
0x18000d330  mov     [rsp+148h+var_D0], r12b
0x18000d335  lea     rax, qword_180077320
0x18000d33c  mov     [rsp+148h+var_C8], rax
0x18000d344  mov     [rsp+148h+var_C0], r12
0x18000d34c  mov     [rsp+148h+var_B8], r12
0x18000d354  mov     [rsp+148h+var_B0], 0Eh
0x18000d35f  mov     [rsp+148h+var_AC], 0FFFFFFFFFFFFFFFFh
0x18000d36b  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000d372  mov     [rsp+148h+pExceptionObject], rax
0x18000d377  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18000d37e  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x18000d383  call    _CxxThrowException_0
0x18000d389  lea     rcx, [rsp+148h+var_50]
0x18000d391  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d396  mov     [rsp+148h+var_104], esi
0x18000d39a  mov     edi, esi
0x18000d39c  lea     rcx, [rsp+148h+var_E0]
0x18000d3a1  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x18000d3a6  nop
0x18000d3a7  mov     rcx, [rsp+148h+var_100]; void *
0x18000d3ac  call    MIDL_user_free
0x18000d3b1  mov     eax, edi
0x18000d3b3  jmp     loc_18000D1B8
0x18000d3b8  mov     r8d, r12d
0x18000d3bb  movzx   ecx, [rsp+148h+var_108]
0x18000d3c0  cmp     r12w, cx
0x18000d3c4  jnb     short loc_18000D3EE
0x18000d3c6  movsxd  rcx, r8d
0x18000d3c9  add     rcx, rcx
0x18000d3cc  mov     rax, [rsp+148h+var_F0]
0x18000d3d1  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18000d3d5  movdqu  xmmword ptr [rdx+rcx*8], xmm0
0x18000d3da  add     r8d, r14d
0x18000d3dd  movzx   ecx, [rsp+148h+var_108]
0x18000d3e2  cmp     r8d, ecx
0x18000d3e5  jge     short loc_18000D3EE
0x18000d3e7  mov     rdx, [rsp+148h+var_100]
0x18000d3ec  jmp     short loc_18000D3C6
0x18000d3ee  movzx   eax, cx
0x18000d3f1  mov     [rsp+148h+var_F8], eax
0x18000d3f5  lea     rcx, [rsp+148h+var_68]
0x18000d3fd  call    ??1?$ScopeGuardImpl1@P6AXPEAX@ZPEAU_SYSTEMTIME@@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>::~ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>(void)
0x18000d402  nop
0x18000d403  lea     rcx, [rsp+148h+var_50]
0x18000d40b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d410  mov     esi, r12d
0x18000d413  jmp     loc_18000D18C
0x18000d418  mov     esi, 41304h
0x18000d41d  mov     [rsp+148h+var_104], esi
0x18000d421  jmp     loc_18000D19C
0x18000d426  mov     edi, [rsp+148h+var_104]
0x18000d42a  jmp     loc_18000D23F
```
