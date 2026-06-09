# CreateScopeFromLibraryDescription(ILibraryDescription *,IShellItem *,IShellItem *,LIBRARY_SCOPE_FLAGS,SCOPE_ITEM_DEPTH,SCOPE_ITEM_FLAGS,ushort const *,IScope * *)

- ea: `0x18003b224`
- end: `0x18003b4c2`
- name: `?CreateScopeFromLibraryDescription@@YAJPEAUILibraryDescription@@PEAUIShellItem@@1W4LIBRARY_SCOPE_FLAGS@@W4SCOPE_ITEM_DEPTH@@W4SCOPE_ITEM_FLAGS@@PEBGPEAPEAUIScope@@@Z`
- size: `670`
- prototype: `int __high(struct ILibraryDescription *, struct IShellItem *, struct IShellItem *, enum LIBRARY_SCOPE_FLAGS, enum SCOPE_ITEM_DEPTH, enum SCOPE_ITEM_FLAGS, const unsigned __int16 *, struct IScope **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180040818`

## callees

- `0x18003b224`
- `0x18003bff8`
- `0x18003c130`
- `0x18003c22c`
- `0x18003c354`
- `0x18003f34c`
- `0x180057010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_Set` at `0x18003b478`
- `SHLWAPI!__imp_IUnknown_Set` at `0x18003b478`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003b279`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003b279`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003b3c2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003b3c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreateScopeFromLibraryDescription(
        __int64 a1,
        struct ILocationDescription *a2,
        struct IShellItem *a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        IUnknown *punk,
        IUnknown **ppunk)
{
  int v10; // edi
  IUnknown **v11; // r12
  HRESULT v12; // ebx
  int v13; // esi
  unsigned int v14; // r14d
  int v15; // eax
  IUnknown **v16; // rcx
  int v17; // esi
  __int64 v19; // [rsp+30h] [rbp-50h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-48h] BYREF
  PROPERTYKEY v21; // [rsp+40h] [rbp-40h] BYREF
  PROPVARIANT pvar; // [rsp+60h] [rbp-20h] BYREF
  __int16 v23; // [rsp+68h] [rbp-18h]
  struct ILocationDescription *v24; // [rsp+C8h] [rbp+48h] BYREF
  unsigned int v25; // [rsp+D8h] [rbp+58h] BYREF

  v25 = a4;
  v24 = a2;
  v10 = 0;
  v11 = ppunk;
  *ppunk = 0;
  ppv = 0;
  v12 = CoCreateInstance(
          &GUID_6746c347_576b_4f73_9012_cdfeea251bc4,
          0,
          1u,
          &GUID_54410b83_6787_4418_9735_5aaaabe83a9a,
          &ppv);
  if ( v12 >= 0 )
  {
    punk = 0;
    v12 = (*(__int64 (__fastcall **)(LPVOID, GUID *, IUnknown **))(*(_QWORD *)ppv + 24LL))(
            ppv,
            &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798,
            &punk);
    if ( v12 >= 0 )
    {
      v13 = IsSearchConnector(a3);
      a5 = v13;
      v25 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 104LL))(a1, &v25);
      v14 = 0;
      if ( v12 >= 0 )
      {
        while ( v14 < v25 )
        {
          v24 = 0;
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct ILocationDescription **))(*(_QWORD *)a1 + 112LL))(
                  a1,
                  v14,
                  &v24);
          if ( v12 >= 0 )
          {
            v19 = 0;
            v12 = (**(__int64 (__fastcall ***)(struct ILocationDescription *, GUID *, __int64 *))v24)(
                    v24,
                    &GUID_f8e6532b_c735_4517_bf1d_cbe30df8fe1c,
                    &v19);
            if ( v12 >= 0 )
            {
              ppunk = 0;
              if ( (*(int (__fastcall **)(struct ILocationDescription *, GUID *, IUnknown ***))(*(_QWORD *)v24 + 176LL))(
                     v24,
                     &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                     &ppunk) >= 0 )
              {
                LOWORD(pvar) = 0;
                v21 = PKEY_IsSearchOnlyItem;
                v15 = ((__int64 (__fastcall *)(IUnknown **, PROPERTYKEY *, PROPVARIANT *))(*ppunk)[5].lpVtbl)(
                        ppunk,
                        &v21,
                        &pvar);
                if ( v15 < 0 || (_WORD)pvar )
                {
                  v10 = 0;
                  if ( v15 >= 0 && (_WORD)pvar == 11 )
                    LOBYTE(v10) = v23 == -1;
                }
                else
                {
                  v10 = 0;
                }
                PropVariantClear(&pvar);
              }
              v16 = ppunk;
              if ( ppunk )
              {
                ppunk = 0;
                ((void (__fastcall *)(IUnknown **))(*v16)[2].lpVtbl)(v16);
              }
              if ( (unsigned int)IsProviderLocation(v24) || v13 )
                v17 = 0;
              else
                v17 = IsUnsupportedLocation(v24);
              if ( !(unsigned int)IsAccessibleLibraryLocation(v24) || v10 )
              {
                v10 = 0;
              }
              else
              {
                v10 = 0;
                if ( !v17 )
                  v12 = _AddScopeForLocation(v19, punk, a3);
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
              v13 = a5;
            }
            (*(void (__fastcall **)(struct ILocationDescription *))(*(_QWORD *)v24 + 16LL))(v24);
          }
          ++v14;
          if ( v12 < 0 )
            goto LABEL_31;
        }
        IUnknown_Set(v11, punk);
      }
LABEL_31:
      ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003b224  mov     [rsp-38h+arg_0], rbx
0x18003b229  mov     [rsp-38h+arg_18], r9d
0x18003b22e  mov     [rsp-38h+arg_8], rdx
0x18003b233  push    rbp
0x18003b234  push    rsi
0x18003b235  push    rdi
0x18003b236  push    r12
0x18003b238  push    r13
0x18003b23a  push    r14
0x18003b23c  push    r15
0x18003b23e  mov     rbp, rsp
0x18003b241  sub     rsp, 80h
0x18003b248  mov     r13, r8
0x18003b24b  mov     r15, rcx
0x18003b24e  xor     edi, edi
0x18003b250  mov     r12, [rbp+ppunk]
0x18003b254  mov     [r12], rdi
0x18003b258  mov     [rbp+var_48], rdi
0x18003b25c  lea     rax, [rbp+var_48]
0x18003b260  mov     [rsp+80h+ppv], rax; ppv
0x18003b265  lea     r9, _GUID_54410b83_6787_4418_9735_5aaaabe83a9a; riid
0x18003b26c  xor     edx, edx; pUnkOuter
0x18003b26e  lea     r8d, [rdi+1]; dwClsContext
0x18003b272  lea     rcx, _GUID_6746c347_576b_4f73_9012_cdfeea251bc4; rclsid
0x18003b279  call    cs:__imp_CoCreateInstance
0x18003b280  nop     dword ptr [rax+rax+00h]
0x18003b285  mov     ebx, eax
0x18003b287  test    eax, eax
0x18003b289  js      loc_18003B4A4
0x18003b28f  mov     [rbp+punk], rdi
0x18003b293  mov     rcx, [rbp+var_48]
0x18003b297  mov     rax, [rcx]
0x18003b29a  lea     r8, [rbp+punk]
0x18003b29e  lea     rdx, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x18003b2a5  mov     rax, [rax+18h]
0x18003b2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b2ae  mov     ebx, eax
0x18003b2b0  test    eax, eax
0x18003b2b2  js      loc_18003B494
0x18003b2b8  mov     rcx, r13; struct IShellItem *
0x18003b2bb  call    ?IsSearchConnector@@YAHPEAUIShellItem@@@Z; IsSearchConnector(IShellItem *)
0x18003b2c0  mov     esi, eax
0x18003b2c2  mov     [rbp+arg_20], eax
0x18003b2c5  mov     [rbp+arg_18], edi
0x18003b2c8  mov     rcx, [r15]
0x18003b2cb  mov     rax, [rcx+68h]
0x18003b2cf  lea     rdx, [rbp+arg_18]
0x18003b2d3  mov     rcx, r15
0x18003b2d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b2db  mov     ebx, eax
0x18003b2dd  mov     r14d, edi
0x18003b2e0  test    eax, eax
0x18003b2e2  js      loc_18003B484
0x18003b2e8  cmp     r14d, [rbp+arg_18]
0x18003b2ec  jnb     loc_18003B471
0x18003b2f2  mov     [rbp+arg_8], rdi
0x18003b2f6  mov     rax, [r15]
0x18003b2f9  lea     r8, [rbp+arg_8]
0x18003b2fd  mov     edx, r14d
0x18003b300  mov     rcx, r15
0x18003b303  mov     rax, [rax+70h]
0x18003b307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b30c  mov     ebx, eax
0x18003b30e  test    eax, eax
0x18003b310  js      loc_18003B464
0x18003b316  mov     [rbp+var_50], rdi
0x18003b31a  mov     rcx, [rbp+arg_8]
0x18003b31e  mov     rax, [rcx]
0x18003b321  lea     r8, [rbp+var_50]
0x18003b325  lea     rdx, _GUID_f8e6532b_c735_4517_bf1d_cbe30df8fe1c
0x18003b32c  mov     rax, [rax]
0x18003b32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b334  mov     ebx, eax
0x18003b336  test    eax, eax
0x18003b338  js      loc_18003B454
0x18003b33e  mov     rcx, [rbp+arg_8]
0x18003b342  mov     [rbp+ppunk], rdi
0x18003b346  mov     rax, [rcx]
0x18003b349  lea     r8, [rbp+ppunk]
0x18003b34d  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18003b354  mov     rax, [rax+0B0h]
0x18003b35b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b360  xor     edx, edx
0x18003b362  test    eax, eax
0x18003b364  js      short loc_18003B3D0
0x18003b366  movups  xmm0, xmmword ptr cs:PKEY_IsSearchOnlyItem.fmtid.Data1
0x18003b36d  mov     ecx, cs:PKEY_IsSearchOnlyItem.pid
0x18003b373  mov     word ptr [rbp+pvar], dx
0x18003b377  movaps  [rbp+var_40], xmm0
0x18003b37b  mov     [rbp+var_30], ecx
0x18003b37e  mov     rcx, [rbp+ppunk]
0x18003b382  mov     rax, [rcx]
0x18003b385  lea     r8, [rbp+pvar]
0x18003b389  lea     rdx, [rbp+var_40]
0x18003b38d  mov     rax, [rax+28h]
0x18003b391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b396  movzx   ecx, word ptr [rbp+pvar]
0x18003b39a  xor     edx, edx
0x18003b39c  test    eax, eax
0x18003b39e  js      short loc_18003B3A9
0x18003b3a0  test    cx, cx
0x18003b3a3  jnz     short loc_18003B3A9
0x18003b3a5  mov     edi, edx
0x18003b3a7  jmp     short loc_18003B3BE
0x18003b3a9  mov     edi, edx
0x18003b3ab  test    eax, eax
0x18003b3ad  js      short loc_18003B3BE
0x18003b3af  cmp     cx, 0Bh
0x18003b3b3  jnz     short loc_18003B3BE
0x18003b3b5  cmp     [rbp+var_18], 0FFFFh
0x18003b3ba  setz    dil
0x18003b3be  lea     rcx, [rbp+pvar]; pvar
0x18003b3c2  call    cs:__imp_PropVariantClear
0x18003b3c9  nop     dword ptr [rax+rax+00h]
0x18003b3ce  xor     edx, edx
0x18003b3d0  mov     rcx, [rbp+ppunk]
0x18003b3d4  test    rcx, rcx
0x18003b3d7  jz      short loc_18003B3EA
0x18003b3d9  mov     [rbp+ppunk], rdx
0x18003b3dd  mov     rax, [rcx]
0x18003b3e0  mov     rax, [rax+10h]
0x18003b3e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3e9  nop
0x18003b3ea  mov     rcx, [rbp+arg_8]; struct ILocationDescription *
0x18003b3ee  call    ?IsProviderLocation@@YAHPEAUILocationDescription@@@Z; IsProviderLocation(ILocationDescription *)
0x18003b3f3  xor     ecx, ecx
0x18003b3f5  test    eax, eax
0x18003b3f7  jnz     short loc_18003B40A
0x18003b3f9  test    esi, esi
0x18003b3fb  jnz     short loc_18003B40A
0x18003b3fd  mov     rcx, [rbp+arg_8]; struct ILocationDescription *
0x18003b401  call    ?IsUnsupportedLocation@@YAHPEAUILocationDescription@@@Z; IsUnsupportedLocation(ILocationDescription *)
0x18003b406  mov     esi, eax
0x18003b408  jmp     short loc_18003B40C
0x18003b40a  mov     esi, ecx
0x18003b40c  mov     rcx, [rbp+arg_8]; struct ILocationDescription *
0x18003b410  call    ?IsAccessibleLibraryLocation@@YAHPEAUILocationDescription@@@Z; IsAccessibleLibraryLocation(ILocationDescription *)
0x18003b415  test    eax, eax
0x18003b417  jz      short loc_18003B43F
0x18003b419  test    edi, edi
0x18003b41b  jnz     short loc_18003B43F
0x18003b41d  xor     edi, edi
0x18003b41f  test    esi, esi
0x18003b421  jnz     short loc_18003B441
0x18003b423  mov     dword ptr [rsp+80h+ppv], 50h ; 'P'
0x18003b42b  mov     r8, r13
0x18003b42e  mov     rdx, [rbp+punk]
0x18003b432  mov     rcx, [rbp+var_50]
0x18003b436  call    ?_AddScopeForLocation@@YAJPEAUILocationDescription2@@PEAUIScope@@PEAUIShellItem@@W4SCOPE_ITEM_DEPTH@@W4SCOPE_ITEM_FLAGS@@PEBG@Z; _AddScopeForLocation(ILocationDescription2 *,IScope *,IShellItem *,SCOPE_ITEM_DEPTH,SCOPE_ITEM_FLAGS,ushort const *)
0x18003b43b  mov     ebx, eax
0x18003b43d  jmp     short loc_18003B441
0x18003b43f  xor     edi, edi
0x18003b441  mov     rcx, [rbp+var_50]
0x18003b445  mov     rax, [rcx]
0x18003b448  mov     rax, [rax+10h]
0x18003b44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b451  mov     esi, [rbp+arg_20]
0x18003b454  mov     rcx, [rbp+arg_8]
0x18003b458  mov     rax, [rcx]
0x18003b45b  mov     rax, [rax+10h]
0x18003b45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b464  inc     r14d
0x18003b467  test    ebx, ebx
0x18003b469  jns     loc_18003B2E8
0x18003b46f  jmp     short loc_18003B484
0x18003b471  mov     rdx, [rbp+punk]; punk
0x18003b475  mov     rcx, r12; ppunk
0x18003b478  call    cs:__imp_IUnknown_Set
0x18003b47f  nop     dword ptr [rax+rax+00h]
0x18003b484  mov     rcx, [rbp+punk]
0x18003b488  mov     rax, [rcx]
0x18003b48b  mov     rax, [rax+10h]
0x18003b48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b494  mov     rcx, [rbp+var_48]
0x18003b498  mov     rax, [rcx]
0x18003b49b  mov     rax, [rax+10h]
0x18003b49f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b4a4  mov     eax, ebx
0x18003b4a6  mov     rbx, [rsp+80h+arg_0]
0x18003b4ae  add     rsp, 80h
0x18003b4b5  pop     r15
0x18003b4b7  pop     r14
0x18003b4b9  pop     r13
0x18003b4bb  pop     r12
0x18003b4bd  pop     rdi
0x18003b4be  pop     rsi
0x18003b4bf  pop     rbp
0x18003b4c0  retn
```
