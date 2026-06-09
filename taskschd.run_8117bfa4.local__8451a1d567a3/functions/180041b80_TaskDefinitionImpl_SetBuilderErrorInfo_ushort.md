# TaskDefinitionImpl::SetBuilderErrorInfo(ushort *)

- ea: `0x180041b80`
- end: `0x180041c48`
- name: `?SetBuilderErrorInfo@TaskDefinitionImpl@@EEAAJPEAG@Z`
- size: `200`
- prototype: `__int64 __fastcall(TaskDefinitionImpl *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001880`
- `0x180041b80`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x180041c1a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180041c1a`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180041bad`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180041bad`

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
0x180041b80  mov     [rsp+arg_0], rbx
0x180041b85  push    rdi
0x180041b86  sub     rsp, 20h
0x180041b8a  mov     [rsp+28h+pperrinfo], 0
0x180041b93  mov     rdi, rdx
0x180041b96  mov     [rsp+28h+perrinfo], 0
0x180041b9f  test    rdx, rdx
0x180041ba2  jnz     short loc_180041BA8
0x180041ba4  xor     ebx, ebx
0x180041ba6  jmp     short loc_180041C26
0x180041ba8  lea     rcx, [rsp+28h+pperrinfo]; pperrinfo
0x180041bad  call    cs:__imp_CreateErrorInfo
0x180041bb4  nop     dword ptr [rax+rax+00h]
0x180041bb9  mov     ebx, eax
0x180041bbb  test    eax, eax
0x180041bbd  js      short loc_180041C26
0x180041bbf  mov     rcx, [rsp+28h+pperrinfo]
0x180041bc4  mov     rdx, rdi
0x180041bc7  mov     rax, [rcx]
0x180041bca  mov     rax, [rax+28h]
0x180041bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041bd3  mov     ebx, eax
0x180041bd5  test    eax, eax
0x180041bd7  js      short loc_180041C26
0x180041bd9  mov     rcx, [rsp+28h+pperrinfo]
0x180041bde  lea     rdx, IID_ITaskDefinition
0x180041be5  mov     rax, [rcx]
0x180041be8  mov     rax, [rax+18h]
0x180041bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041bf1  mov     rcx, [rsp+28h+pperrinfo]
0x180041bf6  lea     r8, [rsp+28h+perrinfo]
0x180041bfb  lea     rdx, IID_IErrorInfo
0x180041c02  mov     rax, [rcx]
0x180041c05  mov     rax, [rax]
0x180041c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c0d  mov     ebx, eax
0x180041c0f  test    eax, eax
0x180041c11  js      short loc_180041C26
0x180041c13  mov     rdx, [rsp+28h+perrinfo]; perrinfo
0x180041c18  xor     ecx, ecx; dwReserved
0x180041c1a  call    cs:__imp_SetErrorInfo
0x180041c21  nop     dword ptr [rax+rax+00h]
0x180041c26  lea     rcx, [rsp+28h+perrinfo]
0x180041c2b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180041c30  lea     rcx, [rsp+28h+pperrinfo]
0x180041c35  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180041c3a  mov     eax, ebx
0x180041c3c  mov     rbx, [rsp+28h+arg_0]
0x180041c41  add     rsp, 20h
0x180041c45  pop     rdi
0x180041c46  retn
```
