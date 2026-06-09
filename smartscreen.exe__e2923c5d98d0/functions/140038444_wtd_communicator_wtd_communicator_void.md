# wtd_communicator::~wtd_communicator(void)

- ea: `0x140038444`
- end: `0x1400384d1`
- name: `??1wtd_communicator@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wtd_communicator *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140011040`

## callees

- `0x140001448`
- `0x1400014c4`
- `0x140038444`
- `0x14004c318`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x14003845b`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x14003845b`
- `WTDSENSOR!WtdsUnregisterSensor` at `0x1400384bd`
- `WTDSENSOR!WtdsUnregisterSensor` at `0x1400384bd`

## pseudocode

```c
void __fastcall wtd_communicator::~wtd_communicator(wtd_communicator *this)
{
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  int v5; // ecx
  int v6; // r9d
  __int64 v7; // rcx
  int v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  if ( !*(_QWORD *)this )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v2 = RtlUnsubscribeWnfNotificationWaitForCompletion(*(_QWORD *)this);
  v4 = (unsigned int)v2;
  if ( v2 < 0
    && (unsigned int)dword_140084088 > 2
    && (unsigned __int8)tlgKeywordOn((unsigned int)dword_140084088, 0x400000000000LL, (unsigned int)v2) )
  {
    v9 = 0x1000000;
    v8 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v5,
      (unsigned int)&byte_140076FDF,
      v4,
      v6,
      (__int64)&v8,
      (__int64)&v9);
  }
  v7 = *((_QWORD *)this + 1);
  if ( v7 )
  {
    WtdsUnregisterSensor(v7, v3, v4);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x140038444  push    rbx
0x140038446  sub     rsp, 30h
0x14003844a  mov     rbx, rcx
0x14003844d  cmp     qword ptr [rcx], 0
0x140038451  jnz     short loc_140038458
0x140038453  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140038458  mov     rcx, [rbx]
0x14003845b  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x140038461  mov     r8d, eax
0x140038464  test    eax, eax
0x140038466  jns     short loc_1400384B4
0x140038468  mov     ecx, cs:dword_140084088
0x14003846e  cmp     ecx, 2
0x140038471  jbe     short loc_1400384B4
0x140038473  mov     rdx, 400000000000h
0x14003847d  call    _tlgKeywordOn
0x140038482  test    al, al
0x140038484  jz      short loc_1400384B4
0x140038486  mov     [rsp+38h+arg_8], 1000000h
0x14003848f  mov     [rsp+38h+arg_0], r8d
0x140038494  lea     rax, [rsp+38h+arg_8]
0x140038499  mov     [rsp+38h+var_10], rax
0x14003849e  lea     rax, [rsp+38h+arg_0]
0x1400384a3  mov     [rsp+38h+var_18], rax
0x1400384a8  lea     rdx, byte_140076FDF
0x1400384af  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400384b4  mov     rcx, [rbx+8]
0x1400384b8  test    rcx, rcx
0x1400384bb  jz      short loc_1400384CB
0x1400384bd  call    cs:__imp_WtdsUnregisterSensor
0x1400384c3  mov     qword ptr [rbx+8], 0
0x1400384cb  add     rsp, 30h
0x1400384cf  pop     rbx
0x1400384d0  retn
```
