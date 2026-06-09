# HrReadRequest(_EXTENSION_CONTROL_BLOCK *,IXMLDOMNode * *)

- ea: `0x180005e60`
- end: `0x1800063d8`
- name: `?HrReadRequest@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@PEAPEAUIXMLDOMNode@@@Z`
- size: `1400`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *, struct IXMLDOMNode **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000512c`

## callees

- `0x18000249c`
- `0x1800024c4`
- `0x180003728`
- `0x1800038ec`
- `0x180005e60`
- `0x180009070`
- `0x180009c44`
- `0x180009c80`
- `0x18000b158`
- `0x18000b308`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006076`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000638b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006076`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000638b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180005f5e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180005f5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000604e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000604e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060ef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006148`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006148`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180005f44`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180005f86`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180005f44`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180005f86`
- `OLEAUT32!__imp_SysAllocString` at `0x180005f9d`
- `OLEAUT32!__imp_SysAllocString` at `0x180005f9d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000636d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000636d`

## string_xrefs

- `0x180005f09`: `HrReadRequest(): Request had no body`
- `0x180006010`: `HrReadRequest(): Failed to allocate BSTR request body`
- `0x1800060b1`: `HrReadRequest(): Failed to allocate memory for wide char body`
- `0x180006263`: `HrReadRequest(): Failed to QI for IXMLDOMNode`
- `0x1800062ab`: `HrReadRequest(): Failed to get document element`
- `0x1800062df`: `HrReadRequest(): Failed to load XML`
- `0x1800062ff`: `HrReadRequest(): Failed to set async property on DOM document`
- `0x180006342`: `HrReadRequest(): Failed to create XML DOM document`
- `0x1800063ab`: `HrReadRequest(): Exiting`

## pseudocode

```c
__int64 __fastcall HrReadRequest(struct _EXTENSION_CONTROL_BLOCK *a1, struct IXMLDOMNode **a2)
{
  DWORD cbAvailable; // ebx
  struct IXMLDOMNode **v3; // rsi
  int Win32Error; // ebx
  _QWORD *v6; // rcx
  CHAR *lpbData; // r13
  OLECHAR *v8; // r12
  int v9; // eax
  __int64 cchWideChar; // rdi
  WCHAR *lpWideCharStr; // rax
  OLECHAR *v12; // rsi
  BSTR v13; // rax
  DWORD LastError; // eax
  DWORD v15; // eax
  HRESULT v16; // eax
  int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // r8d
  int v20; // eax
  _QWORD *v21; // rcx
  int v22; // edx
  const char *v23; // r9
  __int16 v25; // [rsp+70h] [rbp+40h] BYREF
  struct IXMLDOMNode **v26; // [rsp+78h] [rbp+48h]
  LPVOID ppv; // [rsp+80h] [rbp+50h] BYREF
  __int64 v28; // [rsp+88h] [rbp+58h] BYREF

  v26 = a2;
  cbAvailable = a1->cbAvailable;
  v3 = a2;
  if ( cbAvailable < a1->cbTotalBytes )
  {
    Win32Error = -2147467259;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return (unsigned int)Win32Error;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    goto LABEL_71;
  }
  lpbData = (CHAR *)a1->lpbData;
  if ( !cbAvailable )
  {
    Win32Error = -2147180030;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        77,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (unsigned int)"HrReadRequest(): Request had no body",
        2);
LABEL_66:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_67;
    }
    goto LABEL_67;
  }
  v8 = 0;
  v9 = MultiByteToWideChar(0xFDE9u, 0, lpbData, cbAvailable, 0, 0);
  cchWideChar = v9;
  if ( v9 )
  {
    lpWideCharStr = (WCHAR *)malloc(2LL * (v9 + 1));
    v12 = lpWideCharStr;
    if ( lpWideCharStr )
    {
      if ( MultiByteToWideChar(0xFDE9u, 0, lpbData, cbAvailable, lpWideCharStr, cchWideChar) )
      {
        v12[cchWideChar] = 0;
        v13 = SysAllocString(v12);
        v8 = v13;
        if ( v13 )
        {
          Win32Error = 0;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, v13);
          }
        }
        else
        {
          Win32Error = -2147024882;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              79,
              (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
              (unsigned int)"HrReadRequest(): Failed to allocate BSTR request body",
              14);
        }
      }
      else
      {
        Win32Error = HrFromLastWin32Error();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, LastError);
        }
      }
      free(v12);
    }
    else
    {
      Win32Error = -2147024882;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_67;
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        81,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (unsigned int)"HrReadRequest(): Failed to allocate memory for wide char body",
        14);
    }
    v3 = v26;
    goto LABEL_30;
  }
  Win32Error = HrFromLastWin32Error();
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v15 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, v15);
LABEL_30:
    v6 = WPP_GLOBAL_Control;
  }
  if ( Win32Error < 0 )
    goto LABEL_64;
  ppv = 0;
  v16 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, &ppv);
  Win32Error = v16;
  if ( v16 >= 0 )
  {
    v17 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
    Win32Error = v17;
    if ( v17 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_59;
      v22 = 87;
      v23 = "HrReadRequest(): Failed to set async property on DOM document";
      goto LABEL_58;
    }
    v25 = 0;
    Win32Error = HrValidateContentType(a1);
    if ( Win32Error >= 0 )
    {
      v18 = DwSoapSizeLimit();
      RestrictDomDocument((struct IXMLDOMDocument *)ppv, v18, v19);
      Win32Error = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, v8, &v25);
      if ( Win32Error >= 0 && v25 == -1 )
      {
        v28 = 0;
        HrRemoveComments((struct IXMLDOMDocument *)ppv);
        v17 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 360LL))(ppv, &v28);
        Win32Error = v17;
        if ( !v17 )
        {
          v20 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IXMLDOMNode **))v28)(v28, &IID_IXMLDOMNode, v3);
          Win32Error = v20;
          if ( v20 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                84,
                (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
                (unsigned int)"HrReadRequest(): Failed to QI for IXMLDOMNode",
                v20);
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          goto LABEL_59;
        }
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v22 = 85;
          v23 = "HrReadRequest(): Failed to get document element";
LABEL_58:
          WPP_SF_sd(v21[2], v22, (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, (_DWORD)v23, v17);
        }
LABEL_59:
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_63:
        v6 = WPP_GLOBAL_Control;
        goto LABEL_64;
      }
    }
    if ( Win32Error == 1 )
    {
      Win32Error = -2147180027;
    }
    else if ( !Win32Error )
    {
      goto LABEL_59;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (unsigned int)"HrReadRequest(): Failed to load XML",
        Win32Error);
    goto LABEL_59;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      88,
      (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
      (unsigned int)"HrReadRequest(): Failed to create XML DOM document",
      v16);
    goto LABEL_63;
  }
LABEL_64:
  if ( v8 )
  {
    SysFreeString(v8);
    goto LABEL_66;
  }
LABEL_67:
  if ( lpbData && lpbData != (CHAR *)a1->lpbData )
  {
    free(lpbData);
    v6 = WPP_GLOBAL_Control;
  }
  if ( Win32Error )
  {
LABEL_71:
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
      WPP_SF_sd(
        v6[2],
        89,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (unsigned int)"HrReadRequest(): Exiting",
        Win32Error);
  }
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x180005e60  mov     [rsp-38h+arg_8], rdx
0x180005e65  push    rbp
0x180005e66  push    rbx
0x180005e67  push    rsi
0x180005e68  push    rdi
0x180005e69  push    r12
0x180005e6b  push    r13
0x180005e6d  push    r15
0x180005e6f  mov     rbp, rsp
0x180005e72  sub     rsp, 30h
0x180005e76  mov     ebx, [rcx+8Ch]
0x180005e7c  mov     rsi, rdx
0x180005e7f  mov     r15, rcx
0x180005e82  cmp     ebx, [rcx+88h]
0x180005e88  jnb     short loc_180005ED4
0x180005e8a  mov     ebx, 80004005h
0x180005e8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e96  lea     rdi, WPP_GLOBAL_Control
0x180005e9d  cmp     rcx, rdi
0x180005ea0  jz      loc_1800063C7
0x180005ea6  test    dword ptr [rcx+1Ch], 400h
0x180005ead  jz      loc_18000639C
0x180005eb3  mov     rcx, [rcx+10h]
0x180005eb7  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180005ebe  mov     edx, 4Ch ; 'L'
0x180005ec3  call    WPP_SF_
0x180005ec8  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ecf  jmp     loc_18000639C
0x180005ed4  mov     r13, [rcx+90h]
0x180005edb  test    ebx, ebx
0x180005edd  jnz     short loc_180005F2A
0x180005edf  mov     ebx, 8004A202h
0x180005ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x180005eeb  lea     rdi, WPP_GLOBAL_Control
0x180005ef2  cmp     rcx, rdi
0x180005ef5  jz      loc_18000637A
0x180005efb  test    byte ptr [rcx+1Ch], 1
0x180005eff  jz      loc_18000637A
0x180005f05  mov     rcx, [rcx+10h]
0x180005f09  lea     r9, aHrreadrequestR; "HrReadRequest(): Request had no body"
0x180005f10  mov     edx, 4Dh ; 'M'
0x180005f15  mov     dword ptr [rsp+30h+lpWideCharStr], ebx
0x180005f19  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180005f20  call    WPP_SF_sd
0x180005f25  jmp     loc_180006373
0x180005f2a  xor     r12d, r12d
0x180005f2d  mov     r9d, ebx; cbMultiByte
0x180005f30  mov     [rsp+30h+cchWideChar], r12d; cchWideChar
0x180005f35  mov     r8, r13; lpMultiByteStr
0x180005f38  xor     edx, edx; dwFlags
0x180005f3a  mov     [rsp+30h+lpWideCharStr], r12; lpWideCharStr
0x180005f3f  mov     ecx, 0FDE9h; CodePage
0x180005f44  call    cs:__imp_MultiByteToWideChar
0x180005f4a  movsxd  rdi, eax
0x180005f4d  test    eax, eax
0x180005f4f  jz      loc_1800060CF
0x180005f55  lea     eax, [rdi+1]
0x180005f58  movsxd  rcx, eax
0x180005f5b  add     rcx, rcx; Size
0x180005f5e  call    cs:__imp_malloc
0x180005f64  mov     rsi, rax
0x180005f67  test    rax, rax
0x180005f6a  jz      loc_180006085
0x180005f70  mov     [rsp+30h+cchWideChar], edi; cchWideChar
0x180005f74  mov     r9d, ebx; cbMultiByte
0x180005f77  mov     r8, r13; lpMultiByteStr
0x180005f7a  mov     [rsp+30h+lpWideCharStr], rax; lpWideCharStr
0x180005f7f  xor     edx, edx; dwFlags
0x180005f81  mov     ecx, 0FDE9h; CodePage
0x180005f86  call    cs:__imp_MultiByteToWideChar
0x180005f8c  test    eax, eax
0x180005f8e  jz      loc_18000602E
0x180005f94  xor     eax, eax
0x180005f96  mov     rcx, rsi; psz
0x180005f99  mov     [rsi+rdi*2], ax
0x180005f9d  call    cs:__imp_SysAllocString
0x180005fa3  mov     r12, rax
0x180005fa6  test    rax, rax
0x180005fa9  jz      short loc_180005FEC
0x180005fab  xor     ebx, ebx
0x180005fad  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fb4  lea     rdi, WPP_GLOBAL_Control
0x180005fbb  cmp     rcx, rdi
0x180005fbe  jz      loc_180006073
0x180005fc4  test    dword ptr [rcx+1Ch], 400h
0x180005fcb  jz      loc_180006073
0x180005fd1  mov     rcx, [rcx+10h]
0x180005fd5  lea     edx, [rbx+4Eh]
0x180005fd8  mov     r9, rax
0x180005fdb  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180005fe2  call    WPP_SF_S
0x180005fe7  jmp     loc_180006073
0x180005fec  mov     eax, 8007000Eh
0x180005ff1  mov     ebx, eax
0x180005ff3  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ffa  lea     rdi, WPP_GLOBAL_Control
0x180006001  cmp     rcx, rdi
0x180006004  jz      short loc_180006073
0x180006006  test    byte ptr [rcx+1Ch], 1
0x18000600a  jz      short loc_180006073
0x18000600c  mov     rcx, [rcx+10h]
0x180006010  lea     r9, aHrreadrequestF; "HrReadRequest(): Failed to allocate BST"...
0x180006017  mov     edx, 4Fh ; 'O'
0x18000601c  mov     dword ptr [rsp+30h+lpWideCharStr], eax
0x180006020  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180006027  call    WPP_SF_sd
0x18000602c  jmp     short loc_180006073
0x18000602e  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180006033  mov     ebx, eax
0x180006035  mov     rcx, cs:WPP_GLOBAL_Control
0x18000603c  lea     rdi, WPP_GLOBAL_Control
0x180006043  cmp     rcx, rdi
0x180006046  jz      short loc_180006073
0x180006048  test    byte ptr [rcx+1Ch], 1
0x18000604c  jz      short loc_180006073
0x18000604e  call    cs:__imp_GetLastError
0x180006054  mov     rcx, cs:WPP_GLOBAL_Control
0x18000605b  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180006062  mov     edx, 50h ; 'P'
0x180006067  mov     r9d, eax
0x18000606a  mov     rcx, [rcx+10h]
0x18000606e  call    WPP_SF_d
0x180006073  mov     rcx, rsi; Block
0x180006076  call    cs:__imp_free
0x18000607c  mov     rsi, [rbp+arg_8]
0x180006080  jmp     loc_180006114
0x180006085  mov     eax, 8007000Eh
0x18000608a  mov     ebx, eax
0x18000608c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006093  lea     rdi, WPP_GLOBAL_Control
0x18000609a  cmp     rcx, rdi
0x18000609d  jz      loc_18000637A
0x1800060a3  test    byte ptr [rcx+1Ch], 1
0x1800060a7  jz      loc_18000637A
0x1800060ad  mov     rcx, [rcx+10h]
0x1800060b1  lea     r9, aHrreadrequestF_0; "HrReadRequest(): Failed to allocate mem"...
0x1800060b8  mov     edx, 51h ; 'Q'
0x1800060bd  mov     dword ptr [rsp+30h+lpWideCharStr], eax
0x1800060c1  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x1800060c8  call    WPP_SF_sd
0x1800060cd  jmp     short loc_18000607C
0x1800060cf  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800060d4  mov     ebx, eax
0x1800060d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060dd  lea     rdi, WPP_GLOBAL_Control
0x1800060e4  cmp     rcx, rdi
0x1800060e7  jz      short loc_18000611B
0x1800060e9  test    byte ptr [rcx+1Ch], 1
0x1800060ed  jz      short loc_18000611B
0x1800060ef  call    cs:__imp_GetLastError
0x1800060f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060fc  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180006103  mov     edx, 52h ; 'R'
0x180006108  mov     r9d, eax
0x18000610b  mov     rcx, [rcx+10h]
0x18000610f  call    WPP_SF_d
0x180006114  mov     rcx, cs:WPP_GLOBAL_Control
0x18000611b  test    ebx, ebx
0x18000611d  js      loc_180006365
0x180006123  xor     edx, edx; pUnkOuter
0x180006125  mov     [rbp+ppv], 0
0x18000612d  lea     rax, [rbp+ppv]
0x180006131  lea     r9, IID_IXMLDOMDocument; riid
0x180006138  mov     [rsp+30h+lpWideCharStr], rax; ppv
0x18000613d  lea     rcx, CLSID_DOMDocument60; rclsid
0x180006144  lea     r8d, [rdx+1]; dwClsContext
0x180006148  call    cs:__imp_CoCreateInstance
0x18000614e  mov     ebx, eax
0x180006150  test    eax, eax
0x180006152  js      loc_18000632C
0x180006158  mov     rcx, [rbp+ppv]
0x18000615c  xor     edx, edx
0x18000615e  mov     rax, [rcx]
0x180006161  mov     rax, [rax+1F8h]
0x180006168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000616d  mov     ebx, eax
0x18000616f  test    eax, eax
0x180006171  js      loc_1800062E8
0x180006177  xor     eax, eax
0x180006179  mov     rcx, r15; struct _EXTENSION_CONTROL_BLOCK *
0x18000617c  mov     [rbp+arg_0], ax
0x180006180  call    ?HrValidateContentType@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@@Z; HrValidateContentType(_EXTENSION_CONTROL_BLOCK *)
0x180006185  mov     ebx, eax
0x180006187  test    eax, eax
0x180006189  js      loc_1800062B4
0x18000618f  call    ?DwSoapSizeLimit@@YAKXZ; DwSoapSizeLimit(void)
0x180006194  mov     rcx, [rbp+ppv]; struct IXMLDOMDocument *
0x180006198  mov     edx, eax; unsigned int
0x18000619a  call    ?RestrictDomDocument@@YAXPEAUIXMLDOMDocument@@KK@Z; RestrictDomDocument(IXMLDOMDocument *,ulong,ulong)
0x18000619f  mov     rcx, [rbp+ppv]
0x1800061a3  lea     r8, [rbp+arg_0]
0x1800061a7  mov     rdx, r12
0x1800061aa  mov     rax, [rcx]
0x1800061ad  mov     rax, [rax+208h]
0x1800061b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061b9  mov     ebx, eax
0x1800061bb  test    eax, eax
0x1800061bd  js      loc_1800062B4
0x1800061c3  or      eax, 0FFFFFFFFh
0x1800061c6  cmp     ax, [rbp+arg_0]
0x1800061ca  jnz     loc_1800062B4
0x1800061d0  mov     rcx, [rbp+ppv]; struct IXMLDOMDocument *
0x1800061d4  mov     [rbp+arg_18], 0
0x1800061dc  call    ?HrRemoveComments@@YAJPEAUIXMLDOMDocument@@@Z; HrRemoveComments(IXMLDOMDocument *)
0x1800061e1  mov     rcx, [rbp+ppv]
0x1800061e5  lea     rdx, [rbp+arg_18]
0x1800061e9  mov     rax, [rcx]
0x1800061ec  mov     rax, [rax+168h]
0x1800061f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061f8  mov     ebx, eax
0x1800061fa  test    eax, eax
0x1800061fc  jnz     loc_180006294
0x180006202  mov     rcx, [rbp+arg_18]
0x180006206  lea     rdx, IID_IXMLDOMNode
0x18000620d  mov     r8, rsi
0x180006210  mov     rax, [rcx]
0x180006213  mov     rax, [rax]
0x180006216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000621b  mov     ebx, eax
0x18000621d  test    eax, eax
0x18000621f  js      short loc_18000624D
0x180006221  mov     rcx, cs:WPP_GLOBAL_Control
0x180006228  cmp     rcx, rdi
0x18000622b  jz      short loc_18000627F
0x18000622d  test    dword ptr [rcx+1Ch], 400h
0x180006234  jz      short loc_18000627F
0x180006236  mov     rcx, [rcx+10h]
0x18000623a  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180006241  mov     edx, 53h ; 'S'
0x180006246  call    WPP_SF_
0x18000624b  jmp     short loc_18000627F
0x18000624d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006254  cmp     rcx, rdi
0x180006257  jz      short loc_18000627F
0x180006259  test    byte ptr [rcx+1Ch], 1
0x18000625d  jz      short loc_18000627F
0x18000625f  mov     rcx, [rcx+10h]
0x180006263  lea     r9, aHrreadrequestF_1; "HrReadRequest(): Failed to QI for IXMLD"...
0x18000626a  mov     edx, 54h ; 'T'
0x18000626f  mov     dword ptr [rsp+30h+lpWideCharStr], eax
0x180006273  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x18000627a  call    WPP_SF_sd
0x18000627f  mov     rcx, [rbp+arg_18]
0x180006283  mov     rax, [rcx]
0x180006286  mov     rax, [rax+10h]
0x18000628a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000628f  jmp     loc_18000631A
0x180006294  mov     rcx, cs:WPP_GLOBAL_Control
0x18000629b  cmp     rcx, rdi
0x18000629e  jz      short loc_18000631A
0x1800062a0  test    byte ptr [rcx+1Ch], 1
0x1800062a4  jz      short loc_18000631A
0x1800062a6  mov     edx, 55h ; 'U'
0x1800062ab  lea     r9, aHrreadrequestF_5; "HrReadRequest(): Failed to get document"...
0x1800062b2  jmp     short loc_180006306
0x1800062b4  cmp     ebx, 1
0x1800062b7  jnz     short loc_1800062C0
0x1800062b9  mov     ebx, 8004A205h
0x1800062be  jmp     short loc_1800062C4
0x1800062c0  test    ebx, ebx
0x1800062c2  jz      short loc_18000631A
0x1800062c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062cb  cmp     rcx, rdi
0x1800062ce  jz      short loc_18000631A
0x1800062d0  test    byte ptr [rcx+1Ch], 1
0x1800062d4  jz      short loc_18000631A
0x1800062d6  mov     edx, 56h ; 'V'
0x1800062db  mov     dword ptr [rsp+30h+lpWideCharStr], ebx
0x1800062df  lea     r9, aHrreadrequestF_4; "HrReadRequest(): Failed to load XML"
0x1800062e6  jmp     short loc_18000630A
0x1800062e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062ef  cmp     rcx, rdi
0x1800062f2  jz      short loc_18000631A
0x1800062f4  test    byte ptr [rcx+1Ch], 1
0x1800062f8  jz      short loc_18000631A
0x1800062fa  mov     edx, 57h ; 'W'
0x1800062ff  lea     r9, aHrreadrequestF_2; "HrReadRequest(): Failed to set async pr"...
0x180006306  mov     dword ptr [rsp+30h+lpWideCharStr], eax
0x18000630a  mov     rcx, [rcx+10h]
0x18000630e  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180006315  call    WPP_SF_sd
0x18000631a  mov     rcx, [rbp+ppv]
0x18000631e  mov     rax, [rcx]
0x180006321  mov     rax, [rax+10h]
0x180006325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000632a  jmp     short loc_18000635E
0x18000632c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006333  cmp     rcx, rdi
0x180006336  jz      short loc_180006365
0x180006338  test    byte ptr [rcx+1Ch], 1
0x18000633c  jz      short loc_180006365
0x18000633e  mov     rcx, [rcx+10h]
0x180006342  lea     r9, aHrreadrequestF_3; "HrReadRequest(): Failed to create XML D"...
0x180006349  mov     edx, 58h ; 'X'
0x18000634e  mov     dword ptr [rsp+30h+lpWideCharStr], eax
0x180006352  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180006359  call    WPP_SF_sd
0x18000635e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006365  test    r12, r12
0x180006368  jz      short loc_18000637A
  ... truncated ...
```
