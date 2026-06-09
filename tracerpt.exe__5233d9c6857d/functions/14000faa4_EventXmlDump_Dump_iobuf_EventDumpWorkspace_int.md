# EventXmlDump::Dump(_iobuf *,EventDumpWorkspace *,int)

- ea: `0x14000faa4`
- end: `0x14000fd7f`
- name: `?Dump@EventXmlDump@@QEAAKPEAU_iobuf@@PEAVEventDumpWorkspace@@H@Z`
- size: `731`
- prototype: `unsigned int __fastcall(EventXmlDump *__hidden this, struct _iobuf *, struct EventDumpWorkspace *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000d598`

## callees

- `0x14000faa4`
- `0x14000fd88`
- `0x14000ffcc`
- `0x1400104f0`
- `0x140010594`
- `0x140010a88`
- `0x1400120f4`
- `0x140013564`
- `0x140013a04`
- `0x14001601c`
- `0x1400161b0`
- `0x140016360`
- `0x1400166d4`
- `0x140032488`
- `0x140040130`

## string_xrefs

- `0x14000fc7e`: `xmlns="http://schemas.microsoft.com/win/2004/08/events/trace"`
- `0x14000fad6`: `xmlns="http://schemas.microsoft.com/win/2004/08/events/event"`

## pseudocode

```c
__int64 __fastcall EventXmlDump::Dump(EventXmlDump *this, struct _iobuf *a2, EventXmlDump **a3, int a4)
{
  EventXmlDump *v8; // rcx
  int v9; // eax
  int file; // ebp
  int flag; // r14d
  unsigned int v12; // esi
  _DWORD *v13; // rsi
  unsigned int v14; // r9d
  int v15; // r14d
  int v16; // r15d
  unsigned int v17; // ebp
  EventXmlDump *v18; // rbp
  unsigned __int8 *v19; // r8
  unsigned __int16 *v20; // rax
  _DWORD *v21; // r8
  unsigned __int16 v23[128]; // [rsp+20h] [rbp-148h] BYREF

  TracerptFPrintf(a2, "<Event %ws>\r\n", L"xmlns=\"http://schemas.microsoft.com/win/2004/08/events/event\"");
  EventXmlDump::DumpHeader(this, a2, (struct EventDumpWorkspace *)a3);
  v8 = a3[1];
  v9 = 0;
  if ( v8 )
  {
    LOBYTE(v9) = *((_DWORD *)v8 + 27) == 2;
    if ( *((_DWORD *)v8 + 12) == 2 )
    {
      file = a2[1365]._file;
      flag = a2[1365]._flag;
      v12 = PrintWPPEventXmlDump(a2, (PEVENT_RECORD)*a3);
      if ( v12 && !TracerptFseek(a2, flag + file) )
        EventXmlDump::DumpError(v8, a2, (struct EventDumpWorkspace *)a3, v12);
      v13 = a3 + 5;
      goto LABEL_26;
    }
  }
  v13 = a3 + 5;
  v14 = *((_DWORD *)a3 + 10);
  if ( v14 && (!a4 || v9 || v14 != 111 && (v14 != 15005 || !a3[42])) )
  {
LABEL_18:
    EventXmlDump::DumpError(v8, a2, (struct EventDumpWorkspace *)a3, v14);
    goto LABEL_26;
  }
  if ( v8 )
  {
    if ( !v9 )
    {
      EventXmlDump::DumpData(v8, a2, (struct EventDumpWorkspace *)a3, a4);
      goto LABEL_26;
    }
    v15 = a2[1365]._file;
    v16 = a2[1365]._flag;
    v17 = EventXmlDump::DumpCustomData(v8, a2, (struct EventDumpWorkspace *)a3);
    if ( v17 && !TracerptFseek(a2, v16 + v15) )
    {
      v14 = v17;
      goto LABEL_18;
    }
  }
  else
  {
    v18 = *a3;
    if ( (*((_BYTE *)*a3 + 4) & 4) != 0 )
    {
      TracerptFPuts("\t\t<Data>", a2);
      PrintWString(a2, 1u, 0, *((unsigned __int16 **)*a3 + 12));
      TracerptFPuts("</Data>\r\n", a2);
    }
    else
    {
      TracerptFPutws((wchar_t *)L"\t<BinaryEventData>", a2);
      if ( *((_WORD *)v18 + 43) )
      {
        v19 = (unsigned __int8 *)*((_QWORD *)v18 + 12);
        if ( v19 )
          PrintBinaryHex(a2, *((unsigned __int16 *)v18 + 43), v19, 0);
      }
      TracerptFPutws((wchar_t *)L"</BinaryEventData>\r\n", a2);
    }
  }
LABEL_26:
  EventXmlDump::DumpRenderingInfo(v8, a2, (struct EventDumpWorkspace *)a3);
  if ( *((_QWORD *)this + 133) || (*((_WORD *)*a3 + 2) & 0x100) != 0 )
  {
    TracerptFPrintf(
      a2,
      "\t<ExtendedTracingInfo %ws>\r\n",
      L"xmlns=\"http://schemas.microsoft.com/win/2004/08/events/trace\"");
    if ( (*((_WORD *)*a3 + 2) & 0x100) != 0 )
    {
      TracerptFPuts("\t\t<EventGuid>", a2);
      v20 = CpdiGuidToString(v23, 0x80u, (struct _GUID *)((char *)*a3 + 24));
      PrintWString(a2, 1u, 0, v20);
      TracerptFPuts("</EventGuid>\r\n", a2);
    }
    v21 = (_DWORD *)*((_QWORD *)this + 133);
    if ( v21 )
    {
      TracerptFPrintf(a2, "\t\t<InstanceID>%lu</InstanceID>\r\n", *v21);
      TracerptFPrintf(
        a2,
        "\t\t<ParentInstanceID>%lu</ParentInstanceID>\r\n",
        *(_DWORD *)(*((_QWORD *)this + 133) + 4LL));
    }
    TracerptFPuts("\t</ExtendedTracingInfo>\r\n", a2);
  }
  TracerptFPuts("</Event>\r\n", a2);
  if ( *v13 == 111 )
    return 111;
  else
    return a3[42] != 0 ? 0x3A9D : 0;
}

```

## disassembly

```asm
0x14000faa4  mov     [rsp+arg_18], rbx
0x14000faa9  push    rbp
0x14000faaa  push    rsi
0x14000faab  push    rdi
0x14000faac  push    r12
0x14000faae  push    r13
0x14000fab0  push    r14
0x14000fab2  push    r15
0x14000fab4  sub     rsp, 130h
0x14000fabb  mov     rax, cs:__security_cookie
0x14000fac2  xor     rax, rsp
0x14000fac5  mov     [rsp+168h+var_48], rax
0x14000facd  mov     rbx, rdx
0x14000fad0  mov     rdi, r8
0x14000fad3  mov     r13, rcx
0x14000fad6  lea     r8, aXmlnsHttpSchem; "xmlns=\"http://schemas.microsoft.com/wi"...
0x14000fadd  mov     rcx, rbx; struct _iobuf *
0x14000fae0  lea     rdx, aEventWs; "<Event %ws>\r\n"
0x14000fae7  mov     ebp, r9d
0x14000faea  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x14000faef  mov     r8, rdi; struct EventDumpWorkspace *
0x14000faf2  mov     rdx, rbx; struct _iobuf *
0x14000faf5  mov     rcx, r13; this
0x14000faf8  call    ?DumpHeader@EventXmlDump@@QEAAKPEAU_iobuf@@PEAVEventDumpWorkspace@@@Z; EventXmlDump::DumpHeader(_iobuf *,EventDumpWorkspace *)
0x14000fafd  mov     rcx, [rdi+8]; this
0x14000fb01  xor     r12d, r12d
0x14000fb04  mov     eax, r12d
0x14000fb07  test    rcx, rcx
0x14000fb0a  jz      short loc_14000FB5E
0x14000fb0c  cmp     dword ptr [rcx+6Ch], 2
0x14000fb10  setz    al
0x14000fb13  cmp     dword ptr [rcx+30h], 2
0x14000fb17  jnz     short loc_14000FB5E
0x14000fb19  mov     rdx, [rdi]; pEvent
0x14000fb1c  mov     rcx, rbx; struct _iobuf *
0x14000fb1f  mov     ebp, [rbx+1000Ch]
0x14000fb25  mov     r14d, [rbx+10008h]
0x14000fb2c  call    ?PrintWPPEventXmlDump@@YAKPEAU_iobuf@@PEAU_EVENT_RECORD@@@Z; PrintWPPEventXmlDump(_iobuf *,_EVENT_RECORD *)
0x14000fb31  mov     esi, eax
0x14000fb33  test    eax, eax
0x14000fb35  jz      short loc_14000FB55
0x14000fb37  lea     edx, [r14+rbp]; unsigned int
0x14000fb3b  mov     rcx, rbx; struct _iobuf *
0x14000fb3e  call    ?TracerptFseek@@YAKPEAU_iobuf@@K@Z; TracerptFseek(_iobuf *,ulong)
0x14000fb43  test    eax, eax
0x14000fb45  jnz     short loc_14000FB55
0x14000fb47  mov     r9d, esi; unsigned int
0x14000fb4a  mov     r8, rdi; struct EventDumpWorkspace *
0x14000fb4d  mov     rdx, rbx; struct _iobuf *
0x14000fb50  call    ?DumpError@EventXmlDump@@QEAAKPEAU_iobuf@@PEAVEventDumpWorkspace@@K@Z; EventXmlDump::DumpError(_iobuf *,EventDumpWorkspace *,ulong)
0x14000fb55  lea     rsi, [rdi+28h]
0x14000fb59  jmp     loc_14000FC58
0x14000fb5e  lea     rsi, [rdi+28h]
0x14000fb62  mov     r9d, [rsi]
0x14000fb65  test    r9d, r9d
0x14000fb68  jz      short loc_14000FB8A
0x14000fb6a  test    ebp, ebp
0x14000fb6c  jz      short loc_14000FBCD
0x14000fb6e  test    eax, eax
0x14000fb70  jnz     short loc_14000FBCD
0x14000fb72  cmp     r9d, 6Fh ; 'o'
0x14000fb76  jz      short loc_14000FB8A
0x14000fb78  cmp     r9d, 3A9Dh
0x14000fb7f  jnz     short loc_14000FBCD
0x14000fb81  cmp     [rdi+150h], r12
0x14000fb88  jz      short loc_14000FBCD
0x14000fb8a  mov     rdx, rbx; struct _iobuf *
0x14000fb8d  test    rcx, rcx
0x14000fb90  jz      short loc_14000FBE4
0x14000fb92  mov     r8, rdi; struct EventDumpWorkspace *
0x14000fb95  test    eax, eax
0x14000fb97  jz      short loc_14000FBDA
0x14000fb99  mov     r14d, [rbx+1000Ch]
0x14000fba0  mov     r15d, [rbx+10008h]
0x14000fba7  call    ?DumpCustomData@EventXmlDump@@QEAAKPEAU_iobuf@@PEAVEventDumpWorkspace@@@Z; EventXmlDump::DumpCustomData(_iobuf *,EventDumpWorkspace *)
0x14000fbac  mov     ebp, eax
0x14000fbae  test    eax, eax
0x14000fbb0  jz      loc_14000FC58
0x14000fbb6  lea     edx, [r15+r14]; unsigned int
0x14000fbba  mov     rcx, rbx; struct _iobuf *
0x14000fbbd  call    ?TracerptFseek@@YAKPEAU_iobuf@@K@Z; TracerptFseek(_iobuf *,ulong)
0x14000fbc2  test    eax, eax
0x14000fbc4  jnz     loc_14000FC58
0x14000fbca  mov     r9d, ebp; unsigned int
0x14000fbcd  mov     r8, rdi; struct EventDumpWorkspace *
0x14000fbd0  mov     rdx, rbx; struct _iobuf *
0x14000fbd3  call    ?DumpError@EventXmlDump@@QEAAKPEAU_iobuf@@PEAVEventDumpWorkspace@@K@Z; EventXmlDump::DumpError(_iobuf *,EventDumpWorkspace *,ulong)
0x14000fbd8  jmp     short loc_14000FC58
0x14000fbda  mov     r9d, ebp; int
0x14000fbdd  call    ?DumpData@EventXmlDump@@QEAAKPEAU_iobuf@@PEAVEventDumpWorkspace@@H@Z; EventXmlDump::DumpData(_iobuf *,EventDumpWorkspace *,int)
0x14000fbe2  jmp     short loc_14000FC58
0x14000fbe4  mov     rbp, [rdi]
0x14000fbe7  test    byte ptr [rbp+4], 4
0x14000fbeb  jz      short loc_14000FC1E
0x14000fbed  lea     rcx, Src; "\t\t<Data>"
0x14000fbf4  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14000fbf9  mov     r9, [rdi]
0x14000fbfc  xor     r8d, r8d; unsigned __int8
0x14000fbff  mov     dl, 1; unsigned __int8
0x14000fc01  mov     rcx, rbx; struct _iobuf *
0x14000fc04  mov     r9, [r9+60h]; unsigned __int16 *
0x14000fc08  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x14000fc0d  mov     rdx, rbx; struct _iobuf *
0x14000fc10  lea     rcx, aData_4; "</Data>\r\n"
0x14000fc17  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14000fc1c  jmp     short loc_14000FC58
0x14000fc1e  lea     rcx, aBinaryeventdat; "\t<BinaryEventData>"
0x14000fc25  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14000fc2a  cmp     [rbp+56h], r12w
0x14000fc2f  jbe     short loc_14000FC49
0x14000fc31  mov     r8, [rbp+60h]; unsigned __int8 *
0x14000fc35  test    r8, r8
0x14000fc38  jz      short loc_14000FC49
0x14000fc3a  movzx   edx, word ptr [rbp+56h]; unsigned __int64
0x14000fc3e  xor     r9d, r9d; unsigned __int8
0x14000fc41  mov     rcx, rbx; struct _iobuf *
0x14000fc44  call    ?PrintBinaryHex@@YAXPEAU_iobuf@@_KPEAEE@Z; PrintBinaryHex(_iobuf *,unsigned __int64,uchar *,uchar)
0x14000fc49  mov     rdx, rbx; struct _iobuf *
0x14000fc4c  lea     rcx, aBinaryeventdat_0; "</BinaryEventData>\r\n"
0x14000fc53  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14000fc58  mov     r8, rdi; struct EventDumpWorkspace *
0x14000fc5b  mov     rdx, rbx; struct _iobuf *
0x14000fc5e  call    ?DumpRenderingInfo@EventXmlDump@@QEAAXPEAU_iobuf@@PEAVEventDumpWorkspace@@@Z; EventXmlDump::DumpRenderingInfo(_iobuf *,EventDumpWorkspace *)
0x14000fc63  mov     ebp, 100h
0x14000fc68  cmp     [r13+428h], r12
0x14000fc6f  jnz     short loc_14000FC7E
0x14000fc71  mov     rax, [rdi]
0x14000fc74  test    [rax+4], bp
0x14000fc78  jz      loc_14000FD28
0x14000fc7e  lea     r8, aXmlnsHttpSchem_0; "xmlns=\"http://schemas.microsoft.com/wi"...
0x14000fc85  mov     rcx, rbx; struct _iobuf *
0x14000fc88  lea     rdx, aExtendedtracin; "\t<ExtendedTracingInfo %ws>\r\n"
0x14000fc8f  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x14000fc94  mov     rax, [rdi]
0x14000fc97  test    [rax+4], bp
0x14000fc9b  jz      short loc_14000FCE1
0x14000fc9d  mov     rdx, rbx; struct _iobuf *
0x14000fca0  lea     rcx, aEventguid; "\t\t<EventGuid>"
0x14000fca7  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14000fcac  mov     r8, [rdi]
0x14000fcaf  lea     rcx, [rsp+168h+var_148]; unsigned __int16 *
0x14000fcb4  add     r8, 18h; struct _GUID *
0x14000fcb8  mov     edx, 80h; unsigned int
0x14000fcbd  call    ?CpdiGuidToString@@YAPEAGPEAGKPEAU_GUID@@@Z; CpdiGuidToString(ushort *,ulong,_GUID *)
0x14000fcc2  mov     r9, rax; unsigned __int16 *
0x14000fcc5  xor     r8d, r8d; unsigned __int8
0x14000fcc8  mov     dl, 1; unsigned __int8
0x14000fcca  mov     rcx, rbx; struct _iobuf *
0x14000fccd  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x14000fcd2  mov     rdx, rbx; struct _iobuf *
0x14000fcd5  lea     rcx, aEventguid_0; "</EventGuid>\r\n"
0x14000fcdc  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14000fce1  mov     r8, [r13+428h]
0x14000fce8  test    r8, r8
0x14000fceb  jz      short loc_14000FD19
0x14000fced  mov     r8d, [r8]
0x14000fcf0  lea     rdx, aInstanceidLuIn; "\t\t<InstanceID>%lu</InstanceID>\r\n"
0x14000fcf7  mov     rcx, rbx; struct _iobuf *
0x14000fcfa  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x14000fcff  mov     r8, [r13+428h]
0x14000fd06  lea     rdx, aParentinstance; "\t\t<ParentInstanceID>%lu</ParentInstan"...
0x14000fd0d  mov     rcx, rbx; struct _iobuf *
0x14000fd10  mov     r8d, [r8+4]
0x14000fd14  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x14000fd19  mov     rdx, rbx; struct _iobuf *
0x14000fd1c  lea     rcx, aExtendedtracin_0; "\t</ExtendedTracingInfo>\r\n"
0x14000fd23  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14000fd28  mov     rdx, rbx; struct _iobuf *
0x14000fd2b  lea     rcx, aEvent; "</Event>\r\n"
0x14000fd32  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14000fd37  cmp     dword ptr [rsi], 6Fh ; 'o'
0x14000fd3a  jnz     short loc_14000FD43
0x14000fd3c  mov     eax, 6Fh ; 'o'
0x14000fd41  jmp     short loc_14000FD54
0x14000fd43  mov     rax, [rdi+150h]
0x14000fd4a  neg     rax
0x14000fd4d  sbb     eax, eax
0x14000fd4f  and     eax, 3A9Dh
0x14000fd54  mov     rcx, [rsp+168h+var_48]
0x14000fd5c  xor     rcx, rsp; StackCookie
0x14000fd5f  call    __security_check_cookie
0x14000fd64  mov     rbx, [rsp+168h+arg_18]
0x14000fd6c  add     rsp, 130h
0x14000fd73  pop     r15
0x14000fd75  pop     r14
0x14000fd77  pop     r13
0x14000fd79  pop     r12
0x14000fd7b  pop     rdi
0x14000fd7c  pop     rsi
0x14000fd7d  pop     rbp
0x14000fd7e  retn
```
