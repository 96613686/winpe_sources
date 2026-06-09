# HrWriteResponse(_EXTENSION_CONTROL_BLOCK *,IXMLDOMDocument *,int)

- ea: `0x180006868`
- end: `0x180006bbb`
- name: `?HrWriteResponse@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@PEAUIXMLDOMDocument@@H@Z`
- size: `851`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *, struct IXMLDOMDocument *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x1800063e0`

## callees

- `0x180001400`
- `0x18000249c`
- `0x1800024c4`
- `0x180002504`
- `0x180002884`
- `0x1800038ec`
- `0x180006868`
- `0x180006bc4`
- `0x180009908`
- `0x180009c44`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006b0f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006b0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006adb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006adb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000698c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000698c`

## string_xrefs

- `0x18000699d`: `Content-Length: %d\nContent-Type: text/xml; charset="utf-8"\nEXT:\n\n`
- `0x180006970`: `HrWriteResponse(): Failed to convert response envelope to ANSI`
- `0x180006b3f`: `HrWriteResponse(): Failed to get envelope XML text`
- `0x180006b71`: `HrWriteResponse(): Exiting`

## pseudocode

```c
__int64 __fastcall HrWriteResponse(struct _EXTENSION_CONTROL_BLOCK *a1, struct IXMLDOMDocument *a2, int a3)
{
  struct IXMLDOMDocumentVtbl *lpVtbl; // rax
  int v6; // eax
  signed int Win32Error; // ebx
  char *v8; // rax
  char *v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // rsi
  __int64 v12; // rcx
  char *v13; // rax
  __int64 v14; // r8
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  DWORD LastError; // eax
  __int64 v18; // rdx
  BSTR bstrString[2]; // [rsp+30h] [rbp-148h] BYREF
  char v21[256]; // [rsp+40h] [rbp-138h] BYREF

  lpVtbl = a2->lpVtbl;
  bstrString[0] = 0;
  v6 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, BSTR *))lpVtbl->get_xml)(a2, bstrString);
  Win32Error = v6;
  if ( v6 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return (unsigned int)Win32Error;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (unsigned int)"HrWriteResponse(): Failed to get envelope XML text",
        v6);
      v15 = WPP_GLOBAL_Control;
    }
    goto LABEL_45;
  }
  v8 = Utf8FromWsz(bstrString[0]);
  v9 = v8;
  if ( v8 )
  {
    v10 = 0x7FFFFFFF;
    do
    {
      if ( !*v8 )
        break;
      ++v8;
      --v10;
    }
    while ( v10 );
    Win32Error = v10 == 0 ? 0x80070057 : 0;
    v11 = (0x7FFFFFFF - v10) & -(__int64)(v10 != 0);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, v9);
    }
    else
    {
      LODWORD(v11) = 0;
    }
  }
  else
  {
    LODWORD(v11) = 0;
    Win32Error = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (unsigned int)"HrWriteResponse(): Failed to convert response envelope to ANSI",
        14);
  }
  SysFreeString(bstrString[0]);
  if ( Win32Error < 0 )
    goto LABEL_37;
  Win32Error = StringCbPrintfA(
                 v21,
                 0x100u,
                 "Content-Length: %d\r\nContent-Type: text/xml; charset=\"utf-8\"\r\nEXT:\r\n\r\n",
                 v11);
  if ( Win32Error < 0 )
    goto LABEL_37;
  v12 = 0x7FFFFFFF;
  v13 = v21;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v12;
  }
  while ( v12 );
  Win32Error = v12 == 0 ? 0x80070057 : 0;
  v14 = (0x7FFFFFFF - v12) & -(__int64)(v12 != 0);
  if ( !v12 )
    goto LABEL_37;
  if ( a3 )
  {
    if ( (unsigned int)bSendResponseToClient(a1, "200 OK", v14, v21, v11, v9) )
    {
      a1->dwHttpStatusCode = 200;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        v16 = 14;
LABEL_25:
        WPP_SF_(v15[2], v16, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids);
LABEL_37:
        v15 = WPP_GLOBAL_Control;
        goto LABEL_38;
      }
      goto LABEL_38;
    }
    Win32Error = HrFromLastWin32Error();
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_38;
    LastError = GetLastError();
    v18 = 15;
LABEL_36:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, LastError);
    goto LABEL_37;
  }
  if ( !(unsigned int)bSendResponseToClient(a1, "500 Internal Server Error", v14, v21, v11, v9) )
  {
    Win32Error = HrFromLastWin32Error();
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_38;
    LastError = GetLastError();
    v18 = 17;
    goto LABEL_36;
  }
  a1->dwHttpStatusCode = 500;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    v16 = 16;
    goto LABEL_25;
  }
LABEL_38:
  if ( v9 )
  {
    free(v9);
    v15 = WPP_GLOBAL_Control;
  }
  if ( Win32Error )
  {
LABEL_45:
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
      WPP_SF_sd(
        v15[2],
        18,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (unsigned int)"HrWriteResponse(): Exiting",
        Win32Error);
  }
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x180006868  mov     [rsp+arg_10], rbx
0x18000686d  mov     [rsp+arg_18], rbp
0x180006872  push    rsi
0x180006873  push    rdi
0x180006874  push    r12
0x180006876  push    r14
0x180006878  push    r15
0x18000687a  sub     rsp, 150h
0x180006881  mov     rax, cs:__security_cookie
0x180006888  xor     rax, rsp
0x18000688b  mov     [rsp+178h+var_38], rax
0x180006893  mov     rax, [rdx]
0x180006896  mov     r9, rdx
0x180006899  mov     r15, rcx
0x18000689c  mov     [rsp+178h+bstrString], 0
0x1800068a5  lea     rdx, [rsp+178h+bstrString]
0x1800068aa  mov     rcx, r9
0x1800068ad  mov     r12d, r8d
0x1800068b0  mov     rax, [rax+110h]
0x1800068b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068bc  mov     ebx, eax
0x1800068be  test    eax, eax
0x1800068c0  js      loc_180006B22
0x1800068c6  mov     rcx, [rsp+178h+bstrString]; lpWideCharStr
0x1800068cb  call    ?Utf8FromWsz@@YAPEADPEBG@Z; Utf8FromWsz(ushort const *)
0x1800068d0  lea     rbp, WPP_GLOBAL_Control
0x1800068d7  mov     rdi, rax
0x1800068da  mov     r14d, 7FFFFFFFh
0x1800068e0  test    rax, rax
0x1800068e3  jz      short loc_180006950
0x1800068e5  mov     edx, r14d
0x1800068e8  cmp     byte ptr [rax], 0
0x1800068eb  jz      short loc_1800068F6
0x1800068ed  inc     rax
0x1800068f0  sub     rdx, 1
0x1800068f4  jnz     short loc_1800068E8
0x1800068f6  mov     rax, rdx
0x1800068f9  mov     rcx, r14
0x1800068fc  neg     rax
0x1800068ff  mov     rax, rdx
0x180006902  sbb     ebx, ebx
0x180006904  sub     rcx, rdx
0x180006907  not     ebx
0x180006909  and     ebx, 80070057h
0x18000690f  neg     rax
0x180006912  sbb     rsi, rsi
0x180006915  and     rsi, rcx
0x180006918  test    rdx, rdx
0x18000691b  jnz     short loc_180006921
0x18000691d  xor     esi, esi
0x18000691f  jmp     short loc_180006987
0x180006921  mov     rcx, cs:WPP_GLOBAL_Control
0x180006928  cmp     rcx, rbp
0x18000692b  jz      short loc_180006987
0x18000692d  test    dword ptr [rcx+1Ch], 400h
0x180006934  jz      short loc_180006987
0x180006936  mov     rcx, [rcx+10h]
0x18000693a  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180006941  mov     edx, 0Bh
0x180006946  mov     r9, rdi
0x180006949  call    WPP_SF_s
0x18000694e  jmp     short loc_180006987
0x180006950  xor     esi, esi
0x180006952  mov     ebx, 8007000Eh
0x180006957  mov     rcx, cs:WPP_GLOBAL_Control
0x18000695e  cmp     rcx, rbp
0x180006961  jz      short loc_180006987
0x180006963  test    byte ptr [rcx+1Ch], 1
0x180006967  jz      short loc_180006987
0x180006969  mov     rcx, [rcx+10h]
0x18000696d  lea     edx, [rsi+0Ch]
0x180006970  lea     r9, aHrwriterespons_1; "HrWriteResponse(): Failed to convert re"...
0x180006977  mov     [rsp+178h+var_158], ebx
0x18000697b  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180006982  call    WPP_SF_sd
0x180006987  mov     rcx, [rsp+178h+bstrString]; bstrString
0x18000698c  call    cs:__imp_SysFreeString
0x180006992  test    ebx, ebx
0x180006994  js      loc_180006B00
0x18000699a  mov     r9d, esi
0x18000699d  lea     r8, aContentLengthD; "Content-Length: %d\r\nContent-Type: tex"...
0x1800069a4  mov     edx, 100h; unsigned __int64
0x1800069a9  lea     rcx, [rsp+178h+var_138]; char *
0x1800069ae  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x1800069b3  mov     ebx, eax
0x1800069b5  test    eax, eax
0x1800069b7  js      loc_180006B00
0x1800069bd  mov     rcx, r14
0x1800069c0  lea     rax, [rsp+178h+var_138]
0x1800069c5  cmp     byte ptr [rax], 0
0x1800069c8  jz      short loc_1800069D3
0x1800069ca  inc     rax
0x1800069cd  sub     rcx, 1
0x1800069d1  jnz     short loc_1800069C5
0x1800069d3  mov     rax, rcx
0x1800069d6  neg     rax
0x1800069d9  mov     rax, rcx
0x1800069dc  sbb     ebx, ebx
0x1800069de  sub     r14, rcx
0x1800069e1  not     ebx
0x1800069e3  and     ebx, 80070057h
0x1800069e9  neg     rax
0x1800069ec  sbb     r8, r8
0x1800069ef  and     r8, r14; unsigned int
0x1800069f2  test    rcx, rcx
0x1800069f5  jz      loc_180006B00
0x1800069fb  mov     [rsp+178h+var_150], rdi; char *
0x180006a00  lea     r9, [rsp+178h+var_138]; char *
0x180006a05  mov     [rsp+178h+var_158], esi; unsigned int
0x180006a09  mov     rcx, r15; struct _EXTENSION_CONTROL_BLOCK *
0x180006a0c  test    r12d, r12d
0x180006a0f  jz      short loc_180006A8E
0x180006a11  lea     rdx, a200Ok; "200 OK"
0x180006a18  call    ?bSendResponseToClient@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBDK1K1@Z; bSendResponseToClient(_EXTENSION_CONTROL_BLOCK *,char const *,ulong,char const *,ulong,char const *)
0x180006a1d  test    eax, eax
0x180006a1f  jz      short loc_180006A60
0x180006a21  mov     dword ptr [r15+10h], 0C8h
0x180006a29  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a30  cmp     rcx, rbp
0x180006a33  jz      loc_180006B07
0x180006a39  test    dword ptr [rcx+1Ch], 400h
0x180006a40  jz      loc_180006B07
0x180006a46  mov     edx, 0Eh
0x180006a4b  mov     rcx, [rcx+10h]
0x180006a4f  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180006a56  call    WPP_SF_
0x180006a5b  jmp     loc_180006B00
0x180006a60  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180006a65  mov     ebx, eax
0x180006a67  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a6e  cmp     rcx, rbp
0x180006a71  jz      loc_180006B07
0x180006a77  test    byte ptr [rcx+1Ch], 1
0x180006a7b  jz      loc_180006B07
0x180006a81  call    cs:__imp_GetLastError
0x180006a87  mov     edx, 0Fh
0x180006a8c  jmp     short loc_180006AE6
0x180006a8e  lea     rdx, a500InternalSer; "500 Internal Server Error"
0x180006a95  call    ?bSendResponseToClient@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBDK1K1@Z; bSendResponseToClient(_EXTENSION_CONTROL_BLOCK *,char const *,ulong,char const *,ulong,char const *)
0x180006a9a  test    eax, eax
0x180006a9c  jz      short loc_180006AC2
0x180006a9e  mov     dword ptr [r15+10h], 1F4h
0x180006aa6  mov     rcx, cs:WPP_GLOBAL_Control
0x180006aad  cmp     rcx, rbp
0x180006ab0  jz      short loc_180006B07
0x180006ab2  test    dword ptr [rcx+1Ch], 400h
0x180006ab9  jz      short loc_180006B07
0x180006abb  mov     edx, 10h
0x180006ac0  jmp     short loc_180006A4B
0x180006ac2  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180006ac7  mov     ebx, eax
0x180006ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ad0  cmp     rcx, rbp
0x180006ad3  jz      short loc_180006B07
0x180006ad5  test    byte ptr [rcx+1Ch], 1
0x180006ad9  jz      short loc_180006B07
0x180006adb  call    cs:__imp_GetLastError
0x180006ae1  mov     edx, 11h
0x180006ae6  mov     rcx, cs:WPP_GLOBAL_Control
0x180006aed  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180006af4  mov     r9d, eax
0x180006af7  mov     rcx, [rcx+10h]
0x180006afb  call    WPP_SF_d
0x180006b00  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b07  test    rdi, rdi
0x180006b0a  jz      short loc_180006B1C
0x180006b0c  mov     rcx, rdi; Block
0x180006b0f  call    cs:__imp_free
0x180006b15  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b1c  test    ebx, ebx
0x180006b1e  jz      short loc_180006B8D
0x180006b20  jmp     short loc_180006B62
0x180006b22  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b29  lea     rbp, WPP_GLOBAL_Control
0x180006b30  cmp     rcx, rbp
0x180006b33  jz      short loc_180006B8D
0x180006b35  test    byte ptr [rcx+1Ch], 1
0x180006b39  jz      short loc_180006B62
0x180006b3b  mov     rcx, [rcx+10h]
0x180006b3f  lea     r9, aHrwriterespons; "HrWriteResponse(): Failed to get envelo"...
0x180006b46  mov     edx, 0Dh
0x180006b4b  mov     [rsp+178h+var_158], eax
0x180006b4f  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180006b56  call    WPP_SF_sd
0x180006b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b62  cmp     rcx, rbp
0x180006b65  jz      short loc_180006B8D
0x180006b67  test    byte ptr [rcx+1Ch], 1
0x180006b6b  jz      short loc_180006B8D
0x180006b6d  mov     rcx, [rcx+10h]
0x180006b71  lea     r9, aHrwriterespons_0; "HrWriteResponse(): Exiting"
0x180006b78  mov     edx, 12h
0x180006b7d  mov     [rsp+178h+var_158], ebx
0x180006b81  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180006b88  call    WPP_SF_sd
0x180006b8d  mov     eax, ebx
0x180006b8f  mov     rcx, [rsp+178h+var_38]
0x180006b97  xor     rcx, rsp; StackCookie
0x180006b9a  call    __security_check_cookie
0x180006b9f  lea     r11, [rsp+178h+var_28]
0x180006ba7  mov     rbx, [r11+40h]
0x180006bab  mov     rbp, [r11+48h]
0x180006baf  mov     rsp, r11
0x180006bb2  pop     r15
0x180006bb4  pop     r14
0x180006bb6  pop     r12
0x180006bb8  pop     rdi
0x180006bb9  pop     rsi
0x180006bba  retn
```
