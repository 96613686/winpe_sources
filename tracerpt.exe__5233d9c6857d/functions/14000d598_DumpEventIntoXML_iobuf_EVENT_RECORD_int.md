# DumpEventIntoXML(_iobuf *,_EVENT_RECORD *,int)

- ea: `0x14000d598`
- end: `0x14000d731`
- name: `?DumpEventIntoXML@@YAKPEAU_iobuf@@PEAU_EVENT_RECORD@@H@Z`
- size: `409`
- prototype: `unsigned int __fastcall(struct _iobuf *, PEVENT_RECORD Event, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x140011a0c`

## callees

- `0x14000d598`
- `0x14000d7b4`
- `0x14000d848`
- `0x14000e254`
- `0x14000f0bc`
- `0x14000faa4`
- `0x140040130`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x14000d679`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x14000d679`

## pseudocode

```c
__int64 __fastcall DumpEventIntoXML(struct _iobuf *a1, PEVENT_RECORD Event, unsigned int a3)
{
  unsigned int v6; // ebx
  EventXmlDump *v8; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v9; // [rsp+28h] [rbp-D8h]
  _QWORD *v10; // [rsp+50h] [rbp-B0h]
  void ***v11; // [rsp+158h] [rbp+58h]
  void ***v12; // [rsp+160h] [rbp+60h]
  _QWORD v13[52]; // [rsp+180h] [rbp+80h] BYREF
  int v14; // [rsp+320h] [rbp+220h]
  __int64 v15; // [rsp+328h] [rbp+228h]
  __int64 v16; // [rsp+330h] [rbp+230h]
  __int64 v17; // [rsp+438h] [rbp+338h]
  __int64 v18; // [rsp+440h] [rbp+340h]
  __int64 v19; // [rsp+548h] [rbp+448h]
  __int128 v20; // [rsp+550h] [rbp+450h]
  __int128 v21; // [rsp+560h] [rbp+460h]
  __int128 v22; // [rsp+570h] [rbp+470h]
  int v23; // [rsp+580h] [rbp+480h]
  __int64 v24; // [rsp+588h] [rbp+488h]
  __int128 v25; // [rsp+590h] [rbp+490h]
  int v26; // [rsp+5A0h] [rbp+4A0h]
  __int64 v27; // [rsp+5A8h] [rbp+4A8h]
  _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+5B0h] [rbp+4B0h] BYREF

  EventDumpWorkspace::EventDumpWorkspace((EventDumpWorkspace *)&v8);
  v13[0] = &EventXmlDump::`vftable'{for `IEventDumpHeaderHandler'};
  v13[2] = 0;
  v13[1] = &EventXmlDump::`vftable'{for `IEventDumpPropertyHandler'};
  v13[35] = 0;
  v14 = 0;
  v16 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v27 = 0;
  v25 = 0;
  v26 = 0;
  v15 = 0;
  v17 = 0;
  GetTimeZoneInformation(&TimeZoneInformation);
  v11 = off_140060000;
  v12 = off_140060008;
  v10 = v13;
  EventDumpWorkspace::Process((EventDumpWorkspace *)&v8, Event, a3);
  v6 = EventXmlDump::Dump((EventXmlDump *)v13, a1, &v8, a3);
  if ( v9 && *(_DWORD *)(v9 + 48) != 2 && !a3 && (v6 == 111 || v6 == 15005) )
    byte_140083438 = 1;
  EventXmlDump::~EventXmlDump((EventXmlDump *)v13);
  EventDumpWorkspace::~EventDumpWorkspace((EventDumpWorkspace *)&v8);
  return v6;
}

```

## disassembly

```asm
0x14000d598  mov     [rsp-8+arg_10], rbx
0x14000d59d  mov     [rsp-8+arg_18], rsi
0x14000d5a2  push    rbp
0x14000d5a3  push    rdi
0x14000d5a4  push    r14
0x14000d5a6  lea     rbp, [rsp-570h]
0x14000d5ae  sub     rsp, 670h
0x14000d5b5  mov     rax, cs:__security_cookie
0x14000d5bc  xor     rax, rsp
0x14000d5bf  mov     [rbp+580h+var_20], rax
0x14000d5c6  mov     rdi, rcx
0x14000d5c9  mov     esi, r8d
0x14000d5cc  lea     rcx, [rsp+680h+var_660]; this
0x14000d5d1  mov     rbx, rdx
0x14000d5d4  call    ??0EventDumpWorkspace@@QEAA@XZ; EventDumpWorkspace::EventDumpWorkspace(void)
0x14000d5d9  xor     r14d, r14d
0x14000d5dc  lea     rcx, ??_7EventXmlDump@@6BIEventDumpHeaderHandler@@@; const EventXmlDump::`vftable'{for `IEventDumpHeaderHandler'}
0x14000d5e3  xorps   xmm0, xmm0
0x14000d5e6  mov     [rbp+580h+var_500], rcx
0x14000d5ed  lea     rax, ??_7EventXmlDump@@6BIEventDumpPropertyHandler@@@; const EventXmlDump::`vftable'{for `IEventDumpPropertyHandler'}
0x14000d5f4  mov     [rbp+580h+var_4F0], r14
0x14000d5fb  xorps   xmm1, xmm1
0x14000d5fe  mov     [rbp+580h+var_4F8], rax
0x14000d605  lea     rcx, [rbp+580h+TimeZoneInformation]; lpTimeZoneInformation
0x14000d60c  mov     [rbp+580h+var_3E8], r14
0x14000d613  mov     [rbp+580h+var_360], r14d
0x14000d61a  mov     [rbp+580h+var_350], r14
0x14000d621  mov     [rbp+580h+var_240], r14
0x14000d628  mov     [rbp+580h+var_138], r14
0x14000d62f  movdqa  [rbp+580h+var_130], xmm0
0x14000d637  movdqa  [rbp+580h+var_120], xmm1
0x14000d63f  movdqa  [rbp+580h+var_110], xmm0
0x14000d647  mov     [rbp+580h+var_100], r14d
0x14000d64e  mov     [rbp+580h+var_F8], r14
0x14000d655  mov     [rbp+580h+var_D8], r14
0x14000d65c  movdqa  [rbp+580h+var_F0], xmm0
0x14000d664  mov     [rbp+580h+var_E0], r14d
0x14000d66b  mov     [rbp+580h+var_358], r14
0x14000d672  mov     [rbp+580h+var_248], r14
0x14000d679  call    cs:__imp_GetTimeZoneInformation
0x14000d67f  lea     rax, off_140060000
0x14000d686  mov     r8d, esi; unsigned int
0x14000d689  mov     [rbp+580h+var_528], rax
0x14000d68d  lea     rcx, [rsp+680h+var_660]; this
0x14000d692  lea     rax, off_140060008
0x14000d699  mov     rdx, rbx; Event
0x14000d69c  mov     [rbp+580h+var_520], rax
0x14000d6a0  lea     rax, [rbp+580h+var_500]
0x14000d6a7  mov     [rsp+680h+var_630], rax
0x14000d6ac  call    ?Process@EventDumpWorkspace@@QEAAKPEAU_EVENT_RECORD@@K@Z; EventDumpWorkspace::Process(_EVENT_RECORD *,ulong)
0x14000d6b1  mov     r9d, esi; int
0x14000d6b4  lea     r8, [rsp+680h+var_660]; struct EventDumpWorkspace *
0x14000d6b9  mov     rdx, rdi; struct _iobuf *
0x14000d6bc  lea     rcx, [rbp+580h+var_500]; this
0x14000d6c3  call    ?Dump@EventXmlDump@@QEAAKPEAU_iobuf@@PEAVEventDumpWorkspace@@H@Z; EventXmlDump::Dump(_iobuf *,EventDumpWorkspace *,int)
0x14000d6c8  mov     ebx, eax
0x14000d6ca  mov     rax, [rsp+680h+var_658]
0x14000d6cf  test    rax, rax
0x14000d6d2  jz      short loc_14000D6F2
0x14000d6d4  cmp     dword ptr [rax+30h], 2
0x14000d6d8  jz      short loc_14000D6F2
0x14000d6da  test    esi, esi
0x14000d6dc  jnz     short loc_14000D6F2
0x14000d6de  cmp     ebx, 6Fh ; 'o'
0x14000d6e1  jz      short loc_14000D6EB
0x14000d6e3  cmp     ebx, 3A9Dh
0x14000d6e9  jnz     short loc_14000D6F2
0x14000d6eb  mov     cs:byte_140083438, 1
0x14000d6f2  lea     rcx, [rbp+580h+var_500]; this
0x14000d6f9  call    ??1EventXmlDump@@QEAA@XZ; EventXmlDump::~EventXmlDump(void)
0x14000d6fe  lea     rcx, [rsp+680h+var_660]; this
0x14000d703  call    ??1EventDumpWorkspace@@QEAA@XZ; EventDumpWorkspace::~EventDumpWorkspace(void)
0x14000d708  mov     eax, ebx
0x14000d70a  mov     rcx, [rbp+580h+var_20]
0x14000d711  xor     rcx, rsp; StackCookie
0x14000d714  call    __security_check_cookie
0x14000d719  lea     r11, [rsp+680h+var_10]
0x14000d721  mov     rbx, [r11+30h]
0x14000d725  mov     rsi, [r11+38h]
0x14000d729  mov     rsp, r11
0x14000d72c  pop     r14
0x14000d72e  pop     rdi
0x14000d72f  pop     rbp
0x14000d730  retn
```
