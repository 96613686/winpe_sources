# CBlbVhdHelper::MountVHDAndCreatePartition(CBlbImpersonationHelper *,ushort const *,ushort *,uchar,ushort *,ushort * *)

- ea: `0x140109f18`
- end: `0x14010a682`
- name: `?MountVHDAndCreatePartition@CBlbVhdHelper@@SAJPEAVCBlbImpersonationHelper@@PEBGPEAGE2PEAPEAG@Z`
- size: `1898`
- prototype: `__int64 __usercall@<rax>(struct CBlbImpersonationHelper *@<rcx>, const unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int8@<r9b>, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140020bf0`

## callees

- `0x140006ca8`
- `0x140006d94`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014260`
- `0x140014bc0`
- `0x140014fd8`
- `0x140015010`
- `0x14003e678`
- `0x1400ec7d0`
- `0x1400f76f0`
- `0x140107f88`
- `0x140108554`
- `0x140109f18`
- `0x14010b9e0`
- `0x14010c394`
- `0x14010d66c`
- `0x1401113c4`
- `0x1401116c4`
- `0x140111bf4`
- `0x1401170b0`
- `0x1401269e8`
- `0x140137010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x14010a319`
- `KERNEL32!WaitForSingleObject` at `0x14010a319`
- `KERNEL32!CreateEventW` at `0x14010a142`
- `KERNEL32!CreateEventW` at `0x14010a142`
- `KERNEL32!LeaveCriticalSection` at `0x14010a2fe`
- `KERNEL32!LeaveCriticalSection` at `0x14010a59d`
- `KERNEL32!LeaveCriticalSection` at `0x14010a2fe`
- `KERNEL32!LeaveCriticalSection` at `0x14010a59d`
- `KERNEL32!EnterCriticalSection` at `0x14010a1a1`
- `KERNEL32!EnterCriticalSection` at `0x14010a1a1`
- `ole32!CoTaskMemFree` at `0x14010a5f2`
- `ole32!CoTaskMemFree` at `0x14010a60b`
- `ole32!CoTaskMemFree` at `0x14010a5f2`
- `ole32!CoTaskMemFree` at `0x14010a60b`
- `ole32!CoCreateInstance` at `0x14010a00b`
- `ole32!CoCreateInstance` at `0x14010a00b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CBlbVhdHelper::MountVHDAndCreatePartition(
        struct CBlbImpersonationHelper *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int8 a4,
        unsigned __int16 *String1,
        unsigned __int16 **a6)
{
  WCHAR *v8; // r14
  LPVOID *ppv; // rax
  int Instance; // ebx
  PVOID *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, _QWORD *); // rbx
  _QWORD *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rbx
  HANDLE EventW; // rsi
  __int64 v19; // rdi
  struct IUnknown **v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned __int16 **v23; // rax
  unsigned __int16 **v24; // rsi
  char v25; // r12
  unsigned int v26; // edi
  struct CBlbImpersonationHelper *v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  _QWORD *v31; // rcx
  int v32; // edx
  int v33; // r9d
  unsigned int Data1; // ebx
  CBlbVdsHelperLibrary *v35; // rax
  CBlbVdsHelperLibrary *v36; // rdi
  unsigned int v37; // edx
  __int64 v38; // rax
  int v39; // eax
  __int64 v40; // rax
  __int64 v42; // [rsp+38h] [rbp-69h] BYREF
  __int16 v43; // [rsp+40h] [rbp-61h]
  struct IUnknown *v44; // [rsp+48h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-51h] BYREF
  unsigned int v46; // [rsp+58h] [rbp-49h] BYREF
  unsigned int v47; // [rsp+5Ch] [rbp-45h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-41h] BYREF
  __int64 v49[2]; // [rsp+68h] [rbp-39h] BYREF
  struct _GUID Buf2; // [rsp+78h] [rbp-29h] BYREF
  struct _GET_VIRTUAL_DISK_INFO v51; // [rsp+88h] [rbp-19h] BYREF
  char v52; // [rsp+100h] [rbp+5Fh]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids);
  }
  v8 = 0;
  lpFileName = 0;
  memset(&v51, 0, sizeof(v51));
  pv = 0;
  v46 = 0;
  v43 = *(_WORD *)&GUID_NULL.Data4[6];
  v42 = 0;
  v47 = 0;
  v52 = 0;
  if ( !a2 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbvhdhelper.cpp", 0xCDCu, "wszVhdFile");
  memset(&v51, 0, sizeof(v51));
  v49[0] = 0;
  v44 = 0;
  ppv = (LPVOID *)ATL::CComPtrBase<IRegisteredTask>::operator&(v49);
  Instance = CoCreateInstance(&CLSID_VdsLoader, 0, 0x10004u, &IID_IVdsServiceLoader, ppv);
  if ( Instance >= 0 )
  {
    v13 = ATL::CComPtrBase<IRegistrationInfo>::operator->((__int64)v49);
    v14 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v13 + 24LL);
    v15 = ATL::CComPtrBase<IRegisteredTask>::operator&(&v44);
    Instance = v14(v13, 0, v15);
    if ( Instance < 0 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 174;
        goto LABEL_12;
      }
LABEL_80:
      v39 = 0;
      if ( v52 && v44 )
      {
        v40 = ATL::CComPtrBase<IRegistrationInfo>::operator->((__int64)&v44);
        v39 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v40 + 128LL))(v40, v47);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( Instance >= 0 && v39 < 0 )
        Instance = v39;
      goto LABEL_86;
    }
    v16 = ATL::CComPtrBase<IRegistrationInfo>::operator->((__int64)&v44);
    Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 32LL))(v16);
    if ( Instance < 0 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 175;
        goto LABEL_12;
      }
      goto LABEL_80;
    }
    ATL::CComObject<BlbVdsAdviseSink>::CreateInstance(&v42);
    v17 = v42;
    if ( !v42 )
    {
      Instance = -2147024882;
      goto LABEL_88;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 8LL))(v42);
    EventW = CreateEventW(0, 1, 0, 0);
    v19 = ATL::CComPtrBase<IRegistrationInfo>::operator->((__int64)&v42);
    if ( *(_QWORD *)(v19 + 64) )
      BlbAssert("base\\stor\\blb\\engine\\blbengutils\\Blbvhdhelper.h", 0x43u, "this->m_handle == NULL");
    *(_QWORD *)(v19 + 64) = EventW;
    v20 = (struct IUnknown **)(ATL::CComPtrBase<IRegistrationInfo>::operator->((__int64)&v42) + 72);
    if ( *v20 != v44 )
      ATL::AtlComPtrAssign(v20, v44);
    v21 = ATL::CComPtrBase<IRegistrationInfo>::operator->((__int64)&v42);
    EnterCriticalSection((LPCRITICAL_SECTION)(v21 + 88));
    v22 = ATL::CComPtrBase<IRegistrationInfo>::operator->((__int64)&v44);
    Instance = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v22 + 120LL))(v22, v17, &v47);
    if ( Instance >= 0 )
    {
      v52 = 1;
      v23 = (unsigned __int16 **)operator new(0x10u);
      v24 = v23;
      *(_QWORD *)&Buf2.Data1 = v23;
      if ( v23 )
      {
        *v23 = 0;
        v23[1] = (unsigned __int16 *)-1LL;
        v25 = 1;
        v26 = CBlbVhdHelper::_ConvertBlbVhdMountFlags(1);
        Instance = CBlbVhd::Initialize(
                     v24,
                     a1,
                     a2,
                     (VIRTUAL_DISK_ACCESS_MASK)((v26 & 1) != 0 ? VIRTUAL_DISK_ACCESS_READ : VIRTUAL_DISK_ACCESS_ALL));
        if ( Instance < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids);
          }
          goto LABEL_72;
        }
        Instance = CBlbVhd::MountVHD((CBlbVhd *)v24, v27, v26, (unsigned __int16 **)&lpFileName);
        if ( Instance < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids);
          }
          v8 = (WCHAR *)lpFileName;
          goto LABEL_72;
        }
        v28 = ATL::CComPtrBase<IRegistrationInfo>::operator->((__int64)&v42);
        v8 = (WCHAR *)lpFileName;
        *(_QWORD *)(v28 + 80) = lpFileName;
        v29 = ATL::CComPtrBase<IRegistrationInfo>::operator->((__int64)&v42);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v29 + 88));
        v25 = 0;
        v30 = ATL::CComPtrBase<IRegistrationInfo>::operator->((__int64)&v42);
        if ( WaitForSingleObject(*(HANDLE *)(v30 + 64), 0x1D4C0u) )
        {
          Instance = -2147024890;
          goto LABEL_72;
        }
        Instance = BlbModifyDiskAttributes(v8, 3u, 0);
        if ( Instance >= 0 )
        {
          v51.Version = GET_VIRTUAL_DISK_INFO_SIZE;
          Instance = CBlbVhd::GetVhdDiskInfo((CBlbVhd *)v24, v27, &v51);
          if ( Instance < 0 )
          {
            v31 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_72;
            }
            v32 = 180;
            v33 = (int)a2;
LABEL_50:
            WPP_SF_Sd(v31[2], v32, (unsigned int)&WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids, v33, Instance);
            goto LABEL_72;
          }
          Instance = CBlbVhdHelper::_GetMountedVhdDiskNumber(v8, &v46);
          if ( Instance >= 0 )
          {
            Data1 = v51.Identifier.Data1;
            v35 = (CBlbVdsHelperLibrary *)operator new(0x58u);
            v36 = v35;
            *(_QWORD *)&Buf2.Data1 = v35;
            if ( v35 )
            {
              *(_QWORD *)v35 = 0;
              *((_QWORD *)v35 + 1) = 0;
              *((_QWORD *)v35 + 2) = 0;
              *((_QWORD *)v35 + 3) = 0;
              *((_QWORD *)v35 + 4) = 0;
              *((_DWORD *)v35 + 10) = 10;
              *((_QWORD *)v35 + 7) = 0;
              *((_DWORD *)v35 + 16) = 0;
              *((_QWORD *)v35 + 9) = 0;
              *((_BYTE *)v35 + 80) = 0;
              *((_DWORD *)v35 + 12) = 0;
              Buf2.Data1 = Data1;
              Buf2.Data2 = v46;
              *(_QWORD *)&Buf2.Data3 = *(_QWORD *)&GUID_NULL.Data3;
              *(_WORD *)&Buf2.Data4[6] = v43;
              Instance = CBlbVdsHelperLibrary::FormatAndCreateSinglePartition(
                           v35,
                           &Buf2,
                           a3,
                           a4,
                           String1,
                           (unsigned __int16 **)&pv);
              if ( Instance >= 0 )
              {
                Instance = CBlbVhdHelper::_AddVhdContext((struct CBlbVhd *)v24, (const unsigned __int16 *)pv, a2, 0);
                if ( Instance >= 0 )
                {
                  v24 = 0;
                  *a6 = (unsigned __int16 *)pv;
                  pv = 0;
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids);
                }
              }
              CBlbVdsHelperLibrary::`scalar deleting destructor'(v36, v37);
              if ( !v24 )
                goto LABEL_79;
            }
            else
            {
              Instance = -2147024882;
            }
LABEL_72:
            CBlbVhd::`scalar deleting destructor'((CBlbVhd *)v24, (unsigned int)v27);
            if ( !v25 )
              goto LABEL_79;
            goto LABEL_78;
          }
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_72;
          }
          v32 = 181;
        }
        else
        {
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_72;
          }
          v32 = 179;
        }
        v33 = (int)v8;
        goto LABEL_50;
      }
      Instance = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids);
      }
    }
LABEL_78:
    v38 = ATL::CComPtrBase<IRegistrationInfo>::operator->((__int64)&v42);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v38 + 88));
LABEL_79:
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_80;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_80;
  }
  v12 = 173;
LABEL_12:
  WPP_SF_d(v11[2], v12, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids);
  v11 = (PVOID *)WPP_GLOBAL_Control;
LABEL_86:
  if ( !v8 )
    goto LABEL_89;
  CoTaskMemFree(v8);
LABEL_88:
  v11 = (PVOID *)WPP_GLOBAL_Control;
LABEL_89:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 4u )
    WPP_SF_(v11[2], 183, &WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v44);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v49);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v42);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140109f18  mov     rax, rsp
0x140109f1b  mov     [rax+8], rbx
0x140109f1f  mov     [rax+20h], r9b
0x140109f23  mov     [rax+18h], r8
0x140109f27  push    rbp
0x140109f28  push    rsi
0x140109f29  push    rdi
0x140109f2a  push    r12
0x140109f2c  push    r13
0x140109f2e  push    r14
0x140109f30  push    r15
0x140109f32  lea     rbp, [rax-4Fh]
0x140109f36  sub     rsp, 0B0h
0x140109f3d  movaps  xmmword ptr [rax-48h], xmm6
0x140109f41  mov     r15, rdx
0x140109f44  mov     r13, rcx
0x140109f47  lea     rsi, WPP_GLOBAL_Control
0x140109f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140109f55  cmp     rcx, rsi
0x140109f58  jz      short loc_140109F7B
0x140109f5a  test    byte ptr [rcx+1Ch], 1
0x140109f5e  jz      short loc_140109F7B
0x140109f60  cmp     byte ptr [rcx+19h], 4
0x140109f64  jb      short loc_140109F7B
0x140109f66  mov     edx, 0ACh
0x140109f6b  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x140109f72  mov     rcx, [rcx+10h]
0x140109f76  call    WPP_SF_
0x140109f7b  xor     r12d, r12d
0x140109f7e  mov     r14d, r12d
0x140109f81  mov     [rbp+47h+lpFileName], r12
0x140109f85  xorps   xmm0, xmm0
0x140109f88  movups  xmmword ptr [rbp+47h+var_60.Version], xmm0
0x140109f8c  movups  xmmword ptr [rbp+47h+var_60.8+8], xmm0
0x140109f90  mov     [rbp+47h+pv], r12
0x140109f94  mov     [rbp+47h+var_90], r12d
0x140109f98  movsd   xmm6, qword ptr cs:GUID_NULL.Data3
0x140109fa0  movzx   eax, word ptr cs:GUID_NULL.Data4+6
0x140109fa7  mov     [rbp+47h+var_A8], ax
0x140109fab  mov     [rbp+47h+var_B0], r12
0x140109faf  mov     [rbp+47h+var_8C], r12d
0x140109fb3  mov     [rbp+47h+arg_8], r12b
0x140109fb7  test    r15, r15
0x140109fba  jnz     short loc_140109FD4
0x140109fbc  lea     r8, aWszvhdfile; "wszVhdFile"
0x140109fc3  mov     edx, 0CDCh; unsigned int
0x140109fc8  lea     rcx, aBaseStorBlbEng_8; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x140109fcf  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140109fd4  xorps   xmm0, xmm0
0x140109fd7  movups  xmmword ptr [rbp+47h+var_60.Version], xmm0
0x140109fdb  movups  xmmword ptr [rbp+47h+var_60.8+8], xmm0
0x140109fdf  mov     [rbp+47h+var_80], r12
0x140109fe3  mov     [rbp+47h+var_A0], r12
0x140109fe7  lea     rcx, [rbp+47h+var_80]
0x140109feb  call    ??I?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAAPEAPEAUIRegisteredTask@@XZ; ATL::CComPtrBase<IRegisteredTask>::operator&(void)
0x140109ff0  mov     [rsp+0E0h+ppv], rax; ppv
0x140109ff5  lea     r9, IID_IVdsServiceLoader; riid
0x140109ffc  xor     edx, edx; pUnkOuter
0x140109ffe  mov     r8d, 10004h; dwClsContext
0x14010a004  lea     rcx, CLSID_VdsLoader; rclsid
0x14010a00b  call    cs:__imp_CoCreateInstance
0x14010a011  mov     ebx, eax
0x14010a013  test    eax, eax
0x14010a015  jns     short loc_14010A05F
0x14010a017  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a01e  cmp     rcx, rsi
0x14010a021  jz      loc_14010A5AA
0x14010a027  test    byte ptr [rcx+1Ch], 1
0x14010a02b  jz      loc_14010A5AA
0x14010a031  cmp     byte ptr [rcx+19h], 2
0x14010a035  jb      loc_14010A5AA
0x14010a03b  mov     edx, 0ADh
0x14010a040  mov     r9d, eax
0x14010a043  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x14010a04a  mov     rcx, [rcx+10h]
0x14010a04e  call    WPP_SF_d
0x14010a053  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a05a  jmp     loc_14010A5EA
0x14010a05f  lea     rcx, [rbp+47h+var_80]
0x14010a063  call    ??C?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIRegistrationInfo@@@1@XZ; ATL::CComPtrBase<IRegistrationInfo>::operator->(void)
0x14010a068  mov     rdi, rax
0x14010a06b  mov     rcx, [rax]
0x14010a06e  mov     rbx, [rcx+18h]
0x14010a072  lea     rcx, [rbp+47h+var_A0]
0x14010a076  call    ??I?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAAPEAPEAUIRegisteredTask@@XZ; ATL::CComPtrBase<IRegisteredTask>::operator&(void)
0x14010a07b  mov     r8, rax
0x14010a07e  xor     edx, edx
0x14010a080  mov     rcx, rdi
0x14010a083  mov     rax, rbx
0x14010a086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010a08b  mov     ebx, eax
0x14010a08d  test    eax, eax
0x14010a08f  jns     short loc_14010A0BC
0x14010a091  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a098  cmp     rcx, rsi
0x14010a09b  jz      loc_14010A5AA
0x14010a0a1  test    byte ptr [rcx+1Ch], 1
0x14010a0a5  jz      loc_14010A5AA
0x14010a0ab  cmp     byte ptr [rcx+19h], 2
0x14010a0af  jb      loc_14010A5AA
0x14010a0b5  mov     edx, 0AEh
0x14010a0ba  jmp     short loc_14010A040
0x14010a0bc  lea     rcx, [rbp+47h+var_A0]
0x14010a0c0  call    ??C?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIRegistrationInfo@@@1@XZ; ATL::CComPtrBase<IRegistrationInfo>::operator->(void)
0x14010a0c5  mov     rdx, rax
0x14010a0c8  mov     rcx, [rax]
0x14010a0cb  mov     rax, [rcx+20h]
0x14010a0cf  mov     rcx, rdx
0x14010a0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010a0d7  mov     ebx, eax
0x14010a0d9  test    eax, eax
0x14010a0db  jns     short loc_14010A10B
0x14010a0dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a0e4  cmp     rcx, rsi
0x14010a0e7  jz      loc_14010A5AA
0x14010a0ed  test    byte ptr [rcx+1Ch], 1
0x14010a0f1  jz      loc_14010A5AA
0x14010a0f7  cmp     byte ptr [rcx+19h], 2
0x14010a0fb  jb      loc_14010A5AA
0x14010a101  mov     edx, 0AFh
0x14010a106  jmp     loc_14010A040
0x14010a10b  lea     rcx, [rbp+47h+var_B0]
0x14010a10f  call    ?CreateInstance@?$CComObject@VBlbVdsAdviseSink@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<BlbVdsAdviseSink>::CreateInstance(ATL::CComObject<BlbVdsAdviseSink> * *)
0x14010a114  mov     rbx, [rbp+47h+var_B0]
0x14010a118  test    rbx, rbx
0x14010a11b  jnz     short loc_14010A127
0x14010a11d  mov     ebx, 8007000Eh
0x14010a122  jmp     loc_14010A5F8
0x14010a127  mov     rax, [rbx]
0x14010a12a  mov     rcx, rbx
0x14010a12d  mov     rax, [rax+8]
0x14010a131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010a136  xor     r9d, r9d; lpName
0x14010a139  xor     r8d, r8d; bInitialState
0x14010a13c  lea     edx, [r9+1]; bManualReset
0x14010a140  xor     ecx, ecx; lpEventAttributes
0x14010a142  call    cs:__imp_CreateEventW
0x14010a148  mov     rsi, rax
0x14010a14b  lea     rcx, [rbp+47h+var_B0]
0x14010a14f  call    ??C?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIRegistrationInfo@@@1@XZ; ATL::CComPtrBase<IRegistrationInfo>::operator->(void)
0x14010a154  mov     rdi, rax
0x14010a157  cmp     [rax+40h], r12
0x14010a15b  jz      short loc_14010A175
0x14010a15d  lea     r8, aThisMHandleNul; "this->m_handle == NULL"
0x14010a164  mov     edx, 43h ; 'C'; unsigned int
0x14010a169  lea     rcx, aBaseStorBlbEng_19; "base\\stor\\blb\\engine\\blbengutils\\B"...
0x14010a170  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14010a175  mov     [rdi+40h], rsi
0x14010a179  lea     rcx, [rbp+47h+var_B0]
0x14010a17d  call    ??C?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIRegistrationInfo@@@1@XZ; ATL::CComPtrBase<IRegistrationInfo>::operator->(void)
0x14010a182  mov     rdx, [rbp+47h+var_A0]; struct IUnknown *
0x14010a186  lea     rcx, [rax+48h]; struct IUnknown **
0x14010a18a  cmp     [rcx], rdx
0x14010a18d  jz      short loc_14010A194
0x14010a18f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x14010a194  lea     rcx, [rbp+47h+var_B0]
0x14010a198  call    ??C?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIRegistrationInfo@@@1@XZ; ATL::CComPtrBase<IRegistrationInfo>::operator->(void)
0x14010a19d  lea     rcx, [rax+58h]; lpCriticalSection
0x14010a1a1  call    cs:__imp_EnterCriticalSection
0x14010a1a7  lea     rcx, [rbp+47h+var_A0]
0x14010a1ab  call    ??C?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIRegistrationInfo@@@1@XZ; ATL::CComPtrBase<IRegistrationInfo>::operator->(void)
0x14010a1b0  mov     r9, rax
0x14010a1b3  mov     rcx, [rax]
0x14010a1b6  mov     rax, [rcx+78h]
0x14010a1ba  lea     r8, [rbp+47h+var_8C]
0x14010a1be  mov     rdx, rbx
0x14010a1c1  mov     rcx, r9
0x14010a1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010a1c9  mov     ebx, eax
0x14010a1cb  test    eax, eax
0x14010a1cd  js      loc_14010A589
0x14010a1d3  mov     [rbp+47h+arg_8], 1
0x14010a1d7  mov     ecx, 10h; Size
0x14010a1dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14010a1e1  mov     rsi, rax
0x14010a1e4  mov     qword ptr [rbp+47h+Buf2.Data1], rax
0x14010a1e8  test    rax, rax
0x14010a1eb  jz      loc_14010A54B
0x14010a1f1  mov     [rax], r12
0x14010a1f4  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x14010a1fc  test    rax, rax
0x14010a1ff  jz      loc_14010A54B
0x14010a205  mov     r12b, 1
0x14010a208  mov     ecx, 1; unsigned int
0x14010a20d  call    ?_ConvertBlbVhdMountFlags@CBlbVhdHelper@@CAKK@Z; CBlbVhdHelper::_ConvertBlbVhdMountFlags(ulong)
0x14010a212  mov     edi, eax
0x14010a214  mov     ecx, eax
0x14010a216  and     cl, r12b
0x14010a219  neg     cl
0x14010a21b  sbb     r9d, r9d
0x14010a21e  and     r9d, 0FFCE0000h
0x14010a225  add     r9d, 3F0000h; VirtualDiskAccessMask
0x14010a22c  mov     r8, r15; Path
0x14010a22f  mov     rdx, r13; struct CBlbImpersonationHelper *
0x14010a232  mov     rcx, rsi; this
0x14010a235  call    ?Initialize@CBlbVhd@@QEAAJPEAVCBlbImpersonationHelper@@PEBGK@Z; CBlbVhd::Initialize(CBlbImpersonationHelper *,ushort const *,ulong)
0x14010a23a  mov     ebx, eax
0x14010a23c  xor     r13d, r13d
0x14010a23f  test    eax, eax
0x14010a241  jns     short loc_14010A28B
0x14010a243  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a24a  lea     rax, WPP_GLOBAL_Control
0x14010a251  cmp     rcx, rax
0x14010a254  jz      loc_14010A532
0x14010a25a  test    [rcx+1Ch], r12b
0x14010a25e  jz      loc_14010A532
0x14010a264  cmp     byte ptr [rcx+19h], 2
0x14010a268  jb      loc_14010A532
0x14010a26e  mov     edx, 0B1h
0x14010a273  mov     r9d, ebx
0x14010a276  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x14010a27d  mov     rcx, [rcx+10h]
0x14010a281  call    WPP_SF_d
0x14010a286  jmp     loc_14010A532
0x14010a28b  lea     r9, [rbp+47h+lpFileName]; unsigned __int16 **
0x14010a28f  mov     r8d, edi; unsigned int
0x14010a292  mov     rcx, rsi; this
0x14010a295  call    ?MountVHD@CBlbVhd@@QEAAJPEAVCBlbImpersonationHelper@@KPEAPEAG@Z; CBlbVhd::MountVHD(CBlbImpersonationHelper *,ulong,ushort * *)
0x14010a29a  mov     ebx, eax
0x14010a29c  test    eax, eax
0x14010a29e  jns     short loc_14010A2E0
0x14010a2a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a2a7  lea     rax, WPP_GLOBAL_Control
0x14010a2ae  cmp     rcx, rax
0x14010a2b1  jz      short loc_14010A2D7
0x14010a2b3  test    [rcx+1Ch], r12b
0x14010a2b7  jz      short loc_14010A2D7
0x14010a2b9  cmp     byte ptr [rcx+19h], 2
0x14010a2bd  jb      short loc_14010A2D7
0x14010a2bf  mov     edx, 0B2h
0x14010a2c4  mov     r9d, ebx
0x14010a2c7  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x14010a2ce  mov     rcx, [rcx+10h]
0x14010a2d2  call    WPP_SF_d
0x14010a2d7  mov     r14, [rbp+47h+lpFileName]
0x14010a2db  jmp     loc_14010A532
0x14010a2e0  lea     rcx, [rbp+47h+var_B0]
0x14010a2e4  call    ??C?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIRegistrationInfo@@@1@XZ; ATL::CComPtrBase<IRegistrationInfo>::operator->(void)
0x14010a2e9  mov     r14, [rbp+47h+lpFileName]
0x14010a2ed  mov     [rax+50h], r14
0x14010a2f1  lea     rcx, [rbp+47h+var_B0]
0x14010a2f5  call    ??C?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIRegistrationInfo@@@1@XZ; ATL::CComPtrBase<IRegistrationInfo>::operator->(void)
0x14010a2fa  lea     rcx, [rax+58h]; lpCriticalSection
0x14010a2fe  call    cs:__imp_LeaveCriticalSection
0x14010a304  mov     r12b, r13b
0x14010a307  lea     rcx, [rbp+47h+var_B0]
0x14010a30b  call    ??C?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIRegistrationInfo@@@1@XZ; ATL::CComPtrBase<IRegistrationInfo>::operator->(void)
0x14010a310  mov     edx, 1D4C0h; dwMilliseconds
0x14010a315  mov     rcx, [rax+40h]; hHandle
0x14010a319  call    cs:__imp_WaitForSingleObject
0x14010a31f  test    eax, eax
0x14010a321  jz      short loc_14010A32D
0x14010a323  mov     ebx, 80070006h
0x14010a328  jmp     loc_14010A532
0x14010a32d  xor     r8d, r8d; unsigned __int8
0x14010a330  lea     edx, [r8+3]; unsigned int
0x14010a334  mov     rcx, r14; lpFileName
0x14010a337  call    ?BlbModifyDiskAttributes@@YAJPEBGKE@Z; BlbModifyDiskAttributes(ushort const *,ulong,uchar)
0x14010a33c  mov     ebx, eax
0x14010a33e  test    eax, eax
0x14010a340  jns     short loc_14010A38E
0x14010a342  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a349  lea     rax, WPP_GLOBAL_Control
0x14010a350  cmp     rcx, rax
0x14010a353  jz      loc_14010A532
0x14010a359  test    byte ptr [rcx+1Ch], 1
0x14010a35d  jz      loc_14010A532
0x14010a363  cmp     byte ptr [rcx+19h], 2
0x14010a367  jb      loc_14010A532
0x14010a36d  mov     edx, 0B3h
0x14010a372  mov     r9, r14
0x14010a375  mov     dword ptr [rsp+0E0h+ppv], ebx
0x14010a379  lea     r8, WPP_0619bbd85a9d310cc95ab1c924db12f6_Traceguids
0x14010a380  mov     rcx, [rcx+10h]
0x14010a384  call    WPP_SF_Sd
0x14010a389  jmp     loc_14010A532
0x14010a38e  mov     [rbp+47h+var_60.Version], 1
0x14010a395  lea     r8, [rbp+47h+var_60]; struct _GET_VIRTUAL_DISK_INFO *
0x14010a399  mov     rcx, rsi; this
0x14010a39c  call    ?GetVhdDiskInfo@CBlbVhd@@QEAAJPEAVCBlbImpersonationHelper@@PEAU_GET_VIRTUAL_DISK_INFO@@@Z; CBlbVhd::GetVhdDiskInfo(CBlbImpersonationHelper *,_GET_VIRTUAL_DISK_INFO *)
0x14010a3a1  mov     ebx, eax
0x14010a3a3  test    eax, eax
0x14010a3a5  jns     short loc_14010A3DC
0x14010a3a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14010a3ae  lea     rax, WPP_GLOBAL_Control
0x14010a3b5  cmp     rcx, rax
0x14010a3b8  jz      loc_14010A532
0x14010a3be  test    byte ptr [rcx+1Ch], 1
0x14010a3c2  jz      loc_14010A532
0x14010a3c8  cmp     byte ptr [rcx+19h], 2
0x14010a3cc  jb      loc_14010A532
0x14010a3d2  mov     edx, 0B4h
0x14010a3d7  mov     r9, r15
0x14010a3da  jmp     short loc_14010A375
0x14010a3dc  lea     rdx, [rbp+47h+var_90]; unsigned int *
0x14010a3e0  mov     rcx, r14; lpFileName
0x14010a3e3  call    ?_GetMountedVhdDiskNumber@CBlbVhdHelper@@CAJPEAGPEAK@Z; CBlbVhdHelper::_GetMountedVhdDiskNumber(ushort *,ulong *)
0x14010a3e8  mov     ebx, eax
0x14010a3ea  test    eax, eax
0x14010a3ec  jns     short loc_14010A423
  ... truncated ...
```
