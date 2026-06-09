# CSupportErrorInfo::SetErrorInfo(ushort const *,_GUID const &,bool)

- ea: `0x18001e9c4`
- end: `0x18001ea86`
- name: `?SetErrorInfo@CSupportErrorInfo@@IEAAJPEBGAEBU_GUID@@_N@Z`
- size: `194`
- prototype: `__int64 __fastcall(CSupportErrorInfo *__hidden this, const unsigned __int16 *, const struct _GUID *, bool)`
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001a70`
- `0x18001e560`
- `0x18001f070`
- `0x18002e06d`
- `0x18002e0b7`
- `0x18002feff`
- `0x18002ff2e`
- `0x180030046`
- `0x18003008d`

## callees

- `0x180001a34`
- `0x18001e9c4`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x18001ea5a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001ea5a`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18001e9ee`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18001e9ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSupportErrorInfo::SetErrorInfo(
        CSupportErrorInfo *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3)
{
  HRESULT v5; // ebx
  IErrorInfo *perrinfo[3]; // [rsp+20h] [rbp-18h] BYREF
  ICreateErrorInfo *pperrinfo; // [rsp+60h] [rbp+28h] BYREF

  perrinfo[1] = (IErrorInfo *)-2LL;
  pperrinfo = 0;
  v5 = CreateErrorInfo(&pperrinfo);
  if ( v5 >= 0 )
  {
    v5 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const struct _GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, a3);
    if ( v5 >= 0 )
    {
      v5 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const unsigned __int16 *))pperrinfo->lpVtbl->SetDescription)(
             pperrinfo,
             a2);
      if ( v5 >= 0 )
      {
        perrinfo[0] = 0;
        v5 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
               pperrinfo,
               &GUID_1cf2b120_547d_101b_8e65_08002b2bd119,
               perrinfo);
        if ( v5 >= 0 )
        {
          v5 = SetErrorInfo(0, perrinfo[0]);
          if ( v5 >= 0 )
            v5 = 0;
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)perrinfo);
      }
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&pperrinfo);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001e9c4  mov     [rsp-20h+pperrinfo], rcx
0x18001e9c9  push    rbp
0x18001e9ca  push    rbx
0x18001e9cb  push    rsi
0x18001e9cc  push    rdi
0x18001e9cd  mov     rbp, rsp
0x18001e9d0  sub     rsp, 38h
0x18001e9d4  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x18001e9dc  mov     rdi, r8
0x18001e9df  mov     rsi, rdx
0x18001e9e2  mov     [rbp+pperrinfo], 0
0x18001e9ea  lea     rcx, [rbp+pperrinfo]; pperrinfo
0x18001e9ee  call    cs:__imp_CreateErrorInfo
0x18001e9f4  mov     ebx, eax
0x18001e9f6  test    eax, eax
0x18001e9f8  js      short loc_18001EA72
0x18001e9fa  mov     rcx, [rbp+pperrinfo]
0x18001e9fe  mov     rax, [rcx]
0x18001ea01  mov     rdx, rdi
0x18001ea04  mov     rax, [rax+18h]
0x18001ea08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea0d  mov     ebx, eax
0x18001ea0f  test    eax, eax
0x18001ea11  js      short loc_18001EA72
0x18001ea13  mov     rcx, [rbp+pperrinfo]
0x18001ea17  mov     rax, [rcx]
0x18001ea1a  mov     rdx, rsi
0x18001ea1d  mov     rax, [rax+28h]
0x18001ea21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea26  mov     ebx, eax
0x18001ea28  test    eax, eax
0x18001ea2a  js      short loc_18001EA72
0x18001ea2c  mov     [rbp+perrinfo], 0
0x18001ea34  mov     rcx, [rbp+pperrinfo]
0x18001ea38  mov     rax, [rcx]
0x18001ea3b  lea     r8, [rbp+perrinfo]
0x18001ea3f  lea     rdx, _GUID_1cf2b120_547d_101b_8e65_08002b2bd119
0x18001ea46  mov     rax, [rax]
0x18001ea49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea4e  mov     ebx, eax
0x18001ea50  test    eax, eax
0x18001ea52  js      short loc_18001EA68
0x18001ea54  mov     rdx, [rbp+perrinfo]; perrinfo
0x18001ea58  xor     ecx, ecx; dwReserved
0x18001ea5a  call    cs:__imp_SetErrorInfo
0x18001ea60  mov     ebx, eax
0x18001ea62  test    eax, eax
0x18001ea64  js      short loc_18001EA68
0x18001ea66  xor     ebx, ebx
0x18001ea68  lea     rcx, [rbp+perrinfo]
0x18001ea6c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ea71  nop
0x18001ea72  lea     rcx, [rbp+pperrinfo]
0x18001ea76  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ea7b  mov     eax, ebx
0x18001ea7d  add     rsp, 38h
0x18001ea81  pop     rdi
0x18001ea82  pop     rsi
0x18001ea83  pop     rbx
0x18001ea84  pop     rbp
0x18001ea85  retn
```
