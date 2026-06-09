# CThumbnailCache::GetImage(WTS_THUMBNAILID,uint,HBITMAP__ * *)

- ea: `0x180013a70`
- end: `0x180013d32`
- name: `?GetImage@CThumbnailCache@@UEAAJUWTS_THUMBNAILID@@IPEAPEAUHBITMAP__@@@Z`
- size: `706`
- prototype: `int(CThumbnailCache *__hidden this, struct WTS_THUMBNAILID *__struct_ptr, unsigned int, HBITMAP *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003624`
- `0x18000bfd8`
- `0x18000bffc`
- `0x18000cb34`
- `0x180013a70`
- `0x180013d38`
- `0x180013d80`
- `0x18001455c`
- `0x180015868`
- `0x180035830`
- `0x180041270`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013c72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013c72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b53`
- `OLEAUT32!__imp_SysFreeString` at `0x180013c7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180013c7c`

## string_xrefs

- `0x180013cd8`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x180013cff`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CThumbnailCache::GetImage(
        CThumbnailCache *this,
        struct WTS_THUMBNAILID *a2,
        unsigned int a3,
        HBITMAP *a4)
{
  int ThumbnailFromCache; // ebx
  char *v9; // rdi
  CThumbnailCache *v10; // rcx
  int v11; // eax
  void *v12; // rcx
  void *v13; // rcx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64, GUID *, __int64 *); // rbx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v19; // rdx
  int v20; // [rsp+20h] [rbp-69h]
  unsigned int v21; // [rsp+50h] [rbp-39h] BYREF
  HANDLE hObject[2]; // [rsp+58h] [rbp-31h] BYREF
  int v23; // [rsp+68h] [rbp-21h]
  __int64 v24; // [rsp+70h] [rbp-19h] BYREF
  __int64 v25; // [rsp+78h] [rbp-11h] BYREF
  IUnknown v26; // [rsp+80h] [rbp-9h] BYREF
  __int64 v27; // [rsp+88h] [rbp-1h]
  LPVOID pv; // [rsp+90h] [rbp+7h] BYREF
  int v29; // [rsp+98h] [rbp+Fh]
  int v30; // [rsp+9Ch] [rbp+13h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  *a4 = 0;
  ThumbnailFromCache = _ValidateSize(a3);
  if ( ThumbnailFromCache < 0 )
    return (unsigned int)ThumbnailFromCache;
  v9 = (char *)this - 32;
  ThumbnailFromCache = CThumbnailCache::_ValidateCallingThread((CThumbnailCache *)((char *)this - 32));
  if ( ThumbnailFromCache < 0 )
    return (unsigned int)ThumbnailFromCache;
  if ( v9[756] )
  {
    if ( !v9[757] )
    {
      ThumbnailFromCache = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x733,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
        (const char *)0x8000FFFFLL,
        v20);
      return (unsigned int)ThumbnailFromCache;
    }
    v10 = (CThumbnailCache *)((char *)this - 32);
    if ( v9[758] )
    {
      v11 = CThumbnailCache::ResetDestroyedCache(v10);
      ThumbnailFromCache = v11;
      if ( v11 >= 0 )
        goto LABEL_7;
      v19 = 1851;
    }
    else
    {
      v11 = CThumbnailCache::ResetCache(v10);
      ThumbnailFromCache = v11;
      if ( v11 >= 0 )
      {
LABEL_7:
        ThumbnailFromCache = 0;
        goto LABEL_8;
      }
      v19 = 1855;
    }
  }
  else
  {
    v11 = CThumbnailCache::AttemptInitialize((CThumbnailCache *)((char *)this - 32), WTS_NONE, a3);
    ThumbnailFromCache = v11;
    if ( v11 >= 0 )
      goto LABEL_7;
    v19 = 1847;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v19,
    (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
    (const char *)(unsigned int)v11,
    v20);
LABEL_8:
  if ( ThumbnailFromCache >= 0 )
  {
    v29 = *((_DWORD *)this + 184) & 1;
    v26.lpVtbl = 0;
    pv = 0;
    CoTaskMemFree(0);
    v30 = 0;
    v27 = 0;
    v12 = pv;
    pv = 0;
    CoTaskMemFree(v12);
    v13 = pv;
    pv = 0;
    CoTaskMemFree(v13);
    pv = 0;
    v30 = 0;
    v26.lpVtbl = *(struct IUnknownVtbl **)a2->rgbKey;
    v27 = 0x1100000000LL;
    *(_OWORD *)hObject = 0;
    v23 = 0;
    v21 = 0;
    LODWORD(v24) = 0;
    v25 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    ThumbnailFromCache = CThumbnailCache::_TryGetThumbnailFromCache(
                           (__int64)this - 32,
                           &v26,
                           a3,
                           0,
                           (CGlobalRefCount *)hObject,
                           &v21,
                           &v24,
                           (__int64)&GUID_b11c5842_71c1_4cef_be46_1203d5fdb22f,
                           &v25);
    if ( ThumbnailFromCache >= 0 )
    {
      if ( v21 )
      {
        ThumbnailFromCache = -2147467259;
      }
      else
      {
        v24 = 0;
        v14 = v25;
        v15 = *(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)v25 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
        ThumbnailFromCache = v15(v14, 2, &GUID_091162a4_bc96_411f_aae8_c5122cd03363, &v24);
        if ( ThumbnailFromCache >= 0 )
          ThumbnailFromCache = (*(__int64 (__fastcall **)(__int64, HBITMAP *))(*(_QWORD *)v24 + 56LL))(v24, a4);
        v16 = v24;
        if ( v24 )
        {
          v24 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
      }
    }
    v17 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    if ( hObject[1] )
      CloseHandle(hObject[1]);
    SysFreeString((BSTR)hObject[0]);
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&pv);
  }
  return (unsigned int)ThumbnailFromCache;
}

```

## disassembly

```asm
0x180013a70  mov     [rsp-8+arg_8], rbx
0x180013a75  push    rbp
0x180013a76  push    rsi
0x180013a77  push    rdi
0x180013a78  push    r12
0x180013a7a  push    r13
0x180013a7c  push    r14
0x180013a7e  push    r15
0x180013a80  lea     rbp, [rsp-27h]
0x180013a85  sub     rsp, 0B0h
0x180013a8c  mov     rax, cs:__security_cookie
0x180013a93  xor     rax, rsp
0x180013a96  mov     [rbp+57h+var_40], rax
0x180013a9a  mov     r14, r9
0x180013a9d  mov     esi, r8d
0x180013aa0  mov     r12, rdx
0x180013aa3  mov     r15, rcx
0x180013aa6  xor     r13d, r13d
0x180013aa9  mov     [r9], r13
0x180013aac  mov     ecx, r8d; unsigned int
0x180013aaf  call    ?_ValidateSize@@YAJI@Z; _ValidateSize(uint)
0x180013ab4  mov     ebx, eax
0x180013ab6  test    eax, eax
0x180013ab8  js      loc_180013C8C
0x180013abe  lea     rdi, [r15-20h]
0x180013ac2  mov     rcx, rdi; this
0x180013ac5  call    ?_ValidateCallingThread@CThumbnailCache@@AEAAJXZ; CThumbnailCache::_ValidateCallingThread(void)
0x180013aca  mov     ebx, eax
0x180013acc  test    eax, eax
0x180013ace  js      loc_180013C8C
0x180013ad4  cmp     [rdi+2F4h], r13b
0x180013adb  jz      loc_180013CB5
0x180013ae1  cmp     [rdi+2F5h], r13b
0x180013ae8  jz      loc_180013CF3
0x180013aee  mov     rcx, rdi; this
0x180013af1  cmp     [rdi+2F6h], r13b
0x180013af8  jnz     loc_180013D15
0x180013afe  call    ?ResetCache@CThumbnailCache@@AEAAJXZ; CThumbnailCache::ResetCache(void)
0x180013b03  mov     ebx, eax
0x180013b05  test    eax, eax
0x180013b07  js      loc_180013D2B
0x180013b0d  mov     ebx, r13d
0x180013b10  test    ebx, ebx
0x180013b12  js      loc_180013C8C
0x180013b18  mov     eax, [r15+2E0h]
0x180013b1f  and     eax, 1
0x180013b22  mov     [rbp+57h+var_48], eax
0x180013b25  mov     [rbp+57h+var_60], r13
0x180013b29  mov     [rbp+57h+pv], r13
0x180013b2d  xor     ecx, ecx; pv
0x180013b2f  call    cs:__imp_CoTaskMemFree
0x180013b35  mov     [rbp+57h+var_44], r13d
0x180013b39  mov     [rbp+57h+var_58], r13
0x180013b3d  mov     rcx, [rbp+57h+pv]; pv
0x180013b41  mov     [rbp+57h+pv], r13
0x180013b45  call    cs:__imp_CoTaskMemFree
0x180013b4b  mov     rcx, [rbp+57h+pv]; pv
0x180013b4f  mov     [rbp+57h+pv], r13
0x180013b53  call    cs:__imp_CoTaskMemFree
0x180013b59  mov     [rbp+57h+pv], r13
0x180013b5d  mov     [rbp+57h+var_44], r13d
0x180013b61  mov     rax, [r12]
0x180013b65  mov     [rbp+57h+var_60], rax
0x180013b69  mov     dword ptr [rbp+57h+var_58], r13d
0x180013b6d  mov     dword ptr [rbp+57h+var_58+4], 11h
0x180013b74  xorps   xmm0, xmm0
0x180013b77  movdqu  xmmword ptr [rbp+57h+hObject], xmm0
0x180013b7c  mov     [rbp+57h+var_78], r13d
0x180013b80  mov     [rbp+57h+var_90], r13d
0x180013b84  mov     dword ptr [rbp+57h+var_70], r13d
0x180013b88  mov     [rbp+57h+var_68], r13
0x180013b8c  lea     rcx, [rbp+57h+var_68]
0x180013b90  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013b95  lea     rax, [rbp+57h+var_68]
0x180013b99  mov     [rsp+0E0h+var_A0], rax
0x180013b9e  lea     rax, _GUID_b11c5842_71c1_4cef_be46_1203d5fdb22f
0x180013ba5  mov     [rsp+0E0h+var_A8], rax
0x180013baa  lea     rax, [rbp+57h+var_70]
0x180013bae  mov     [rsp+0E0h+var_B0], rax
0x180013bb3  lea     rax, [rbp+57h+var_90]
0x180013bb7  mov     [rsp+0E0h+var_B8], rax
0x180013bbc  lea     rax, [rbp+57h+hObject]
0x180013bc0  mov     [rsp+0E0h+var_C0], rax
0x180013bc5  xor     r9d, r9d
0x180013bc8  mov     r8d, esi
0x180013bcb  lea     rdx, [rbp+57h+var_60]
0x180013bcf  mov     rcx, rdi
0x180013bd2  call    ?_TryGetThumbnailFromCache@CThumbnailCache@@AEAAJAEAVCThumbnailMoniker@@IW4GFC_FLAGS@@PEAVCGlobalRefCount@@PEAHPEAW4WTS_ALPHATYPE@@AEBU_GUID@@PEAPEAX@Z; CThumbnailCache::_TryGetThumbnailFromCache(CThumbnailMoniker &,uint,GFC_FLAGS,CGlobalRefCount *,int *,WTS_ALPHATYPE *,_GUID const &,void * *)
0x180013bd7  mov     ebx, eax
0x180013bd9  test    eax, eax
0x180013bdb  js      short loc_180013C4F
0x180013bdd  cmp     [rbp+57h+var_90], r13d
0x180013be1  jnz     loc_180013CE9
0x180013be7  mov     [rbp+57h+var_70], r13
0x180013beb  mov     rdi, [rbp+57h+var_68]
0x180013bef  mov     rax, [rdi]
0x180013bf2  mov     rbx, [rax+30h]
0x180013bf6  lea     rcx, [rbp+57h+var_70]
0x180013bfa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013bff  lea     r9, [rbp+57h+var_70]
0x180013c03  lea     r8, _GUID_091162a4_bc96_411f_aae8_c5122cd03363
0x180013c0a  mov     edx, 2
0x180013c0f  mov     rcx, rdi
0x180013c12  mov     rax, rbx
0x180013c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c1a  mov     ebx, eax
0x180013c1c  test    eax, eax
0x180013c1e  js      short loc_180013C35
0x180013c20  mov     rcx, [rbp+57h+var_70]
0x180013c24  mov     rax, [rcx]
0x180013c27  mov     rdx, r14
0x180013c2a  mov     rax, [rax+38h]
0x180013c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c33  mov     ebx, eax
0x180013c35  mov     rcx, [rbp+57h+var_70]
0x180013c39  test    rcx, rcx
0x180013c3c  jz      short loc_180013C4F
0x180013c3e  mov     [rbp+57h+var_70], r13
0x180013c42  mov     rax, [rcx]
0x180013c45  mov     rax, [rax+10h]
0x180013c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c4e  nop
0x180013c4f  mov     rcx, [rbp+57h+var_68]
0x180013c53  test    rcx, rcx
0x180013c56  jz      short loc_180013C69
0x180013c58  mov     [rbp+57h+var_68], r13
0x180013c5c  mov     rax, [rcx]
0x180013c5f  mov     rax, [rax+10h]
0x180013c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c68  nop
0x180013c69  mov     rcx, [rbp+57h+hObject+8]; hObject
0x180013c6d  test    rcx, rcx
0x180013c70  jz      short loc_180013C78
0x180013c72  call    cs:__imp_CloseHandle
0x180013c78  mov     rcx, [rbp+57h+hObject]; bstrString
0x180013c7c  call    cs:__imp_SysFreeString
0x180013c82  nop
0x180013c83  lea     rcx, [rbp+57h+pv]
0x180013c87  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180013c8c  mov     eax, ebx
0x180013c8e  mov     rcx, [rbp+57h+var_40]
0x180013c92  xor     rcx, rsp; StackCookie
0x180013c95  call    __security_check_cookie
0x180013c9a  mov     rbx, [rsp+0E0h+arg_8]
0x180013ca2  add     rsp, 0B0h
0x180013ca9  pop     r15
0x180013cab  pop     r14
0x180013cad  pop     r13
0x180013caf  pop     r12
0x180013cb1  pop     rdi
0x180013cb2  pop     rsi
0x180013cb3  pop     rbp
0x180013cb4  retn
0x180013cb5  mov     r8d, esi; int
0x180013cb8  xor     edx, edx; enum WTS_FLAGS
0x180013cba  mov     rcx, rdi; this
0x180013cbd  call    ?AttemptInitialize@CThumbnailCache@@AEAAJW4WTS_FLAGS@@H@Z; CThumbnailCache::AttemptInitialize(WTS_FLAGS,int)
0x180013cc2  mov     ebx, eax
0x180013cc4  test    eax, eax
0x180013cc6  jns     loc_180013B0D
0x180013ccc  mov     edx, 737h; void *
0x180013cd1  mov     rcx, [rbp+5Fh]; this
0x180013cd5  mov     r9d, eax; char *
0x180013cd8  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180013cdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013ce4  jmp     loc_180013B10
0x180013ce9  mov     ebx, 80004005h
0x180013cee  jmp     loc_180013C4F
0x180013cf3  mov     rcx, [rbp+5Fh]; this
0x180013cf7  mov     ebx, 8000FFFFh
0x180013cfc  mov     r9d, ebx; char *
0x180013cff  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180013d06  mov     edx, 733h; void *
0x180013d0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013d10  jmp     loc_180013C8C
0x180013d15  call    ?ResetDestroyedCache@CThumbnailCache@@AEAAJXZ; CThumbnailCache::ResetDestroyedCache(void)
0x180013d1a  mov     ebx, eax
0x180013d1c  test    eax, eax
0x180013d1e  jns     loc_180013B0D
0x180013d24  mov     edx, 73Bh
0x180013d29  jmp     short loc_180013CD1
0x180013d2b  mov     edx, 73Fh
0x180013d30  jmp     short loc_180013CD1
```
