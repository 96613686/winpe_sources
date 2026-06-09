# CThumbnailCacheAPI::_GetThumbCacheForDrivePath(ushort const *,_GUID const &,void * *)

- ea: `0x18002ed6c`
- end: `0x18002f08e`
- name: `?_GetThumbCacheForDrivePath@CThumbnailCacheAPI@@AEAAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `802`
- prototype: `int(CThumbnailCacheAPI *__hidden this, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x180018bf8`

## callees

- `0x180003624`
- `0x18000bfd8`
- `0x180017be0`
- `0x18001bfe0`
- `0x18002ed6c`
- `0x180034650`
- `0x180035830`
- `0x180035860`
- `0x18003f608`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002ef01`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002ef01`

## string_xrefs

- `0x18002edfc`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18002f00a`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18002f052`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18002eef2`: `WPSystem\SharedData\ThumbnailCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CThumbnailCacheAPI::_GetThumbCacheForDrivePath(
        CThumbnailCacheAPI *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned __int64 v8; // r8
  _QWORD *v9; // rdi
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // r14d
  void *v13; // rax
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // rax
  __int64 (__fastcall ***v15)(_QWORD, GUID *, _QWORD *); // r14
  int v16; // eax
  __int64 v17; // rdx
  size_t v18; // r10
  unsigned __int64 v19; // r9
  HRESULT v20; // eax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rcx
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  __int64 v30; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 v31; // [rsp+30h] [rbp-D0h]
  __int64 v32; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *a4 = 0;
  v8 = 0;
  v9 = (_QWORD *)((char *)this + 568);
  while ( 1 )
  {
    if ( v8 >= *((_QWORD *)this + 72) )
      goto LABEL_8;
    if ( *(_WORD *)(*v9 + 16 * v8) == *a2 )
      break;
    ++v8;
  }
  v10 = (***(__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))(*v9 + 16 * v8 + 8))(
          *(_QWORD *)(*v9 + 16 * v8 + 8),
          a3,
          a4);
  v11 = v10;
  if ( v10 >= 0 )
  {
    if ( !*a4 )
    {
LABEL_8:
      v30 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
      v12 = *((_DWORD *)this + 11);
      v30 = 0;
      v11 = -2147024882;
      v13 = operator new(0x320u, (const struct std::nothrow_t *)&std::nothrow);
      v29 = (int)v13;
      if ( !v13
        || (v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))CThumbnailCache::CThumbnailCache(v13, v12 | 4u),
            (v15 = v14) == 0)
        || (v11 = (**v14)(v14, &GUID_3413b9cd_0db3_4e97_8bf4_68fb100d1815, &v30),
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v15)[2])(v15),
            (v11 & 0x80000000) != 0) )
      {
        v19 = v11;
        v17 = 534;
        goto LABEL_35;
      }
      v16 = CThumbnailCacheAPI::_EnsureSystemDrivePath((WCHAR *)this);
      v11 = v16;
      if ( v16 < 0 )
      {
        v17 = 536;
LABEL_16:
        v19 = (unsigned int)v16;
LABEL_35:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
          (const char *)v19,
          v29);
        goto LABEL_36;
      }
      if ( *((_WORD *)this + 24) != *a2 )
      {
        v16 = StringCchCopyW(pszPath, 0x104u, a2);
        v11 = v16;
        if ( v16 < 0 )
        {
          v17 = 540;
          goto LABEL_16;
        }
        v20 = PathCchAppend(pszPath, v18, L"WPSystem\\SharedData\\ThumbnailCache");
        v11 = v20;
        if ( v20 < 0 )
        {
          v19 = (unsigned int)v20;
          v17 = 541;
          goto LABEL_35;
        }
        v21 = (*(__int64 (__fastcall **)(__int64, WCHAR *))(*(_QWORD *)v30 + 24LL))(v30, pszPath);
        v11 = v21;
        if ( v21 < 0 )
        {
          v19 = (unsigned int)v21;
          v17 = 542;
          goto LABEL_35;
        }
      }
      v32 = 0;
      v31 = *a2;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
      v22 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v30)(
              v30,
              &GUID_f676c15d_596a_4ce2_8234_33996f445db1,
              &v32);
      v11 = v22;
      if ( v22 < 0 )
      {
        v23 = 547;
LABEL_31:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
          (const char *)(unsigned int)v22,
          v29);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
LABEL_36:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
        return v11;
      }
      v24 = v9[1];
      if ( v24 == v9[3] )
      {
        v22 = CTSimpleArray<DriveCacheEntry,4294967294,CTPolicyCoTaskMem<DriveCacheEntry>,CSimpleArrayStandardCompareHelper<DriveCacheEntry>,CSimpleArrayStandardMergeHelper<DriveCacheEntry>>::_EnsureCapacity(
                v9,
                v24 + 1);
        v11 = v22;
        if ( v22 < 0 )
        {
          v23 = 548;
          goto LABEL_31;
        }
      }
      ++v9[1];
      v25 = 16LL * v9[1] + *v9 - 16LL;
      if ( v25 )
      {
        *(_WORD *)v25 = v31;
        v26 = v32;
        *(_QWORD *)(v25 + 8) = v32;
        if ( v26 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
      }
      v22 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v30)(v30, a3, a4);
      v11 = v22;
      if ( v22 < 0 )
      {
        v23 = 550;
        goto LABEL_31;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x20D,
    (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
    (const char *)(unsigned int)v10,
    v28);
  return v11;
}

```

## disassembly

```asm
0x18002ed6c  push    rbp
0x18002ed6e  push    rbx
0x18002ed6f  push    rsi
0x18002ed70  push    rdi
0x18002ed71  push    r12
0x18002ed73  push    r13
0x18002ed75  push    r14
0x18002ed77  push    r15
0x18002ed79  lea     rbp, [rsp-168h]
0x18002ed81  sub     rsp, 268h
0x18002ed88  mov     rax, cs:__security_cookie
0x18002ed8f  xor     rax, rsp
0x18002ed92  mov     [rbp+1A0h+var_50], rax
0x18002ed99  mov     r12, r9
0x18002ed9c  mov     r13, r8
0x18002ed9f  mov     r15, rdx
0x18002eda2  mov     rsi, rcx
0x18002eda5  xor     r14d, r14d
0x18002eda8  mov     [r9], r14
0x18002edab  mov     r8d, r14d
0x18002edae  lea     rdi, [rcx+238h]
0x18002edb5  cmp     r8, [rsi+240h]
0x18002edbc  jnb     short loc_18002EE1C
0x18002edbe  mov     rcx, r8
0x18002edc1  add     rcx, rcx
0x18002edc4  mov     rdx, [rdi]
0x18002edc7  movzx   eax, word ptr [r15]
0x18002edcb  cmp     [rdx+rcx*8], ax
0x18002edcf  jz      short loc_18002EDD6
0x18002edd1  inc     r8
0x18002edd4  jmp     short loc_18002EDB5
0x18002edd6  mov     rcx, [rdx+rcx*8+8]
0x18002eddb  mov     rax, [rcx]
0x18002edde  mov     r8, r12
0x18002ede1  mov     rdx, r13
0x18002ede4  mov     rax, [rax]
0x18002ede7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002edec  mov     ebx, eax
0x18002edee  test    eax, eax
0x18002edf0  jns     short loc_18002EE12
0x18002edf2  mov     rcx, [rbp+1A8h]; this
0x18002edf9  mov     r9d, eax; char *
0x18002edfc  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18002ee03  mov     edx, 20Dh; void *
0x18002ee08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ee0d  jmp     loc_18002F069
0x18002ee12  cmp     [r12], r14
0x18002ee16  jnz     loc_18002F03F
0x18002ee1c  mov     [rsp+2A0h+var_278], r14
0x18002ee21  lea     rcx, [rsp+2A0h+var_278]
0x18002ee26  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ee2b  mov     r14d, [rsi+2Ch]
0x18002ee2f  mov     [rsp+2A0h+var_278], 0
0x18002ee38  mov     ebx, 8007000Eh
0x18002ee3d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ee44  mov     ecx, 320h; unsigned __int64
0x18002ee49  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002ee4e  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x18002ee53  test    rax, rax
0x18002ee56  jz      loc_18002F043
0x18002ee5c  or      r14d, 4
0x18002ee60  mov     edx, r14d
0x18002ee63  mov     rcx, rax
0x18002ee66  call    ??0CThumbnailCache@@AEAA@W4THUMBNAILCACHECREATEFLAGS@@@Z; CThumbnailCache::CThumbnailCache(THUMBNAILCACHECREATEFLAGS)
0x18002ee6b  mov     r14, rax
0x18002ee6e  test    rax, rax
0x18002ee71  jz      loc_18002F043
0x18002ee77  mov     rcx, [rax]
0x18002ee7a  mov     rax, [rcx]
0x18002ee7d  lea     r8, [rsp+2A0h+var_278]
0x18002ee82  lea     rdx, _GUID_3413b9cd_0db3_4e97_8bf4_68fb100d1815
0x18002ee89  mov     rcx, r14
0x18002ee8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee91  mov     ebx, eax
0x18002ee93  mov     rcx, [r14]
0x18002ee96  mov     rax, [rcx+10h]
0x18002ee9a  mov     rcx, r14
0x18002ee9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eea2  test    ebx, ebx
0x18002eea4  js      loc_18002F043
0x18002eeaa  mov     rcx, rsi; this
0x18002eead  call    ?_EnsureSystemDrivePath@CThumbnailCacheAPI@@AEAAJXZ; CThumbnailCacheAPI::_EnsureSystemDrivePath(void)
0x18002eeb2  mov     ebx, eax
0x18002eeb4  test    eax, eax
0x18002eeb6  jns     short loc_18002EEBF
0x18002eeb8  mov     edx, 218h
0x18002eebd  jmp     short loc_18002EEEA
0x18002eebf  movzx   eax, word ptr [r15]
0x18002eec3  cmp     [rsi+30h], ax
0x18002eec7  jz      short loc_18002EF43
0x18002eec9  mov     r8, r15; unsigned __int16 *
0x18002eecc  mov     r10d, 104h
0x18002eed2  mov     edx, r10d; unsigned __int64
0x18002eed5  lea     rcx, [rsp+2A0h+pszPath]; unsigned __int16 *
0x18002eeda  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002eedf  mov     ebx, eax
0x18002eee1  test    eax, eax
0x18002eee3  jns     short loc_18002EEF2
0x18002eee5  mov     edx, 21Ch
0x18002eeea  mov     r9d, eax
0x18002eeed  jmp     loc_18002F04B
0x18002eef2  lea     r8, aWpsystemShared; "WPSystem\\SharedData\\ThumbnailCache"
0x18002eef9  mov     rdx, r10; cchPath
0x18002eefc  lea     rcx, [rsp+2A0h+pszPath]; pszPath
0x18002ef01  call    cs:__imp_PathCchAppend
0x18002ef07  mov     ebx, eax
0x18002ef09  test    eax, eax
0x18002ef0b  jns     short loc_18002EF1A
0x18002ef0d  mov     r9d, eax
0x18002ef10  mov     edx, 21Dh
0x18002ef15  jmp     loc_18002F04B
0x18002ef1a  mov     rcx, [rsp+2A0h+var_278]
0x18002ef1f  mov     rax, [rcx]
0x18002ef22  lea     rdx, [rsp+2A0h+pszPath]
0x18002ef27  mov     rax, [rax+18h]
0x18002ef2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef30  mov     ebx, eax
0x18002ef32  test    eax, eax
0x18002ef34  jns     short loc_18002EF43
0x18002ef36  mov     r9d, eax
0x18002ef39  mov     edx, 21Eh
0x18002ef3e  jmp     loc_18002F04B
0x18002ef43  mov     [rsp+2A0h+var_268], 0
0x18002ef4c  movzx   eax, word ptr [r15]
0x18002ef50  mov     [rsp+2A0h+var_270], ax
0x18002ef55  lea     rcx, [rsp+2A0h+var_268]
0x18002ef5a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ef5f  nop
0x18002ef60  mov     rcx, [rsp+2A0h+var_278]
0x18002ef65  mov     rax, [rcx]
0x18002ef68  lea     r8, [rsp+2A0h+var_268]
0x18002ef6d  lea     rdx, _GUID_f676c15d_596a_4ce2_8234_33996f445db1
0x18002ef74  mov     rax, [rax]
0x18002ef77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef7c  mov     ebx, eax
0x18002ef7e  test    eax, eax
0x18002ef80  jns     short loc_18002EF89
0x18002ef82  mov     edx, 223h
0x18002ef87  jmp     short loc_18002F007
0x18002ef89  mov     rdx, [rdi+8]
0x18002ef8d  cmp     rdx, [rdi+18h]
0x18002ef91  jnz     short loc_18002EFAB
0x18002ef93  inc     rdx
0x18002ef96  mov     rcx, rdi
0x18002ef99  call    ?_EnsureCapacity@?$CTSimpleArray@UDriveCacheEntry@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UDriveCacheEntry@@@@V?$CSimpleArrayStandardCompareHelper@UDriveCacheEntry@@@@V?$CSimpleArrayStandardMergeHelper@UDriveCacheEntry@@@@@@QEAAJ_K0@Z; CTSimpleArray<DriveCacheEntry,4294967294,CTPolicyCoTaskMem<DriveCacheEntry>,CSimpleArrayStandardCompareHelper<DriveCacheEntry>,CSimpleArrayStandardMergeHelper<DriveCacheEntry>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18002ef9e  mov     ebx, eax
0x18002efa0  test    eax, eax
0x18002efa2  jns     short loc_18002EFAB
0x18002efa4  mov     edx, 224h
0x18002efa9  jmp     short loc_18002F007
0x18002efab  inc     qword ptr [rdi+8]
0x18002efaf  mov     rcx, [rdi+8]
0x18002efb3  shl     rcx, 4
0x18002efb7  mov     rdx, [rdi]
0x18002efba  add     rdx, 0FFFFFFFFFFFFFFF0h
0x18002efbe  add     rdx, rcx
0x18002efc1  jz      short loc_18002EFE6
0x18002efc3  movzx   eax, [rsp+2A0h+var_270]
0x18002efc8  mov     [rdx], ax
0x18002efcb  mov     rcx, [rsp+2A0h+var_268]
0x18002efd0  mov     [rdx+8], rcx
0x18002efd4  test    rcx, rcx
0x18002efd7  jz      short loc_18002EFE6
0x18002efd9  mov     rax, [rcx]
0x18002efdc  mov     rax, [rax+8]
0x18002efe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efe5  nop
0x18002efe6  mov     rcx, [rsp+2A0h+var_278]
0x18002efeb  mov     rax, [rcx]
0x18002efee  mov     r8, r12
0x18002eff1  mov     rdx, r13
0x18002eff4  mov     rax, [rax]
0x18002eff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002effc  mov     ebx, eax
0x18002effe  test    eax, eax
0x18002f000  jns     short loc_18002F02A
0x18002f002  mov     edx, 226h; void *
0x18002f007  mov     r9d, eax; char *
0x18002f00a  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18002f011  mov     rcx, [rbp+1A8h]; this
0x18002f018  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f01d  nop
0x18002f01e  lea     rcx, [rsp+2A0h+var_268]
0x18002f023  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f028  jmp     short loc_18002F05F
0x18002f02a  lea     rcx, [rsp+2A0h+var_268]
0x18002f02f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f034  nop
0x18002f035  lea     rcx, [rsp+2A0h+var_278]
0x18002f03a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f03f  xor     eax, eax
0x18002f041  jmp     short loc_18002F06B
0x18002f043  mov     r9d, ebx; char *
0x18002f046  mov     edx, 216h; void *
0x18002f04b  mov     rcx, [rbp+1A8h]; this
0x18002f052  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18002f059  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f05e  nop
0x18002f05f  lea     rcx, [rsp+2A0h+var_278]
0x18002f064  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f069  mov     eax, ebx
0x18002f06b  mov     rcx, [rbp+1A0h+var_50]
0x18002f072  xor     rcx, rsp; StackCookie
0x18002f075  call    __security_check_cookie
0x18002f07a  add     rsp, 268h
0x18002f081  pop     r15
0x18002f083  pop     r14
0x18002f085  pop     r13
0x18002f087  pop     r12
0x18002f089  pop     rdi
0x18002f08a  pop     rsi
0x18002f08b  pop     rbx
0x18002f08c  pop     rbp
0x18002f08d  retn
```
