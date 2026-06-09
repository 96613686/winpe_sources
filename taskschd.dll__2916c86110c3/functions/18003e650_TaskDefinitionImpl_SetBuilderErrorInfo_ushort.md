# TaskDefinitionImpl::SetBuilderErrorInfo(ushort *)

- ea: `0x18003e650`
- end: `0x18003e70b`
- name: `?SetBuilderErrorInfo@TaskDefinitionImpl@@EEAAJPEAG@Z`
- size: `187`
- prototype: `__int64 __fastcall(TaskDefinitionImpl *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800017f0`
- `0x18003e650`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x18003e6e4`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18003e6e4`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18003e67d`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18003e67d`

## pseudocode

```c
__int64 __fastcall TaskDefinitionImpl::SetBuilderErrorInfo(TaskDefinitionImpl *this, unsigned __int16 *a2)
{
  HRESULT v3; // ebx
  ICreateErrorInfo *pperrinfo; // [rsp+38h] [rbp+10h] BYREF
  IErrorInfo *perrinfo; // [rsp+40h] [rbp+18h] BYREF

  pperrinfo = 0;
  perrinfo = 0;
  if ( a2 )
  {
    v3 = CreateErrorInfo(&pperrinfo);
    if ( v3 >= 0 )
    {
      v3 = ((__int64 (__fastcall *)(ICreateErrorInfo *, unsigned __int16 *))pperrinfo->lpVtbl->SetDescription)(
             pperrinfo,
             a2);
      if ( v3 >= 0 )
      {
        ((void (__fastcall *)(ICreateErrorInfo *, GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, &IID_ITaskDefinition);
        v3 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
               pperrinfo,
               &IID_IErrorInfo,
               &perrinfo);
        if ( v3 >= 0 )
          SetErrorInfo(0, perrinfo);
      }
    }
  }
  else
  {
    v3 = 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&perrinfo);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pperrinfo);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003e650  mov     [rsp+arg_0], rbx
0x18003e655  push    rdi
0x18003e656  sub     rsp, 20h
0x18003e65a  mov     [rsp+28h+pperrinfo], 0
0x18003e663  mov     rdi, rdx
0x18003e666  mov     [rsp+28h+perrinfo], 0
0x18003e66f  test    rdx, rdx
0x18003e672  jnz     short loc_18003E678
0x18003e674  xor     ebx, ebx
0x18003e676  jmp     short loc_18003E6EA
0x18003e678  lea     rcx, [rsp+28h+pperrinfo]; pperrinfo
0x18003e67d  call    cs:__imp_CreateErrorInfo
0x18003e683  mov     ebx, eax
0x18003e685  test    eax, eax
0x18003e687  js      short loc_18003E6EA
0x18003e689  mov     rcx, [rsp+28h+pperrinfo]
0x18003e68e  mov     rdx, rdi
0x18003e691  mov     rax, [rcx]
0x18003e694  mov     rax, [rax+28h]
0x18003e698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e69d  mov     ebx, eax
0x18003e69f  test    eax, eax
0x18003e6a1  js      short loc_18003E6EA
0x18003e6a3  mov     rcx, [rsp+28h+pperrinfo]
0x18003e6a8  lea     rdx, IID_ITaskDefinition
0x18003e6af  mov     rax, [rcx]
0x18003e6b2  mov     rax, [rax+18h]
0x18003e6b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6bb  mov     rcx, [rsp+28h+pperrinfo]
0x18003e6c0  lea     r8, [rsp+28h+perrinfo]
0x18003e6c5  lea     rdx, IID_IErrorInfo
0x18003e6cc  mov     rax, [rcx]
0x18003e6cf  mov     rax, [rax]
0x18003e6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6d7  mov     ebx, eax
0x18003e6d9  test    eax, eax
0x18003e6db  js      short loc_18003E6EA
0x18003e6dd  mov     rdx, [rsp+28h+perrinfo]; perrinfo
0x18003e6e2  xor     ecx, ecx; dwReserved
0x18003e6e4  call    cs:__imp_SetErrorInfo
0x18003e6ea  lea     rcx, [rsp+28h+perrinfo]
0x18003e6ef  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003e6f4  lea     rcx, [rsp+28h+pperrinfo]
0x18003e6f9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003e6fe  mov     eax, ebx
0x18003e700  mov     rbx, [rsp+28h+arg_0]
0x18003e705  add     rsp, 20h
0x18003e709  pop     rdi
0x18003e70a  retn
```
