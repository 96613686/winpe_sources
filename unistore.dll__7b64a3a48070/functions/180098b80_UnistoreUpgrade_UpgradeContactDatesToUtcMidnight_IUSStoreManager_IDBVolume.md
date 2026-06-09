# UnistoreUpgrade::UpgradeContactDatesToUtcMidnight(IUSStoreManager *,IDBVolume *)

- ea: `0x180098b80`
- end: `0x18009905e`
- name: `?UpgradeContactDatesToUtcMidnight@UnistoreUpgrade@@YAJPEAUIUSStoreManager@@PEAVIDBVolume@@@Z`
- size: `1246`
- prototype: `__int64 __fastcall(UnistoreUpgrade *__hidden this, struct IUSStoreManager *, struct IDBVolume *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x18001e2f4`
- `0x180034664`
- `0x180035d40`
- `0x1800576c0`
- `0x180059828`
- `0x180098b80`
- `0x1800c50aa`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098ed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098f23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098ed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098f23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098ec2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098f10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098f61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098ec2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098f10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098f61`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x180098bce`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x180098bce`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180098dc8`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180098dc8`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180098d96`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180098d96`
- `UserDataTimeUtil!AdjustForBias` at `0x180098d76`
- `UserDataTimeUtil!AdjustForBias` at `0x180098d76`
- `UserDataTimeUtil!RoundEventTime` at `0x180098da8`
- `UserDataTimeUtil!RoundEventTime` at `0x180098da8`

## string_xrefs

- `0x180098bf4`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180098ef6`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180098f46`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180098f87`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180098fdd`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009901a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`

## pseudocode

```c
__int64 __fastcall UnistoreUpgrade::UpgradeContactDatesToUtcMidnight(
        UnistoreUpgrade *this,
        struct IUSStoreManager *a2,
        struct IDBVolume *a3)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, _DWORD *); // rbx
  int v15; // eax
  _WORD *v16; // rax
  __int64 v17; // r14
  __int64 v18; // rbx
  int v19; // edi
  __int64 v20; // rdx
  int started; // eax
  __int64 v22; // rdx
  signed int v23; // eax
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r9
  signed int v28; // eax
  __int64 v29; // r9
  __int64 v30; // rcx
  __int64 v31; // r9
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  int v36; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v37[8]; // [rsp+60h] [rbp-A0h] BYREF
  int v38; // [rsp+68h] [rbp-98h]
  _DWORD v39[2]; // [rsp+70h] [rbp-90h] BYREF
  FILETIME FileTime; // [rsp+78h] [rbp-88h] BYREF
  struct _FILETIME v41; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v42[2]; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v43[3]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v44; // [rsp+C0h] [rbp-40h] BYREF
  int v45; // [rsp+C8h] [rbp-38h]
  struct _SYSTEMTIME SystemTime; // [rsp+D0h] [rbp-30h] BYREF
  _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
  if ( GetTimeZoneInformation(&TimeZoneInformation) == -1 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    Log_UnistoreHREvent_0(
      v6,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
      902);
    return v6;
  }
  v7 = *(_QWORD *)this;
  v35 = 0;
  v8 = (*(__int64 (__fastcall **)(UnistoreUpgrade *, __int64, _QWORD))(v7 + 136))(this, 1, 0);
  v6 = v8;
  if ( v8 < 0 )
  {
    v9 = 905;
    v10 = 1;
    v11 = (unsigned int)v8;
    goto LABEL_60;
  }
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 120LL))(v35);
  while ( 1 )
  {
    if ( v6 )
    {
      if ( v6 == -2147024871 )
      {
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v35);
        return 0;
      }
      v9 = 963;
      v10 = 0;
      v11 = v6;
LABEL_60:
      Log_UnistoreHREvent_0(
        v11,
        v10,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
        v9);
      goto LABEL_61;
    }
    v33 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 40LL))(v35, &v33);
    v6 = v12;
    if ( v12 < 0 )
    {
      v31 = 911;
      goto LABEL_55;
    }
    v44 = 0;
    v45 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 24LL))(v33, &v44);
    v6 = v12;
    if ( v12 < 0 )
    {
      v31 = 914;
LABEL_55:
      Log_UnistoreHREvent_0(
        (unsigned int)v12,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
        v31);
LABEL_56:
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v33);
      goto LABEL_61;
    }
    v13 = v33;
    v39[0] = 15728704;
    v39[1] = 15794240;
    hMem = 0;
    v14 = *(__int64 (__fastcall **)(__int64, __int64, _DWORD *))(*(_QWORD *)v33 + 48LL);
    tlx::replace<_USPROPVAL,&void _LocalFreer<_USPROPVAL>(_USPROPVAL *)>(&hMem);
    v15 = v14(v13, 2, v39);
    v6 = v15;
    if ( v15 < 0 )
    {
      v24 = 918;
      v25 = 1;
      v26 = (unsigned int)v15;
LABEL_34:
      Log_UnistoreHREvent_0(
        v26,
        v25,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
        v24);
LABEL_35:
      if ( hMem )
        LocalFree(hMem);
      goto LABEL_56;
    }
    v16 = hMem;
    v17 = 0;
    memset(v43, 0, sizeof(v43));
    v18 = 0;
LABEL_13:
    if ( (unsigned int)v18 < 2 )
      break;
    if ( (_DWORD)v17 )
    {
      v42[0] = v44;
      v42[1] = 2147483643;
      ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(v37, a2);
      v38 = 0;
      started = DBAutoTopLevelTransact::StartTransaction(
                  (DBAutoTopLevelTransact *)v37,
                  3u,
                  2u,
                  (const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *)v42);
      v6 = started;
      if ( started < 0 )
      {
        v29 = 952;
LABEL_48:
        v22 = 1;
LABEL_49:
        v30 = (unsigned int)started;
        goto LABEL_46;
      }
      started = (*(__int64 (__fastcall **)(__int64, _QWORD, _OWORD *, _QWORD))(*(_QWORD *)v33 + 80LL))(
                  v33,
                  (unsigned int)v17,
                  v43,
                  0);
      v6 = started;
      v22 = 1;
      if ( started < 0 )
      {
        v29 = 954;
        goto LABEL_49;
      }
      v36 = 0;
      started = DBAutoTopLevelTransact::EndTransaction((DBAutoTopLevelTransact *)v37, 1, &v36);
      v6 = started;
      if ( started < 0 )
      {
        v29 = 957;
        goto LABEL_48;
      }
      if ( !v36 )
      {
        v6 = -2147418113;
        v29 = 958;
        v30 = 2147549183LL;
        v22 = 0;
LABEL_46:
        Log_UnistoreHREvent_0(
          v30,
          v22,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          v29);
        DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)v37);
        goto LABEL_35;
      }
      DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)v37);
    }
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 96LL))(v35);
    if ( hMem )
      LocalFree(hMem);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v33);
  }
  if ( (v16[12 * v18 + 3] & 0x300) != 0 )
    goto LABEL_20;
  FileTime = 0;
  v19 = AdjustForBias(&v16[12 * v18 + 4], 0, 0, &FileTime);
  if ( v19 >= 0 )
  {
    SystemTime = 0;
    if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
    {
      v28 = GetLastError();
      v6 = v28;
      if ( v28 > 0 )
        v6 = (unsigned __int16)v28 | 0x80070000;
      v24 = 930;
      goto LABEL_33;
    }
    v19 = RoundEventTime(&SystemTime);
    if ( v19 < 0 )
    {
      v27 = 931;
      goto LABEL_42;
    }
    v41 = 0;
    if ( !SystemTimeToFileTime(&SystemTime, &v41) )
    {
      v23 = GetLastError();
      v6 = v23;
      if ( v23 > 0 )
        v6 = (unsigned __int16)v23 | 0x80070000;
      v24 = 934;
LABEL_33:
      v25 = 0;
      v26 = v6;
      goto LABEL_34;
    }
    v16 = hMem;
    v20 = 3 * v17;
    v17 = (unsigned int)(v17 + 1);
    *((_DWORD *)v43 + 2 * v20) = *((_DWORD *)hMem + 6 * v18);
    *((struct _FILETIME *)v43 + v20 + 1) = v41;
LABEL_20:
    v18 = (unsigned int)(v18 + 1);
    goto LABEL_13;
  }
  v27 = 927;
LABEL_42:
  Log_UnistoreHREvent_0(
    (unsigned int)v19,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
    v27);
  if ( hMem )
    LocalFree(hMem);
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v33);
  v6 = v19;
LABEL_61:
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v35);
  return v6;
}

```

## disassembly

```asm
0x180098b80  mov     [rsp-8+arg_10], rbx
0x180098b85  mov     [rsp-8+arg_18], rdi
0x180098b8a  push    rbp
0x180098b8b  push    r12
0x180098b8d  push    r13
0x180098b8f  push    r14
0x180098b91  push    r15
0x180098b93  lea     rbp, [rsp-0A0h]
0x180098b9b  sub     rsp, 1A0h
0x180098ba2  mov     rax, cs:__security_cookie
0x180098ba9  xor     rax, rsp
0x180098bac  mov     [rbp+0C0h+var_30], rax
0x180098bb3  mov     r12, rdx
0x180098bb6  mov     rbx, rcx
0x180098bb9  xor     edx, edx; Val
0x180098bbb  lea     rcx, [rbp+0C0h+TimeZoneInformation]; void *
0x180098bbf  mov     r8d, 0ACh; Size
0x180098bc5  call    memset_0
0x180098bca  lea     rcx, [rbp+0C0h+TimeZoneInformation]; lpTimeZoneInformation
0x180098bce  call    cs:__imp_GetTimeZoneInformation
0x180098bd4  cmp     eax, 0FFFFFFFFh
0x180098bd7  jnz     short loc_180098C09
0x180098bd9  call    cs:__imp_GetLastError
0x180098bdf  mov     ebx, eax
0x180098be1  test    eax, eax
0x180098be3  jle     short loc_180098BEE
0x180098be5  movzx   ebx, ax
0x180098be8  or      ebx, 80070000h
0x180098bee  mov     r9d, 386h
0x180098bf4  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180098bfb  xor     edx, edx
0x180098bfd  mov     ecx, ebx
0x180098bff  call    Log_UnistoreHREvent_0
0x180098c04  jmp     loc_180099030
0x180098c09  mov     rax, [rbx]
0x180098c0c  lea     rcx, [rsp+1C0h+var_170]
0x180098c11  mov     [rsp+1C0h+var_190], rcx
0x180098c16  xor     r9d, r9d
0x180098c19  mov     [rsp+1C0h+var_198], 0
0x180098c22  xor     r8d, r8d
0x180098c25  mov     rcx, rbx
0x180098c28  mov     [rsp+1C0h+var_170], 0
0x180098c31  mov     rax, [rax+88h]
0x180098c38  lea     r13d, [r9+1]
0x180098c3c  mov     [rsp+1C0h+var_1A0], 0
0x180098c45  mov     edx, r13d
0x180098c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098c4d  mov     ebx, eax
0x180098c4f  test    eax, eax
0x180098c51  jns     short loc_180098C63
0x180098c53  mov     r9d, 389h
0x180098c59  mov     edx, r13d
0x180098c5c  mov     ecx, eax
0x180098c5e  jmp     loc_18009901A
0x180098c63  mov     rcx, [rsp+1C0h+var_170]
0x180098c68  mov     rax, [rcx]
0x180098c6b  mov     rax, [rax+78h]
0x180098c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098c74  mov     ebx, eax
0x180098c76  test    ebx, ebx
0x180098c78  jnz     loc_180098FFA
0x180098c7e  mov     rcx, [rsp+1C0h+var_170]
0x180098c83  lea     rdx, [rsp+1C0h+var_180]
0x180098c88  mov     [rsp+1C0h+var_180], 0
0x180098c91  mov     rax, [rcx]
0x180098c94  mov     rax, [rax+28h]
0x180098c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098c9d  mov     ebx, eax
0x180098c9f  test    eax, eax
0x180098ca1  js      loc_180098FD7
0x180098ca7  mov     rcx, [rsp+1C0h+var_180]
0x180098cac  lea     rdx, [rbp+0C0h+var_100]
0x180098cb0  xor     eax, eax
0x180098cb2  mov     [rbp+0C0h+var_100], rax
0x180098cb6  mov     [rbp+0C0h+var_F8], eax
0x180098cb9  mov     rax, [rcx]
0x180098cbc  mov     rax, [rax+18h]
0x180098cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098cc5  mov     ebx, eax
0x180098cc7  test    eax, eax
0x180098cc9  js      loc_180098FCF
0x180098ccf  mov     rdi, [rsp+1C0h+var_180]
0x180098cd4  lea     rcx, [rsp+1C0h+hMem]
0x180098cd9  mov     [rsp+1C0h+var_150], 0F00040h
0x180098ce1  mov     [rsp+1C0h+var_14C], 0F10040h
0x180098ce9  mov     [rsp+1C0h+hMem], 0
0x180098cf2  mov     rax, [rdi]
0x180098cf5  mov     rbx, [rax+30h]
0x180098cf9  call    ??$replace@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_USPROPVAL@@AEAV?$auto_ptr@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)>(tlx::auto_ptr<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)> &)
0x180098cfe  xor     r9d, r9d
0x180098d01  mov     [rsp+1C0h+var_1A0], rax
0x180098d06  lea     r8, [rsp+1C0h+var_150]
0x180098d0b  mov     rcx, rdi
0x180098d0e  mov     rax, rbx
0x180098d11  lea     edx, [r9+2]
0x180098d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098d1a  mov     ebx, eax
0x180098d1c  test    eax, eax
0x180098d1e  js      loc_180098FBF
0x180098d24  mov     rax, [rsp+1C0h+hMem]
0x180098d29  xorps   xmm0, xmm0
0x180098d2c  xor     r14d, r14d
0x180098d2f  movups  [rbp+0C0h+var_130], xmm0
0x180098d33  xor     ebx, ebx
0x180098d35  movups  [rbp+0C0h+var_120], xmm0
0x180098d39  movups  [rbp+0C0h+var_110], xmm0
0x180098d3d  cmp     ebx, 2
0x180098d40  jnb     loc_180098DFB
0x180098d46  lea     r15, [rbx+rbx*2]
0x180098d4a  mov     ecx, 300h
0x180098d4f  test    [rax+r15*8+6], cx
0x180098d55  jnz     loc_180098DF3
0x180098d5b  lea     rcx, [rax+8]
0x180098d5f  mov     qword ptr [rsp+1C0h+FileTime.dwLowDateTime], 0
0x180098d68  lea     rcx, [rcx+r15*8]
0x180098d6c  xor     r8d, r8d
0x180098d6f  lea     r9, [rsp+1C0h+FileTime]
0x180098d74  xor     edx, edx
0x180098d76  call    cs:__imp_AdjustForBias
0x180098d7c  mov     edi, eax
0x180098d7e  test    eax, eax
0x180098d80  js      loc_180098F40
0x180098d86  xorps   xmm0, xmm0
0x180098d89  lea     rdx, [rbp+0C0h+SystemTime]; lpSystemTime
0x180098d8d  lea     rcx, [rsp+1C0h+FileTime]; lpFileTime
0x180098d92  movups  xmmword ptr [rbp+0C0h+SystemTime.wYear], xmm0
0x180098d96  call    cs:__imp_FileTimeToSystemTime
0x180098d9c  test    eax, eax
0x180098d9e  jz      loc_180098F23
0x180098da4  lea     rcx, [rbp+0C0h+SystemTime]
0x180098da8  call    cs:__imp_RoundEventTime
0x180098dae  mov     edi, eax
0x180098db0  test    eax, eax
0x180098db2  js      loc_180098F1B
0x180098db8  lea     rdx, [rbp+0C0h+var_140]; lpFileTime
0x180098dbc  mov     qword ptr [rbp+0C0h+var_140.dwLowDateTime], 0
0x180098dc4  lea     rcx, [rbp+0C0h+SystemTime]; lpSystemTime
0x180098dc8  call    cs:__imp_SystemTimeToFileTime
0x180098dce  test    eax, eax
0x180098dd0  jz      loc_180098ED7
0x180098dd6  mov     rax, [rsp+1C0h+hMem]
0x180098ddb  lea     rdx, [r14+r14*2]
0x180098ddf  add     r14d, r13d
0x180098de2  mov     ecx, [rax+r15*8]
0x180098de6  mov     dword ptr [rbp+rdx*8+0C0h+var_130], ecx
0x180098dea  mov     rcx, qword ptr [rbp+0C0h+var_140.dwLowDateTime]
0x180098dee  mov     qword ptr [rbp+rdx*8+0C0h+var_130+8], rcx
0x180098df3  add     ebx, r13d
0x180098df6  jmp     loc_180098D3D
0x180098dfb  test    r14d, r14d
0x180098dfe  jz      loc_180098EA5
0x180098e04  mov     eax, dword ptr [rbp+0C0h+var_100]
0x180098e07  lea     rcx, [rsp+1C0h+var_160]
0x180098e0c  mov     rdx, r12
0x180098e0f  mov     [rbp+0C0h+var_138], eax
0x180098e12  mov     [rbp+0C0h+var_134], 7FFFFFFBh
0x180098e19  call    ??0?$CComPtrBase@VIDBVolume@@@ATL@@IEAA@PEAVIDBVolume@@@Z; ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(IDBVolume *)
0x180098e1e  mov     edx, 3; unsigned int
0x180098e23  mov     [rsp+1C0h+var_158], 0
0x180098e2b  lea     r9, [rbp+0C0h+var_138]; enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *
0x180098e2f  lea     rcx, [rsp+1C0h+var_160]; this
0x180098e34  lea     r8d, [rdx-1]; unsigned int
0x180098e38  call    ?StartTransaction@DBAutoTopLevelTransact@@QEAAJKKPEBW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@@Z; DBAutoTopLevelTransact::StartTransaction(ulong,ulong,__MIDL___MIDL_itf_unistore_0000_0002_0001 const *)
0x180098e3d  mov     ebx, eax
0x180098e3f  test    eax, eax
0x180098e41  js      loc_180098FB7
0x180098e47  mov     rcx, [rsp+1C0h+var_180]
0x180098e4c  lea     r8, [rbp+0C0h+var_130]
0x180098e50  xor     r9d, r9d
0x180098e53  mov     edx, r14d
0x180098e56  mov     rax, [rcx]
0x180098e59  mov     rax, [rax+50h]
0x180098e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098e62  mov     ebx, eax
0x180098e64  mov     edx, r13d; int
0x180098e67  test    eax, eax
0x180098e69  js      loc_180098FAF
0x180098e6f  lea     r8, [rsp+1C0h+var_168]; int *
0x180098e74  mov     [rsp+1C0h+var_168], 0
0x180098e7c  lea     rcx, [rsp+1C0h+var_160]; this
0x180098e81  call    ?EndTransaction@DBAutoTopLevelTransact@@QEAAJHPEAH@Z; DBAutoTopLevelTransact::EndTransaction(int,int *)
0x180098e86  mov     ebx, eax
0x180098e88  test    eax, eax
0x180098e8a  js      loc_180098FA2
0x180098e90  cmp     [rsp+1C0h+var_168], 0
0x180098e95  jz      loc_180098F78
0x180098e9b  lea     rcx, [rsp+1C0h+var_160]; this
0x180098ea0  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x180098ea5  mov     rcx, [rsp+1C0h+var_170]
0x180098eaa  mov     rax, [rcx]
0x180098ead  mov     rax, [rax+60h]
0x180098eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098eb6  mov     rcx, [rsp+1C0h+hMem]; hMem
0x180098ebb  mov     ebx, eax
0x180098ebd  test    rcx, rcx
0x180098ec0  jz      short loc_180098EC8
0x180098ec2  call    cs:__imp_LocalFree
0x180098ec8  lea     rcx, [rsp+1C0h+var_180]; void *
0x180098ecd  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180098ed2  jmp     loc_180098C76
0x180098ed7  call    cs:__imp_GetLastError
0x180098edd  mov     ebx, eax
0x180098edf  test    eax, eax
0x180098ee1  jle     short loc_180098EEC
0x180098ee3  movzx   ebx, ax
0x180098ee6  or      ebx, 80070000h
0x180098eec  mov     r9d, 3A6h
0x180098ef2  xor     edx, edx
0x180098ef4  mov     ecx, ebx
0x180098ef6  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180098efd  call    Log_UnistoreHREvent_0
0x180098f02  mov     rcx, [rsp+1C0h+hMem]; hMem
0x180098f07  test    rcx, rcx
0x180098f0a  jz      loc_180098FEE
0x180098f10  call    cs:__imp_LocalFree
0x180098f16  jmp     loc_180098FEE
0x180098f1b  mov     r9d, 3A3h
0x180098f21  jmp     short loc_180098F46
0x180098f23  call    cs:__imp_GetLastError
0x180098f29  mov     ebx, eax
0x180098f2b  test    eax, eax
0x180098f2d  jle     short loc_180098F38
0x180098f2f  movzx   ebx, ax
0x180098f32  or      ebx, 80070000h
0x180098f38  mov     r9d, 3A2h
0x180098f3e  jmp     short loc_180098EF2
0x180098f40  mov     r9d, 39Fh
0x180098f46  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180098f4d  mov     edx, r13d
0x180098f50  mov     ecx, edi
0x180098f52  call    Log_UnistoreHREvent_0
0x180098f57  mov     rcx, [rsp+1C0h+hMem]; hMem
0x180098f5c  test    rcx, rcx
0x180098f5f  jz      short loc_180098F67
0x180098f61  call    cs:__imp_LocalFree
0x180098f67  lea     rcx, [rsp+1C0h+var_180]; void *
0x180098f6c  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180098f71  mov     ebx, edi
0x180098f73  jmp     loc_180099026
0x180098f78  mov     ebx, 8000FFFFh
0x180098f7d  mov     r9d, 3BEh
0x180098f83  mov     ecx, ebx
0x180098f85  xor     edx, edx
0x180098f87  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180098f8e  call    Log_UnistoreHREvent_0
0x180098f93  lea     rcx, [rsp+1C0h+var_160]; this
0x180098f98  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x180098f9d  jmp     loc_180098F02
0x180098fa2  mov     r9d, 3BDh
0x180098fa8  mov     edx, r13d
0x180098fab  mov     ecx, eax
0x180098fad  jmp     short loc_180098F87
0x180098faf  mov     r9d, 3BAh
0x180098fb5  jmp     short loc_180098FAB
0x180098fb7  mov     r9d, 3B8h
0x180098fbd  jmp     short loc_180098FA8
0x180098fbf  mov     r9d, 396h
0x180098fc5  mov     edx, r13d
0x180098fc8  mov     ecx, eax
0x180098fca  jmp     loc_180098EF6
0x180098fcf  mov     r9d, 392h
0x180098fd5  jmp     short loc_180098FDD
0x180098fd7  mov     r9d, 38Fh
0x180098fdd  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180098fe4  mov     edx, r13d
0x180098fe7  mov     ecx, eax
0x180098fe9  call    Log_UnistoreHREvent_0
0x180098fee  lea     rcx, [rsp+1C0h+var_180]; void *
0x180098ff3  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180098ff8  jmp     short loc_180099026
0x180098ffa  cmp     ebx, 80070019h
0x180099000  jnz     short loc_180099010
0x180099002  lea     rcx, [rsp+1C0h+var_170]; void *
0x180099007  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009900c  xor     eax, eax
0x18009900e  jmp     short loc_180099032
0x180099010  mov     r9d, 3C3h
0x180099016  xor     edx, edx
0x180099018  mov     ecx, ebx
0x18009901a  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180099021  call    Log_UnistoreHREvent_0
0x180099026  lea     rcx, [rsp+1C0h+var_170]; void *
0x18009902b  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180099030  mov     eax, ebx
0x180099032  mov     rcx, [rbp+0C0h+var_30]
0x180099039  xor     rcx, rsp; StackCookie
0x18009903c  call    __security_check_cookie
0x180099041  lea     r11, [rsp+1C0h+var_20]
0x180099049  mov     rbx, [r11+40h]
0x18009904d  mov     rdi, [r11+48h]
0x180099051  mov     rsp, r11
0x180099054  pop     r15
0x180099056  pop     r14
0x180099058  pop     r13
0x18009905a  pop     r12
0x18009905c  pop     rbp
0x18009905d  retn
```
