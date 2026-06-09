# WusaIsUUPProductNameMatch(IUpdate *,ushort const *)

- ea: `0x14000e78c`
- end: `0x14000e9a4`
- name: `?WusaIsUUPProductNameMatch@@YA_NPEAUIUpdate@@PEBG@Z`
- size: `536`
- prototype: `bool __fastcall(struct IUpdate *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000e78c`
- `0x14000f294`

## callees

- `0x14000e78c`
- `0x140013490`
- `0x140015010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14000e872`
- `msvcrt!_wcsicmp` at `0x14000e872`
- `OLEAUT32!__imp_VariantInit` at `0x14000e7ad`
- `OLEAUT32!__imp_VariantInit` at `0x14000e7e8`
- `OLEAUT32!__imp_VariantInit` at `0x14000e7ad`
- `OLEAUT32!__imp_VariantInit` at `0x14000e7e8`
- `OLEAUT32!__imp_VariantClear` at `0x14000e97e`
- `OLEAUT32!__imp_VariantClear` at `0x14000e97e`

## string_xrefs

- `0x14000e89a`: `Failed to get update property BundledUpdates`
- `0x14000e7c7`: `update cannot be null`
- `0x14000e82b`: `Failed to get IUpdateInternalProperty interface`
- `0x14000e8c3`: `Failed to get update count`
- `0x14000e938`: `Failed to get update item`
- `0x14000e86b`: `UUP.Update`
- `0x14000e906`: `UUP.Update`

## pseudocode

```c
char __fastcall WusaIsUUPProductNameMatch(struct IUpdate *a1, const unsigned __int16 *a2)
{
  char v3; // bl
  __int64 v4; // rcx
  struct IUpdateVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IUpdate *, const IID *const, void **); // rsi
  unsigned int v7; // edi
  bool IsUUPProductNameMatch; // al
  struct IUpdate *v9; // rcx
  VARIANTARG pvarg; // [rsp+20h] [rbp-28h] BYREF
  struct IUpdate *v12; // [rsp+70h] [rbp+28h] BYREF
  const unsigned __int16 *v13; // [rsp+78h] [rbp+30h] BYREF
  __int64 v14; // [rsp+80h] [rbp+38h] BYREF
  __int64 v15; // [rsp+88h] [rbp+40h] BYREF

  v13 = a2;
  v14 = 0;
  v3 = 0;
  VariantInit(&pvarg);
  v15 = 0;
  LODWORD(v13) = 0;
  if ( a1 )
  {
    VariantInit(&pvarg);
    v4 = v14;
    lpVtbl = a1->lpVtbl;
    v14 = 0;
    QueryInterface = lpVtbl->QueryInterface;
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    if ( ((int (__fastcall *)(struct IUpdate *, GUID *, __int64 *))QueryInterface)(
           a1,
           &GUID_f7a9d4c1_ea19_4c5a_bf5d_c4173d2734c2,
           &v14) >= 0 )
    {
      if ( (*(int (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v14 + 24LL))(v14, 1114127, &pvarg) >= 0 )
      {
        if ( _wcsicmp(pvarg.bstrVal, L"UUP.Update") )
        {
          if ( ((int (__fastcall *)(struct IUpdate *, __int64 *))a1->lpVtbl->get_BundledUpdates)(a1, &v15) >= 0 )
          {
            if ( (*(int (__fastcall **)(__int64, const unsigned __int16 **))(*(_QWORD *)v15 + 80LL))(v15, &v13) >= 0 )
            {
              if ( (int)v13 > 0 )
              {
                v7 = 0;
                while ( 1 )
                {
                  v12 = 0;
                  if ( (*(int (__fastcall **)(__int64, _QWORD, struct IUpdate **))(*(_QWORD *)v15 + 56LL))(
                         v15,
                         v7,
                         &v12) < 0 )
                    break;
                  IsUUPProductNameMatch = WusaIsUUPProductNameMatch(v12, L"UUP.Update");
                  v9 = v12;
                  if ( IsUUPProductNameMatch )
                  {
                    v3 = 1;
                    goto LABEL_26;
                  }
                  if ( v12 )
                    ((void (*)(void))v12->lpVtbl->Release)();
                  if ( (int)++v7 >= (int)v13 )
                    goto LABEL_28;
                }
                WusaLogDebugEventA(L"WusaIsUUPProductNameMatch", 1010, "Failed to get update item");
                v9 = v12;
LABEL_26:
                if ( v9 )
                  ((void (__fastcall *)(struct IUpdate *))v9->lpVtbl->Release)(v9);
              }
            }
            else
            {
              WusaLogDebugEventA(L"WusaIsUUPProductNameMatch", 1002, "Failed to get update count");
            }
          }
          else
          {
            WusaLogDebugEventA(L"WusaIsUUPProductNameMatch", 999, "Failed to get update property BundledUpdates");
          }
        }
        else
        {
          v3 = 1;
        }
      }
      else
      {
        WusaLogDebugEventA(L"WusaIsUUPProductNameMatch", 989, "Failed to get product name");
      }
    }
    else
    {
      WusaLogDebugEventA(L"WusaIsUUPProductNameMatch", 986, "Failed to get IUpdateInternalProperty interface");
    }
  }
  else
  {
    WusaLogDebugEventA(L"WusaIsUUPProductNameMatch", 979, "update cannot be null");
  }
LABEL_28:
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  VariantClear(&pvarg);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return v3;
}

```

## disassembly

```asm
0x14000e78c  mov     [rsp-20h+arg_8], rdx
0x14000e791  push    rbp
0x14000e792  push    rbx
0x14000e793  push    rsi
0x14000e794  push    rdi
0x14000e795  mov     rbp, rsp
0x14000e798  sub     rsp, 48h
0x14000e79c  mov     rdi, rcx
0x14000e79f  mov     [rbp+arg_10], 0
0x14000e7a7  lea     rcx, [rbp+pvarg]; pvarg
0x14000e7ab  xor     bl, bl
0x14000e7ad  call    cs:__imp_VariantInit
0x14000e7b3  mov     [rbp+arg_18], 0
0x14000e7bb  mov     dword ptr [rbp+arg_8], 0
0x14000e7c2  test    rdi, rdi
0x14000e7c5  jnz     short loc_14000E7E4
0x14000e7c7  lea     r8, aUpdateCannotBe; "update cannot be null"
0x14000e7ce  mov     edx, 3D3h
0x14000e7d3  lea     rcx, aWusaisuupprodu; "WusaIsUUPProductNameMatch"
0x14000e7da  call    WusaLogDebugEventA
0x14000e7df  jmp     loc_14000E965
0x14000e7e4  lea     rcx, [rbp+pvarg]; pvarg
0x14000e7e8  call    cs:__imp_VariantInit
0x14000e7ee  mov     rcx, [rbp+arg_10]
0x14000e7f2  mov     rax, [rdi]
0x14000e7f5  mov     [rbp+arg_10], 0
0x14000e7fd  mov     rsi, [rax]
0x14000e800  test    rcx, rcx
0x14000e803  jz      short loc_14000E811
0x14000e805  mov     rax, [rcx]
0x14000e808  mov     rax, [rax+10h]
0x14000e80c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e811  lea     r8, [rbp+arg_10]
0x14000e815  mov     rcx, rdi
0x14000e818  lea     rdx, _GUID_f7a9d4c1_ea19_4c5a_bf5d_c4173d2734c2
0x14000e81f  mov     rax, rsi
0x14000e822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e827  test    eax, eax
0x14000e829  jns     short loc_14000E839
0x14000e82b  lea     r8, aFailedToGetIup_1; "Failed to get IUpdateInternalProperty i"...
0x14000e832  mov     edx, 3DAh
0x14000e837  jmp     short loc_14000E7D3
0x14000e839  mov     rcx, [rbp+arg_10]
0x14000e83d  lea     r8, [rbp+pvarg]
0x14000e841  mov     edx, 11000Fh
0x14000e846  mov     rax, [rcx]
0x14000e849  mov     rax, [rax+18h]
0x14000e84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e852  test    eax, eax
0x14000e854  jns     short loc_14000E867
0x14000e856  lea     r8, aFailedToGetPro_1; "Failed to get product name"
0x14000e85d  mov     edx, 3DDh
0x14000e862  jmp     loc_14000E7D3
0x14000e867  mov     rcx, qword ptr [rbp+pvarg+8]; String1
0x14000e86b  lea     rdx, aUupUpdate; "UUP.Update"
0x14000e872  call    cs:__imp__wcsicmp
0x14000e878  test    eax, eax
0x14000e87a  jnz     short loc_14000E883
0x14000e87c  mov     bl, 1
0x14000e87e  jmp     loc_14000E965
0x14000e883  mov     rax, [rdi]
0x14000e886  lea     rdx, [rbp+arg_18]
0x14000e88a  mov     rcx, rdi
0x14000e88d  mov     rax, [rax+48h]
0x14000e891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e896  test    eax, eax
0x14000e898  jns     short loc_14000E8AB
0x14000e89a  lea     r8, aFailedToGetUpd_4; "Failed to get update property BundledUp"...
0x14000e8a1  mov     edx, 3E7h
0x14000e8a6  jmp     loc_14000E7D3
0x14000e8ab  mov     rcx, [rbp+arg_18]
0x14000e8af  lea     rdx, [rbp+arg_8]
0x14000e8b3  mov     rax, [rcx]
0x14000e8b6  mov     rax, [rax+50h]
0x14000e8ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e8bf  test    eax, eax
0x14000e8c1  jns     short loc_14000E8D4
0x14000e8c3  lea     r8, aFailedToGetUpd; "Failed to get update count"
0x14000e8ca  mov     edx, 3EAh
0x14000e8cf  jmp     loc_14000E7D3
0x14000e8d4  cmp     dword ptr [rbp+arg_8], 0
0x14000e8d8  jle     loc_14000E965
0x14000e8de  xor     edi, edi
0x14000e8e0  mov     rcx, [rbp+arg_18]
0x14000e8e4  lea     r8, [rbp+arg_0]
0x14000e8e8  mov     [rbp+arg_0], 0
0x14000e8f0  mov     edx, edi
0x14000e8f2  mov     rax, [rcx]
0x14000e8f5  mov     rax, [rax+38h]
0x14000e8f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e8fe  test    eax, eax
0x14000e900  js      short loc_14000E938
0x14000e902  mov     rcx, [rbp+arg_0]; struct IUpdate *
0x14000e906  lea     rdx, aUupUpdate; "UUP.Update"
0x14000e90d  call    ?WusaIsUUPProductNameMatch@@YA_NPEAUIUpdate@@PEBG@Z; WusaIsUUPProductNameMatch(IUpdate *,ushort const *)
0x14000e912  mov     rcx, [rbp+arg_0]
0x14000e916  test    al, al
0x14000e918  jnz     short loc_14000E934
0x14000e91a  test    rcx, rcx
0x14000e91d  jz      short loc_14000E92B
0x14000e91f  mov     rax, [rcx]
0x14000e922  mov     rax, [rax+10h]
0x14000e926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e92b  inc     edi
0x14000e92d  cmp     edi, dword ptr [rbp+arg_8]
0x14000e930  jl      short loc_14000E8E0
0x14000e932  jmp     short loc_14000E965
0x14000e934  mov     bl, 1
0x14000e936  jmp     short loc_14000E954
0x14000e938  lea     r8, aFailedToGetUpd_6; "Failed to get update item"
0x14000e93f  mov     edx, 3F2h
0x14000e944  lea     rcx, aWusaisuupprodu; "WusaIsUUPProductNameMatch"
0x14000e94b  call    WusaLogDebugEventA
0x14000e950  mov     rcx, [rbp+arg_0]
0x14000e954  test    rcx, rcx
0x14000e957  jz      short loc_14000E965
0x14000e959  mov     rax, [rcx]
0x14000e95c  mov     rax, [rax+10h]
0x14000e960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e965  mov     rcx, [rbp+arg_18]
0x14000e969  test    rcx, rcx
0x14000e96c  jz      short loc_14000E97A
0x14000e96e  mov     rax, [rcx]
0x14000e971  mov     rax, [rax+10h]
0x14000e975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e97a  lea     rcx, [rbp+pvarg]; pvarg
0x14000e97e  call    cs:__imp_VariantClear
0x14000e984  mov     rcx, [rbp+arg_10]
0x14000e988  test    rcx, rcx
0x14000e98b  jz      short loc_14000E999
0x14000e98d  mov     rdx, [rcx]
0x14000e990  mov     rax, [rdx+10h]
0x14000e994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e999  mov     al, bl
0x14000e99b  add     rsp, 48h
0x14000e99f  pop     rdi
0x14000e9a0  pop     rsi
0x14000e9a1  pop     rbx
0x14000e9a2  pop     rbp
0x14000e9a3  retn
```
