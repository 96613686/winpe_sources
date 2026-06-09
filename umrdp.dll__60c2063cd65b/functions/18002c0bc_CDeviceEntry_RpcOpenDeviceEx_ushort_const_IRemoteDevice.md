# CDeviceEntry::RpcOpenDeviceEx(ushort const *,IRemoteDevice * *)

- ea: `0x18002c0bc`
- end: `0x18002c5f9`
- name: `?RpcOpenDeviceEx@CDeviceEntry@@QEAAJPEBGPEAPEAUIRemoteDevice@@@Z`
- size: `1341`
- prototype: `__int64 __fastcall(CDeviceEntry *__hidden this, const unsigned __int16 *, struct IRemoteDevice **)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002b090`

## callees

- `0x180007da0`
- `0x180009fa8`
- `0x18000add8`
- `0x18000b3d0`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18000bd04`
- `0x18000bd44`
- `0x18000f79c`
- `0x1800179a8`
- `0x18001ba64`
- `0x18002a540`
- `0x18002b234`
- `0x18002b6d0`
- `0x18002c0bc`
- `0x18002c6c4`
- `0x18003fd18`
- `0x18003fd98`
- `0x180047ef0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c407`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c46f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c4e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c407`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c46f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c4e1`
- `KERNEL32!lstrcmpiW` at `0x18002c531`
- `KERNEL32!lstrcmpiW` at `0x18002c531`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c595`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c5a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c5b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c595`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c5a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c5b3`

## pseudocode

```c
__int64 __fastcall CDeviceEntry::RpcOpenDeviceEx(
        CDeviceEntry *this,
        const unsigned __int16 *a2,
        struct IRemoteDevice **a3)
{
  CTSCriticalSection *v3; // rbx
  __int64 v5; // r14
  int DeviceInfDetails; // edi
  void *v9; // rcx
  __int64 v10; // rcx
  unsigned __int16 *v11; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v13; // rdx
  WCHAR *v14; // rbx
  unsigned __int16 *v15; // r15
  unsigned int v16; // eax
  int v17; // edx
  const char *v18; // rcx
  unsigned int v19; // eax
  HKEY v20; // rdx
  unsigned int v21; // r9d
  unsigned int v22; // eax
  __int64 v23; // rdx
  const BYTE *v24; // rcx
  __int64 v25; // rcx
  unsigned __int16 *lpData; // [rsp+20h] [rbp-E0h]
  BYTE Data[8]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v29; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v31[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v32; // [rsp+58h] [rbp-A8h]
  HKEY hKey; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+68h] [rbp-98h]
  int v35; // [rsp+6Ch] [rbp-94h]
  char *v36; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v37[264]; // [rsp+80h] [rbp-80h] BYREF

  v3 = (CDeviceEntry *)((char *)this + 128);
  *(_QWORD *)Data = 0;
  pv = 0;
  v5 = -1;
  v29 = 0;
  v31[0] = &CRegistry::`vftable';
  v31[1] = 0;
  v32 = 0;
  hKey = 0;
  v34 = -1;
  v35 = -1;
  *a3 = 0;
  v36 = (char *)this + 128;
  CTSCriticalSection::Lock((CDeviceEntry *)((char *)this + 128));
  if ( (*((_BYTE *)this + 28) & 4) != 0 )
  {
    DeviceInfDetails = -2147467260;
    goto LABEL_67;
  }
  CDeviceEntry::StopTimer(this);
  v9 = (void *)*((_QWORD *)this + 11);
  if ( v9 )
    operator delete(v9);
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  v11 = (unsigned __int16 *)operator new(saturated_mul(v10 + 1, 2u));
  *((_QWORD *)this + 11) = v11;
  if ( !v11 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        30,
        (unsigned int)WPP_9f8b2618b856326daa1832c892715ef0_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"WCHAR[]");
    }
    DeviceInfDetails = -2147024882;
    goto LABEL_67;
  }
  v13 = -1;
  do
    ++v13;
  while ( a2[v13] );
  StringCchCopyW(v11, v13 + 1, a2);
  CTSCriticalSection::UnLock(v3);
  DeviceInfDetails = GetDeviceInfDetails(a2, (unsigned __int16 **)Data, (unsigned __int16 **)&pv, &v29);
  CTSCriticalSection::Lock(v3);
  v14 = *(WCHAR **)Data;
  v15 = v29;
  if ( DeviceInfDetails >= 0 )
  {
    if ( (*((_BYTE *)this + 28) & 4) != 0 )
    {
      DeviceInfDetails = -2147467260;
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          32,
          (unsigned int)WPP_9f8b2618b856326daa1832c892715ef0_Traceguids,
          v19,
          (__int64)"Terminated",
          4);
      }
      goto LABEL_61;
    }
    lpData = v29;
    DeviceInfDetails = StringCbPrintfW(v37, 0x208u, L"%s\\%s", L"SYSTEM\\CurrentControlSet\\Control\\Class");
    if ( DeviceInfDetails < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_61;
      }
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 33;
      v18 = "StringCbPrintfW";
      goto LABEL_20;
    }
    DeviceInfDetails = CRegistry::OpenKey((CRegistry *)v31, v20, v37, v21, lpData);
    if ( DeviceInfDetails )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        v23 = 34;
LABEL_36:
        WPP_SF_Dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          v23,
          WPP_9f8b2618b856326daa1832c892715ef0_Traceguids,
          v22,
          DeviceInfDetails);
      }
    }
    else
    {
      v24 = (const BYTE *)*((_QWORD *)this + 11);
      do
        ++v5;
      while ( *(_WORD *)&v24[2 * v5] );
      DeviceInfDetails = RegSetValueExW(hKey, L"TS_deviceinstanceId", 0, 1u, v24, 2 * v5 + 2);
      if ( DeviceInfDetails )
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v22 = RdpWppGetCurrentThreadActivityIdPrefix();
          v23 = 35;
          goto LABEL_36;
        }
      }
      else
      {
        *(_DWORD *)Data = *((_DWORD *)this + 17);
        DeviceInfDetails = RegSetValueExW(hKey, L"TS_sessionId", 0, 4u, Data, 4u);
        if ( !DeviceInfDetails )
        {
          *(_DWORD *)Data = CDeviceEntry::GetRemoteId(this);
          DeviceInfDetails = RegSetValueExW(hKey, L"TS_clientDeviceId", 0, 4u, Data, 4u);
          if ( !DeviceInfDetails )
          {
            if ( !lstrcmpiW(L"TS_GENERIC_PNP_DEVICE", v14) )
              CrimsonHelper::RaiseEvent<unsigned short *>(
                &CrimsonHelper::s_instance,
                EVENT_NOTIFY_MATCHING_DEVICE_NOT_FOUND,
                *((_QWORD *)this + 12));
            *a3 = (struct IRemoteDevice *)*((_QWORD *)this + 10);
            v25 = *((_QWORD *)this + 10);
            if ( v25 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
            *((_DWORD *)this + 18) |= 0x20u;
            DeviceInfDetails = 0;
            CrimsonHelper::RaiseEvent<unsigned short *>(
              &CrimsonHelper::s_instance,
              EVENT_NOTIFY_DEVICE_REDIRECT_SUCCESS,
              *((_QWORD *)this + 12));
            goto LABEL_61;
          }
          if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
            || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
          {
            goto LABEL_37;
          }
          v22 = RdpWppGetCurrentThreadActivityIdPrefix();
          v23 = 37;
          goto LABEL_36;
        }
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v22 = RdpWppGetCurrentThreadActivityIdPrefix();
          v23 = 36;
          goto LABEL_36;
        }
      }
    }
LABEL_37:
    if ( DeviceInfDetails > 0 )
      DeviceInfDetails = (unsigned __int16)DeviceInfDetails | 0x80070000;
    goto LABEL_61;
  }
  if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
    || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
  {
    goto LABEL_61;
  }
  v16 = RdpWppGetCurrentThreadActivityIdPrefix();
  v17 = 31;
  v18 = "GetDeviceInfDetails FAILED";
LABEL_20:
  WPP_SF_DsD(
    *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
    v17,
    (unsigned int)WPP_9f8b2618b856326daa1832c892715ef0_Traceguids,
    v16,
    (__int64)v18,
    DeviceInfDetails);
LABEL_61:
  if ( v14 )
    CoTaskMemFree(v14);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v15 )
    CoTaskMemFree(v15);
LABEL_67:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v36);
  CRegistry::~CRegistry((CRegistry *)v31);
  return (unsigned int)DeviceInfDetails;
}

```

## disassembly

```asm
0x18002c0bc  mov     [rsp-8+arg_18], rbx
0x18002c0c1  push    rbp
0x18002c0c2  push    rsi
0x18002c0c3  push    rdi
0x18002c0c4  push    r12
0x18002c0c6  push    r13
0x18002c0c8  push    r14
0x18002c0ca  push    r15
0x18002c0cc  lea     rbp, [rsp-1A0h]
0x18002c0d4  sub     rsp, 2A0h
0x18002c0db  mov     rax, cs:__security_cookie
0x18002c0e2  xor     rax, rsp
0x18002c0e5  mov     [rbp+1D0h+var_40], rax
0x18002c0ec  xor     r13d, r13d
0x18002c0ef  lea     rbx, [rcx+80h]
0x18002c0f6  mov     rsi, rcx
0x18002c0f9  mov     qword ptr [rsp+2D0h+Data], r13
0x18002c0fe  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18002c105  mov     [rsp+2D0h+pv], r13
0x18002c10a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002c10e  mov     [rsp+2D0h+var_298], r13
0x18002c113  mov     rcx, rbx; this
0x18002c116  mov     [rsp+2D0h+var_288], rax
0x18002c11b  mov     r12, r8
0x18002c11e  mov     [rsp+2D0h+var_280], r13
0x18002c123  mov     rdi, rdx
0x18002c126  mov     [rsp+2D0h+var_278], r13d
0x18002c12b  mov     [rsp+2D0h+hKey], r13
0x18002c130  mov     [rsp+2D0h+var_268], r14d
0x18002c135  mov     [rsp+2D0h+var_264], r14d
0x18002c13a  mov     [r8], r13
0x18002c13d  mov     [rsp+2D0h+var_260], rbx
0x18002c142  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18002c147  test    byte ptr [rsi+1Ch], 4
0x18002c14b  jz      short loc_18002C157
0x18002c14d  mov     edi, 80004004h
0x18002c152  jmp     loc_18002C5B9
0x18002c157  mov     rcx, rsi; this
0x18002c15a  call    ?StopTimer@CDeviceEntry@@AEAAXXZ; CDeviceEntry::StopTimer(void)
0x18002c15f  mov     rcx, [rsi+58h]; Block
0x18002c163  test    rcx, rcx
0x18002c166  jz      short loc_18002C16D
0x18002c168  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c16d  mov     rcx, r14
0x18002c170  inc     rcx
0x18002c173  cmp     [rdi+rcx*2], r13w
0x18002c178  jnz     short loc_18002C170
0x18002c17a  inc     rcx
0x18002c17d  mov     eax, 2
0x18002c182  mul     rcx
0x18002c185  cmovb   rax, r14
0x18002c189  mov     rcx, rax; Size
0x18002c18c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c191  mov     [rsi+58h], rax
0x18002c195  test    rax, rax
0x18002c198  jnz     short loc_18002C1F3
0x18002c19a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c1a1  lea     rax, WPP_GLOBAL_Control
0x18002c1a8  cmp     rcx, rax
0x18002c1ab  jz      short loc_18002C1E9
0x18002c1ad  test    byte ptr [rcx+1Ch], 8
0x18002c1b1  jz      short loc_18002C1E9
0x18002c1b3  cmp     byte ptr [rcx+19h], 2
0x18002c1b7  jb      short loc_18002C1E9
0x18002c1b9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002c1be  lea     rcx, aWchar; "WCHAR[]"
0x18002c1c5  mov     edx, 1Eh
0x18002c1ca  mov     [rsp+2D0h+lpData], rcx
0x18002c1cf  lea     r8, WPP_9f8b2618b856326daa1832c892715ef0_Traceguids
0x18002c1d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c1dd  mov     r9d, eax
0x18002c1e0  mov     rcx, [rcx+10h]
0x18002c1e4  call    WPP_SF_Ds
0x18002c1e9  mov     edi, 8007000Eh
0x18002c1ee  jmp     loc_18002C5B9
0x18002c1f3  mov     rdx, r14
0x18002c1f6  inc     rdx
0x18002c1f9  cmp     [rdi+rdx*2], r13w
0x18002c1fe  jnz     short loc_18002C1F6
0x18002c200  inc     rdx; unsigned __int64
0x18002c203  mov     r8, rdi; unsigned __int16 *
0x18002c206  mov     rcx, rax; unsigned __int16 *
0x18002c209  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c20e  mov     rcx, rbx; this
0x18002c211  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x18002c216  lea     r9, [rsp+2D0h+var_298]; unsigned __int16 **
0x18002c21b  mov     rcx, rdi; unsigned __int16 *
0x18002c21e  lea     r8, [rsp+2D0h+pv]; unsigned __int16 **
0x18002c223  lea     rdx, [rsp+2D0h+Data]; unsigned __int16 **
0x18002c228  call    ?GetDeviceInfDetails@@YAJPEBGPEAPEAG11@Z; GetDeviceInfDetails(ushort const *,ushort * *,ushort * *,ushort * *)
0x18002c22d  mov     rcx, rbx; this
0x18002c230  mov     edi, eax
0x18002c232  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18002c237  mov     rbx, qword ptr [rsp+2D0h+Data]
0x18002c23c  mov     r15, [rsp+2D0h+var_298]
0x18002c241  test    edi, edi
0x18002c243  jns     short loc_18002C2A9
0x18002c245  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c24c  lea     rax, WPP_GLOBAL_Control
0x18002c253  cmp     rcx, rax
0x18002c256  jz      loc_18002C58D
0x18002c25c  test    byte ptr [rcx+1Ch], 8
0x18002c260  jz      loc_18002C58D
0x18002c266  cmp     byte ptr [rcx+19h], 2
0x18002c26a  jb      loc_18002C58D
0x18002c270  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002c275  mov     edx, 1Fh
0x18002c27a  lea     rcx, aGetdeviceinfde; "GetDeviceInfDetails FAILED"
0x18002c281  mov     [rsp+2D0h+cbData], edi
0x18002c285  mov     [rsp+2D0h+lpData], rcx
0x18002c28a  lea     r8, WPP_9f8b2618b856326daa1832c892715ef0_Traceguids
0x18002c291  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c298  mov     r9d, eax
0x18002c29b  mov     rcx, [rcx+10h]
0x18002c29f  call    WPP_SF_DsD
0x18002c2a4  jmp     loc_18002C58D
0x18002c2a9  test    byte ptr [rsi+1Ch], 4
0x18002c2ad  jz      short loc_18002C2FA
0x18002c2af  mov     edi, 80004004h
0x18002c2b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c2bb  lea     rax, WPP_GLOBAL_Control
0x18002c2c2  cmp     rcx, rax
0x18002c2c5  jz      loc_18002C58D
0x18002c2cb  test    byte ptr [rcx+1Ch], 8
0x18002c2cf  jz      loc_18002C58D
0x18002c2d5  cmp     byte ptr [rcx+19h], 2
0x18002c2d9  jb      loc_18002C58D
0x18002c2df  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002c2e4  mov     edx, 20h ; ' '
0x18002c2e9  mov     [rsp+2D0h+cbData], 80004004h
0x18002c2f1  lea     rcx, aTerminated; "Terminated"
0x18002c2f8  jmp     short loc_18002C285
0x18002c2fa  lea     r9, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Cla"...
0x18002c301  mov     [rsp+2D0h+lpData], r15; unsigned __int16 *
0x18002c306  lea     r8, aSS; "%s\\%s"
0x18002c30d  mov     edx, 208h; unsigned __int64
0x18002c312  lea     rcx, [rbp+1D0h+var_250]; unsigned __int16 *
0x18002c316  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c31b  mov     edi, eax
0x18002c31d  test    eax, eax
0x18002c31f  jns     short loc_18002C362
0x18002c321  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c328  lea     rax, WPP_GLOBAL_Control
0x18002c32f  cmp     rcx, rax
0x18002c332  jz      loc_18002C58D
0x18002c338  test    byte ptr [rcx+1Ch], 8
0x18002c33c  jz      loc_18002C58D
0x18002c342  cmp     byte ptr [rcx+19h], 2
0x18002c346  jb      loc_18002C58D
0x18002c34c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002c351  mov     edx, 21h ; '!'
0x18002c356  lea     rcx, aStringcbprintf_1; "StringCbPrintfW"
0x18002c35d  jmp     loc_18002C281
0x18002c362  lea     r8, [rbp+1D0h+var_250]; unsigned __int16 *
0x18002c366  lea     rcx, [rsp+2D0h+var_288]; this
0x18002c36b  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18002c370  mov     edi, eax
0x18002c372  test    eax, eax
0x18002c374  jz      short loc_18002C3D3
0x18002c376  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c37d  lea     rax, WPP_GLOBAL_Control
0x18002c384  cmp     rcx, rax
0x18002c387  jz      short loc_18002C3BD
0x18002c389  test    byte ptr [rcx+1Ch], 8
0x18002c38d  jz      short loc_18002C3BD
0x18002c38f  cmp     byte ptr [rcx+19h], 2
0x18002c393  jb      short loc_18002C3BD
0x18002c395  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002c39a  mov     edx, 22h ; '"'
0x18002c39f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c3a6  lea     r8, WPP_9f8b2618b856326daa1832c892715ef0_Traceguids
0x18002c3ad  mov     r9d, eax
0x18002c3b0  mov     dword ptr [rsp+2D0h+lpData], edi
0x18002c3b4  mov     rcx, [rcx+10h]
0x18002c3b8  call    WPP_SF_Dd
0x18002c3bd  test    edi, edi
0x18002c3bf  jle     loc_18002C58D
0x18002c3c5  movzx   edi, di
0x18002c3c8  or      edi, 80070000h
0x18002c3ce  jmp     loc_18002C58D
0x18002c3d3  mov     rcx, [rsi+58h]
0x18002c3d7  inc     r14
0x18002c3da  cmp     [rcx+r14*2], r13w
0x18002c3df  jnz     short loc_18002C3D7
0x18002c3e1  lea     eax, ds:2[r14*2]
0x18002c3e9  mov     r9d, 1; dwType
0x18002c3ef  mov     [rsp+2D0h+cbData], eax; cbData
0x18002c3f3  lea     rdx, aTsDeviceinstan; "TS_deviceinstanceId"
0x18002c3fa  mov     [rsp+2D0h+lpData], rcx; lpData
0x18002c3ff  xor     r8d, r8d; Reserved
0x18002c402  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18002c407  call    cs:__imp_RegSetValueExW
0x18002c40d  mov     edi, eax
0x18002c40f  test    eax, eax
0x18002c411  jz      short loc_18002C441
0x18002c413  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c41a  lea     rax, WPP_GLOBAL_Control
0x18002c421  cmp     rcx, rax
0x18002c424  jz      short loc_18002C3BD
0x18002c426  test    byte ptr [rcx+1Ch], 8
0x18002c42a  jz      short loc_18002C3BD
0x18002c42c  cmp     byte ptr [rcx+19h], 2
0x18002c430  jb      short loc_18002C3BD
0x18002c432  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002c437  mov     edx, 23h ; '#'
0x18002c43c  jmp     loc_18002C39F
0x18002c441  mov     eax, [rsi+44h]
0x18002c444  lea     rdx, aTsSessionid; "TS_sessionId"
0x18002c44b  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18002c450  mov     r14d, 4
0x18002c456  mov     dword ptr [rsp+2D0h+Data], eax
0x18002c45a  mov     r9d, r14d; dwType
0x18002c45d  lea     rax, [rsp+2D0h+Data]
0x18002c462  mov     [rsp+2D0h+cbData], r14d; cbData
0x18002c467  xor     r8d, r8d; Reserved
0x18002c46a  mov     [rsp+2D0h+lpData], rax; lpData
0x18002c46f  call    cs:__imp_RegSetValueExW
0x18002c475  mov     edi, eax
0x18002c477  test    eax, eax
0x18002c479  jz      short loc_18002C4B4
0x18002c47b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c482  lea     rax, WPP_GLOBAL_Control
0x18002c489  cmp     rcx, rax
0x18002c48c  jz      loc_18002C3BD
0x18002c492  test    byte ptr [rcx+1Ch], 8
0x18002c496  jz      loc_18002C3BD
0x18002c49c  cmp     byte ptr [rcx+19h], 2
0x18002c4a0  jb      loc_18002C3BD
0x18002c4a6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002c4ab  lea     edx, [r14+20h]
0x18002c4af  jmp     loc_18002C39F
0x18002c4b4  mov     rcx, rsi; this
0x18002c4b7  call    ?GetRemoteId@CDeviceEntry@@QEBAKXZ; CDeviceEntry::GetRemoteId(void)
0x18002c4bc  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18002c4c1  lea     rdx, aTsClientdevice; "TS_clientDeviceId"
0x18002c4c8  mov     dword ptr [rsp+2D0h+Data], eax
0x18002c4cc  mov     r9d, r14d; dwType
0x18002c4cf  lea     rax, [rsp+2D0h+Data]
0x18002c4d4  mov     [rsp+2D0h+cbData], r14d; cbData
0x18002c4d9  xor     r8d, r8d; Reserved
0x18002c4dc  mov     [rsp+2D0h+lpData], rax; lpData
0x18002c4e1  call    cs:__imp_RegSetValueExW
0x18002c4e7  mov     edi, eax
0x18002c4e9  test    eax, eax
0x18002c4eb  jz      short loc_18002C527
0x18002c4ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c4f4  lea     rax, WPP_GLOBAL_Control
0x18002c4fb  cmp     rcx, rax
0x18002c4fe  jz      loc_18002C3BD
0x18002c504  test    byte ptr [rcx+1Ch], 8
0x18002c508  jz      loc_18002C3BD
0x18002c50e  cmp     byte ptr [rcx+19h], 2
0x18002c512  jb      loc_18002C3BD
0x18002c518  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002c51d  mov     edx, 25h ; '%'
0x18002c522  jmp     loc_18002C39F
0x18002c527  mov     rdx, rbx; lpString2
0x18002c52a  lea     rcx, String1; "TS_GENERIC_PNP_DEVICE"
0x18002c531  call    cs:__imp_lstrcmpiW
0x18002c537  test    eax, eax
0x18002c539  jnz     short loc_18002C552
0x18002c53b  mov     r8, [rsi+60h]
0x18002c53f  lea     rdx, EVENT_NOTIFY_MATCHING_DEVICE_NOT_FOUND
0x18002c546  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x18002c54d  call    ??$RaiseEvent@PEAG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG@Z; CrimsonHelper::RaiseEvent<ushort *>(_EVENT_DESCRIPTOR const &,ushort *)
0x18002c552  mov     rax, [rsi+50h]
0x18002c556  mov     [r12], rax
0x18002c55a  mov     rcx, [rsi+50h]
0x18002c55e  test    rcx, rcx
0x18002c561  jz      short loc_18002C56F
0x18002c563  mov     rax, [rcx]
0x18002c566  mov     rax, [rax+8]
0x18002c56a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c56f  or      dword ptr [rsi+48h], 20h
0x18002c573  lea     rdx, EVENT_NOTIFY_DEVICE_REDIRECT_SUCCESS
0x18002c57a  mov     r8, [rsi+60h]
0x18002c57e  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x18002c585  mov     edi, r13d
0x18002c588  call    ??$RaiseEvent@PEAG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG@Z; CrimsonHelper::RaiseEvent<ushort *>(_EVENT_DESCRIPTOR const &,ushort *)
0x18002c58d  test    rbx, rbx
0x18002c590  jz      short loc_18002C59B
0x18002c592  mov     rcx, rbx; pv
0x18002c595  call    cs:__imp_CoTaskMemFree
0x18002c59b  mov     rcx, [rsp+2D0h+pv]; pv
0x18002c5a0  test    rcx, rcx
0x18002c5a3  jz      short loc_18002C5AB
0x18002c5a5  call    cs:__imp_CoTaskMemFree
0x18002c5ab  test    r15, r15
0x18002c5ae  jz      short loc_18002C5B9
0x18002c5b0  mov     rcx, r15; pv
0x18002c5b3  call    cs:__imp_CoTaskMemFree
0x18002c5b9  lea     rcx, [rsp+2D0h+var_260]; this
0x18002c5be  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18002c5c3  lea     rcx, [rsp+2D0h+var_288]; this
0x18002c5c8  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18002c5cd  mov     eax, edi
0x18002c5cf  mov     rcx, [rbp+1D0h+var_40]
0x18002c5d6  xor     rcx, rsp; StackCookie
0x18002c5d9  call    __security_check_cookie
0x18002c5de  mov     rbx, [rsp+2D0h+arg_18]
  ... truncated ...
```
