# _GetSearchIDListOverPictureLibraryAll(_ITEMIDLIST_ABSOLUTE * *,ushort const *)

- ea: `0x1800408ec`
- end: `0x180040a97`
- name: `?_GetSearchIDListOverPictureLibraryAll@@YAJPEAPEAU_ITEMIDLIST_ABSOLUTE@@PEBG@Z`
- size: `427`
- prototype: `int(struct _ITEMIDLIST_ABSOLUTE **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180041df8`

## callees

- `0x180002280`
- `0x180002f34`
- `0x180039890`
- `0x18003e3a8`
- `0x180040818`
- `0x1800408ec`
- `0x18004e89c`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800409b8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800409b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040a67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040a67`

## pseudocode

```c
__int64 __fastcall _GetSearchIDListOverPictureLibraryAll(struct _ITEMIDLIST_ABSOLUTE **a1, const unsigned __int16 *a2)
{
  HRESULT PictureLibraryScope; // ebx
  const struct _GUID *v5; // rdx
  const unsigned __int16 *v6; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-79h] BYREF
  __int64 v9; // [rsp+38h] [rbp-71h] BYREF
  _BYTE v10[8]; // [rsp+40h] [rbp-69h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-61h] BYREF
  GUID v12; // [rsp+50h] [rbp-59h]
  int v13; // [rsp+6Ch] [rbp-3Dh]
  int v14; // [rsp+70h] [rbp-39h]
  void *v15; // [rsp+B8h] [rbp+Fh] BYREF
  struct IScope *v16; // [rsp+C0h] [rbp+17h] BYREF
  struct ICondition *v17; // [rsp+D0h] [rbp+27h] BYREF

  *a1 = 0;
  memset_0(v10, 0, 0xB0u);
  v13 = -1;
  v12 = FOLDERTYPEID_Pictures;
  v14 = -1;
  PictureLibraryScope = CoAllocString(a2, (unsigned __int16 **)&pv);
  if ( PictureLibraryScope >= 0 )
  {
    PictureLibraryScope = _GetPictureLibraryScope(&v16);
    if ( PictureLibraryScope >= 0 )
    {
      PictureLibraryScope = GetImageFileExtensionFilterCondition(&v17);
      if ( PictureLibraryScope >= 0 )
      {
        PictureLibraryScope = SHCreateSingleKindList(v6, v5, &v15);
        if ( PictureLibraryScope >= 0 )
        {
          ppv = 0;
          PictureLibraryScope = CoCreateInstance(
                                  &GUID_6e682784_1eca_4cf2_988d_96b6e89e9a4d,
                                  0,
                                  1u,
                                  &GUID_c0a6c367_c264_4385_a704_9088bdc3640e,
                                  &ppv);
          if ( PictureLibraryScope >= 0 )
          {
            v9 = 0;
            PictureLibraryScope = (*(__int64 (__fastcall **)(LPVOID, _BYTE *, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
                                    ppv,
                                    v10,
                                    &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
                                    &v9);
            if ( PictureLibraryScope >= 0 )
            {
              PictureLibraryScope = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, struct _ITEMIDLIST_ABSOLUTE **))(*(_QWORD *)ppv + 40LL))(
                                      ppv,
                                      v9,
                                      0,
                                      a1);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
            }
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
        }
        ((void (__fastcall *)(struct ICondition *))v17->lpVtbl->Release)(v17);
      }
      (*(void (__fastcall **)(struct IScope *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    CoTaskMemFree(pv);
  }
  return (unsigned int)PictureLibraryScope;
}

```

## disassembly

```asm
0x1800408ec  mov     [rsp-8+arg_10], rbx
0x1800408f1  mov     [rsp-8+arg_18], rdi
0x1800408f6  push    rbp
0x1800408f7  lea     rbp, [rsp-57h]
0x1800408fc  sub     rsp, 100h
0x180040903  mov     rax, cs:__security_cookie
0x18004090a  xor     rax, rsp
0x18004090d  mov     [rbp+57h+var_10], rax
0x180040911  mov     rbx, rdx
0x180040914  mov     qword ptr [rcx], 0
0x18004091b  mov     rdi, rcx
0x18004091e  xor     edx, edx; Val
0x180040920  lea     rcx, [rbp+57h+var_C0]; void *
0x180040924  mov     r8d, 0B0h; Size
0x18004092a  call    memset_0
0x18004092f  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Pictures.Data1
0x180040936  or      eax, 0FFFFFFFFh
0x180040939  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x18004093d  mov     rcx, rbx; unsigned __int16 *
0x180040940  mov     [rbp+57h+var_94], eax
0x180040943  movdqu  [rbp+57h+var_B0], xmm0
0x180040948  mov     [rbp+57h+var_90], eax
0x18004094b  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x180040950  mov     ebx, eax
0x180040952  test    eax, eax
0x180040954  js      loc_180040A73
0x18004095a  lea     rcx, [rbp+57h+var_40]; struct IScope **
0x18004095e  call    ?_GetPictureLibraryScope@@YAJPEAPEAUIScope@@@Z; _GetPictureLibraryScope(IScope * *)
0x180040963  mov     ebx, eax
0x180040965  test    eax, eax
0x180040967  js      loc_180040A63
0x18004096d  lea     rcx, [rbp+57h+var_30]; struct ICondition **
0x180040971  call    ?GetImageFileExtensionFilterCondition@@YAJPEAPEAUICondition@@@Z; GetImageFileExtensionFilterCondition(ICondition * *)
0x180040976  mov     ebx, eax
0x180040978  test    eax, eax
0x18004097a  js      loc_180040A53
0x180040980  lea     r8, [rbp+57h+var_48]; void **
0x180040984  call    ?SHCreateSingleKindList@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; SHCreateSingleKindList(ushort const *,_GUID const &,void * *)
0x180040989  mov     ebx, eax
0x18004098b  test    eax, eax
0x18004098d  js      loc_180040A43
0x180040993  xor     edx, edx; pUnkOuter
0x180040995  mov     [rbp+57h+var_D0], 0
0x18004099d  lea     rax, [rbp+57h+var_D0]
0x1800409a1  lea     r9, _GUID_c0a6c367_c264_4385_a704_9088bdc3640e; riid
0x1800409a8  mov     [rsp+100h+ppv], rax; ppv
0x1800409ad  lea     rcx, _GUID_6e682784_1eca_4cf2_988d_96b6e89e9a4d; rclsid
0x1800409b4  lea     r8d, [rdx+1]; dwClsContext
0x1800409b8  call    cs:__imp_CoCreateInstance
0x1800409bf  nop     dword ptr [rax+rax+00h]
0x1800409c4  mov     ebx, eax
0x1800409c6  test    eax, eax
0x1800409c8  js      short loc_180040A33
0x1800409ca  mov     rcx, [rbp+57h+var_D0]
0x1800409ce  lea     r9, [rbp+57h+var_C8]
0x1800409d2  mov     [rbp+57h+var_C8], 0
0x1800409da  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x1800409e1  lea     rdx, [rbp+57h+var_C0]
0x1800409e5  mov     rax, [rcx]
0x1800409e8  mov     rax, [rax+18h]
0x1800409ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800409f1  mov     ebx, eax
0x1800409f3  test    eax, eax
0x1800409f5  js      short loc_180040A23
0x1800409f7  mov     rcx, [rbp+57h+var_D0]
0x1800409fb  mov     r9, rdi
0x1800409fe  mov     rdx, [rbp+57h+var_C8]
0x180040a02  xor     r8d, r8d
0x180040a05  mov     rax, [rcx]
0x180040a08  mov     rax, [rax+28h]
0x180040a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a11  mov     rcx, [rbp+57h+var_C8]
0x180040a15  mov     ebx, eax
0x180040a17  mov     rax, [rcx]
0x180040a1a  mov     rax, [rax+10h]
0x180040a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a23  mov     rcx, [rbp+57h+var_D0]
0x180040a27  mov     rax, [rcx]
0x180040a2a  mov     rax, [rax+10h]
0x180040a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a33  mov     rcx, [rbp+57h+var_48]
0x180040a37  mov     rax, [rcx]
0x180040a3a  mov     rax, [rax+10h]
0x180040a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a43  mov     rcx, [rbp+57h+var_30]
0x180040a47  mov     rax, [rcx]
0x180040a4a  mov     rax, [rax+10h]
0x180040a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a53  mov     rcx, [rbp+57h+var_40]
0x180040a57  mov     rax, [rcx]
0x180040a5a  mov     rax, [rax+10h]
0x180040a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a63  mov     rcx, [rbp+57h+pv]; pv
0x180040a67  call    cs:__imp_CoTaskMemFree
0x180040a6e  nop     dword ptr [rax+rax+00h]
0x180040a73  mov     eax, ebx
0x180040a75  mov     rcx, [rbp+57h+var_10]
0x180040a79  xor     rcx, rsp; StackCookie
0x180040a7c  call    __security_check_cookie
0x180040a81  lea     r11, [rsp+100h+var_s0]
0x180040a89  mov     rbx, [r11+20h]
0x180040a8d  mov     rdi, [r11+28h]
0x180040a91  mov     rsp, r11
0x180040a94  pop     rbp
0x180040a95  retn
```
