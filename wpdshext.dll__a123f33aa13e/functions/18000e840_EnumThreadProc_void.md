# EnumThreadProc(void *)

- ea: `0x18000e840`
- end: `0x18000ef48`
- name: `?EnumThreadProc@@YAKPEAX@Z`
- size: `1800`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180004110`
- `0x1800050d0`
- `0x1800082e0`
- `0x18000e760`
- `0x18000e840`
- `0x18000ef50`
- `0x18000fbd8`
- `0x180014b60`
- `0x18001d6b0`
- `0x1800206f0`
- `0x18002e4d0`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180039e80`
- `0x180041ab0`
- `0x180078010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000ec8e`
- `KERNEL32!EnterCriticalSection` at `0x18000ec8e`
- `KERNEL32!LeaveCriticalSection` at `0x18000ecce`
- `KERNEL32!LeaveCriticalSection` at `0x18000ecce`
- `KERNEL32!SetEvent` at `0x18000ecac`
- `KERNEL32!SetEvent` at `0x18000ee8c`
- `KERNEL32!SetEvent` at `0x18000ecac`
- `KERNEL32!SetEvent` at `0x18000ee8c`
- `KERNEL32!QueryPerformanceCounter` at `0x18000eb55`
- `KERNEL32!QueryPerformanceCounter` at `0x18000eb55`
- `ADVAPI32!TraceEvent` at `0x18000eea3`
- `ADVAPI32!TraceEvent` at `0x18000ef1d`
- `ADVAPI32!TraceEvent` at `0x18000eea3`
- `ADVAPI32!TraceEvent` at `0x18000ef1d`
- `ole32!CoTaskMemFree` at `0x18000ece4`
- `ole32!CoTaskMemFree` at `0x18000ece4`
- `ole32!CoCreateInstance` at `0x18000ed96`
- `ole32!CoCreateInstance` at `0x18000ed96`
- `SHELL32!__imp_ILFindLastID` at `0x18000e8ef`
- `SHELL32!__imp_ILFindLastID` at `0x18000e8ef`
- `SHELL32!__imp_ILFree` at `0x18000ec3b`
- `SHELL32!__imp_ILFree` at `0x18000ecbc`
- `SHELL32!__imp_ILFree` at `0x18000ec3b`
- `SHELL32!__imp_ILFree` at `0x18000ecbc`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall EnumThreadProc(char *lpThreadParameter, const struct EtwContext *a2, const struct _GUID *a3)
{
  int *v4; // rbx
  LPCITEMIDLIST *v5; // r12
  const struct _ITEMIDLIST *ID; // rax
  CContentFolder *v7; // rcx
  const struct CONTENTITEM *v8; // rax
  int ObjectID; // eax
  int v10; // edi
  int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // ebx
  int v15; // eax
  unsigned int i; // r13d
  int v17; // r15d
  LPITEMIDLIST v18; // rbx
  const struct CONTENTITEM *v19; // rax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rdx
  void *v23; // rcx
  int v24; // eax
  int v25; // ecx
  int j; // esi
  const struct _ITEMIDLIST *Ptr; // rax
  CContentFolder *v28; // rcx
  const struct CONTENTITEM *v29; // rax
  unsigned int v31; // [rsp+30h] [rbp-D0h] BYREF
  int v32; // [rsp+34h] [rbp-CCh] BYREF
  int v33; // [rsp+38h] [rbp-C8h]
  struct IPortableDevice *v34; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST pidl; // [rsp+48h] [rbp-B8h] BYREF
  int *v36; // [rsp+50h] [rbp-B0h]
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h]
  LARGE_INTEGER PerformanceCount[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v43; // [rsp+90h] [rbp-70h]
  __int64 v44; // [rsp+A0h] [rbp-60h]
  char v45; // [rsp+A8h] [rbp-58h]
  __int128 v46; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v47; // [rsp+C0h] [rbp-40h]
  int v48; // [rsp+D0h] [rbp-30h] BYREF
  TRACEHANDLE TraceHandle; // [rsp+D8h] [rbp-28h]
  _EVENT_TRACE_HEADER EventTrace; // [rsp+F0h] [rbp-10h] BYREF
  int v51; // [rsp+124h] [rbp+24h]
  int v52; // [rsp+128h] [rbp+28h]
  LPVOID pv[32]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v54[264]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v55[264]; // [rsp+440h] [rbp+340h] BYREF
  unsigned __int16 v56[264]; // [rsp+650h] [rbp+550h] BYREF

  CElapsedTime::CElapsedTime((CElapsedTime *)&v48, a2, a3, 1u, 1u);
  v40 = 0;
  v41 = 0;
  v45 = 0;
  *(_OWORD *)&PerformanceCount[0].LowPart = 0;
  v43 = 0;
  v44 = 0;
  pidl = 0;
  v32 = 0;
  memset_0(pv, 0, sizeof(pv));
  v31 = 0;
  v4 = 0;
  v36 = 0;
  v34 = 0;
  v38 = 0;
  ppv = 0;
  v39 = 0;
  v5 = (LPCITEMIDLIST *)*((_QWORD *)lpThreadParameter + 8);
  ID = ILFindLastID(v5[8]);
  v8 = CContentFolder::_IsValid(v7, ID);
  if ( v8 )
  {
    StringCchCopyW(
      v54,
      0x104u,
      (const unsigned __int16 *)v8 + *(unsigned int *)((char *)v8 + 62) + *(unsigned int *)((char *)v8 + 66) + 37);
    ObjectID = CBaseFolder::_GetObjectID((CBaseFolder *)v5, v54, v55, 0x104u);
    v10 = ObjectID;
    if ( ObjectID < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)WPP_dfacde6f4b3f3ae519c2a03af24374aa_Traceguids,
          (unsigned int)v54,
          ObjectID);
      goto LABEL_67;
    }
  }
  else
  {
    v11 = (*(__int64 (__fastcall **)(LPCITEMIDLIST *, LPCITEMIDLIST, unsigned __int16 *, __int64))((char *)&(*v5)[29].mkid.cb
                                                                                                 + 1))(
            v5,
            v5[8],
            v55,
            260);
    v10 = v11;
    if ( v11 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_67;
      v13 = 23;
LABEL_10:
      WPP_SF_d(v12[2], v13, WPP_dfacde6f4b3f3ae519c2a03af24374aa_Traceguids, (unsigned int)v11);
      goto LABEL_67;
    }
  }
  v11 = (*(__int64 (__fastcall **)(LPCITEMIDLIST *, LPCITEMIDLIST, struct IPortableDevice **))((char *)&(*v5)[45].mkid.cb
                                                                                             + 1))(
          v5,
          v5[8],
          &v34);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_67;
    v13 = 24;
    goto LABEL_10;
  }
  v11 = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))v34->lpVtbl->Content)(v34, &v38);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_67;
    v13 = 25;
    goto LABEL_10;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, _QWORD, __int64 *))(*(_QWORD *)v38 + 24LL))(
          v38,
          0,
          v55,
          0,
          &v39);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_67;
    v13 = 26;
    goto LABEL_10;
  }
  v14 = 8;
  v33 = 8;
LABEL_24:
  v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *, unsigned int *))(*(_QWORD *)v39 + 24LL))(
          v39,
          v14,
          pv,
          &v31);
  v10 = v15;
  if ( v15 >= 0 )
  {
    if ( !v31 )
      goto LABEL_66;
    for ( i = 0; ; ++i )
    {
      if ( i >= v31 )
      {
        if ( *((_DWORD *)lpThreadParameter + 10) == 1 )
          goto LABEL_66;
        v14 = v33;
        if ( v33 != 32 )
        {
          v24 = 32;
          if ( v33 == 8 )
            v24 = 16;
          v14 = v24;
          v33 = v24;
        }
        goto LABEL_24;
      }
      if ( !*((_DWORD *)lpThreadParameter + 10) )
      {
        if ( !v45 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        {
          QueryPerformanceCounter(PerformanceCount);
          v40 = 9;
          v41 = 0;
          v43 = 0;
          v45 = 1;
        }
        v17 = CContentFolder::_CreateIDList(
                (CContentFolder *)v5,
                v34,
                (unsigned __int16 *)pv[i],
                *((_DWORD *)lpThreadParameter + 7),
                &pidl,
                &v32);
        v18 = pidl;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        {
          v19 = CContentFolder::_IsValid((CContentFolder *)WPP_GLOBAL_Control, pidl);
          CPerfTraceHelper::ProcessPerformanceData(
            (CPerfTraceHelper *)&v40,
            9u,
            v17,
            (const unsigned __int16 *)(((unsigned __int64)v19 + 74) & -(__int64)(v19 != 0)));
        }
        if ( v17 == -2147024726 )
        {
          v10 = -2147024726;
          goto LABEL_66;
        }
        if ( v17 >= 0 )
        {
          if ( v32 )
          {
            if ( (lpThreadParameter[24] & 0x20) == 0 )
            {
              v20 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              {
                v21 = 18;
                goto LABEL_41;
              }
              goto LABEL_42;
            }
          }
          else if ( (lpThreadParameter[24] & 0x40) == 0 )
          {
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              v21 = 19;
LABEL_41:
              WPP_SF_(v20[2], v21, WPP_dfacde6f4b3f3ae519c2a03af24374aa_Traceguids);
            }
LABEL_42:
            if ( v18 )
            {
              ILFree(v18);
              pidl = 0;
            }
            goto LABEL_54;
          }
          if ( (unsigned int)FilterContentItem(v18, v34) )
            goto LABEL_42;
          EnterCriticalSection((LPCRITICAL_SECTION)(lpThreadParameter + 136));
          if ( (unsigned int)IsolationAwareDPA_InsertPtr(*((_QWORD *)lpThreadParameter + 23), v22, v18) == -1 )
          {
            if ( v18 )
            {
              ILFree(v18);
              pidl = 0;
            }
          }
          else
          {
            SetEvent(*((HANDLE *)lpThreadParameter + 6));
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)(lpThreadParameter + 136));
        }
      }
LABEL_54:
      v23 = pv[i];
      if ( v23 )
        CoTaskMemFree(v23);
      pv[i] = 0;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      WPP_dfacde6f4b3f3ae519c2a03af24374aa_Traceguids,
      (unsigned int)v15);
LABEL_66:
  v4 = v36;
LABEL_67:
  v25 = v10;
  if ( v10 >= 0 )
    v25 = 0;
  *((_DWORD *)lpThreadParameter + 14) = v25;
  if ( v4 )
  {
    if ( *v4 > 0
      && CoCreateInstance(
           &CLSID_PortableDevicePropVariantCollection,
           0,
           1u,
           &GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3,
           &ppv) >= 0 )
    {
      v46 = 0;
      v47 = 0;
      for ( j = 0; j < *v4; ++j )
      {
        Ptr = (const struct _ITEMIDLIST *)IsolationAwareDPA_GetPtr(v4, j);
        v29 = CContentFolder::_IsValid(v28, Ptr);
        if ( v29 )
        {
          StringCchCopyW(
            v54,
            0x104u,
            (const unsigned __int16 *)v29
          + *(unsigned int *)((char *)v29 + 62)
          + *(unsigned int *)((char *)v29 + 66)
          + 37);
          if ( CBaseFolder::_GetObjectID((CBaseFolder *)v5, v54, v56, 0x104u) >= 0 )
          {
            LOWORD(v46) = 31;
            *((_QWORD *)&v46 + 1) = v56;
            (*(void (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)ppv + 40LL))(ppv, &v46);
          }
        }
      }
      (*(void (__fastcall **)(__int64, _QWORD, LPVOID, _QWORD))(*(_QWORD *)v38 + 64LL))(v38, 0, ppv, 0);
    }
    IsolationAwareDPA_DestroyCallback(v4, DPA_ILFreeCB<_ITEMIDLIST __unaligned>);
  }
  *((_DWORD *)lpThreadParameter + 9) = 0;
  SetEvent(*((HANDLE *)lpThreadParameter + 6));
  if ( v48 )
  {
    v51 = v10;
    TraceEvent(TraceHandle, &EventTrace);
    v52 = 0;
  }
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v34 )
    ((void (__fastcall *)(struct IPortableDevice *))v34->lpVtbl->Release)(v34);
  if ( v48 && v52 )
    TraceEvent(TraceHandle, &EventTrace);
  return 0;
}

```

## disassembly

```asm
0x18000e840  push    rbp
0x18000e842  push    rbx
0x18000e843  push    rsi
0x18000e844  push    rdi
0x18000e845  push    r12
0x18000e847  push    r13
0x18000e849  push    r14
0x18000e84b  push    r15
0x18000e84d  lea     rbp, [rsp-778h]
0x18000e855  sub     rsp, 878h
0x18000e85c  mov     rax, cs:__security_cookie
0x18000e863  xor     rax, rsp
0x18000e866  mov     [rbp+7B0h+var_50], rax
0x18000e86d  mov     r14, rcx
0x18000e870  mov     dword ptr [rsp+8B0h+ppv], 1; unsigned int
0x18000e878  mov     r9b, 1; unsigned __int8
0x18000e87b  lea     rcx, [rbp+7B0h+var_7E0]; this
0x18000e87f  call    ??0CElapsedTime@@QEAA@AEBUEtwContext@@AEBU_GUID@@EK@Z; CElapsedTime::CElapsedTime(EtwContext const &,_GUID const &,uchar,ulong)
0x18000e884  nop
0x18000e885  xor     r15d, r15d
0x18000e888  mov     [rsp+8B0h+var_840], r15
0x18000e88d  mov     [rsp+8B0h+var_838], r15
0x18000e892  mov     [rbp+7B0h+var_808], r15b
0x18000e896  xorps   xmm0, xmm0
0x18000e899  movdqa  xmmword ptr [rbp+7B0h+PerformanceCount], xmm0
0x18000e89e  xorps   xmm1, xmm1
0x18000e8a1  movdqa  [rbp+7B0h+var_820], xmm1
0x18000e8a6  mov     [rbp+7B0h+var_810], r15
0x18000e8aa  mov     [rsp+8B0h+pidl], r15
0x18000e8af  mov     [rsp+8B0h+var_87C], r15d
0x18000e8b4  xor     edx, edx; Val
0x18000e8b6  mov     r8d, 100h; Size
0x18000e8bc  lea     rcx, [rbp+7B0h+pv]; void *
0x18000e8c0  call    memset_0
0x18000e8c5  mov     [rsp+8B0h+var_880], r15d
0x18000e8ca  mov     ebx, r15d
0x18000e8cd  mov     [rsp+8B0h+var_860], rbx
0x18000e8d2  mov     [rsp+8B0h+var_870], r15
0x18000e8d7  mov     [rsp+8B0h+var_850], r15
0x18000e8dc  mov     [rsp+8B0h+var_858], r15
0x18000e8e1  mov     [rsp+8B0h+var_848], r15
0x18000e8e6  mov     r12, [r14+40h]
0x18000e8ea  mov     rcx, [r12+40h]; pidl
0x18000e8ef  call    cs:__imp_ILFindLastID
0x18000e8f5  mov     rdx, rax; struct _ITEMIDLIST *
0x18000e8f8  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x18000e8fd  test    rax, rax
0x18000e900  jz      loc_18000E992
0x18000e906  mov     edx, [rax+42h]
0x18000e909  mov     ecx, [rax+3Eh]
0x18000e90c  add     rcx, 25h ; '%'
0x18000e910  add     rdx, rcx
0x18000e913  lea     r8, [rax+rdx*2]; unsigned __int16 *
0x18000e917  mov     esi, 104h
0x18000e91c  mov     edx, esi; unsigned __int64
0x18000e91e  lea     rcx, [rbp+7B0h+var_680]; unsigned __int16 *
0x18000e925  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e92a  mov     r9d, esi; unsigned int
0x18000e92d  lea     r8, [rbp+7B0h+var_470]; unsigned __int16 *
0x18000e934  lea     rdx, [rbp+7B0h+var_680]; unsigned __int16 *
0x18000e93b  mov     rcx, r12; this
0x18000e93e  call    ?_GetObjectID@CBaseFolder@@QEAAJPEBGPEAGI@Z; CBaseFolder::_GetObjectID(ushort const *,ushort *,uint)
0x18000e943  mov     edi, eax
0x18000e945  test    eax, eax
0x18000e947  jns     loc_18000E9F8
0x18000e94d  lea     rsi, WPP_GLOBAL_Control
0x18000e954  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e95b  cmp     rcx, rsi
0x18000e95e  jz      loc_18000ED5A
0x18000e964  test    byte ptr [rcx+1Ch], 2
0x18000e968  jz      loc_18000ED5A
0x18000e96e  lea     edx, [r15+16h]
0x18000e972  mov     dword ptr [rsp+8B0h+ppv], eax
0x18000e976  lea     r9, [rbp+7B0h+var_680]
0x18000e97d  lea     r8, WPP_dfacde6f4b3f3ae519c2a03af24374aa_Traceguids
0x18000e984  mov     rcx, [rcx+10h]
0x18000e988  call    WPP_SF_Sd
0x18000e98d  jmp     loc_18000ED5A
0x18000e992  mov     rax, [r12]
0x18000e996  mov     r9d, 104h
0x18000e99c  lea     r8, [rbp+7B0h+var_470]
0x18000e9a3  mov     rdx, [r12+40h]
0x18000e9a8  mov     rcx, r12
0x18000e9ab  mov     rax, [rax+58h]
0x18000e9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9b4  mov     edi, eax
0x18000e9b6  test    eax, eax
0x18000e9b8  jns     short loc_18000E9F8
0x18000e9ba  lea     rsi, WPP_GLOBAL_Control
0x18000e9c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9c8  cmp     rcx, rsi
0x18000e9cb  jz      loc_18000ED5A
0x18000e9d1  test    byte ptr [rcx+1Ch], 2
0x18000e9d5  jz      loc_18000ED5A
0x18000e9db  mov     edx, 17h
0x18000e9e0  mov     r9d, eax
0x18000e9e3  lea     r8, WPP_dfacde6f4b3f3ae519c2a03af24374aa_Traceguids
0x18000e9ea  mov     rcx, [rcx+10h]
0x18000e9ee  call    WPP_SF_d
0x18000e9f3  jmp     loc_18000ED5A
0x18000e9f8  mov     rax, [r12]
0x18000e9fc  lea     r8, [rsp+8B0h+var_870]
0x18000ea01  mov     rdx, [r12+40h]
0x18000ea06  mov     rcx, r12
0x18000ea09  mov     rax, [rax+88h]
0x18000ea10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea15  mov     edi, eax
0x18000ea17  test    eax, eax
0x18000ea19  jns     short loc_18000EA43
0x18000ea1b  lea     rsi, WPP_GLOBAL_Control
0x18000ea22  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea29  cmp     rcx, rsi
0x18000ea2c  jz      loc_18000ED5A
0x18000ea32  test    byte ptr [rcx+1Ch], 2
0x18000ea36  jz      loc_18000ED5A
0x18000ea3c  mov     edx, 18h
0x18000ea41  jmp     short loc_18000E9E0
0x18000ea43  mov     rcx, [rsp+8B0h+var_870]
0x18000ea48  mov     rax, [rcx]
0x18000ea4b  lea     rdx, [rsp+8B0h+var_850]
0x18000ea50  mov     rax, [rax+28h]
0x18000ea54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea59  mov     edi, eax
0x18000ea5b  test    eax, eax
0x18000ea5d  jns     short loc_18000EA8A
0x18000ea5f  lea     rsi, WPP_GLOBAL_Control
0x18000ea66  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea6d  cmp     rcx, rsi
0x18000ea70  jz      loc_18000ED5A
0x18000ea76  test    byte ptr [rcx+1Ch], 2
0x18000ea7a  jz      loc_18000ED5A
0x18000ea80  mov     edx, 19h
0x18000ea85  jmp     loc_18000E9E0
0x18000ea8a  mov     rcx, [rsp+8B0h+var_850]
0x18000ea8f  mov     rax, [rcx]
0x18000ea92  lea     rdx, [rsp+8B0h+var_848]
0x18000ea97  mov     [rsp+8B0h+ppv], rdx
0x18000ea9c  xor     r9d, r9d
0x18000ea9f  lea     r8, [rbp+7B0h+var_470]
0x18000eaa6  xor     edx, edx
0x18000eaa8  mov     rax, [rax+18h]
0x18000eaac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eab1  mov     edi, eax
0x18000eab3  test    eax, eax
0x18000eab5  jns     short loc_18000EAE2
0x18000eab7  lea     rsi, WPP_GLOBAL_Control
0x18000eabe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eac5  cmp     rcx, rsi
0x18000eac8  jz      loc_18000ED5A
0x18000eace  test    byte ptr [rcx+1Ch], 2
0x18000ead2  jz      loc_18000ED5A
0x18000ead8  mov     edx, 1Ah
0x18000eadd  jmp     loc_18000E9E0
0x18000eae2  mov     ebx, 8
0x18000eae7  mov     [rsp+8B0h+var_878], ebx
0x18000eaeb  lea     rsi, WPP_GLOBAL_Control
0x18000eaf2  mov     rcx, [rsp+8B0h+var_848]
0x18000eaf7  mov     rax, [rcx]
0x18000eafa  lea     r9, [rsp+8B0h+var_880]
0x18000eaff  lea     r8, [rbp+7B0h+pv]
0x18000eb03  mov     edx, ebx
0x18000eb05  mov     rax, [rax+18h]
0x18000eb09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb0e  mov     edi, eax
0x18000eb10  test    eax, eax
0x18000eb12  js      loc_18000ED2B
0x18000eb18  cmp     [rsp+8B0h+var_880], r15d
0x18000eb1d  jz      loc_18000ED55
0x18000eb23  mov     r13d, r15d
0x18000eb26  cmp     r13d, [rsp+8B0h+var_880]
0x18000eb2b  jnb     loc_18000ECF7
0x18000eb31  cmp     [r14+28h], r15d
0x18000eb35  jnz     loc_18000ECD7
0x18000eb3b  cmp     [rbp+7B0h+var_808], r15b
0x18000eb3f  jnz     short loc_18000EB75
0x18000eb41  mov     rax, cs:WPP_GLOBAL_Control
0x18000eb48  test    dword ptr [rax+1Ch], 800h
0x18000eb4f  jz      short loc_18000EB75
0x18000eb51  lea     rcx, [rbp+7B0h+PerformanceCount]; lpPerformanceCount
0x18000eb55  call    cs:__imp_QueryPerformanceCounter
0x18000eb5b  mov     [rsp+8B0h+var_840], 9
0x18000eb64  mov     [rsp+8B0h+var_838], r15
0x18000eb69  xorps   xmm0, xmm0
0x18000eb6c  movdqa  [rbp+7B0h+var_820], xmm0
0x18000eb71  mov     [rbp+7B0h+var_808], 1
0x18000eb75  mov     r8d, r13d
0x18000eb78  lea     rax, [rsp+8B0h+var_87C]
0x18000eb7d  mov     [rsp+8B0h+var_888], rax; int *
0x18000eb82  lea     rax, [rsp+8B0h+pidl]
0x18000eb87  mov     [rsp+8B0h+ppv], rax; struct _ITEMIDLIST **
0x18000eb8c  mov     r9d, [r14+1Ch]; int
0x18000eb90  mov     r8, [rbp+r8*8+7B0h+pv]; unsigned __int16 *
0x18000eb95  mov     rdx, [rsp+8B0h+var_870]; struct IPortableDevice *
0x18000eb9a  mov     rcx, r12; this
0x18000eb9d  call    ?_CreateIDList@CContentFolder@@QEAAJPEAUIPortableDevice@@PEBGHPEAPEFAU_ITEMIDLIST@@PEAH@Z; CContentFolder::_CreateIDList(IPortableDevice *,ushort const *,int,_ITEMIDLIST * *,int *)
0x18000eba2  mov     r15d, eax
0x18000eba5  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18000ebac  mov     rbx, [rsp+8B0h+pidl]
0x18000ebb1  test    dword ptr [rcx+1Ch], 800h
0x18000ebb8  jz      short loc_18000EBE1
0x18000ebba  mov     rdx, rbx; struct _ITEMIDLIST *
0x18000ebbd  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x18000ebc2  lea     rcx, [rax+4Ah]
0x18000ebc6  neg     rax
0x18000ebc9  sbb     r9, r9
0x18000ebcc  and     r9, rcx; unsigned __int16 *
0x18000ebcf  mov     r8d, r15d; int
0x18000ebd2  mov     edx, 9; unsigned int
0x18000ebd7  lea     rcx, [rsp+8B0h+var_840]; this
0x18000ebdc  call    ?ProcessPerformanceData@CPerfTraceHelper@@QEAAXKJPEBG@Z; CPerfTraceHelper::ProcessPerformanceData(ulong,long,ushort const *)
0x18000ebe1  mov     eax, 800700AAh
0x18000ebe6  cmp     r15d, eax
0x18000ebe9  jz      loc_18000ED24
0x18000ebef  test    r15d, r15d
0x18000ebf2  js      loc_18000ECD4
0x18000ebf8  xor     r15d, r15d
0x18000ebfb  cmp     [rsp+8B0h+var_87C], r15d
0x18000ec00  jz      short loc_18000EC4B
0x18000ec02  test    byte ptr [r14+18h], 20h
0x18000ec07  jnz     short loc_18000EC6B
0x18000ec09  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec10  cmp     rcx, rsi
0x18000ec13  jz      short loc_18000EC2F
0x18000ec15  test    byte ptr [rcx+1Ch], 40h
0x18000ec19  jz      short loc_18000EC2F
0x18000ec1b  lea     edx, [r15+12h]
0x18000ec1f  lea     r8, WPP_dfacde6f4b3f3ae519c2a03af24374aa_Traceguids
0x18000ec26  mov     rcx, [rcx+10h]
0x18000ec2a  call    WPP_SF_
0x18000ec2f  test    rbx, rbx
0x18000ec32  jz      loc_18000ECD7
0x18000ec38  mov     rcx, rbx; pidl
0x18000ec3b  call    cs:__imp_ILFree
0x18000ec41  mov     [rsp+8B0h+pidl], r15
0x18000ec46  jmp     loc_18000ECD7
0x18000ec4b  test    byte ptr [r14+18h], 40h
0x18000ec50  jnz     short loc_18000EC6B
0x18000ec52  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec59  cmp     rcx, rsi
0x18000ec5c  jz      short loc_18000EC2F
0x18000ec5e  test    byte ptr [rcx+1Ch], 40h
0x18000ec62  jz      short loc_18000EC2F
0x18000ec64  mov     edx, 13h
0x18000ec69  jmp     short loc_18000EC1F
0x18000ec6b  lea     r9, [rsp+8B0h+var_860]
0x18000ec70  mov     r8, r14
0x18000ec73  mov     rdx, [rsp+8B0h+var_870]; struct IPortableDevice *
0x18000ec78  mov     rcx, rbx; struct _ITEMIDLIST *
0x18000ec7b  call    ?FilterContentItem@@YAHPEFAU_ITEMIDLIST@@PEAUIPortableDevice@@PEAVCContentEnum@@PEAV?$CDPA@$$CFAU_ITEMIDLIST@@@@@Z; FilterContentItem(_ITEMIDLIST *,IPortableDevice *,CContentEnum *,CDPA<_ITEMIDLIST> *)
0x18000ec80  test    eax, eax
0x18000ec82  jnz     short loc_18000EC2F
0x18000ec84  lea     r15, [r14+88h]
0x18000ec8b  mov     rcx, r15; lpCriticalSection
0x18000ec8e  call    cs:__imp_EnterCriticalSection
0x18000ec94  mov     r8, rbx
0x18000ec97  mov     rcx, [r14+0B8h]
0x18000ec9e  call    IsolationAwareDPA_InsertPtr
0x18000eca3  cmp     eax, 0FFFFFFFFh
0x18000eca6  jz      short loc_18000ECB4
0x18000eca8  mov     rcx, [r14+30h]; hEvent
0x18000ecac  call    cs:__imp_SetEvent
0x18000ecb2  jmp     short loc_18000ECCB
0x18000ecb4  test    rbx, rbx
0x18000ecb7  jz      short loc_18000ECCB
0x18000ecb9  mov     rcx, rbx; pidl
0x18000ecbc  call    cs:__imp_ILFree
0x18000ecc2  mov     [rsp+8B0h+pidl], 0
0x18000eccb  mov     rcx, r15; lpCriticalSection
0x18000ecce  call    cs:__imp_LeaveCriticalSection
0x18000ecd4  xor     r15d, r15d
0x18000ecd7  mov     ebx, r13d
0x18000ecda  mov     rcx, [rbp+rbx*8+7B0h+pv]; pv
0x18000ecdf  test    rcx, rcx
0x18000ece2  jz      short loc_18000ECEA
0x18000ece4  call    cs:__imp_CoTaskMemFree
0x18000ecea  mov     [rbp+rbx*8+7B0h+pv], r15
0x18000ecef  inc     r13d
0x18000ecf2  jmp     loc_18000EB26
0x18000ecf7  cmp     dword ptr [r14+28h], 1
0x18000ecfc  jz      short loc_18000ED55
0x18000ecfe  mov     ebx, [rsp+8B0h+var_878]
0x18000ed02  cmp     ebx, 20h ; ' '
0x18000ed05  jz      loc_18000EAF2
0x18000ed0b  mov     eax, 20h ; ' '
0x18000ed10  lea     ecx, [rax-10h]
0x18000ed13  cmp     ebx, 8
0x18000ed16  cmovz   eax, ecx
0x18000ed19  mov     ebx, eax
0x18000ed1b  mov     [rsp+8B0h+var_878], eax
0x18000ed1f  jmp     loc_18000EAF2
0x18000ed24  mov     edi, eax
0x18000ed26  xor     r15d, r15d
0x18000ed29  jmp     short loc_18000ED55
0x18000ed2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed32  cmp     rcx, rsi
0x18000ed35  jz      short loc_18000ED55
0x18000ed37  test    byte ptr [rcx+1Ch], 2
0x18000ed3b  jz      short loc_18000ED55
0x18000ed3d  mov     edx, 1Bh
0x18000ed42  mov     r9d, eax
  ... truncated ...
```
