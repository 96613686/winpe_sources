# ScheduledToasts::RemoveHelper(_GUID,int)

- ea: `0x180022888`
- end: `0x180022a50`
- name: `?RemoveHelper@ScheduledToasts@@AEAAJU_GUID@@H@Z`
- size: `456`
- prototype: `__int64 __fastcall(ScheduledToasts *__hidden this, struct _GUID *__struct_ptr, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180021d5c`
- `0x18008e000`

## callees

- `0x180022888`
- `0x1800264a4`
- `0x18006a950`
- `0x18008a97c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800228da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800228da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800228a9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800228a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022a26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022a26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022a34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022a34`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180022930`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180022930`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180022962`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180022962`
- `OLEAUT32!__imp_SysFreeString` at `0x180022a15`
- `OLEAUT32!__imp_SysFreeString` at `0x180022a15`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x18002291a`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x18002291a`
- `TimeBrokerClient!TbDeleteEvent` at `0x180022909`
- `TimeBrokerClient!TbDeleteEvent` at `0x180022909`

## string_xrefs

- `0x18002297e`: `RemoveScheduledToastUpdate`

## pseudocode

```c
__int64 __fastcall ScheduledToasts::RemoveHelper(RTL_SRWLOCK *this, struct _GUID *a2, int a3)
{
  ScheduledToasts *v4; // rbx
  int v5; // edi
  ScheduledToasts *i; // r9
  __int64 v9; // rcx
  int v10; // eax
  int v11; // edi
  __int64 v12; // rcx
  ScheduledToasts *v13; // rax
  ScheduledToasts **v14; // rcx
  const unsigned __int16 *v15; // r8
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  OLECHAR *v19; // rcx
  HANDLE ProcessHeap; // rax
  _OWORD v22[3]; // [rsp+40h] [rbp-38h] BYREF
  int v23; // [rsp+80h] [rbp+8h] BYREF
  char *v24; // [rsp+98h] [rbp+20h] BYREF

  v4 = 0;
  v5 = 0;
  AcquireSRWLockExclusive(this + 4);
  for ( i = (ScheduledToasts *)this[2].Ptr; i != (ScheduledToasts *)&this[2]; i = *(ScheduledToasts **)i )
  {
    v4 = i;
    if ( *(_QWORD *)&a2->Data1 == *((_QWORD *)i + 4) && *(_QWORD *)a2->Data4 == *((_QWORD *)i + 5) )
    {
      v13 = *(ScheduledToasts **)i;
      if ( *(ScheduledToasts **)(*(_QWORD *)i + 8LL) != i || (v14 = (ScheduledToasts **)*((_QWORD *)i + 1), *v14 != i) )
        __fastfail(3u);
      *v14 = v13;
      v5 = 1;
      *((_QWORD *)v13 + 1) = v14;
      break;
    }
  }
  ReleaseSRWLockExclusive(this + 4);
  if ( v5 )
  {
    v9 = ((unsigned __int64)v4 + 68) & -(__int64)(*((_DWORD *)v4 + 16) != 0);
    v22[0] = *((_OWORD *)v4 + 2);
    v10 = TbDeleteEvent(v9, v22);
    v11 = 0;
    if ( v10 >= 0 )
      v11 = v10;
    if ( (int)BiPtDeleteEvent((char *)v4 + 48) < 0 )
      v11 = 0;
    v12 = *((_QWORD *)v4 + 3);
    if ( a3 )
      RtlUnsubscribeWnfNotificationWaitForCompletion(v12);
    else
      RtlUnsubscribeWnfStateChangeNotification(v12);
    v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 41);
    *((_QWORD *)v4 + 3) = 0;
    if ( WpnTelemetryAggregator::AddEventCount(
           *((WpnTelemetryAggregator **)this[5].Ptr + 43),
           L"RemoveScheduledToastUpdate",
           v15,
           L"Toast")
      && (unsigned int)dword_18015C038 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_18015C038, 0x400000000000LL) )
    {
      *(_QWORD *)&v22[0] = *((_QWORD *)v4 + 41);
      v24 = (char *)v4 + 32;
      v23 = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
        v16,
        (unsigned int)byte_180138A8B,
        v17,
        v18,
        (__int64)&v23,
        (__int64)v22,
        (__int64)&v24);
    }
    v19 = (OLECHAR *)*((_QWORD *)v4 + 41);
    if ( v19 )
    {
      SysFreeString(v19);
      *((_QWORD *)v4 + 41) = 0;
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  return 0;
}

```

## disassembly

```asm
0x180022888  mov     [rsp+arg_8], rbx
0x18002288d  push    rbp
0x18002288e  push    rsi
0x18002288f  push    rdi
0x180022890  push    r14
0x180022892  push    r15
0x180022894  sub     rsp, 50h
0x180022898  mov     rbp, rcx
0x18002289b  xor     ebx, ebx
0x18002289d  add     rcx, 20h ; ' '; SRWLock
0x1800228a1  xor     edi, edi
0x1800228a3  mov     r15d, r8d
0x1800228a6  mov     rsi, rdx
0x1800228a9  call    cs:__imp_AcquireSRWLockExclusive
0x1800228af  lea     r10, [rbp+10h]
0x1800228b3  mov     r9, [r10]
0x1800228b6  jmp     short loc_1800228D1
0x1800228b8  mov     rax, [rsi]
0x1800228bb  mov     rbx, r9
0x1800228be  cmp     rax, [r9+20h]
0x1800228c2  jnz     short loc_1800228CE
0x1800228c4  mov     rax, [rsi+8]
0x1800228c8  cmp     rax, [r9+28h]
0x1800228cc  jz      short loc_180022938
0x1800228ce  mov     r9, [r9]
0x1800228d1  cmp     r9, r10
0x1800228d4  jnz     short loc_1800228B8
0x1800228d6  lea     rcx, [rbp+20h]; SRWLock
0x1800228da  call    cs:__imp_ReleaseSRWLockExclusive
0x1800228e0  test    edi, edi
0x1800228e2  jz      loc_180022A3A
0x1800228e8  mov     eax, [rbx+40h]
0x1800228eb  lea     rdx, [rbx+44h]
0x1800228ef  neg     eax
0x1800228f1  lea     rsi, [rbx+20h]
0x1800228f5  movups  xmm0, xmmword ptr [rsi]
0x1800228f8  sbb     rcx, rcx
0x1800228fb  and     rcx, rdx
0x1800228fe  lea     rdx, [rsp+78h+var_38]
0x180022903  movdqu  [rsp+78h+var_38], xmm0
0x180022909  call    cs:__imp_TbDeleteEvent
0x18002290f  xor     edi, edi
0x180022911  lea     rcx, [rbx+30h]
0x180022915  test    eax, eax
0x180022917  cmovns  edi, eax
0x18002291a  call    cs:__imp_BiPtDeleteEvent
0x180022920  xor     ecx, ecx
0x180022922  test    eax, eax
0x180022924  cmovs   edi, ecx
0x180022927  mov     rcx, [rbx+18h]
0x18002292b  test    r15d, r15d
0x18002292e  jz      short loc_180022962
0x180022930  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180022936  jmp     short loc_180022968
0x180022938  mov     rax, [r9]
0x18002293b  cmp     [rax+8], r9
0x18002293f  jnz     short loc_18002295B
0x180022941  mov     rcx, [r9+8]
0x180022945  cmp     [rcx], r9
0x180022948  jnz     short loc_18002295B
0x18002294a  mov     [rcx], rax
0x18002294d  mov     edi, 1
0x180022952  mov     [rax+8], rcx
0x180022956  jmp     loc_1800228D6
0x18002295b  mov     ecx, 3
0x180022960  int     29h; Win8: RtlFailFast(ecx)
0x180022962  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x180022968  mov     r8, [rbx+148h]; unsigned __int16 *
0x18002296f  lea     r9, aToast; "Toast"
0x180022976  mov     qword ptr [rbx+18h], 0
0x18002297e  lea     rdx, aRemoveschedule; "RemoveScheduledToastUpdate"
0x180022985  mov     rcx, [rbp+28h]
0x180022989  mov     rcx, [rcx+158h]; this
0x180022990  call    ?AddEventCount@WpnTelemetryAggregator@@QEAA_NPEBG00@Z; WpnTelemetryAggregator::AddEventCount(ushort const *,ushort const *,ushort const *)
0x180022995  test    al, al
0x180022997  jz      short loc_180022A09
0x180022999  mov     eax, cs:dword_18015C038
0x18002299f  cmp     eax, 5
0x1800229a2  jbe     short loc_180022A09
0x1800229a4  mov     rdx, 400000000000h
0x1800229ae  lea     rcx, dword_18015C038
0x1800229b5  call    _tlgKeywordOn
0x1800229ba  test    al, al
0x1800229bc  jz      short loc_180022A09
0x1800229be  mov     rax, [rbx+148h]
0x1800229c5  lea     rdx, byte_180138A8B
0x1800229cc  mov     qword ptr [rsp+78h+var_38], rax
0x1800229d1  lea     rax, [rsp+78h+arg_18]
0x1800229d9  mov     [rsp+78h+var_48], rax
0x1800229de  lea     rax, [rsp+78h+var_38]
0x1800229e3  mov     [rsp+78h+var_50], rax
0x1800229e8  lea     rax, [rsp+78h+arg_0]
0x1800229f0  mov     [rsp+78h+var_58], rax
0x1800229f5  mov     [rsp+78h+arg_18], rsi
0x1800229fd  mov     [rsp+78h+arg_0], edi
0x180022a04  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &)
0x180022a09  mov     rcx, [rbx+148h]; bstrString
0x180022a10  test    rcx, rcx
0x180022a13  jz      short loc_180022A26
0x180022a15  call    cs:__imp_SysFreeString
0x180022a1b  mov     qword ptr [rbx+148h], 0
0x180022a26  call    cs:__imp_GetProcessHeap
0x180022a2c  mov     r8, rbx; lpMem
0x180022a2f  xor     edx, edx; dwFlags
0x180022a31  mov     rcx, rax; hHeap
0x180022a34  call    cs:__imp_HeapFree
0x180022a3a  mov     rbx, [rsp+78h+arg_8]
0x180022a42  xor     eax, eax
0x180022a44  add     rsp, 50h
0x180022a48  pop     r15
0x180022a4a  pop     r14
0x180022a4c  pop     rdi
0x180022a4d  pop     rsi
0x180022a4e  pop     rbp
0x180022a4f  retn
```
