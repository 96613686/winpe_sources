# CWbemDispatchMgr::RaiseException(long)

- ea: `0x180024774`
- end: `0x180024850`
- name: `?RaiseException@CWbemDispatchMgr@@QEAAXJ@Z`
- size: `220`
- prototype: `void(CWbemDispatchMgr *__hidden this, int)`
- caller_count: `30`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180001370`
- `0x1800015f0`
- `0x1800023b0`
- `0x1800055c0`
- `0x180015770`
- `0x1800191d0`
- `0x180019510`
- `0x18002a840`
- `0x18002a990`
- `0x18002aa50`
- `0x18002ab30`
- `0x18002abf0`
- `0x18002af00`
- `0x18002b020`
- `0x18002b130`
- `0x18002b240`
- `0x18002b310`
- `0x18002b3a0`
- `0x18002b5b0`
- `0x18002b610`
- `0x18002b770`
- `0x18002b880`
- `0x18002bc50`
- `0x18002bd60`
- `0x18002c0c0`
- `0x18002c350`
- `0x18002c460`
- `0x18002c540`
- `0x18002c710`
- `0x18002c790`

## callees

- `0x180014984`
- `0x180024774`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800247bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800247bc`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180024822`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180024822`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18002478d`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18002478d`

## pseudocode

```c
void __fastcall CWbemDispatchMgr::RaiseException(CWbemDispatchMgr *this, int a2)
{
  OLECHAR *v3; // rbx
  ICreateErrorInfo *pperrinfo; // [rsp+30h] [rbp+8h] BYREF
  IErrorInfo *perrinfo; // [rsp+40h] [rbp+18h] BYREF

  *((_DWORD *)this + 2) = a2;
  pperrinfo = 0;
  if ( CreateErrorInfo(&pperrinfo) >= 0 )
  {
    v3 = MapHresultToWmiDescription(a2);
    ((void (__fastcall *)(ICreateErrorInfo *, OLECHAR *))pperrinfo->lpVtbl->SetDescription)(pperrinfo, v3);
    SysFreeString(v3);
    ((void (__fastcall *)(ICreateErrorInfo *, GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, &IID_ISWbemObjectEx);
    ((void (__fastcall *)(ICreateErrorInfo *, const unsigned __int16 *))pperrinfo->lpVtbl->SetSource)(
      pperrinfo,
      L"SWbemObjectEx");
    perrinfo = 0;
    if ( ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
           pperrinfo,
           &IID_IErrorInfo,
           &perrinfo) >= 0 )
    {
      SetErrorInfo(0, perrinfo);
      ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
    }
    ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  }
}

```

## disassembly

```asm
0x180024774  push    rbx
0x180024776  sub     rsp, 20h
0x18002477a  mov     [rcx+8], edx
0x18002477d  mov     ebx, edx
0x18002477f  lea     rcx, [rsp+28h+pperrinfo]; pperrinfo
0x180024784  mov     [rsp+28h+pperrinfo], 0
0x18002478d  call    cs:__imp_CreateErrorInfo
0x180024793  test    eax, eax
0x180024795  js      loc_18002484A
0x18002479b  mov     ecx, ebx; int
0x18002479d  call    ?MapHresultToWmiDescription@@YAPEAGJ@Z; MapHresultToWmiDescription(long)
0x1800247a2  mov     rcx, [rsp+28h+pperrinfo]
0x1800247a7  mov     rbx, rax
0x1800247aa  mov     rdx, [rcx]
0x1800247ad  mov     rax, [rdx+28h]
0x1800247b1  mov     rdx, rbx
0x1800247b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247b9  mov     rcx, rbx; bstrString
0x1800247bc  call    cs:__imp_SysFreeString
0x1800247c2  mov     rcx, [rsp+28h+pperrinfo]
0x1800247c7  lea     rdx, IID_ISWbemObjectEx
0x1800247ce  mov     rax, [rcx]
0x1800247d1  mov     rax, [rax+18h]
0x1800247d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247da  mov     rcx, [rsp+28h+pperrinfo]
0x1800247df  lea     rdx, aSwbemobjectex; "SWbemObjectEx"
0x1800247e6  mov     rax, [rcx]
0x1800247e9  mov     rax, [rax+20h]
0x1800247ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247f2  mov     rcx, [rsp+28h+pperrinfo]
0x1800247f7  lea     r8, [rsp+28h+perrinfo]
0x1800247fc  mov     [rsp+28h+perrinfo], 0
0x180024805  lea     rdx, IID_IErrorInfo
0x18002480c  mov     rax, [rcx]
0x18002480f  mov     rax, [rax]
0x180024812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024817  test    eax, eax
0x180024819  js      short loc_180024839
0x18002481b  mov     rdx, [rsp+28h+perrinfo]; perrinfo
0x180024820  xor     ecx, ecx; dwReserved
0x180024822  call    cs:__imp_SetErrorInfo
0x180024828  mov     rcx, [rsp+28h+perrinfo]
0x18002482d  mov     rax, [rcx]
0x180024830  mov     rax, [rax+10h]
0x180024834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024839  mov     rcx, [rsp+28h+pperrinfo]
0x18002483e  mov     rax, [rcx]
0x180024841  mov     rax, [rax+10h]
0x180024845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002484a  add     rsp, 20h
0x18002484e  pop     rbx
0x18002484f  retn
```
