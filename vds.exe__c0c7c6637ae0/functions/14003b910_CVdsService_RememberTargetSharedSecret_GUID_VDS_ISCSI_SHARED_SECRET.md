# CVdsService::RememberTargetSharedSecret(_GUID,_VDS_ISCSI_SHARED_SECRET *)

- ea: `0x14003b910`
- end: `0x14003bbe5`
- name: `?RememberTargetSharedSecret@CVdsService@@UEAAJU_GUID@@PEAU_VDS_ISCSI_SHARED_SECRET@@@Z`
- size: `725`
- prototype: `__int64 __fastcall(CVdsService *__hidden this, struct _GUID *__struct_ptr, struct _VDS_ISCSI_SHARED_SECRET *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14000dd3c`
- `0x140012c48`
- `0x14002e123`
- `0x14003b910`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003bb43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003bb5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003bb43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003bb5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003b9e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003b9e8`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003b97a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003b97a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003b9bb`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003bbaf`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003b9bb`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003bbaf`
- `vdsutil!VdsTraceW` at `0x14003ba93`
- `vdsutil!VdsTraceW` at `0x14003baae`
- `vdsutil!VdsTraceW` at `0x14003bb2f`
- `vdsutil!VdsTraceW` at `0x14003bb7f`
- `vdsutil!VdsTraceW` at `0x14003bba0`
- `vdsutil!VdsTraceW` at `0x14003ba93`
- `vdsutil!VdsTraceW` at `0x14003baae`
- `vdsutil!VdsTraceW` at `0x14003bb2f`
- `vdsutil!VdsTraceW` at `0x14003bb7f`
- `vdsutil!VdsTraceW` at `0x14003bba0`

## string_xrefs

- `0x14003b96a`: `CVdsService::RememberTargetSharedSecret()`
- `0x14003bb97`: `CVdsService::RememberTargetSharedSecret: Could not access necessary function in iSCSI library.`
- `0x14003ba26`: `CVdsService::RememberTargetSharedSecret, 1, %lX`
- `0x14003bb8e`: `CVdsService::RememberTargetSharedSecret: Could not retrieve target object from provider: %X`
- `0x14003bb73`: `CVdsService::RememberTargetSharedSecret: spTargetUnk->QueryInterface IID_IVdsIscsiTarget: %X`
- `0x14003ba8a`: `CVdsService::RememberTargetSharedSecret: spTarget->GetProperties: %X`
- `0x14003baa7`: `CVdsService::RememberTargetSharedSecret: Invalid target target iSCSI name retrieved from provider.`
- `0x14003bb26`: `CVdsService::RememberTargetSharedSecret: AddIScsiStaticTarget failed: %X`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CVdsService::RememberTargetSharedSecret(
        CVdsService *this,
        struct _GUID *a2,
        struct _VDS_ISCSI_SHARED_SECRET *a3)
{
  int ObjectFromProviders; // ebx
  FARPROC ProcAddress; // rsi
  int v8; // eax
  __int64 v9; // r9
  unsigned int v10; // eax
  __int64 v12; // [rsp+40h] [rbp-69h] BYREF
  struct IUnknown *v13; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v14[16]; // [rsp+50h] [rbp-59h] BYREF
  struct _GUID v15; // [rsp+60h] [rbp-49h] BYREF
  _DWORD v16[14]; // [rsp+70h] [rbp-39h] BYREF
  UCHAR *pSharedSecret; // [rsp+A8h] [rbp-1h]
  __int128 v18; // [rsp+B0h] [rbp+7h] BYREF
  LPVOID pv[2]; // [rsp+C0h] [rbp+17h]
  __int64 v20; // [rsp+D0h] [rbp+27h]

  v13 = 0;
  v12 = 0;
  v18 = 0;
  *(_OWORD *)pv = 0;
  v20 = 0;
  memset_0(v16, 0, 0x40u);
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v14, 0x5Eu, "CVdsService::RememberTargetSharedSecret()");
  v18 = 0;
  *(_OWORD *)pv = 0;
  v20 = 0;
  memset_0(v16, 0, 0x40u);
  ObjectFromProviders = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 2) + 32LL))((char *)this - 16);
  if ( ObjectFromProviders >= 0 )
  {
    if ( !CVdsService::m_hIscsidscModule
      || (ProcAddress = GetProcAddress(CVdsService::m_hIscsidscModule, "AddIScsiStaticTargetW")) == 0 )
    {
      VdsTraceW(0, L"CVdsService::RememberTargetSharedSecret: Could not access necessary function in iSCSI library.");
      ObjectFromProviders = -2147212288;
      goto LABEL_33;
    }
    v15 = *a2;
    ObjectFromProviders = CVdsService::GetObjectFromProviders(&v15, VDS_OT_TARGET, &v13);
    if ( ObjectFromProviders == -2147212283 )
    {
      ObjectFromProviders = -2147024809;
      VdsTraceW(0, L"CVdsService::RememberTargetSharedSecret, 1, %lX", 2147942487LL);
LABEL_33:
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v14);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
      goto LABEL_34;
    }
    if ( ObjectFromProviders >= 0 && v13 )
    {
      ObjectFromProviders = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v13->lpVtbl->QueryInterface)(
                              v13,
                              &IID_IVdsIscsiTarget,
                              &v12);
      if ( ObjectFromProviders >= 0 && v12 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v12 + 24LL))(v12, &v18);
        ObjectFromProviders = v8;
        if ( v8 < 0 )
        {
          VdsTraceW(0, L"CVdsService::RememberTargetSharedSecret: spTarget->GetProperties: %X", (unsigned int)v8);
          goto LABEL_33;
        }
        if ( pv[0] )
        {
          v16[0] = 0;
          v16[1] = 64;
          if ( a3 )
          {
            v16[10] = a3->ulSharedSecretSize;
            pSharedSecret = a3->pSharedSecret;
          }
          LOBYTE(v9) = 1;
          v10 = ((__int64 (__fastcall *)(LPVOID, LPVOID, _QWORD, __int64, _QWORD, _DWORD *, _QWORD))ProcAddress)(
                  pv[0],
                  pv[1],
                  0,
                  v9,
                  0,
                  v16,
                  0);
          if ( v10 && ((v10 & 0xFFF0000) == 0 || (v10 & 0xC0000000) == 0xC0000000) )
          {
            VdsTraceW(0, L"CVdsService::RememberTargetSharedSecret: AddIScsiStaticTarget failed: %X", v10);
            ObjectFromProviders = -2147467259;
          }
          if ( pv[0] )
          {
            CoTaskMemFree(pv[0]);
            pv[0] = 0;
          }
          if ( pv[1] )
            CoTaskMemFree(pv[1]);
          v18 = 0;
          *(_OWORD *)pv = 0;
          v20 = 0;
          goto LABEL_33;
        }
        VdsTraceW(
          0,
          L"CVdsService::RememberTargetSharedSecret: Invalid target target iSCSI name retrieved from provider.");
LABEL_16:
        ObjectFromProviders = -2147467259;
        goto LABEL_33;
      }
      VdsTraceW(
        0,
        L"CVdsService::RememberTargetSharedSecret: spTargetUnk->QueryInterface IID_IVdsIscsiTarget: %X",
        (unsigned int)ObjectFromProviders);
    }
    else
    {
      VdsTraceW(
        0,
        L"CVdsService::RememberTargetSharedSecret: Could not retrieve target object from provider: %X",
        (unsigned int)ObjectFromProviders);
    }
    if ( ObjectFromProviders < 0 )
      goto LABEL_33;
    goto LABEL_16;
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v14);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
LABEL_34:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v13);
  return (unsigned int)ObjectFromProviders;
}

```

## disassembly

```asm
0x14003b910  push    rbp
0x14003b912  push    rbx
0x14003b913  push    rsi
0x14003b914  push    rdi
0x14003b915  push    r14
0x14003b917  lea     rbp, [rsp-37h]
0x14003b91c  sub     rsp, 0E0h
0x14003b923  mov     rax, cs:__security_cookie
0x14003b92a  xor     rax, rsp
0x14003b92d  mov     [rbp+57h+var_28], rax
0x14003b931  mov     rdi, r8
0x14003b934  mov     r14, rdx
0x14003b937  mov     rbx, rcx
0x14003b93a  mov     [rbp+57h+var_B8], 0
0x14003b942  mov     [rbp+57h+var_C0], 0
0x14003b94a  xorps   xmm0, xmm0
0x14003b94d  xor     eax, eax
0x14003b94f  movups  [rbp+57h+var_50], xmm0
0x14003b953  movups  xmmword ptr [rbp+57h+pv], xmm0
0x14003b957  mov     [rbp+57h+var_30], rax
0x14003b95b  xor     edx, edx; Val
0x14003b95d  lea     r8d, [rax+40h]; Size
0x14003b961  lea     rcx, [rbp+57h+var_90]; void *
0x14003b965  call    memset_0
0x14003b96a  lea     r8, aCvdsserviceRem_30; "CVdsService::RememberTargetSharedSecret"...
0x14003b971  mov     edx, 5Eh ; '^'
0x14003b976  lea     rcx, [rbp+57h+var_B0]
0x14003b97a  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003b980  nop
0x14003b981  xorps   xmm0, xmm0
0x14003b984  xor     eax, eax
0x14003b986  movups  [rbp+57h+var_50], xmm0
0x14003b98a  movups  xmmword ptr [rbp+57h+pv], xmm0
0x14003b98e  mov     [rbp+57h+var_30], rax
0x14003b992  xor     edx, edx; Val
0x14003b994  lea     r8d, [rax+40h]; Size
0x14003b998  lea     rcx, [rbp+57h+var_90]; void *
0x14003b99c  call    memset_0
0x14003b9a1  lea     rcx, [rbx-10h]
0x14003b9a5  mov     rax, [rcx]
0x14003b9a8  mov     rax, [rax+20h]
0x14003b9ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b9b1  mov     ebx, eax
0x14003b9b3  test    eax, eax
0x14003b9b5  jns     short loc_14003B9D1
0x14003b9b7  lea     rcx, [rbp+57h+var_B0]
0x14003b9bb  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003b9c1  nop
0x14003b9c2  lea     rcx, [rbp+57h+var_C0]
0x14003b9c6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003b9cb  nop
0x14003b9cc  jmp     loc_14003BBC0
0x14003b9d1  mov     rcx, cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x14003b9d8  test    rcx, rcx
0x14003b9db  jz      loc_14003BB97
0x14003b9e1  lea     rdx, aAddiscsistatic; "AddIScsiStaticTargetW"
0x14003b9e8  call    cs:__imp_GetProcAddress
0x14003b9ee  mov     rsi, rax
0x14003b9f1  test    rax, rax
0x14003b9f4  jz      loc_14003BB97
0x14003b9fa  movups  xmm0, xmmword ptr [r14]
0x14003b9fe  movdqu  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x14003ba03  lea     r8, [rbp+57h+var_B8]; struct IUnknown **
0x14003ba07  mov     edx, 25h ; '%'; enum _VDS_OBJECT_TYPE
0x14003ba0c  lea     rcx, [rbp+57h+var_A0]; struct _GUID
0x14003ba10  call    ?GetObjectFromProviders@CVdsService@@SAJU_GUID@@W4_VDS_OBJECT_TYPE@@PEAPEAUIUnknown@@@Z; CVdsService::GetObjectFromProviders(_GUID,_VDS_OBJECT_TYPE,IUnknown * *)
0x14003ba15  mov     ebx, eax
0x14003ba17  cmp     eax, 80042405h
0x14003ba1c  jnz     short loc_14003BA2F
0x14003ba1e  mov     ebx, 80070057h
0x14003ba23  mov     r8d, ebx
0x14003ba26  lea     rdx, aCvdsserviceRem_0; "CVdsService::RememberTargetSharedSecret"...
0x14003ba2d  jmp     short loc_14003BA91
0x14003ba2f  test    ebx, ebx
0x14003ba31  js      loc_14003BB8E
0x14003ba37  mov     rcx, [rbp+57h+var_B8]
0x14003ba3b  test    rcx, rcx
0x14003ba3e  jz      loc_14003BB8E
0x14003ba44  mov     rax, [rcx]
0x14003ba47  lea     r8, [rbp+57h+var_C0]
0x14003ba4b  lea     rdx, IID_IVdsIscsiTarget
0x14003ba52  mov     rax, [rax]
0x14003ba55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ba5a  mov     ebx, eax
0x14003ba5c  test    eax, eax
0x14003ba5e  js      loc_14003BB73
0x14003ba64  mov     rcx, [rbp+57h+var_C0]
0x14003ba68  test    rcx, rcx
0x14003ba6b  jz      loc_14003BB73
0x14003ba71  mov     rax, [rcx]
0x14003ba74  lea     rdx, [rbp+57h+var_50]
0x14003ba78  mov     rax, [rax+18h]
0x14003ba7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ba81  mov     ebx, eax
0x14003ba83  test    eax, eax
0x14003ba85  jns     short loc_14003BA9E
0x14003ba87  mov     r8d, eax
0x14003ba8a  lea     rdx, aCvdsserviceRem_8; "CVdsService::RememberTargetSharedSecret"...
0x14003ba91  xor     ecx, ecx
0x14003ba93  call    cs:__imp_VdsTraceW
0x14003ba99  jmp     loc_14003BBAB
0x14003ba9e  mov     rcx, [rbp+57h+pv]
0x14003baa2  test    rcx, rcx
0x14003baa5  jnz     short loc_14003BABE
0x14003baa7  lea     rdx, aCvdsserviceRem_20; "CVdsService::RememberTargetSharedSecret"...
0x14003baae  call    cs:__imp_VdsTraceW
0x14003bab4  mov     ebx, 80004005h
0x14003bab9  jmp     loc_14003BBAB
0x14003babe  mov     [rbp+57h+var_90], 0
0x14003bac5  mov     [rbp+57h+var_8C], 40h ; '@'
0x14003bacc  test    rdi, rdi
0x14003bacf  jz      short loc_14003BADE
0x14003bad1  mov     eax, [rdi+8]
0x14003bad4  mov     [rbp+57h+var_68], eax
0x14003bad7  mov     rax, [rdi]
0x14003bada  mov     [rbp+57h+var_58], rax
0x14003bade  mov     [rsp+100h+var_D0], 0
0x14003bae7  lea     rax, [rbp+57h+var_90]
0x14003baeb  mov     [rsp+100h+var_D8], rax
0x14003baf0  mov     [rsp+100h+var_E0], 0
0x14003baf9  mov     r9b, 1
0x14003bafc  xor     r8d, r8d
0x14003baff  mov     rdx, [rbp+57h+pv+8]
0x14003bb03  mov     rax, rsi
0x14003bb06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bb0b  test    eax, eax
0x14003bb0d  jz      short loc_14003BB3A
0x14003bb0f  test    eax, 0FFF0000h
0x14003bb14  jz      short loc_14003BB23
0x14003bb16  mov     ecx, eax
0x14003bb18  mov     edx, 0C0000000h
0x14003bb1d  and     ecx, edx
0x14003bb1f  cmp     ecx, edx
0x14003bb21  jnz     short loc_14003BB3A
0x14003bb23  mov     r8d, eax
0x14003bb26  lea     rdx, aCvdsserviceRem_21; "CVdsService::RememberTargetSharedSecret"...
0x14003bb2d  xor     ecx, ecx
0x14003bb2f  call    cs:__imp_VdsTraceW
0x14003bb35  mov     ebx, 80004005h
0x14003bb3a  mov     rcx, [rbp+57h+pv]; pv
0x14003bb3e  test    rcx, rcx
0x14003bb41  jz      short loc_14003BB51
0x14003bb43  call    cs:__imp_CoTaskMemFree
0x14003bb49  mov     [rbp+57h+pv], 0
0x14003bb51  mov     rcx, [rbp+57h+pv+8]; pv
0x14003bb55  test    rcx, rcx
0x14003bb58  jz      short loc_14003BB60
0x14003bb5a  call    cs:__imp_CoTaskMemFree
0x14003bb60  xorps   xmm0, xmm0
0x14003bb63  xor     eax, eax
0x14003bb65  movups  [rbp+57h+var_50], xmm0
0x14003bb69  movups  xmmword ptr [rbp+57h+pv], xmm0
0x14003bb6d  mov     [rbp+57h+var_30], rax
0x14003bb71  jmp     short loc_14003BBAB
0x14003bb73  lea     rdx, aCvdsserviceRem_15; "CVdsService::RememberTargetSharedSecret"...
0x14003bb7a  mov     r8d, ebx
0x14003bb7d  xor     ecx, ecx
0x14003bb7f  call    cs:__imp_VdsTraceW
0x14003bb85  test    ebx, ebx
0x14003bb87  js      short loc_14003BBAB
0x14003bb89  jmp     loc_14003BAB4
0x14003bb8e  lea     rdx, aCvdsserviceRem_25; "CVdsService::RememberTargetSharedSecret"...
0x14003bb95  jmp     short loc_14003BB7A
0x14003bb97  lea     rdx, aCvdsserviceRem_32; "CVdsService::RememberTargetSharedSecret"...
0x14003bb9e  xor     ecx, ecx
0x14003bba0  call    cs:__imp_VdsTraceW
0x14003bba6  mov     ebx, 80042400h
0x14003bbab  lea     rcx, [rbp+57h+var_B0]
0x14003bbaf  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003bbb5  nop
0x14003bbb6  lea     rcx, [rbp+57h+var_C0]
0x14003bbba  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003bbbf  nop
0x14003bbc0  lea     rcx, [rbp+57h+var_B8]
0x14003bbc4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14003bbc9  mov     eax, ebx
0x14003bbcb  mov     rcx, [rbp+57h+var_28]
0x14003bbcf  xor     rcx, rsp; StackCookie
0x14003bbd2  call    __security_check_cookie
0x14003bbd7  add     rsp, 0E0h
0x14003bbde  pop     r14
0x14003bbe0  pop     rdi
0x14003bbe1  pop     rsi
0x14003bbe2  pop     rbx
0x14003bbe3  pop     rbp
0x14003bbe4  retn
```
