# EventJoinFieldElementEnd(_XMRW_OPEN_CONTEXT *)

- ea: `0x1400343e8`
- end: `0x140034515`
- name: `?EventJoinFieldElementEnd@@YAKPEAU_XMRW_OPEN_CONTEXT@@@Z`
- size: `301`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14003290c`

## callees

- `0x140004cac`
- `0x140004f08`
- `0x1400343e8`
- `0x140035b7c`
- `0x14003694c`
- `0x1400400d6`
- `0x140040130`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventJoinFieldElementEnd(struct _XMRW_OPEN_CONTEXT *a1)
{
  __int64 v1; // rbx
  __int64 v3; // rdi
  struct RPT_STRING *v4; // rdx
  unsigned int TdhEventInfo; // esi
  struct _MOF_INFO *MofInfoHead; // rax
  struct _MOF_VERSION *MofVersion; // rax
  _DWORD v9[4]; // [rsp+20h] [rbp-59h] BYREF
  struct _EVENT_RECORD Event; // [rsp+30h] [rbp-49h] BYREF

  v1 = *((_QWORD *)a1 + 13);
  memset_0(&Event, 0, sizeof(Event));
  v9[0] = 0;
  if ( !v1 )
    return 0;
  v3 = *((_QWORD *)a1 + 3);
  v4 = 0;
  if ( (*(_BYTE *)(v1 + 176) & 0x10) == 0 )
    v4 = (struct RPT_STRING *)v1;
  TdhEventInfo = GetTdhEventInfo((struct _TRACERPT_EVENT_FIELD_SOURCE *)(v1 + 40), v4, 0, &Event);
  if ( TdhEventInfo )
  {
    (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v3 + 168LL))(v3, v9);
    if ( TdhEventInfo == -1073222108 )
      PrintMessage(0x475u, v9[0]);
    else
      PrintMessage(0x476u, v9[0]);
    return 0;
  }
  MofInfoHead = GetMofInfoHead(&Event.EventHeader.ProviderId);
  if ( MofInfoHead )
  {
    MofVersion = GetMofVersion(&Event, MofInfoHead, 1u);
    if ( MofVersion )
    {
      *((_BYTE *)MofVersion + 40) = 1;
      *(struct _EVENT_RECORD *)(v1 + 64) = Event;
      return 0;
    }
  }
  return 8;
}

```

## disassembly

```asm
0x1400343e8  push    rbp
0x1400343ea  push    rbx
0x1400343eb  push    rsi
0x1400343ec  push    rdi
0x1400343ed  lea     rbp, [rsp-3Fh]
0x1400343f2  sub     rsp, 0B8h
0x1400343f9  mov     rax, cs:__security_cookie
0x140034400  xor     rax, rsp
0x140034403  mov     [rbp+57h+var_30], rax
0x140034407  mov     rbx, [rcx+68h]
0x14003440b  xor     edx, edx; Val
0x14003440d  mov     rdi, rcx
0x140034410  lea     rcx, [rbp+57h+Event]; void *
0x140034414  lea     r8d, [rdx+70h]; Size
0x140034418  call    memset_0
0x14003441d  mov     [rbp+57h+var_B0], 0
0x140034424  test    rbx, rbx
0x140034427  jz      short loc_14003447E
0x140034429  test    byte ptr [rbx+0B0h], 10h
0x140034430  lea     rcx, [rbx+28h]; struct _TRACERPT_EVENT_FIELD_SOURCE *
0x140034434  mov     rdi, [rdi+18h]
0x140034438  lea     r9, [rbp+57h+Event]; struct _EVENT_RECORD *
0x14003443c  mov     edx, 0
0x140034441  cmovz   rdx, rbx; struct RPT_STRING *
0x140034445  xor     r8d, r8d; struct _EVENT_PROPERTY_INFO *
0x140034448  call    ?GetTdhEventInfo@@YAKPEAU_TRACERPT_EVENT_FIELD_SOURCE@@PEAVRPT_STRING@@PEAU_EVENT_PROPERTY_INFO@@PEAU_EVENT_RECORD@@@Z; GetTdhEventInfo(_TRACERPT_EVENT_FIELD_SOURCE *,RPT_STRING *,_EVENT_PROPERTY_INFO *,_EVENT_RECORD *)
0x14003444d  mov     esi, eax
0x14003444f  test    eax, eax
0x140034451  jz      short loc_14003449F
0x140034453  mov     rdx, [rdi]
0x140034456  mov     rcx, rdi
0x140034459  mov     rax, [rdx+0A8h]
0x140034460  lea     rdx, [rbp+57h+var_B0]
0x140034464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034469  mov     edx, [rbp+57h+var_B0]
0x14003446c  cmp     esi, 0C007EE24h
0x140034472  jnz     short loc_140034498
0x140034474  mov     ecx, 475h; unsigned int
0x140034479  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003447e  xor     eax, eax
0x140034480  mov     rcx, [rbp+57h+var_30]
0x140034484  xor     rcx, rsp; StackCookie
0x140034487  call    __security_check_cookie
0x14003448c  add     rsp, 0B8h
0x140034493  pop     rdi
0x140034494  pop     rsi
0x140034495  pop     rbx
0x140034496  pop     rbp
0x140034497  retn
0x140034498  mov     ecx, 476h
0x14003449d  jmp     short loc_140034479
0x14003449f  lea     rcx, [rbp+57h+Event.EventHeader.ProviderId]; struct _GUID *
0x1400344a3  call    ?GetMofInfoHead@@YAPEAU_MOF_INFO@@PEBU_GUID@@@Z; GetMofInfoHead(_GUID const *)
0x1400344a8  test    rax, rax
0x1400344ab  jz      short loc_14003450B
0x1400344ad  mov     r8b, 1; unsigned __int8
0x1400344b0  lea     rcx, [rbp+57h+Event]; Event
0x1400344b4  mov     rdx, rax; struct _MOF_INFO *
0x1400344b7  call    ?GetMofVersion@@YAPEAU_MOF_VERSION@@PEAU_EVENT_RECORD@@PEAU_MOF_INFO@@E@Z; GetMofVersion(_EVENT_RECORD *,_MOF_INFO *,uchar)
0x1400344bc  test    rax, rax
0x1400344bf  jz      short loc_14003450B
0x1400344c1  mov     byte ptr [rax+28h], 1
0x1400344c5  movaps  xmm0, xmmword ptr [rbp+57h+Event.EventHeader.Size]
0x1400344c9  movups  xmmword ptr [rbx+40h], xmm0
0x1400344cd  movaps  xmm1, xmmword ptr [rbp-39h]
0x1400344d1  movups  xmmword ptr [rbx+50h], xmm1
0x1400344d5  movaps  xmm0, xmmword ptr [rbp+57h+Event.EventHeader.ProviderId.Data4]
0x1400344d9  movups  xmmword ptr [rbx+60h], xmm0
0x1400344dd  movaps  xmm1, xmmword ptr [rbp+57h+Event.EventHeader.EventDescriptor.Keyword]
0x1400344e1  movups  xmmword ptr [rbx+70h], xmm1
0x1400344e5  movaps  xmm0, xmmword ptr [rbp+57h+Event.EventHeader.ActivityId.Data1]
0x1400344e9  movups  xmmword ptr [rbx+80h], xmm0
0x1400344f0  movaps  xmm1, xmmword ptr [rbp+57h+Event.BufferContext]
0x1400344f4  movups  xmmword ptr [rbx+90h], xmm1
0x1400344fb  movaps  xmm0, xmmword ptr [rbp+57h+Event.UserData]
0x1400344ff  movups  xmmword ptr [rbx+0A0h], xmm0
0x140034506  jmp     loc_14003447E
0x14003450b  mov     eax, 8
0x140034510  jmp     loc_140034480
```
