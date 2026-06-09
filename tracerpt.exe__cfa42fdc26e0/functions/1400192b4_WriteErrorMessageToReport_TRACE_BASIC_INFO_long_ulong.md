# WriteErrorMessageToReport(_TRACE_BASIC_INFO *,long,ulong)

- ea: `0x1400192b4`
- end: `0x140019559`
- name: `?WriteErrorMessageToReport@@YAKPEAU_TRACE_BASIC_INFO@@JK@Z`
- size: `677`
- prototype: `DWORD __fastcall(struct _TRACE_BASIC_INFO *, DWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x14002ec00`

## callees

- `0x140013a04`
- `0x140015fa0`
- `0x1400162b4`
- `0x140016360`
- `0x1400164c4`
- `0x140016754`
- `0x1400172f4`
- `0x1400192b4`
- `0x14001eed0`
- `0x14002fba4`
- `0x14003012c`
- `0x140040130`
- `0x1400401c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140019529`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140019529`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140019403`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140019403`

## string_xrefs

- `0x140019377`: `<?xml version="1.0" encoding="UTF-16"?>\n`
- `0x140019398`: `<?xml-stylesheet type="text/xsl" href="%s"?>\n`
- `0x140019430`: `pdh.dll`

## pseudocode

```c
DWORD __fastcall WriteErrorMessageToReport(struct _TRACE_BASIC_INFO *a1, DWORD a2)
{
  int v3; // edx
  unsigned int v5; // esi
  WCHAR *v6; // rcx
  __int64 v7; // rax
  DWORD result; // eax
  struct _iobuf *v9; // rax
  struct _iobuf *v10; // rbx
  const unsigned __int16 *v11; // rcx
  __int64 v12; // rdx
  WCHAR *v13; // rax
  __int64 v14; // r8
  WCHAR *v15; // rcx
  OLECHAR *v16; // rdx
  WCHAR FileName[1024]; // [rsp+30h] [rbp-1028h] BYREF
  WCHAR Buffer[1024]; // [rsp+830h] [rbp-828h] BYREF

  v3 = *((_DWORD *)a1 + 50);
  v5 = 0;
  if ( (v3 & 8) != 0 )
  {
    v6 = (WCHAR *)*((_QWORD *)a1 + 8);
    if ( v6 )
    {
      v7 = -1;
      do
        ++v7;
      while ( v6[v7] );
      if ( v7 )
      {
        if ( (v3 & 0x40000) != 0 && *((_QWORD *)a1 + 14) )
        {
          result = GetTempName(FileName, 0x400u);
          v5 = result;
          if ( result )
            return result;
        }
        else
        {
          v12 = 1024;
          v13 = FileName;
          v14 = 2147483646;
          do
          {
            if ( !v14 )
              break;
            if ( !*v6 )
              break;
            *v13++ = *v6++;
            --v14;
            --v12;
          }
          while ( v12 );
          v15 = v13 - 1;
          if ( v12 )
            v15 = v13;
          *v15 = 0;
          if ( !v12 )
            return 1359;
        }
        v9 = TracerptWFopen(FileName, 1u, 0);
        v10 = v9;
        if ( v9 )
        {
          TracerptFPutwc(0xFEFFu, v9);
          TracerptFPutws(L"<?xml version=\"1.0\" encoding=\"UTF-16\"?>\r\n", v10);
          if ( (*((_DWORD *)a1 + 50) & 0x40000) == 0 && *((_QWORD *)a1 + 14) )
            TracerptFWPrintf(v10, L"<?xml-stylesheet type=\"text/xsl\" href=\"%s\"?>\r\n");
          TracerptFWPrintf(
            v10,
            L"<Report name='tracerpt' level='%d' top='25' version='%d.%d'>\r\n",
            *((unsigned int *)a1 + 56),
            10,
            0);
          TracerptFPutws(
            L"<Section key='-90000' name='tracerptHeader'>\r\n<Table name='error' style='info'>\r\n\t<Item>\r\n",
            v10);
          TracerptFWPrintf(v10, L"\t\t<Data name='errorCode'>0x%x</Data>\r\n", a2);
          if ( a2 == 6 && LoadStringW(0, 0x12Eu, Buffer, 1024) > 0
            || (int)FormatErrorMessage(a2, 0, Buffer) >= 0
            || (int)FormatErrorMessage(a2, L"pdh.dll", Buffer) >= 0 )
          {
            TracerptFPutws(L"\t\t<Data name='errorMessage'>", v10);
            PrintWString(v10, 1u, 0, Buffer);
            v11 = L"</Data>\r\n";
          }
          else
          {
            v11 = L"\t\t<Data name='errorMessage' translate='value'>unknownError</Data>\r\n";
          }
          TracerptFPutws(v11, v10);
          TracerptFPutws(L"\t</Item>\r\n</Table>\r\n</Section>\r\n", v10);
          TracerptFPutws(L"</Report>\r\n", v10);
          TracerptFClose(v10);
          TracerptMergeSections(FileName);
        }
        if ( (*((_DWORD *)a1 + 50) & 0x40000) != 0 )
        {
          v16 = (OLECHAR *)*((_QWORD *)a1 + 14);
          if ( v16 )
          {
            v5 = TransformXML(FileName, v16, *((LPCWSTR *)a1 + 8));
            DeleteFileW(FileName);
          }
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1400192b4  mov     [rsp+arg_10], rbx
0x1400192b9  mov     [rsp+arg_18], rbp
0x1400192be  push    rsi
0x1400192bf  push    rdi
0x1400192c0  push    r14
0x1400192c2  mov     eax, 1040h
0x1400192c7  call    _alloca_probe
0x1400192cc  sub     rsp, rax
0x1400192cf  mov     rax, cs:__security_cookie
0x1400192d6  xor     rax, rsp
0x1400192d9  mov     [rsp+1058h+var_28], rax
0x1400192e1  xor     r14d, r14d
0x1400192e4  mov     ebp, edx
0x1400192e6  mov     edx, [rcx+0C8h]
0x1400192ec  mov     rdi, rcx
0x1400192ef  mov     esi, r14d
0x1400192f2  test    dl, 8
0x1400192f5  jz      loc_14001952F
0x1400192fb  mov     rcx, [rcx+40h]
0x1400192ff  test    rcx, rcx
0x140019302  jz      loc_14001952F
0x140019308  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001930c  inc     rax
0x14001930f  cmp     [rcx+rax*2], r14w
0x140019314  jnz     short loc_14001930C
0x140019316  test    rax, rax
0x140019319  jz      loc_14001952F
0x14001931f  bt      edx, 12h
0x140019323  jnb     loc_140019449
0x140019329  cmp     [rdi+70h], r14
0x14001932d  jz      loc_140019449
0x140019333  mov     edx, 400h; unsigned __int64
0x140019338  lea     rcx, [rsp+1058h+FileName]; unsigned __int16 *
0x14001933d  call    ?GetTempName@@YAKPEAG_K@Z; GetTempName(ushort *,unsigned __int64)
0x140019342  mov     esi, eax
0x140019344  test    eax, eax
0x140019346  jnz     loc_140019531
0x14001934c  xor     r8d, r8d; unsigned __int8
0x14001934f  lea     rcx, [rsp+1058h+FileName]; unsigned __int16 *
0x140019354  mov     dl, 1; unsigned __int8
0x140019356  call    ?TracerptWFopen@@YAPEAU_iobuf@@PEBGEE@Z; TracerptWFopen(ushort const *,uchar,uchar)
0x14001935b  mov     rbx, rax
0x14001935e  test    rax, rax
0x140019361  jz      loc_1400194FF
0x140019367  mov     ecx, 0FEFFh; unsigned __int16
0x14001936c  mov     rdx, rax; struct _iobuf *
0x14001936f  call    ?TracerptFPutwc@@YAKGPEAU_iobuf@@@Z; TracerptFPutwc(ushort,_iobuf *)
0x140019374  mov     rdx, rbx; struct _iobuf *
0x140019377  lea     rcx, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"UTF-16"...
0x14001937e  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140019383  test    dword ptr [rdi+0C8h], 40000h
0x14001938d  jnz     short loc_1400193A7
0x14001938f  mov     r8, [rdi+70h]
0x140019393  test    r8, r8
0x140019396  jz      short loc_1400193A7
0x140019398  lea     rdx, aXmlStylesheetT; "<?xml-stylesheet type=\"text/xsl\" href"...
0x14001939f  mov     rcx, rbx; struct _iobuf *
0x1400193a2  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400193a7  mov     r8d, [rdi+0E0h]
0x1400193ae  lea     rdx, aReportNameTrac; "<Report name='tracerpt' level='%d' top="...
0x1400193b5  mov     r9d, 0Ah
0x1400193bb  mov     [rsp+1058h+var_1038], r14d
0x1400193c0  mov     rcx, rbx; struct _iobuf *
0x1400193c3  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400193c8  mov     rdx, rbx; struct _iobuf *
0x1400193cb  lea     rcx, aSectionKey9000; "<Section key='-90000' name='tracerptHea"...
0x1400193d2  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400193d7  mov     r8d, ebp
0x1400193da  lea     rdx, aDataNameErrorc; "\t\t<Data name='errorCode'>0x%x</Data>"...
0x1400193e1  mov     rcx, rbx; struct _iobuf *
0x1400193e4  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400193e9  cmp     ebp, 6
0x1400193ec  jnz     short loc_140019411
0x1400193ee  mov     r9d, 400h; cchBufferMax
0x1400193f4  lea     r8, [rsp+1058h+Buffer]; lpBuffer
0x1400193fc  mov     edx, 12Eh; uID
0x140019401  xor     ecx, ecx; hInstance
0x140019403  call    cs:__imp_LoadStringW
0x140019409  test    eax, eax
0x14001940b  jg      loc_14001949C
0x140019411  lea     r8, [rsp+1058h+Buffer]; lpBuffer
0x140019419  xor     edx, edx; lpLibFileName
0x14001941b  mov     ecx, ebp; dwMessageId
0x14001941d  call    FormatErrorMessage
0x140019422  test    eax, eax
0x140019424  jns     short loc_14001949C
0x140019426  lea     r8, [rsp+1058h+Buffer]; lpBuffer
0x14001942e  mov     ecx, ebp; dwMessageId
0x140019430  lea     rdx, aPdhDll_0; "pdh.dll"
0x140019437  call    FormatErrorMessage
0x14001943c  test    eax, eax
0x14001943e  jns     short loc_14001949C
0x140019440  lea     rcx, aDataNameErrorm; "\t\t<Data name='errorMessage' translate"...
0x140019447  jmp     short loc_1400194C7
0x140019449  mov     edx, 400h
0x14001944e  lea     rax, [rsp+1058h+FileName]
0x140019453  mov     r8d, 7FFFFFFEh
0x140019459  test    r8, r8
0x14001945c  jz      short loc_14001947D
0x14001945e  movzx   r9d, word ptr [rcx]
0x140019462  test    r9w, r9w
0x140019466  jz      short loc_14001947D
0x140019468  mov     [rax], r9w
0x14001946c  add     rcx, 2
0x140019470  add     rax, 2
0x140019474  dec     r8
0x140019477  sub     rdx, 1
0x14001947b  jnz     short loc_140019459
0x14001947d  test    rdx, rdx
0x140019480  lea     rcx, [rax-2]
0x140019484  cmovnz  rcx, rax
0x140019488  mov     [rcx], r14w
0x14001948c  jnz     loc_14001934C
0x140019492  mov     eax, 54Fh
0x140019497  jmp     loc_140019531
0x14001949c  mov     rdx, rbx; struct _iobuf *
0x14001949f  lea     rcx, aDataNameErrorm_0; "\t\t<Data name='errorMessage'>"
0x1400194a6  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400194ab  lea     r9, [rsp+1058h+Buffer]; unsigned __int16 *
0x1400194b3  xor     r8d, r8d; unsigned __int8
0x1400194b6  mov     dl, 1; unsigned __int8
0x1400194b8  mov     rcx, rbx; struct _iobuf *
0x1400194bb  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x1400194c0  lea     rcx, aData; "</Data>\r\n"
0x1400194c7  mov     rdx, rbx; struct _iobuf *
0x1400194ca  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400194cf  mov     rdx, rbx; struct _iobuf *
0x1400194d2  lea     rcx, aItemTableSecti; "\t</Item>\r\n</Table>\r\n</Section>\r\n"
0x1400194d9  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400194de  mov     rdx, rbx; struct _iobuf *
0x1400194e1  lea     rcx, aReport_0; "</Report>\r\n"
0x1400194e8  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400194ed  mov     rcx, rbx; struct _iobuf *
0x1400194f0  call    ?TracerptFClose@@YAHPEAU_iobuf@@@Z; TracerptFClose(_iobuf *)
0x1400194f5  lea     rcx, [rsp+1058h+FileName]; unsigned __int16 *
0x1400194fa  call    ?TracerptMergeSections@@YAJPEBG@Z; TracerptMergeSections(ushort const *)
0x1400194ff  test    dword ptr [rdi+0C8h], 40000h
0x140019509  jz      short loc_14001952F
0x14001950b  mov     rdx, [rdi+70h]; OLECHAR *
0x14001950f  test    rdx, rdx
0x140019512  jz      short loc_14001952F
0x140019514  mov     r8, [rdi+40h]; lpFileName
0x140019518  lea     rcx, [rsp+1058h+FileName]; psz
0x14001951d  call    ?TransformXML@@YAJPEBG00@Z; TransformXML(ushort const *,ushort const *,ushort const *)
0x140019522  lea     rcx, [rsp+1058h+FileName]; lpFileName
0x140019527  mov     esi, eax
0x140019529  call    cs:__imp_DeleteFileW
0x14001952f  mov     eax, esi
0x140019531  mov     rcx, [rsp+1058h+var_28]
0x140019539  xor     rcx, rsp; StackCookie
0x14001953c  call    __security_check_cookie
0x140019541  lea     r11, [rsp+1058h+var_18]
0x140019549  mov     rbx, [r11+30h]
0x14001954d  mov     rbp, [r11+38h]
0x140019551  mov     rsp, r11
0x140019554  pop     r14
0x140019556  pop     rdi
0x140019557  pop     rsi
0x140019558  retn
```
