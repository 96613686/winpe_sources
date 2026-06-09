# UpgradeMediaStorageGuidsInOneTable(IUSStoreManager *,IDBVolume *,_GUID const &,US_ITEMTYPE,ulong *,ulong)

- ea: `0x18009aa28`
- end: `0x18009ae07`
- name: `?UpgradeMediaStorageGuidsInOneTable@@YAJPEAUIUSStoreManager@@PEAVIDBVolume@@AEBU_GUID@@W4US_ITEMTYPE@@PEAKK@Z`
- size: `991`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18009a870`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x18001e2f4`
- `0x180034664`
- `0x180035d40`
- `0x1800576c0`
- `0x180059828`
- `0x180078a40`
- `0x180078a8c`
- `0x18009aa28`
- `0x1800c50aa`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009accf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ad36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ad6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009accf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ad36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ad6b`

## string_xrefs

- `0x18009aa9b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009ad0e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009ad56`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009ad8d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009adce`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`

## pseudocode

```c
__int64 __fastcall UpgradeMediaStorageGuidsInOneTable(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6)
{
  __int64 v6; // rax
  __int64 v8; // r14
  __int64 (__fastcall *v9)(__int64 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *); // rax
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // edi
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64, _QWORD, void **); // rbx
  void **v17; // rax
  int v18; // eax
  unsigned __int64 v19; // rdi
  _DWORD *v20; // rax
  __int64 v21; // rdx
  _DWORD *v22; // rbx
  unsigned int v23; // r10d
  __int64 v24; // r14
  __int64 v25; // r11
  __int64 v26; // rdx
  __int64 v27; // rdi
  _QWORD *v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  int started; // edi
  __int64 v32; // rdx
  __int64 v33; // r9
  __int64 v34; // r9
  __int64 v35; // rcx
  __int64 v37; // [rsp+40h] [rbp-49h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-41h] BYREF
  __int64 v39; // [rsp+50h] [rbp-39h] BYREF
  int v40; // [rsp+58h] [rbp-31h] BYREF
  char v41[8]; // [rsp+60h] [rbp-29h] BYREF
  int v42; // [rsp+68h] [rbp-21h]
  int v43; // [rsp+70h] [rbp-19h] BYREF
  __int64 v44; // [rsp+78h] [rbp-11h]
  __int64 v45; // [rsp+80h] [rbp-9h] BYREF
  int v46; // [rsp+88h] [rbp-1h]

  v6 = *a1;
  v8 = a5;
  v44 = a5;
  v9 = *(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *))(v6 + 136);
  v39 = 0;
  v11 = v9(a1, a4, 0, 0, 0, 0, &v39);
  v12 = v11;
  if ( v11 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v11,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
      514);
    goto LABEL_43;
  }
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 120LL))(v39);
  while ( 1 )
  {
    if ( v13 )
    {
      if ( v13 == -2147024871 )
      {
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v39);
        return 0;
      }
      else
      {
        Log_UnistoreHREvent_0(
          v13,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          569);
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v39);
        return v13;
      }
    }
    v37 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 40LL))(v39, &v37);
    v12 = v14;
    if ( v14 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v14,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
        520);
LABEL_42:
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v37);
      goto LABEL_43;
    }
    v15 = v37;
    hMem = 0;
    v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, void **))(*(_QWORD *)v37 + 48LL);
    v17 = tlx::replace<_USPROPVAL,&void _LocalFreer<_USPROPVAL>(_USPROPVAL *)>(&hMem);
    v18 = v16(v15, a6, v8, 0, v17);
    v12 = v18;
    if ( v18 < 0 )
    {
      v34 = 523;
      goto LABEL_39;
    }
    v45 = 0;
    v46 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 24LL))(v37, &v45);
    v12 = v18;
    if ( v18 < 0 )
    {
      v34 = 526;
LABEL_39:
      v21 = 1;
      v35 = (unsigned int)v18;
LABEL_36:
      Log_UnistoreHREvent_0(
        v35,
        v21,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
        v34);
      if ( hMem )
        LocalFree(hMem);
      goto LABEL_42;
    }
    v19 = saturated_mul(a6, 0x18u);
    v20 = operator new[](v19);
    v21 = 0;
    v22 = v20;
    if ( !v20 )
    {
      v12 = -2147024882;
      v34 = 530;
      v35 = 2147942414LL;
      goto LABEL_36;
    }
    memset_0(v20, 0, v19);
    v23 = 0;
    v24 = 0;
    if ( !a6 )
      goto LABEL_24;
    v25 = *(_QWORD *)GUID_NULL.Data4;
    v26 = 0;
    v27 = *(_QWORD *)&GUID_NULL.Data1;
    do
    {
      if ( (*((_WORD *)hMem + 12 * v26 + 3) & 0x300) == 0 && *((_DWORD *)hMem + 6 * v26 + 2) == 16 )
      {
        v28 = (_QWORD *)*((_QWORD *)hMem + 3 * v26 + 2);
        v29 = *v28 - v27;
        if ( *v28 == v27 )
          v29 = v28[1] - v25;
        if ( !v29 )
        {
          v30 = 3 * v24;
          v22[2 * v30] = *((_DWORD *)hMem + 6 * v26);
          v24 = (unsigned int)(v24 + 1);
          v22[2 * v30 + 2] = 16;
          *(_QWORD *)&v22[2 * v30 + 4] = a3;
          v25 = *(_QWORD *)GUID_NULL.Data4;
          v27 = *(_QWORD *)&GUID_NULL.Data1;
        }
      }
      ++v23;
      ++v26;
    }
    while ( v23 < a6 );
    if ( !(_DWORD)v24 )
      goto LABEL_24;
    v43 = v45;
    ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(v41, a2);
    v42 = 0;
    started = DBAutoTopLevelTransact::StartTransaction(
                (DBAutoTopLevelTransact *)v41,
                3u,
                1u,
                (const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *)&v43);
    if ( started < 0 )
      break;
    started = (*(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *, _QWORD))(*(_QWORD *)v37 + 80LL))(
                v37,
                (unsigned int)v24,
                v22,
                0);
    v32 = 1;
    if ( started < 0 )
    {
      v33 = 560;
      goto LABEL_32;
    }
    v40 = 0;
    started = DBAutoTopLevelTransact::EndTransaction((DBAutoTopLevelTransact *)v41, 1, &v40);
    if ( started < 0 )
    {
      v33 = 563;
      goto LABEL_31;
    }
    if ( !v40 )
    {
      v33 = 564;
      v32 = 0;
      started = -2147418113;
      goto LABEL_32;
    }
    DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)v41);
LABEL_24:
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 96LL))(v39);
    operator delete(v22);
    if ( hMem )
      LocalFree(hMem);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v37);
    v8 = v44;
  }
  v33 = 558;
LABEL_31:
  v32 = 1;
LABEL_32:
  Log_UnistoreHREvent_0(
    (unsigned int)started,
    v32,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
    v33);
  DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)v41);
  operator delete(v22);
  if ( hMem )
    LocalFree(hMem);
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v37);
  v12 = started;
LABEL_43:
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v39);
  return v12;
}

```

## disassembly

```asm
0x18009aa28  push    rbp
0x18009aa2a  push    rbx
0x18009aa2b  push    rsi
0x18009aa2c  push    rdi
0x18009aa2d  push    r12
0x18009aa2f  push    r13
0x18009aa31  push    r14
0x18009aa33  lea     rbp, [rsp-17h]
0x18009aa38  sub     rsp, 0A0h
0x18009aa3f  mov     rax, cs:__security_cookie
0x18009aa46  xor     rax, rsp
0x18009aa49  mov     [rbp+47h+var_40], rax
0x18009aa4d  mov     rax, [rcx]
0x18009aa50  mov     r13, rdx
0x18009aa53  mov     r14, [rbp+47h+arg_20]
0x18009aa57  lea     rdx, [rbp+47h+var_80]
0x18009aa5b  mov     [rsp+0D0h+var_A0], rdx
0x18009aa60  mov     r10d, r9d
0x18009aa63  xor     edi, edi
0x18009aa65  mov     [rbp+47h+var_58], r14
0x18009aa69  mov     rax, [rax+88h]
0x18009aa70  mov     r12, r8
0x18009aa73  mov     [rsp+0D0h+var_A8], rdi
0x18009aa78  xor     r9d, r9d
0x18009aa7b  xor     r8d, r8d
0x18009aa7e  mov     [rbp+47h+var_80], rdi
0x18009aa82  mov     edx, r10d
0x18009aa85  mov     [rsp+0D0h+var_B0], rdi
0x18009aa8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aa8f  mov     ebx, eax
0x18009aa91  test    eax, eax
0x18009aa93  jns     short loc_18009AAB1
0x18009aa95  mov     r9d, 202h
0x18009aa9b  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009aaa2  lea     edx, [rdi+1]
0x18009aaa5  mov     ecx, eax
0x18009aaa7  call    Log_UnistoreHREvent_0
0x18009aaac  jmp     loc_18009ADA6
0x18009aab1  mov     rcx, [rbp+47h+var_80]
0x18009aab5  mov     rax, [rcx]
0x18009aab8  mov     rax, [rax+78h]
0x18009aabc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aac1  mov     edi, eax
0x18009aac3  mov     esi, 1
0x18009aac8  test    edi, edi
0x18009aaca  jnz     loc_18009ADB3
0x18009aad0  mov     rcx, [rbp+47h+var_80]
0x18009aad4  lea     rdx, [rbp+47h+var_90]
0x18009aad8  mov     [rbp+47h+var_90], 0
0x18009aae0  mov     rax, [rcx]
0x18009aae3  mov     rax, [rax+28h]
0x18009aae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aaec  mov     ebx, eax
0x18009aaee  test    eax, eax
0x18009aaf0  js      loc_18009AD87
0x18009aaf6  mov     rdi, [rbp+47h+var_90]
0x18009aafa  lea     rcx, [rbp+47h+hMem]
0x18009aafe  mov     [rbp+47h+hMem], 0
0x18009ab06  mov     rax, [rdi]
0x18009ab09  mov     rbx, [rax+30h]
0x18009ab0d  call    ??$replace@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_USPROPVAL@@AEAV?$auto_ptr@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)>(tlx::auto_ptr<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)> &)
0x18009ab12  mov     edx, [rbp+47h+arg_28]
0x18009ab15  xor     r9d, r9d
0x18009ab18  mov     [rsp+0D0h+var_B0], rax
0x18009ab1d  mov     r8, r14
0x18009ab20  mov     rax, rbx
0x18009ab23  mov     rcx, rdi
0x18009ab26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ab2b  mov     ebx, eax
0x18009ab2d  test    eax, eax
0x18009ab2f  js      loc_18009AD7F
0x18009ab35  mov     rcx, [rbp+47h+var_90]
0x18009ab39  lea     rdx, [rbp+47h+var_50]
0x18009ab3d  xor     eax, eax
0x18009ab3f  mov     [rbp+47h+var_50], rax
0x18009ab43  mov     [rbp+47h+var_48], eax
0x18009ab46  mov     rax, [rcx]
0x18009ab49  mov     rax, [rax+18h]
0x18009ab4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ab52  mov     ebx, eax
0x18009ab54  test    eax, eax
0x18009ab56  js      loc_18009AD73
0x18009ab5c  mov     ecx, [rbp+47h+arg_28]
0x18009ab5f  mov     eax, 18h
0x18009ab64  mul     rcx
0x18009ab67  mov     rdi, rax
0x18009ab6a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18009ab71  cmovb   rdi, rax
0x18009ab75  mov     rcx, rdi; unsigned __int64
0x18009ab78  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18009ab7d  xor     edx, edx; Val
0x18009ab7f  mov     rbx, rax
0x18009ab82  test    rax, rax
0x18009ab85  jz      loc_18009AD49
0x18009ab8b  mov     r8, rdi; Size
0x18009ab8e  mov     rcx, rax; void *
0x18009ab91  call    memset_0
0x18009ab96  xor     r10d, r10d
0x18009ab99  xor     r14d, r14d
0x18009ab9c  cmp     [rbp+47h+arg_28], r10d
0x18009aba0  jbe     loc_18009ACAC
0x18009aba6  mov     r11, qword ptr cs:GUID_NULL.Data4
0x18009abad  xor     edx, edx
0x18009abaf  mov     rdi, qword ptr cs:GUID_NULL.Data1
0x18009abb6  mov     r9, [rbp+47h+hMem]
0x18009abba  lea     r8, [rdx+rdx*2]
0x18009abbe  mov     eax, 300h
0x18009abc3  test    [r9+r8*8+6], ax
0x18009abc9  jnz     short loc_18009AC15
0x18009abcb  cmp     dword ptr [r9+r8*8+8], 10h
0x18009abd1  jnz     short loc_18009AC15
0x18009abd3  mov     rcx, [r9+r8*8+10h]
0x18009abd8  mov     rax, [rcx]
0x18009abdb  sub     rax, rdi
0x18009abde  jnz     short loc_18009ABE7
0x18009abe0  mov     rax, [rcx+8]
0x18009abe4  sub     rax, r11
0x18009abe7  test    rax, rax
0x18009abea  jnz     short loc_18009AC15
0x18009abec  mov     eax, [r9+r8*8]
0x18009abf0  lea     rcx, [r14+r14*2]
0x18009abf4  mov     [rbx+rcx*8], eax
0x18009abf7  add     r14d, esi
0x18009abfa  mov     dword ptr [rbx+rcx*8+8], 10h
0x18009ac02  mov     [rbx+rcx*8+10h], r12
0x18009ac07  mov     r11, qword ptr cs:GUID_NULL.Data4
0x18009ac0e  mov     rdi, qword ptr cs:GUID_NULL.Data1
0x18009ac15  add     r10d, esi
0x18009ac18  add     rdx, rsi
0x18009ac1b  cmp     r10d, [rbp+47h+arg_28]
0x18009ac1f  jb      short loc_18009ABB6
0x18009ac21  test    r14d, r14d
0x18009ac24  jz      loc_18009ACAC
0x18009ac2a  mov     eax, dword ptr [rbp+47h+var_50]
0x18009ac2d  lea     rcx, [rbp+47h+var_70]
0x18009ac31  mov     rdx, r13
0x18009ac34  mov     [rbp+47h+var_60], eax
0x18009ac37  call    ??0?$CComPtrBase@VIDBVolume@@@ATL@@IEAA@PEAVIDBVolume@@@Z; ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(IDBVolume *)
0x18009ac3c  lea     r9, [rbp+47h+var_60]; enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *
0x18009ac40  mov     [rbp+47h+var_68], 0
0x18009ac47  mov     r8d, esi; unsigned int
0x18009ac4a  lea     rcx, [rbp+47h+var_70]; this
0x18009ac4e  mov     edx, 3; unsigned int
0x18009ac53  call    ?StartTransaction@DBAutoTopLevelTransact@@QEAAJKKPEBW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@@Z; DBAutoTopLevelTransact::StartTransaction(ulong,ulong,__MIDL___MIDL_itf_unistore_0000_0002_0001 const *)
0x18009ac58  mov     edi, eax
0x18009ac5a  test    eax, eax
0x18009ac5c  js      loc_18009AD06
0x18009ac62  mov     rcx, [rbp+47h+var_90]
0x18009ac66  xor     r9d, r9d
0x18009ac69  mov     r8, rbx
0x18009ac6c  mov     edx, r14d
0x18009ac6f  mov     rax, [rcx]
0x18009ac72  mov     rax, [rax+50h]
0x18009ac76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ac7b  mov     edi, eax
0x18009ac7d  mov     edx, esi; int
0x18009ac7f  test    eax, eax
0x18009ac81  js      short loc_18009ACFE
0x18009ac83  lea     r8, [rbp+47h+var_78]; int *
0x18009ac87  mov     [rbp+47h+var_78], 0
0x18009ac8e  lea     rcx, [rbp+47h+var_70]; this
0x18009ac92  call    ?EndTransaction@DBAutoTopLevelTransact@@QEAAJHPEAH@Z; DBAutoTopLevelTransact::EndTransaction(int,int *)
0x18009ac97  mov     edi, eax
0x18009ac99  test    eax, eax
0x18009ac9b  js      short loc_18009ACF6
0x18009ac9d  cmp     [rbp+47h+var_78], 0
0x18009aca1  jz      short loc_18009ACE7
0x18009aca3  lea     rcx, [rbp+47h+var_70]; this
0x18009aca7  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x18009acac  mov     rcx, [rbp+47h+var_80]
0x18009acb0  mov     rax, [rcx]
0x18009acb3  mov     rax, [rax+60h]
0x18009acb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009acbc  mov     rcx, rbx; Block
0x18009acbf  mov     edi, eax
0x18009acc1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009acc6  mov     rcx, [rbp+47h+hMem]; hMem
0x18009acca  test    rcx, rcx
0x18009accd  jz      short loc_18009ACD5
0x18009accf  call    cs:__imp_LocalFree
0x18009acd5  lea     rcx, [rbp+47h+var_90]; void *
0x18009acd9  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009acde  mov     r14, [rbp+47h+var_58]
0x18009ace2  jmp     loc_18009AAC8
0x18009ace7  mov     r9d, 234h
0x18009aced  xor     edx, edx
0x18009acef  mov     edi, 8000FFFFh
0x18009acf4  jmp     short loc_18009AD0E
0x18009acf6  mov     r9d, 233h
0x18009acfc  jmp     short loc_18009AD0C
0x18009acfe  mov     r9d, 230h
0x18009ad04  jmp     short loc_18009AD0E
0x18009ad06  mov     r9d, 22Eh
0x18009ad0c  mov     edx, esi
0x18009ad0e  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009ad15  mov     ecx, edi
0x18009ad17  call    Log_UnistoreHREvent_0
0x18009ad1c  lea     rcx, [rbp+47h+var_70]; this
0x18009ad20  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x18009ad25  mov     rcx, rbx; Block
0x18009ad28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009ad2d  mov     rcx, [rbp+47h+hMem]; hMem
0x18009ad31  test    rcx, rcx
0x18009ad34  jz      short loc_18009AD3C
0x18009ad36  call    cs:__imp_LocalFree
0x18009ad3c  lea     rcx, [rbp+47h+var_90]; void *
0x18009ad40  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009ad45  mov     ebx, edi
0x18009ad47  jmp     short loc_18009ADA6
0x18009ad49  mov     ebx, 8007000Eh
0x18009ad4e  mov     r9d, 212h
0x18009ad54  mov     ecx, ebx
0x18009ad56  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009ad5d  call    Log_UnistoreHREvent_0
0x18009ad62  mov     rcx, [rbp+47h+hMem]; hMem
0x18009ad66  test    rcx, rcx
0x18009ad69  jz      short loc_18009AD9D
0x18009ad6b  call    cs:__imp_LocalFree
0x18009ad71  jmp     short loc_18009AD9D
0x18009ad73  mov     r9d, 20Eh
0x18009ad79  mov     edx, esi
0x18009ad7b  mov     ecx, eax
0x18009ad7d  jmp     short loc_18009AD56
0x18009ad7f  mov     r9d, 20Bh
0x18009ad85  jmp     short loc_18009AD79
0x18009ad87  mov     r9d, 208h
0x18009ad8d  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009ad94  mov     edx, esi
0x18009ad96  mov     ecx, eax
0x18009ad98  call    Log_UnistoreHREvent_0
0x18009ad9d  lea     rcx, [rbp+47h+var_90]; void *
0x18009ada1  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009ada6  lea     rcx, [rbp+47h+var_80]; void *
0x18009adaa  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009adaf  mov     eax, ebx
0x18009adb1  jmp     short loc_18009ADE9
0x18009adb3  cmp     edi, 80070019h
0x18009adb9  jnz     short loc_18009ADC8
0x18009adbb  lea     rcx, [rbp+47h+var_80]; void *
0x18009adbf  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009adc4  xor     eax, eax
0x18009adc6  jmp     short loc_18009ADE9
0x18009adc8  mov     r9d, 239h
0x18009adce  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009add5  xor     edx, edx
0x18009add7  mov     ecx, edi
0x18009add9  call    Log_UnistoreHREvent_0
0x18009adde  lea     rcx, [rbp+47h+var_80]; void *
0x18009ade2  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009ade7  mov     eax, edi
0x18009ade9  mov     rcx, [rbp+47h+var_40]
0x18009aded  xor     rcx, rsp; StackCookie
0x18009adf0  call    __security_check_cookie
0x18009adf5  add     rsp, 0A0h
0x18009adfc  pop     r14
0x18009adfe  pop     r13
0x18009ae00  pop     r12
0x18009ae02  pop     rdi
0x18009ae03  pop     rsi
0x18009ae04  pop     rbx
0x18009ae05  pop     rbp
0x18009ae06  retn
```
