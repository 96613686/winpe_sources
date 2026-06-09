# CThumbCacheClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180017d50`
- end: `0x180018094`
- name: `?CreateInstance@CThumbCacheClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `836`
- prototype: `__int64 __fastcall(CThumbCacheClassFactory *this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180017be0`
- `0x180017d50`
- `0x18001809c`
- `0x1800182e0`
- `0x180035860`
- `0x1800388cc`
- `0x18003f1f4`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017fb2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017fb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CThumbCacheClassFactory::CreateInstance(
        CThumbCacheClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v6; // rax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  void *v15; // rdi
  void *v16; // rax
  __int64 (__fastcall ***v17)(_QWORD, const struct _GUID *, void **); // rax
  __int64 (__fastcall ***v18)(_QWORD, const struct _GUID *, void **); // rdi
  __int64 v19; // rax
  __int64 v20; // rax
  int *v21; // rbx
  _DWORD *v22; // rdi
  LPVOID ppv; // [rsp+30h] [rbp-38h] BYREF
  int v24; // [rsp+38h] [rbp-30h] BYREF
  __int64 v25; // [rsp+40h] [rbp-28h]
  char v26; // [rsp+48h] [rbp-20h] BYREF

  *a4 = 0;
  if ( a2 )
    return (unsigned int)-2147221232;
  v6 = *(_QWORD *)((char *)this + 12) - *(_QWORD *)&GUID_cbe0fed3_4b91_4e90_8354_8a8c84ec6872.Data1;
  if ( !v6 )
    v6 = *(_QWORD *)((char *)this + 20) - *(_QWORD *)GUID_cbe0fed3_4b91_4e90_8354_8a8c84ec6872.Data4;
  if ( !v6 )
    return (unsigned int)ThumbnailStreamCacheCreateInstance(a3, a4);
  v11 = *(_QWORD *)((char *)this + 12) - *(_QWORD *)&GUID_50ef4544_ac9f_4a8e_b21b_8a26180db13f.Data1;
  if ( !v11 )
    v11 = *(_QWORD *)((char *)this + 20) - *(_QWORD *)GUID_50ef4544_ac9f_4a8e_b21b_8a26180db13f.Data4;
  if ( !v11 )
  {
    v8 = 0;
    return (unsigned int)ThumbnailCacheAPICreateInstance(v8, a3, a4);
  }
  v12 = *(_QWORD *)((char *)this + 12) - *(_QWORD *)&GUID_7efc002a_071f_4ce7_b265_f4b4263d2fd2.Data1;
  if ( !v12 )
    v12 = *(_QWORD *)((char *)this + 20) - *(_QWORD *)GUID_7efc002a_071f_4ce7_b265_f4b4263d2fd2.Data4;
  if ( !v12 )
  {
    v8 = 1;
    return (unsigned int)ThumbnailCacheAPICreateInstance(v8, a3, a4);
  }
  v13 = *(_QWORD *)((char *)this + 12) - *(_QWORD *)&GUID_2155fee3_2419_4373_b102_6843707eb41f.Data1;
  if ( !v13 )
    v13 = *(_QWORD *)((char *)this + 20) - *(_QWORD *)GUID_2155fee3_2419_4373_b102_6843707eb41f.Data4;
  if ( v13 )
  {
    v14 = *(_QWORD *)((char *)this + 12) - *(_QWORD *)&GUID_4db26476_6787_4046_b836_e8412a9e8a27.Data1;
    if ( !v14 )
      v14 = *(_QWORD *)((char *)this + 20) - *(_QWORD *)GUID_4db26476_6787_4046_b836_e8412a9e8a27.Data4;
    if ( v14 )
    {
      v19 = *(_QWORD *)((char *)this + 12) - *(_QWORD *)&GUID_889900c3_59f3_4c2f_ae21_a409ea01e605.Data1;
      if ( !v19 )
        v19 = *(_QWORD *)((char *)this + 20) - *(_QWORD *)GUID_889900c3_59f3_4c2f_ae21_a409ea01e605.Data4;
      if ( !v19 )
        return (unsigned int)CEmptyVolumeCache::CreateInstance(a3, a4);
      v20 = *(_QWORD *)((char *)this + 12) - *(_QWORD *)&GUID_ab8902b4_09ca_4bb6_b78d_a8f59079a8d5.Data1;
      if ( !v20 )
        v20 = *(_QWORD *)((char *)this + 20) - *(_QWORD *)GUID_ab8902b4_09ca_4bb6_b78d_a8f59079a8d5.Data4;
      if ( v20 )
      {
        return (unsigned int)-2147221231;
      }
      else
      {
        v24 = 1;
        v25 = 2;
        ppv = 0;
        if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv) >= 0 )
        {
          v21 = &v24;
          do
          {
            (*(void (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
              ppv,
              (unsigned int)*v21,
              *((_QWORD *)v21 + 1));
            v21 += 4;
          }
          while ( v21 != (int *)&v26 );
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        v9 = -2147024882;
        v22 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
        ppv = v22;
        if ( v22 )
        {
          *(_QWORD *)v22 = &CCreateObject::`vftable';
          v22[2] = 1;
          DllAddRef();
        }
        else
        {
          v22 = 0;
        }
        ppv = v22;
        if ( v22 )
        {
          v9 = (**(__int64 (__fastcall ***)(_DWORD *, const struct _GUID *, void **))v22)(v22, a3, a4);
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v22 + 16LL))(v22);
        }
      }
    }
    else
    {
      v9 = -2147024882;
      v15 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
      ppv = v15;
      if ( v15 )
      {
        *(_QWORD *)v15 = &CSharedBitmap::`vftable';
        *((_DWORD *)v15 + 2) = 1;
        *((_QWORD *)v15 + 4) = 0;
        *((_QWORD *)v15 + 5) = 0;
        *((_QWORD *)v15 + 6) = 0;
        *((_DWORD *)v15 + 14) = 0;
        DllAddRef();
        *((_QWORD *)v15 + 2) = 0;
        *((_DWORD *)v15 + 6) = 0;
        v9 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v15)(v15, a3, a4);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
      }
    }
  }
  else
  {
    v9 = -2147024882;
    v16 = operator new(0x320u, (const struct std::nothrow_t *)&std::nothrow);
    ppv = v16;
    if ( v16 )
    {
      v17 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))CThumbnailCache::CThumbnailCache(v16, 2);
      v18 = v17;
      if ( v17 )
      {
        v9 = (**v17)(v17, a3, a4);
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v18)[2])(v18);
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180017d50  mov     [rsp+arg_0], rbx
0x180017d55  push    rbp
0x180017d56  push    rsi
0x180017d57  push    rdi
0x180017d58  sub     rsp, 50h
0x180017d5c  mov     rsi, r9
0x180017d5f  mov     rbp, r8
0x180017d62  mov     qword ptr [r9], 0
0x180017d69  test    rdx, rdx
0x180017d6c  jnz     loc_180018085
0x180017d72  mov     rax, [rcx+0Ch]
0x180017d76  sub     rax, qword ptr cs:_GUID_cbe0fed3_4b91_4e90_8354_8a8c84ec6872.Data1
0x180017d7d  jnz     short loc_180017D8A
0x180017d7f  mov     rax, [rcx+14h]
0x180017d83  sub     rax, qword ptr cs:_GUID_cbe0fed3_4b91_4e90_8354_8a8c84ec6872.Data4
0x180017d8a  test    rax, rax
0x180017d8d  jnz     short loc_180017DBA
0x180017d8f  mov     rdx, rsi; void **
0x180017d92  mov     rcx, rbp; struct _GUID *
0x180017d95  call    ?ThumbnailStreamCacheCreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; ThumbnailStreamCacheCreateInstance(_GUID const &,void * *)
0x180017d9a  jmp     short loc_180017DA9
0x180017d9c  xor     ecx, ecx
0x180017d9e  mov     rdx, rbp
0x180017da1  mov     r8, rsi
0x180017da4  call    ?ThumbnailCacheAPICreateInstance@@YAJW4THUMBNAILCACHECREATEFLAGS@@AEBU_GUID@@PEAPEAX@Z; ThumbnailCacheAPICreateInstance(THUMBNAILCACHECREATEFLAGS,_GUID const &,void * *)
0x180017da9  mov     ebx, eax
0x180017dab  mov     eax, ebx
0x180017dad  mov     rbx, [rsp+68h+arg_0]
0x180017db2  add     rsp, 50h
0x180017db6  pop     rdi
0x180017db7  pop     rsi
0x180017db8  pop     rbp
0x180017db9  retn
0x180017dba  mov     rax, [rcx+0Ch]
0x180017dbe  sub     rax, qword ptr cs:_GUID_50ef4544_ac9f_4a8e_b21b_8a26180db13f.Data1
0x180017dc5  jnz     short loc_180017DD2
0x180017dc7  mov     rax, [rcx+14h]
0x180017dcb  sub     rax, qword ptr cs:_GUID_50ef4544_ac9f_4a8e_b21b_8a26180db13f.Data4
0x180017dd2  test    rax, rax
0x180017dd5  jz      short loc_180017D9C
0x180017dd7  mov     rax, [rcx+0Ch]
0x180017ddb  sub     rax, qword ptr cs:_GUID_7efc002a_071f_4ce7_b265_f4b4263d2fd2.Data1
0x180017de2  jnz     short loc_180017DEF
0x180017de4  mov     rax, [rcx+14h]
0x180017de8  sub     rax, qword ptr cs:_GUID_7efc002a_071f_4ce7_b265_f4b4263d2fd2.Data4
0x180017def  test    rax, rax
0x180017df2  jz      loc_180017ED6
0x180017df8  mov     rax, [rcx+0Ch]
0x180017dfc  sub     rax, qword ptr cs:_GUID_2155fee3_2419_4373_b102_6843707eb41f.Data1
0x180017e03  jnz     short loc_180017E10
0x180017e05  mov     rax, [rcx+14h]
0x180017e09  sub     rax, qword ptr cs:_GUID_2155fee3_2419_4373_b102_6843707eb41f.Data4
0x180017e10  test    rax, rax
0x180017e13  jz      loc_180017EE0
0x180017e19  mov     rax, [rcx+0Ch]
0x180017e1d  sub     rax, qword ptr cs:_GUID_4db26476_6787_4046_b836_e8412a9e8a27.Data1
0x180017e24  jnz     short loc_180017E31
0x180017e26  mov     rax, [rcx+14h]
0x180017e2a  sub     rax, qword ptr cs:_GUID_4db26476_6787_4046_b836_e8412a9e8a27.Data4
0x180017e31  test    rax, rax
0x180017e34  jnz     loc_180017F3C
0x180017e3a  mov     ebx, 8007000Eh
0x180017e3f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017e46  lea     ecx, [rax+40h]; unsigned __int64
0x180017e49  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017e4e  mov     rdi, rax
0x180017e51  mov     [rsp+68h+var_38], rax
0x180017e56  test    rax, rax
0x180017e59  jz      loc_180017DAB
0x180017e5f  lea     rax, ??_7CSharedBitmap@@6B@; const CSharedBitmap::`vftable'
0x180017e66  mov     [rdi], rax
0x180017e69  mov     dword ptr [rdi+8], 1
0x180017e70  mov     qword ptr [rdi+20h], 0
0x180017e78  mov     qword ptr [rdi+28h], 0
0x180017e80  mov     qword ptr [rdi+30h], 0
0x180017e88  mov     dword ptr [rdi+38h], 0
0x180017e8f  call    DllAddRef
0x180017e94  test    rdi, rdi
0x180017e97  jz      loc_180017DAB
0x180017e9d  mov     qword ptr [rdi+10h], 0
0x180017ea5  mov     dword ptr [rdi+18h], 0
0x180017eac  mov     rax, [rdi]
0x180017eaf  mov     r8, rsi
0x180017eb2  mov     rdx, rbp
0x180017eb5  mov     rcx, rdi
0x180017eb8  mov     rax, [rax]
0x180017ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ec0  mov     ebx, eax
0x180017ec2  mov     rax, [rdi]
0x180017ec5  mov     rax, [rax+10h]
0x180017ec9  mov     rcx, rdi
0x180017ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ed1  jmp     loc_180017DAB
0x180017ed6  mov     ecx, 1
0x180017edb  jmp     loc_180017D9E
0x180017ee0  mov     ebx, 8007000Eh
0x180017ee5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017eec  mov     ecx, 320h; unsigned __int64
0x180017ef1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017ef6  mov     [rsp+68h+var_38], rax
0x180017efb  test    rax, rax
0x180017efe  jz      loc_180017DAB
0x180017f04  mov     edx, 2
0x180017f09  mov     rcx, rax
0x180017f0c  call    ??0CThumbnailCache@@AEAA@W4THUMBNAILCACHECREATEFLAGS@@@Z; CThumbnailCache::CThumbnailCache(THUMBNAILCACHECREATEFLAGS)
0x180017f11  mov     rdi, rax
0x180017f14  test    rax, rax
0x180017f17  jz      loc_180017DAB
0x180017f1d  mov     rcx, [rax]
0x180017f20  mov     rax, [rcx]
0x180017f23  mov     r8, rsi
0x180017f26  mov     rdx, rbp
0x180017f29  mov     rcx, rdi
0x180017f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f31  mov     ebx, eax
0x180017f33  mov     rcx, [rdi]
0x180017f36  mov     rax, [rcx+10h]
0x180017f3a  jmp     short loc_180017EC9
0x180017f3c  mov     rax, [rcx+0Ch]
0x180017f40  sub     rax, qword ptr cs:_GUID_889900c3_59f3_4c2f_ae21_a409ea01e605.Data1
0x180017f47  jnz     short loc_180017F54
0x180017f49  mov     rax, [rcx+14h]
0x180017f4d  sub     rax, qword ptr cs:_GUID_889900c3_59f3_4c2f_ae21_a409ea01e605.Data4
0x180017f54  test    rax, rax
0x180017f57  jz      loc_18001806B
0x180017f5d  mov     rax, [rcx+0Ch]
0x180017f61  sub     rax, qword ptr cs:_GUID_ab8902b4_09ca_4bb6_b78d_a8f59079a8d5.Data1
0x180017f68  jnz     short loc_180017F75
0x180017f6a  mov     rax, [rcx+14h]
0x180017f6e  sub     rax, qword ptr cs:_GUID_ab8902b4_09ca_4bb6_b78d_a8f59079a8d5.Data4
0x180017f75  test    rax, rax
0x180017f78  jnz     loc_18001807B
0x180017f7e  mov     [rsp+68h+var_30], 1
0x180017f86  mov     [rsp+68h+var_28], 2
0x180017f8f  mov     [rsp+68h+var_38], rax
0x180017f94  lea     rax, [rsp+68h+var_38]
0x180017f99  mov     [rsp+68h+ppv], rax; ppv
0x180017f9e  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180017fa5  xor     edx, edx; pUnkOuter
0x180017fa7  lea     r8d, [rdx+1]; dwClsContext
0x180017fab  lea     rcx, CLSID_GlobalOptions; rclsid
0x180017fb2  call    cs:__imp_CoCreateInstance
0x180017fb8  test    eax, eax
0x180017fba  js      short loc_180017FF7
0x180017fbc  lea     rbx, [rsp+68h+var_30]
0x180017fc1  mov     rcx, [rsp+68h+var_38]
0x180017fc6  mov     rax, [rcx]
0x180017fc9  mov     r8, [rbx+8]
0x180017fcd  mov     edx, [rbx]
0x180017fcf  mov     rax, [rax+18h]
0x180017fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fd8  add     rbx, 10h
0x180017fdc  lea     rax, [rsp+68h+var_20]
0x180017fe1  cmp     rbx, rax
0x180017fe4  jnz     short loc_180017FC1
0x180017fe6  mov     rcx, [rsp+68h+var_38]
0x180017feb  mov     rax, [rcx]
0x180017fee  mov     rax, [rax+10h]
0x180017ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ff7  mov     ebx, 8007000Eh
0x180017ffc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018003  mov     ecx, 10h; unsigned __int64
0x180018008  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001800d  mov     rdi, rax
0x180018010  mov     [rsp+68h+var_38], rax
0x180018015  test    rax, rax
0x180018018  jz      short loc_18001808F
0x18001801a  lea     rax, ??_7CCreateObject@@6B@; const CCreateObject::`vftable'
0x180018021  mov     [rdi], rax
0x180018024  mov     dword ptr [rdi+8], 1
0x18001802b  call    DllAddRef
0x180018030  nop
0x180018031  mov     [rsp+68h+var_38], rdi
0x180018036  test    rdi, rdi
0x180018039  jz      short loc_180018051
0x18001803b  mov     rax, [rdi]
0x18001803e  mov     r8, rsi
0x180018041  mov     rdx, rbp
0x180018044  mov     rcx, rdi
0x180018047  mov     rax, [rax]
0x18001804a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001804f  mov     ebx, eax
0x180018051  test    rdi, rdi
0x180018054  jz      short loc_180018066
0x180018056  mov     rax, [rdi]
0x180018059  mov     rcx, rdi
0x18001805c  mov     rax, [rax+10h]
0x180018060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018065  nop
0x180018066  jmp     loc_180017DAB
0x18001806b  mov     rdx, rsi; void **
0x18001806e  mov     rcx, rbp; struct _GUID *
0x180018071  call    ?CreateInstance@CEmptyVolumeCache@@SAJAEBU_GUID@@PEAPEAX@Z; CEmptyVolumeCache::CreateInstance(_GUID const &,void * *)
0x180018076  jmp     loc_180017DA9
0x18001807b  mov     ebx, 80040111h
0x180018080  jmp     loc_180017DAB
0x180018085  mov     ebx, 80040110h
0x18001808a  jmp     loc_180017DAB
0x18001808f  xor     edi, edi
0x180018091  jmp     short loc_180018031
```
