# EventXmlDump::DumpRenderingInfo(_iobuf *,EventDumpWorkspace *)

- ea: `0x140010a88`
- end: `0x140010f7a`
- name: `?DumpRenderingInfo@EventXmlDump@@QEAAXPEAU_iobuf@@PEAVEventDumpWorkspace@@@Z`
- size: `1266`
- prototype: `void __fastcall(EventXmlDump *this, struct _iobuf *, struct EventDumpWorkspace *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000faa4`

## callees

- `0x14000d738`
- `0x14000d818`
- `0x14000e214`
- `0x140010a88`
- `0x140013a04`
- `0x14001601c`
- `0x1400161b0`
- `0x140040130`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140010cc7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140010cc7`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x140010ace`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x140010ace`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010d24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010d24`

## string_xrefs

- `0x140010c45`: `		<Task>`
- `0x140010c73`: `</Task>\n`
- `0x140010df4`: `xmlns="http://schemas.microsoft.com/win/2004/08/events/trace"`
- `0x140010e85`: `xmlns="http://schemas.microsoft.com/win/2004/08/events/trace"`

## pseudocode

```c
void __fastcall EventXmlDump::DumpRenderingInfo(EventXmlDump *this, struct _iobuf *a2, struct EventDumpWorkspace *a3)
{
  _DWORD *v3; // rbx
  unsigned __int16 *v6; // r9
  unsigned __int16 *v7; // r9
  unsigned __int16 *v8; // rsi
  __int64 v9; // rax
  unsigned __int16 *v10; // r9
  char *v11; // rdx
  DWORD v12; // eax
  unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rsi
  unsigned __int16 *v15; // r9
  __int64 v16; // rcx
  unsigned __int16 *v17; // rsi
  bool v18; // zf
  __int64 v19; // rsi
  unsigned __int16 *v20; // rsi
  int v21; // esi
  struct _EVENT_DUMP_DATA *NextTopLevel; // rbx
  va_list *Arguments; // [rsp+30h] [rbp-108h]
  WCHAR Buffer[4]; // [rsp+40h] [rbp-F8h] BYREF
  _BYTE v25[24]; // [rsp+48h] [rbp-F0h] BYREF
  WCHAR LocaleName[88]; // [rsp+60h] [rbp-D8h] BYREF

  v3 = (_DWORD *)*((_QWORD *)a3 + 1);
  if ( v3 && GetUserDefaultLocaleName(LocaleName, 85) )
  {
    TracerptFPuts("\t<RenderingInfo", a2);
    TracerptFPrintf(a2, " Culture=\"%ws\"", LocaleName);
    TracerptFPuts(">\r\n", a2);
    if ( v3[14] && (_DWORD *)((char *)v3 + (unsigned int)v3[14]) )
    {
      TracerptFPuts("\t\t<Level>", a2);
      if ( v3[14] )
        v6 = (unsigned __int16 *)((char *)v3 + (unsigned int)v3[14]);
      else
        v6 = 0;
      PrintWString(a2, 1u, 0, v6);
      TracerptFPuts("</Level>\r\n", a2);
    }
    if ( v3[18] && (_DWORD *)((char *)v3 + (unsigned int)v3[18]) )
    {
      TracerptFPuts("\t\t<Opcode>", a2);
      if ( v3[18] )
        v7 = (unsigned __int16 *)((char *)v3 + (unsigned int)v3[18]);
      else
        v7 = 0;
      PrintWString(a2, 1u, 0, v7);
      TracerptFPuts("</Opcode>\r\n", a2);
    }
    if ( v3[16] && (_DWORD *)((char *)v3 + (unsigned int)v3[16]) )
    {
      TracerptFPuts("\t\t<Keywords>\r\n", a2);
      if ( v3[16] )
        v8 = (unsigned __int16 *)((char *)v3 + (unsigned int)v3[16]);
      else
        v8 = 0;
      while ( *v8 )
      {
        TracerptFPuts("\t\t\t<Keyword>", a2);
        PrintWString(a2, 1u, 0, v8);
        TracerptFPuts("</Keyword>\r\n", a2);
        v9 = -1;
        do
          ++v9;
        while ( v8[v9] );
        v8 += v9 + 1;
      }
      TracerptFPuts("\t\t</Keywords>\r\n", a2);
    }
    if ( v3[12] != 1 && v3[17] && (_DWORD *)((char *)v3 + (unsigned int)v3[17]) )
    {
      TracerptFPuts("\t\t<Task>", a2);
      if ( v3[17] )
        v10 = (unsigned __int16 *)((char *)v3 + (unsigned int)v3[17]);
      else
        v10 = 0;
      PrintWString(a2, 1u, 0, v10);
      TracerptFPuts("</Task>\r\n", a2);
    }
    if ( !v3[19] || (v11 = (char *)v3 + (unsigned int)v3[19]) == 0 || !*((_QWORD *)a3 + 3) )
    {
LABEL_43:
      if ( v3[12] )
        goto LABEL_54;
      if ( v3[15] && (_DWORD *)((char *)v3 + (unsigned int)v3[15]) )
      {
        TracerptFPuts("\t\t<Channel>", a2);
        if ( v3[15] )
          v15 = (unsigned __int16 *)((char *)v3 + (unsigned int)v3[15]);
        else
          v15 = 0;
        PrintWString(a2, 1u, 0, v15);
        TracerptFPuts("</Channel>\r\n", a2);
      }
      if ( v3[12] )
      {
LABEL_54:
        if ( v3[12] != 1 )
        {
LABEL_76:
          TracerptFPuts("\t</RenderingInfo>\r\n", a2);
          return;
        }
        if ( !v3[13] )
        {
LABEL_59:
          if ( v3[12] == 1 )
          {
            if ( v3[17] )
            {
              v20 = (unsigned __int16 *)((char *)v3 + (unsigned int)v3[17]);
              if ( v20 )
              {
                TracerptFPrintf(
                  a2,
                  "\t\t<EventName %ws>",
                  L"xmlns=\"http://schemas.microsoft.com/win/2004/08/events/trace\"");
                PrintWString(a2, 1u, 0, v20);
                TracerptFPuts("</EventName>\r\n", a2);
              }
            }
            if ( v3[12] == 1 && *((_DWORD *)a3 + 9) )
            {
              EventDumpIterator::EventDumpIterator((EventDumpIterator *)v25, a3);
              v21 = 0;
              NextTopLevel = EventDumpIterator::GetNextTopLevel((EventDumpIterator *)v25);
              if ( NextTopLevel )
              {
                do
                {
                  if ( (*((_BYTE *)NextTopLevel + 60) & 0x40) != 0
                    && *((_QWORD *)NextTopLevel + 4)
                    && *((_QWORD *)NextTopLevel + 5) )
                  {
                    if ( !v21 )
                    {
                      TracerptFPrintf(
                        a2,
                        "\t\t<Map %ws>\r\n",
                        L"xmlns=\"http://schemas.microsoft.com/win/2004/08/events/trace\"");
                      v21 = 1;
                    }
                    TracerptFPuts("\t\t\t<Data Name=\"", a2);
                    PrintWString(a2, 1u, 0, *(unsigned __int16 **)NextTopLevel);
                    TracerptFPuts("\" Value=\"", a2);
                    TracerptFPrintf(a2, "%ws", *((_QWORD *)NextTopLevel + 5));
                    TracerptFPuts("\">", a2);
                    PrintWString(a2, 1u, 0, *((unsigned __int16 **)NextTopLevel + 4));
                    TracerptFPuts("</Data>\r\n", a2);
                  }
                  NextTopLevel = EventDumpIterator::GetNextTopLevel((EventDumpIterator *)v25);
                }
                while ( NextTopLevel );
                if ( v21 )
                  TracerptFPuts("\t\t</Map>\r\n", a2);
              }
              EventDumpIterator::~EventDumpIterator((EventDumpIterator *)v25);
            }
          }
          goto LABEL_76;
        }
        v19 = (unsigned int)v3[13];
        v18 = (_DWORD *)((char *)v3 + v19) == 0;
        v17 = (unsigned __int16 *)((char *)v3 + v19);
      }
      else
      {
        v16 = (unsigned int)v3[20];
        v17 = 0;
        if ( (_DWORD)v16 )
          v17 = (unsigned __int16 *)((char *)v3 + v16);
        v18 = v17 == 0;
      }
      if ( !v18 )
      {
        TracerptFPuts("\t\t<Provider>", a2);
        PrintWString(a2, 1u, 0, v17);
        TracerptFPuts("</Provider>\r\n", a2);
      }
      goto LABEL_59;
    }
    Arguments = (va_list *)*((_QWORD *)a3 + 3);
    *(_QWORD *)Buffer = 0;
    v12 = FormatMessageW(0x2500u, v11, 0xFFFFFFFF, 0, Buffer, 0, Arguments);
    v13 = *(unsigned __int16 **)Buffer;
    if ( v12 )
    {
      v14 = *(unsigned __int16 **)Buffer;
    }
    else
    {
      if ( !v3[19] )
      {
LABEL_41:
        if ( v13 )
          LocalFree(v13);
        goto LABEL_43;
      }
      v14 = (unsigned __int16 *)((char *)v3 + (unsigned int)v3[19]);
    }
    if ( v14 )
    {
      TracerptFPuts("\t\t<Message>", a2);
      PrintWString(a2, 1u, 0, v14);
      TracerptFPuts("</Message>\r\n", a2);
      v13 = *(unsigned __int16 **)Buffer;
    }
    goto LABEL_41;
  }
}

```

## disassembly

```asm
0x140010a88  mov     [rsp+arg_0], rbx
0x140010a8d  mov     [rsp+arg_18], rbp
0x140010a92  push    rsi
0x140010a93  push    rdi
0x140010a94  push    r14
0x140010a96  sub     rsp, 120h
0x140010a9d  mov     rax, cs:__security_cookie
0x140010aa4  xor     rax, rsp
0x140010aa7  mov     [rsp+138h+var_28], rax
0x140010aaf  mov     rbx, [r8+8]
0x140010ab3  xor     r14d, r14d
0x140010ab6  mov     rbp, r8
0x140010ab9  mov     rdi, rdx
0x140010abc  test    rbx, rbx
0x140010abf  jz      loc_140010F52
0x140010ac5  lea     edx, [r14+55h]; cchLocaleName
0x140010ac9  lea     rcx, [rsp+138h+LocaleName]; lpLocaleName
0x140010ace  call    cs:__imp_GetUserDefaultLocaleName
0x140010ad4  test    eax, eax
0x140010ad6  jz      loc_140010F52
0x140010adc  mov     rdx, rdi; struct _iobuf *
0x140010adf  lea     rcx, aRenderinginfo_0; "\t<RenderingInfo"
0x140010ae6  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010aeb  lea     r8, [rsp+138h+LocaleName]
0x140010af0  mov     rcx, rdi; struct _iobuf *
0x140010af3  lea     rdx, aCultureWs; " Culture=\"%ws\""
0x140010afa  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x140010aff  mov     rdx, rdi; struct _iobuf *
0x140010b02  lea     rcx, asc_140045800; ">\r\n"
0x140010b09  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010b0e  cmp     [rbx+38h], r14d
0x140010b12  jz      short loc_140010B59
0x140010b14  mov     eax, [rbx+38h]
0x140010b17  add     rax, rbx
0x140010b1a  jz      short loc_140010B59
0x140010b1c  mov     rdx, rdi; struct _iobuf *
0x140010b1f  lea     rcx, aLevel_2; "\t\t<Level>"
0x140010b26  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010b2b  cmp     [rbx+38h], r14d
0x140010b2f  jnz     short loc_140010B36
0x140010b31  mov     r9d, r14d
0x140010b34  jmp     short loc_140010B3D
0x140010b36  mov     r9d, [rbx+38h]
0x140010b3a  add     r9, rbx; unsigned __int16 *
0x140010b3d  xor     r8d, r8d; unsigned __int8
0x140010b40  mov     dl, 1; unsigned __int8
0x140010b42  mov     rcx, rdi; struct _iobuf *
0x140010b45  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140010b4a  mov     rdx, rdi; struct _iobuf *
0x140010b4d  lea     rcx, aLevel_3; "</Level>\r\n"
0x140010b54  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010b59  cmp     [rbx+48h], r14d
0x140010b5d  jz      short loc_140010BA4
0x140010b5f  mov     eax, [rbx+48h]
0x140010b62  add     rax, rbx
0x140010b65  jz      short loc_140010BA4
0x140010b67  mov     rdx, rdi; struct _iobuf *
0x140010b6a  lea     rcx, aOpcode_1; "\t\t<Opcode>"
0x140010b71  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010b76  cmp     [rbx+48h], r14d
0x140010b7a  jnz     short loc_140010B81
0x140010b7c  mov     r9, r14
0x140010b7f  jmp     short loc_140010B88
0x140010b81  mov     r9d, [rbx+48h]
0x140010b85  add     r9, rbx; unsigned __int16 *
0x140010b88  xor     r8d, r8d; unsigned __int8
0x140010b8b  mov     dl, 1; unsigned __int8
0x140010b8d  mov     rcx, rdi; struct _iobuf *
0x140010b90  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140010b95  mov     rdx, rdi; struct _iobuf *
0x140010b98  lea     rcx, aOpcode_0; "</Opcode>\r\n"
0x140010b9f  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010ba4  cmp     [rbx+40h], r14d
0x140010ba8  jz      loc_140010C2E
0x140010bae  mov     eax, [rbx+40h]
0x140010bb1  add     rax, rbx
0x140010bb4  jz      short loc_140010C2E
0x140010bb6  mov     rdx, rdi; struct _iobuf *
0x140010bb9  lea     rcx, aKeywords_3; "\t\t<Keywords>\r\n"
0x140010bc0  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010bc5  cmp     [rbx+40h], r14d
0x140010bc9  jnz     short loc_140010BD0
0x140010bcb  mov     rsi, r14
0x140010bce  jmp     short loc_140010C19
0x140010bd0  mov     esi, [rbx+40h]
0x140010bd3  add     rsi, rbx
0x140010bd6  jmp     short loc_140010C19
0x140010bd8  lea     rcx, aKeyword_1; "\t\t\t<Keyword>"
0x140010bdf  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010be4  mov     r9, rsi; unsigned __int16 *
0x140010be7  xor     r8d, r8d; unsigned __int8
0x140010bea  mov     dl, 1; unsigned __int8
0x140010bec  mov     rcx, rdi; struct _iobuf *
0x140010bef  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140010bf4  mov     rdx, rdi; struct _iobuf *
0x140010bf7  lea     rcx, aKeyword; "</Keyword>\r\n"
0x140010bfe  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010c03  or      rax, 0FFFFFFFFFFFFFFFFh
0x140010c07  inc     rax
0x140010c0a  cmp     [rsi+rax*2], r14w
0x140010c0f  jnz     short loc_140010C07
0x140010c11  lea     rsi, [rsi+rax*2]
0x140010c15  add     rsi, 2
0x140010c19  mov     rdx, rdi; struct _iobuf *
0x140010c1c  cmp     [rsi], r14w
0x140010c20  jnz     short loc_140010BD8
0x140010c22  lea     rcx, aKeywords_1; "\t\t</Keywords>\r\n"
0x140010c29  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010c2e  cmp     dword ptr [rbx+30h], 1
0x140010c32  jz      short loc_140010C7F
0x140010c34  cmp     [rbx+44h], r14d
0x140010c38  jz      short loc_140010C7F
0x140010c3a  mov     eax, [rbx+44h]
0x140010c3d  add     rax, rbx
0x140010c40  jz      short loc_140010C7F
0x140010c42  mov     rdx, rdi; struct _iobuf *
0x140010c45  lea     rcx, aTask; "\t\t<Task>"
0x140010c4c  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010c51  cmp     [rbx+44h], r14d
0x140010c55  jnz     short loc_140010C5C
0x140010c57  mov     r9, r14
0x140010c5a  jmp     short loc_140010C63
0x140010c5c  mov     r9d, [rbx+44h]
0x140010c60  add     r9, rbx; unsigned __int16 *
0x140010c63  xor     r8d, r8d; unsigned __int8
0x140010c66  mov     dl, 1; unsigned __int8
0x140010c68  mov     rcx, rdi; struct _iobuf *
0x140010c6b  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140010c70  mov     rdx, rdi; struct _iobuf *
0x140010c73  lea     rcx, aTask_3; "</Task>\r\n"
0x140010c7a  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010c7f  cmp     [rbx+4Ch], r14d
0x140010c83  jz      loc_140010D2A
0x140010c89  mov     edx, [rbx+4Ch]
0x140010c8c  add     rdx, rbx; lpSource
0x140010c8f  jz      loc_140010D2A
0x140010c95  mov     rax, [rbp+18h]
0x140010c99  test    rax, rax
0x140010c9c  jz      loc_140010D2A
0x140010ca2  mov     [rsp+138h+Arguments], rax; Arguments
0x140010ca7  xor     r9d, r9d; dwLanguageId
0x140010caa  lea     rax, [rsp+138h+Buffer]
0x140010caf  mov     [rsp+138h+nSize], r14d; nSize
0x140010cb4  or      r8d, 0FFFFFFFFh; dwMessageId
0x140010cb8  mov     [rsp+138h+lpBuffer], rax; lpBuffer
0x140010cbd  mov     ecx, 2500h; dwFlags
0x140010cc2  mov     qword ptr [rsp+138h+Buffer], r14
0x140010cc7  call    cs:__imp_FormatMessageW
0x140010ccd  mov     rcx, qword ptr [rsp+138h+Buffer]
0x140010cd2  test    eax, eax
0x140010cd4  jnz     short loc_140010CE4
0x140010cd6  cmp     [rbx+4Ch], r14d
0x140010cda  jz      short loc_140010D1F
0x140010cdc  mov     esi, [rbx+4Ch]
0x140010cdf  add     rsi, rbx
0x140010ce2  jmp     short loc_140010CE7
0x140010ce4  mov     rsi, rcx
0x140010ce7  test    rsi, rsi
0x140010cea  jz      short loc_140010D1F
0x140010cec  mov     rdx, rdi; struct _iobuf *
0x140010cef  lea     rcx, aMessage_0; "\t\t<Message>"
0x140010cf6  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010cfb  mov     r9, rsi; unsigned __int16 *
0x140010cfe  xor     r8d, r8d; unsigned __int8
0x140010d01  mov     dl, 1; unsigned __int8
0x140010d03  mov     rcx, rdi; struct _iobuf *
0x140010d06  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140010d0b  mov     rdx, rdi; struct _iobuf *
0x140010d0e  lea     rcx, aMessage; "</Message>\r\n"
0x140010d15  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010d1a  mov     rcx, qword ptr [rsp+138h+Buffer]; hMem
0x140010d1f  test    rcx, rcx
0x140010d22  jz      short loc_140010D2A
0x140010d24  call    cs:__imp_LocalFree
0x140010d2a  cmp     [rbx+30h], r14d
0x140010d2e  jnz     short loc_140010D96
0x140010d30  cmp     [rbx+3Ch], r14d
0x140010d34  jz      short loc_140010D7B
0x140010d36  mov     eax, [rbx+3Ch]
0x140010d39  add     rax, rbx
0x140010d3c  jz      short loc_140010D7B
0x140010d3e  mov     rdx, rdi; struct _iobuf *
0x140010d41  lea     rcx, aChannel; "\t\t<Channel>"
0x140010d48  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010d4d  cmp     [rbx+3Ch], r14d
0x140010d51  jnz     short loc_140010D58
0x140010d53  mov     r9, r14
0x140010d56  jmp     short loc_140010D5F
0x140010d58  mov     r9d, [rbx+3Ch]
0x140010d5c  add     r9, rbx; unsigned __int16 *
0x140010d5f  xor     r8d, r8d; unsigned __int8
0x140010d62  mov     dl, 1; unsigned __int8
0x140010d64  mov     rcx, rdi; struct _iobuf *
0x140010d67  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140010d6c  mov     rdx, rdi; struct _iobuf *
0x140010d6f  lea     rcx, aChannel_0; "</Channel>\r\n"
0x140010d76  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010d7b  cmp     [rbx+30h], r14d
0x140010d7f  jnz     short loc_140010D96
0x140010d81  mov     ecx, [rbx+50h]
0x140010d84  mov     rsi, r14
0x140010d87  test    ecx, ecx
0x140010d89  lea     rax, [rbx+rcx]
0x140010d8d  cmovnz  rsi, rax
0x140010d91  test    rsi, rsi
0x140010d94  jmp     short loc_140010DAC
0x140010d96  cmp     dword ptr [rbx+30h], 1
0x140010d9a  jnz     loc_140010F43
0x140010da0  cmp     [rbx+34h], r14d
0x140010da4  jz      short loc_140010DDC
0x140010da6  mov     esi, [rbx+34h]
0x140010da9  add     rsi, rbx
0x140010dac  jz      short loc_140010DDC
0x140010dae  mov     rdx, rdi; struct _iobuf *
0x140010db1  lea     rcx, aProvider_0; "\t\t<Provider>"
0x140010db8  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010dbd  mov     r9, rsi; unsigned __int16 *
0x140010dc0  xor     r8d, r8d; unsigned __int8
0x140010dc3  mov     dl, 1; unsigned __int8
0x140010dc5  mov     rcx, rdi; struct _iobuf *
0x140010dc8  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140010dcd  mov     rdx, rdi; struct _iobuf *
0x140010dd0  lea     rcx, aProvider_1; "</Provider>\r\n"
0x140010dd7  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010ddc  cmp     dword ptr [rbx+30h], 1
0x140010de0  jnz     loc_140010F43
0x140010de6  cmp     [rbx+44h], r14d
0x140010dea  jz      short loc_140010E29
0x140010dec  mov     esi, [rbx+44h]
0x140010def  add     rsi, rbx
0x140010df2  jz      short loc_140010E29
0x140010df4  lea     r8, aXmlnsHttpSchem_0; "xmlns=\"http://schemas.microsoft.com/wi"...
0x140010dfb  mov     rcx, rdi; struct _iobuf *
0x140010dfe  lea     rdx, aEventnameWs; "\t\t<EventName %ws>"
0x140010e05  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x140010e0a  mov     r9, rsi; unsigned __int16 *
0x140010e0d  xor     r8d, r8d; unsigned __int8
0x140010e10  mov     dl, 1; unsigned __int8
0x140010e12  mov     rcx, rdi; struct _iobuf *
0x140010e15  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140010e1a  mov     rdx, rdi; struct _iobuf *
0x140010e1d  lea     rcx, aEventname; "</EventName>\r\n"
0x140010e24  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010e29  cmp     dword ptr [rbx+30h], 1
0x140010e2d  jnz     loc_140010F43
0x140010e33  cmp     [rbp+24h], r14d
0x140010e37  jz      loc_140010F43
0x140010e3d  mov     rdx, rbp; struct EventDumpWorkspace *
0x140010e40  lea     rcx, [rsp+138h+var_F0]; this
0x140010e45  call    ??0EventDumpIterator@@QEAA@PEAVEventDumpWorkspace@@@Z; EventDumpIterator::EventDumpIterator(EventDumpWorkspace *)
0x140010e4a  lea     rcx, [rsp+138h+var_F0]; this
0x140010e4f  mov     esi, r14d
0x140010e52  call    ?GetNextTopLevel@EventDumpIterator@@QEAAPEAU_EVENT_DUMP_DATA@@XZ; EventDumpIterator::GetNextTopLevel(void)
0x140010e57  mov     rbx, rax
0x140010e5a  test    rax, rax
0x140010e5d  jz      loc_140010F39
0x140010e63  test    byte ptr [rbx+3Ch], 40h
0x140010e67  jz      loc_140010F10
0x140010e6d  cmp     [rbx+20h], r14
0x140010e71  jz      loc_140010F10
0x140010e77  cmp     [rbx+28h], r14
0x140010e7b  jz      loc_140010F10
0x140010e81  test    esi, esi
0x140010e83  jnz     short loc_140010EA0
0x140010e85  lea     r8, aXmlnsHttpSchem_0; "xmlns=\"http://schemas.microsoft.com/wi"...
0x140010e8c  mov     rcx, rdi; struct _iobuf *
0x140010e8f  lea     rdx, aMapWs_0; "\t\t<Map %ws>\r\n"
0x140010e96  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x140010e9b  mov     esi, 1
0x140010ea0  mov     rdx, rdi; struct _iobuf *
0x140010ea3  lea     rcx, aDataName_0; "\t\t\t<Data Name=\""
0x140010eaa  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010eaf  mov     r9, [rbx]; unsigned __int16 *
0x140010eb2  xor     r8d, r8d; unsigned __int8
0x140010eb5  mov     dl, 1; unsigned __int8
0x140010eb7  mov     rcx, rdi; struct _iobuf *
0x140010eba  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140010ebf  mov     rdx, rdi; struct _iobuf *
0x140010ec2  lea     rcx, aValue; "\" Value=\""
0x140010ec9  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010ece  mov     r8, [rbx+28h]
0x140010ed2  lea     rdx, aWs_3; "%ws"
0x140010ed9  mov     rcx, rdi; struct _iobuf *
0x140010edc  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x140010ee1  mov     rdx, rdi; struct _iobuf *
0x140010ee4  lea     rcx, asc_14004574C; "\">"
0x140010eeb  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010ef0  mov     r9, [rbx+20h]; unsigned __int16 *
0x140010ef4  xor     r8d, r8d; unsigned __int8
0x140010ef7  mov     dl, 1; unsigned __int8
0x140010ef9  mov     rcx, rdi; struct _iobuf *
0x140010efc  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x140010f01  mov     rdx, rdi; struct _iobuf *
0x140010f04  lea     rcx, aData_4; "</Data>\r\n"
0x140010f0b  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140010f10  lea     rcx, [rsp+138h+var_F0]; this
0x140010f15  call    ?GetNextTopLevel@EventDumpIterator@@QEAAPEAU_EVENT_DUMP_DATA@@XZ; EventDumpIterator::GetNextTopLevel(void)
0x140010f1a  mov     rbx, rax
0x140010f1d  test    rax, rax
0x140010f20  jnz     loc_140010E63
  ... truncated ...
```
