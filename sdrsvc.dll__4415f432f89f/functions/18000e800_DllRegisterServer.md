# DllRegisterServer

- ea: `0x18000e800`
- end: `0x18000e882`
- name: `DllRegisterServer`
- size: `130`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ade0`
- `0x18000b868`
- `0x18000d530`
- `0x18000d5b4`
- `0x18000e800`
- `0x18001586c`
- `0x180015974`

## string_xrefs

- `0x18000e80b`: `DllRegisterServer`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  CSdRestoreServiceModule *v0; // rcx
  CSdRestoreServiceModule *v1; // rcx
  __int16 v2; // ax
  HRESULT v3; // ebx
  int v5; // [rsp+20h] [rbp-48h] BYREF
  __int16 v6; // [rsp+24h] [rbp-44h]
  __int16 v7; // [rsp+26h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v5, "DllRegisterServer", 113, 1);
  v5 = CSdRestoreServiceModule::InitializeCOM(v0, 1);
  v2 = 116;
  if ( v5 >= 0
    && (v6 = 116,
        CSdRestoreServiceModule::Unregister(v1),
        v5 = CSdRestoreServiceModule::Register((CSdRestoreServiceModule *)&g_Service),
        v2 = 121,
        v5 >= 0) )
  {
    v6 = 121;
  }
  else
  {
    v7 = v2;
    CSdRestoreServiceModule::Unregister(v1);
  }
  CSdRestoreServiceModule::UninitializeCOM(v1);
  v3 = v5;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v5);
  return v3;
}

```

## disassembly

```asm
0x18000e800  push    rbx
0x18000e802  sub     rsp, 60h
0x18000e806  mov     ebx, 1
0x18000e80b  lea     rdx, aDllregisterser_0; "DllRegisterServer"
0x18000e812  mov     r9d, ebx; unsigned __int16
0x18000e815  lea     rcx, [rsp+68h+var_48]; this
0x18000e81a  lea     r8d, [rbx+70h]; unsigned __int16
0x18000e81e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000e823  mov     edx, ebx; int
0x18000e825  call    ?InitializeCOM@CSdRestoreServiceModule@@QEAAJH@Z; CSdRestoreServiceModule::InitializeCOM(int)
0x18000e82a  mov     [rsp+68h+var_48], eax
0x18000e82e  test    eax, eax
0x18000e830  lea     eax, [rbx+73h]
0x18000e833  js      short loc_18000E856
0x18000e835  mov     [rsp+68h+var_44], ax
0x18000e83a  call    ?Unregister@CSdRestoreServiceModule@@QEAAJXZ; CSdRestoreServiceModule::Unregister(void)
0x18000e83f  lea     rcx, ?g_Service@@3VCSdRestoreServiceModule@@A; this
0x18000e846  call    ?Register@CSdRestoreServiceModule@@QEAAJXZ; CSdRestoreServiceModule::Register(void)
0x18000e84b  mov     [rsp+68h+var_48], eax
0x18000e84f  test    eax, eax
0x18000e851  lea     eax, [rbx+78h]
0x18000e854  jns     short loc_18000E862
0x18000e856  mov     [rsp+68h+var_42], ax
0x18000e85b  call    ?Unregister@CSdRestoreServiceModule@@QEAAJXZ; CSdRestoreServiceModule::Unregister(void)
0x18000e860  jmp     short loc_18000E867
0x18000e862  mov     [rsp+68h+var_44], ax
0x18000e867  call    ?UninitializeCOM@CSdRestoreServiceModule@@QEAAJXZ; CSdRestoreServiceModule::UninitializeCOM(void)
0x18000e86c  mov     ebx, [rsp+68h+var_48]
0x18000e870  lea     rcx, [rsp+68h+var_48]; this
0x18000e875  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000e87a  mov     eax, ebx
0x18000e87c  add     rsp, 60h
0x18000e880  pop     rbx
0x18000e881  retn
```
