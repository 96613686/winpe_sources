# _GetSearchIDListOverPictureLibraryTopRated(_ITEMIDLIST_ABSOLUTE * *,ushort const *)

- ea: `0x180040aa0`
- end: `0x180040d40`
- name: `?_GetSearchIDListOverPictureLibraryTopRated@@YAJPEAPEAU_ITEMIDLIST_ABSOLUTE@@PEBG@Z`
- size: `672`
- prototype: `int(struct _ITEMIDLIST_ABSOLUTE **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180041df8`

## callees

- `0x180002280`
- `0x180002f34`
- `0x180039890`
- `0x18003e140`
- `0x18003e3a8`
- `0x180040818`
- `0x180040aa0`
- `0x18004e89c`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040b4a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040c25`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040b4a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040c25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d10`

## pseudocode

```c
__int64 __fastcall _GetSearchIDListOverPictureLibraryTopRated(
        struct _ITEMIDLIST_ABSOLUTE **a1,
        const unsigned __int16 *a2)
{
  HRESULT PictureLibraryScope; // ebx
  const struct _GUID *v5; // r9
  const struct _GUID *v6; // rdx
  const unsigned __int16 *v7; // rcx
  LPVOID v9; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  struct ICondition *v12[2]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v13[8]; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  GUID v15; // [rsp+80h] [rbp-80h]
  int v16; // [rsp+9Ch] [rbp-64h]
  int v17; // [rsp+A0h] [rbp-60h]
  void *v18; // [rsp+E8h] [rbp-18h] BYREF
  struct IScope *v19; // [rsp+F0h] [rbp-10h] BYREF
  void *v20; // [rsp+100h] [rbp+0h] BYREF

  *a1 = 0;
  memset_0(v13, 0, 0xB0u);
  v16 = -1;
  v15 = FOLDERTYPEID_Pictures;
  v17 = -1;
  PictureLibraryScope = CoAllocString(a2, (unsigned __int16 **)&pv);
  if ( PictureLibraryScope >= 0 )
  {
    PictureLibraryScope = _GetPictureLibraryScope(&v19);
    if ( PictureLibraryScope >= 0 )
    {
      ppv = 0;
      PictureLibraryScope = CoCreateInstance(
                              &CLSID_ConditionFactory,
                              0,
                              1u,
                              &GUID_71d222e1_432f_429e_8c13_b6dafde5077a,
                              &ppv);
      if ( PictureLibraryScope >= 0 )
      {
        *(_OWORD *)v12 = 0;
        PictureLibraryScope = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, __int64))(*(_QWORD *)ppv + 96LL))(
                                ppv,
                                &PKEY_Rating,
                                6);
        if ( PictureLibraryScope >= 0 )
        {
          PictureLibraryScope = GetImageFileExtensionFilterCondition(&v12[1]);
          if ( PictureLibraryScope >= 0 )
          {
            PictureLibraryScope = SHCombineMultipleConditions(CT_AND_CONDITION, v12, 2u, v5, &v20);
            if ( PictureLibraryScope >= 0 )
            {
              PictureLibraryScope = SHCreateSingleKindList(v7, v6, &v18);
              if ( PictureLibraryScope >= 0 )
              {
                v9 = 0;
                PictureLibraryScope = CoCreateInstance(
                                        &GUID_6e682784_1eca_4cf2_988d_96b6e89e9a4d,
                                        0,
                                        1u,
                                        &GUID_c0a6c367_c264_4385_a704_9088bdc3640e,
                                        &v9);
                if ( PictureLibraryScope >= 0 )
                {
                  v10 = 0;
                  PictureLibraryScope = (*(__int64 (__fastcall **)(LPVOID, _BYTE *, GUID *, __int64 *))(*(_QWORD *)v9 + 24LL))(
                                          v9,
                                          v13,
                                          &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
                                          &v10);
                  if ( PictureLibraryScope >= 0 )
                  {
                    PictureLibraryScope = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, struct _ITEMIDLIST_ABSOLUTE **))(*(_QWORD *)v9 + 40LL))(
                                            v9,
                                            v10,
                                            0,
                                            a1);
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
                  }
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
                }
                (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
              }
              (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
            }
            ((void (__fastcall *)(struct ICondition *))v12[1]->lpVtbl->Release)(v12[1]);
          }
          ((void (__fastcall *)(struct ICondition *))v12[0]->lpVtbl->Release)(v12[0]);
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      (*(void (__fastcall **)(struct IScope *))(*(_QWORD *)v19 + 16LL))(v19);
    }
    CoTaskMemFree(pv);
  }
  return (unsigned int)PictureLibraryScope;
}

```

## disassembly

```asm
0x180040aa0  mov     [rsp-8+arg_10], rbx
0x180040aa5  mov     [rsp-8+arg_18], rdi
0x180040aaa  push    rbp
0x180040aab  lea     rbp, [rsp-30h]
0x180040ab0  sub     rsp, 130h
0x180040ab7  mov     rax, cs:__security_cookie
0x180040abe  xor     rax, rsp
0x180040ac1  mov     [rbp+30h+var_10], rax
0x180040ac5  mov     rbx, rdx
0x180040ac8  mov     qword ptr [rcx], 0
0x180040acf  mov     rdi, rcx
0x180040ad2  xor     edx, edx; Val
0x180040ad4  lea     rcx, [rsp+130h+var_C0]; void *
0x180040ad9  mov     r8d, 0B0h; Size
0x180040adf  call    memset_0
0x180040ae4  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Pictures.Data1
0x180040aeb  or      eax, 0FFFFFFFFh
0x180040aee  lea     rdx, [rsp+130h+pv]; unsigned __int16 **
0x180040af3  mov     rcx, rbx; unsigned __int16 *
0x180040af6  mov     [rbp+30h+var_94], eax
0x180040af9  movdqu  [rbp+30h+var_B0], xmm0
0x180040afe  mov     [rbp+30h+var_90], eax
0x180040b01  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x180040b06  mov     ebx, eax
0x180040b08  test    eax, eax
0x180040b0a  js      loc_180040D1C
0x180040b10  lea     rcx, [rbp+30h+var_40]; struct IScope **
0x180040b14  call    ?_GetPictureLibraryScope@@YAJPEAPEAUIScope@@@Z; _GetPictureLibraryScope(IScope * *)
0x180040b19  mov     ebx, eax
0x180040b1b  test    eax, eax
0x180040b1d  js      loc_180040D0B
0x180040b23  xor     edx, edx; pUnkOuter
0x180040b25  mov     [rsp+130h+var_E0], 0
0x180040b2e  lea     rax, [rsp+130h+var_E0]
0x180040b33  lea     r9, _GUID_71d222e1_432f_429e_8c13_b6dafde5077a; riid
0x180040b3a  mov     [rsp+130h+ppv], rax; ppv
0x180040b3f  lea     rcx, CLSID_ConditionFactory; rclsid
0x180040b46  lea     r8d, [rdx+1]; dwClsContext
0x180040b4a  call    cs:__imp_CoCreateInstance
0x180040b51  nop     dword ptr [rax+rax+00h]
0x180040b56  mov     ebx, eax
0x180040b58  test    eax, eax
0x180040b5a  js      loc_180040CFB
0x180040b60  mov     rcx, [rsp+130h+var_E0]
0x180040b65  lea     rdx, [rsp+130h+var_D8]
0x180040b6a  mov     [rsp+130h+var_100], rdx
0x180040b6f  xorps   xmm0, xmm0
0x180040b72  movups  xmmword ptr [rsp+130h+var_D8], xmm0
0x180040b77  mov     r9d, 3Fh ; '?'
0x180040b7d  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x180040b84  mov     rax, [rcx]
0x180040b87  mov     [rsp+130h+var_108], rdx
0x180040b8c  lea     rdx, PKEY_Rating
0x180040b93  mov     dword ptr [rsp+130h+ppv], 0
0x180040b9b  lea     r8d, [r9-39h]
0x180040b9f  mov     rax, [rax+60h]
0x180040ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ba8  mov     ebx, eax
0x180040baa  test    eax, eax
0x180040bac  js      loc_180040CEA
0x180040bb2  lea     rcx, [rsp+130h+var_D8+8]; struct ICondition **
0x180040bb7  call    ?GetImageFileExtensionFilterCondition@@YAJPEAPEAUICondition@@@Z; GetImageFileExtensionFilterCondition(ICondition * *)
0x180040bbc  mov     ebx, eax
0x180040bbe  test    eax, eax
0x180040bc0  js      loc_180040CD9
0x180040bc6  lea     rax, [rbp+30h+var_30]
0x180040bca  mov     r8d, 2; unsigned int
0x180040bd0  lea     rdx, [rsp+130h+var_D8]; struct ICondition **
0x180040bd5  mov     [rsp+130h+ppv], rax; void **
0x180040bda  xor     ecx, ecx; enum tagCONDITION_TYPE
0x180040bdc  call    ?SHCombineMultipleConditions@@YAJW4tagCONDITION_TYPE@@PEAPEAUICondition@@IAEBU_GUID@@PEAPEAX@Z; SHCombineMultipleConditions(tagCONDITION_TYPE,ICondition * *,uint,_GUID const &,void * *)
0x180040be1  mov     ebx, eax
0x180040be3  test    eax, eax
0x180040be5  js      loc_180040CC8
0x180040beb  lea     r8, [rbp+30h+var_48]; void **
0x180040bef  call    ?SHCreateSingleKindList@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; SHCreateSingleKindList(ushort const *,_GUID const &,void * *)
0x180040bf4  mov     ebx, eax
0x180040bf6  test    eax, eax
0x180040bf8  js      loc_180040CB8
0x180040bfe  xor     edx, edx; pUnkOuter
0x180040c00  mov     [rsp+130h+var_F0], 0
0x180040c09  lea     rax, [rsp+130h+var_F0]
0x180040c0e  lea     r9, _GUID_c0a6c367_c264_4385_a704_9088bdc3640e; riid
0x180040c15  mov     [rsp+130h+ppv], rax; ppv
0x180040c1a  lea     rcx, _GUID_6e682784_1eca_4cf2_988d_96b6e89e9a4d; rclsid
0x180040c21  lea     r8d, [rdx+1]; dwClsContext
0x180040c25  call    cs:__imp_CoCreateInstance
0x180040c2c  nop     dword ptr [rax+rax+00h]
0x180040c31  mov     ebx, eax
0x180040c33  test    eax, eax
0x180040c35  js      short loc_180040CA8
0x180040c37  mov     rcx, [rsp+130h+var_F0]
0x180040c3c  lea     r9, [rsp+130h+var_E8]
0x180040c41  mov     [rsp+130h+var_E8], 0
0x180040c4a  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x180040c51  lea     rdx, [rsp+130h+var_C0]
0x180040c56  mov     rax, [rcx]
0x180040c59  mov     rax, [rax+18h]
0x180040c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c62  mov     ebx, eax
0x180040c64  test    eax, eax
0x180040c66  js      short loc_180040C97
0x180040c68  mov     rcx, [rsp+130h+var_F0]
0x180040c6d  mov     r9, rdi
0x180040c70  mov     rdx, [rsp+130h+var_E8]
0x180040c75  xor     r8d, r8d
0x180040c78  mov     rax, [rcx]
0x180040c7b  mov     rax, [rax+28h]
0x180040c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c84  mov     rcx, [rsp+130h+var_E8]
0x180040c89  mov     ebx, eax
0x180040c8b  mov     rax, [rcx]
0x180040c8e  mov     rax, [rax+10h]
0x180040c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c97  mov     rcx, [rsp+130h+var_F0]
0x180040c9c  mov     rax, [rcx]
0x180040c9f  mov     rax, [rax+10h]
0x180040ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ca8  mov     rcx, [rbp+30h+var_48]
0x180040cac  mov     rax, [rcx]
0x180040caf  mov     rax, [rax+10h]
0x180040cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cb8  mov     rcx, [rbp+30h+var_30]
0x180040cbc  mov     rax, [rcx]
0x180040cbf  mov     rax, [rax+10h]
0x180040cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cc8  mov     rcx, [rsp+130h+var_D8+8]
0x180040ccd  mov     rax, [rcx]
0x180040cd0  mov     rax, [rax+10h]
0x180040cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cd9  mov     rcx, [rsp+130h+var_D8]
0x180040cde  mov     rax, [rcx]
0x180040ce1  mov     rax, [rax+10h]
0x180040ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cea  mov     rcx, [rsp+130h+var_E0]
0x180040cef  mov     rax, [rcx]
0x180040cf2  mov     rax, [rax+10h]
0x180040cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cfb  mov     rcx, [rbp+30h+var_40]
0x180040cff  mov     rax, [rcx]
0x180040d02  mov     rax, [rax+10h]
0x180040d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d0b  mov     rcx, [rsp+130h+pv]; pv
0x180040d10  call    cs:__imp_CoTaskMemFree
0x180040d17  nop     dword ptr [rax+rax+00h]
0x180040d1c  mov     eax, ebx
0x180040d1e  mov     rcx, [rbp+30h+var_10]
0x180040d22  xor     rcx, rsp; StackCookie
0x180040d25  call    __security_check_cookie
0x180040d2a  lea     r11, [rsp+130h+var_s0]
0x180040d32  mov     rbx, [r11+20h]
0x180040d36  mov     rdi, [r11+28h]
0x180040d3a  mov     rsp, r11
0x180040d3d  pop     rbp
0x180040d3e  retn
```
