# _DeleteOldSPPGroups(ISharedProtectionPoints *)

- ea: `0x140004410`
- end: `0x1400047de`
- name: `?_DeleteOldSPPGroups@@YAJPEAUISharedProtectionPoints@@@Z`
- size: `974`
- prototype: `__int64 __fastcall(struct ISharedProtectionPoints *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140004a70`

## callees

- `0x140002e1c`
- `0x140002e44`
- `0x140004410`
- `0x140005608`
- `0x14000595c`
- `0x14000e324`
- `0x14000e41c`
- `0x14001094e`
- `0x140011010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400044bf`
- `ADVAPI32!RegOpenKeyExW` at `0x1400044bf`
- `ADVAPI32!RegCloseKey` at `0x14000477f`
- `ADVAPI32!RegCloseKey` at `0x140004799`
- `ADVAPI32!RegCloseKey` at `0x14000477f`
- `ADVAPI32!RegCloseKey` at `0x140004799`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140004670`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140004670`
- `SRCORE!SrFreeRpPropArray` at `0x14000476b`
- `SRCORE!SrFreeRpPropArray` at `0x14000476b`
- `ole32!CoTaskMemAlloc` at `0x14000462c`
- `ole32!CoTaskMemAlloc` at `0x14000462c`
- `ole32!CoCreateInstance` at `0x1400045a6`
- `ole32!CoCreateInstance` at `0x1400045a6`
- `ole32!CoTaskMemFree` at `0x14000475e`
- `ole32!CoTaskMemFree` at `0x14000475e`

## string_xrefs

- `0x140004468`: `_DeleteOldSPPGroups`

## pseudocode

```c
__int64 __fastcall _DeleteOldSPPGroups(struct ISharedProtectionPoints *a1)
{
  _DWORD *v2; // rdi
  _QWORD *v3; // rcx
  unsigned int v4; // ebx
  __int16 v5; // ax
  __int64 v6; // rdx
  __int16 v7; // ax
  _DWORD *v8; // rax
  int v9; // esi
  unsigned __int64 v10; // rbx
  unsigned __int64 v11; // r14
  __int64 v12; // r8
  __int64 v13; // rdx
  struct _FILETIME i; // rax
  __int64 v15; // r10
  __int64 v16; // r9
  unsigned int v17; // ebx
  unsigned int j; // eax
  __int128 *v19; // rsi
  __int64 (__fastcall *v20)(struct ISharedProtectionPoints *, __int128 *); // rax
  HKEY v21; // rcx
  unsigned int v22; // ebx
  __int64 v24; // [rsp+30h] [rbp-49h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-41h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-39h] BYREF
  __int128 v27; // [rsp+50h] [rbp-29h] BYREF
  HRESULT v28; // [rsp+60h] [rbp-19h] BYREF
  __int16 v29; // [rsp+64h] [rbp-15h]
  __int16 v30; // [rsp+66h] [rbp-13h]
  unsigned int v31; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned int v32; // [rsp+F0h] [rbp+77h] BYREF
  HKEY hKey; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v28, "_DeleteOldSPPGroups", 0xBCu, 1u);
  ppv = 0;
  v31 = 0;
  v24 = 0;
  v32 = 0;
  v2 = 0;
  SystemTimeAsFileTime = 0;
  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SystemRestore",
         0,
         0x20019u,
         &hKey)
    || (unsigned int)SxRegReadDWORD(hKey, L"SystemRestorePointTimeToLive", &v32, 1) )
  {
    v4 = 20160;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      v6 = 22;
      goto LABEL_21;
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    v4 = v32;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids, v32);
      v3 = WPP_GLOBAL_Control;
    }
    if ( !v4 )
    {
      if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 7) & 0x8000000) != 0 )
        WPP_SF_(v3[2], 20, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
      v5 = 216;
LABEL_14:
      v28 = 0;
      v29 = v5;
      goto LABEL_47;
    }
    if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 7) & 0x8000000) != 0 )
    {
      v6 = 21;
LABEL_21:
      WPP_SF_d(v3[2], v6, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids, v4);
    }
  }
  v28 = CoCreateInstance(&CLSID_SrControl, 0, 1u, &IID_ISrControl, &ppv);
  v7 = 234;
  if ( v28 < 0
    || (v29 = 234,
        v28 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, &v31, &v24),
        v7 = 235,
        v28 < 0) )
  {
    v30 = v7;
    goto LABEL_47;
  }
  v29 = 235;
  if ( v31 <= 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids, v31);
    v5 = 241;
    goto LABEL_14;
  }
  v8 = CoTaskMemAlloc(4LL * v31);
  v2 = v8;
  if ( v8 )
  {
    v9 = 0;
    v10 = 600000000LL * v4;
    v29 = 245;
    v11 = 0;
    v28 = 0;
    memset_0(v8, 0, 4LL * v31);
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v13 = 0;
    for ( i = SystemTimeAsFileTime; (unsigned int)v13 < v31; v13 = (unsigned int)(v13 + 1) )
    {
      v15 = v24;
      v12 = (unsigned int)v13;
      v16 = 152LL * (unsigned int)v13;
      if ( *(_QWORD *)&i - *(_QWORD *)(v16 + v24 + 16) > v10 )
      {
        v2[(unsigned int)v13] = 1;
        if ( v11 < *(_QWORD *)(v16 + v15 + 16) )
        {
          v11 = *(_QWORD *)(v16 + v15 + 16);
          v9 = v13;
        }
      }
    }
    v17 = 0;
    v2[v9] = 0;
    for ( j = v31; v17 < j; ++v17 )
    {
      if ( v2[v17] )
      {
        v19 = (__int128 *)(v24 + 152LL * v17);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF__guid_i(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v12, v19, *((_QWORD *)v19 + 2));
        }
        v20 = *(__int64 (__fastcall **)(struct ISharedProtectionPoints *, __int128 *))(*(_QWORD *)a1 + 56LL);
        v27 = *v19;
        v28 = v20(a1, &v27);
        if ( v28 < 0 )
        {
          v30 = 282;
          break;
        }
        j = v31;
        v29 = 282;
      }
    }
  }
  else
  {
    v28 = -2147024882;
    v30 = 245;
  }
LABEL_47:
  CoTaskMemFree(v2);
  SrFreeRpPropArray(v31, &v24);
  v21 = hKey;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    v21 = 0;
    hKey = 0;
  }
  v22 = v28;
  if ( (unsigned __int64)v21 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(v21);
    hKey = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v28);
  return v22;
}

```

## disassembly

```asm
0x140004410  mov     [rsp-8+arg_0], rbx
0x140004415  push    rbp
0x140004416  push    rsi
0x140004417  push    rdi
0x140004418  push    r12
0x14000441a  push    r13
0x14000441c  push    r14
0x14000441e  push    r15
0x140004420  lea     rbp, [rsp-27h]
0x140004425  sub     rsp, 0A0h
0x14000442c  mov     r15, rcx
0x14000442f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004436  lea     r13, WPP_GLOBAL_Control
0x14000443d  lea     rsi, WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids
0x140004444  cmp     rcx, r13
0x140004447  jz      short loc_140004463
0x140004449  test    dword ptr [rcx+1Ch], 20000000h
0x140004450  jz      short loc_140004463
0x140004452  mov     rcx, [rcx+10h]
0x140004456  mov     edx, 12h
0x14000445b  mov     r8, rsi
0x14000445e  call    WPP_SF_
0x140004463  mov     ebx, 1
0x140004468  lea     rdx, aDeleteoldsppgr; "_DeleteOldSPPGroups"
0x14000446f  mov     r9d, ebx; unsigned __int16
0x140004472  lea     rcx, [rbp+57h+var_70]; this
0x140004476  mov     r8d, 0BCh; unsigned __int16
0x14000447c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140004481  xor     r12d, r12d
0x140004484  lea     rax, [rbp+57h+hKey]
0x140004488  mov     r9d, 20019h; samDesired
0x14000448e  mov     [rsp+0D0h+phkResult], rax; phkResult
0x140004493  xor     r8d, r8d; ulOptions
0x140004496  mov     [rbp+57h+ppv], r12
0x14000449a  lea     rdx, s_cszSRRegKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400044a1  mov     [rbp+57h+arg_8], r12d
0x1400044a5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400044ac  mov     [rbp+57h+var_A0], r12
0x1400044b0  mov     [rbp+57h+arg_10], r12d
0x1400044b4  mov     edi, r12d
0x1400044b7  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r12
0x1400044bb  mov     [rbp+57h+hKey], r12
0x1400044bf  call    cs:__imp_RegOpenKeyExW
0x1400044c5  mov     r14d, 8000000h
0x1400044cb  test    eax, eax
0x1400044cd  jnz     loc_14000455E
0x1400044d3  mov     rcx, [rbp+57h+hKey]; hKey
0x1400044d7  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x1400044db  mov     r9d, ebx; int
0x1400044de  lea     rdx, c_wszRestorePointTimeToLive; "SystemRestorePointTimeToLive"
0x1400044e5  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x1400044ea  test    eax, eax
0x1400044ec  jnz     short loc_14000455E
0x1400044ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400044f5  mov     ebx, [rbp+57h+arg_10]
0x1400044f8  cmp     rcx, r13
0x1400044fb  jz      short loc_14000451C
0x1400044fd  test    [rcx+1Ch], r14d
0x140004501  jz      short loc_14000451C
0x140004503  mov     rcx, [rcx+10h]
0x140004507  lea     edx, [rax+13h]
0x14000450a  mov     r9d, ebx
0x14000450d  mov     r8, rsi
0x140004510  call    WPP_SF_d
0x140004515  mov     rcx, cs:WPP_GLOBAL_Control
0x14000451c  test    ebx, ebx
0x14000451e  jnz     short loc_14000454C
0x140004520  cmp     rcx, r13
0x140004523  jz      short loc_14000453A
0x140004525  test    [rcx+1Ch], r14d
0x140004529  jz      short loc_14000453A
0x14000452b  mov     rcx, [rcx+10h]
0x14000452f  lea     edx, [rbx+14h]
0x140004532  mov     r8, rsi
0x140004535  call    WPP_SF_
0x14000453a  mov     eax, 0D8h
0x14000453f  mov     [rbp+57h+var_70], r12d
0x140004543  mov     [rbp+57h+var_6C], ax
0x140004547  jmp     loc_14000475B
0x14000454c  cmp     rcx, r13
0x14000454f  jz      short loc_140004589
0x140004551  test    [rcx+1Ch], r14d
0x140004555  jz      short loc_140004589
0x140004557  mov     edx, 15h
0x14000455c  jmp     short loc_14000457A
0x14000455e  mov     ebx, 4EC0h
0x140004563  mov     rcx, cs:WPP_GLOBAL_Control
0x14000456a  cmp     rcx, r13
0x14000456d  jz      short loc_140004589
0x14000456f  test    [rcx+1Ch], r14d
0x140004573  jz      short loc_140004589
0x140004575  mov     edx, 16h
0x14000457a  mov     rcx, [rcx+10h]
0x14000457e  mov     r9d, ebx
0x140004581  mov     r8, rsi
0x140004584  call    WPP_SF_d
0x140004589  xor     edx, edx; pUnkOuter
0x14000458b  lea     rax, [rbp+57h+ppv]
0x14000458f  lea     r9, IID_ISrControl; riid
0x140004596  mov     [rsp+0D0h+phkResult], rax; ppv
0x14000459b  lea     rcx, CLSID_SrControl; rclsid
0x1400045a2  lea     r8d, [rdx+1]; dwClsContext
0x1400045a6  call    cs:__imp_CoCreateInstance
0x1400045ac  mov     [rbp+57h+var_70], eax
0x1400045af  test    eax, eax
0x1400045b1  mov     eax, 0EAh
0x1400045b6  jns     short loc_1400045C1
0x1400045b8  mov     [rbp+57h+var_6A], ax
0x1400045bc  jmp     loc_14000475B
0x1400045c1  mov     rcx, [rbp+57h+ppv]
0x1400045c5  lea     r8, [rbp+57h+var_A0]
0x1400045c9  mov     [rbp+57h+var_6C], ax
0x1400045cd  lea     rdx, [rbp+57h+arg_8]
0x1400045d1  mov     rax, [rcx]
0x1400045d4  mov     rax, [rax+18h]
0x1400045d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045dd  mov     [rbp+57h+var_70], eax
0x1400045e0  test    eax, eax
0x1400045e2  mov     eax, 0EBh
0x1400045e7  js      short loc_1400045B8
0x1400045e9  mov     [rbp+57h+var_6C], ax
0x1400045ed  mov     eax, [rbp+57h+arg_8]
0x1400045f0  cmp     eax, 1
0x1400045f3  ja      short loc_140004625
0x1400045f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400045fc  cmp     rcx, r13
0x1400045ff  jz      short loc_14000461B
0x140004601  test    [rcx+1Ch], r14d
0x140004605  jz      short loc_14000461B
0x140004607  mov     rcx, [rcx+10h]
0x14000460b  mov     edx, 17h
0x140004610  mov     r9d, eax
0x140004613  mov     r8, rsi
0x140004616  call    WPP_SF_d
0x14000461b  mov     eax, 0F1h
0x140004620  jmp     loc_14000453F
0x140004625  mov     rcx, rax
0x140004628  shl     rcx, 2; cb
0x14000462c  call    cs:__imp_CoTaskMemAlloc
0x140004632  mov     rdi, rax
0x140004635  test    rax, rax
0x140004638  jz      loc_14000474B
0x14000463e  mov     r8d, [rbp+57h+arg_8]
0x140004642  xor     edx, edx; Val
0x140004644  mov     ecx, ebx
0x140004646  mov     esi, r12d
0x140004649  imul    rbx, rcx, 23C34600h
0x140004650  mov     ecx, 0F5h
0x140004655  shl     r8, 2; Size
0x140004659  mov     [rbp+57h+var_6C], cx
0x14000465d  mov     r14, r12
0x140004660  mov     rcx, rax; void *
0x140004663  mov     [rbp+57h+var_70], r12d
0x140004667  call    memset_0
0x14000466c  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140004670  call    cs:__imp_GetSystemTimeAsFileTime
0x140004676  mov     edx, r12d
0x140004679  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x14000467d  cmp     [rbp+57h+arg_8], r12d
0x140004681  jbe     short loc_1400046BB
0x140004683  mov     r10, [rbp+57h+var_A0]
0x140004687  mov     rcx, rax
0x14000468a  mov     r8d, edx
0x14000468d  imul    r9, r8, 98h
0x140004694  sub     rcx, [r9+r10+10h]
0x140004699  cmp     rcx, rbx
0x14000469c  jbe     short loc_1400046B4
0x14000469e  mov     dword ptr [rdi+r8*4], 1
0x1400046a6  cmp     r14, [r9+r10+10h]
0x1400046ab  jnb     short loc_1400046B4
0x1400046ad  mov     r14, [r9+r10+10h]
0x1400046b2  mov     esi, edx
0x1400046b4  inc     edx
0x1400046b6  cmp     edx, [rbp+57h+arg_8]
0x1400046b9  jb      short loc_140004683
0x1400046bb  mov     eax, esi
0x1400046bd  mov     ebx, r12d
0x1400046c0  mov     [rdi+rax*4], r12d
0x1400046c4  mov     eax, [rbp+57h+arg_8]
0x1400046c7  test    eax, eax
0x1400046c9  jz      loc_14000475B
0x1400046cf  mov     r14d, 11Ah
0x1400046d5  mov     ecx, ebx
0x1400046d7  cmp     [rdi+rcx*4], r12d
0x1400046db  jz      short loc_14000473C
0x1400046dd  imul    rsi, rcx, 98h
0x1400046e4  add     rsi, [rbp+57h+var_A0]
0x1400046e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046ef  cmp     rcx, r13
0x1400046f2  jz      short loc_140004712
0x1400046f4  test    dword ptr [rcx+1Ch], 8000000h
0x1400046fb  jz      short loc_140004712
0x1400046fd  mov     rax, [rsi+10h]
0x140004701  mov     r9, rsi
0x140004704  mov     rcx, [rcx+10h]
0x140004708  mov     [rsp+0D0h+phkResult], rax
0x14000470d  call    WPP_SF__guid_i
0x140004712  mov     rax, [r15]
0x140004715  lea     rdx, [rbp+57h+var_80]
0x140004719  movups  xmm0, xmmword ptr [rsi]
0x14000471c  mov     rcx, r15
0x14000471f  mov     rax, [rax+38h]
0x140004723  movdqu  [rbp+57h+var_80], xmm0
0x140004728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000472d  mov     [rbp+57h+var_70], eax
0x140004730  test    eax, eax
0x140004732  js      short loc_140004744
0x140004734  mov     eax, [rbp+57h+arg_8]
0x140004737  mov     [rbp+57h+var_6C], r14w
0x14000473c  inc     ebx
0x14000473e  cmp     ebx, eax
0x140004740  jb      short loc_1400046D5
0x140004742  jmp     short loc_14000475B
0x140004744  mov     [rbp+57h+var_6A], r14w
0x140004749  jmp     short loc_14000475B
0x14000474b  mov     ecx, 0F5h
0x140004750  mov     [rbp+57h+var_70], 8007000Eh
0x140004757  mov     [rbp+57h+var_6A], cx
0x14000475b  mov     rcx, rdi; pv
0x14000475e  call    cs:__imp_CoTaskMemFree
0x140004764  mov     ecx, [rbp+57h+arg_8]
0x140004767  lea     rdx, [rbp+57h+var_A0]
0x14000476b  call    cs:__imp_SrFreeRpPropArray
0x140004771  mov     rcx, [rbp+57h+hKey]; hKey
0x140004775  lea     rax, [rcx-1]
0x140004779  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000477d  ja      short loc_14000478C
0x14000477f  call    cs:__imp_RegCloseKey
0x140004785  mov     rcx, r12; hKey
0x140004788  mov     [rbp+57h+hKey], rcx
0x14000478c  mov     ebx, [rbp+57h+var_70]
0x14000478f  lea     rax, [rcx-1]
0x140004793  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140004797  ja      short loc_1400047A3
0x140004799  call    cs:__imp_RegCloseKey
0x14000479f  mov     [rbp+57h+hKey], r12
0x1400047a3  mov     rcx, [rbp+57h+ppv]
0x1400047a7  test    rcx, rcx
0x1400047aa  jz      short loc_1400047B8
0x1400047ac  mov     rdx, [rcx]
0x1400047af  mov     rax, [rdx+10h]
0x1400047b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047b8  lea     rcx, [rbp+57h+var_70]; this
0x1400047bc  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1400047c1  mov     eax, ebx
0x1400047c3  mov     rbx, [rsp+0D0h+arg_0]
0x1400047cb  add     rsp, 0A0h
0x1400047d2  pop     r15
0x1400047d4  pop     r14
0x1400047d6  pop     r13
0x1400047d8  pop     r12
0x1400047da  pop     rdi
0x1400047db  pop     rsi
0x1400047dc  pop     rbp
0x1400047dd  retn
```
