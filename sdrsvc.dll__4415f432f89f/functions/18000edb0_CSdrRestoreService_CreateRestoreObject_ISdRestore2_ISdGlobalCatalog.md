# CSdrRestoreService::CreateRestoreObject(ISdRestore2 * *,ISdGlobalCatalog * *)

- ea: `0x18000edb0`
- end: `0x18000ef9f`
- name: `?CreateRestoreObject@CSdrRestoreService@@UEAAJPEAPEAUISdRestore2@@PEAPEAUISdGlobalCatalog@@@Z`
- size: `495`
- prototype: `__int64 __fastcall(CSdrRestoreService *__hidden this, struct ISdRestore2 **, struct ISdGlobalCatalog **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18000edb0`
- `0x18001586c`
- `0x180015974`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ee5b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ee5b`

## string_xrefs

- `0x18000edd1`: `CSdrRestoreService::CreateRestoreObject`

## pseudocode

```c
__int64 __fastcall CSdrRestoreService::CreateRestoreObject(
        CSdrRestoreService *this,
        struct ISdRestore2 **a2,
        struct ISdGlobalCatalog **a3)
{
  __int16 v5; // ax
  HRESULT v6; // ebx
  __int16 v7; // ax
  __int64 v9; // [rsp+30h] [rbp-40h] BYREF
  int v10; // [rsp+38h] [rbp-38h] BYREF
  __int16 v11; // [rsp+3Ch] [rbp-34h]
  __int16 v12; // [rsp+3Eh] [rbp-32h]
  struct ISdGlobalCatalog *v13; // [rsp+98h] [rbp+28h] BYREF
  struct ISdRestore2 *v14; // [rsp+A0h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+A8h] [rbp+38h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "CSdrRestoreService::CreateRestoreObject", 0x22u, 1u);
  ppv = 0;
  v9 = 0;
  v14 = 0;
  v13 = 0;
  if ( a2 )
    *a2 = 0;
  v5 = 43;
  if ( a3 && (v11 = 43, v5 = 44, *a3 = 0, a2) )
  {
    v11 = 44;
    v10 = 0;
    v6 = CoCreateInstance(&CLSID_SdEngine2, 0, 1u, &IID_ISdRestoreObjectSetup, &ppv);
    v10 = v6;
    v7 = 46;
    if ( v6 < 0 )
      goto LABEL_6;
    v11 = 46;
    v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
           ppv,
           &GUID_c7930797_7deb_45c9_aa71_ae0dc66251d6,
           &v9);
    v10 = v6;
    v7 = 48;
    if ( v6 < 0 )
      goto LABEL_6;
    v11 = 48;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, struct ISdRestore2 **))(*(_QWORD *)v9 + 24LL))(
           v9,
           11,
           &IID_ISdRestore2,
           &v14);
    v10 = v6;
    v7 = 50;
    if ( v6 < 0
      || (v11 = 50,
          v6 = (*(__int64 (__fastcall **)(LPVOID, struct ISdGlobalCatalog **))(*(_QWORD *)ppv + 24LL))(ppv, &v13),
          v10 = v6,
          v7 = 52,
          v6 < 0) )
    {
LABEL_6:
      v12 = v7;
    }
    else
    {
      v11 = 52;
      *a3 = v13;
      *a2 = v14;
      v13 = 0;
      v14 = 0;
    }
    if ( v13 )
      (*(void (__fastcall **)(struct ISdGlobalCatalog *))(*(_QWORD *)v13 + 16LL))(v13);
    if ( v14 )
      (*(void (__fastcall **)(struct ISdRestore2 *))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
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
0x18000edb0  mov     [rsp-18h+arg_0], rbx
0x18000edb5  push    rbp
0x18000edb6  push    rsi
0x18000edb7  push    rdi
0x18000edb8  mov     rbp, rsp
0x18000edbb  sub     rsp, 70h
0x18000edbf  mov     ebx, 1
0x18000edc4  lea     rcx, [rbp+var_38]; this
0x18000edc8  mov     rsi, r8
0x18000edcb  mov     rdi, rdx
0x18000edce  mov     r9d, ebx; unsigned __int16
0x18000edd1  lea     rdx, aCsdrrestoreser_0; "CSdrRestoreService::CreateRestoreObject"
0x18000edd8  lea     r8d, [rbx+21h]; unsigned __int16
0x18000eddc  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000ede1  mov     [rbp+arg_18], 0
0x18000ede9  mov     [rbp+var_40], 0
0x18000edf1  mov     [rbp+arg_10], 0
0x18000edf9  mov     [rbp+arg_8], 0
0x18000ee01  test    rdi, rdi
0x18000ee04  jz      short loc_18000EE0D
0x18000ee06  mov     qword ptr [rdi], 0
0x18000ee0d  mov     eax, 2Bh ; '+'
0x18000ee12  test    rsi, rsi
0x18000ee15  jz      loc_18000EF78
0x18000ee1b  mov     [rbp+var_34], ax
0x18000ee1f  mov     eax, 2Ch ; ','
0x18000ee24  mov     qword ptr [rsi], 0
0x18000ee2b  test    rdi, rdi
0x18000ee2e  jz      loc_18000EF78
0x18000ee34  mov     [rbp+var_34], ax
0x18000ee38  lea     r9, IID_ISdRestoreObjectSetup; riid
0x18000ee3f  lea     rax, [rbp+arg_18]
0x18000ee43  mov     [rbp+var_38], 0
0x18000ee4a  mov     r8d, ebx; dwClsContext
0x18000ee4d  mov     [rsp+70h+ppv], rax; ppv
0x18000ee52  xor     edx, edx; pUnkOuter
0x18000ee54  lea     rcx, CLSID_SdEngine2; rclsid
0x18000ee5b  call    cs:__imp_CoCreateInstance
0x18000ee61  mov     ebx, eax
0x18000ee63  mov     [rbp+var_38], eax
0x18000ee66  test    eax, eax
0x18000ee68  mov     eax, 2Eh ; '.'
0x18000ee6d  jns     short loc_18000EE78
0x18000ee6f  mov     [rbp+var_32], ax
0x18000ee73  jmp     loc_18000EF22
0x18000ee78  mov     rcx, [rbp+arg_18]
0x18000ee7c  lea     r8, [rbp+var_40]
0x18000ee80  mov     [rbp+var_34], ax
0x18000ee84  lea     rdx, _GUID_c7930797_7deb_45c9_aa71_ae0dc66251d6
0x18000ee8b  mov     rax, [rcx]
0x18000ee8e  mov     rax, [rax]
0x18000ee91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee96  mov     ebx, eax
0x18000ee98  mov     [rbp+var_38], eax
0x18000ee9b  test    eax, eax
0x18000ee9d  mov     eax, 30h ; '0'
0x18000eea2  js      short loc_18000EE6F
0x18000eea4  mov     rcx, [rbp+var_40]
0x18000eea8  lea     r9, [rbp+arg_10]
0x18000eeac  mov     [rbp+var_34], ax
0x18000eeb0  lea     r8, IID_ISdRestore2
0x18000eeb7  mov     edx, 0Bh
0x18000eebc  mov     rax, [rcx]
0x18000eebf  mov     rax, [rax+18h]
0x18000eec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eec8  mov     ebx, eax
0x18000eeca  mov     [rbp+var_38], eax
0x18000eecd  test    eax, eax
0x18000eecf  mov     eax, 32h ; '2'
0x18000eed4  js      short loc_18000EE6F
0x18000eed6  mov     rcx, [rbp+arg_18]
0x18000eeda  lea     rdx, [rbp+arg_8]
0x18000eede  mov     [rbp+var_34], ax
0x18000eee2  mov     rax, [rcx]
0x18000eee5  mov     rax, [rax+18h]
0x18000eee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eeee  mov     ebx, eax
0x18000eef0  mov     [rbp+var_38], eax
0x18000eef3  test    eax, eax
0x18000eef5  mov     eax, 34h ; '4'
0x18000eefa  js      loc_18000EE6F
0x18000ef00  mov     [rbp+var_34], ax
0x18000ef04  mov     rax, [rbp+arg_8]
0x18000ef08  mov     [rsi], rax
0x18000ef0b  mov     rax, [rbp+arg_10]
0x18000ef0f  mov     [rdi], rax
0x18000ef12  mov     [rbp+arg_8], 0
0x18000ef1a  mov     [rbp+arg_10], 0
0x18000ef22  mov     rcx, [rbp+arg_8]
0x18000ef26  test    rcx, rcx
0x18000ef29  jz      short loc_18000EF37
0x18000ef2b  mov     rax, [rcx]
0x18000ef2e  mov     rax, [rax+10h]
0x18000ef32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef37  mov     rcx, [rbp+arg_10]
0x18000ef3b  test    rcx, rcx
0x18000ef3e  jz      short loc_18000EF4C
0x18000ef40  mov     rax, [rcx]
0x18000ef43  mov     rax, [rax+10h]
0x18000ef47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef4c  mov     rcx, [rbp+var_40]
0x18000ef50  test    rcx, rcx
0x18000ef53  jz      short loc_18000EF61
0x18000ef55  mov     rax, [rcx]
0x18000ef58  mov     rax, [rax+10h]
0x18000ef5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef61  mov     rcx, [rbp+arg_18]
0x18000ef65  test    rcx, rcx
0x18000ef68  jz      short loc_18000EF84
0x18000ef6a  mov     rax, [rcx]
0x18000ef6d  mov     rax, [rax+10h]
0x18000ef71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef76  jmp     short loc_18000EF84
0x18000ef78  mov     ebx, 80070057h
0x18000ef7d  mov     [rbp+var_32], ax
0x18000ef81  mov     [rbp+var_38], ebx
0x18000ef84  lea     rcx, [rbp+var_38]; this
0x18000ef88  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000ef8d  mov     eax, ebx
0x18000ef8f  mov     rbx, [rsp+70h+arg_0]
0x18000ef97  add     rsp, 70h
0x18000ef9b  pop     rdi
0x18000ef9c  pop     rsi
0x18000ef9d  pop     rbp
0x18000ef9e  retn
```
