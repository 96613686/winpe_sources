# EventXmlDump::DumpError(_iobuf *,EventDumpWorkspace *,ulong)

- ea: `0x1400104f0`
- end: `0x14001058b`
- name: `?DumpError@EventXmlDump@@QEAAKPEAU_iobuf@@PEAVEventDumpWorkspace@@K@Z`
- size: `155`
- prototype: `__int64 __fastcall(EventXmlDump *this, struct _iobuf *, struct EventDumpWorkspace *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000faa4`

## callees

- `0x1400120f4`
- `0x14001601c`
- `0x1400161b0`

## pseudocode

```c
__int64 __fastcall EventXmlDump::DumpError(
        EventXmlDump *this,
        struct _iobuf *a2,
        struct EventDumpWorkspace *a3,
        int a4)
{
  TracerptFPuts("\t<ProcessingErrorData>\r\n", a2);
  TracerptFPrintf(a2, "\t\t<ErrorCode>%d</ErrorCode>\r\n", a4);
  TracerptFPuts("\t\t<DataItemName />\r\n", a2);
  TracerptFPuts("\t\t<EventPayload>", a2);
  PrintBinaryHex(a2, *(unsigned __int16 *)(*(_QWORD *)a3 + 86LL), *(unsigned __int8 **)(*(_QWORD *)a3 + 96LL), 0);
  TracerptFPuts("</EventPayload>\r\n", a2);
  TracerptFPuts("\t</ProcessingErrorData>\r\n", a2);
  return 0;
}

```

## disassembly

```asm
0x1400104f0  mov     [rsp+arg_0], rbx
0x1400104f5  mov     [rsp+arg_8], rsi
0x1400104fa  push    rdi
0x1400104fb  sub     rsp, 20h
0x1400104ff  lea     rcx, aProcessingerro; "\t<ProcessingErrorData>\r\n"
0x140010506  mov     ebx, r9d
0x140010509  mov     rdi, r8
0x14001050c  mov     rsi, rdx
0x14001050f  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010514  mov     r8d, ebx
0x140010517  lea     rdx, aErrorcodeDErro; "\t\t<ErrorCode>%d</ErrorCode>\r\n"
0x14001051e  mov     rcx, rsi; struct _iobuf *
0x140010521  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x140010526  mov     rdx, rsi; struct _iobuf *
0x140010529  lea     rcx, aDataitemname; "\t\t<DataItemName />\r\n"
0x140010530  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010535  mov     rdx, rsi; struct _iobuf *
0x140010538  lea     rcx, aEventpayload; "\t\t<EventPayload>"
0x14001053f  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010544  mov     r8, [rdi]
0x140010547  xor     r9d, r9d; unsigned __int8
0x14001054a  mov     rcx, rsi; struct _iobuf *
0x14001054d  movzx   edx, word ptr [r8+56h]; unsigned __int64
0x140010552  mov     r8, [r8+60h]; unsigned __int8 *
0x140010556  call    ?PrintBinaryHex@@YAXPEAU_iobuf@@_KPEAEE@Z; PrintBinaryHex(_iobuf *,unsigned __int64,uchar *,uchar)
0x14001055b  mov     rdx, rsi; struct _iobuf *
0x14001055e  lea     rcx, aEventpayload_0; "</EventPayload>\r\n"
0x140010565  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14001056a  mov     rdx, rsi; struct _iobuf *
0x14001056d  lea     rcx, aProcessingerro_0; "\t</ProcessingErrorData>\r\n"
0x140010574  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010579  mov     rbx, [rsp+28h+arg_0]
0x14001057e  xor     eax, eax
0x140010580  mov     rsi, [rsp+28h+arg_8]
0x140010585  add     rsp, 20h
0x140010589  pop     rdi
0x14001058a  retn
```
