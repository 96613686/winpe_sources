# CThirdPartyManager::LoadWmiInstances(_SECURITY_PRODUCT_TYPE,CWmiEventManager *,CList<ushort *,ushort *> *)

- ea: `0x180037460`
- end: `0x180037680`
- name: `?LoadWmiInstances@CThirdPartyManager@@QEAAJW4_SECURITY_PRODUCT_TYPE@@PEAVCWmiEventManager@@PEAV?$CList@PEAGPEAG@@@Z`
- size: `544`
- prototype: `__int64 __fastcall(CThirdPartyManager *this, unsigned int, struct IWbemServices *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001d9e0`

## callees

- `0x180018774`
- `0x180018b60`
- `0x18001c4c0`
- `0x18002698c`
- `0x1800371ec`
- `0x180037460`
- `0x18003e88c`
- `0x180042010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800374da`
- `OLEAUT32!__imp_SysAllocString` at `0x1800374da`
- `OLEAUT32!__imp_SysFreeString` at `0x18003765d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003765d`

## pseudocode

```c
__int64 __fastcall CThirdPartyManager::LoadWmiInstances(
        CThirdPartyManager *this,
        unsigned int a2,
        struct IWbemServices *a3,
        __int64 a4)
{
  CWmiEventManager *v7; // rdi
  __int64 v9; // rdx
  int WbemServices; // ebx
  __int64 (__fastcall ***v11)(_QWORD, __int64); // rcx
  OLECHAR *v12; // r14
  const OLECHAR *v13; // rax
  struct IWbemServices *v14; // r12
  int v15; // eax
  int v16; // edi
  enum _SECURITY_PRODUCT_TYPE v17; // ecx
  int v18; // eax
  struct CExternalBase *v19; // [rsp+30h] [rbp-38h] BYREF
  __int64 (__fastcall ***v20)(_QWORD, __int64); // [rsp+38h] [rbp-30h] BYREF
  __int64 *v21; // [rsp+40h] [rbp-28h] BYREF
  __int64 v22; // [rsp+48h] [rbp-20h]
  __int64 (__fastcall ***v23)(_QWORD, __int64); // [rsp+50h] [rbp-18h] BYREF
  struct IWbemServices *v24; // [rsp+C0h] [rbp+58h] BYREF

  v24 = a3;
  v7 = g_pWmiEventManagerAvFw;
  if ( !g_pWmiEventManagerAvFw )
    return 2147942487LL;
  v20 = 0;
  WbemServices = (*(__int64 (__fastcall **)(CThirdPartyManager *, _QWORD))(*(_QWORD *)this + 40LL))(this, &v20);
  v11 = v20;
  v23 = v20;
  v20 = 0;
  if ( WbemServices >= 0 )
  {
    v12 = 0;
    if ( v11 )
    {
      v13 = (const OLECHAR *)((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64)))(*v11)[2])(v11);
      v12 = SysAllocString(v13);
      if ( !v12 )
      {
        WbemServices = -2147024882;
        goto LABEL_29;
      }
    }
    v24 = 0;
    WbemServices = CWmiEventManager::GetWbemServices(v7, v9, &v24);
    if ( WbemServices < 0 )
    {
LABEL_28:
      SysFreeString(v12);
      goto LABEL_29;
    }
    v22 = 0;
    v14 = v24;
    v15 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, __int64))v24->lpVtbl->CreateInstanceEnum)(
            v24,
            v12,
            32);
    WbemServices = v15;
    if ( v15 < 0 )
    {
LABEL_27:
      ((void (__fastcall *)(struct IWbemServices *))v14->lpVtbl->Release)(v14);
      goto LABEL_28;
    }
    v16 = 0;
    if ( !v15 )
    {
      while ( 1 )
      {
        v21 = 0;
        LODWORD(v24) = 0;
        WbemServices = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 **, struct IWbemServices **))(*(_QWORD *)v22 + 32LL))(
                         v22,
                         1000,
                         1,
                         &v21,
                         &v24);
        if ( WbemServices )
          break;
        ++v16;
        v19 = 0;
        if ( (int)CThirdPartyManager::CreateExternalBaseFromWbemProduct(
                    (CSecurityVerificationManager **)this,
                    a2,
                    v21,
                    &v19,
                    a4) >= 0 )
        {
          CThirdPartyManager::UpdateExternalProduct(this, v19);
          WscTelemetryEventWriteProductLoad(v19, 0);
          if ( v19 )
            (**(void (__fastcall ***)(struct CExternalBase *, _QWORD))v19)(v19, (unsigned int)(WbemServices + 1));
        }
        (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
      }
    }
    if ( a2 == 1 )
    {
      if ( g_dwFwMigrated || v16 )
        goto LABEL_24;
      g_dwFwMigrated = 1;
      v17 = SECURITY_PRODUCT_TYPE_FIREWALL;
    }
    else
    {
      if ( a2 || g_dwAvMigrated || v16 )
        goto LABEL_24;
      g_dwAvMigrated = 1;
      v17 = SECURITY_PRODUCT_TYPE_ANTIVIRUS;
    }
    WscMigrationComplete(v17);
LABEL_24:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v18 = 0;
    if ( WbemServices != 1 )
      v18 = WbemServices;
    WbemServices = v18;
    goto LABEL_27;
  }
LABEL_29:
  CommonUtil::CAutoUniquePtr<CExternalBase,void>::~CAutoUniquePtr<CExternalBase,void>(&v23);
  return (unsigned int)WbemServices;
}

```

## disassembly

```asm
0x180037460  mov     [rsp-40h+arg_10], r8
0x180037465  push    rbp
0x180037466  push    rbx
0x180037467  push    rsi
0x180037468  push    rdi
0x180037469  push    r12
0x18003746b  push    r13
0x18003746d  push    r14
0x18003746f  push    r15
0x180037471  mov     rbp, rsp
0x180037474  sub     rsp, 68h
0x180037478  mov     r13, r9
0x18003747b  mov     esi, edx
0x18003747d  mov     r15, rcx
0x180037480  mov     rdi, cs:?g_pWmiEventManagerAvFw@@3PEAVCWmiEventManagerAvFw@@EA; CWmiEventManagerAvFw * g_pWmiEventManagerAvFw
0x180037487  xor     r12d, r12d
0x18003748a  test    rdi, rdi
0x18003748d  jnz     short loc_180037499
0x18003748f  mov     eax, 80070057h
0x180037494  jmp     loc_18003766F
0x180037499  mov     [rbp+var_30], r12
0x18003749d  mov     rax, [rcx]
0x1800374a0  lea     rdx, [rbp+var_30]
0x1800374a4  mov     rax, [rax+28h]
0x1800374a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374ad  mov     ebx, eax
0x1800374af  mov     rcx, [rbp+var_30]
0x1800374b3  mov     [rbp+var_18], rcx
0x1800374b7  mov     [rbp+var_30], r12
0x1800374bb  test    eax, eax
0x1800374bd  js      loc_180037664
0x1800374c3  mov     r14, r12
0x1800374c6  test    rcx, rcx
0x1800374c9  jz      short loc_1800374F2
0x1800374cb  mov     rax, [rcx]
0x1800374ce  mov     rax, [rax+10h]
0x1800374d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374d7  mov     rcx, rax; psz
0x1800374da  call    cs:__imp_SysAllocString
0x1800374e0  mov     r14, rax
0x1800374e3  test    rax, rax
0x1800374e6  jnz     short loc_1800374F2
0x1800374e8  mov     ebx, 8007000Eh
0x1800374ed  jmp     loc_180037664
0x1800374f2  mov     [rbp+arg_10], r12
0x1800374f6  lea     r8, [rbp+arg_10]; struct IWbemServices **
0x1800374fa  mov     rcx, rdi; this
0x1800374fd  call    ?GetWbemServices@CWmiEventManager@@QEAAJHPEAPEAUIWbemServices@@@Z; CWmiEventManager::GetWbemServices(int,IWbemServices * *)
0x180037502  mov     ebx, eax
0x180037504  test    eax, eax
0x180037506  js      loc_18003765A
0x18003750c  mov     [rbp+var_20], r12
0x180037510  mov     r12, [rbp+arg_10]
0x180037514  mov     rax, [r12]
0x180037518  lea     rcx, [rbp+var_20]
0x18003751c  mov     [rsp+68h+var_48], rcx
0x180037521  xor     r9d, r9d
0x180037524  lea     r8d, [r9+20h]
0x180037528  mov     rdx, r14
0x18003752b  mov     rcx, r12
0x18003752e  mov     rax, [rax+90h]
0x180037535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003753a  mov     ebx, eax
0x18003753c  test    eax, eax
0x18003753e  js      loc_18003764A
0x180037544  xor     edi, edi
0x180037546  test    eax, eax
0x180037548  jnz     loc_1800375F3
0x18003754e  mov     [rbp+var_28], 0
0x180037556  mov     dword ptr [rbp+arg_10], 0
0x18003755d  mov     rcx, [rbp+var_20]
0x180037561  mov     rax, [rcx]
0x180037564  lea     rdx, [rbp+arg_10]
0x180037568  mov     [rsp+68h+var_48], rdx
0x18003756d  lea     r9, [rbp+var_28]
0x180037571  mov     edx, 3E8h
0x180037576  mov     r8d, 1
0x18003757c  mov     rax, [rax+20h]
0x180037580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037585  mov     ebx, eax
0x180037587  test    eax, eax
0x180037589  jnz     short loc_1800375F3
0x18003758b  inc     edi
0x18003758d  mov     [rbp+var_38], 0
0x180037595  mov     [rsp+68h+var_48], r13; __int64
0x18003759a  lea     r9, [rbp+var_38]
0x18003759e  mov     r8, [rbp+var_28]
0x1800375a2  mov     edx, esi; enum _SECURITY_PRODUCT_TYPE
0x1800375a4  mov     rcx, r15; this
0x1800375a7  call    ?CreateExternalBaseFromWbemProduct@CThirdPartyManager@@QEAAJW4_SECURITY_PRODUCT_TYPE@@PEAUIWbemClassObject@@PEAPEAVCExternalBase@@PEAV?$CList@PEAGPEAG@@@Z; CThirdPartyManager::CreateExternalBaseFromWbemProduct(_SECURITY_PRODUCT_TYPE,IWbemClassObject *,CExternalBase * *,CList<ushort *,ushort *> *)
0x1800375ac  test    eax, eax
0x1800375ae  js      short loc_1800375DE
0x1800375b0  mov     rdx, [rbp+var_38]; struct CExternalBase *
0x1800375b4  mov     rcx, r15; this
0x1800375b7  call    ?UpdateExternalProduct@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::UpdateExternalProduct(CExternalBase *)
0x1800375bc  xor     edx, edx; bool
0x1800375be  mov     rcx, [rbp+var_38]; this
0x1800375c2  call    ?WscTelemetryEventWriteProductLoad@@YAXPEAVCExternalBase@@_N@Z; WscTelemetryEventWriteProductLoad(CExternalBase *,bool)
0x1800375c7  mov     rcx, [rbp+var_38]
0x1800375cb  test    rcx, rcx
0x1800375ce  jz      short loc_1800375DE
0x1800375d0  mov     rax, [rcx]
0x1800375d3  lea     edx, [rbx+1]
0x1800375d6  mov     rax, [rax]
0x1800375d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375de  mov     rcx, [rbp+var_28]
0x1800375e2  mov     rax, [rcx]
0x1800375e5  mov     rax, [rax+10h]
0x1800375e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375ee  jmp     loc_18003754E
0x1800375f3  cmp     esi, 1
0x1800375f6  jnz     short loc_18003760F
0x1800375f8  cmp     cs:?g_dwFwMigrated@@3KA, 0; ulong g_dwFwMigrated
0x1800375ff  jnz     short loc_180037630
0x180037601  test    edi, edi
0x180037603  jnz     short loc_180037630
0x180037605  mov     cs:?g_dwFwMigrated@@3KA, esi; ulong g_dwFwMigrated
0x18003760b  mov     ecx, esi
0x18003760d  jmp     short loc_18003762B
0x18003760f  test    esi, esi
0x180037611  jnz     short loc_180037630
0x180037613  cmp     cs:?g_dwAvMigrated@@3KA, esi; ulong g_dwAvMigrated
0x180037619  jnz     short loc_180037630
0x18003761b  test    edi, edi
0x18003761d  jnz     short loc_180037630
0x18003761f  mov     cs:?g_dwAvMigrated@@3KA, 1; ulong g_dwAvMigrated
0x180037629  xor     ecx, ecx; enum _SECURITY_PRODUCT_TYPE
0x18003762b  call    ?WscMigrationComplete@@YAJW4_SECURITY_PRODUCT_TYPE@@@Z; WscMigrationComplete(_SECURITY_PRODUCT_TYPE)
0x180037630  mov     rcx, [rbp+var_20]
0x180037634  mov     rax, [rcx]
0x180037637  mov     rax, [rax+10h]
0x18003763b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037640  xor     eax, eax
0x180037642  cmp     ebx, 1
0x180037645  cmovnz  eax, ebx
0x180037648  mov     ebx, eax
0x18003764a  mov     rax, [r12]
0x18003764e  mov     rcx, r12
0x180037651  mov     rax, [rax+10h]
0x180037655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003765a  mov     rcx, r14; bstrString
0x18003765d  call    cs:__imp_SysFreeString
0x180037663  nop
0x180037664  lea     rcx, [rbp+var_18]
0x180037668  call    ??1?$CAutoUniquePtr@VCExternalBase@@X@CommonUtil@@QEAA@XZ; CommonUtil::CAutoUniquePtr<CExternalBase,void>::~CAutoUniquePtr<CExternalBase,void>(void)
0x18003766d  mov     eax, ebx
0x18003766f  add     rsp, 68h
0x180037673  pop     r15
0x180037675  pop     r14
0x180037677  pop     r13
0x180037679  pop     r12
0x18003767b  pop     rdi
0x18003767c  pop     rsi
0x18003767d  pop     rbx
0x18003767e  pop     rbp
0x18003767f  retn
```
