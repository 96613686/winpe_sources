# ExportEventSchema(ushort const *)

- ea: `0x1400152e8`
- end: `0x1400155d9`
- name: `?ExportEventSchema@@YAKPEBG@Z`
- size: `753`
- prototype: `unsigned int __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140018d04`

## callees

- `0x14001489c`
- `0x140014b98`
- `0x1400150f8`
- `0x1400152e8`
- `0x140015fa0`
- `0x140016360`
- `0x140016754`
- `0x1400400d6`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001532e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001532e`

## string_xrefs

- `0x14001550f`: `<?xml version="1.0" encoding="utf-8"?>\n`
- `0x140015520`: `<instrumentationManifest    xmlns="http://schemas.microsoft.com/win/2004/08/events"\n    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"\n    xmlns:xs="http://www.w3.org/2001/XMLSchema"\n    xmlns:win="http://manifests.microsoft.com/win/2004/08/windows/events"\n    xmlns:trace="http://schemas.microsoft.com/win/2004/08/events/trace"\n    xsi:schemaLocation="http://schemas.microsoft.com/win/2004/08/events eventman.xsd"\n    >\n`
- `0x1400155a9`: `</instrumentationManifest>\n`

## pseudocode

```c
DWORD __fastcall ExportEventSchema(const unsigned __int16 *a1)
{
  struct _iobuf *v2; // rdx
  LPVOID *i; // rdi
  unsigned int j; // ebx
  LPVOID *v6; // rcx
  struct _iobuf *v7; // [rsp+30h] [rbp-128h] BYREF
  _QWORD v8[3]; // [rsp+38h] [rbp-120h] BYREF
  _QWORD v9[2]; // [rsp+50h] [rbp-108h] BYREF
  int v10; // [rsp+60h] [rbp-F8h]
  _QWORD v11[2]; // [rsp+68h] [rbp-F0h] BYREF
  int v12; // [rsp+78h] [rbp-E0h]
  _QWORD v13[2]; // [rsp+80h] [rbp-D8h] BYREF
  int v14; // [rsp+90h] [rbp-C8h]
  _QWORD v15[2]; // [rsp+98h] [rbp-C0h] BYREF
  int v16; // [rsp+A8h] [rbp-B0h]
  _QWORD v17[2]; // [rsp+B0h] [rbp-A8h] BYREF
  int v18; // [rsp+C0h] [rbp-98h]
  _QWORD v19[2]; // [rsp+C8h] [rbp-90h] BYREF
  int v20; // [rsp+D8h] [rbp-80h]
  _QWORD v21[2]; // [rsp+E0h] [rbp-78h] BYREF
  int v22; // [rsp+F0h] [rbp-68h]
  _QWORD v23[2]; // [rsp+F8h] [rbp-60h] BYREF
  int v24; // [rsp+108h] [rbp-50h]
  _QWORD v25[9]; // [rsp+110h] [rbp-48h] BYREF
  int v26; // [rsp+168h] [rbp+10h] BYREF

  memset_0(&v7, 0, 0xF0u);
  v26 = 0;
  v2 = TracerptWFopen(a1, 0, 0);
  if ( !v2 )
    return GetLastError();
  v8[2] = 0;
  v10 = 0;
  v14 = 0;
  v16 = 0;
  v12 = 0;
  v18 = 0;
  v20 = 1;
  v24 = 0;
  v22 = 10;
  v9[1] = v9;
  v9[0] = v9;
  v8[1] = v8;
  v8[0] = v8;
  v11[1] = v11;
  v11[0] = v11;
  v15[1] = v15;
  v15[0] = v15;
  v17[1] = v17;
  v17[0] = v17;
  v13[1] = v13;
  v13[0] = v13;
  v19[1] = v19;
  v19[0] = v19;
  v21[1] = v21;
  v21[0] = v21;
  v23[1] = v23;
  v23[0] = v23;
  v25[1] = v25;
  v25[0] = v25;
  v7 = v2;
  qword_140083658 = (__int64)&qword_140083650;
  qword_140083650 = (__int64)&qword_140083650;
  qword_140083668 = (__int64)&qword_140083660;
  qword_140083660 = (__int64)&qword_140083660;
  for ( i = (LPVOID *)qword_140082180; i != &qword_140082180; i = (LPVOID *)*i )
  {
    for ( j = 0; j < 0x100; ++j )
    {
      v6 = &i[2 * j + 8];
      if ( *v6 != v6 )
      {
        EnumerateVersions(v6);
        v2 = v7;
      }
    }
  }
  TracerptFPutws((wchar_t *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?>\r\n", v2);
  TracerptFPutws(
    (wchar_t *)L"<instrumentationManifest    xmlns=\"http://schemas.microsoft.com/win/2004/08/events\"\r\n"
                "    xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instance\"\r\n"
                "    xmlns:xs=\"http://www.w3.org/2001/XMLSchema\"\r\n"
                "    xmlns:win=\"http://manifests.microsoft.com/win/2004/08/windows/events\"\r\n"
                "    xmlns:trace=\"http://schemas.microsoft.com/win/2004/08/events/trace\"\r\n"
                "    xsi:schemaLocation=\"http://schemas.microsoft.com/win/2004/08/events eventman.xsd\"\r\n"
                "    >\r\n",
    v7);
  TracerptFPutws((wchar_t *)L"  <instrumentation>\r\n", v7);
  TracerptFPutws((wchar_t *)L"    <events>\r\n", v7);
  DumpProviders(&v7, &qword_140083650, &v26);
  DumpProviders(&v7, &qword_140083660, &v26);
  TracerptFPutws((wchar_t *)L"    </events>\r\n", v7);
  TracerptFPutws((wchar_t *)L"  </instrumentation>\r\n", v7);
  DumpStringList(&v7);
  TracerptFPutws((wchar_t *)L"</instrumentationManifest>\r\n", v7);
  TracerptFClose(v7);
  return 0;
}

```

## disassembly

```asm
0x1400152e8  push    rbx
0x1400152ea  push    rsi
0x1400152eb  push    rdi
0x1400152ec  push    r12
0x1400152ee  push    r13
0x1400152f0  push    r15
0x1400152f2  sub     rsp, 128h
0x1400152f9  mov     rbx, rcx
0x1400152fc  xor     edx, edx; Val
0x1400152fe  mov     r8d, 0F0h; Size
0x140015304  lea     rcx, [rsp+158h+var_128]; void *
0x140015309  call    memset_0
0x14001530e  mov     [rsp+158h+arg_8], 0
0x140015319  xor     r8d, r8d; unsigned __int8
0x14001531c  xor     edx, edx; unsigned __int8
0x14001531e  mov     rcx, rbx; unsigned __int16 *
0x140015321  call    ?TracerptWFopen@@YAPEAU_iobuf@@PEBGEE@Z; TracerptWFopen(ushort const *,uchar,uchar)
0x140015326  mov     rdx, rax; struct _iobuf *
0x140015329  test    rax, rax
0x14001532c  jnz     short loc_140015339
0x14001532e  call    cs:__imp_GetLastError
0x140015334  jmp     loc_1400155C8
0x140015339  xor     esi, esi
0x14001533b  mov     [rsp+158h+var_110], rsi
0x140015340  mov     [rsp+158h+var_F8], esi
0x140015344  mov     [rsp+158h+var_C8], esi
0x14001534b  mov     [rsp+158h+var_B0], esi
0x140015352  mov     [rsp+158h+var_E0], esi
0x140015356  mov     [rsp+158h+var_98], esi
0x14001535d  mov     [rsp+158h+var_80], 1
0x140015368  mov     [rsp+158h+var_50], esi
0x14001536f  mov     [rsp+158h+var_68], 0Ah
0x14001537a  lea     rax, [rsp+158h+var_108]
0x14001537f  mov     [rsp+158h+var_100], rax
0x140015384  lea     rax, [rsp+158h+var_108]
0x140015389  mov     [rsp+158h+var_108], rax
0x14001538e  lea     rax, [rsp+158h+var_120]
0x140015393  mov     [rsp+158h+var_118], rax
0x140015398  lea     rax, [rsp+158h+var_120]
0x14001539d  mov     [rsp+158h+var_120], rax
0x1400153a2  lea     rax, [rsp+158h+var_F0]
0x1400153a7  mov     [rsp+158h+var_E8], rax
0x1400153ac  lea     rax, [rsp+158h+var_F0]
0x1400153b1  mov     [rsp+158h+var_F0], rax
0x1400153b6  lea     rax, [rsp+158h+var_C0]
0x1400153be  mov     [rsp+158h+var_B8], rax
0x1400153c6  lea     rax, [rsp+158h+var_C0]
0x1400153ce  mov     [rsp+158h+var_C0], rax
0x1400153d6  lea     rax, [rsp+158h+var_A8]
0x1400153de  mov     [rsp+158h+var_A0], rax
0x1400153e6  lea     rax, [rsp+158h+var_A8]
0x1400153ee  mov     [rsp+158h+var_A8], rax
0x1400153f6  lea     rax, [rsp+158h+var_D8]
0x1400153fe  mov     [rsp+158h+var_D0], rax
0x140015406  lea     rax, [rsp+158h+var_D8]
0x14001540e  mov     [rsp+158h+var_D8], rax
0x140015416  lea     rax, [rsp+158h+var_90]
0x14001541e  mov     [rsp+158h+var_88], rax
0x140015426  lea     rax, [rsp+158h+var_90]
0x14001542e  mov     [rsp+158h+var_90], rax
0x140015436  lea     rax, [rsp+158h+var_78]
0x14001543e  mov     [rsp+158h+var_70], rax
0x140015446  lea     rax, [rsp+158h+var_78]
0x14001544e  mov     [rsp+158h+var_78], rax
0x140015456  lea     rax, [rsp+158h+var_60]
0x14001545e  mov     [rsp+158h+var_58], rax
0x140015466  lea     rax, [rsp+158h+var_60]
0x14001546e  mov     [rsp+158h+var_60], rax
0x140015476  lea     rax, [rsp+158h+var_48]
0x14001547e  mov     [rsp+158h+var_40], rax
0x140015486  lea     rax, [rsp+158h+var_48]
0x14001548e  mov     [rsp+158h+var_48], rax
0x140015496  mov     [rsp+158h+var_128], rdx
0x14001549b  lea     r15, qword_140083650
0x1400154a2  mov     cs:qword_140083658, r15
0x1400154a9  mov     cs:qword_140083650, r15
0x1400154b0  lea     r12, qword_140083660
0x1400154b7  mov     cs:qword_140083668, r12
0x1400154be  mov     cs:qword_140083660, r12
0x1400154c5  mov     [rsp+158h+var_138], esi
0x1400154c9  lea     r13, qword_140082180
0x1400154d0  mov     rdi, cs:qword_140082180
0x1400154d7  cmp     rdi, r13
0x1400154da  jz      short loc_14001550F
0x1400154dc  xor     ebx, ebx
0x1400154de  mov     [rsp+158h+var_138], ebx
0x1400154e2  cmp     ebx, 100h
0x1400154e8  jnb     short loc_14001550A
0x1400154ea  mov     ecx, ebx
0x1400154ec  add     rcx, 4
0x1400154f0  shl     rcx, 4
0x1400154f4  add     rcx, rdi
0x1400154f7  cmp     [rcx], rcx
0x1400154fa  jz      short loc_140015506
0x1400154fc  call    EnumerateVersions
0x140015501  mov     rdx, [rsp+158h+var_128]
0x140015506  inc     ebx
0x140015508  jmp     short loc_1400154DE
0x14001550a  mov     rdi, [rdi]
0x14001550d  jmp     short loc_1400154D7
0x14001550f  lea     rcx, aXmlVersion10En_0; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x140015516  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001551b  mov     rdx, [rsp+158h+var_128]; struct _iobuf *
0x140015520  lea     rcx, aInstrumentatio_0; "<instrumentationManifest    xmlns=\"htt"...
0x140015527  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001552c  mov     rdx, [rsp+158h+var_128]; struct _iobuf *
0x140015531  lea     rcx, aInstrumentatio_2; "  <instrumentation>\r\n"
0x140015538  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001553d  mov     rdx, [rsp+158h+var_128]; struct _iobuf *
0x140015542  lea     rcx, aEvents_0; "    <events>\r\n"
0x140015549  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001554e  lea     r8, [rsp+158h+arg_8]
0x140015556  mov     rdx, r15
0x140015559  lea     rcx, [rsp+158h+var_128]
0x14001555e  call    DumpProviders
0x140015563  lea     r8, [rsp+158h+arg_8]
0x14001556b  mov     rdx, r12
0x14001556e  lea     rcx, [rsp+158h+var_128]
0x140015573  call    DumpProviders
0x140015578  mov     rdx, [rsp+158h+var_128]; struct _iobuf *
0x14001557d  lea     rcx, aEvents_2; "    </events>\r\n"
0x140015584  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140015589  mov     rdx, [rsp+158h+var_128]; struct _iobuf *
0x14001558e  lea     rcx, aInstrumentatio_1; "  </instrumentation>\r\n"
0x140015595  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001559a  lea     rcx, [rsp+158h+var_128]
0x14001559f  call    DumpStringList
0x1400155a4  mov     rdx, [rsp+158h+var_128]; struct _iobuf *
0x1400155a9  lea     rcx, aInstrumentatio; "</instrumentationManifest>\r\n"
0x1400155b0  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400155b5  jmp     short loc_1400155BC
0x1400155b7  mov     esi, 8
0x1400155bc  mov     rcx, [rsp+158h+var_128]; struct _iobuf *
0x1400155c1  call    ?TracerptFClose@@YAHPEAU_iobuf@@@Z; TracerptFClose(_iobuf *)
0x1400155c6  mov     eax, esi
0x1400155c8  add     rsp, 128h
0x1400155cf  pop     r15
0x1400155d1  pop     r13
0x1400155d3  pop     r12
0x1400155d5  pop     rdi
0x1400155d6  pop     rsi
0x1400155d7  pop     rbx
0x1400155d8  retn
0x1400402d7  push    rbp
0x1400402d9  sub     rsp, 20h
0x1400402dd  mov     rbp, rdx
0x1400402e0  mov     rax, [rcx]
0x1400402e3  xor     ecx, ecx
0x1400402e5  cmp     dword ptr [rax], 0C0000017h
0x1400402eb  setz    cl
0x1400402ee  mov     eax, ecx
0x1400402f0  add     rsp, 20h
0x1400402f4  pop     rbp
0x1400402f5  retn
```
