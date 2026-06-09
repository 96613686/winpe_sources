# GetFilteredShellItem(IShellItem *,IShellItem * *)

- ea: `0x1800618d0`
- end: `0x1800619cd`
- name: `?GetFilteredShellItem@@YAJPEAUIShellItem@@PEAPEAU1@@Z`
- size: `253`
- prototype: `__int64 __fastcall(struct IShellItem *, struct IShellItem **)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006ae0`
- `0x180008e20`
- `0x18004949c`
- `0x18004e3a4`

## callees

- `0x180007b20`
- `0x1800618d0`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061997`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061997`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180061910`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180061910`

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
0x1800618d0  mov     r11, rsp
0x1800618d3  mov     [r11+8], rbx
0x1800618d7  push    rsi
0x1800618d8  push    rdi
0x1800618d9  push    r14
0x1800618db  sub     rsp, 40h
0x1800618df  mov     r14, rdx
0x1800618e2  mov     qword ptr [rdx], 0
0x1800618e9  xor     edx, edx; pUnkOuter
0x1800618eb  mov     qword ptr [r11+18h], 0
0x1800618f3  mov     rsi, rcx
0x1800618f6  lea     rax, [r11+18h]
0x1800618fa  lea     r9, _GUID_a4cbb5d1_b912_4bf6_a96b_b02855169492; riid
0x180061901  mov     [r11-38h], rax
0x180061905  lea     rcx, _GUID_36a479ef_8b67_4d01_8dda_753cfcb2dd96; rclsid
0x18006190c  lea     r8d, [rdx+15h]; dwClsContext
0x180061910  call    cs:__imp_CoCreateInstance
0x180061916  mov     ebx, eax
0x180061918  test    eax, eax
0x18006191a  js      loc_1800619BD
0x180061920  lea     rcx, [rsp+58h+arg_18]; struct ICondition **
0x180061925  mov     [rsp+58h+arg_18], 0
0x18006192e  call    ?GetImageFileExtensionFilterCondition@@YAJPEAPEAUICondition@@@Z; GetImageFileExtensionFilterCondition(ICondition * *)
0x180061933  mov     ebx, eax
0x180061935  test    eax, eax
0x180061937  js      short loc_1800619AC
0x180061939  mov     rax, [rsi]
0x18006193c  lea     r8, [rsp+58h+pv]
0x180061941  xor     edx, edx
0x180061943  mov     [rsp+58h+pv], 0
0x18006194c  mov     rcx, rsi
0x18006194f  mov     rax, [rax+28h]
0x180061953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061958  mov     rdi, [rsp+58h+arg_18]
0x18006195d  mov     ebx, eax
0x18006195f  test    eax, eax
0x180061961  js      short loc_18006199D
0x180061963  mov     rcx, [rsp+58h+arg_10]
0x180061968  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18006196f  mov     r8, [rsp+58h+pv]
0x180061974  mov     r9, rdi
0x180061977  mov     [rsp+58h+var_30], r14
0x18006197c  mov     [rsp+58h+var_38], rdx
0x180061981  mov     rdx, rsi
0x180061984  mov     rax, [rcx]
0x180061987  mov     rax, [rax+18h]
0x18006198b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061990  mov     rcx, [rsp+58h+pv]; pv
0x180061995  mov     ebx, eax
0x180061997  call    cs:__imp_CoTaskMemFree
0x18006199d  mov     rax, [rdi]
0x1800619a0  mov     rcx, rdi
0x1800619a3  mov     rax, [rax+10h]
0x1800619a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800619ac  mov     rcx, [rsp+58h+arg_10]
0x1800619b1  mov     rax, [rcx]
0x1800619b4  mov     rax, [rax+10h]
0x1800619b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800619bd  mov     eax, ebx
0x1800619bf  mov     rbx, [rsp+58h+arg_0]
0x1800619c4  add     rsp, 40h
0x1800619c8  pop     r14
0x1800619ca  pop     rdi
0x1800619cb  pop     rsi
0x1800619cc  retn
```
