# CDispatchHelp::RaiseException(long)

- ea: `0x1800050dc`
- end: `0x1800051be`
- name: `?RaiseException@CDispatchHelp@@QEAAXJ@Z`
- size: `226`
- prototype: `void(CDispatchHelp *__hidden this, int)`
- caller_count: `175`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180001070`
- `0x1800012b0`
- `0x180001e14`
- `0x180001f70`
- `0x180002610`
- `0x1800031b0`
- `0x180003420`
- `0x180003cb0`
- `0x180004dc0`
- `0x180004e10`
- `0x180004f90`
- `0x1800051d0`
- `0x1800052d0`
- `0x180005f20`
- `0x180006580`
- `0x180006850`
- `0x180008230`
- `0x180008800`
- `0x18000c960`
- `0x18000d3f0`
- `0x180012a30`
- `0x180012c90`
- `0x1800130d0`
- `0x180013310`
- `0x1800134d0`
- `0x180013aa0`
- `0x180014b20`
- `0x180014fe0`
- `0x180015260`
- `0x180015a20`
- `0x180016800`
- `0x1800168a0`
- `0x180016970`
- `0x180016de0`
- `0x180016ea4`
- `0x180017380`
- `0x180017700`
- `0x1800178e0`
- `0x180017c20`
- `0x180017d20`
- `0x180017e60`
- `0x180018ac0`
- `0x180018bf0`
- `0x180018ee0`
- `0x1800192e0`
- `0x180019410`
- `0x18001a020`
- `0x18001a1e0`
- `0x18001a280`
- `0x18001c120`

## callees

- `0x1800050dc`
- `0x180014984`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000512b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000512b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000518b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000518b`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800050fc`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800050fc`

## pseudocode

```c
void __fastcall CDispatchHelp::RaiseException(CDispatchHelp *this, int a2)
{
  OLECHAR *v4; // rbx
  ICreateErrorInfo *pperrinfo; // [rsp+30h] [rbp+8h] BYREF
  IErrorInfo *perrinfo; // [rsp+40h] [rbp+18h] BYREF

  *((_DWORD *)this + 4) = a2;
  pperrinfo = 0;
  if ( CreateErrorInfo(&pperrinfo) >= 0 )
  {
    v4 = MapHresultToWmiDescription(a2);
    ((void (__fastcall *)(ICreateErrorInfo *, OLECHAR *))pperrinfo->lpVtbl->SetDescription)(pperrinfo, v4);
    SysFreeString(v4);
    ((void (__fastcall *)(ICreateErrorInfo *, char *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, (char *)this + 64);
    ((void (__fastcall *)(ICreateErrorInfo *, _QWORD))pperrinfo->lpVtbl->SetSource)(pperrinfo, *((_QWORD *)this + 1));
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
0x1800050dc  mov     [rsp+arg_8], rbx
0x1800050e1  push    rdi
0x1800050e2  sub     rsp, 20h
0x1800050e6  mov     rdi, rcx
0x1800050e9  mov     [rcx+10h], edx
0x1800050ec  lea     rcx, [rsp+28h+pperrinfo]; pperrinfo
0x1800050f1  mov     [rsp+28h+pperrinfo], 0
0x1800050fa  mov     ebx, edx
0x1800050fc  call    cs:__imp_CreateErrorInfo
0x180005102  test    eax, eax
0x180005104  js      loc_1800051B3
0x18000510a  mov     ecx, ebx; int
0x18000510c  call    ?MapHresultToWmiDescription@@YAPEAGJ@Z; MapHresultToWmiDescription(long)
0x180005111  mov     rcx, [rsp+28h+pperrinfo]
0x180005116  mov     rbx, rax
0x180005119  mov     rdx, [rcx]
0x18000511c  mov     rax, [rdx+28h]
0x180005120  mov     rdx, rbx
0x180005123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005128  mov     rcx, rbx; bstrString
0x18000512b  call    cs:__imp_SysFreeString
0x180005131  mov     rcx, [rsp+28h+pperrinfo]
0x180005136  lea     rdx, [rdi+40h]
0x18000513a  mov     rax, [rcx]
0x18000513d  mov     rax, [rax+18h]
0x180005141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005146  mov     rcx, [rsp+28h+pperrinfo]
0x18000514b  mov     rdx, [rdi+8]
0x18000514f  mov     rax, [rcx]
0x180005152  mov     rax, [rax+20h]
0x180005156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000515b  mov     rcx, [rsp+28h+pperrinfo]
0x180005160  lea     r8, [rsp+28h+perrinfo]
0x180005165  mov     [rsp+28h+perrinfo], 0
0x18000516e  lea     rdx, IID_IErrorInfo
0x180005175  mov     rax, [rcx]
0x180005178  mov     rax, [rax]
0x18000517b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005180  test    eax, eax
0x180005182  js      short loc_1800051A2
0x180005184  mov     rdx, [rsp+28h+perrinfo]; perrinfo
0x180005189  xor     ecx, ecx; dwReserved
0x18000518b  call    cs:__imp_SetErrorInfo
0x180005191  mov     rcx, [rsp+28h+perrinfo]
0x180005196  mov     rax, [rcx]
0x180005199  mov     rax, [rax+10h]
0x18000519d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051a2  mov     rcx, [rsp+28h+pperrinfo]
0x1800051a7  mov     rax, [rcx]
0x1800051aa  mov     rax, [rax+10h]
0x1800051ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051b3  mov     rbx, [rsp+28h+arg_8]
0x1800051b8  add     rsp, 20h
0x1800051bc  pop     rdi
0x1800051bd  retn
```
