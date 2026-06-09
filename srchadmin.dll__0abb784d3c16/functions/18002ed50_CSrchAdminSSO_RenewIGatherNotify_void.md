# CSrchAdminSSO::_RenewIGatherNotify(void)

- ea: `0x18002ed50`
- end: `0x18002ee53`
- name: `?_RenewIGatherNotify@CSrchAdminSSO@@AEAAJXZ`
- size: `259`
- prototype: `__int64 __fastcall(IUnknown **this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002270`

## callees

- `0x1800206cc`
- `0x18002ed50`
- `0x180032010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_Set` at `0x18002ee1f`
- `SHLWAPI!__imp_IUnknown_Set` at `0x18002ee1f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ed83`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ed83`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ee29`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ee33`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ee29`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ee33`
- `OLEAUT32!__imp_VariantClear` at `0x18002ee0e`
- `OLEAUT32!__imp_VariantClear` at `0x18002ee0e`

## pseudocode

```c
__int64 __fastcall CSrchAdminSSO::_RenewIGatherNotify(IUnknown **this)
{
  HRESULT Instance; // ebx
  struct IUnknownVtbl *lpVtbl; // rax
  __int128 v5; // [rsp+30h] [rbp-40h] BYREF
  __int64 v6; // [rsp+40h] [rbp-30h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-20h] BYREF
  IUnknown *punk; // [rsp+98h] [rbp+28h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp+30h] BYREF
  BSTR v10; // [rsp+A8h] [rbp+38h] BYREF

  punk = 0;
  Instance = CoCreateInstance(
               &GUID_9e175b6d_f52a_11d8_b9a5_505054503030,
               0,
               0x15u,
               &GUID_b05651f9_9b10_425e_b616_1fcd828db3b1,
               (LPVOID *)&punk);
  if ( Instance >= 0 )
  {
    v10 = 0;
    Instance = SHSysAllocString(L"Windows", &v10);
    if ( Instance >= 0 )
    {
      bstrString = 0;
      Instance = SHSysAllocString(L"SystemIndex", &bstrString);
      if ( Instance >= 0 )
      {
        v6 = 0;
        memset(&pvarg, 0, sizeof(pvarg));
        lpVtbl = punk->lpVtbl;
        v5 = 0;
        Instance = ((__int64 (__fastcall *)(IUnknown *, BSTR, BSTR, __int128 *))lpVtbl[2].AddRef)(
                     punk,
                     v10,
                     bstrString,
                     &v5);
        if ( Instance >= 0 )
        {
          VariantClear(&pvarg);
          IUnknown_Set(this + 40, punk);
        }
        SysFreeString(bstrString);
      }
      SysFreeString(v10);
    }
    ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002ed50  push    rbp
0x18002ed52  push    rbx
0x18002ed53  push    rdi
0x18002ed54  mov     rbp, rsp
0x18002ed57  sub     rsp, 70h
0x18002ed5b  xor     edx, edx; pUnkOuter
0x18002ed5d  mov     [rbp+punk], 0
0x18002ed65  mov     rdi, rcx
0x18002ed68  lea     rax, [rbp+punk]
0x18002ed6c  lea     r9, _GUID_b05651f9_9b10_425e_b616_1fcd828db3b1; riid
0x18002ed73  mov     [rsp+70h+ppv], rax; ppv
0x18002ed78  lea     rcx, _GUID_9e175b6d_f52a_11d8_b9a5_505054503030; rclsid
0x18002ed7f  lea     r8d, [rdx+15h]; dwClsContext
0x18002ed83  call    cs:__imp_CoCreateInstance
0x18002ed89  mov     ebx, eax
0x18002ed8b  test    eax, eax
0x18002ed8d  js      loc_18002EE49
0x18002ed93  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x18002ed97  mov     [rbp+arg_18], 0
0x18002ed9f  lea     rcx, aWindows; "Windows"
0x18002eda6  call    ?SHSysAllocString@@YAJPEBGPEAPEAG@Z; SHSysAllocString(ushort const *,ushort * *)
0x18002edab  mov     ebx, eax
0x18002edad  test    eax, eax
0x18002edaf  js      loc_18002EE39
0x18002edb5  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x18002edb9  mov     [rbp+bstrString], 0
0x18002edc1  lea     rcx, aSystemindex; "SystemIndex"
0x18002edc8  call    ?SHSysAllocString@@YAJPEBGPEAPEAG@Z; SHSysAllocString(ushort const *,ushort * *)
0x18002edcd  mov     ebx, eax
0x18002edcf  test    eax, eax
0x18002edd1  js      short loc_18002EE2F
0x18002edd3  mov     rcx, [rbp+punk]
0x18002edd7  lea     r9, [rbp+var_40]
0x18002eddb  mov     r8, [rbp+bstrString]
0x18002eddf  xor     eax, eax
0x18002ede1  mov     rdx, [rbp+arg_18]
0x18002ede5  xorps   xmm0, xmm0
0x18002ede8  mov     qword ptr [rbp+pvarg+10h], rax
0x18002edec  mov     [rbp+var_30], rax
0x18002edf0  movups  xmmword ptr [rbp+pvarg], xmm0
0x18002edf4  mov     rax, [rcx]
0x18002edf7  movaps  [rbp+var_40], xmm0
0x18002edfb  mov     rax, [rax+38h]
0x18002edff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee04  mov     ebx, eax
0x18002ee06  test    eax, eax
0x18002ee08  js      short loc_18002EE25
0x18002ee0a  lea     rcx, [rbp+pvarg]; pvarg
0x18002ee0e  call    cs:__imp_VariantClear
0x18002ee14  mov     rdx, [rbp+punk]; punk
0x18002ee18  lea     rcx, [rdi+140h]; ppunk
0x18002ee1f  call    cs:__imp_IUnknown_Set
0x18002ee25  mov     rcx, [rbp+bstrString]; bstrString
0x18002ee29  call    cs:__imp_SysFreeString
0x18002ee2f  mov     rcx, [rbp+arg_18]; bstrString
0x18002ee33  call    cs:__imp_SysFreeString
0x18002ee39  mov     rcx, [rbp+punk]
0x18002ee3d  mov     rax, [rcx]
0x18002ee40  mov     rax, [rax+10h]
0x18002ee44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee49  mov     eax, ebx
0x18002ee4b  add     rsp, 70h
0x18002ee4f  pop     rdi
0x18002ee50  pop     rbx
0x18002ee51  pop     rbp
0x18002ee52  retn
```
