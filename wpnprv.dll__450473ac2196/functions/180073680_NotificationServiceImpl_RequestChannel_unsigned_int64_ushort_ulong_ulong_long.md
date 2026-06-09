# NotificationServiceImpl::RequestChannel(unsigned __int64,ushort *,ulong,ulong,long)

- ea: `0x180073680`
- end: `0x18007392b`
- name: `?RequestChannel@NotificationServiceImpl@@UEAAJ_KPEAGKKJ@Z`
- size: `683`
- prototype: `__int64 __fastcall(WNPMessageGenerator **this, __int64, unsigned __int16 *, unsigned int, unsigned int, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000af1c`
- `0x18000fe0c`
- `0x18001c06c`
- `0x18001c4bc`
- `0x18001cc10`
- `0x1800683f8`
- `0x18006b000`
- `0x180073680`
- `0x180075bac`
- `0x180096010`

## import_xrefs

- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x180073735`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x180073735`

## string_xrefs

- `0x1800736f2`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800737b0`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x180073886`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800738c9`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::RequestChannel(
        WNPMessageGenerator **this,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        int a6)
{
  int v10; // eax
  int v11; // eax
  int v12; // edx
  int v13; // ecx
  int v14; // ebx
  int v15; // eax
  int v16; // eax
  const char *v17; // r9
  void *v18; // rcx
  char *v19; // rcx
  __int64 result; // rax
  int v21; // [rsp+20h] [rbp-B8h]
  int v22; // [rsp+20h] [rbp-B8h]
  unsigned int v23; // [rsp+20h] [rbp-B8h]
  void *v24; // [rsp+78h] [rbp-60h] BYREF
  char *v25; // [rsp+80h] [rbp-58h] BYREF
  unsigned __int64 RandomBuffer; // [rsp+88h] [rbp-50h] BYREF
  void *v27; // [rsp+90h] [rbp-48h] BYREF
  char *v28; // [rsp+98h] [rbp-40h] BYREF
  char v29; // [rsp+A0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  unsigned int v31; // [rsp+F0h] [rbp+18h] BYREF

  try
  {
    if ( !a3 )
      MicrosoftTelemetryAssertTriggeredNoArgs(this);
    v25 = 0;
    v27 = &v25;
    v28 = 0;
    v29 = 1;
    v10 = WpnUtf16ToUtf8(a3, &v28);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5B5,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v10,
        v21);
    wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v27);
    v31 = 0;
    RandomBuffer = 0;
    SystemFunction036(&RandomBuffer, 8u);
    v24 = 0;
    v27 = &v24;
    v28 = 0;
    v29 = 1;
    v11 = WNPMessageGenerator::GenerateChannelRequest(this[16], v25, a4, RandomBuffer, (unsigned __int8 **)&v28, &v31);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5BE,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v11,
        v22);
    wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v27);
    v14 = a6;
    if ( (byte_1800AFD82 & 0x10) != 0 )
      McTemplateU0dssqqbr4sxqbr8x_EventWriteTransfer(v13, v12, a6, 0, (__int64)v25, a4);
    v23 = v31;
    v15 = (*(__int64 (__fastcall **)(WNPMessageGenerator *, __int64, unsigned __int8 near **, const char *))(*(_QWORD *)this[14] + 48LL))(
            this[14],
            a2,
            &WNPMessageGenerator::s_GetCommand,
            "CHANNEL");
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5D3,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v15,
        v23);
    v16 = NotificationServiceImpl::AddOutstandingRequest(this, this + 20, a2, 0);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5D9,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v16,
        v14);
    v18 = v24;
    v24 = 0;
    if ( v18 )
      MemoryFree(v18);
    v19 = v25;
    v25 = 0;
    if ( v19 )
      MemoryFree(v19);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5DC,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x180073680  push    rbx
0x180073682  push    rsi
0x180073683  push    rdi
0x180073684  push    r14
0x180073686  sub     rsp, 0B8h
0x18007368d  mov     r14d, r9d
0x180073690  mov     rbx, r8
0x180073693  mov     rsi, rdx
0x180073696  mov     rdi, rcx
0x180073699  test    rbx, rbx
0x18007369c  jnz     short loc_1800736A3
0x18007369e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800736a3  mov     [rsp+0D8h+var_58], 0
0x1800736af  lea     rax, [rsp+0D8h+var_58]
0x1800736b7  mov     [rsp+0D8h+var_48], rax
0x1800736bf  mov     [rsp+0D8h+var_40], 0
0x1800736cb  mov     [rsp+0D8h+var_38], 1
0x1800736d3  lea     rdx, [rsp+0D8h+var_40]; char **
0x1800736db  mov     rcx, rbx; lpWideCharStr
0x1800736de  call    ?WpnUtf16ToUtf8@@YAJPEBGPEAPEAD@Z; WpnUtf16ToUtf8(ushort const *,char * *)
0x1800736e3  mov     rcx, [rsp+0D8h]; this
0x1800736eb  test    eax, eax
0x1800736ed  jns     short loc_180073704
0x1800736ef  mov     r9d, eax; char *
0x1800736f2  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800736f9  mov     edx, 5B5h; void *
0x1800736fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073704  lea     rcx, [rsp+0D8h+var_48]
0x18007370c  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180073711  mov     [rsp+0D8h+arg_10], 0
0x18007371c  mov     [rsp+0D8h+RandomBuffer], 0
0x180073728  mov     edx, 8; RandomBufferLength
0x18007372d  lea     rcx, [rsp+0D8h+RandomBuffer]; RandomBuffer
0x180073735  call    cs:__imp_SystemFunction036
0x18007373b  mov     rbx, [rsp+0D8h+RandomBuffer]
0x180073743  mov     [rsp+0D8h+var_60], 0
0x18007374c  lea     rax, [rsp+0D8h+var_60]
0x180073751  mov     [rsp+0D8h+var_48], rax
0x180073759  mov     [rsp+0D8h+var_40], 0
0x180073765  mov     [rsp+0D8h+var_38], 1
0x18007376d  lea     rax, [rsp+0D8h+arg_10]
0x180073775  mov     [rsp+0D8h+var_B0], rax; unsigned int *
0x18007377a  lea     rax, [rsp+0D8h+var_40]
0x180073782  mov     [rsp+0D8h+var_B8], rax; int
0x180073787  mov     r9, rbx; unsigned __int64
0x18007378a  mov     r8d, r14d; unsigned int
0x18007378d  mov     rdx, [rsp+0D8h+var_58]; char *
0x180073795  mov     rcx, [rdi+80h]; this
0x18007379c  call    ?GenerateChannelRequest@WNPMessageGenerator@@QEAAJPEBDK_KPEAPEAEPEAK@Z; WNPMessageGenerator::GenerateChannelRequest(char const *,ulong,unsigned __int64,uchar * *,ulong *)
0x1800737a1  mov     rcx, [rsp+0D8h]; this
0x1800737a9  test    eax, eax
0x1800737ab  jns     short loc_1800737C2
0x1800737ad  mov     r9d, eax; char *
0x1800737b0  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800737b7  mov     edx, 5BEh; void *
0x1800737bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800737c2  lea     rcx, [rsp+0D8h+var_48]
0x1800737ca  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x1800737cf  test    cs:byte_1800AFD82, 10h
0x1800737d6  jz      short loc_18007381D
0x1800737d8  mov     [rsp+0D8h+var_78], rsi
0x1800737dd  mov     rax, [rsp+0D8h+var_60]
0x1800737e2  mov     [rsp+0D8h+var_80], rax
0x1800737e7  mov     eax, [rsp+0D8h+arg_10]
0x1800737ee  mov     [rsp+0D8h+var_88], eax
0x1800737f2  mov     [rsp+0D8h+var_90], rbx
0x1800737f7  mov     dword ptr [rsp+0D8h+var_B0], r14d
0x1800737fc  mov     rax, [rsp+0D8h+var_58]
0x180073804  mov     [rsp+0D8h+var_B8], rax
0x180073809  xor     r9d, r9d
0x18007380c  mov     ebx, [rsp+0D8h+arg_28]
0x180073813  mov     r8d, ebx
0x180073816  call    McTemplateU0dssqqbr4sxqbr8x_EventWriteTransfer
0x18007381b  jmp     short loc_180073824
0x18007381d  mov     ebx, [rsp+0D8h+arg_28]
0x180073824  mov     [rsp+0D8h+var_68], 0
0x18007382c  mov     rcx, [rdi+70h]
0x180073830  mov     rdx, [rsp+0D8h+var_60]
0x180073835  mov     r8d, [rsp+0D8h+arg_10]
0x18007383d  mov     rax, [rcx]
0x180073840  lea     r9, [rsp+0D8h+var_68]
0x180073845  mov     [rsp+0D8h+var_A0], r9
0x18007384a  mov     [rsp+0D8h+var_A8], 0
0x180073853  mov     [rsp+0D8h+var_B0], rdx
0x180073858  mov     dword ptr [rsp+0D8h+var_B8], r8d; int
0x18007385d  lea     r9, aChannel; "CHANNEL"
0x180073864  lea     r8, ?s_GetCommand@WNPMessageGenerator@@2PAEA; uchar near * WNPMessageGenerator::s_GetCommand
0x18007386b  mov     rdx, rsi
0x18007386e  mov     rax, [rax+30h]
0x180073872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073877  mov     rcx, [rsp+0D8h]; this
0x18007387f  test    eax, eax
0x180073881  jns     short loc_180073897
0x180073883  mov     r9d, eax; char *
0x180073886  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007388d  mov     edx, 5D3h; void *
0x180073892  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073897  lea     rdx, [rdi+0A0h]
0x18007389e  mov     dword ptr [rsp+0D8h+var_B0], 1
0x1800738a6  mov     dword ptr [rsp+0D8h+var_B8], ebx; int
0x1800738aa  mov     r9d, [rsp+0D8h+var_68]
0x1800738af  mov     r8, rsi
0x1800738b2  mov     rcx, rdi
0x1800738b5  call    ?AddOutstandingRequest@NotificationServiceImpl@@AEAAJPEAU_LIST_ENTRY@@_KKJW4_RequestTypes@@@Z; NotificationServiceImpl::AddOutstandingRequest(_LIST_ENTRY *,unsigned __int64,ulong,long,_RequestTypes)
0x1800738ba  mov     rcx, [rsp+0D8h]; this
0x1800738c2  test    eax, eax
0x1800738c4  jns     short loc_1800738DB
0x1800738c6  mov     r9d, eax; char *
0x1800738c9  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800738d0  mov     edx, 5D9h; void *
0x1800738d5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800738db  mov     rcx, [rsp+0D8h+var_60]; void *
0x1800738e0  mov     [rsp+0D8h+var_60], 0
0x1800738e9  test    rcx, rcx
0x1800738ec  jz      short loc_1800738F4
0x1800738ee  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800738f3  nop
0x1800738f4  mov     rcx, [rsp+0D8h+var_58]; void *
0x1800738fc  mov     [rsp+0D8h+var_58], 0
0x180073908  test    rcx, rcx
0x18007390b  jz      short loc_180073912
0x18007390d  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180073912  xor     eax, eax
0x180073914  jmp     short loc_18007391D
0x180073916  mov     eax, [rsp+0D8h+arg_10]
0x18007391d  add     rsp, 0B8h
0x180073924  pop     r14
0x180073926  pop     rdi
0x180073927  pop     rsi
0x180073928  pop     rbx
0x180073929  retn
```
