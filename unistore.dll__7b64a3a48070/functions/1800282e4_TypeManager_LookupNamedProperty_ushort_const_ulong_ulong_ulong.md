# TypeManager::_LookupNamedProperty(ushort const *,ulong *,ulong *,ulong *)

- ea: `0x1800282e4`
- end: `0x18002876f`
- name: `?_LookupNamedProperty@TypeManager@@AEAAJPEBGPEAK11@Z`
- size: `1163`
- prototype: `__int64 __fastcall(TypeManager *__hidden this, const unsigned __int16 *, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026310`
- `0x1800b5f80`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x1800282e4`
- `0x180028ef4`
- `0x18002c9f0`
- `0x1800396c8`
- `0x180039898`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002846e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028598`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800285e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002866f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002846e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028598`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800285e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002866f`

## string_xrefs

- `0x1800284d9`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\typemanager.cpp`
- `0x180028547`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\typemanager.cpp`
- `0x18002857c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\typemanager.cpp`
- `0x1800285fb`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\typemanager.cpp`
- `0x180028614`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\typemanager.cpp`
- `0x1800286a3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\typemanager.cpp`
- `0x18002870a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\typemanager.cpp`
- `0x18002872e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\typemanager.cpp`

## pseudocode

```c
__int64 __fastcall TypeManager::_LookupNamedProperty(
        TypeManager *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  int Instance; // eax
  unsigned int v9; // ebx
  struct IDBManager *v10; // rbx
  int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  int v14; // eax
  _DWORD *v15; // rcx
  __int64 v17; // r9
  void *v18; // rax
  __int64 v19; // [rsp+40h] [rbp-31h] BYREF
  __int64 v20; // [rsp+48h] [rbp-29h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-21h] BYREF
  struct IDBManager *v22; // [rsp+58h] [rbp-19h] BYREF
  int v23; // [rsp+60h] [rbp-11h]
  __int128 v24; // [rsp+64h] [rbp-Dh]
  int v25; // [rsp+74h] [rbp+3h]
  _DWORD v26[4]; // [rsp+78h] [rbp+7h] BYREF

  if ( !a2 )
  {
    v17 = 317;
    v9 = -2147024809;
    goto LABEL_39;
  }
  if ( !a3 )
  {
    v17 = 318;
LABEL_38:
    v9 = -2147467261;
LABEL_39:
    Log_UnistoreHREvent_0(
      v9,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\typemanager.cpp",
      v17);
    return v9;
  }
  if ( !a4 )
  {
    v17 = 319;
    goto LABEL_38;
  }
  if ( !a5 )
  {
    v17 = 320;
    goto LABEL_38;
  }
  v22 = 0;
  Instance = DBManager::GetInstance(&v22);
  v9 = Instance;
  if ( Instance < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)Instance,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\typemanager.cpp",
      324);
    if ( v22 )
      (*(void (__fastcall **)(struct IDBManager *))(*(_QWORD *)v22 + 16LL))(v22);
    return v9;
  }
  v10 = v22;
  v20 = 0;
  v11 = (*(__int64 (__fastcall **)(struct IDBManager *, __int64, __int64, __int64 *))(*(_QWORD *)v22 + 40LL))(
          v22,
          6,
          1,
          &v20);
  v12 = v11;
  if ( v11 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v11,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\typemanager.cpp",
      328);
LABEL_55:
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v20);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v22);
    return v12;
  }
  v25 = 0;
  v19 = 0;
  v24 = 0;
  v23 = 805371935;
  *(_QWORD *)((char *)&v24 + 4) = a2;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v20 + 56LL))(v20, 4, 0);
  v12 = v13;
  if ( (_WORD)v13 == 25 )
  {
    if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x20) != 0 )
    {
      v18 = _t_address();
      EtwTraceMessage(&ETWMESSAGE, v18, a2, -2, 0, -1);
    }
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v19);
    v12 = -2147023728;
    goto LABEL_55;
  }
  if ( v13 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v13,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\typemanager.cpp",
      344);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v19);
    goto LABEL_55;
  }
  hMem = 0;
  v26[0] = 65539;
  v26[1] = 537526291;
  v26[2] = 538181651;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, _DWORD *, HLOCAL *, _QWORD))(*(_QWORD *)v19 + 40LL))(
          v19,
          3,
          v26,
          &hMem,
          0);
  v12 = v14;
  if ( v14 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v14,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\typemanager.cpp",
      349);
    if ( hMem )
      LocalFree(hMem);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    if ( v10 )
      (*(void (__fastcall **)(struct IDBManager *))(*(_QWORD *)v10 + 16LL))(v10);
    return v12;
  }
  v15 = hMem;
  if ( (*((_WORD *)hMem + 3) & 0x100) != 0 )
  {
    Log_UnistoreHREvent_0(
      2147500037LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\typemanager.cpp",
      351);
    if ( hMem )
      LocalFree(hMem);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    if ( !v10 )
      return 2147500037LL;
LABEL_25:
    (*(void (__fastcall **)(struct IDBManager *))(*(_QWORD *)v10 + 16LL))(v10);
    return 2147500037LL;
  }
  if ( (*((_WORD *)hMem + 15) & 0x100) != 0 )
  {
    Log_UnistoreHREvent_0(
      2147500037LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\typemanager.cpp",
      352);
    if ( hMem )
      LocalFree(hMem);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    if ( !v10 )
      return 2147500037LL;
    goto LABEL_25;
  }
  if ( (*((_WORD *)hMem + 27) & 0x100) != 0 )
  {
    Log_UnistoreHREvent_0(
      2147500037LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\typemanager.cpp",
      353);
    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&hMem);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v19);
    v12 = -2147467259;
    goto LABEL_55;
  }
  *a3 = *((_DWORD *)hMem + 2);
  *a4 = v15[8];
  *a5 = v15[14];
  LocalFree(v15);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v10 )
    (*(void (__fastcall **)(struct IDBManager *))(*(_QWORD *)v10 + 16LL))(v10);
  return 0;
}

```

## disassembly

```asm
0x1800282e4  push    rbp
0x1800282e6  push    rbx
0x1800282e7  push    rdi
0x1800282e8  push    r12
0x1800282ea  push    r13
0x1800282ec  push    r14
0x1800282ee  push    r15
0x1800282f0  lea     rbp, [rsp-1Fh]
0x1800282f5  sub     rsp, 90h
0x1800282fc  mov     rax, cs:__security_cookie
0x180028303  xor     rax, rsp
0x180028306  mov     [rbp+4Fh+var_38], rax
0x18002830a  mov     r15, [rbp+4Fh+arg_20]
0x18002830e  mov     r12, r9
0x180028311  mov     r13, r8
0x180028314  mov     r14, rdx
0x180028317  test    rdx, rdx
0x18002831a  jz      loc_180028677
0x180028320  test    r8, r8
0x180028323  jz      loc_1800285EE
0x180028329  test    r9, r9
0x18002832c  jz      loc_180028687
0x180028332  test    r15, r15
0x180028335  jz      loc_180028692
0x18002833b  lea     rcx, [rbp+4Fh+var_68]; struct IDBManager **
0x18002833f  mov     [rbp+4Fh+var_68], 0
0x180028347  call    ?GetInstance@DBManager@@SAJPEAPEAVIDBManager@@@Z; DBManager::GetInstance(IDBManager * *)
0x18002834c  mov     ebx, eax
0x18002834e  test    eax, eax
0x180028350  js      loc_180028541
0x180028356  mov     rbx, [rbp+4Fh+var_68]
0x18002835a  lea     r9, [rbp+4Fh+var_78]
0x18002835e  mov     [rbp+4Fh+var_78], 0
0x180028366  mov     edx, 6
0x18002836b  mov     rcx, rbx
0x18002836e  mov     rax, [rbx]
0x180028371  lea     r8d, [rdx-5]
0x180028375  mov     rax, [rax+28h]
0x180028379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002837e  mov     edi, eax
0x180028380  test    eax, eax
0x180028382  js      loc_18002869D
0x180028388  mov     rcx, [rbp+4Fh+var_78]
0x18002838c  lea     rdx, [rbp+4Fh+var_80]
0x180028390  xor     eax, eax
0x180028392  mov     [rsp+0C0h+var_98], rdx
0x180028397  mov     [rbp+4Fh+var_4C], eax
0x18002839a  lea     rdx, [rbp+4Fh+var_60]
0x18002839e  mov     [rbp+4Fh+var_80], rax
0x1800283a2  xorps   xmm0, xmm0
0x1800283a5  movups  [rbp+4Fh+var_5C], xmm0
0x1800283a9  mov     [rbp+4Fh+var_60], 3001001Fh
0x1800283b0  mov     r9d, 1
0x1800283b6  mov     qword ptr [rbp+4Fh+var_5C+4], r14
0x1800283ba  xor     r8d, r8d
0x1800283bd  mov     rax, [rcx]
0x1800283c0  mov     [rsp+0C0h+var_A0], rdx
0x1800283c5  lea     edx, [r9+3]
0x1800283c9  mov     rax, [rax+38h]
0x1800283cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283d2  mov     edi, eax
0x1800283d4  cmp     ax, 19h
0x1800283d8  jz      loc_1800286BB
0x1800283de  test    eax, eax
0x1800283e0  js      loc_180028704
0x1800283e6  mov     rcx, [rbp+4Fh+var_80]
0x1800283ea  lea     r9, [rbp+4Fh+hMem]
0x1800283ee  mov     [rbp+4Fh+hMem], 0
0x1800283f6  lea     r8, [rbp+4Fh+var_48]
0x1800283fa  mov     [rbp+4Fh+var_48], 10003h
0x180028401  mov     edx, 3
0x180028406  mov     [rbp+4Fh+var_44], 200A0013h
0x18002840d  mov     [rbp+4Fh+var_40], 20140013h
0x180028414  mov     rax, [rcx]
0x180028417  mov     [rsp+0C0h+var_A0], 0
0x180028420  mov     rax, [rax+28h]
0x180028424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028429  mov     edi, eax
0x18002842b  test    eax, eax
0x18002842d  js      loc_180028576
0x180028433  mov     rcx, [rbp+4Fh+hMem]; hMem
0x180028437  mov     eax, 100h
0x18002843c  test    [rcx+6], ax
0x180028440  jnz     loc_18002860E
0x180028446  test    [rcx+1Eh], ax
0x18002844a  jnz     loc_1800284D3
0x180028450  test    [rcx+36h], ax
0x180028454  jnz     loc_180028728
0x18002845a  mov     eax, [rcx+8]
0x18002845d  mov     [r13+0], eax
0x180028461  mov     eax, [rcx+20h]
0x180028464  mov     [r12], eax
0x180028468  mov     eax, [rcx+38h]
0x18002846b  mov     [r15], eax
0x18002846e  call    cs:__imp_LocalFree
0x180028474  mov     rcx, [rbp+4Fh+var_80]
0x180028478  test    rcx, rcx
0x18002847b  jz      short loc_180028489
0x18002847d  mov     rax, [rcx]
0x180028480  mov     rax, [rax+10h]
0x180028484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028489  mov     rcx, [rbp+4Fh+var_78]
0x18002848d  test    rcx, rcx
0x180028490  jz      short loc_18002849E
0x180028492  mov     rax, [rcx]
0x180028495  mov     rax, [rax+10h]
0x180028499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002849e  test    rbx, rbx
0x1800284a1  jz      short loc_1800284B2
0x1800284a3  mov     rax, [rbx]
0x1800284a6  mov     rcx, rbx
0x1800284a9  mov     rax, [rax+10h]
0x1800284ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284b2  xor     eax, eax
0x1800284b4  mov     rcx, [rbp+4Fh+var_38]
0x1800284b8  xor     rcx, rsp; StackCookie
0x1800284bb  call    __security_check_cookie
0x1800284c0  add     rsp, 90h
0x1800284c7  pop     r15
0x1800284c9  pop     r14
0x1800284cb  pop     r13
0x1800284cd  pop     r12
0x1800284cf  pop     rdi
0x1800284d0  pop     rbx
0x1800284d1  pop     rbp
0x1800284d2  retn
0x1800284d3  mov     r9d, 160h
0x1800284d9  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800284e0  xor     edx, edx
0x1800284e2  mov     ecx, 80004005h
0x1800284e7  call    Log_UnistoreHREvent_0
0x1800284ec  mov     rcx, [rbp+4Fh+hMem]; hMem
0x1800284f0  test    rcx, rcx
0x1800284f3  jnz     loc_1800285E3
0x1800284f9  mov     rcx, [rbp+4Fh+var_80]
0x1800284fd  test    rcx, rcx
0x180028500  jz      short loc_18002850E
0x180028502  mov     rax, [rcx]
0x180028505  mov     rax, [rax+10h]
0x180028509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002850e  mov     rcx, [rbp+4Fh+var_78]
0x180028512  test    rcx, rcx
0x180028515  jz      short loc_180028523
0x180028517  mov     rax, [rcx]
0x18002851a  mov     rax, [rax+10h]
0x18002851e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028523  test    rbx, rbx
0x180028526  jz      short loc_180028537
0x180028528  mov     rcx, [rbx]
0x18002852b  mov     rax, [rcx+10h]
0x18002852f  mov     rcx, rbx
0x180028532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028537  mov     eax, 80004005h
0x18002853c  jmp     loc_1800284B4
0x180028541  mov     r9d, 144h
0x180028547  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002854e  mov     edx, 1
0x180028553  mov     ecx, ebx
0x180028555  call    Log_UnistoreHREvent_0
0x18002855a  mov     rcx, [rbp+4Fh+var_68]
0x18002855e  test    rcx, rcx
0x180028561  jz      short loc_18002856F
0x180028563  mov     rax, [rcx]
0x180028566  mov     rax, [rax+10h]
0x18002856a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002856f  mov     eax, ebx
0x180028571  jmp     loc_1800284B4
0x180028576  mov     r9d, 15Dh
0x18002857c  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180028583  mov     edx, 1
0x180028588  mov     ecx, edi
0x18002858a  call    Log_UnistoreHREvent_0
0x18002858f  mov     rcx, [rbp+4Fh+hMem]; hMem
0x180028593  test    rcx, rcx
0x180028596  jz      short loc_18002859E
0x180028598  call    cs:__imp_LocalFree
0x18002859e  mov     rcx, [rbp+4Fh+var_80]
0x1800285a2  test    rcx, rcx
0x1800285a5  jz      short loc_1800285B3
0x1800285a7  mov     rax, [rcx]
0x1800285aa  mov     rax, [rax+10h]
0x1800285ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285b3  mov     rcx, [rbp+4Fh+var_78]
0x1800285b7  test    rcx, rcx
0x1800285ba  jz      short loc_1800285C8
0x1800285bc  mov     rax, [rcx]
0x1800285bf  mov     rax, [rax+10h]
0x1800285c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285c8  test    rbx, rbx
0x1800285cb  jz      short loc_1800285DC
0x1800285cd  mov     rax, [rbx]
0x1800285d0  mov     rcx, rbx
0x1800285d3  mov     rax, [rax+10h]
0x1800285d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285dc  mov     eax, edi
0x1800285de  jmp     loc_1800284B4
0x1800285e3  call    cs:__imp_LocalFree
0x1800285e9  jmp     loc_1800284F9
0x1800285ee  mov     r9d, 13Eh
0x1800285f4  mov     ebx, 80004003h
0x1800285f9  xor     edx, edx
0x1800285fb  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180028602  mov     ecx, ebx
0x180028604  call    Log_UnistoreHREvent_0
0x180028609  jmp     loc_18002856F
0x18002860e  mov     r9d, 15Fh
0x180028614  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002861b  xor     edx, edx
0x18002861d  mov     ecx, 80004005h
0x180028622  call    Log_UnistoreHREvent_0
0x180028627  mov     rcx, [rbp+4Fh+hMem]; hMem
0x18002862b  test    rcx, rcx
0x18002862e  jnz     short loc_18002866F
0x180028630  mov     rcx, [rbp+4Fh+var_80]
0x180028634  test    rcx, rcx
0x180028637  jz      short loc_180028645
0x180028639  mov     rax, [rcx]
0x18002863c  mov     rax, [rax+10h]
0x180028640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028645  mov     rcx, [rbp+4Fh+var_78]
0x180028649  test    rcx, rcx
0x18002864c  jz      short loc_18002865A
0x18002864e  mov     rax, [rcx]
0x180028651  mov     rax, [rax+10h]
0x180028655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002865a  test    rbx, rbx
0x18002865d  jz      loc_180028537
0x180028663  mov     rax, [rbx]
0x180028666  mov     rax, [rax+10h]
0x18002866a  jmp     loc_18002852F
0x18002866f  call    cs:__imp_LocalFree
0x180028675  jmp     short loc_180028630
0x180028677  mov     r9d, 13Dh
0x18002867d  mov     ebx, 80070057h
0x180028682  jmp     loc_1800285F9
0x180028687  mov     r9d, 13Fh
0x18002868d  jmp     loc_1800285F4
0x180028692  mov     r9d, 140h
0x180028698  jmp     loc_1800285F4
0x18002869d  mov     r9d, 148h
0x1800286a3  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800286aa  mov     edx, 1
0x1800286af  mov     ecx, eax
0x1800286b1  call    Log_UnistoreHREvent_0
0x1800286b6  jmp     loc_180028758
0x1800286bb  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits, 20h
0x1800286c2  jz      short loc_1800286F4
0x1800286c4  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x1800286c9  mov     rdx, rax; void *
0x1800286cc  mov     [rsp+0C0h+var_98], 0FFFFFFFFFFFFFFFFh
0x1800286d5  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800286dc  mov     [rsp+0C0h+var_A0], 0
0x1800286e5  mov     r8, r14
0x1800286e8  lea     rcx, _ETWMESSAGE; EventDescriptor
0x1800286ef  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x1800286f4  lea     rcx, [rbp+4Fh+var_80]; void *
0x1800286f8  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800286fd  mov     edi, 80070490h
0x180028702  jmp     short loc_180028758
0x180028704  mov     r9d, 158h
0x18002870a  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180028711  mov     edx, 1
0x180028716  mov     ecx, eax
0x180028718  call    Log_UnistoreHREvent_0
0x18002871d  lea     rcx, [rbp+4Fh+var_80]; void *
0x180028721  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180028726  jmp     short loc_180028758
0x180028728  mov     r9d, 161h
0x18002872e  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180028735  xor     edx, edx
0x180028737  mov     ecx, 80004005h
0x18002873c  call    Log_UnistoreHREvent_0
0x180028741  lea     rcx, [rbp+4Fh+hMem]
0x180028745  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18002874a  lea     rcx, [rbp+4Fh+var_80]; void *
0x18002874e  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180028753  mov     edi, 80004005h
0x180028758  lea     rcx, [rbp+4Fh+var_78]; void *
0x18002875c  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180028761  lea     rcx, [rbp+4Fh+var_68]; void *
0x180028765  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18002876a  jmp     loc_1800285DC
```
