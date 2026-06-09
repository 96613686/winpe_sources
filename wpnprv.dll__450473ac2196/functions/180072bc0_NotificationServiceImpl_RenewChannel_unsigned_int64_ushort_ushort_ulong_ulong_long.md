# NotificationServiceImpl::RenewChannel(unsigned __int64,ushort *,ushort *,ulong,ulong,long)

- ea: `0x180072bc0`
- end: `0x180072ef8`
- name: `?RenewChannel@NotificationServiceImpl@@UEAAJ_KPEAG1KKJ@Z`
- size: `824`
- prototype: `__int64 __fastcall(WNPMessageGenerator **this, __int64, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000af1c`
- `0x18000fe0c`
- `0x18001c06c`
- `0x18001c4bc`
- `0x18001cc10`
- `0x180068228`
- `0x18006b000`
- `0x180072bc0`
- `0x180075bac`
- `0x180096010`

## import_xrefs

- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x180072cdd`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x180072cdd`

## string_xrefs

- `0x180072c3b`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x180072ca1`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x180072d61`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x180072e34`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x180072e77`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::RenewChannel(
        WNPMessageGenerator **this,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        int a7)
{
  int v11; // eax
  int v12; // eax
  char v13; // di
  int v14; // eax
  int v15; // edx
  int v16; // ecx
  int v17; // ebx
  int v18; // eax
  int v19; // eax
  const char *v20; // r9
  void *v21; // rcx
  char *v22; // rcx
  char *v23; // rcx
  __int64 result; // rax
  int v25; // [rsp+20h] [rbp-A8h]
  int v26; // [rsp+20h] [rbp-A8h]
  unsigned int v27; // [rsp+20h] [rbp-A8h]
  void *v28; // [rsp+78h] [rbp-50h] BYREF
  char *v29; // [rsp+80h] [rbp-48h] BYREF
  char *v30; // [rsp+88h] [rbp-40h] BYREF
  unsigned __int64 RandomBuffer; // [rsp+90h] [rbp-38h] BYREF
  void *v32; // [rsp+98h] [rbp-30h] BYREF
  char *v33; // [rsp+A0h] [rbp-28h] BYREF
  char v34; // [rsp+A8h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  unsigned int v36; // [rsp+E0h] [rbp+18h] BYREF

  try
  {
    if ( !a3 || !a4 )
      MicrosoftTelemetryAssertTriggeredNoArgs(this);
    v30 = 0;
    v32 = &v30;
    v33 = 0;
    v34 = 1;
    v11 = WpnUtf16ToUtf8(a4, &v33);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5EC,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v11,
        v25);
    wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v32);
    v29 = 0;
    v32 = &v29;
    v33 = 0;
    v34 = 1;
    v12 = WpnUtf16ToUtf8(a3, &v33);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5EF,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v12,
        v25);
    wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v32);
    v36 = 0;
    RandomBuffer = 0;
    SystemFunction036(&RandomBuffer, 8u);
    v28 = 0;
    v32 = &v28;
    v33 = 0;
    v34 = 1;
    v13 = a5;
    v14 = WNPMessageGenerator::GenerateChannelRenewal(
            this[16],
            v29,
            v30,
            a5,
            RandomBuffer,
            (unsigned __int8 **)&v33,
            &v36);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5F4,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v14,
        v26);
    wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v32);
    v17 = a7;
    if ( (byte_1800AFD82 & 0x10) != 0 )
      McTemplateU0dssqqbr4sxqbr8x_EventWriteTransfer(v16, v15, a7, (_DWORD)v29, (__int64)v30, v13);
    v27 = v36;
    v18 = (*(__int64 (__fastcall **)(WNPMessageGenerator *, __int64, unsigned __int8 near **, const char *))(*(_QWORD *)this[14] + 48LL))(
            this[14],
            a2,
            &WNPMessageGenerator::s_GetCommand,
            "CHANNEL");
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x609,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v18,
        v27);
    v19 = NotificationServiceImpl::AddOutstandingRequest(this, this + 20, a2, 0);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x60F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v19,
        v17);
    v21 = v28;
    v28 = 0;
    if ( v21 )
      MemoryFree(v21);
    v22 = v29;
    v29 = 0;
    if ( v22 )
      MemoryFree(v22);
    v23 = v30;
    v30 = 0;
    if ( v23 )
      MemoryFree(v23);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x612,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x180072bc0  mov     [rsp+arg_0], rbx
0x180072bc5  mov     [rsp+arg_8], rsi
0x180072bca  push    rdi
0x180072bcb  push    r14
0x180072bcd  push    r15
0x180072bcf  sub     rsp, 0B0h
0x180072bd6  mov     rbx, r9
0x180072bd9  mov     rdi, r8
0x180072bdc  mov     r14, rdx
0x180072bdf  mov     rsi, rcx
0x180072be2  xor     r15d, r15d
0x180072be5  test    r8, r8
0x180072be8  jz      short loc_180072BEF
0x180072bea  test    rbx, rbx
0x180072bed  jnz     short loc_180072BF4
0x180072bef  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180072bf4  mov     [rsp+0C8h+var_40], r15
0x180072bfc  lea     rax, [rsp+0C8h+var_40]
0x180072c04  mov     [rsp+0C8h+var_30], rax
0x180072c0c  mov     [rsp+0C8h+var_28], r15
0x180072c14  mov     [rsp+0C8h+var_20], 1
0x180072c1c  lea     rdx, [rsp+0C8h+var_28]; char **
0x180072c24  mov     rcx, rbx; lpWideCharStr
0x180072c27  call    ?WpnUtf16ToUtf8@@YAJPEBGPEAPEAD@Z; WpnUtf16ToUtf8(ushort const *,char * *)
0x180072c2c  mov     rcx, [rsp+0C8h]; this
0x180072c34  test    eax, eax
0x180072c36  jns     short loc_180072C4D
0x180072c38  mov     r9d, eax; char *
0x180072c3b  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180072c42  mov     edx, 5ECh; void *
0x180072c47  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072c4d  lea     rcx, [rsp+0C8h+var_30]
0x180072c55  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180072c5a  mov     [rsp+0C8h+var_48], r15
0x180072c62  lea     rax, [rsp+0C8h+var_48]
0x180072c6a  mov     [rsp+0C8h+var_30], rax
0x180072c72  mov     [rsp+0C8h+var_28], r15
0x180072c7a  mov     [rsp+0C8h+var_20], 1
0x180072c82  lea     rdx, [rsp+0C8h+var_28]; char **
0x180072c8a  mov     rcx, rdi; lpWideCharStr
0x180072c8d  call    ?WpnUtf16ToUtf8@@YAJPEBGPEAPEAD@Z; WpnUtf16ToUtf8(ushort const *,char * *)
0x180072c92  mov     rcx, [rsp+0C8h]; this
0x180072c9a  test    eax, eax
0x180072c9c  jns     short loc_180072CB3
0x180072c9e  mov     r9d, eax; char *
0x180072ca1  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180072ca8  mov     edx, 5EFh; void *
0x180072cad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072cb3  lea     rcx, [rsp+0C8h+var_30]
0x180072cbb  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180072cc0  mov     [rsp+0C8h+arg_10], r15d
0x180072cc8  mov     [rsp+0C8h+RandomBuffer], r15
0x180072cd0  mov     edx, 8; RandomBufferLength
0x180072cd5  lea     rcx, [rsp+0C8h+RandomBuffer]; RandomBuffer
0x180072cdd  call    cs:__imp_SystemFunction036
0x180072ce3  mov     rbx, [rsp+0C8h+RandomBuffer]
0x180072ceb  mov     [rsp+0C8h+var_50], r15
0x180072cf0  lea     rax, [rsp+0C8h+var_50]
0x180072cf5  mov     [rsp+0C8h+var_30], rax
0x180072cfd  mov     [rsp+0C8h+var_28], r15
0x180072d05  mov     [rsp+0C8h+var_20], 1
0x180072d0d  lea     rax, [rsp+0C8h+arg_10]
0x180072d15  mov     [rsp+0C8h+var_98], rax; unsigned int *
0x180072d1a  lea     rax, [rsp+0C8h+var_28]
0x180072d22  mov     [rsp+0C8h+var_A0], rax; unsigned __int8 **
0x180072d27  mov     [rsp+0C8h+var_A8], rbx; int
0x180072d2c  mov     edi, [rsp+0C8h+arg_20]
0x180072d33  mov     r9d, edi; unsigned int
0x180072d36  mov     r8, [rsp+0C8h+var_40]; char *
0x180072d3e  mov     rdx, [rsp+0C8h+var_48]; char *
0x180072d46  mov     rcx, [rsi+80h]; this
0x180072d4d  call    ?GenerateChannelRenewal@WNPMessageGenerator@@QEAAJPEBD0K_KPEAPEAEPEAK@Z; WNPMessageGenerator::GenerateChannelRenewal(char const *,char const *,ulong,unsigned __int64,uchar * *,ulong *)
0x180072d52  mov     rcx, [rsp+0C8h]; this
0x180072d5a  test    eax, eax
0x180072d5c  jns     short loc_180072D73
0x180072d5e  mov     r9d, eax; char *
0x180072d61  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180072d68  mov     edx, 5F4h; void *
0x180072d6d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072d73  lea     rcx, [rsp+0C8h+var_30]
0x180072d7b  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180072d80  test    cs:byte_1800AFD82, 10h
0x180072d87  jz      short loc_180072DD2
0x180072d89  mov     [rsp+0C8h+var_68], r14
0x180072d8e  mov     rax, [rsp+0C8h+var_50]
0x180072d93  mov     [rsp+0C8h+var_70], rax
0x180072d98  mov     eax, [rsp+0C8h+arg_10]
0x180072d9f  mov     [rsp+0C8h+var_78], eax
0x180072da3  mov     [rsp+0C8h+var_80], rbx
0x180072da8  mov     dword ptr [rsp+0C8h+var_A0], edi
0x180072dac  mov     rax, [rsp+0C8h+var_40]
0x180072db4  mov     [rsp+0C8h+var_A8], rax
0x180072db9  mov     r9, [rsp+0C8h+var_48]
0x180072dc1  mov     ebx, [rsp+0C8h+arg_30]
0x180072dc8  mov     r8d, ebx
0x180072dcb  call    McTemplateU0dssqqbr4sxqbr8x_EventWriteTransfer
0x180072dd0  jmp     short loc_180072DD9
0x180072dd2  mov     ebx, [rsp+0C8h+arg_30]
0x180072dd9  mov     [rsp+0C8h+var_58], r15d
0x180072dde  mov     rcx, [rsi+70h]
0x180072de2  mov     rdx, [rsp+0C8h+var_50]
0x180072de7  mov     r8d, [rsp+0C8h+arg_10]
0x180072def  mov     rax, [rcx]
0x180072df2  lea     r9, [rsp+0C8h+var_58]
0x180072df7  mov     [rsp+0C8h+var_90], r9
0x180072dfc  mov     [rsp+0C8h+var_98], r15
0x180072e01  mov     [rsp+0C8h+var_A0], rdx
0x180072e06  mov     dword ptr [rsp+0C8h+var_A8], r8d; int
0x180072e0b  lea     r9, aChannel; "CHANNEL"
0x180072e12  lea     r8, ?s_GetCommand@WNPMessageGenerator@@2PAEA; uchar near * WNPMessageGenerator::s_GetCommand
0x180072e19  mov     rdx, r14
0x180072e1c  mov     rax, [rax+30h]
0x180072e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072e25  mov     rcx, [rsp+0C8h]; this
0x180072e2d  test    eax, eax
0x180072e2f  jns     short loc_180072E45
0x180072e31  mov     r9d, eax; char *
0x180072e34  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180072e3b  mov     edx, 609h; void *
0x180072e40  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072e45  lea     rdx, [rsi+0A0h]
0x180072e4c  mov     dword ptr [rsp+0C8h+var_A0], 2
0x180072e54  mov     dword ptr [rsp+0C8h+var_A8], ebx; int
0x180072e58  mov     r9d, [rsp+0C8h+var_58]
0x180072e5d  mov     r8, r14
0x180072e60  mov     rcx, rsi
0x180072e63  call    ?AddOutstandingRequest@NotificationServiceImpl@@AEAAJPEAU_LIST_ENTRY@@_KKJW4_RequestTypes@@@Z; NotificationServiceImpl::AddOutstandingRequest(_LIST_ENTRY *,unsigned __int64,ulong,long,_RequestTypes)
0x180072e68  mov     rcx, [rsp+0C8h]; this
0x180072e70  test    eax, eax
0x180072e72  jns     short loc_180072E89
0x180072e74  mov     r9d, eax; char *
0x180072e77  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180072e7e  mov     edx, 60Fh; void *
0x180072e83  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072e89  mov     rcx, [rsp+0C8h+var_50]; void *
0x180072e8e  mov     [rsp+0C8h+var_50], r15
0x180072e93  test    rcx, rcx
0x180072e96  jz      short loc_180072E9E
0x180072e98  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180072e9d  nop
0x180072e9e  mov     rcx, [rsp+0C8h+var_48]; void *
0x180072ea6  mov     [rsp+0C8h+var_48], r15
0x180072eae  test    rcx, rcx
0x180072eb1  jz      short loc_180072EB9
0x180072eb3  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180072eb8  nop
0x180072eb9  mov     rcx, [rsp+0C8h+var_40]; void *
0x180072ec1  mov     [rsp+0C8h+var_40], r15
0x180072ec9  test    rcx, rcx
0x180072ecc  jz      short loc_180072ED3
0x180072ece  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180072ed3  xor     eax, eax
0x180072ed5  jmp     short loc_180072EDE
0x180072ed7  mov     eax, [rsp+0C8h+arg_10]
0x180072ede  lea     r11, [rsp+0C8h+var_18]
0x180072ee6  mov     rbx, [r11+20h]
0x180072eea  mov     rsi, [r11+28h]
0x180072eee  mov     rsp, r11
0x180072ef1  pop     r15
0x180072ef3  pop     r14
0x180072ef5  pop     rdi
0x180072ef6  retn
```
