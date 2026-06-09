# DllGetClassObject

- ea: `0x18000a110`
- end: `0x18000a1b5`
- name: `DllGetClassObject`
- size: `165`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003ce0`
- `0x1800083ec`
- `0x18000a110`
- `0x18000d348`
- `0x18000d43c`

## string_xrefs

- `0x18000a15f`: `DllGetClassObject`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  ATL::CComModule *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  HRESULT v9; // ebx
  int ClassObject; // [rsp+20h] [rbp-48h] BYREF
  __int16 v12; // [rsp+24h] [rbp-44h]
  __int16 v13; // [rsp+26h] [rbp-42h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_dc1e325698af3ebf27dfb8b3dda856da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&ClassObject, "DllGetClassObject", 41);
  ClassObject = ATL::CComModule::GetClassObject(v6, rclsid, riid, ppv);
  v9 = ClassObject;
  if ( ClassObject >= 0 )
    v12 = 43;
  else
    v13 = 43;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&ClassObject, v7, v8);
  return v9;
}

```

## disassembly

```asm
0x18000a110  mov     [rsp+arg_0], rbx
0x18000a115  mov     [rsp+arg_8], rsi
0x18000a11a  push    rdi
0x18000a11b  sub     rsp, 60h
0x18000a11f  mov     rbx, r8
0x18000a122  mov     rdi, rdx
0x18000a125  mov     rsi, rcx
0x18000a128  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a12f  lea     rax, WPP_GLOBAL_Control
0x18000a136  cmp     rcx, rax
0x18000a139  jz      short loc_18000A159
0x18000a13b  test    dword ptr [rcx+1Ch], 20000000h
0x18000a142  jz      short loc_18000A159
0x18000a144  mov     rcx, [rcx+10h]
0x18000a148  lea     r8, WPP_dc1e325698af3ebf27dfb8b3dda856da_Traceguids
0x18000a14f  mov     edx, 0Ah
0x18000a154  call    WPP_SF_
0x18000a159  mov     r8d, 29h ; ')'; unsigned __int16
0x18000a15f  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x18000a166  lea     rcx, [rsp+68h+var_48]; this
0x18000a16b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000a170  mov     r9, rbx; void **
0x18000a173  mov     r8, rdi; struct _GUID *
0x18000a176  mov     rdx, rsi; struct _GUID *
0x18000a179  call    ?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)
0x18000a17e  mov     [rsp+68h+var_48], eax
0x18000a182  mov     ebx, eax
0x18000a184  mov     ecx, 2Bh ; '+'
0x18000a189  test    eax, eax
0x18000a18b  jns     short loc_18000A194
0x18000a18d  mov     [rsp+68h+var_42], cx
0x18000a192  jmp     short loc_18000A199
0x18000a194  mov     [rsp+68h+var_44], cx
0x18000a199  lea     rcx, [rsp+68h+var_48]; this
0x18000a19e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000a1a3  mov     rsi, [rsp+68h+arg_8]
0x18000a1a8  mov     eax, ebx
0x18000a1aa  mov     rbx, [rsp+68h+arg_0]
0x18000a1af  add     rsp, 60h
0x18000a1b3  pop     rdi
0x18000a1b4  retn
```
