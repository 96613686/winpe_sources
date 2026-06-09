# WmiEventManager::RaiseEvent(WmiData *,int)

- ea: `0x18004b0c0`
- end: `0x18004b8e6`
- name: `?RaiseEvent@WmiEventManager@@QEAAJPEAUWmiData@@H@Z`
- size: `2086`
- prototype: `__int64 __fastcall(WmiEventManager *__hidden this, struct WmiData *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004bbc0`

## callees

- `0x180015050`
- `0x18004af18`
- `0x18004b0c0`
- `0x18004b960`
- `0x18004b9b8`
- `0x18004ba08`
- `0x18004baa0`
- `0x18004d854`
- `0x180065b60`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18004b15d`
- `KERNEL32!EnterCriticalSection` at `0x18004b15d`
- `KERNEL32!LeaveCriticalSection` at `0x18004b237`
- `KERNEL32!LeaveCriticalSection` at `0x18004b8c6`
- `KERNEL32!LeaveCriticalSection` at `0x18004b237`
- `KERNEL32!LeaveCriticalSection` at `0x18004b8c6`
- `ole32!CoUninitialize` at `0x18004b87f`
- `ole32!CoUninitialize` at `0x18004b87f`
- `OLEAUT32!__imp_SysAllocString` at `0x18004b17e`
- `OLEAUT32!__imp_SysAllocString` at `0x18004b17e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b861`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b861`

## string_xrefs

- `0x18004b369`: `ApplicationVirtualPath`
- `0x18004b385`: `ApplicationPath`
- `0x18004b3e0`: `ProcessID`
- `0x18004b462`: `RequestPath`
- `0x18004b4fc`: `RequestThreadAccountName`
- `0x18004b545`: `ThreadCount`
- `0x18004b640`: `ThreadID`
- `0x18004b65f`: `ThreadAccountName`
- `0x18004b69c`: `IsImpersonating`
- `0x18004b791`: `UserAgent`

## pseudocode

```c
__int64 __fastcall WmiEventManager::RaiseEvent(WmiEventManager *this, struct WmiData *a2, int a3)
{
  int v3; // edi
  __int64 v7; // r14
  signed int WmiObjects; // ebx
  BSTR v9; // rbx
  int v10; // eax
  struct IUnknown *v11; // rcx
  struct IUnknown *v12; // rcx
  int v13; // eax
  int v14; // ebx
  unsigned int v15; // eax
  struct IUnknown *v16; // rcx
  struct IUnknown *v18; // [rsp+40h] [rbp-20h] BYREF
  struct IUnknown *v19; // [rsp+48h] [rbp-18h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-10h]
  struct IUnknown *v21; // [rsp+58h] [rbp-8h] BYREF
  struct IUnknown *v22; // [rsp+A8h] [rbp+48h] BYREF
  int v23; // [rsp+B0h] [rbp+50h] BYREF
  struct IUnknown *v24; // [rsp+B8h] [rbp+58h] BYREF

  v22 = 0;
  v3 = 0;
  v23 = 0;
  v21 = 0;
  bstrString = 0;
  v19 = 0;
  v18 = 0;
  v24 = 0;
  v7 = *(int *)a2;
  if ( !a3 )
  {
    v18 = (struct IUnknown *)*((_QWORD *)this + 1);
    v24 = (struct IUnknown *)*((_QWORD *)this + 2);
  }
  WmiObjects = EnsureCoInitialized(&v23);
  if ( !WmiObjects && (unsigned int)v7 <= 0xD )
  {
    if ( !*((_QWORD *)this + v7 + 5) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
      v3 = 1;
      if ( !*((_QWORD *)this + v7 + 5) )
      {
        bstrString = SysAllocString((const OLECHAR *)*(&g_eventTypeInfos + 2 * v7));
        v9 = bstrString;
        if ( !bstrString )
        {
          WmiObjects = -2147024882;
          goto LABEL_87;
        }
        if ( a3 )
        {
          WmiObjects = WmiEventManager::GetWmiObjects((LPVOID *)&v19, 0, (struct IWbemServices **)&v24);
          if ( WmiObjects )
            goto LABEL_87;
          v9 = bstrString;
        }
        v10 = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, _QWORD, _QWORD, struct IUnknown **, _QWORD))v24->lpVtbl[2].QueryInterface)(
                v24,
                v9,
                0,
                0,
                &v21,
                0);
        if ( v10
          || (v10 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, struct IUnknown **))v21->lpVtbl[5].QueryInterface)(
                      v21,
                      0,
                      &v22)) != 0 )
        {
          WmiObjects = (unsigned __int16)v10 | 0x80070000;
          if ( v10 <= 0 )
            WmiObjects = v10;
          goto LABEL_87;
        }
        v11 = v22;
        *((_QWORD *)this + v7 + 5) = v22;
        ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->AddRef)(v11);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
    }
    v12 = v22;
    if ( !v22 )
    {
      v13 = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown **))(**((_QWORD **)this + v7 + 5) + 96LL))(
              *((_QWORD *)this + v7 + 5),
              &v22);
      if ( v13 )
        goto LABEL_21;
      v12 = v22;
    }
    v14 = *((_DWORD *)&g_eventTypeInfos + 4 * v7 + 2);
    v13 = SetInstancePropertyInt((struct IWbemClassObject *)v12, *((_DWORD *)a2 + 1), L"EventCode");
    if ( v13 )
      goto LABEL_21;
    v13 = SetInstancePropertyInt((struct IWbemClassObject *)v22, *((_DWORD *)a2 + 2), L"EventDetailCode");
    if ( v13 )
      goto LABEL_21;
    v13 = SetInstancePropertySpecial((struct IWbemClassObject *)v22, *((unsigned __int16 **)a2 + 2), L"EventTime");
    if ( v13 )
      goto LABEL_21;
    v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 3), L"EventMessage");
    if ( v13 )
      goto LABEL_21;
    v13 = SetInstancePropertySpecial((struct IWbemClassObject *)v22, *((unsigned __int16 **)a2 + 4), L"EventID");
    if ( v13 )
      goto LABEL_21;
    v13 = SetInstancePropertySpecial((struct IWbemClassObject *)v22, *((unsigned __int16 **)a2 + 5), L"SequenceNumber");
    if ( v13 )
      goto LABEL_21;
    v13 = SetInstancePropertySpecial((struct IWbemClassObject *)v22, *((unsigned __int16 **)a2 + 6), L"Occurrence");
    if ( v13 )
      goto LABEL_21;
    v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 11), L"ApplicationDomain");
    if ( v13 )
      goto LABEL_21;
    v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 12), L"TrustLevel");
    if ( v13 )
      goto LABEL_21;
    v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 13), L"ApplicationVirtualPath");
    if ( v13 )
      goto LABEL_21;
    v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 14), L"ApplicationPath");
    if ( v13 )
      goto LABEL_21;
    v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 10), L"MachineName");
    if ( v13 )
      goto LABEL_21;
    v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 15), L"CustomEventDetails");
    if ( v13 )
      goto LABEL_21;
    if ( (v14 & WebProcessInformation) != 0 )
    {
      v13 = SetInstancePropertyInt((struct IWbemClassObject *)v22, *((_DWORD *)a2 + 14), L"ProcessID");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 8), L"ProcessName");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 9), L"AccountName");
      if ( v13 )
        goto LABEL_21;
    }
    if ( (v14 & WebRequestInformation) != 0 )
    {
      v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 16), L"RequestUrl");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 17), L"RequestPath");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 18), L"UserHostAddress");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 19), L"UserName");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertyBoolean((struct IWbemClassObject *)v22, *((_DWORD *)a2 + 40), L"UserAuthenticated");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 21), L"UserAuthenticationType");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertyString(
              (struct IWbemClassObject *)v22,
              *((OLECHAR **)a2 + 22),
              L"RequestThreadAccountName");
      if ( v13 )
        goto LABEL_21;
    }
    if ( (v14 & WebProcessStatistics) != 0 )
    {
      v13 = SetInstancePropertySpecial(
              (struct IWbemClassObject *)v22,
              *((unsigned __int16 **)a2 + 23),
              L"ProcessStartTime");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertyInt((struct IWbemClassObject *)v22, *((_DWORD *)a2 + 48), L"ThreadCount");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertySpecial((struct IWbemClassObject *)v22, *((unsigned __int16 **)a2 + 25), L"WorkingSet");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertySpecial(
              (struct IWbemClassObject *)v22,
              *((unsigned __int16 **)a2 + 26),
              L"PeakWorkingSet");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertySpecial(
              (struct IWbemClassObject *)v22,
              *((unsigned __int16 **)a2 + 27),
              L"ManagedHeapSize");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertyInt((struct IWbemClassObject *)v22, *((_DWORD *)a2 + 56), L"AppdomainCount");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertyInt((struct IWbemClassObject *)v22, *((_DWORD *)a2 + 57), L"RequestsExecuting");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertyInt((struct IWbemClassObject *)v22, *((_DWORD *)a2 + 58), L"RequestsQueued");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertyInt((struct IWbemClassObject *)v22, *((_DWORD *)a2 + 59), L"RequestsRejected");
      if ( v13 )
        goto LABEL_21;
    }
    if ( (v14 & WebThreadInformation) != 0 )
    {
      v13 = SetInstancePropertyInt((struct IWbemClassObject *)v22, *((_DWORD *)a2 + 60), L"ThreadID");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 31), L"ThreadAccountName");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 32), L"StackTrace");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertyBoolean((struct IWbemClassObject *)v22, *((_DWORD *)a2 + 66), L"IsImpersonating");
      if ( v13 )
        goto LABEL_21;
    }
    if ( (v14 & Exception) != 0 )
    {
      v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 34), L"ExceptionType");
      if ( v13 )
        goto LABEL_21;
      v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 35), L"ExceptionMessage");
      if ( v13 )
        goto LABEL_21;
    }
    if ( (v14 & NameToAuthenticate) != 0 )
    {
      v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 36), L"NameToAuthenticate");
      if ( v13 )
        goto LABEL_21;
    }
    if ( (v14 & ViewStateException) != 0 )
    {
      v13 = SetInstancePropertyString(
              (struct IWbemClassObject *)v22,
              *((OLECHAR **)a2 + 35),
              L"ViewStateExceptionMessage");
      if ( v13
        || (v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 37), L"RemoteAddress")) != 0
        || (v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 38), L"RemotePort")) != 0
        || (v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 39), L"UserAgent")) != 0
        || (v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 40), L"PersistedState")) != 0
        || (v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 41), L"Referer")) != 0
        || (v13 = SetInstancePropertyString((struct IWbemClassObject *)v22, *((OLECHAR **)a2 + 42), L"Path")) != 0 )
      {
LABEL_21:
        WmiObjects = (unsigned __int16)v13 | 0x80070000;
        if ( v13 <= 0 )
          WmiObjects = v13;
LABEL_86:
        v3 = 0;
        goto LABEL_87;
      }
    }
    if ( !a3
      || (v3 = 0, (WmiObjects = WmiEventManager::GetWmiObjects((LPVOID *)&v19, (struct IWbemObjectSink **)&v18, 0)) == 0) )
    {
      WmiObjects = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **))v18->lpVtbl[1].QueryInterface)(
                     v18,
                     1,
                     &v22);
      if ( WmiObjects == 1 )
      {
        WmiObjects = 0;
      }
      else if ( WmiObjects )
      {
        v15 = (unsigned __int16)WmiObjects | 0x80070000;
        if ( WmiObjects <= 0 )
          v15 = WmiObjects;
        WmiObjects = v15;
      }
      goto LABEL_86;
    }
  }
LABEL_87:
  SysFreeString(bstrString);
  ReleaseInterface(v22);
  ReleaseInterface(v21);
  if ( v23 )
    CoUninitialize();
  if ( a3 )
  {
    ReleaseInterface(v24);
    ReleaseInterface(v18);
    v16 = v19;
    if ( v19 )
    {
      ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl[1].AddRef)(v19);
      v16 = v19;
    }
    ReleaseInterface(v16);
  }
  if ( v3 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  return (unsigned int)WmiObjects;
}

```

## disassembly

```asm
0x18004b0c0  mov     [rsp-38h+arg_0], rbx
0x18004b0c5  push    rbp
0x18004b0c6  push    rsi
0x18004b0c7  push    rdi
0x18004b0c8  push    r12
0x18004b0ca  push    r13
0x18004b0cc  push    r14
0x18004b0ce  push    r15
0x18004b0d0  mov     rbp, rsp
0x18004b0d3  sub     rsp, 60h
0x18004b0d7  and     [rbp+arg_8], 0
0x18004b0dc  xor     edi, edi
0x18004b0de  and     [rbp+arg_10], edi
0x18004b0e1  mov     r12d, r8d
0x18004b0e4  and     [rbp+var_8], 0
0x18004b0e9  mov     rsi, rdx
0x18004b0ec  and     [rbp+bstrString], 0
0x18004b0f1  mov     r13, rcx
0x18004b0f4  and     [rbp+var_18], 0
0x18004b0f9  and     [rbp+var_20], 0
0x18004b0fe  and     [rbp+arg_18], 0
0x18004b103  movsxd  r14, dword ptr [rdx]
0x18004b106  test    r8d, r8d
0x18004b109  jnz     short loc_18004B11B
0x18004b10b  mov     rax, [rcx+8]
0x18004b10f  mov     [rbp+var_20], rax
0x18004b113  mov     rax, [rcx+10h]
0x18004b117  mov     [rbp+arg_18], rax
0x18004b11b  lea     rcx, [rbp+arg_10]; int *
0x18004b11f  call    ?EnsureCoInitialized@@YAJPEAH@Z; EnsureCoInitialized(int *)
0x18004b124  mov     ebx, eax
0x18004b126  test    eax, eax
0x18004b128  jnz     loc_18004B85D
0x18004b12e  test    r14d, r14d
0x18004b131  js      loc_18004B85D
0x18004b137  cmp     r14d, 0Eh
0x18004b13b  jnb     loc_18004B85D
0x18004b141  lea     rbx, ?g_eventTypeInfos@@3PAUEventTypeInfo@@A; EventTypeInfo near * g_eventTypeInfos
0x18004b148  cmp     [r13+r14*8+28h], rdi
0x18004b14d  jnz     loc_18004B23D
0x18004b153  lea     r15, [r13+0C0h]
0x18004b15a  mov     rcx, r15; lpCriticalSection
0x18004b15d  call    cs:__imp_EnterCriticalSection
0x18004b163  cmp     qword ptr [r13+r14*8+28h], 0
0x18004b169  mov     edi, 1
0x18004b16e  jnz     loc_18004B234
0x18004b174  mov     rcx, r14
0x18004b177  add     rcx, rcx
0x18004b17a  mov     rcx, [rbx+rcx*8]; psz
0x18004b17e  call    cs:__imp_SysAllocString
0x18004b184  mov     [rbp+bstrString], rax
0x18004b188  mov     rbx, rax
0x18004b18b  test    rax, rax
0x18004b18e  jnz     short loc_18004B19A
0x18004b190  mov     ebx, 8007000Eh
0x18004b195  jmp     loc_18004B85D
0x18004b19a  test    r12d, r12d
0x18004b19d  jz      short loc_18004B1BC
0x18004b19f  lea     r8, [rbp+arg_18]; struct IWbemServices **
0x18004b1a3  xor     edx, edx; struct IWbemObjectSink **
0x18004b1a5  lea     rcx, [rbp+var_18]; ppv
0x18004b1a9  call    ?GetWmiObjects@WmiEventManager@@CAJPEAPEAUIWbemDecoupledBasicEventProvider@@PEAPEAUIWbemObjectSink@@PEAPEAUIWbemServices@@@Z; WmiEventManager::GetWmiObjects(IWbemDecoupledBasicEventProvider * *,IWbemObjectSink * *,IWbemServices * *)
0x18004b1ae  mov     ebx, eax
0x18004b1b0  test    eax, eax
0x18004b1b2  jnz     loc_18004B85D
0x18004b1b8  mov     rbx, [rbp+bstrString]
0x18004b1bc  mov     rcx, [rbp+arg_18]
0x18004b1c0  lea     rdx, [rbp+var_8]
0x18004b1c4  and     [rsp+60h+var_38], 0
0x18004b1ca  xor     r9d, r9d
0x18004b1cd  mov     [rsp+60h+var_40], rdx
0x18004b1d2  xor     r8d, r8d
0x18004b1d5  mov     rdx, rbx
0x18004b1d8  mov     rax, [rcx]
0x18004b1db  mov     rax, [rax+30h]
0x18004b1df  call    cs:__guard_dispatch_icall_fptr
0x18004b1e5  test    eax, eax
0x18004b1e7  jz      short loc_18004B1FC
0x18004b1e9  movzx   ebx, ax
0x18004b1ec  or      ebx, 80070000h
0x18004b1f2  test    eax, eax
0x18004b1f4  cmovle  ebx, eax
0x18004b1f7  jmp     loc_18004B85D
0x18004b1fc  mov     rcx, [rbp+var_8]
0x18004b200  lea     r8, [rbp+arg_8]
0x18004b204  xor     edx, edx
0x18004b206  mov     rax, [rcx]
0x18004b209  mov     rax, [rax+78h]
0x18004b20d  call    cs:__guard_dispatch_icall_fptr
0x18004b213  test    eax, eax
0x18004b215  jnz     short loc_18004B1E9
0x18004b217  mov     rcx, [rbp+arg_8]
0x18004b21b  mov     [r13+r14*8+28h], rcx
0x18004b220  mov     rax, [rcx]
0x18004b223  mov     rax, [rax+8]
0x18004b227  call    cs:__guard_dispatch_icall_fptr
0x18004b22d  lea     rbx, ?g_eventTypeInfos@@3PAUEventTypeInfo@@A; EventTypeInfo near * g_eventTypeInfos
0x18004b234  mov     rcx, r15; lpCriticalSection
0x18004b237  call    cs:__imp_LeaveCriticalSection
0x18004b23d  mov     rcx, [rbp+arg_8]
0x18004b241  test    rcx, rcx
0x18004b244  jnz     short loc_18004B277
0x18004b246  mov     rcx, [r13+r14*8+28h]
0x18004b24b  lea     rdx, [rbp+arg_8]
0x18004b24f  mov     rax, [rcx]
0x18004b252  mov     rax, [rax+60h]
0x18004b256  call    cs:__guard_dispatch_icall_fptr
0x18004b25c  test    eax, eax
0x18004b25e  jz      short loc_18004B273
0x18004b260  movzx   ebx, ax
0x18004b263  or      ebx, 80070000h
0x18004b269  test    eax, eax
0x18004b26b  cmovle  ebx, eax
0x18004b26e  jmp     loc_18004B85B
0x18004b273  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b277  mov     edx, [rsi+4]; int
0x18004b27a  lea     r8, aEventcode; "EventCode"
0x18004b281  add     r14, r14
0x18004b284  mov     ebx, [rbx+r14*8+8]
0x18004b289  call    ?SetInstancePropertyInt@@YAJPEAUIWbemClassObject@@HPEBG@Z; SetInstancePropertyInt(IWbemClassObject *,int,ushort const *)
0x18004b28e  test    eax, eax
0x18004b290  jnz     short loc_18004B260
0x18004b292  mov     edx, [rsi+8]; int
0x18004b295  lea     r8, aEventdetailcod; "EventDetailCode"
0x18004b29c  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b2a0  call    ?SetInstancePropertyInt@@YAJPEAUIWbemClassObject@@HPEBG@Z; SetInstancePropertyInt(IWbemClassObject *,int,ushort const *)
0x18004b2a5  test    eax, eax
0x18004b2a7  jnz     short loc_18004B260
0x18004b2a9  mov     rdx, [rsi+10h]; unsigned __int16 *
0x18004b2ad  lea     r8, aEventtime; "EventTime"
0x18004b2b4  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b2b8  call    ?SetInstancePropertySpecial@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertySpecial(IWbemClassObject *,ushort *,ushort const *)
0x18004b2bd  test    eax, eax
0x18004b2bf  jnz     short loc_18004B260
0x18004b2c1  mov     rdx, [rsi+18h]; psz
0x18004b2c5  lea     r8, aEventmessage; "EventMessage"
0x18004b2cc  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b2d0  call    ?SetInstancePropertyString@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertyString(IWbemClassObject *,ushort *,ushort const *)
0x18004b2d5  test    eax, eax
0x18004b2d7  jnz     short loc_18004B260
0x18004b2d9  mov     rdx, [rsi+20h]; unsigned __int16 *
0x18004b2dd  lea     r8, aEventid; "EventID"
0x18004b2e4  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b2e8  call    ?SetInstancePropertySpecial@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertySpecial(IWbemClassObject *,ushort *,ushort const *)
0x18004b2ed  test    eax, eax
0x18004b2ef  jnz     loc_18004B260
0x18004b2f5  mov     rdx, [rsi+28h]; unsigned __int16 *
0x18004b2f9  lea     r8, aSequencenumber; "SequenceNumber"
0x18004b300  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b304  call    ?SetInstancePropertySpecial@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertySpecial(IWbemClassObject *,ushort *,ushort const *)
0x18004b309  test    eax, eax
0x18004b30b  jnz     loc_18004B260
0x18004b311  mov     rdx, [rsi+30h]; unsigned __int16 *
0x18004b315  lea     r8, aOccurrence; "Occurrence"
0x18004b31c  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b320  call    ?SetInstancePropertySpecial@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertySpecial(IWbemClassObject *,ushort *,ushort const *)
0x18004b325  test    eax, eax
0x18004b327  jnz     loc_18004B260
0x18004b32d  mov     rdx, [rsi+58h]; psz
0x18004b331  lea     r8, aApplicationdom; "ApplicationDomain"
0x18004b338  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b33c  call    ?SetInstancePropertyString@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertyString(IWbemClassObject *,ushort *,ushort const *)
0x18004b341  test    eax, eax
0x18004b343  jnz     loc_18004B260
0x18004b349  mov     rdx, [rsi+60h]; psz
0x18004b34d  lea     r8, aTrustlevel; "TrustLevel"
0x18004b354  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b358  call    ?SetInstancePropertyString@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertyString(IWbemClassObject *,ushort *,ushort const *)
0x18004b35d  test    eax, eax
0x18004b35f  jnz     loc_18004B260
0x18004b365  mov     rdx, [rsi+68h]; psz
0x18004b369  lea     r8, aApplicationvir; "ApplicationVirtualPath"
0x18004b370  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b374  call    ?SetInstancePropertyString@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertyString(IWbemClassObject *,ushort *,ushort const *)
0x18004b379  test    eax, eax
0x18004b37b  jnz     loc_18004B260
0x18004b381  mov     rdx, [rsi+70h]; psz
0x18004b385  lea     r8, aApplicationpat; "ApplicationPath"
0x18004b38c  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b390  call    ?SetInstancePropertyString@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertyString(IWbemClassObject *,ushort *,ushort const *)
0x18004b395  test    eax, eax
0x18004b397  jnz     loc_18004B260
0x18004b39d  mov     rdx, [rsi+50h]; psz
0x18004b3a1  lea     r8, aMachinename; "MachineName"
0x18004b3a8  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b3ac  call    ?SetInstancePropertyString@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertyString(IWbemClassObject *,ushort *,ushort const *)
0x18004b3b1  test    eax, eax
0x18004b3b3  jnz     loc_18004B260
0x18004b3b9  mov     rdx, [rsi+78h]; psz
0x18004b3bd  lea     r8, aCustomeventdet; "CustomEventDetails"
0x18004b3c4  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b3c8  call    ?SetInstancePropertyString@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertyString(IWbemClassObject *,ushort *,ushort const *)
0x18004b3cd  test    eax, eax
0x18004b3cf  jnz     loc_18004B260
0x18004b3d5  test    cs:?WebProcessInformation@@3HA, ebx; int WebProcessInformation
0x18004b3db  jz      short loc_18004B430
0x18004b3dd  mov     edx, [rsi+38h]; int
0x18004b3e0  lea     r8, aProcessid; "ProcessID"
0x18004b3e7  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b3eb  call    ?SetInstancePropertyInt@@YAJPEAUIWbemClassObject@@HPEBG@Z; SetInstancePropertyInt(IWbemClassObject *,int,ushort const *)
0x18004b3f0  test    eax, eax
0x18004b3f2  jnz     loc_18004B260
0x18004b3f8  mov     rdx, [rsi+40h]; psz
0x18004b3fc  lea     r8, aProcessname; "ProcessName"
0x18004b403  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b407  call    ?SetInstancePropertyString@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertyString(IWbemClassObject *,ushort *,ushort const *)
0x18004b40c  test    eax, eax
0x18004b40e  jnz     loc_18004B260
0x18004b414  mov     rdx, [rsi+48h]; psz
0x18004b418  lea     r8, aAccountname; "AccountName"
0x18004b41f  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b423  call    ?SetInstancePropertyString@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertyString(IWbemClassObject *,ushort *,ushort const *)
0x18004b428  test    eax, eax
0x18004b42a  jnz     loc_18004B260
0x18004b430  test    cs:?WebRequestInformation@@3HA, ebx; int WebRequestInformation
0x18004b436  jz      loc_18004B514
0x18004b43c  mov     rdx, [rsi+80h]; psz
0x18004b443  lea     r8, aRequesturl; "RequestUrl"
0x18004b44a  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b44e  call    ?SetInstancePropertyString@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertyString(IWbemClassObject *,ushort *,ushort const *)
0x18004b453  test    eax, eax
0x18004b455  jnz     loc_18004B260
0x18004b45b  mov     rdx, [rsi+88h]; psz
0x18004b462  lea     r8, aRequestpath; "RequestPath"
0x18004b469  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b46d  call    ?SetInstancePropertyString@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertyString(IWbemClassObject *,ushort *,ushort const *)
0x18004b472  test    eax, eax
0x18004b474  jnz     loc_18004B260
0x18004b47a  mov     rdx, [rsi+90h]; psz
0x18004b481  lea     r8, aUserhostaddres; "UserHostAddress"
0x18004b488  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b48c  call    ?SetInstancePropertyString@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertyString(IWbemClassObject *,ushort *,ushort const *)
0x18004b491  test    eax, eax
0x18004b493  jnz     loc_18004B260
0x18004b499  mov     rdx, [rsi+98h]; psz
0x18004b4a0  lea     r8, aUsername; "UserName"
0x18004b4a7  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b4ab  call    ?SetInstancePropertyString@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertyString(IWbemClassObject *,ushort *,ushort const *)
0x18004b4b0  test    eax, eax
0x18004b4b2  jnz     loc_18004B260
0x18004b4b8  mov     edx, [rsi+0A0h]; int
0x18004b4be  lea     r8, aUserauthentica; "UserAuthenticated"
0x18004b4c5  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b4c9  call    ?SetInstancePropertyBoolean@@YAJPEAUIWbemClassObject@@HPEBG@Z; SetInstancePropertyBoolean(IWbemClassObject *,int,ushort const *)
0x18004b4ce  test    eax, eax
0x18004b4d0  jnz     loc_18004B260
0x18004b4d6  mov     rdx, [rsi+0A8h]; psz
0x18004b4dd  lea     r8, aUserauthentica_0; "UserAuthenticationType"
0x18004b4e4  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b4e8  call    ?SetInstancePropertyString@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertyString(IWbemClassObject *,ushort *,ushort const *)
0x18004b4ed  test    eax, eax
0x18004b4ef  jnz     loc_18004B260
0x18004b4f5  mov     rdx, [rsi+0B0h]; psz
0x18004b4fc  lea     r8, aRequestthreada; "RequestThreadAccountName"
0x18004b503  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b507  call    ?SetInstancePropertyString@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertyString(IWbemClassObject *,ushort *,ushort const *)
0x18004b50c  test    eax, eax
0x18004b50e  jnz     loc_18004B260
0x18004b514  test    cs:?WebProcessStatistics@@3HA, ebx; int WebProcessStatistics
0x18004b51a  jz      loc_18004B632
0x18004b520  mov     rdx, [rsi+0B8h]; unsigned __int16 *
0x18004b527  lea     r8, aProcessstartti; "ProcessStartTime"
0x18004b52e  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b532  call    ?SetInstancePropertySpecial@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertySpecial(IWbemClassObject *,ushort *,ushort const *)
0x18004b537  test    eax, eax
0x18004b539  jnz     loc_18004B260
0x18004b53f  mov     edx, [rsi+0C0h]; int
0x18004b545  lea     r8, aThreadcount; "ThreadCount"
0x18004b54c  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b550  call    ?SetInstancePropertyInt@@YAJPEAUIWbemClassObject@@HPEBG@Z; SetInstancePropertyInt(IWbemClassObject *,int,ushort const *)
0x18004b555  test    eax, eax
0x18004b557  jnz     loc_18004B260
0x18004b55d  mov     rdx, [rsi+0C8h]; unsigned __int16 *
0x18004b564  lea     r8, aWorkingset; "WorkingSet"
0x18004b56b  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b56f  call    ?SetInstancePropertySpecial@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertySpecial(IWbemClassObject *,ushort *,ushort const *)
0x18004b574  test    eax, eax
0x18004b576  jnz     loc_18004B260
0x18004b57c  mov     rdx, [rsi+0D0h]; unsigned __int16 *
0x18004b583  lea     r8, aPeakworkingset; "PeakWorkingSet"
0x18004b58a  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b58e  call    ?SetInstancePropertySpecial@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertySpecial(IWbemClassObject *,ushort *,ushort const *)
0x18004b593  test    eax, eax
0x18004b595  jnz     loc_18004B260
0x18004b59b  mov     rdx, [rsi+0D8h]; unsigned __int16 *
0x18004b5a2  lea     r8, aManagedheapsiz; "ManagedHeapSize"
0x18004b5a9  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b5ad  call    ?SetInstancePropertySpecial@@YAJPEAUIWbemClassObject@@PEAGPEBG@Z; SetInstancePropertySpecial(IWbemClassObject *,ushort *,ushort const *)
0x18004b5b2  test    eax, eax
0x18004b5b4  jnz     loc_18004B260
0x18004b5ba  mov     edx, [rsi+0E0h]; int
0x18004b5c0  lea     r8, aAppdomaincount; "AppdomainCount"
0x18004b5c7  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b5cb  call    ?SetInstancePropertyInt@@YAJPEAUIWbemClassObject@@HPEBG@Z; SetInstancePropertyInt(IWbemClassObject *,int,ushort const *)
0x18004b5d0  test    eax, eax
0x18004b5d2  jnz     loc_18004B260
0x18004b5d8  mov     edx, [rsi+0E4h]; int
0x18004b5de  lea     r8, aRequestsexecut; "RequestsExecuting"
0x18004b5e5  mov     rcx, [rbp+arg_8]; struct IWbemClassObject *
0x18004b5e9  call    ?SetInstancePropertyInt@@YAJPEAUIWbemClassObject@@HPEBG@Z; SetInstancePropertyInt(IWbemClassObject *,int,ushort const *)
  ... truncated ...
```
