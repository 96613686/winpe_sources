# GetFilteredShellItem(IShellItem *,IShellItem * *)

- ea: `0x18004e78c`
- end: `0x18004e896`
- name: `?GetFilteredShellItem@@YAJPEAUIShellItem@@PEAPEAU1@@Z`
- size: `266`
- prototype: `__int64 __fastcall(struct IShellItem *, struct IShellItem **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003f0d8`
- `0x180041900`

## callees

- `0x18004e78c`
- `0x18004e89c`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e7cc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e7cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e859`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e859`

## pseudocode

```c
__int64 __fastcall GetFilteredShellItem(struct IShellItem *a1, struct IShellItem **a2)
{
  HRESULT ImageFileExtensionFilterCondition; // ebx
  struct IShellItemVtbl *lpVtbl; // rax
  int v6; // eax
  struct ICondition *v7; // rdi
  LPVOID pv; // [rsp+68h] [rbp+10h] BYREF
  LPVOID v10; // [rsp+70h] [rbp+18h] BYREF
  struct ICondition *v11; // [rsp+78h] [rbp+20h] BYREF

  *a2 = 0;
  v10 = 0;
  ImageFileExtensionFilterCondition = CoCreateInstance(
                                        &GUID_36a479ef_8b67_4d01_8dda_753cfcb2dd96,
                                        0,
                                        0x15u,
                                        &GUID_a4cbb5d1_b912_4bf6_a96b_b02855169492,
                                        &v10);
  if ( ImageFileExtensionFilterCondition >= 0 )
  {
    v11 = 0;
    ImageFileExtensionFilterCondition = GetImageFileExtensionFilterCondition(&v11);
    if ( ImageFileExtensionFilterCondition >= 0 )
    {
      lpVtbl = a1->lpVtbl;
      pv = 0;
      v6 = ((__int64 (__fastcall *)(struct IShellItem *, _QWORD, LPVOID *))lpVtbl->GetDisplayName)(a1, 0, &pv);
      v7 = v11;
      ImageFileExtensionFilterCondition = v6;
      if ( v6 >= 0 )
      {
        ImageFileExtensionFilterCondition = (*(__int64 (__fastcall **)(LPVOID, struct IShellItem *, LPVOID, struct ICondition *, GUID *, struct IShellItem **))(*(_QWORD *)v10 + 24LL))(
                                              v10,
                                              a1,
                                              pv,
                                              v11,
                                              &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                              a2);
        CoTaskMemFree(pv);
      }
      ((void (__fastcall *)(struct ICondition *))v7->lpVtbl->Release)(v7);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return (unsigned int)ImageFileExtensionFilterCondition;
}

```

## disassembly

```asm
0x18004e78c  mov     r11, rsp
0x18004e78f  mov     [r11+8], rbx
0x18004e793  push    rsi
0x18004e794  push    rdi
0x18004e795  push    r14
0x18004e797  sub     rsp, 40h
0x18004e79b  mov     r14, rdx
0x18004e79e  mov     qword ptr [rdx], 0
0x18004e7a5  xor     edx, edx; pUnkOuter
0x18004e7a7  mov     qword ptr [r11+18h], 0
0x18004e7af  mov     rsi, rcx
0x18004e7b2  lea     rax, [r11+18h]
0x18004e7b6  lea     r9, _GUID_a4cbb5d1_b912_4bf6_a96b_b02855169492; riid
0x18004e7bd  mov     [r11-38h], rax
0x18004e7c1  lea     rcx, _GUID_36a479ef_8b67_4d01_8dda_753cfcb2dd96; rclsid
0x18004e7c8  lea     r8d, [rdx+15h]; dwClsContext
0x18004e7cc  call    cs:__imp_CoCreateInstance
0x18004e7d3  nop     dword ptr [rax+rax+00h]
0x18004e7d8  mov     ebx, eax
0x18004e7da  test    eax, eax
0x18004e7dc  js      loc_18004E885
0x18004e7e2  lea     rcx, [rsp+58h+arg_18]; struct ICondition **
0x18004e7e7  mov     [rsp+58h+arg_18], 0
0x18004e7f0  call    ?GetImageFileExtensionFilterCondition@@YAJPEAPEAUICondition@@@Z; GetImageFileExtensionFilterCondition(ICondition * *)
0x18004e7f5  mov     ebx, eax
0x18004e7f7  test    eax, eax
0x18004e7f9  js      short loc_18004E874
0x18004e7fb  mov     rax, [rsi]
0x18004e7fe  lea     r8, [rsp+58h+pv]
0x18004e803  xor     edx, edx
0x18004e805  mov     [rsp+58h+pv], 0
0x18004e80e  mov     rcx, rsi
0x18004e811  mov     rax, [rax+28h]
0x18004e815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e81a  mov     rdi, [rsp+58h+arg_18]
0x18004e81f  mov     ebx, eax
0x18004e821  test    eax, eax
0x18004e823  js      short loc_18004E865
0x18004e825  mov     rcx, [rsp+58h+arg_10]
0x18004e82a  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18004e831  mov     r8, [rsp+58h+pv]
0x18004e836  mov     r9, rdi
0x18004e839  mov     [rsp+58h+var_30], r14
0x18004e83e  mov     [rsp+58h+var_38], rdx
0x18004e843  mov     rdx, rsi
0x18004e846  mov     rax, [rcx]
0x18004e849  mov     rax, [rax+18h]
0x18004e84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e852  mov     rcx, [rsp+58h+pv]; pv
0x18004e857  mov     ebx, eax
0x18004e859  call    cs:__imp_CoTaskMemFree
0x18004e860  nop     dword ptr [rax+rax+00h]
0x18004e865  mov     rax, [rdi]
0x18004e868  mov     rcx, rdi
0x18004e86b  mov     rax, [rax+10h]
0x18004e86f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e874  mov     rcx, [rsp+58h+arg_10]
0x18004e879  mov     rax, [rcx]
0x18004e87c  mov     rax, [rax+10h]
0x18004e880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e885  mov     eax, ebx
0x18004e887  mov     rbx, [rsp+58h+arg_0]
0x18004e88c  add     rsp, 40h
0x18004e890  pop     r14
0x18004e892  pop     rdi
0x18004e893  pop     rsi
0x18004e894  retn
```
