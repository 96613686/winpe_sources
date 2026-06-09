# CSdController::QueryDeviceProperties(ushort const *,_SD_STORAGE_DEVICE_PROP *)

- ea: `0x18000f9d0`
- end: `0x18000facf`
- name: `?QueryDeviceProperties@CSdController@@EEAAJPEBGPEAU_SD_STORAGE_DEVICE_PROP@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(CSdController *__hidden this, const unsigned __int16 *, struct _SD_STORAGE_DEVICE_PROP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000f9d0`
- `0x18001586c`
- `0x180015974`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fa66`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fa66`

## pseudocode

```c
__int64 __fastcall CSdController::QueryDeviceProperties(
        CSdController *this,
        const unsigned __int16 *a2,
        struct _SD_STORAGE_DEVICE_PROP *a3)
{
  LPVOID v5; // rcx
  __int64 v6; // rdx
  struct _SD_STORAGE_DEVICE_PROP *v7; // rax
  __int16 v8; // ax
  unsigned int v9; // ebx
  HRESULT v10; // eax
  bool v11; // sf
  int v12; // eax
  int v14; // [rsp+30h] [rbp-48h] BYREF
  __int16 v15; // [rsp+34h] [rbp-44h]
  __int16 v16; // [rsp+36h] [rbp-42h]
  LPVOID ppv; // [rsp+A8h] [rbp+30h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "CSdController::QueryDeviceProperties", 0x671u, 1u);
  v5 = 0;
  ppv = 0;
  if ( a3 )
  {
    v6 = 144;
    v7 = a3;
    do
    {
      *(_BYTE *)v7 = 0;
      v7 = (struct _SD_STORAGE_DEVICE_PROP *)((char *)v7 + 1);
      --v6;
    }
    while ( v6 );
  }
  v8 = 1655;
  if ( !a2 || (v15 = 1655, v8 = 1656, !a3) )
  {
    v9 = -2147024809;
    v14 = -2147024809;
LABEL_6:
    v16 = v8;
    goto LABEL_11;
  }
  v15 = 1656;
  v14 = 0;
  v10 = CoCreateInstance(&CLSID_SdEngine2, 0, 1u, &IID_ISdCommon2, &ppv);
  v5 = ppv;
  v9 = v10;
  v14 = v10;
  v11 = v10 < 0;
  v8 = 1658;
  if ( v11 )
    goto LABEL_6;
  v15 = 1658;
  v12 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, struct _SD_STORAGE_DEVICE_PROP *))(*(_QWORD *)ppv + 104LL))(
          ppv,
          a2,
          a3);
  v5 = ppv;
  v9 = v12;
  v14 = v12;
  v11 = v12 < 0;
  v8 = 1661;
  if ( v11 )
    goto LABEL_6;
  v15 = 1661;
LABEL_11:
  if ( v5 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14);
  return v9;
}

```

## disassembly

```asm
0x18000f9d0  push    rbp
0x18000f9d2  push    rbx
0x18000f9d3  push    rsi
0x18000f9d4  push    rdi
0x18000f9d5  mov     rbp, rsp
0x18000f9d8  sub     rsp, 78h
0x18000f9dc  mov     rdi, r8
0x18000f9df  lea     rcx, [rbp+var_48]; this
0x18000f9e3  mov     rsi, rdx
0x18000f9e6  mov     r8d, 671h; unsigned __int16
0x18000f9ec  lea     rdx, aCsdcontrollerQ_0; "CSdController::QueryDeviceProperties"
0x18000f9f3  mov     r9d, 1; unsigned __int16
0x18000f9f9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000f9fe  xor     ecx, ecx
0x18000fa00  mov     [rbp+arg_8], rcx
0x18000fa04  test    rdi, rdi
0x18000fa07  jz      short loc_18000FA1C
0x18000fa09  mov     edx, 90h
0x18000fa0e  mov     rax, rdi
0x18000fa11  mov     [rax], cl
0x18000fa13  inc     rax
0x18000fa16  sub     rdx, 1
0x18000fa1a  jnz     short loc_18000FA11
0x18000fa1c  mov     eax, 677h
0x18000fa21  test    rsi, rsi
0x18000fa24  jnz     short loc_18000FA34
0x18000fa26  mov     ebx, 80070057h
0x18000fa2b  mov     [rbp+var_48], ebx
0x18000fa2e  mov     [rbp+var_42], ax
0x18000fa32  jmp     short loc_18000FAAA
0x18000fa34  mov     [rbp+var_44], ax
0x18000fa38  mov     eax, 678h
0x18000fa3d  test    rdi, rdi
0x18000fa40  jz      short loc_18000FA26
0x18000fa42  xor     edx, edx; pUnkOuter
0x18000fa44  mov     [rbp+var_44], ax
0x18000fa48  mov     [rbp+var_48], ecx
0x18000fa4b  lea     rax, [rbp+arg_8]
0x18000fa4f  lea     r9, IID_ISdCommon2; riid
0x18000fa56  mov     [rsp+78h+ppv], rax; ppv
0x18000fa5b  lea     rcx, CLSID_SdEngine2; rclsid
0x18000fa62  lea     r8d, [rdx+1]; dwClsContext
0x18000fa66  call    cs:__imp_CoCreateInstance
0x18000fa6c  mov     rcx, [rbp+arg_8]
0x18000fa70  mov     ebx, eax
0x18000fa72  mov     [rbp+var_48], eax
0x18000fa75  test    eax, eax
0x18000fa77  mov     eax, 67Ah
0x18000fa7c  js      short loc_18000FA2E
0x18000fa7e  mov     [rbp+var_44], ax
0x18000fa82  mov     r8, rdi
0x18000fa85  mov     rax, [rcx]
0x18000fa88  mov     rdx, rsi
0x18000fa8b  mov     rax, [rax+68h]
0x18000fa8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa94  mov     rcx, [rbp+arg_8]
0x18000fa98  mov     ebx, eax
0x18000fa9a  mov     [rbp+var_48], eax
0x18000fa9d  test    eax, eax
0x18000fa9f  mov     eax, 67Dh
0x18000faa4  js      short loc_18000FA2E
0x18000faa6  mov     [rbp+var_44], ax
0x18000faaa  test    rcx, rcx
0x18000faad  jz      short loc_18000FABB
0x18000faaf  mov     rdx, [rcx]
0x18000fab2  mov     rax, [rdx+10h]
0x18000fab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fabb  lea     rcx, [rbp+var_48]; this
0x18000fabf  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000fac4  mov     eax, ebx
0x18000fac6  add     rsp, 78h
0x18000faca  pop     rdi
0x18000facb  pop     rsi
0x18000facc  pop     rbx
0x18000facd  pop     rbp
0x18000face  retn
```
