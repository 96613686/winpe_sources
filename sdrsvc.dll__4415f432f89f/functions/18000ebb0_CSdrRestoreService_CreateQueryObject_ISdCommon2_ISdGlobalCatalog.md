# CSdrRestoreService::CreateQueryObject(ISdCommon2 * *,ISdGlobalCatalog * *)

- ea: `0x18000ebb0`
- end: `0x18000ed9f`
- name: `?CreateQueryObject@CSdrRestoreService@@UEAAJPEAPEAUISdCommon2@@PEAPEAUISdGlobalCatalog@@@Z`
- size: `495`
- prototype: `__int64 __fastcall(CSdrRestoreService *__hidden this, struct ISdCommon2 **, struct ISdGlobalCatalog **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18000ebb0`
- `0x18001586c`
- `0x180015974`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ec5b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ec5b`

## string_xrefs

- `0x18000ebd1`: `CSdrRestoreService::CreateQueryObject`

## pseudocode

```c
__int64 __fastcall CSdrRestoreService::CreateQueryObject(
        CSdrRestoreService *this,
        struct ISdCommon2 **a2,
        struct ISdGlobalCatalog **a3)
{
  __int16 v5; // ax
  HRESULT v6; // ebx
  __int16 v7; // ax
  __int64 v9; // [rsp+30h] [rbp-40h] BYREF
  int v10; // [rsp+38h] [rbp-38h] BYREF
  __int16 v11; // [rsp+3Ch] [rbp-34h]
  __int16 v12; // [rsp+3Eh] [rbp-32h]
  struct ISdCommon2 *v13; // [rsp+98h] [rbp+28h] BYREF
  struct ISdGlobalCatalog *v14; // [rsp+A0h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+A8h] [rbp+38h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "CSdrRestoreService::CreateQueryObject", 0x44u, 1u);
  ppv = 0;
  v13 = 0;
  v14 = 0;
  v9 = 0;
  if ( a2 )
    *a2 = 0;
  v5 = 77;
  if ( a3 && (v11 = 77, v5 = 78, *a3 = 0, a2) )
  {
    v11 = 78;
    v10 = 0;
    v6 = CoCreateInstance(&CLSID_SdEngine2, 0, 1u, &IID_ISdRestoreObjectSetup, &ppv);
    v10 = v6;
    v7 = 80;
    if ( v6 < 0 )
      goto LABEL_6;
    v11 = 80;
    v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct ISdCommon2 **))ppv)(
           ppv,
           &GUID_c7930797_7deb_45c9_aa71_ae0dc66251d6,
           &v13);
    v10 = v6;
    v7 = 82;
    if ( v6 < 0 )
      goto LABEL_6;
    v11 = 82;
    v6 = (*(__int64 (__fastcall **)(struct ISdCommon2 *, __int64, GUID *, __int64 *))(*(_QWORD *)v13 + 24LL))(
           v13,
           12,
           &IID_IUnknown,
           &v9);
    v10 = v6;
    v7 = 84;
    if ( v6 < 0
      || (v11 = 84,
          v6 = (*(__int64 (__fastcall **)(LPVOID, struct ISdGlobalCatalog **))(*(_QWORD *)ppv + 24LL))(ppv, &v14),
          v10 = v6,
          v7 = 86,
          v6 < 0) )
    {
LABEL_6:
      v12 = v7;
    }
    else
    {
      v11 = 86;
      *a3 = v14;
      *a2 = v13;
      v14 = 0;
      v13 = 0;
    }
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    if ( v14 )
      (*(void (__fastcall **)(struct ISdGlobalCatalog *))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v13 )
      (*(void (__fastcall **)(struct ISdCommon2 *))(*(_QWORD *)v13 + 16LL))(v13);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  else
  {
    v6 = -2147024809;
    v12 = v5;
    v10 = -2147024809;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000ebb0  mov     [rsp-18h+arg_0], rbx
0x18000ebb5  push    rbp
0x18000ebb6  push    rsi
0x18000ebb7  push    rdi
0x18000ebb8  mov     rbp, rsp
0x18000ebbb  sub     rsp, 70h
0x18000ebbf  mov     ebx, 1
0x18000ebc4  lea     rcx, [rbp+var_38]; this
0x18000ebc8  mov     rsi, r8
0x18000ebcb  mov     rdi, rdx
0x18000ebce  mov     r9d, ebx; unsigned __int16
0x18000ebd1  lea     rdx, aCsdrrestoreser_1; "CSdrRestoreService::CreateQueryObject"
0x18000ebd8  lea     r8d, [rbx+43h]; unsigned __int16
0x18000ebdc  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000ebe1  mov     [rbp+arg_18], 0
0x18000ebe9  mov     [rbp+arg_8], 0
0x18000ebf1  mov     [rbp+arg_10], 0
0x18000ebf9  mov     [rbp+var_40], 0
0x18000ec01  test    rdi, rdi
0x18000ec04  jz      short loc_18000EC0D
0x18000ec06  mov     qword ptr [rdi], 0
0x18000ec0d  mov     eax, 4Dh ; 'M'
0x18000ec12  test    rsi, rsi
0x18000ec15  jz      loc_18000ED78
0x18000ec1b  mov     [rbp+var_34], ax
0x18000ec1f  mov     eax, 4Eh ; 'N'
0x18000ec24  mov     qword ptr [rsi], 0
0x18000ec2b  test    rdi, rdi
0x18000ec2e  jz      loc_18000ED78
0x18000ec34  mov     [rbp+var_34], ax
0x18000ec38  lea     r9, IID_ISdRestoreObjectSetup; riid
0x18000ec3f  lea     rax, [rbp+arg_18]
0x18000ec43  mov     [rbp+var_38], 0
0x18000ec4a  mov     r8d, ebx; dwClsContext
0x18000ec4d  mov     [rsp+70h+ppv], rax; ppv
0x18000ec52  xor     edx, edx; pUnkOuter
0x18000ec54  lea     rcx, CLSID_SdEngine2; rclsid
0x18000ec5b  call    cs:__imp_CoCreateInstance
0x18000ec61  mov     ebx, eax
0x18000ec63  mov     [rbp+var_38], eax
0x18000ec66  test    eax, eax
0x18000ec68  mov     eax, 50h ; 'P'
0x18000ec6d  jns     short loc_18000EC78
0x18000ec6f  mov     [rbp+var_32], ax
0x18000ec73  jmp     loc_18000ED22
0x18000ec78  mov     rcx, [rbp+arg_18]
0x18000ec7c  lea     r8, [rbp+arg_8]
0x18000ec80  mov     [rbp+var_34], ax
0x18000ec84  lea     rdx, _GUID_c7930797_7deb_45c9_aa71_ae0dc66251d6
0x18000ec8b  mov     rax, [rcx]
0x18000ec8e  mov     rax, [rax]
0x18000ec91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec96  mov     ebx, eax
0x18000ec98  mov     [rbp+var_38], eax
0x18000ec9b  test    eax, eax
0x18000ec9d  mov     eax, 52h ; 'R'
0x18000eca2  js      short loc_18000EC6F
0x18000eca4  mov     rcx, [rbp+arg_8]
0x18000eca8  lea     r9, [rbp+var_40]
0x18000ecac  mov     [rbp+var_34], ax
0x18000ecb0  lea     r8, IID_IUnknown
0x18000ecb7  mov     edx, 0Ch
0x18000ecbc  mov     rax, [rcx]
0x18000ecbf  mov     rax, [rax+18h]
0x18000ecc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecc8  mov     ebx, eax
0x18000ecca  mov     [rbp+var_38], eax
0x18000eccd  test    eax, eax
0x18000eccf  mov     eax, 54h ; 'T'
0x18000ecd4  js      short loc_18000EC6F
0x18000ecd6  mov     rcx, [rbp+arg_18]
0x18000ecda  lea     rdx, [rbp+arg_10]
0x18000ecde  mov     [rbp+var_34], ax
0x18000ece2  mov     rax, [rcx]
0x18000ece5  mov     rax, [rax+18h]
0x18000ece9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecee  mov     ebx, eax
0x18000ecf0  mov     [rbp+var_38], eax
0x18000ecf3  test    eax, eax
0x18000ecf5  mov     eax, 56h ; 'V'
0x18000ecfa  js      loc_18000EC6F
0x18000ed00  mov     [rbp+var_34], ax
0x18000ed04  mov     rax, [rbp+arg_10]
0x18000ed08  mov     [rsi], rax
0x18000ed0b  mov     rax, [rbp+arg_8]
0x18000ed0f  mov     [rdi], rax
0x18000ed12  mov     [rbp+arg_10], 0
0x18000ed1a  mov     [rbp+arg_8], 0
0x18000ed22  mov     rcx, [rbp+var_40]
0x18000ed26  test    rcx, rcx
0x18000ed29  jz      short loc_18000ED37
0x18000ed2b  mov     rax, [rcx]
0x18000ed2e  mov     rax, [rax+10h]
0x18000ed32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed37  mov     rcx, [rbp+arg_10]
0x18000ed3b  test    rcx, rcx
0x18000ed3e  jz      short loc_18000ED4C
0x18000ed40  mov     rax, [rcx]
0x18000ed43  mov     rax, [rax+10h]
0x18000ed47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed4c  mov     rcx, [rbp+arg_8]
0x18000ed50  test    rcx, rcx
0x18000ed53  jz      short loc_18000ED61
0x18000ed55  mov     rax, [rcx]
0x18000ed58  mov     rax, [rax+10h]
0x18000ed5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed61  mov     rcx, [rbp+arg_18]
0x18000ed65  test    rcx, rcx
0x18000ed68  jz      short loc_18000ED84
0x18000ed6a  mov     rax, [rcx]
0x18000ed6d  mov     rax, [rax+10h]
0x18000ed71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed76  jmp     short loc_18000ED84
0x18000ed78  mov     ebx, 80070057h
0x18000ed7d  mov     [rbp+var_32], ax
0x18000ed81  mov     [rbp+var_38], ebx
0x18000ed84  lea     rcx, [rbp+var_38]; this
0x18000ed88  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000ed8d  mov     eax, ebx
0x18000ed8f  mov     rbx, [rsp+70h+arg_0]
0x18000ed97  add     rsp, 70h
0x18000ed9b  pop     rdi
0x18000ed9c  pop     rsi
0x18000ed9d  pop     rbp
0x18000ed9e  retn
```
