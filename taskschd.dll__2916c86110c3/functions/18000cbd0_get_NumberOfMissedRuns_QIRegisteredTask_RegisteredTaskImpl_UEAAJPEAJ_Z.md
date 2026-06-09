# ?get_NumberOfMissedRuns@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAJ@Z

- ea: `0x18000cbd0`
- end: `0x18000d03f`
- name: `?get_NumberOfMissedRuns@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAJ@Z`
- size: `1135`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800017f0`
- `0x18000c750`
- `0x18000cbd0`
- `0x18000d7e8`
- `0x18002c2d0`
- `0x180036290`
- `0x1800381f8`
- `0x18003b51c`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cd34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cd92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cde1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cd34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cd92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cde1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cc35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cc35`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000cca5`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000cca5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf32`

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
            v26 = &qword_180077320;
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
0x18000cbd0  mov     r11, rsp
0x18000cbd3  mov     [r11+18h], rbx
0x18000cbd7  push    rsi
0x18000cbd8  push    rdi
0x18000cbd9  push    r12
0x18000cbdb  push    r14
0x18000cbdd  push    r15
0x18000cbdf  sub     rsp, 0F0h
0x18000cbe6  mov     rax, cs:__security_cookie
0x18000cbed  xor     rax, rsp
0x18000cbf0  mov     [rsp+118h+var_30], rax
0x18000cbf8  mov     r15, rdx
0x18000cbfb  mov     r14, rcx
0x18000cbfe  xor     r12d, r12d
0x18000cc01  test    rdx, rdx
0x18000cc04  jz      loc_18000CDEF
0x18000cc0a  mov     [rdx], r12d
0x18000cc0d  mov     [rsp+118h+var_D8], r12d
0x18000cc12  xorps   xmm0, xmm0
0x18000cc15  movups  xmmword ptr [r11-50h], xmm0
0x18000cc1a  mov     [rsp+118h+var_C8], r12d
0x18000cc1f  mov     rax, rcx
0x18000cc22  add     rcx, 10h
0x18000cc26  neg     rax
0x18000cc29  sbb     rbx, rbx
0x18000cc2c  and     rbx, rcx
0x18000cc2f  jz      short loc_18000CC3B
0x18000cc31  lea     rcx, [rbx+8]; lpCriticalSection
0x18000cc35  call    cs:__imp_EnterCriticalSection
0x18000cc3b  mov     [rsp+118h+var_58], rbx
0x18000cc43  lea     rsi, [r14+50h]
0x18000cc47  cmp     qword ptr [rsi+18h], 8
0x18000cc4c  jb      loc_18000CD64
0x18000cc52  mov     rdx, [rsi]; unsigned __int16 *
0x18000cc55  cmp     [r14+80h], r12d
0x18000cc5c  jz      loc_18000CD9C
0x18000cc62  mov     rcx, [r14+88h]; this
0x18000cc69  test    rcx, rcx
0x18000cc6c  jz      loc_18000CDF9
0x18000cc72  lea     r9, [rsp+118h+var_C8]; unsigned int *
0x18000cc77  lea     r8, [rsp+118h+var_50]; struct _SYSTEMTIME *
0x18000cc7f  call    ?GetLastRunInfo@RpcSession@@QEBAJPEBGPEAU_SYSTEMTIME@@PEAK@Z; RpcSession::GetLastRunInfo(ushort const *,_SYSTEMTIME *,ulong *)
0x18000cc84  mov     edi, eax
0x18000cc86  mov     [rsp+118h+var_D8], edi
0x18000cc8a  test    edi, edi
0x18000cc8c  jnz     loc_18000CDA5
0x18000cc92  xorps   xmm0, xmm0
0x18000cc95  movups  xmmword ptr [rsp+118h+SystemTime.wYear], xmm0
0x18000cc9d  lea     rcx, [rsp+118h+SystemTime]; lpSystemTime
0x18000cca5  call    cs:__imp_GetLocalTime
0x18000ccab  mov     [rsp+118h+var_C0], r12
0x18000ccb0  mov     [rsp+118h+var_B8], r12d
0x18000ccb5  cmp     qword ptr [rsi+18h], 8
0x18000ccba  jb      short loc_18000CCBF
0x18000ccbc  mov     rsi, [rsi]
0x18000ccbf  cmp     [r14+80h], r12d
0x18000ccc6  jz      loc_18000CD6C
0x18000cccc  mov     rcx, [r14+88h]
0x18000ccd3  test    rcx, rcx
0x18000ccd6  jz      loc_18000CEA4
0x18000ccdc  lea     rax, [rsp+118h+var_C0]
0x18000cce1  mov     [rsp+118h+var_E8], rax
0x18000cce6  mov     [rsp+118h+var_F0], 0FFFFFFFFh
0x18000ccee  lea     r9, [rsp+118h+SystemTime]
0x18000ccf6  lea     r8, [rsp+118h+var_50]
0x18000ccfe  mov     rdx, rsi
0x18000cd01  call    ?Runtimes@RpcSession@@QEBAJPEBGPEAU_SYSTEMTIME@@1KKAEAV?$RpcArray@U_SYSTEMTIME@@@@@Z; RpcSession::Runtimes(ushort const *,_SYSTEMTIME *,_SYSTEMTIME *,ulong,ulong,RpcArray<_SYSTEMTIME> &)
0x18000cd06  mov     edi, eax
0x18000cd08  mov     [rsp+118h+var_D8], eax
0x18000cd0c  cmp     eax, 41304h
0x18000cd11  jnz     loc_18000CDB8
0x18000cd17  mov     rcx, [rsp+118h+var_C0]; void *
0x18000cd1c  call    MIDL_user_free
0x18000cd21  mov     [rsp+118h+var_C0], r12
0x18000cd26  mov     [rsp+118h+var_B8], r12d
0x18000cd2b  test    rbx, rbx
0x18000cd2e  jz      short loc_18000CD3A
0x18000cd30  lea     rcx, [rbx+8]; lpCriticalSection
0x18000cd34  call    cs:__imp_LeaveCriticalSection
0x18000cd3a  xor     eax, eax
0x18000cd3c  mov     rcx, [rsp+118h+var_30]
0x18000cd44  xor     rcx, rsp; StackCookie
0x18000cd47  call    __security_check_cookie
0x18000cd4c  mov     rbx, [rsp+118h+arg_10]
0x18000cd54  add     rsp, 0F0h
0x18000cd5b  pop     r15
0x18000cd5d  pop     r14
0x18000cd5f  pop     r12
0x18000cd61  pop     rdi
0x18000cd62  pop     rsi
0x18000cd63  retn
0x18000cd64  mov     rdx, rsi
0x18000cd67  jmp     loc_18000CC55
0x18000cd6c  mov     edi, 800704E3h
0x18000cd71  mov     [rsp+118h+var_D8], edi
0x18000cd75  mov     rcx, [rsp+118h+var_C0]; void *
0x18000cd7a  call    MIDL_user_free
0x18000cd7f  mov     [rsp+118h+var_C0], r12
0x18000cd84  mov     [rsp+118h+var_B8], r12d
0x18000cd89  test    rbx, rbx
0x18000cd8c  jz      short loc_18000CD98
0x18000cd8e  lea     rcx, [rbx+8]; lpCriticalSection
0x18000cd92  call    cs:__imp_LeaveCriticalSection
0x18000cd98  mov     eax, edi
0x18000cd9a  jmp     short loc_18000CD3C
0x18000cd9c  mov     edi, 800704E3h
0x18000cda1  mov     [rsp+118h+var_D8], edi
0x18000cda5  test    rbx, rbx
0x18000cda8  jz      short loc_18000CDB4
0x18000cdaa  lea     rcx, [rbx+8]; lpCriticalSection
0x18000cdae  call    cs:__imp_LeaveCriticalSection
0x18000cdb4  mov     eax, edi
0x18000cdb6  jmp     short loc_18000CD3C
0x18000cdb8  cmp     eax, 1
0x18000cdbb  ja      short loc_18000CD75
0x18000cdbd  mov     eax, [rsp+118h+var_B8]
0x18000cdc1  mov     [r15], eax
0x18000cdc4  mov     rcx, [rsp+118h+var_C0]; void *
0x18000cdc9  call    MIDL_user_free
0x18000cdce  mov     [rsp+118h+var_C0], r12
0x18000cdd3  mov     [rsp+118h+var_B8], r12d
0x18000cdd8  test    rbx, rbx
0x18000cddb  jz      short loc_18000CDE8
0x18000cddd  lea     rcx, [rbx+8]; lpCriticalSection
0x18000cde1  call    cs:__imp_LeaveCriticalSection
0x18000cde7  nop
0x18000cde8  mov     eax, edi
0x18000cdea  jmp     loc_18000CD3C
0x18000cdef  mov     eax, 80004003h
0x18000cdf4  jmp     loc_18000CD3C
0x18000cdf9  test    rdx, rdx
0x18000cdfc  jz      short loc_18000CE08
0x18000cdfe  cmp     word ptr [rdx], 5Ch ; '\'
0x18000ce02  jnz     short loc_18000CE08
0x18000ce04  add     rdx, 2
0x18000ce08  mov     [rsp+118h+var_D0], r12
0x18000ce0d  mov     rcx, [r14+90h]
0x18000ce14  mov     rax, [rcx]
0x18000ce17  lea     r9, [rsp+118h+var_D0]
0x18000ce1c  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x18000ce23  mov     rax, [rax+30h]
0x18000ce27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce2c  mov     edi, eax
0x18000ce2e  test    eax, eax
0x18000ce30  js      short loc_18000CE86
0x18000ce32  mov     rcx, [rsp+118h+var_D0]
0x18000ce37  mov     rax, [rcx]
0x18000ce3a  lea     rdx, [rsp+118h+var_50]
0x18000ce42  mov     rax, [rax+78h]
0x18000ce46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce4b  mov     edi, eax
0x18000ce4d  test    eax, eax
0x18000ce4f  js      short loc_18000CE86
0x18000ce51  mov     rcx, [rsp+118h+var_D0]
0x18000ce56  lea     rdx, [rsp+118h+var_C8]
0x18000ce5b  mov     rax, [rcx]
0x18000ce5e  mov     rax, [rax+88h]
0x18000ce65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce6a  cmp     edi, 41303h
0x18000ce70  mov     edi, eax
0x18000ce72  jnz     short loc_18000CE95
0x18000ce74  test    eax, eax
0x18000ce76  jns     short loc_18000CE95
0x18000ce78  movzx   eax, ax
0x18000ce7b  mov     [rsp+118h+var_C8], eax
0x18000ce7f  mov     edi, 41303h
0x18000ce84  jmp     short loc_18000CE95
0x18000ce86  lea     rcx, [rsp+118h+var_D0]
0x18000ce8b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ce90  jmp     loc_18000CDA1
0x18000ce95  lea     rcx, [rsp+118h+var_D0]
0x18000ce9a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ce9f  jmp     loc_18000CC86
0x18000cea4  test    rsi, rsi
0x18000cea7  jz      short loc_18000CEB3
0x18000cea9  cmp     word ptr [rsi], 5Ch ; '\'
0x18000cead  jnz     short loc_18000CEB3
0x18000ceaf  add     rsi, 2
0x18000ceb3  mov     [rsp+118h+var_D0], r12
0x18000ceb8  mov     rcx, [r14+90h]
0x18000cebf  mov     rax, [rcx]
0x18000cec2  lea     r9, [rsp+118h+var_D0]
0x18000cec7  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x18000cece  mov     rdx, rsi
0x18000ced1  mov     rax, [rax+30h]
0x18000ced5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceda  mov     edi, eax
0x18000cedc  test    eax, eax
0x18000cede  js      loc_18000CFC5
0x18000cee4  mov     [rsp+118h+var_B0], r12
0x18000cee9  mov     eax, 0FFFFh
0x18000ceee  mov     [rsp+118h+var_D4], ax
0x18000cef3  mov     rcx, [rsp+118h+var_D0]
0x18000cef8  mov     rax, [rcx]
0x18000cefb  lea     rdx, [rsp+118h+var_B0]
0x18000cf00  mov     [rsp+118h+var_F8], rdx
0x18000cf05  lea     r9, [rsp+118h+var_D4]
0x18000cf0a  lea     r8, [rsp+118h+SystemTime]
0x18000cf12  lea     rdx, [rsp+118h+var_50]
0x18000cf1a  mov     rax, [rax+40h]
0x18000cf1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf23  mov     edi, eax
0x18000cf25  test    eax, eax
0x18000cf27  js      loc_18000CFC5
0x18000cf2d  mov     rcx, [rsp+118h+var_B0]
0x18000cf32  mov     rax, cs:__imp_CoTaskMemFree
0x18000cf39  mov     [rsp+118h+var_70], r12b
0x18000cf41  mov     [rsp+118h+var_68], rax
0x18000cf49  mov     [rsp+118h+var_60], rcx
0x18000cf51  movzx   ecx, [rsp+118h+var_D4]
0x18000cf56  shl     rcx, 4; size
0x18000cf5a  call    MIDL_user_allocate
0x18000cf5f  mov     rdx, rax
0x18000cf62  mov     [rsp+118h+var_C0], rax
0x18000cf67  test    rax, rax
0x18000cf6a  jnz     short loc_18000CFD4
0x18000cf6c  mov     [rsp+118h+var_A0], r12b
0x18000cf71  lea     rax, qword_180077320
0x18000cf78  mov     [rsp+118h+var_98], rax
0x18000cf80  mov     [rsp+118h+var_90], r12
0x18000cf88  mov     [rsp+118h+var_88], r12
0x18000cf90  mov     [rsp+118h+var_80], 0Eh
0x18000cf9b  mov     [rsp+118h+var_7C], 0FFFFFFFFFFFFFFFFh
0x18000cfa7  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000cfae  mov     [rsp+118h+pExceptionObject], rax
0x18000cfb3  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18000cfba  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18000cfbf  call    _CxxThrowException_0
0x18000cfc5  lea     rcx, [rsp+118h+var_D0]
0x18000cfca  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000cfcf  jmp     loc_18000CD71
0x18000cfd4  mov     r8d, r12d
0x18000cfd7  movzx   ecx, [rsp+118h+var_D4]
0x18000cfdc  cmp     r12w, cx
0x18000cfe0  jnb     short loc_18000D00A
0x18000cfe2  movsxd  rcx, r8d
0x18000cfe5  add     rcx, rcx
0x18000cfe8  mov     rax, [rsp+118h+var_B0]
0x18000cfed  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18000cff1  movdqu  xmmword ptr [rdx+rcx*8], xmm0
0x18000cff6  inc     r8d
0x18000cff9  movzx   ecx, [rsp+118h+var_D4]
0x18000cffe  cmp     r8d, ecx
0x18000d001  jge     short loc_18000D00A
0x18000d003  mov     rdx, [rsp+118h+var_C0]
0x18000d008  jmp     short loc_18000CFE2
0x18000d00a  movzx   eax, cx
0x18000d00d  mov     [rsp+118h+var_B8], eax
0x18000d011  lea     rcx, [rsp+118h+var_70]
0x18000d019  call    ??1?$ScopeGuardImpl1@P6AXPEAX@ZPEAU_SYSTEMTIME@@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>::~ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>(void)
0x18000d01e  nop
0x18000d01f  lea     rcx, [rsp+118h+var_D0]
0x18000d024  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d029  mov     edi, r12d
0x18000d02c  mov     [rsp+118h+var_D8], r12d
0x18000d031  jmp     loc_18000CDBD
0x18000d036  mov     edi, [rsp+118h+var_D8]
0x18000d03a  jmp     loc_18000CDE8
```
