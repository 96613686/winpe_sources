# CNotification::Notify(ulong,__MIDL___MIDL_itf_unistore_0000_0000_0009 const * const * const,int)

- ea: `0x180026b10`
- end: `0x180026df2`
- name: `?Notify@CNotification@@UEAAJKQEBQEBU__MIDL___MIDL_itf_unistore_0000_0000_0009@@H@Z`
- size: `738`
- prototype: `__int64 __fastcall(CNotification *__hidden this, unsigned int, const struct __MIDL___MIDL_itf_unistore_0000_0000_0009 *const *const, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800068f0`
- `0x180026b10`
- `0x180027db0`
- `0x180027e58`
- `0x1800289f4`
- `0x180072348`
- `0x180073a04`
- `0x180078a40`
- `0x180078a8c`
- `0x180093048`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026b48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026b48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026c9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026ce4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026c9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026ce4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026b92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026b92`

## string_xrefs

- `0x180026da5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\rpcservice.cpp`

## pseudocode

```c
__int64 __fastcall CNotification::Notify(
        CNotification *this,
        unsigned int a2,
        const struct __MIDL___MIDL_itf_unistore_0000_0000_0009 *const *a3,
        int a4)
{
  const struct __MIDL___MIDL_itf_unistore_0000_0000_0009 *const *v5; // r12
  char *v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // r15
  unsigned int CallerClientId; // eax
  RundownProtectionList *v11; // rcx
  unsigned int CurrentProcessId; // r13d
  char *v13; // rdi
  __int64 v14; // r8
  _QWORD *v15; // rbx
  __int64 v16; // r8
  __int64 v17; // rbp
  const struct __MIDL___MIDL_itf_unistore_0000_0000_0009 *v18; // rax
  char *v19; // rcx
  __int128 v20; // xmm1
  __int128 v21; // xmm2
  __int128 v22; // xmm3
  __int128 v23; // xmm4
  int v24; // eax
  __int64 v25; // r8
  unsigned int v26; // r12d
  int v27; // eax
  __int64 v28; // r8
  int v30; // eax
  __int64 v31; // r8
  unsigned int v32; // ebp
  __int64 v33; // rdx
  __int64 v34; // r9
  int v35; // eax
  __int64 v36; // r8
  __int64 v37; // [rsp+30h] [rbp-58h] BYREF
  char v38; // [rsp+38h] [rbp-50h]
  char *v39; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v40; // [rsp+98h] [rbp+10h]
  const struct __MIDL___MIDL_itf_unistore_0000_0000_0009 *const *v41; // [rsp+A0h] [rbp+18h]
  unsigned int v42; // [rsp+A8h] [rbp+20h] BYREF

  v41 = a3;
  v40 = a2;
  v5 = a3;
  if ( this )
  {
    v7 = (char *)this + 16;
    if ( this != (CNotification *)-16LL )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  }
  else
  {
    v7 = 0;
  }
  v39 = v7;
  v9 = *wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
          &v37,
          (__int64)this);
  v37 = v9;
  v38 = 1;
  if ( !a4 )
  {
    CallerClientId = GetCallerClientId(v8);
    v42 = 0;
    if ( CallerClientId <= 0xFFFFFFFD )
    {
      if ( !(unsigned int)RundownProtectionList::GetProcessIdFromRundownProtectionId(v11, CallerClientId, &v42) )
      {
        v32 = -2147483622;
        Log_UnistoreHREvent_0(
          2147483674LL,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\rpcservice.cpp",
          1181);
        v34 = 90;
        v33 = 1;
        goto LABEL_29;
      }
      CurrentProcessId = v42;
    }
    else
    {
      CurrentProcessId = GetCurrentProcessId();
    }
    v13 = (char *)operator new[](0x3E80u);
    if ( v13 )
    {
      v15 = operator new[](0x640u);
      if ( v15 )
      {
        v17 = 0;
        while ( (unsigned int)v17 < v40 )
        {
          v18 = v5[v17];
          v19 = &v13[80 * v17];
          v20 = *((_OWORD *)v18 + 1);
          v21 = *((_OWORD *)v18 + 2);
          v22 = *((_OWORD *)v18 + 3);
          v23 = *((_OWORD *)v18 + 4);
          *(_OWORD *)v19 = *(_OWORD *)v18;
          *((_OWORD *)v19 + 1) = v20;
          *((_OWORD *)v19 + 2) = v21;
          *((_OWORD *)v19 + 3) = v22;
          *((_OWORD *)v19 + 4) = v23;
          *((_DWORD *)v19 + 18) = CurrentProcessId;
          v15[v17] = v19;
          v17 = (unsigned int)(v17 + 1);
          if ( (_DWORD)v17 == 200 )
          {
            v24 = (*(__int64 (__fastcall **)(CNotification *, __int64, _QWORD *, _QWORD))(*(_QWORD *)this + 32LL))(
                    this,
                    200,
                    v15,
                    0);
            v26 = v24;
            if ( v24 < 0 )
            {
              Log_UnistoreHREvent_20((unsigned int)v24, 1, v25, 108);
              operator delete(v15);
              operator delete(v13);
              v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v9 + 32LL))(v9, 0, 0, 1);
              if ( v27 < 0 )
                Log_UnistoreHREvent_20((unsigned int)v27, 0, v28, 205);
              if ( v7 )
                LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 8));
              return v26;
            }
            v5 = v41;
          }
        }
        if ( !(_DWORD)v17
          || (v30 = (*(__int64 (__fastcall **)(CNotification *, _QWORD, _QWORD *, _QWORD))(*(_QWORD *)this + 32LL))(
                      this,
                      (unsigned int)v17,
                      v15,
                      0),
              v32 = v30,
              v30 >= 0) )
        {
          operator delete(v15);
          operator delete(v13);
          goto LABEL_21;
        }
        Log_UnistoreHREvent_20((unsigned int)v30, 1, v31, 116);
        operator delete(v15);
      }
      else
      {
        v32 = -2147024882;
        Log_UnistoreHREvent_20(2147942414LL, 0, v16, 97);
      }
      operator delete(v13);
      goto LABEL_26;
    }
    v33 = 0;
    v32 = -2147024882;
    v34 = 94;
LABEL_29:
    Log_UnistoreHREvent_20(v32, v33, v14, v34);
LABEL_26:
    tlx::_UndoSolo__lambda_e4b4baa9baf3de765227b06144d2e027___::__UndoSolo__lambda_e4b4baa9baf3de765227b06144d2e027___(&v37);
    ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(&v39);
    return v32;
  }
  v35 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v9 + 32LL))(v9, 0, 0, 1);
  if ( v35 < 0 )
    Log_UnistoreHREvent_20((unsigned int)v35, 0, v36, 205);
LABEL_21:
  if ( v7 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 8));
  return 0;
}

```

## disassembly

```asm
0x180026b10  mov     [rsp+arg_10], r8
0x180026b15  mov     [rsp+arg_8], edx
0x180026b19  push    rbx
0x180026b1a  push    rbp
0x180026b1b  push    rsi
0x180026b1c  push    rdi
0x180026b1d  push    r12
0x180026b1f  push    r13
0x180026b21  push    r14
0x180026b23  push    r15
0x180026b25  sub     rsp, 48h
0x180026b29  mov     ebx, r9d
0x180026b2c  mov     r12, r8
0x180026b2f  mov     r14, rcx
0x180026b32  test    rcx, rcx
0x180026b35  jz      loc_180026D32
0x180026b3b  lea     rsi, [rcx+10h]
0x180026b3f  test    rsi, rsi
0x180026b42  jz      short loc_180026B4E
0x180026b44  lea     rcx, [rsi+8]; lpCriticalSection
0x180026b48  call    cs:__imp_EnterCriticalSection
0x180026b4e  mov     rdx, r14
0x180026b51  mov     [rsp+88h+arg_0], rsi
0x180026b59  lea     rcx, [rsp+88h+var_58]
0x180026b5e  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180026b63  mov     edi, 1
0x180026b68  mov     r15, [rax]
0x180026b6b  mov     [rsp+88h+var_58], r15
0x180026b70  mov     [rsp+88h+var_50], dil
0x180026b75  test    ebx, ebx
0x180026b77  jnz     loc_180026D6D
0x180026b7d  call    ?GetCallerClientId@@YA?AUCallerId@@XZ; GetCallerClientId(void)
0x180026b82  mov     [rsp+88h+arg_18], ebx
0x180026b89  cmp     eax, 0FFFFFFFDh
0x180026b8c  jbe     loc_180026D4D
0x180026b92  call    cs:__imp_GetCurrentProcessId
0x180026b98  mov     r13d, eax
0x180026b9b  mov     ecx, 3E80h; unsigned __int64
0x180026ba0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180026ba5  mov     rdi, rax
0x180026ba8  test    rax, rax
0x180026bab  jz      loc_180026D39
0x180026bb1  mov     ecx, 640h; unsigned __int64
0x180026bb6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180026bbb  mov     rbx, rax
0x180026bbe  test    rax, rax
0x180026bc1  jz      loc_180026CEE
0x180026bc7  xor     ebp, ebp
0x180026bc9  cmp     ebp, [rsp+88h+arg_8]
0x180026bd0  jnb     loc_180026CA6
0x180026bd6  mov     rax, [r12+rbp*8]
0x180026bda  lea     rcx, ds:0[rbp*4]
0x180026be2  add     rcx, rbp
0x180026be5  shl     rcx, 4
0x180026be9  add     rcx, rdi
0x180026bec  movups  xmm0, xmmword ptr [rax]
0x180026bef  movups  xmm1, xmmword ptr [rax+10h]
0x180026bf3  movups  xmm2, xmmword ptr [rax+20h]
0x180026bf7  movups  xmm3, xmmword ptr [rax+30h]
0x180026bfb  movups  xmm4, xmmword ptr [rax+40h]
0x180026bff  movups  xmmword ptr [rcx], xmm0
0x180026c02  movups  xmmword ptr [rcx+10h], xmm1
0x180026c06  movups  xmmword ptr [rcx+20h], xmm2
0x180026c0a  movups  xmmword ptr [rcx+30h], xmm3
0x180026c0e  movups  xmmword ptr [rcx+40h], xmm4
0x180026c12  mov     [rcx+48h], r13d
0x180026c16  mov     [rbx+rbp*8], rcx
0x180026c1a  inc     ebp
0x180026c1c  cmp     ebp, 0C8h
0x180026c22  jnz     short loc_180026BC9
0x180026c24  mov     rax, [r14]
0x180026c27  xor     r9d, r9d
0x180026c2a  mov     r8, rbx
0x180026c2d  mov     edx, ebp
0x180026c2f  mov     rcx, r14
0x180026c32  mov     rax, [rax+20h]
0x180026c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c3b  mov     r12d, eax
0x180026c3e  test    eax, eax
0x180026c40  jns     loc_180026DC8
0x180026c46  mov     ebp, 1
0x180026c4b  mov     ecx, eax
0x180026c4d  mov     edx, ebp
0x180026c4f  lea     r9d, [rbp+6Bh]
0x180026c53  call    Log_UnistoreHREvent_20
0x180026c58  mov     rcx, rbx; Block
0x180026c5b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026c60  mov     rcx, rdi; Block
0x180026c63  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026c68  mov     rdx, [r15]
0x180026c6b  mov     r9d, ebp
0x180026c6e  xor     r8d, r8d
0x180026c71  mov     rcx, r15
0x180026c74  mov     rax, [rdx+20h]
0x180026c78  xor     edx, edx
0x180026c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c7f  test    eax, eax
0x180026c81  jns     short loc_180026C92
0x180026c83  xor     edx, edx
0x180026c85  mov     r9d, 0CDh
0x180026c8b  mov     ecx, eax
0x180026c8d  call    Log_UnistoreHREvent_20
0x180026c92  test    rsi, rsi
0x180026c95  jz      short loc_180026CA1
0x180026c97  lea     rcx, [rsi+8]; lpCriticalSection
0x180026c9b  call    cs:__imp_LeaveCriticalSection
0x180026ca1  mov     eax, r12d
0x180026ca4  jmp     short loc_180026D21
0x180026ca6  test    ebp, ebp
0x180026ca8  jz      short loc_180026CCB
0x180026caa  mov     rax, [r14]
0x180026cad  xor     r9d, r9d
0x180026cb0  mov     r8, rbx
0x180026cb3  mov     edx, ebp
0x180026cb5  mov     rcx, r14
0x180026cb8  mov     rax, [rax+20h]
0x180026cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cc1  mov     ebp, eax
0x180026cc3  test    eax, eax
0x180026cc5  js      loc_180026DD5
0x180026ccb  mov     rcx, rbx; Block
0x180026cce  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026cd3  mov     rcx, rdi; Block
0x180026cd6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026cdb  test    rsi, rsi
0x180026cde  jz      short loc_180026CEA
0x180026ce0  lea     rcx, [rsi+8]; lpCriticalSection
0x180026ce4  call    cs:__imp_LeaveCriticalSection
0x180026cea  xor     eax, eax
0x180026cec  jmp     short loc_180026D21
0x180026cee  xor     edx, edx
0x180026cf0  mov     ebp, 8007000Eh
0x180026cf5  mov     ecx, ebp
0x180026cf7  lea     r9d, [rdx+61h]
0x180026cfb  call    Log_UnistoreHREvent_20
0x180026d00  mov     rcx, rdi; Block
0x180026d03  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026d08  lea     rcx, [rsp+88h+var_58]
0x180026d0d  call    tlx___UndoSolo__lambda_e4b4baa9baf3de765227b06144d2e027_______UndoSolo__lambda_e4b4baa9baf3de765227b06144d2e027___
0x180026d12  lea     rcx, [rsp+88h+arg_0]
0x180026d1a  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x180026d1f  mov     eax, ebp
0x180026d21  add     rsp, 48h
0x180026d25  pop     r15
0x180026d27  pop     r14
0x180026d29  pop     r13
0x180026d2b  pop     r12
0x180026d2d  pop     rdi
0x180026d2e  pop     rsi
0x180026d2f  pop     rbp
0x180026d30  pop     rbx
0x180026d31  retn
0x180026d32  xor     esi, esi
0x180026d34  jmp     loc_180026B4E
0x180026d39  xor     edx, edx
0x180026d3b  mov     ebp, 8007000Eh
0x180026d40  lea     r9d, [rdx+5Eh]
0x180026d44  mov     ecx, ebp
0x180026d46  call    Log_UnistoreHREvent_20
0x180026d4b  jmp     short loc_180026D08
0x180026d4d  lea     r8, [rsp+88h+arg_18]; unsigned int *
0x180026d55  mov     edx, eax; unsigned int
0x180026d57  call    ?GetProcessIdFromRundownProtectionId@RundownProtectionList@@QEAAHKPEAK@Z; RundownProtectionList::GetProcessIdFromRundownProtectionId(ulong,ulong *)
0x180026d5c  test    eax, eax
0x180026d5e  jz      short loc_180026DA0
0x180026d60  mov     r13d, [rsp+88h+arg_18]
0x180026d68  jmp     loc_180026B9B
0x180026d6d  mov     rax, [r15]
0x180026d70  mov     r9d, edi
0x180026d73  xor     r8d, r8d
0x180026d76  xor     edx, edx
0x180026d78  mov     rcx, r15
0x180026d7b  mov     rax, [rax+20h]
0x180026d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d84  test    eax, eax
0x180026d86  jns     loc_180026CDB
0x180026d8c  xor     edx, edx
0x180026d8e  mov     r9d, 0CDh
0x180026d94  mov     ecx, eax
0x180026d96  call    Log_UnistoreHREvent_20
0x180026d9b  jmp     loc_180026CDB
0x180026da0  mov     ebp, 8000001Ah
0x180026da5  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180026dac  mov     ecx, ebp
0x180026dae  mov     r9d, 49Dh
0x180026db4  xor     edx, edx
0x180026db6  call    Log_UnistoreHREvent_0
0x180026dbb  mov     r9d, 5Ah ; 'Z'
0x180026dc1  mov     edx, edi
0x180026dc3  jmp     loc_180026D44
0x180026dc8  mov     r12, [rsp+88h+arg_10]
0x180026dd0  jmp     loc_180026BC9
0x180026dd5  mov     edx, 1
0x180026dda  mov     ecx, eax
0x180026ddc  lea     r9d, [rdx+73h]
0x180026de0  call    Log_UnistoreHREvent_20
0x180026de5  mov     rcx, rbx; Block
0x180026de8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026ded  jmp     loc_180026D00
```
