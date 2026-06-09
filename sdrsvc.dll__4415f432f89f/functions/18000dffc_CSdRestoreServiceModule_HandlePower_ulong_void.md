# CSdRestoreServiceModule::_HandlePower(ulong,void *)

- ea: `0x18000dffc`
- end: `0x18000e100`
- name: `?_HandlePower@CSdRestoreServiceModule@@AEAAJKPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(CSdRestoreServiceModule *__hidden this, unsigned int, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000e900`

## callees

- `0x18000dffc`
- `0x18001586c`
- `0x180015974`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e06b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e06b`

## string_xrefs

- `0x18000e017`: `CSdRestoreServiceModule::_HandlePower`

## pseudocode

```c
__int64 __fastcall CSdRestoreServiceModule::_HandlePower(CSdRestoreServiceModule *this, unsigned int a2, void *a3)
{
  int v4; // eax
  HRESULT v5; // ebx
  __int16 v6; // ax
  __int64 v7; // rax
  GUID v9; // [rsp+30h] [rbp-50h] BYREF
  HRESULT v10; // [rsp+40h] [rbp-40h] BYREF
  __int16 v11; // [rsp+44h] [rbp-3Ch]
  __int16 v12; // [rsp+46h] [rbp-3Ah]
  LPVOID ppv; // [rsp+A0h] [rbp+20h] BYREF

  ppv = a3;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "CSdRestoreServiceModule::_HandlePower", 449, 1);
  ppv = 0;
  if ( a2 <= 9 && (v4 = 593, _bittest(&v4, a2)) )
  {
    v5 = CoCreateInstance(&CLSID_CSdController, 0, 4u, &IID_ISdScheduledBackup, &ppv);
    v10 = v5;
    v6 = 470;
    if ( v5 < 0
      || (v11 = 470,
          v7 = *(_QWORD *)ppv,
          v9 = GUID_NULL,
          v5 = (*(__int64 (__fastcall **)(LPVOID, GUID *))(v7 + 80))(ppv, &v9),
          v10 = v5,
          v6 = 472,
          v5 < 0) )
    {
      v12 = v6;
    }
    else
    {
      v11 = 472;
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  else
  {
    v10 = 0;
    v11 = 476;
    v5 = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000dffc  mov     [rsp-8+arg_0], rbx
0x18000e001  mov     [rsp-8+arg_10], r8
0x18000e006  push    rbp
0x18000e007  mov     rbp, rsp
0x18000e00a  sub     rsp, 80h
0x18000e011  mov     ebx, edx
0x18000e013  lea     rcx, [rbp+var_40]; this
0x18000e017  lea     rdx, aCsdrestoreserv_2; "CSdRestoreServiceModule::_HandlePower"
0x18000e01e  mov     r9d, 1; unsigned __int16
0x18000e024  mov     r8d, 1C1h; unsigned __int16
0x18000e02a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000e02f  mov     [rbp+arg_10], 0
0x18000e037  cmp     ebx, 9
0x18000e03a  ja      loc_18000E0D2
0x18000e040  mov     eax, 251h
0x18000e045  bt      eax, ebx
0x18000e048  jnb     loc_18000E0D2
0x18000e04e  xor     edx, edx; pUnkOuter
0x18000e050  lea     rax, [rbp+arg_10]
0x18000e054  lea     r9, IID_ISdScheduledBackup; riid
0x18000e05b  mov     [rsp+80h+ppv], rax; ppv
0x18000e060  lea     rcx, CLSID_CSdController; rclsid
0x18000e067  lea     r8d, [rdx+4]; dwClsContext
0x18000e06b  call    cs:__imp_CoCreateInstance
0x18000e071  mov     ebx, eax
0x18000e073  mov     [rbp+var_40], eax
0x18000e076  test    eax, eax
0x18000e078  mov     eax, 1D6h
0x18000e07d  jns     short loc_18000E085
0x18000e07f  mov     [rbp+var_3A], ax
0x18000e083  jmp     short loc_18000E0BB
0x18000e085  mov     rcx, [rbp+arg_10]
0x18000e089  lea     rdx, [rbp+var_50]
0x18000e08d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000e094  mov     [rbp+var_3C], ax
0x18000e098  mov     rax, [rcx]
0x18000e09b  movdqu  [rbp+var_50], xmm0
0x18000e0a0  mov     rax, [rax+50h]
0x18000e0a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0a9  mov     ebx, eax
0x18000e0ab  mov     [rbp+var_40], eax
0x18000e0ae  test    eax, eax
0x18000e0b0  mov     eax, 1D8h
0x18000e0b5  js      short loc_18000E07F
0x18000e0b7  mov     [rbp+var_3C], ax
0x18000e0bb  mov     rcx, [rbp+arg_10]
0x18000e0bf  test    rcx, rcx
0x18000e0c2  jz      short loc_18000E0E4
0x18000e0c4  mov     rax, [rcx]
0x18000e0c7  mov     rax, [rax+10h]
0x18000e0cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0d0  jmp     short loc_18000E0E4
0x18000e0d2  mov     eax, 1DCh
0x18000e0d7  mov     [rbp+var_40], 0
0x18000e0de  mov     [rbp+var_3C], ax
0x18000e0e2  xor     ebx, ebx
0x18000e0e4  lea     rcx, [rbp+var_40]; this
0x18000e0e8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000e0ed  mov     eax, ebx
0x18000e0ef  mov     rbx, [rsp+80h+arg_0]
0x18000e0f7  add     rsp, 80h
0x18000e0fe  pop     rbp
0x18000e0ff  retn
```
