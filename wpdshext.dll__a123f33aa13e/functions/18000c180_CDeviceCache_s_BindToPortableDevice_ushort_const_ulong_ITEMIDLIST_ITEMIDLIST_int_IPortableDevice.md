# CDeviceCache::s_BindToPortableDevice(ushort const *,ulong,_ITEMIDLIST *,_ITEMIDLIST *,int,IPortableDevice * *)

- ea: `0x18000c180`
- end: `0x18000cb23`
- name: `?s_BindToPortableDevice@CDeviceCache@@SAJPEBGKPEFAU_ITEMIDLIST@@1HPEAPEAUIPortableDevice@@@Z`
- size: `2467`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct _ITEMIDLIST *, struct _ITEMIDLIST *, int, struct IPortableDevice **)`
- caller_count: `12`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800064e0`
- `0x180013170`
- `0x180016780`
- `0x180028ad0`
- `0x18002e670`
- `0x1800311d8`
- `0x18003d4f4`
- `0x18003da14`
- `0x18003e1c0`
- `0x18003e96c`
- `0x180049d20`
- `0x1800716fc`

## callees

- `0x18000c150`
- `0x18000c180`
- `0x18000cb90`
- `0x18000cc48`
- `0x18000cd60`
- `0x18000ce68`
- `0x18000d540`
- `0x18000d610`
- `0x18000e760`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180041ab0`
- `0x180054850`
- `0x180055514`
- `0x180078010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000ca05`
- `KERNEL32!HeapAlloc` at `0x18000ca05`
- `KERNEL32!GetProcessHeap` at `0x18000c9f1`
- `KERNEL32!GetProcessHeap` at `0x18000c9f1`
- `KERNEL32!EnterCriticalSection` at `0x18000c1d8`
- `KERNEL32!EnterCriticalSection` at `0x18000c1f9`
- `KERNEL32!EnterCriticalSection` at `0x18000c1d8`
- `KERNEL32!EnterCriticalSection` at `0x18000c1f9`
- `KERNEL32!LeaveCriticalSection` at `0x18000c1ec`
- `KERNEL32!LeaveCriticalSection` at `0x18000c34a`
- `KERNEL32!LeaveCriticalSection` at `0x18000c1ec`
- `KERNEL32!LeaveCriticalSection` at `0x18000c34a`
- `KERNEL32!SetEvent` at `0x18000c5ef`
- `KERNEL32!SetEvent` at `0x18000c5ef`
- `KERNEL32!CreateTimerQueueTimer` at `0x18000c2ff`
- `KERNEL32!CreateTimerQueueTimer` at `0x18000c2ff`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000caa5`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000caa5`
- `KERNEL32!GetTickCount` at `0x18000c588`
- `KERNEL32!GetTickCount` at `0x18000c588`
- `KERNEL32!GetCurrentThreadId` at `0x18000c416`
- `KERNEL32!GetCurrentThreadId` at `0x18000c416`
- `KERNEL32!WaitForSingleObject` at `0x18000c605`
- `KERNEL32!WaitForSingleObject` at `0x18000c605`
- `ole32!CoCreateInstance` at `0x18000c6dd`
- `ole32!CoCreateInstance` at `0x18000c796`
- `ole32!CoCreateInstance` at `0x18000c6dd`
- `ole32!CoCreateInstance` at `0x18000c796`
- `ole32!StringFromGUID2` at `0x18000c8ee`
- `ole32!StringFromGUID2` at `0x18000c8ee`

## string_xrefs

- `0x18000c327`: `pThreadItem->hTimer`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDeviceCache::s_BindToPortableDevice(
        const unsigned __int16 *a1,
        unsigned int a2,
        struct _ITEMIDLIST *a3,
        struct _ITEMIDLIST *a4,
        int a5,
        struct IPortableDevice **a6)
{
  struct DEVITEM_CACHE *Item; // r13
  struct THREAD_INFO *Thread; // r14
  LPVOID v12; // rbx
  struct IPortableDevice **v13; // rdx
  HRESULT v14; // edi
  PVOID *v15; // rcx
  int v16; // eax
  CDeviceCache *v17; // rcx
  struct CDeviceCache *v18; // rax
  struct IPortableDeviceVtbl *v19; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v22; // rax
  const struct std::nothrow_t *v23; // rdx
  struct THREAD_INFO *v24; // rax
  __int64 v25; // rdx
  unsigned int v26; // edx
  __int64 v27; // rdx
  __int64 v28; // r9
  struct CDeviceCache *v29; // rcx
  struct CDeviceCache *v30; // rax
  __int64 v31; // r9
  HRESULT v32; // eax
  int v33; // eax
  int v34; // eax
  HANDLE ProcessHeap; // rax
  struct IPortableDevice *v36; // rsi
  int v37; // r15d
  struct IPortableDeviceVtbl *v38; // rcx
  struct IPortableDeviceVtbl *lpVtbl; // rax
  ULONG (__stdcall *AddRef)(IPortableDevice *); // rdx
  LPVOID v41; // [rsp+48h] [rbp-81h] BYREF
  struct IPortableDeviceVtbl *v42; // [rsp+50h] [rbp-79h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-71h] BYREF
  LPVOID v44; // [rsp+60h] [rbp-69h]
  OLECHAR sz[40]; // [rsp+70h] [rbp-59h] BYREF

  Item = 0;
  Thread = 0;
  v42 = 0;
  ppv = 0;
  v12 = 0;
  v44 = 0;
  EnterCriticalSection(&g_csDllRef);
  _InterlockedIncrement(&g_cRefThisDll);
  LeaveCriticalSection(&g_csDllRef);
  EnterCriticalSection(&g_csDeviceCache);
  v13 = a6;
  if ( !a6 )
  {
    v14 = -2147467261;
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_8;
  }
  *a6 = 0;
  v16 = CDeviceCache::s_AddToCache(a1, a3, a4);
  v14 = v16;
  if ( v16 < 0 )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids,
        (unsigned int)v16);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_7;
  }
  Item = CDeviceCache::_FindItem(v17, a1);
  if ( !Item )
  {
    v14 = -2147418113;
    v15 = (PVOID *)WPP_GLOBAL_Control;
LABEL_7:
    v13 = a6;
    goto LABEL_8;
  }
  if ( !a2 )
  {
    CurrentThreadId = GetCurrentThreadId();
    Thread = CDeviceCache::s_FindThread(Item, CurrentThreadId);
    if ( Thread )
      goto LABEL_61;
  }
  if ( !*((_QWORD *)Item + 5) )
  {
    v22 = IsolationAwareDPA_Create(6);
    *((_QWORD *)Item + 5) = v22;
    if ( !v22 )
    {
      v14 = -2147024882;
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids, 2147942414LL);
        v15 = (PVOID *)WPP_GLOBAL_Control;
      }
      Thread = 0;
      goto LABEL_51;
    }
  }
  Thread = CDeviceCache::s_FindThread(Item, a2);
  v14 = 0;
  if ( !Thread )
  {
    v24 = (struct THREAD_INFO *)operator new(0x18u, v23);
    Thread = v24;
    if ( !v24 )
    {
      v14 = -2147024882;
      goto LABEL_48;
    }
    *(_DWORD *)v24 = a2;
    *((_DWORD *)v24 + 1) = 0;
    *((_QWORD *)v24 + 1) = 0;
    *((_QWORD *)v24 + 2) = 0;
    if ( (unsigned int)IsolationAwareDPA_InsertPtr(*((_QWORD *)Item + 5), v25, v24) == -1 )
    {
      v14 = -2147467259;
      THREAD_INFO::`scalar deleting destructor'(Thread, v26);
LABEL_48:
      Thread = 0;
    }
  }
  if ( v14 < 0 )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
LABEL_51:
    if ( v15 == &WPP_GLOBAL_Control )
      goto LABEL_7;
    if ( (*((_BYTE *)v15 + 28) & 2) != 0 )
    {
      WPP_SF_d(v15[2], 32, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids, (unsigned int)v14);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 2) == 0 )
      goto LABEL_7;
    v27 = 34;
    goto LABEL_57;
  }
  if ( !Thread )
  {
    v14 = -2147418113;
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_7;
  }
LABEL_61:
  *((_DWORD *)Thread + 1) = GetTickCount();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids,
      *((unsigned int *)Thread + 5));
  if ( *((_DWORD *)Thread + 5) )
    goto LABEL_78;
  v29 = g_pDeviceCache;
  *((_QWORD *)g_pDeviceCache + 8) = Item;
  *((_QWORD *)v29 + 9) = Thread;
  *((_DWORD *)v29 + 15) = a5;
  SetEvent(*((HANDLE *)v29 + 5));
  WaitForSingleObject(*((HANDLE *)g_pDeviceCache + 6), 0xFFFFFFFF);
  v30 = g_pDeviceCache;
  *((_QWORD *)g_pDeviceCache + 8) = 0;
  *((_QWORD *)v30 + 9) = 0;
  *((_DWORD *)v30 + 15) = 0;
  v14 = *((_DWORD *)v30 + 20);
  if ( v14 < 0 )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_7;
    v27 = 36;
    goto LABEL_57;
  }
  v31 = *((unsigned int *)Thread + 5);
  if ( !(_DWORD)v31 )
    goto LABEL_73;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids, v31);
LABEL_73:
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*((_DWORD *)Thread + 5) )
  {
    v14 = -2147467259;
    if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 2) == 0 )
      goto LABEL_7;
    v27 = 38;
    goto LABEL_57;
  }
LABEL_78:
  v32 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
  v14 = v32;
  if ( v32 < 0 )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_7;
    v27 = 39;
    v28 = (unsigned int)v32;
    goto LABEL_58;
  }
  v33 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, struct IPortableDeviceVtbl **))(*(_QWORD *)ppv + 40LL))(
          ppv,
          *((unsigned int *)Thread + 5),
          &GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c,
          &v42);
  v14 = v33;
  if ( v33 < 0 )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_7;
    v27 = 40;
    v28 = (unsigned int)v33;
    goto LABEL_58;
  }
  v12 = 0;
  v44 = 0;
  v41 = 0;
  v14 = CoCreateInstance(&CLSID_PortableDeviceValues, 0, 1u, &GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143, &v41);
  if ( v14 < 0 )
    goto LABEL_101;
  v14 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, const wchar_t *))(*(_QWORD *)v41 + 56LL))(
          v41,
          &WPD_CLIENT_NAME,
          L"Portable Devices Namespace");
  if ( !v14 )
  {
    v14 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, __int64))(*(_QWORD *)v41 + 72LL))(
            v41,
            &WPD_CLIENT_MAJOR_VERSION,
            10);
    if ( !v14 )
    {
      v14 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, _QWORD))(*(_QWORD *)v41 + 72LL))(
              v41,
              &WPD_CLIENT_MINOR_VERSION,
              0);
      if ( !v14 )
      {
        v14 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, __int64))(*(_QWORD *)v41 + 72LL))(
                v41,
                &WPD_CLIENT_REVISION,
                29595);
        if ( !v14 )
        {
          v14 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, __int64 *, __int64))(*(_QWORD *)v41 + 232LL))(
                  v41,
                  &WPD_CLIENT_WMDRM_APPLICATION_PRIVATE_KEY,
                  qword_18007EF30,
                  4096);
          if ( !v14 )
          {
            v14 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, __int64 *, __int64))(*(_QWORD *)v41 + 232LL))(
                    v41,
                    &WPD_CLIENT_WMDRM_APPLICATION_CERTIFICATE,
                    qword_180083500,
                    100);
            if ( !v14 )
            {
              v14 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, __int64))(*(_QWORD *)v41 + 72LL))(
                      v41,
                      &WPD_CLIENT_SECURITY_QUALITY_OF_SERVICE,
                      0x20000);
              if ( !v14 )
              {
                if ( !a5 )
                {
LABEL_97:
                  v12 = v41;
                  v44 = v41;
                  goto LABEL_100;
                }
                memset_0(sz, 0, 0x4Eu);
                StringFromGUID2(&CLSID_WPD_NAMESPACE_EXTENSION, sz, 39);
                v14 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, OLECHAR *))(*(_QWORD *)v41 + 56LL))(
                        v41,
                        &WPD_CLIENT_EVENT_COOKIE,
                        sz);
              }
            }
          }
        }
      }
    }
  }
  if ( v14 >= 0 )
    goto LABEL_97;
  if ( v41 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
  }
LABEL_100:
  if ( v14 < 0 )
  {
LABEL_101:
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids,
        (unsigned int)v14);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 2) == 0 )
      goto LABEL_7;
    v27 = 41;
LABEL_57:
    v28 = (unsigned int)v14;
LABEL_58:
    WPP_SF_d(v15[2], v27, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids, v28);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_7;
  }
  v34 = (*((__int64 (__fastcall **)(struct IPortableDeviceVtbl *, const unsigned __int16 *, LPVOID))v42->QueryInterface
         + 3))(
          v42,
          a1,
          v12);
  v14 = v34;
  if ( v34 == -2144731135 )
  {
    v14 = 0;
  }
  else if ( v34 < 0 )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_7;
    v27 = 42;
    v28 = (unsigned int)v34;
    goto LABEL_58;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids);
  ProcessHeap = GetProcessHeap();
  v36 = (struct IPortableDevice *)HeapAlloc(ProcessHeap, 8u, 0x20u);
  v41 = v36;
  if ( !v36 )
  {
    v14 = -2147024882;
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_7;
  }
  v37 = *((_DWORD *)Item + 4);
  v38 = v42;
  v36->lpVtbl = (struct IPortableDeviceVtbl *)&CDeviceProxy::`vftable';
  v36[1].lpVtbl = v38;
  if ( v38 )
    (*((void (__fastcall **)(struct IPortableDeviceVtbl *))v38->QueryInterface + 1))(v38);
  v36[2].lpVtbl = (struct IPortableDeviceVtbl *)Thread;
  LODWORD(v36[3].lpVtbl) = v37;
  HIDWORD(v36[3].lpVtbl) = 1;
  ++*((_DWORD *)Thread + 4);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_11650e54d88637af2df44923b0575f13_Traceguids,
      LODWORD(v36[2].lpVtbl->Release));
  lpVtbl = v36[2].lpVtbl;
  if ( LODWORD(lpVtbl->Release) == 1 )
  {
    AddRef = lpVtbl->AddRef;
    if ( AddRef )
    {
      DeleteTimerQueueTimer(0, AddRef, 0);
      v36[2].lpVtbl->AddRef = 0;
      DllRelease();
    }
  }
  v13 = a6;
  *a6 = v36;
  v15 = (PVOID *)WPP_GLOBAL_Control;
LABEL_8:
  v18 = g_pDeviceCache;
  if ( g_pDeviceCache )
  {
    *((_QWORD *)g_pDeviceCache + 8) = 0;
    *((_QWORD *)v18 + 9) = 0;
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( Thread && !*v13 )
  {
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x40) != 0 )
      WPP_SF_d(v15[2], 44, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids, *((unsigned int *)Thread + 4));
    if ( !*((_DWORD *)Thread + 4)
      && CreateTimerQueueTimer((PHANDLE)Thread + 1, 0, TimerProc, (char *)Thread + 8, *((_DWORD *)Item + 4), 0, 8u) )
    {
      if ( !*((_QWORD *)Thread + 1)
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids,
          "pThreadItem->hTimer");
      }
      DllAddRef();
    }
  }
  LeaveCriticalSection(&g_csDeviceCache);
  v19 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*((void (__fastcall **)(struct IPortableDeviceVtbl *))v19->QueryInterface + 2))(v19);
  }
  DllRelease();
  if ( v14 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids,
      (unsigned int)v14);
  if ( v12 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000c180  push    rbp
0x18000c182  push    rbx
0x18000c183  push    rsi
0x18000c184  push    rdi
0x18000c185  push    r12
0x18000c187  push    r13
0x18000c189  push    r14
0x18000c18b  push    r15
0x18000c18d  lea     rbp, [rsp-0Fh]
0x18000c192  sub     rsp, 0D8h
0x18000c199  mov     rax, cs:__security_cookie
0x18000c1a0  xor     rax, rsp
0x18000c1a3  mov     [rbp+47h+var_50], rax
0x18000c1a7  mov     r15, r9
0x18000c1aa  mov     rdi, r8
0x18000c1ad  mov     esi, edx
0x18000c1af  mov     r12, rcx
0x18000c1b2  mov     rax, [rbp+47h+arg_28]
0x18000c1b6  mov     [rsp+110h+var_D0], rax
0x18000c1bb  xor     eax, eax
0x18000c1bd  mov     r13d, eax
0x18000c1c0  mov     r14d, eax
0x18000c1c3  mov     [rbp+47h+var_C0], rax
0x18000c1c7  mov     [rbp+47h+ppv], rax
0x18000c1cb  mov     ebx, eax
0x18000c1cd  mov     [rbp+47h+var_B0], rax
0x18000c1d1  lea     rcx, ?g_csDllRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c1d8  call    cs:__imp_EnterCriticalSection
0x18000c1de  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18000c1e5  lea     rcx, ?g_csDllRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c1ec  call    cs:__imp_LeaveCriticalSection
0x18000c1f2  lea     rcx, ?g_csDeviceCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c1f9  call    cs:__imp_EnterCriticalSection
0x18000c1ff  mov     rdx, [rsp+110h+var_D0]
0x18000c204  test    rdx, rdx
0x18000c207  jnz     short loc_18000C221
0x18000c209  mov     edi, 80004003h
0x18000c20e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c215  xor     r15d, r15d
0x18000c218  lea     rsi, WPP_GLOBAL_Control
0x18000c21f  jmp     short loc_18000C280
0x18000c221  mov     qword ptr [rdx], 0
0x18000c228  mov     r8, r15; struct _ITEMIDLIST *
0x18000c22b  mov     rdx, rdi; struct _ITEMIDLIST *
0x18000c22e  mov     rcx, r12; unsigned __int16 *
0x18000c231  call    ?s_AddToCache@CDeviceCache@@CAJPEBGPEFAU_ITEMIDLIST@@1@Z; CDeviceCache::s_AddToCache(ushort const *,_ITEMIDLIST *,_ITEMIDLIST *)
0x18000c236  mov     edi, eax
0x18000c238  test    eax, eax
0x18000c23a  jns     loc_18000C3EA
0x18000c240  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c247  lea     rsi, WPP_GLOBAL_Control
0x18000c24e  cmp     rcx, rsi
0x18000c251  jz      short loc_18000C278
0x18000c253  test    byte ptr [rcx+1Ch], 2
0x18000c257  jz      short loc_18000C278
0x18000c259  mov     edx, 21h ; '!'
0x18000c25e  mov     r9d, eax
0x18000c261  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18000c268  mov     rcx, [rcx+10h]
0x18000c26c  call    WPP_SF_d
0x18000c271  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c278  xor     r15d, r15d
0x18000c27b  mov     rdx, [rsp+110h+var_D0]
0x18000c280  mov     rax, cs:?g_pDeviceCache@@3PEAVCDeviceCache@@EA; CDeviceCache * g_pDeviceCache
0x18000c287  test    rax, rax
0x18000c28a  jz      short loc_18000C29B
0x18000c28c  mov     [rax+40h], r15
0x18000c290  mov     [rax+48h], r15
0x18000c294  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c29b  test    r14, r14
0x18000c29e  jz      loc_18000C343
0x18000c2a4  cmp     qword ptr [rdx], 0
0x18000c2a8  jnz     loc_18000C343
0x18000c2ae  cmp     rcx, rsi
0x18000c2b1  jz      short loc_18000C2D2
0x18000c2b3  test    byte ptr [rcx+1Ch], 40h
0x18000c2b7  jz      short loc_18000C2D2
0x18000c2b9  mov     edx, 2Ch ; ','
0x18000c2be  mov     r9d, [r14+10h]
0x18000c2c2  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18000c2c9  mov     rcx, [rcx+10h]
0x18000c2cd  call    WPP_SF_d
0x18000c2d2  cmp     dword ptr [r14+10h], 0
0x18000c2d7  jnz     short loc_18000C343
0x18000c2d9  mov     [rsp+110h+Flags], 8; Flags
0x18000c2e1  mov     [rsp+110h+Period], r15d; Period
0x18000c2e6  mov     eax, [r13+10h]
0x18000c2ea  mov     [rsp+110h+DueTime], eax; DueTime
0x18000c2ee  lea     r9, [r14+8]; Parameter
0x18000c2f2  lea     r8, ?TimerProc@@YAXPEAXE@Z; Callback
0x18000c2f9  xor     edx, edx; TimerQueue
0x18000c2fb  lea     rcx, [r14+8]; phNewTimer
0x18000c2ff  call    cs:__imp_CreateTimerQueueTimer
0x18000c305  test    eax, eax
0x18000c307  jz      short loc_18000C343
0x18000c309  cmp     qword ptr [r14+8], 0
0x18000c30e  jnz     short loc_18000C33E
0x18000c310  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c317  cmp     rcx, rsi
0x18000c31a  jz      short loc_18000C33E
0x18000c31c  test    byte ptr [rcx+1Ch], 8
0x18000c320  jz      short loc_18000C33E
0x18000c322  mov     edx, 2Dh ; '-'
0x18000c327  lea     r9, aPthreaditemHti; "pThreadItem->hTimer"
0x18000c32e  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18000c335  mov     rcx, [rcx+10h]
0x18000c339  call    WPP_SF_s
0x18000c33e  call    DllAddRef
0x18000c343  lea     rcx, ?g_csDeviceCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c34a  call    cs:__imp_LeaveCriticalSection
0x18000c350  mov     rcx, [rbp+47h+var_C0]
0x18000c354  test    rcx, rcx
0x18000c357  jz      short loc_18000C369
0x18000c359  mov     [rbp+47h+var_C0], r15
0x18000c35d  mov     rax, [rcx]
0x18000c360  mov     rax, [rax+10h]
0x18000c364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c369  call    DllRelease
0x18000c36e  test    edi, edi
0x18000c370  jns     short loc_18000C39D
0x18000c372  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c379  cmp     rcx, rsi
0x18000c37c  jz      short loc_18000C39D
0x18000c37e  test    byte ptr [rcx+1Ch], 2
0x18000c382  jz      short loc_18000C39D
0x18000c384  mov     edx, 2Eh ; '.'
0x18000c389  mov     r9d, edi
0x18000c38c  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18000c393  mov     rcx, [rcx+10h]
0x18000c397  call    WPP_SF_d
0x18000c39c  nop
0x18000c39d  test    rbx, rbx
0x18000c3a0  jz      short loc_18000C3B2
0x18000c3a2  mov     rax, [rbx]
0x18000c3a5  mov     rcx, rbx
0x18000c3a8  mov     rax, [rax+10h]
0x18000c3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3b1  nop
0x18000c3b2  mov     rcx, [rbp+47h+ppv]
0x18000c3b6  test    rcx, rcx
0x18000c3b9  jz      short loc_18000C3C8
0x18000c3bb  mov     rax, [rcx]
0x18000c3be  mov     rax, [rax+10h]
0x18000c3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3c7  nop
0x18000c3c8  mov     eax, edi
0x18000c3ca  mov     rcx, [rbp+47h+var_50]
0x18000c3ce  xor     rcx, rsp; StackCookie
0x18000c3d1  call    __security_check_cookie
0x18000c3d6  add     rsp, 0D8h
0x18000c3dd  pop     r15
0x18000c3df  pop     r14
0x18000c3e1  pop     r13
0x18000c3e3  pop     r12
0x18000c3e5  pop     rdi
0x18000c3e6  pop     rsi
0x18000c3e7  pop     rbx
0x18000c3e8  pop     rbp
0x18000c3e9  retn
0x18000c3ea  mov     rdx, r12; unsigned __int16 *
0x18000c3ed  call    ?_FindItem@CDeviceCache@@AEAAPEAUDEVITEM_CACHE@@PEBG@Z; CDeviceCache::_FindItem(ushort const *)
0x18000c3f2  mov     r13, rax
0x18000c3f5  test    rax, rax
0x18000c3f8  jnz     short loc_18000C412
0x18000c3fa  mov     edi, 8000FFFFh
0x18000c3ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c406  lea     rsi, WPP_GLOBAL_Control
0x18000c40d  jmp     loc_18000C278
0x18000c412  test    esi, esi
0x18000c414  jnz     short loc_18000C432
0x18000c416  call    cs:__imp_GetCurrentThreadId
0x18000c41c  mov     edx, eax; unsigned int
0x18000c41e  mov     rcx, r13; struct DEVITEM_CACHE *
0x18000c421  call    ?s_FindThread@CDeviceCache@@CAPEAUTHREAD_INFO@@PEBUDEVITEM_CACHE@@K@Z; CDeviceCache::s_FindThread(DEVITEM_CACHE const *,ulong)
0x18000c426  mov     r14, rax
0x18000c429  test    rax, rax
0x18000c42c  jnz     loc_18000C585
0x18000c432  cmp     qword ptr [r13+28h], 0
0x18000c437  jnz     short loc_18000C491
0x18000c439  mov     ecx, 6
0x18000c43e  call    IsolationAwareDPA_Create
0x18000c443  mov     [r13+28h], rax
0x18000c447  test    rax, rax
0x18000c44a  jnz     short loc_18000C491
0x18000c44c  mov     edi, 8007000Eh
0x18000c451  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c458  lea     rsi, WPP_GLOBAL_Control
0x18000c45f  cmp     rcx, rsi
0x18000c462  jz      short loc_18000C489
0x18000c464  test    byte ptr [rcx+1Ch], 2
0x18000c468  jz      short loc_18000C489
0x18000c46a  mov     edx, 1Fh
0x18000c46f  mov     r9d, edi
0x18000c472  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18000c479  mov     rcx, [rcx+10h]
0x18000c47d  call    WPP_SF_d
0x18000c482  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c489  xor     r15d, r15d
0x18000c48c  mov     r14d, r15d
0x18000c48f  jmp     short loc_18000C503
0x18000c491  mov     edx, esi; unsigned int
0x18000c493  mov     rcx, r13; struct DEVITEM_CACHE *
0x18000c496  call    ?s_FindThread@CDeviceCache@@CAPEAUTHREAD_INFO@@PEBUDEVITEM_CACHE@@K@Z; CDeviceCache::s_FindThread(DEVITEM_CACHE const *,ulong)
0x18000c49b  mov     r14, rax
0x18000c49e  xor     r15d, r15d
0x18000c4a1  mov     edi, r15d
0x18000c4a4  test    rax, rax
0x18000c4a7  jnz     short loc_18000C4F1
0x18000c4a9  mov     ecx, 18h; unsigned __int64
0x18000c4ae  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c4b3  mov     r14, rax
0x18000c4b6  test    rax, rax
0x18000c4b9  jz      short loc_18000C4E9
0x18000c4bb  mov     [rax], esi
0x18000c4bd  mov     [rax+4], r15d
0x18000c4c1  mov     [rax+8], r15
0x18000c4c5  mov     [rax+10h], r15
0x18000c4c9  mov     r8, rax
0x18000c4cc  mov     rcx, [r13+28h]
0x18000c4d0  call    IsolationAwareDPA_InsertPtr
0x18000c4d5  cmp     eax, 0FFFFFFFFh
0x18000c4d8  jnz     short loc_18000C4F1
0x18000c4da  mov     edi, 80004005h
0x18000c4df  mov     rcx, r14; this
0x18000c4e2  call    ??_GTHREAD_INFO@@QEAAPEAXI@Z; THREAD_INFO::`scalar deleting destructor'(uint)
0x18000c4e7  jmp     short loc_18000C4EE
0x18000c4e9  mov     edi, 8007000Eh
0x18000c4ee  mov     r14, r15
0x18000c4f1  test    edi, edi
0x18000c4f3  jns     short loc_18000C568
0x18000c4f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4fc  lea     rsi, WPP_GLOBAL_Control
0x18000c503  cmp     rcx, rsi
0x18000c506  jz      loc_18000C27B
0x18000c50c  test    byte ptr [rcx+1Ch], 2
0x18000c510  jz      short loc_18000C531
0x18000c512  mov     edx, 20h ; ' '
0x18000c517  mov     r9d, edi
0x18000c51a  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18000c521  mov     rcx, [rcx+10h]
0x18000c525  call    WPP_SF_d
0x18000c52a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c531  cmp     rcx, rsi
0x18000c534  jz      loc_18000C27B
0x18000c53a  test    byte ptr [rcx+1Ch], 2
0x18000c53e  jz      loc_18000C27B
0x18000c544  mov     edx, 22h ; '"'
0x18000c549  mov     r9d, edi
0x18000c54c  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18000c553  mov     rcx, [rcx+10h]
0x18000c557  call    WPP_SF_d
0x18000c55c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c563  jmp     loc_18000C27B
0x18000c568  test    r14, r14
0x18000c56b  jnz     short loc_18000C588
0x18000c56d  mov     edi, 8000FFFFh
0x18000c572  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c579  lea     rsi, WPP_GLOBAL_Control
0x18000c580  jmp     loc_18000C27B
0x18000c585  xor     r15d, r15d
0x18000c588  call    cs:__imp_GetTickCount
0x18000c58e  mov     [r14+4], eax
0x18000c592  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c599  lea     rax, WPP_GLOBAL_Control
0x18000c5a0  cmp     rcx, rax
0x18000c5a3  jz      short loc_18000C5CB
0x18000c5a5  test    byte ptr [rcx+1Ch], 40h
0x18000c5a9  jz      short loc_18000C5CB
0x18000c5ab  mov     edx, 23h ; '#'
0x18000c5b0  mov     r9d, [r14+14h]
0x18000c5b4  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18000c5bb  mov     rcx, [rcx+10h]
0x18000c5bf  call    WPP_SF_d
0x18000c5c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5cb  mov     esi, [rbp+47h+arg_20]
0x18000c5ce  cmp     dword ptr [r14+14h], 0
0x18000c5d3  jnz     loc_18000C6BE
0x18000c5d9  mov     rcx, cs:?g_pDeviceCache@@3PEAVCDeviceCache@@EA; CDeviceCache * g_pDeviceCache
0x18000c5e0  mov     [rcx+40h], r13
0x18000c5e4  mov     [rcx+48h], r14
0x18000c5e8  mov     [rcx+3Ch], esi
0x18000c5eb  mov     rcx, [rcx+28h]; hEvent
0x18000c5ef  call    cs:__imp_SetEvent
0x18000c5f5  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000c5fa  mov     rcx, cs:?g_pDeviceCache@@3PEAVCDeviceCache@@EA; CDeviceCache * g_pDeviceCache
0x18000c601  mov     rcx, [rcx+30h]; hHandle
0x18000c605  call    cs:__imp_WaitForSingleObject
0x18000c60b  mov     rax, cs:?g_pDeviceCache@@3PEAVCDeviceCache@@EA; CDeviceCache * g_pDeviceCache
0x18000c612  mov     [rax+40h], r15
0x18000c616  mov     [rax+48h], r15
0x18000c61a  mov     [rax+3Ch], r15d
0x18000c61e  mov     edi, [rax+50h]
0x18000c621  test    edi, edi
0x18000c623  jns     short loc_18000C650
0x18000c625  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c62c  lea     rsi, WPP_GLOBAL_Control
0x18000c633  cmp     rcx, rsi
0x18000c636  jz      loc_18000C27B
0x18000c63c  test    byte ptr [rcx+1Ch], 2
0x18000c640  jz      loc_18000C27B
  ... truncated ...
```
