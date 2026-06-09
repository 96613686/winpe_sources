# wtd_communicator::~wtd_communicator(void)

- ea: `0x1400399cc`
- end: `0x140039a66`
- name: `??1wtd_communicator@@QEAA@XZ`
- size: `154`
- prototype: `void __fastcall(wtd_communicator *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001193c`

## callees

- `0x140001454`
- `0x1400014d0`
- `0x1400399cc`
- `0x14004dc5c`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400399e3`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400399e3`
- `WTDSENSOR!WtdsUnregisterSensor` at `0x140039a4b`
- `WTDSENSOR!WtdsUnregisterSensor` at `0x140039a4b`

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
    && (unsigned int)dword_140086088 > 2
    && (unsigned __int8)tlgKeywordOn((unsigned int)dword_140086088, 0x400000000000LL) )
  {
    v9 = 0x1000000;
    v8 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v5,
      (unsigned int)&byte_140078FD7,
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
0x1400399cc  push    rbx
0x1400399ce  sub     rsp, 30h
0x1400399d2  mov     rbx, rcx
0x1400399d5  cmp     qword ptr [rcx], 0
0x1400399d9  jnz     short loc_1400399E0
0x1400399db  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1400399e0  mov     rcx, [rbx]
0x1400399e3  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1400399ea  nop     dword ptr [rax+rax+00h]
0x1400399ef  mov     r8d, eax
0x1400399f2  test    eax, eax
0x1400399f4  jns     short loc_140039A42
0x1400399f6  mov     ecx, cs:dword_140086088
0x1400399fc  cmp     ecx, 2
0x1400399ff  jbe     short loc_140039A42
0x140039a01  mov     rdx, 400000000000h
0x140039a0b  call    _tlgKeywordOn
0x140039a10  test    al, al
0x140039a12  jz      short loc_140039A42
0x140039a14  mov     [rsp+38h+arg_8], 1000000h
0x140039a1d  mov     [rsp+38h+arg_0], r8d
0x140039a22  lea     rax, [rsp+38h+arg_8]
0x140039a27  mov     [rsp+38h+var_10], rax
0x140039a2c  lea     rax, [rsp+38h+arg_0]
0x140039a31  mov     [rsp+38h+var_18], rax
0x140039a36  lea     rdx, byte_140078FD7
0x140039a3d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140039a42  mov     rcx, [rbx+8]
0x140039a46  test    rcx, rcx
0x140039a49  jz      short loc_140039A5F
0x140039a4b  call    cs:__imp_WtdsUnregisterSensor
0x140039a52  nop     dword ptr [rax+rax+00h]
0x140039a57  mov     qword ptr [rbx+8], 0
0x140039a5f  add     rsp, 30h
0x140039a63  pop     rbx
0x140039a64  retn
```
