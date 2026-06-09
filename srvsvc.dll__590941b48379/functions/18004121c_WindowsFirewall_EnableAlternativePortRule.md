# WindowsFirewall_EnableAlternativePortRule

- ea: `0x18004121c`
- end: `0x1800415be`
- name: `WindowsFirewall_EnableAlternativePortRule`
- size: `930`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020ae0`

## callees

- `0x1800119e0`
- `0x180012914`
- `0x18001deb0`
- `0x18003c6f0`
- `0x18003e3f4`
- `0x18004121c`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800412da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800414c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800414e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041544`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041559`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800412da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800414c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800414e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041544`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041559`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800412e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800414d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800414ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041553`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041567`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800412e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800414d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800414ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041553`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041567`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180041353`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180041353`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041389`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041400`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041389`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041400`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800414f9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800414f9`
- `OLEAUT32!__imp_SysFreeString` at `0x180041503`
- `OLEAUT32!__imp_SysFreeString` at `0x18004150c`
- `OLEAUT32!__imp_SysFreeString` at `0x180041516`
- `OLEAUT32!__imp_SysFreeString` at `0x180041571`
- `OLEAUT32!__imp_SysFreeString` at `0x180041503`
- `OLEAUT32!__imp_SysFreeString` at `0x18004150c`
- `OLEAUT32!__imp_SysFreeString` at `0x180041516`
- `OLEAUT32!__imp_SysFreeString` at `0x180041571`

## pseudocode

```c
__int64 __fastcall WindowsFirewall_EnableAlternativePortRule(unsigned __int16 a1, unsigned int a2, _DWORD *a3)
{
  int v3; // r14d
  unsigned int v4; // edi
  int ResourceString; // eax
  int v9; // eax
  HANDLE ProcessHeap; // rax
  BSTR v11; // rsi
  __int64 v12; // rbx
  HRESULT v13; // eax
  OLECHAR *v14; // rbx
  HRESULT v15; // edi
  HANDLE v16; // rax
  HANDLE v17; // rax
  HANDLE v18; // rax
  HANDLE v19; // rax
  LPVOID v20; // [rsp+30h] [rbp-59h] BYREF
  __int64 v21; // [rsp+38h] [rbp-51h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-49h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-41h] BYREF
  BSTR v24; // [rsp+50h] [rbp-39h] BYREF
  __int64 v25; // [rsp+58h] [rbp-31h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-29h] BYREF
  BSTR v27; // [rsp+68h] [rbp-21h] BYREF
  unsigned __int16 v28[8]; // [rsp+70h] [rbp-19h] BYREF
  __int128 v29; // [rsp+80h] [rbp-9h]
  __int128 v30; // [rsp+90h] [rbp+7h]
  __int64 v31; // [rsp+A0h] [rbp+17h]

  v3 = 0;
  v4 = a1;
  ppv = 0;
  v21 = 0;
  v20 = 0;
  v25 = 0;
  lpMem = 0;
  v24 = 0;
  *(_OWORD *)v28 = 0;
  v31 = 0;
  v29 = 0;
  v30 = 0;
  ResourceString = LoadResourceString(0x6Fu, (unsigned __int16 **)&lpMem);
  *a3 = ResourceString;
  if ( ResourceString )
    goto LABEL_2;
  v9 = LoadResourceString((unsigned int)(a2 != 6) + 112, &v24);
  *a3 = v9;
  if ( v9 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
LABEL_2:
    ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(&v25);
    ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>((__int64 *)&v20);
    ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(&v21);
    ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>((__int64 *)&ppv);
    return 2147500037LL;
  }
  v11 = v24;
  v12 = -1;
  do
    ++v12;
  while ( v24[v12] );
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v24, (const unsigned __int16 *)lpMem);
  if ( (unsigned int)swprintf_s<28>(v28, L"%s%d", v11, v4) - 1 > 0xFFFFFFFD )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, lpMem);
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v11);
    SysFreeString(v24);
    ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(&v25);
    ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>((__int64 *)&v20);
    ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(&v21);
    ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>((__int64 *)&ppv);
    return 2147549183LL;
  }
  else
  {
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v27, v28);
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, &v28[v12]);
    v13 = CoInitializeEx(0, 0);
    v14 = v27;
    v15 = v13;
    if ( v13 >= 0 )
    {
      v3 = 1;
      v15 = CoCreateInstance(
              &GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd,
              0,
              1u,
              &GUID_98325047_c671_4174_8d81_defcd3f03186,
              &ppv);
      if ( v15 >= 0 )
      {
        v15 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 144LL))(ppv, &v21);
        if ( v15 >= 0 )
        {
          v15 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v21 + 80LL))(v21, v14, &v25);
          if ( v15 < 0 )
          {
            v15 = CoCreateInstance(
                    &GUID_2c5bc43e_3369_4c33_ab0c_be9469677af4,
                    0,
                    1u,
                    &GUID_af230d27_baba_4e42_aced_f524f22cfce2,
                    &v20);
            if ( v15 >= 0 )
            {
              (*(void (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v20 + 64LL))(v20, v14);
              (*(void (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)v20 + 288LL))(v20, v24);
              (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v20 + 128LL))(v20, a2);
              (*(void (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)v20 + 144LL))(v20, bstrString);
              (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v20 + 224LL))(v20, 1);
              (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v20 + 336LL))(v20, 1);
              (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v20 + 272LL))(v20, 0xFFFFFFFFLL);
              v15 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v21 + 64LL))(v21, v20);
            }
          }
          else
          {
            *a3 = 183;
          }
        }
      }
    }
    if ( lpMem )
    {
      v16 = GetProcessHeap();
      HeapFree(v16, 0, lpMem);
    }
    if ( v11 )
    {
      v17 = GetProcessHeap();
      HeapFree(v17, 0, v11);
    }
    if ( v3 )
      CoUninitialize();
    SysFreeString(bstrString);
    SysFreeString(v14);
    SysFreeString(v24);
    ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(&v25);
    ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>((__int64 *)&v20);
    ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(&v21);
    ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>((__int64 *)&ppv);
    return (unsigned int)v15;
  }
}

```

## disassembly

```asm
0x18004121c  push    rbp
0x18004121e  push    rbx
0x18004121f  push    rsi
0x180041220  push    rdi
0x180041221  push    r12
0x180041223  push    r13
0x180041225  push    r14
0x180041227  lea     rbp, [rsp-27h]
0x18004122c  sub     rsp, 0B0h
0x180041233  mov     rax, cs:__security_cookie
0x18004123a  xor     rax, rsp
0x18004123d  mov     [rbp+57h+var_38], rax
0x180041241  xor     r14d, r14d
0x180041244  movzx   edi, cx
0x180041247  xorps   xmm0, xmm0
0x18004124a  mov     [rbp+57h+var_98], r14
0x18004124e  xor     eax, eax
0x180041250  mov     [rbp+57h+var_A8], r14
0x180041254  mov     r13d, edx
0x180041257  mov     [rbp+57h+var_B0], r14
0x18004125b  lea     rdx, [rbp+57h+lpMem]; unsigned __int16 **
0x18004125f  mov     [rbp+57h+var_88], r14
0x180041263  mov     r12, r8
0x180041266  mov     [rbp+57h+lpMem], r14
0x18004126a  lea     ecx, [rax+6Fh]; uID
0x18004126d  mov     [rbp+57h+var_90], r14
0x180041271  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180041275  mov     [rbp+57h+var_40], rax
0x180041279  movups  [rbp+57h+var_60], xmm0
0x18004127d  movups  [rbp+57h+var_50], xmm0
0x180041281  call    ?LoadResourceString@@YAKIPEAPEAG@Z; LoadResourceString(uint,ushort * *)
0x180041286  mov     [r12], eax
0x18004128a  test    eax, eax
0x18004128c  jz      short loc_1800412BC
0x18004128e  lea     rcx, [rbp+57h+var_88]
0x180041292  call    ??1?$CComPtrBase@UINetFwPolicy2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(void)
0x180041297  lea     rcx, [rbp+57h+var_B0]
0x18004129b  call    ??1?$CComPtrBase@UINetFwPolicy2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(void)
0x1800412a0  lea     rcx, [rbp+57h+var_A8]
0x1800412a4  call    ??1?$CComPtrBase@UINetFwPolicy2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(void)
0x1800412a9  lea     rcx, [rbp+57h+var_98]
0x1800412ad  call    ??1?$CComPtrBase@UINetFwPolicy2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(void)
0x1800412b2  mov     eax, 80004005h
0x1800412b7  jmp     loc_1800415A0
0x1800412bc  mov     ecx, r14d
0x1800412bf  lea     rdx, [rbp+57h+var_90]; unsigned __int16 **
0x1800412c3  cmp     r13d, 6
0x1800412c7  setnz   cl
0x1800412ca  add     ecx, 70h ; 'p'; uID
0x1800412cd  call    ?LoadResourceString@@YAKIPEAPEAG@Z; LoadResourceString(uint,ushort * *)
0x1800412d2  mov     [r12], eax
0x1800412d6  test    eax, eax
0x1800412d8  jz      short loc_1800412F1
0x1800412da  call    cs:__imp_GetProcessHeap
0x1800412e0  mov     r8, [rbp+57h+lpMem]; lpMem
0x1800412e4  xor     edx, edx; dwFlags
0x1800412e6  mov     rcx, rax; hHeap
0x1800412e9  call    cs:__imp_HeapFree
0x1800412ef  jmp     short loc_18004128E
0x1800412f1  mov     rsi, [rbp+57h+var_90]
0x1800412f5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800412f9  inc     rbx
0x1800412fc  cmp     [rsi+rbx*2], r14w
0x180041301  jnz     short loc_1800412F9
0x180041303  mov     rdx, [rbp+57h+lpMem]; unsigned __int16 *
0x180041307  lea     rcx, [rbp+57h+var_90]; this
0x18004130b  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180041310  mov     r9d, edi
0x180041313  lea     rdx, aSD; "%s%d"
0x18004131a  mov     r8, rsi
0x18004131d  lea     rcx, [rbp+57h+var_70]
0x180041321  call    ??$swprintf_s@$0BM@@@YAHAEAY0BM@GPEBGZZ; swprintf_s<28>(ushort (&)[28],ushort const *,...)
0x180041326  dec     eax
0x180041328  cmp     eax, 0FFFFFFFDh
0x18004132b  ja      loc_180041544
0x180041331  lea     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x180041335  lea     rcx, [rbp+57h+var_78]; this
0x180041339  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18004133e  lea     rdx, [rbp+57h+var_70]
0x180041342  lea     rdx, [rdx+rbx*2]; unsigned __int16 *
0x180041346  lea     rcx, [rbp+57h+bstrString]; this
0x18004134a  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18004134f  xor     edx, edx; dwCoInit
0x180041351  xor     ecx, ecx; pvReserved
0x180041353  call    cs:__imp_CoInitializeEx
0x180041359  mov     rbx, [rbp+57h+var_78]
0x18004135d  mov     edi, eax
0x18004135f  test    eax, eax
0x180041361  js      loc_1800414BF
0x180041367  lea     rax, [rbp+57h+var_98]
0x18004136b  mov     r14d, 1
0x180041371  mov     r8d, r14d; dwClsContext
0x180041374  mov     [rsp+0E0h+ppv], rax; ppv
0x180041379  lea     r9, _GUID_98325047_c671_4174_8d81_defcd3f03186; riid
0x180041380  xor     edx, edx; pUnkOuter
0x180041382  lea     rcx, _GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd; rclsid
0x180041389  call    cs:__imp_CoCreateInstance
0x18004138f  mov     edi, eax
0x180041391  test    eax, eax
0x180041393  js      loc_1800414BF
0x180041399  mov     rcx, [rbp+57h+var_98]
0x18004139d  lea     rdx, [rbp+57h+var_A8]
0x1800413a1  mov     rax, [rcx]
0x1800413a4  mov     rax, [rax+90h]
0x1800413ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413b0  mov     edi, eax
0x1800413b2  test    eax, eax
0x1800413b4  js      loc_1800414BF
0x1800413ba  mov     rcx, [rbp+57h+var_A8]
0x1800413be  lea     r8, [rbp+57h+var_88]
0x1800413c2  mov     rdx, rbx
0x1800413c5  mov     rax, [rcx]
0x1800413c8  mov     rax, [rax+50h]
0x1800413cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413d1  mov     edi, eax
0x1800413d3  test    eax, eax
0x1800413d5  js      short loc_1800413E4
0x1800413d7  mov     dword ptr [r12], 0B7h
0x1800413df  jmp     loc_1800414BF
0x1800413e4  lea     rax, [rbp+57h+var_B0]
0x1800413e8  mov     r8d, r14d; dwClsContext
0x1800413eb  lea     r9, _GUID_af230d27_baba_4e42_aced_f524f22cfce2; riid
0x1800413f2  mov     [rsp+0E0h+ppv], rax; ppv
0x1800413f7  xor     edx, edx; pUnkOuter
0x1800413f9  lea     rcx, _GUID_2c5bc43e_3369_4c33_ab0c_be9469677af4; rclsid
0x180041400  call    cs:__imp_CoCreateInstance
0x180041406  mov     edi, eax
0x180041408  test    eax, eax
0x18004140a  js      loc_1800414BF
0x180041410  mov     rcx, [rbp+57h+var_B0]
0x180041414  mov     rdx, rbx
0x180041417  mov     rax, [rcx]
0x18004141a  mov     rax, [rax+40h]
0x18004141e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041423  mov     rcx, [rbp+57h+var_B0]
0x180041427  mov     rdx, [rbp+57h+var_90]
0x18004142b  mov     rax, [rcx]
0x18004142e  mov     rax, [rax+120h]
0x180041435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004143a  mov     rcx, [rbp+57h+var_B0]
0x18004143e  mov     edx, r13d
0x180041441  mov     rax, [rcx]
0x180041444  mov     rax, [rax+80h]
0x18004144b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041450  mov     rcx, [rbp+57h+var_B0]
0x180041454  mov     rdx, [rbp+57h+bstrString]
0x180041458  mov     rax, [rcx]
0x18004145b  mov     rax, [rax+90h]
0x180041462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041467  mov     rcx, [rbp+57h+var_B0]
0x18004146b  mov     edx, r14d
0x18004146e  mov     rax, [rcx]
0x180041471  mov     rax, [rax+0E0h]
0x180041478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004147d  mov     rcx, [rbp+57h+var_B0]
0x180041481  mov     edx, r14d
0x180041484  mov     rax, [rcx]
0x180041487  mov     rax, [rax+150h]
0x18004148e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041493  mov     rcx, [rbp+57h+var_B0]
0x180041497  or      edx, 0FFFFFFFFh
0x18004149a  mov     rax, [rcx]
0x18004149d  mov     rax, [rax+110h]
0x1800414a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414a9  mov     rcx, [rbp+57h+var_A8]
0x1800414ad  mov     rdx, [rbp+57h+var_B0]
0x1800414b1  mov     rax, [rcx]
0x1800414b4  mov     rax, [rax+40h]
0x1800414b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414bd  mov     edi, eax
0x1800414bf  cmp     [rbp+57h+lpMem], 0
0x1800414c4  jz      short loc_1800414DB
0x1800414c6  call    cs:__imp_GetProcessHeap
0x1800414cc  mov     r8, [rbp+57h+lpMem]; lpMem
0x1800414d0  xor     edx, edx; dwFlags
0x1800414d2  mov     rcx, rax; hHeap
0x1800414d5  call    cs:__imp_HeapFree
0x1800414db  test    rsi, rsi
0x1800414de  jz      short loc_1800414F4
0x1800414e0  call    cs:__imp_GetProcessHeap
0x1800414e6  mov     r8, rsi; lpMem
0x1800414e9  xor     edx, edx; dwFlags
0x1800414eb  mov     rcx, rax; hHeap
0x1800414ee  call    cs:__imp_HeapFree
0x1800414f4  test    r14d, r14d
0x1800414f7  jz      short loc_1800414FF
0x1800414f9  call    cs:__imp_CoUninitialize
0x1800414ff  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180041503  call    cs:__imp_SysFreeString
0x180041509  mov     rcx, rbx; bstrString
0x18004150c  call    cs:__imp_SysFreeString
0x180041512  mov     rcx, [rbp+57h+var_90]; bstrString
0x180041516  call    cs:__imp_SysFreeString
0x18004151c  lea     rcx, [rbp+57h+var_88]
0x180041520  call    ??1?$CComPtrBase@UINetFwPolicy2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(void)
0x180041525  lea     rcx, [rbp+57h+var_B0]
0x180041529  call    ??1?$CComPtrBase@UINetFwPolicy2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(void)
0x18004152e  lea     rcx, [rbp+57h+var_A8]
0x180041532  call    ??1?$CComPtrBase@UINetFwPolicy2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(void)
0x180041537  lea     rcx, [rbp+57h+var_98]
0x18004153b  call    ??1?$CComPtrBase@UINetFwPolicy2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(void)
0x180041540  mov     eax, edi
0x180041542  jmp     short loc_1800415A0
0x180041544  call    cs:__imp_GetProcessHeap
0x18004154a  mov     r8, [rbp+57h+lpMem]; lpMem
0x18004154e  xor     edx, edx; dwFlags
0x180041550  mov     rcx, rax; hHeap
0x180041553  call    cs:__imp_HeapFree
0x180041559  call    cs:__imp_GetProcessHeap
0x18004155f  mov     r8, rsi; lpMem
0x180041562  xor     edx, edx; dwFlags
0x180041564  mov     rcx, rax; hHeap
0x180041567  call    cs:__imp_HeapFree
0x18004156d  mov     rcx, [rbp+57h+var_90]; bstrString
0x180041571  call    cs:__imp_SysFreeString
0x180041577  lea     rcx, [rbp+57h+var_88]
0x18004157b  call    ??1?$CComPtrBase@UINetFwPolicy2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(void)
0x180041580  lea     rcx, [rbp+57h+var_B0]
0x180041584  call    ??1?$CComPtrBase@UINetFwPolicy2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(void)
0x180041589  lea     rcx, [rbp+57h+var_A8]
0x18004158d  call    ??1?$CComPtrBase@UINetFwPolicy2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(void)
0x180041592  lea     rcx, [rbp+57h+var_98]
0x180041596  call    ??1?$CComPtrBase@UINetFwPolicy2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(void)
0x18004159b  mov     eax, 8000FFFFh
0x1800415a0  mov     rcx, [rbp+57h+var_38]
0x1800415a4  xor     rcx, rsp; StackCookie
0x1800415a7  call    __security_check_cookie
0x1800415ac  add     rsp, 0B0h
0x1800415b3  pop     r14
0x1800415b5  pop     r13
0x1800415b7  pop     r12
0x1800415b9  pop     rdi
0x1800415ba  pop     rsi
0x1800415bb  pop     rbx
0x1800415bc  pop     rbp
0x1800415bd  retn
```
