# TryGetAdjustedImage(uint,AI_FLAGS,bool,IBitmapResult *,IBitmapResult * *)

- ea: `0x180007390`
- end: `0x1800078bb`
- name: `?TryGetAdjustedImage@@YAJIW4AI_FLAGS@@_NPEAUIBitmapResult@@PEAPEAU2@@Z`
- size: `1323`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006c94`
- `0x1800130d0`
- `0x180013d80`
- `0x18001c6f0`

## callees

- `0x180003624`
- `0x180006f4c`
- `0x1800071ac`
- `0x180007390`
- `0x18000bfd8`
- `0x1800291d4`
- `0x180034f94`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007566`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007566`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007486`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007486`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800075a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000768b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000776e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800075a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000768b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000776e`

## string_xrefs

- `0x180007670`: `onecoreuap\shell\ext\thumbnailcache\common\extract.cpp`
- `0x1800076f9`: `onecoreuap\shell\ext\thumbnailcache\common\extract.cpp`
- `0x180007713`: `onecoreuap\shell\ext\thumbnailcache\common\extract.cpp`
- `0x180007753`: `onecoreuap\shell\ext\thumbnailcache\common\extract.cpp`
- `0x1800077da`: `onecoreuap\shell\ext\thumbnailcache\common\extract.cpp`
- `0x18000785e`: `onecoreuap\shell\ext\thumbnailcache\common\extract.cpp`
- `0x18000787d`: `onecoreuap\shell\ext\thumbnailcache\common\extract.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall TryGetAdjustedImage(unsigned int a1, char a2, char a3, __int64 a4, struct _GUID *a5)
{
  int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  signed int v12; // eax
  unsigned int v13; // ecx
  unsigned int v14; // esi
  HRESULT v15; // eax
  __int64 (__fastcall *v16)(__int64, __int64, GUID *, __int64 *); // rbx
  int v17; // eax
  int v18; // eax
  int v19; // eax
  const WCHAR *v20; // rdi
  wchar_t **i; // rbx
  const struct _GUID *v22; // r8
  const struct tagSIZE *v23; // r9
  int BitmapResult; // eax
  Windows::Internal::Thumbnails *v25; // rcx
  __int64 v26; // rcx
  LPVOID v27; // rcx
  Windows::Internal::Thumbnails *v29; // rcx
  __int64 v30; // rcx
  LPVOID v31; // rcx
  LPVOID v32; // rcx
  Windows::Internal::Thumbnails *v33; // rcx
  __int64 v34; // rcx
  LPVOID v35; // rcx
  __int64 v36; // rcx
  LPVOID v37; // rcx
  unsigned int WideThumbnailHeightFromWidth; // edx
  int ppv; // [rsp+20h] [rbp-60h]
  int ppva; // [rsp+20h] [rbp-60h]
  Windows::Internal::Thumbnails **ppvb; // [rsp+20h] [rbp-60h]
  int ppvc; // [rsp+20h] [rbp-60h]
  Windows::Internal::Thumbnails *v43; // [rsp+30h] [rbp-50h] BYREF
  LPVOID v44; // [rsp+38h] [rbp-48h] BYREF
  __int64 v45; // [rsp+40h] [rbp-40h] BYREF
  __int64 v46; // [rsp+48h] [rbp-38h] BYREF
  LPCWCH lpString2; // [rsp+50h] [rbp-30h] BYREF
  __int64 v48; // [rsp+58h] [rbp-28h]
  __int64 v49; // [rsp+60h] [rbp-20h]
  struct IWICBitmapSource v50[2]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  *(_QWORD *)&a5->Data1 = 0;
  v46 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a4 + 72LL))(a4, &v46);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\common\\extract.cpp",
      (const char *)(unsigned int)v9,
      ppv);
  }
  else
  {
    v11 = 0;
    v12 = v46;
    v13 = HIDWORD(v46);
    if ( (a2 & 1) != 0 )
      v11 = v46 != HIDWORD(v46);
    if ( (a2 & 8) != 0 )
    {
      WideThumbnailHeightFromWidth = GetWideThumbnailHeightFromWidth(a1);
      v13 = HIDWORD(v46);
      v12 = v46;
      if ( v46 != __PAIR64__(WideThumbnailHeightFromWidth, a1) )
        v11 |= 4u;
    }
    if ( (a2 & 2) != 0 || (a2 & 4) != 0 )
    {
      if ( (v11 & 1) != 0 )
      {
        if ( v12 < (int)v13 )
          v13 = v12;
      }
      else if ( v12 > (int)v13 )
      {
        v13 = v12;
      }
      if ( (a2 & 2) != 0 && v13 > a1 || (a2 & 4) != 0 && v13 < a1 )
        v11 |= 2u;
    }
    v14 = v11 | 8;
    if ( (a2 & 0x10) == 0 )
      v14 = v11;
    if ( !v14 && !a3 )
      return 0;
    v44 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
    v15 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &v44);
    v10 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\common\\extract.cpp",
        (const char *)(unsigned int)v15,
        ppva);
      v32 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 16LL))(v32);
      }
    }
    else
    {
      v45 = 0;
      v16 = *(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)a4 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
      v17 = v16(a4, 1, &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94, &v45);
      v10 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5A,
          (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\common\\extract.cpp",
          (const char *)(unsigned int)v17,
          ppva);
        v36 = v45;
        if ( v45 )
        {
          v45 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        }
        v37 = v44;
        if ( v44 )
        {
          v44 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v37 + 16LL))(v37);
        }
      }
      else
      {
        v43 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        ppvb = &v43;
        v18 = PostProcessImageWithWIC(v44, v45, v14, a1);
        v10 = v18;
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5D,
            (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\common\\extract.cpp",
            (const char *)(unsigned int)v18,
            (int)&v43);
LABEL_75:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
        }
        else
        {
          lpString2 = 0;
          v48 = -1;
          v49 = -1;
          v19 = (*(__int64 (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)a4 + 80LL))(a4, &lpString2);
          v10 = v19;
          if ( v19 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x60,
              (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\common\\extract.cpp",
              (const char *)(unsigned int)v19,
              (int)&v43);
            if ( lpString2 )
            {
              CoTaskMemFree((LPVOID)lpString2);
              lpString2 = 0;
            }
            v48 = 0;
            v49 = 0;
            v29 = v43;
            if ( v43 )
            {
              v43 = 0;
              (*(void (__fastcall **)(Windows::Internal::Thumbnails *))(*(_QWORD *)v29 + 16LL))(v29);
            }
            v30 = v45;
            if ( v45 )
            {
              v45 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
            }
            v31 = v44;
            if ( v44 )
            {
              v44 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
            }
          }
          else
          {
            v20 = lpString2;
            *(GUID *)&v50[0].lpVtbl = GUID_NULL;
            for ( i = &off_18004B150; ; i += 3 )
            {
              if ( i == (wchar_t **)off_18004B210 )
              {
                v10 = -2147023728;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x63,
                  (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\common\\extract.cpp",
                  (const char *)0x80070490LL,
                  (int)ppvb);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2);
                goto LABEL_75;
              }
              if ( CompareStringOrdinal(*i, -1, v20, -1, 1) == 2 )
                break;
            }
            *(_OWORD *)&v50[0].lpVtbl = *(_OWORD *)i[2];
            BitmapResult = Windows::Internal::Thumbnails::CreateBitmapResult(
                             v43,
                             v50,
                             v22,
                             v23,
                             (const int *)ppvb,
                             a5,
                             (void **)v43);
            v10 = BitmapResult;
            if ( BitmapResult >= 0 )
            {
              if ( lpString2 )
              {
                CoTaskMemFree((LPVOID)lpString2);
                lpString2 = 0;
              }
              v48 = 0;
              v49 = 0;
              v25 = v43;
              if ( v43 )
              {
                v43 = 0;
                (*(void (__fastcall **)(Windows::Internal::Thumbnails *))(*(_QWORD *)v25 + 16LL))(v25);
              }
              v26 = v45;
              if ( v45 )
              {
                v45 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
              }
              v27 = v44;
              if ( v44 )
              {
                v44 = 0;
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
              }
              return 0;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x64,
              (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\common\\extract.cpp",
              (const char *)(unsigned int)BitmapResult,
              ppvc);
            if ( lpString2 )
            {
              CoTaskMemFree((LPVOID)lpString2);
              lpString2 = 0;
            }
            v48 = 0;
            v49 = 0;
            v33 = v43;
            if ( v43 )
            {
              v43 = 0;
              (*(void (__fastcall **)(Windows::Internal::Thumbnails *))(*(_QWORD *)v33 + 16LL))(v33);
            }
            v34 = v45;
            if ( v45 )
            {
              v45 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
            }
            v35 = v44;
            if ( v44 )
            {
              v44 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v35 + 16LL))(v35);
            }
          }
        }
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180007390  mov     [rsp-38h+arg_8], rbx
0x180007395  push    rbp
0x180007396  push    rsi
0x180007397  push    rdi
0x180007398  push    r12
0x18000739a  push    r13
0x18000739c  push    r14
0x18000739e  push    r15
0x1800073a0  mov     rbp, rsp
0x1800073a3  sub     rsp, 80h
0x1800073aa  mov     rax, cs:__security_cookie
0x1800073b1  xor     rax, rsp
0x1800073b4  mov     [rbp+var_8], rax
0x1800073b8  mov     r15, r9
0x1800073bb  mov     r12b, r8b
0x1800073be  mov     edi, edx
0x1800073c0  mov     r14d, ecx
0x1800073c3  mov     r13, [rbp+arg_20]
0x1800073c7  mov     qword ptr [r13+0], 0
0x1800073cf  mov     [rbp+var_38], 0
0x1800073d7  mov     rax, [r9]
0x1800073da  lea     rdx, [rbp+var_38]
0x1800073de  mov     rcx, r9
0x1800073e1  mov     rax, [rax+48h]
0x1800073e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073ea  mov     ebx, eax
0x1800073ec  test    eax, eax
0x1800073ee  js      loc_1800076F2
0x1800073f4  xor     ebx, ebx
0x1800073f6  mov     rax, [rbp+var_38]
0x1800073fa  mov     ecx, dword ptr [rbp+var_38+4]
0x1800073fd  lea     r8d, [rbx+1]
0x180007401  test    r8b, dil
0x180007404  jnz     loc_180007741
0x18000740a  test    dil, 8
0x18000740e  jnz     loc_180007825
0x180007414  mov     edx, edi
0x180007416  and     edx, 2
0x180007419  jz      loc_180007651
0x18000741f  test    r8b, bl
0x180007422  jnz     loc_18000784D
0x180007428  cmp     eax, ecx
0x18000742a  cmovg   ecx, eax
0x18000742d  test    edx, edx
0x18000742f  jz      loc_180007639
0x180007435  cmp     ecx, r14d
0x180007438  jbe     loc_180007639
0x18000743e  or      ebx, 2
0x180007441  mov     esi, ebx
0x180007443  or      esi, 8
0x180007446  test    dil, 10h
0x18000744a  cmovz   esi, ebx
0x18000744d  test    esi, esi
0x18000744f  jz      loc_18000762F
0x180007455  xor     r12d, r12d
0x180007458  mov     [rbp+var_48], r12
0x18000745c  lea     rcx, [rbp+var_48]
0x180007460  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007465  lea     rax, [rbp+var_48]
0x180007469  mov     [rsp+80h+ppv], rax; int
0x18000746e  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180007475  lea     edi, [r12+1]
0x18000747a  mov     r8d, edi; dwClsContext
0x18000747d  xor     edx, edx; pUnkOuter
0x18000747f  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180007486  call    cs:__imp_CoCreateInstance
0x18000748c  mov     ebx, eax
0x18000748e  test    eax, eax
0x180007490  js      loc_18000770C
0x180007496  mov     [rbp+var_40], r12
0x18000749a  mov     rax, [r15]
0x18000749d  mov     rbx, [rax+30h]
0x1800074a1  lea     rcx, [rbp+var_40]
0x1800074a5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800074aa  lea     r9, [rbp+var_40]
0x1800074ae  lea     r8, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x1800074b5  mov     edx, edi
0x1800074b7  mov     rcx, r15
0x1800074ba  mov     rax, rbx
0x1800074bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074c2  mov     ebx, eax
0x1800074c4  test    eax, eax
0x1800074c6  js      loc_1800077D3
0x1800074cc  mov     [rbp+var_50], r12
0x1800074d0  lea     rcx, [rbp+var_50]
0x1800074d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800074d9  lea     rax, [rbp+var_50]
0x1800074dd  mov     [rsp+80h+ppv], rax; int
0x1800074e2  mov     r9d, r14d
0x1800074e5  mov     r8d, esi
0x1800074e8  mov     rdx, [rbp+var_40]
0x1800074ec  mov     rcx, [rbp+var_48]
0x1800074f0  call    ?PostProcessImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@W4WICPOSTPROCESS_FLAGS@@IPEAPEAU2@@Z; PostProcessImageWithWIC(IWICImagingFactory *,IWICBitmapSource *,WICPOSTPROCESS_FLAGS,uint,IWICBitmapSource * *)
0x1800074f5  mov     ebx, eax
0x1800074f7  test    eax, eax
0x1800074f9  js      loc_180007857
0x1800074ff  mov     [rbp+lpString2], r12
0x180007503  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007507  mov     [rbp+var_28], rsi
0x18000750b  mov     [rbp+var_20], rsi
0x18000750f  mov     rax, [r15]
0x180007512  lea     rdx, [rbp+lpString2]
0x180007516  mov     rcx, r15
0x180007519  mov     rax, [rax+50h]
0x18000751d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007522  mov     ebx, eax
0x180007524  test    eax, eax
0x180007526  js      loc_180007669
0x18000752c  mov     rdi, [rbp+lpString2]
0x180007530  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180007537  movdqu  xmmword ptr [rbp+var_18.lpVtbl], xmm0
0x18000753c  lea     rbx, off_18004B150; "image/jpeg"
0x180007543  lea     rax, off_18004B210
0x18000754a  cmp     rbx, rax
0x18000754d  jz      loc_180007871
0x180007553  mov     dword ptr [rsp+80h+ppv], 1; int
0x18000755b  mov     r9d, esi; cchCount2
0x18000755e  mov     r8, rdi; lpString2
0x180007561  mov     edx, esi; cchCount1
0x180007563  mov     rcx, [rbx]; lpString1
0x180007566  call    cs:__imp_CompareStringOrdinal
0x18000756c  cmp     eax, 2
0x18000756f  jnz     loc_180007660
0x180007575  mov     rax, [rbx+10h]
0x180007579  movups  xmm0, xmmword ptr [rax]
0x18000757c  movdqu  xmmword ptr [rbp+var_18.lpVtbl], xmm0
0x180007581  mov     [rsp+80h+var_58], r13; struct _GUID *
0x180007586  lea     rdx, [rbp+var_18]; struct IWICBitmapSource *
0x18000758a  mov     rcx, [rbp+var_50]; this
0x18000758e  call    ?CreateBitmapResult@Thumbnails@Internal@Windows@@YAJPEAUIWICBitmapSource@@AEBU_GUID@@PEBUtagSIZE@@PEBH1PEAPEAX@Z; Windows::Internal::Thumbnails::CreateBitmapResult(IWICBitmapSource *,_GUID const &,tagSIZE const *,int const *,_GUID const &,void * *)
0x180007593  mov     ebx, eax
0x180007595  test    eax, eax
0x180007597  js      loc_18000774C
0x18000759d  mov     rcx, [rbp+lpString2]; pv
0x1800075a1  test    rcx, rcx
0x1800075a4  jz      short loc_1800075B0
0x1800075a6  call    cs:__imp_CoTaskMemFree
0x1800075ac  mov     [rbp+lpString2], r12
0x1800075b0  mov     [rbp+var_28], r12
0x1800075b4  mov     [rbp+var_20], r12
0x1800075b8  mov     rcx, [rbp+var_50]
0x1800075bc  test    rcx, rcx
0x1800075bf  jz      short loc_1800075D2
0x1800075c1  mov     [rbp+var_50], r12
0x1800075c5  mov     rax, [rcx]
0x1800075c8  mov     rax, [rax+10h]
0x1800075cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075d1  nop
0x1800075d2  mov     rcx, [rbp+var_40]
0x1800075d6  test    rcx, rcx
0x1800075d9  jz      short loc_1800075EC
0x1800075db  mov     [rbp+var_40], r12
0x1800075df  mov     rax, [rcx]
0x1800075e2  mov     rax, [rax+10h]
0x1800075e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075eb  nop
0x1800075ec  mov     rcx, [rbp+var_48]
0x1800075f0  test    rcx, rcx
0x1800075f3  jz      short loc_180007606
0x1800075f5  mov     [rbp+var_48], r12
0x1800075f9  mov     rax, [rcx]
0x1800075fc  mov     rax, [rax+10h]
0x180007600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007605  nop
0x180007606  xor     eax, eax
0x180007608  mov     rcx, [rbp+var_8]
0x18000760c  xor     rcx, rsp; StackCookie
0x18000760f  call    __security_check_cookie
0x180007614  mov     rbx, [rsp+80h+arg_8]
0x18000761c  add     rsp, 80h
0x180007623  pop     r15
0x180007625  pop     r14
0x180007627  pop     r13
0x180007629  pop     r12
0x18000762b  pop     rdi
0x18000762c  pop     rsi
0x18000762d  pop     rbp
0x18000762e  retn
0x18000762f  test    r12b, r12b
0x180007632  jz      short loc_180007606
0x180007634  jmp     loc_180007455
0x180007639  test    dil, 4
0x18000763d  jz      loc_180007441
0x180007643  cmp     ecx, r14d
0x180007646  jnb     loc_180007441
0x18000764c  jmp     loc_18000743E
0x180007651  test    dil, 4
0x180007655  jz      loc_180007441
0x18000765b  jmp     loc_18000741F
0x180007660  add     rbx, 18h
0x180007664  jmp     loc_180007543
0x180007669  mov     rcx, [rbp+38h]; this
0x18000766d  mov     r9d, ebx; char *
0x180007670  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180007677  mov     edx, 60h ; '`'; void *
0x18000767c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007681  nop
0x180007682  mov     rcx, [rbp+lpString2]; pv
0x180007686  test    rcx, rcx
0x180007689  jz      short loc_180007695
0x18000768b  call    cs:__imp_CoTaskMemFree
0x180007691  mov     [rbp+lpString2], r12
0x180007695  mov     [rbp+var_28], r12
0x180007699  mov     [rbp+var_20], r12
0x18000769d  mov     rcx, [rbp+var_50]
0x1800076a1  test    rcx, rcx
0x1800076a4  jz      short loc_1800076B7
0x1800076a6  mov     [rbp+var_50], r12
0x1800076aa  mov     rax, [rcx]
0x1800076ad  mov     rax, [rax+10h]
0x1800076b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076b6  nop
0x1800076b7  mov     rcx, [rbp+var_40]
0x1800076bb  test    rcx, rcx
0x1800076be  jz      short loc_1800076D1
0x1800076c0  mov     [rbp+var_40], r12
0x1800076c4  mov     rax, [rcx]
0x1800076c7  mov     rax, [rax+10h]
0x1800076cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076d0  nop
0x1800076d1  mov     rcx, [rbp+var_48]
0x1800076d5  test    rcx, rcx
0x1800076d8  jz      short loc_1800076EB
0x1800076da  mov     [rbp+var_48], r12
0x1800076de  mov     rax, [rcx]
0x1800076e1  mov     rax, [rax+10h]
0x1800076e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076ea  nop
0x1800076eb  mov     eax, ebx
0x1800076ed  jmp     loc_180007608
0x1800076f2  mov     rcx, [rbp+38h]; this
0x1800076f6  mov     r9d, ebx; char *
0x1800076f9  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180007700  mov     edx, 51h ; 'Q'; void *
0x180007705  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000770a  jmp     short loc_1800076EB
0x18000770c  mov     rcx, [rbp+38h]; this
0x180007710  mov     r9d, ebx; char *
0x180007713  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18000771a  mov     edx, 57h ; 'W'; void *
0x18000771f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007724  nop
0x180007725  mov     rcx, [rbp+var_48]
0x180007729  test    rcx, rcx
0x18000772c  jz      short loc_18000773F
0x18000772e  mov     [rbp+var_48], r12
0x180007732  mov     rax, [rcx]
0x180007735  mov     rax, [rax+10h]
0x180007739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000773e  nop
0x18000773f  jmp     short loc_1800076EB
0x180007741  cmp     eax, ecx
0x180007743  cmovnz  ebx, r8d
0x180007747  jmp     loc_18000740A
0x18000774c  mov     rcx, [rbp+38h]; this
0x180007750  mov     r9d, ebx; char *
0x180007753  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18000775a  mov     edx, 64h ; 'd'; void *
0x18000775f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007764  nop
0x180007765  mov     rcx, [rbp+lpString2]; pv
0x180007769  test    rcx, rcx
0x18000776c  jz      short loc_180007778
0x18000776e  call    cs:__imp_CoTaskMemFree
0x180007774  mov     [rbp+lpString2], r12
0x180007778  mov     [rbp+var_28], r12
0x18000777c  mov     [rbp+var_20], r12
0x180007780  mov     rcx, [rbp+var_50]
0x180007784  test    rcx, rcx
0x180007787  jz      short loc_18000779A
0x180007789  mov     [rbp+var_50], r12
0x18000778d  mov     rax, [rcx]
0x180007790  mov     rax, [rax+10h]
0x180007794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007799  nop
0x18000779a  mov     rcx, [rbp+var_40]
0x18000779e  test    rcx, rcx
0x1800077a1  jz      short loc_1800077B4
0x1800077a3  mov     [rbp+var_40], r12
0x1800077a7  mov     rax, [rcx]
0x1800077aa  mov     rax, [rax+10h]
0x1800077ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077b3  nop
0x1800077b4  mov     rcx, [rbp+var_48]
0x1800077b8  test    rcx, rcx
0x1800077bb  jz      short loc_1800077CE
0x1800077bd  mov     [rbp+var_48], r12
0x1800077c1  mov     rax, [rcx]
0x1800077c4  mov     rax, [rax+10h]
0x1800077c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077cd  nop
0x1800077ce  jmp     loc_1800076EB
0x1800077d3  mov     rcx, [rbp+38h]; this
0x1800077d7  mov     r9d, ebx; char *
0x1800077da  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x1800077e1  mov     edx, 5Ah ; 'Z'; void *
0x1800077e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077eb  nop
0x1800077ec  mov     rcx, [rbp+var_40]
0x1800077f0  test    rcx, rcx
  ... truncated ...
```
