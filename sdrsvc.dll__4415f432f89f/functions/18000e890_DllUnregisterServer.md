# DllUnregisterServer

- ea: `0x18000e890`
- end: `0x18000e8f5`
- name: `DllUnregisterServer`
- size: `101`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ade0`
- `0x18000d530`
- `0x18000d5b4`
- `0x18000e890`
- `0x18001586c`
- `0x180015974`

## string_xrefs

- `0x18000e89b`: `DllUnregisterServer`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  CSdRestoreServiceModule *v0; // rcx
  CSdRestoreServiceModule *v1; // rcx
  HRESULT v2; // ebx
  int v4; // [rsp+20h] [rbp-48h] BYREF
  __int16 v5; // [rsp+24h] [rbp-44h]
  __int16 v6; // [rsp+26h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v4, "DllUnregisterServer", 139, 1);
  v4 = CSdRestoreServiceModule::InitializeCOM(v0, 1);
  if ( v4 >= 0 )
  {
    v5 = 142;
    CSdRestoreServiceModule::Unregister(v1);
  }
  else
  {
    v6 = 142;
  }
  CSdRestoreServiceModule::UninitializeCOM(v1);
  v2 = v4;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v4);
  return v2;
}

```

## disassembly

```asm
0x18000e890  push    rbx
0x18000e892  sub     rsp, 60h
0x18000e896  mov     ebx, 1
0x18000e89b  lea     rdx, aDllunregisters_0; "DllUnregisterServer"
0x18000e8a2  mov     r9d, ebx; unsigned __int16
0x18000e8a5  lea     rcx, [rsp+68h+var_48]; this
0x18000e8aa  mov     r8d, 8Bh; unsigned __int16
0x18000e8b0  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000e8b5  mov     edx, ebx; int
0x18000e8b7  call    ?InitializeCOM@CSdRestoreServiceModule@@QEAAJH@Z; CSdRestoreServiceModule::InitializeCOM(int)
0x18000e8bc  mov     [rsp+68h+var_48], eax
0x18000e8c0  test    eax, eax
0x18000e8c2  mov     eax, 8Eh
0x18000e8c7  jns     short loc_18000E8D0
0x18000e8c9  mov     [rsp+68h+var_42], ax
0x18000e8ce  jmp     short loc_18000E8DA
0x18000e8d0  mov     [rsp+68h+var_44], ax
0x18000e8d5  call    ?Unregister@CSdRestoreServiceModule@@QEAAJXZ; CSdRestoreServiceModule::Unregister(void)
0x18000e8da  call    ?UninitializeCOM@CSdRestoreServiceModule@@QEAAJXZ; CSdRestoreServiceModule::UninitializeCOM(void)
0x18000e8df  mov     ebx, [rsp+68h+var_48]
0x18000e8e3  lea     rcx, [rsp+68h+var_48]; this
0x18000e8e8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000e8ed  mov     eax, ebx
0x18000e8ef  add     rsp, 60h
0x18000e8f3  pop     rbx
0x18000e8f4  retn
```
