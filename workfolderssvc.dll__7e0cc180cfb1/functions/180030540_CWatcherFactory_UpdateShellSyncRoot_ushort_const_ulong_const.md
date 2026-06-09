# CWatcherFactory::UpdateShellSyncRoot(ushort const *,ulong const &)

- ea: `0x180030540`
- end: `0x18003093d`
- name: `?UpdateShellSyncRoot@CWatcherFactory@@UEAAXPEBGAEBK@Z`
- size: `1021`
- prototype: `void __fastcall(CWatcherFactory *__hidden this, const unsigned __int16 *, const unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003604`
- `0x180007e10`
- `0x180009158`
- `0x180011314`
- `0x18001133c`
- `0x18001137c`
- `0x180030540`
- `0x18013e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003063f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030698`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003063f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030698`

## string_xrefs

- `0x18003071e`: `@%systemroot%\system32\WorkfoldersControl.dll,-1`
- `0x180030766`: `%systemroot%\system32\WorkfoldersControl.dll,-1`
- `0x1800305b6`: `CWatcherFactory::UpdateShellSyncRoot`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CWatcherFactory::UpdateShellSyncRoot(
        CWatcherFactory *this,
        const unsigned __int16 *a2,
        const unsigned int *a3)
{
  _BYTE *v5; // rax
  char v6; // al
  unsigned int v7; // edi
  HRESULT v8; // eax
  HRESULT v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // [rsp+30h] [rbp-98h] BYREF
  int v15; // [rsp+34h] [rbp-94h]
  char v16; // [rsp+38h] [rbp-90h]
  const char *v17; // [rsp+40h] [rbp-88h]
  __int64 v18; // [rsp+48h] [rbp-80h]
  LPVOID v19; // [rsp+50h] [rbp-78h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-70h] BYREF
  int pExceptionObject; // [rsp+60h] [rbp-68h] BYREF
  int v22; // [rsp+64h] [rbp-64h]
  HRESULT v23; // [rsp+68h] [rbp-60h] BYREF
  HRESULT v24; // [rsp+6Ch] [rbp-5Ch] BYREF
  int v25; // [rsp+70h] [rbp-58h] BYREF
  int v26; // [rsp+74h] [rbp-54h] BYREF
  int v27; // [rsp+78h] [rbp-50h] BYREF
  int v28; // [rsp+7Ch] [rbp-4Ch] BYREF
  int v29; // [rsp+80h] [rbp-48h] BYREF
  int v30; // [rsp+84h] [rbp-44h] BYREF
  int v31; // [rsp+88h] [rbp-40h] BYREF
  const ATL::CAtlException *v32; // [rsp+90h] [rbp-38h] BYREF

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
  }
  if ( (v5[68] & 8) != 0 && v5[65] >= 6u )
  {
    v6 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v6 = 0;
LABEL_9:
  v14 = 0;
  v15 = 451;
  v16 = v6;
  v17 = "CWatcherFactory::UpdateShellSyncRoot";
  v18 = 0;
  if ( !a2 )
  {
    v14 = -2147024809;
    HIWORD(v15) = 453;
    pExceptionObject = -2147024809;
    throw (long *)&pExceptionObject;
  }
  v14 = 0;
  LOWORD(v15) = 453;
  try
  {
    v7 = 34;
    v22 = 34;
    if ( !*a3 )
      v7 = 98;
    v22 = v7;
    ppv = 0;
    v8 = CoCreateInstance(&CLSID_SyncRootManager, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &ppv);
    v14 = v8;
    if ( v8 < 0 )
    {
      HIWORD(v15) = 467;
      v23 = v8;
      throw (long *)&v23;
    }
    LOWORD(v15) = 467;
    v19 = 0;
    v9 = CoCreateInstance(&CLSID_StorageProviderInfo, 0, 1u, &GUID_ca01c124_2769_4576_bf12_8a54ee671a86, &v19);
    v14 = v9;
    if ( v9 < 0 )
    {
      HIWORD(v15) = 471;
      v24 = v9;
      throw (long *)&v24;
    }
    LOWORD(v15) = 471;
    v10 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)v19 + 32LL))(v19, L"WorkFolders");
    v14 = v10;
    if ( v10 < 0 )
    {
      HIWORD(v15) = 473;
      v25 = v10;
      throw (long *)&v25;
    }
    LOWORD(v15) = 473;
    v11 = (*(__int64 (**)(LPVOID, const wchar_t *, ...))(*(_QWORD *)v19 + 72LL))(
            v19,
            L"@%systemroot%\\system32\\WorkfoldersControl.dll,-1");
    v14 = v11;
    if ( v11 < 0 )
    {
      HIWORD(v15) = 480;
      v26 = v11;
      throw (long *)&v26;
    }
    LOWORD(v15) = 480;
    v12 = (*(__int64 (**)(LPVOID, const wchar_t *, ...))(*(_QWORD *)v19 + 96LL))(
            v19,
            L"%systemroot%\\system32\\WorkfoldersControl.dll,-1");
    v14 = v12;
    if ( v12 < 0 )
    {
      HIWORD(v15) = 482;
      v27 = v12;
      throw (long *)&v27;
    }
    LOWORD(v15) = 482;
    v13 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v19 + 176LL))(v19, 4095, v7);
    v14 = v13;
    if ( v13 < 0 )
    {
      HIWORD(v15) = 485;
      v28 = v13;
      throw (long *)&v28;
    }
    LOWORD(v15) = 485;
    if ( (*(int (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)ppv + 120LL))(ppv, v19) < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids);
      }
    }
    else if ( (*(unsigned int (__fastcall **)(LPVOID, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)ppv + 144LL))(
                ppv,
                L"WorkFolders",
                a2) == -2147024891 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids, a2);
      }
      v14 = -2134375643;
      HIWORD(v15) = 501;
      v29 = -2134375643;
      throw (long *)&v29;
    }
    ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v19);
    ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&ppv);
  }
  catch ( long v31 )
  {
    v14 = v31;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v15) = 514;
    v14 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v15) = 514;
    v14 = -2147418113;
  }
  catch ( const ATL::CAtlException *v32 )
  {
    HIWORD(v15) = 514;
    v14 = *(_DWORD *)v32;
  }
  if ( v14 < 0 )
  {
    HIWORD(v15) = 518;
    v30 = v14;
    throw (long *)&v30;
  }
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v14);
}

```

## disassembly

```asm
0x180030540  push    rbx
0x180030542  push    rsi
0x180030543  push    rdi
0x180030544  push    r14
0x180030546  push    r15
0x180030548  sub     rsp, 0A0h
0x18003054f  mov     r14, r8
0x180030552  mov     rsi, rdx
0x180030555  lea     r15, WPP_GLOBAL_Control
0x18003055c  mov     rax, cs:WPP_GLOBAL_Control
0x180030563  cmp     rax, r15
0x180030566  jz      short loc_180030590
0x180030568  test    byte ptr [rax+44h], 8
0x18003056c  jz      short loc_1800305A2
0x18003056e  cmp     byte ptr [rax+41h], 6
0x180030572  jb      short loc_180030590
0x180030574  mov     edx, 1Bh
0x180030579  lea     r8, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids
0x180030580  mov     rcx, [rax+38h]
0x180030584  call    WPP_SF_
0x180030589  mov     rax, cs:WPP_GLOBAL_Control
0x180030590  test    byte ptr [rax+44h], 8
0x180030594  jz      short loc_1800305A2
0x180030596  cmp     byte ptr [rax+41h], 6
0x18003059a  jb      short loc_1800305A2
0x18003059c  mov     al, 1
0x18003059e  xor     ebx, ebx
0x1800305a0  jmp     short loc_1800305A6
0x1800305a2  xor     ebx, ebx
0x1800305a4  mov     al, bl
0x1800305a6  mov     [rsp+0C8h+var_98], ebx
0x1800305aa  mov     [rsp+0C8h+var_94], 1C3h
0x1800305b2  mov     [rsp+0C8h+var_90], al
0x1800305b6  lea     rax, aCwatcherfactor_7; "CWatcherFactory::UpdateShellSyncRoot"
0x1800305bd  mov     [rsp+0C8h+var_88], rax
0x1800305c2  mov     [rsp+0C8h+var_80], rbx
0x1800305c7  mov     eax, [rsp+0C8h+var_98]
0x1800305cb  mov     [rsp+0C8h+var_98], eax
0x1800305cf  mov     eax, 1C5h
0x1800305d4  test    rsi, rsi
0x1800305d7  jnz     short loc_1800305FD
0x1800305d9  mov     ecx, 80070057h
0x1800305de  mov     [rsp+0C8h+var_98], ecx
0x1800305e2  mov     word ptr [rsp+0C8h+var_94+2], ax
0x1800305e7  mov     [rsp+0C8h+pExceptionObject], ecx
0x1800305eb  lea     rdx, _TI1J; pThrowInfo
0x1800305f2  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x1800305f7  call    _CxxThrowException_0
0x1800305fd  mov     [rsp+0C8h+var_98], ebx
0x180030601  mov     word ptr [rsp+0C8h+var_94], ax
0x180030606  mov     edi, 22h ; '"'
0x18003060b  mov     [rsp+0C8h+var_64], edi
0x18003060f  lea     eax, [rdi+40h]
0x180030612  cmp     [r14], ebx
0x180030615  cmovz   edi, eax
0x180030618  mov     [rsp+0C8h+var_64], edi
0x18003061c  mov     [rsp+0C8h+var_70], rbx
0x180030621  lea     rax, [rsp+0C8h+var_70]
0x180030626  mov     [rsp+0C8h+ppv], rax; ppv
0x18003062b  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x180030632  xor     edx, edx; pUnkOuter
0x180030634  lea     r8d, [rdx+1]; dwClsContext
0x180030638  lea     rcx, CLSID_SyncRootManager; rclsid
0x18003063f  call    cs:__imp_CoCreateInstance
0x180030645  mov     [rsp+0C8h+var_98], eax
0x180030649  mov     [rsp+0C8h+var_98], eax
0x18003064d  mov     ecx, 1D3h
0x180030652  test    eax, eax
0x180030654  jns     short loc_180030670
0x180030656  mov     word ptr [rsp+0C8h+var_94+2], cx
0x18003065b  mov     [rsp+0C8h+var_60], eax
0x18003065f  lea     rdx, _TI1J; pThrowInfo
0x180030666  lea     rcx, [rsp+0C8h+var_60]; pExceptionObject
0x18003066b  call    _CxxThrowException_0
0x180030670  mov     word ptr [rsp+0C8h+var_94], cx
0x180030675  mov     [rsp+0C8h+var_78], rbx
0x18003067a  lea     rax, [rsp+0C8h+var_78]
0x18003067f  mov     [rsp+0C8h+ppv], rax; ppv
0x180030684  lea     r9, _GUID_ca01c124_2769_4576_bf12_8a54ee671a86; riid
0x18003068b  xor     edx, edx; pUnkOuter
0x18003068d  lea     r8d, [rdx+1]; dwClsContext
0x180030691  lea     rcx, CLSID_StorageProviderInfo; rclsid
0x180030698  call    cs:__imp_CoCreateInstance
0x18003069e  mov     [rsp+0C8h+var_98], eax
0x1800306a2  mov     [rsp+0C8h+var_98], eax
0x1800306a6  mov     ecx, 1D7h
0x1800306ab  test    eax, eax
0x1800306ad  jns     short loc_1800306C9
0x1800306af  mov     word ptr [rsp+0C8h+var_94+2], cx
0x1800306b4  mov     [rsp+0C8h+var_5C], eax
0x1800306b8  lea     rdx, _TI1J; pThrowInfo
0x1800306bf  lea     rcx, [rsp+0C8h+var_5C]; pExceptionObject
0x1800306c4  call    _CxxThrowException_0
0x1800306c9  mov     word ptr [rsp+0C8h+var_94], cx
0x1800306ce  mov     rcx, [rsp+0C8h+var_78]
0x1800306d3  mov     rax, [rcx]
0x1800306d6  lea     rdx, aWorkfolders; "WorkFolders"
0x1800306dd  mov     rax, [rax+20h]
0x1800306e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306e6  mov     [rsp+0C8h+var_98], eax
0x1800306ea  mov     [rsp+0C8h+var_98], eax
0x1800306ee  mov     ecx, 1D9h
0x1800306f3  test    eax, eax
0x1800306f5  jns     short loc_180030711
0x1800306f7  mov     word ptr [rsp+0C8h+var_94+2], cx
0x1800306fc  mov     [rsp+0C8h+var_58], eax
0x180030700  lea     rdx, _TI1J; pThrowInfo
0x180030707  lea     rcx, [rsp+0C8h+var_58]; pExceptionObject
0x18003070c  call    _CxxThrowException_0
0x180030711  mov     word ptr [rsp+0C8h+var_94], cx
0x180030716  mov     rcx, [rsp+0C8h+var_78]
0x18003071b  mov     rax, [rcx]
0x18003071e  lea     rdx, aSystemrootSyst_0; "@%systemroot%\\system32\\WorkfoldersCon"...
0x180030725  mov     rax, [rax+48h]
0x180030729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003072e  mov     [rsp+0C8h+var_98], eax
0x180030732  mov     [rsp+0C8h+var_98], eax
0x180030736  mov     ecx, 1E0h
0x18003073b  test    eax, eax
0x18003073d  jns     short loc_180030759
0x18003073f  mov     word ptr [rsp+0C8h+var_94+2], cx
0x180030744  mov     [rsp+0C8h+var_54], eax
0x180030748  lea     rdx, _TI1J; pThrowInfo
0x18003074f  lea     rcx, [rsp+0C8h+var_54]; pExceptionObject
0x180030754  call    _CxxThrowException_0
0x180030759  mov     word ptr [rsp+0C8h+var_94], cx
0x18003075e  mov     rcx, [rsp+0C8h+var_78]
0x180030763  mov     rax, [rcx]
0x180030766  lea     rdx, aSystemrootSyst; "%systemroot%\\system32\\WorkfoldersCont"...
0x18003076d  mov     rax, [rax+60h]
0x180030771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030776  mov     [rsp+0C8h+var_98], eax
0x18003077a  mov     [rsp+0C8h+var_98], eax
0x18003077e  mov     ecx, 1E2h
0x180030783  test    eax, eax
0x180030785  jns     short loc_1800307A1
0x180030787  mov     word ptr [rsp+0C8h+var_94+2], cx
0x18003078c  mov     [rsp+0C8h+var_50], eax
0x180030790  lea     rdx, _TI1J; pThrowInfo
0x180030797  lea     rcx, [rsp+0C8h+var_50]; pExceptionObject
0x18003079c  call    _CxxThrowException_0
0x1800307a1  mov     word ptr [rsp+0C8h+var_94], cx
0x1800307a6  mov     rcx, [rsp+0C8h+var_78]
0x1800307ab  mov     rax, [rcx]
0x1800307ae  mov     r8d, edi
0x1800307b1  mov     edx, 0FFFh
0x1800307b6  mov     rax, [rax+0B0h]
0x1800307bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307c2  mov     [rsp+0C8h+var_98], eax
0x1800307c6  mov     [rsp+0C8h+var_98], eax
0x1800307ca  mov     ecx, 1E5h
0x1800307cf  test    eax, eax
0x1800307d1  jns     short loc_1800307ED
0x1800307d3  mov     word ptr [rsp+0C8h+var_94+2], cx
0x1800307d8  mov     [rsp+0C8h+var_4C], eax
0x1800307dc  lea     rdx, _TI1J; pThrowInfo
0x1800307e3  lea     rcx, [rsp+0C8h+var_4C]; pExceptionObject
0x1800307e8  call    _CxxThrowException_0
0x1800307ed  mov     word ptr [rsp+0C8h+var_94], cx
0x1800307f2  mov     rcx, [rsp+0C8h+var_70]
0x1800307f7  mov     rax, [rcx]
0x1800307fa  mov     rdx, [rsp+0C8h+var_78]
0x1800307ff  mov     rax, [rax+78h]
0x180030803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030808  test    eax, eax
0x18003080a  js      loc_18003089F
0x180030810  mov     rcx, [rsp+0C8h+var_70]
0x180030815  mov     rax, [rcx]
0x180030818  mov     r8, rsi
0x18003081b  lea     rdx, aWorkfolders; "WorkFolders"
0x180030822  mov     rax, [rax+90h]
0x180030829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003082e  cmp     eax, 80070005h
0x180030833  jnz     loc_1800308D0
0x180030839  mov     rcx, cs:WPP_GLOBAL_Control
0x180030840  cmp     rcx, r15
0x180030843  jz      short loc_180030869
0x180030845  test    byte ptr [rcx+44h], 8
0x180030849  jz      short loc_180030869
0x18003084b  cmp     byte ptr [rcx+41h], 2
0x18003084f  jb      short loc_180030869
0x180030851  mov     edx, 1Ch
0x180030856  mov     r9, rsi
0x180030859  lea     r8, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids
0x180030860  mov     rcx, [rcx+38h]
0x180030864  call    WPP_SF_S
0x180030869  mov     eax, [rsp+0C8h+var_98]
0x18003086d  mov     [rsp+0C8h+var_98], eax
0x180030871  mov     ecx, 80C80325h
0x180030876  mov     [rsp+0C8h+var_98], ecx
0x18003087a  mov     eax, 1F5h
0x18003087f  mov     word ptr [rsp+0C8h+var_94+2], ax
0x180030884  mov     [rsp+0C8h+var_48], ecx
0x18003088b  lea     rdx, _TI1J; pThrowInfo
0x180030892  lea     rcx, [rsp+0C8h+var_48]; pExceptionObject
0x18003089a  call    _CxxThrowException_0
0x18003089f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800308a6  cmp     rcx, r15
0x1800308a9  jz      short loc_1800308D0
0x1800308ab  test    byte ptr [rcx+44h], 8
0x1800308af  jz      short loc_1800308D0
0x1800308b1  cmp     byte ptr [rcx+41h], 3
0x1800308b5  jb      short loc_1800308D0
0x1800308b7  mov     edx, 1Dh
0x1800308bc  mov     r9d, eax
0x1800308bf  lea     r8, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids
0x1800308c6  mov     rcx, [rcx+38h]
0x1800308ca  call    WPP_SF_d
0x1800308cf  nop
0x1800308d0  lea     rcx, [rsp+0C8h+var_78]
0x1800308d5  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x1800308da  nop
0x1800308db  lea     rcx, [rsp+0C8h+var_70]
0x1800308e0  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x1800308e5  nop
0x1800308e6  jmp     short loc_1800308EE
0x1800308e8  jmp     short loc_1800308EE
0x1800308ea  jmp     short loc_1800308EE
0x1800308ec  jmp     short $+2
0x1800308ee  mov     eax, [rsp+0C8h+var_98]
0x1800308f2  test    eax, eax
0x1800308f4  jns     short loc_180030924
0x1800308f6  mov     [rsp+0C8h+var_98], eax
0x1800308fa  mov     [rsp+0C8h+var_98], eax
0x1800308fe  mov     ecx, 206h
0x180030903  mov     word ptr [rsp+0C8h+var_94+2], cx
0x180030908  mov     [rsp+0C8h+var_44], eax
0x18003090f  lea     rdx, _TI1J; pThrowInfo
0x180030916  lea     rcx, [rsp+0C8h+var_44]; pExceptionObject
0x18003091e  call    _CxxThrowException_0
0x180030924  lea     rcx, [rsp+0C8h+var_98]; this
0x180030929  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18003092e  add     rsp, 0A0h
0x180030935  pop     r15
0x180030937  pop     r14
0x180030939  pop     rdi
0x18003093a  pop     rsi
0x18003093b  pop     rbx
0x18003093c  retn
```
