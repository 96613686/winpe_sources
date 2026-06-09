# HrProcessRegistryXML(IXMLDOMElement *,ulong,void *,IXWizard *)

- ea: `0x180014248`
- end: `0x18001471c`
- name: `?HrProcessRegistryXML@@YAJPEAUIXMLDOMElement@@KPEAXPEAUIXWizard@@@Z`
- size: `1236`
- prototype: `__int64 __fastcall(struct IXMLDOMElement *, unsigned int, void *, struct IXWizard *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180014f08`

## callees

- `0x180004370`
- `0x18000addc`
- `0x18000ae04`
- `0x18000bf70`
- `0x18000e4ec`
- `0x180013994`
- `0x180014248`
- `0x18001516c`
- `0x18001a27c`
- `0x18001a2cc`
- `0x18001a308`
- `0x18001a4b4`
- `0x180034010`

## import_xrefs

- `msvcrt!wcstoul` at `0x1800143ed`
- `msvcrt!wcstoul` at `0x1800143ed`
- `msvcrt!_wcsicmp` at `0x1800142e1`
- `msvcrt!_wcsicmp` at `0x180014362`
- `msvcrt!_wcsicmp` at `0x180014387`
- `msvcrt!_wcsicmp` at `0x18001446d`
- `msvcrt!_wcsicmp` at `0x1800142e1`
- `msvcrt!_wcsicmp` at `0x180014362`
- `msvcrt!_wcsicmp` at `0x180014387`
- `msvcrt!_wcsicmp` at `0x18001446d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180014543`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180014683`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180014543`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180014683`
- `OLEAUT32!__imp_SysFreeString` at `0x1800142ff`
- `OLEAUT32!__imp_SysFreeString` at `0x180014396`
- `OLEAUT32!__imp_SysFreeString` at `0x180014409`
- `OLEAUT32!__imp_SysFreeString` at `0x180014482`
- `OLEAUT32!__imp_SysFreeString` at `0x1800142ff`
- `OLEAUT32!__imp_SysFreeString` at `0x180014396`
- `OLEAUT32!__imp_SysFreeString` at `0x180014409`
- `OLEAUT32!__imp_SysFreeString` at `0x180014482`

## string_xrefs

- `0x180014380`: `remove`
- `0x180014422`: `unregisterfromCOM`
- `0x180014679`: `  </registryKeys>\n`
- `0x1800146ad`: `  </registryKeys>\n`
- `0x180014539`: `  <registryKeys>\n`
- `0x18001456d`: `  <registryKeys>\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HrProcessRegistryXML(struct IXMLDOMElement *a1, int a2, void *a3, struct IXWizard *a4)
{
  int NamedAttributeValue; // eax
  unsigned int v6; // edi
  int v7; // esi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  wchar_t *v11; // rbx
  unsigned int v12; // r14d
  unsigned int v13; // r13d
  unsigned int v14; // esi
  int v15; // r12d
  int v16; // eax
  int v17; // eax
  char LastErrorHRESULT; // al
  int v19; // esi
  bool v20; // zf
  unsigned int v21; // eax
  PVOID *v22; // rcx
  char v23; // al
  unsigned int v24; // [rsp+58h] [rbp-19h]
  unsigned int v25; // [rsp+5Ch] [rbp-15h]
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp-11h] BYREF
  int v27; // [rsp+64h] [rbp-Dh]
  wchar_t *String2; // [rsp+68h] [rbp-9h] BYREF
  struct IXMLDOMElement *v29; // [rsp+70h] [rbp-1h] BYREF
  _BYTE v30[80]; // [rsp+78h] [rbp+7h] BYREF

  String2 = 0;
  NumberOfBytesWritten = 0;
  NamedAttributeValue = HrGetNamedAttributeValue(a1, L"onerror", &String2);
  v6 = NamedAttributeValue;
  if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
        (unsigned int)NamedAttributeValue);
    return v6;
  }
  v27 = _wcsicmp(L"ignore", String2);
  v6 = 1;
  v25 = (v27 == 0) + 1;
  SysFreeString(String2);
  v7 = HrGetNamedAttributeValue(a1, L"action", &String2);
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return (unsigned int)v7;
    v9 = 47;
LABEL_9:
    WPP_SF_d(v8[2], v9, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids, (unsigned int)v7);
    return (unsigned int)v7;
  }
  v11 = String2;
  if ( _wcsicmp(L"image", String2) )
  {
    v12 = 2;
    if ( !_wcsicmp(L"remove", v11) )
      v12 = 3;
  }
  else
  {
    v12 = 1;
  }
  SysFreeString(v11);
  v7 = HrGetNamedAttributeValue(a1, L"behavior", &String2);
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return (unsigned int)v7;
    v9 = 48;
    goto LABEL_9;
  }
  v13 = 0;
  if ( !v7 )
  {
    v13 = wcstoul(String2, 0, 16);
    if ( (_WORD)v13 == 0xBACE )
      v13 <<= 16;
  }
  SysFreeString(String2);
  if ( v12 == 1 || (v14 = 0, v24 = 0, v12 == 3) )
  {
    v7 = HrGetNamedAttributeValue(a1, L"unregisterfromCOM", &String2);
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        return (unsigned int)v7;
      v9 = 49;
      goto LABEL_9;
    }
    v14 = _wcsicmp(L"yes", String2) == 0;
    v24 = v14;
    SysFreeString(String2);
  }
  v15 = 0;
  if ( v12 == 1 )
  {
    v16 = HrRemoveAllXWizardComponentsFromRegistry(v14, v25, (__int64 *)a4);
    if ( v16 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
          (unsigned int)v16);
      v17 = HrForceRemoveAllWizardComponents(a4);
      v7 = v17;
      if ( v17 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
            (unsigned int)v17);
        if ( v27 )
          return (unsigned int)v7;
        v15 = 1;
      }
    }
  }
  if ( a3
    && !WriteFile(a3, "  <registryKeys>\r\n", 0x12u, &NumberOfBytesWritten, 0)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    LastErrorHRESULT = GetLastErrorHRESULT();
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      (unsigned int)&WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
      (unsigned int)"  <registryKeys>\r\n",
      LastErrorHRESULT);
  }
  CTagEnum::CTagEnum((CTagEnum *)v30, a1);
  v29 = 0;
  v19 = CTagEnum::HrNext((CTagEnum *)v30, &v29);
  if ( !v19 )
  {
    while ( 1 )
    {
      v19 = HrProcessRegistryComponentXML(0, v29, v25, v12, v13, v24, a2, a3, a4);
      ((void (__fastcall *)(struct IXMLDOMElement *))v29->lpVtbl->Release)(v29);
      if ( v19 == 1 )
        break;
      v20 = v19 == 0;
      if ( v19 >= 0 )
        goto LABEL_49;
LABEL_50:
      if ( !v20 )
        goto LABEL_51;
    }
    v15 = 1;
LABEL_49:
    v19 = CTagEnum::HrNext((CTagEnum *)v30, &v29);
    v20 = v19 == 0;
    goto LABEL_50;
  }
LABEL_51:
  v21 = 0;
  if ( v19 != 1 )
    v21 = v19;
  if ( !v15 )
  {
    v6 = v21;
    goto LABEL_58;
  }
  v22 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids);
LABEL_58:
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
    goto LABEL_65;
  if ( WriteFile(a3, "  </registryKeys>\r\n", 0x13u, &NumberOfBytesWritten, 0) )
  {
LABEL_64:
    v22 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_65;
  }
  v22 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v23 = GetLastErrorHRESULT();
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        (unsigned int)&WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
        (unsigned int)"  </registryKeys>\r\n",
        v23);
      goto LABEL_64;
    }
LABEL_65:
    if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 0x10) != 0 )
      WPP_SF_d(v22[2], 55, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids, v6);
  }
  CTagEnum::~CTagEnum((CTagEnum *)v30);
  return v6;
}

```

## disassembly

```asm
0x180014248  mov     rax, rsp
0x18001424b  mov     [rax+8], rbx
0x18001424f  mov     [rax+20h], r9
0x180014253  mov     [rax+18h], r8
0x180014257  mov     [rax+10h], edx
0x18001425a  push    rbp
0x18001425b  push    rsi
0x18001425c  push    rdi
0x18001425d  push    r12
0x18001425f  push    r13
0x180014261  push    r14
0x180014263  push    r15
0x180014265  lea     rbp, [rax-5Fh]
0x180014269  sub     rsp, 90h
0x180014270  mov     r15, rcx
0x180014273  mov     [rbp+57h+String2], 0
0x18001427b  mov     [rbp+57h+NumberOfBytesWritten], 0
0x180014282  lea     r8, [rbp+57h+String2]; unsigned __int16 **
0x180014286  lea     rdx, aOnerror; "onerror"
0x18001428d  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x180014292  mov     edi, eax
0x180014294  test    eax, eax
0x180014296  jns     short loc_1800142D6
0x180014298  lea     rbx, WPP_GLOBAL_Control
0x18001429f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142a6  cmp     rcx, rbx
0x1800142a9  jz      loc_1800146FF
0x1800142af  test    byte ptr [rcx+1Ch], 4
0x1800142b3  jz      loc_1800146FF
0x1800142b9  mov     edx, 2Eh ; '.'
0x1800142be  mov     r9d, eax
0x1800142c1  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x1800142c8  mov     rcx, [rcx+10h]
0x1800142cc  call    WPP_SF_d
0x1800142d1  jmp     loc_1800146FF
0x1800142d6  mov     rdx, [rbp+57h+String2]; String2
0x1800142da  lea     rcx, aIgnore; "ignore"
0x1800142e1  call    cs:__imp__wcsicmp
0x1800142e7  mov     [rbp+57h+var_64], eax
0x1800142ea  xor     ecx, ecx
0x1800142ec  test    eax, eax
0x1800142ee  setz    cl
0x1800142f1  mov     edi, 1
0x1800142f6  add     ecx, edi
0x1800142f8  mov     [rbp+57h+var_6C], ecx
0x1800142fb  mov     rcx, [rbp+57h+String2]; bstrString
0x1800142ff  call    cs:__imp_SysFreeString
0x180014305  lea     r8, [rbp+57h+String2]; unsigned __int16 **
0x180014309  lea     rdx, aAction; "action"
0x180014310  mov     rcx, r15; struct IXMLDOMElement *
0x180014313  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x180014318  mov     esi, eax
0x18001431a  test    eax, eax
0x18001431c  jns     short loc_180014354
0x18001431e  lea     rbx, WPP_GLOBAL_Control
0x180014325  mov     rcx, cs:WPP_GLOBAL_Control
0x18001432c  cmp     rcx, rbx
0x18001432f  jz      short loc_18001434D
0x180014331  test    byte ptr [rcx+1Ch], 4
0x180014335  jz      short loc_18001434D
0x180014337  lea     edx, [rdi+2Eh]
0x18001433a  mov     r9d, esi
0x18001433d  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180014344  mov     rcx, [rcx+10h]
0x180014348  call    WPP_SF_d
0x18001434d  mov     eax, esi
0x18001434f  jmp     loc_180014701
0x180014354  mov     rbx, [rbp+57h+String2]
0x180014358  mov     rdx, rbx; String2
0x18001435b  lea     rcx, aImage; "image"
0x180014362  call    cs:__imp__wcsicmp
0x180014368  mov     r12d, 3
0x18001436e  test    eax, eax
0x180014370  jnz     short loc_180014377
0x180014372  mov     r14d, edi
0x180014375  jmp     short loc_180014393
0x180014377  mov     r14d, 2
0x18001437d  mov     rdx, rbx; String2
0x180014380  lea     rcx, aRemove; "remove"
0x180014387  call    cs:__imp__wcsicmp
0x18001438d  test    eax, eax
0x18001438f  cmovz   r14d, r12d
0x180014393  mov     rcx, rbx; bstrString
0x180014396  call    cs:__imp_SysFreeString
0x18001439c  lea     r8, [rbp+57h+String2]; unsigned __int16 **
0x1800143a0  lea     rdx, aBehavior; "behavior"
0x1800143a7  mov     rcx, r15; struct IXMLDOMElement *
0x1800143aa  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x1800143af  mov     esi, eax
0x1800143b1  test    eax, eax
0x1800143b3  jns     short loc_1800143DC
0x1800143b5  lea     rbx, WPP_GLOBAL_Control
0x1800143bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143c3  cmp     rcx, rbx
0x1800143c6  jz      short loc_18001434D
0x1800143c8  test    byte ptr [rcx+1Ch], 4
0x1800143cc  jz      loc_18001434D
0x1800143d2  mov     edx, 30h ; '0'
0x1800143d7  jmp     loc_18001433A
0x1800143dc  xor     r13d, r13d
0x1800143df  test    esi, esi
0x1800143e1  jnz     short loc_180014405
0x1800143e3  xor     edx, edx; EndPtr
0x1800143e5  lea     r8d, [r13+10h]; Radix
0x1800143e9  mov     rcx, [rbp+57h+String2]; String
0x1800143ed  call    cs:__imp_wcstoul
0x1800143f3  mov     r13d, eax
0x1800143f6  mov     eax, 0BACEh
0x1800143fb  cmp     ax, r13w
0x1800143ff  jnz     short loc_180014405
0x180014401  shl     r13d, 10h
0x180014405  mov     rcx, [rbp+57h+String2]; bstrString
0x180014409  call    cs:__imp_SysFreeString
0x18001440f  cmp     r14d, edi
0x180014412  jz      short loc_18001441E
0x180014414  xor     esi, esi
0x180014416  mov     [rbp+57h+var_70], esi
0x180014419  cmp     r14d, r12d
0x18001441c  jnz     short loc_180014488
0x18001441e  lea     r8, [rbp+57h+String2]; unsigned __int16 **
0x180014422  lea     rdx, aUnregisterfrom; "unregisterfromCOM"
0x180014429  mov     rcx, r15; struct IXMLDOMElement *
0x18001442c  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x180014431  mov     esi, eax
0x180014433  test    eax, eax
0x180014435  jns     short loc_180014462
0x180014437  lea     rbx, WPP_GLOBAL_Control
0x18001443e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014445  cmp     rcx, rbx
0x180014448  jz      loc_18001434D
0x18001444e  test    byte ptr [rcx+1Ch], 4
0x180014452  jz      loc_18001434D
0x180014458  mov     edx, 31h ; '1'
0x18001445d  jmp     loc_18001433A
0x180014462  mov     rdx, [rbp+57h+String2]; String2
0x180014466  lea     rcx, aYes; "yes"
0x18001446d  call    cs:__imp__wcsicmp
0x180014473  xor     esi, esi
0x180014475  test    eax, eax
0x180014477  setz    sil
0x18001447b  mov     [rbp+57h+var_70], esi
0x18001447e  mov     rcx, [rbp+57h+String2]; bstrString
0x180014482  call    cs:__imp_SysFreeString
0x180014488  xor     r12d, r12d
0x18001448b  lea     rbx, WPP_GLOBAL_Control
0x180014492  cmp     r14d, edi
0x180014495  jnz     loc_18001451D
0x18001449b  mov     r8, [rbp+57h+arg_18]
0x18001449f  mov     edx, [rbp+57h+var_6C]
0x1800144a2  mov     ecx, esi
0x1800144a4  call    ?HrRemoveAllXWizardComponentsFromRegistry@@YAJHW4tagXW_XML_ONERROR_TYPE@@PEAUIXWizard@@@Z; HrRemoveAllXWizardComponentsFromRegistry(int,tagXW_XML_ONERROR_TYPE,IXWizard *)
0x1800144a9  test    eax, eax
0x1800144ab  jns     short loc_18001451D
0x1800144ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144b4  cmp     rcx, rbx
0x1800144b7  jz      short loc_1800144D7
0x1800144b9  test    byte ptr [rcx+1Ch], 4
0x1800144bd  jz      short loc_1800144D7
0x1800144bf  lea     edx, [r12+32h]
0x1800144c4  mov     r9d, eax
0x1800144c7  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x1800144ce  mov     rcx, [rcx+10h]
0x1800144d2  call    WPP_SF_d
0x1800144d7  mov     rcx, [rbp+57h+arg_18]; struct IXWizard *
0x1800144db  call    ?HrForceRemoveAllWizardComponents@@YAJPEAUIXWizard@@@Z; HrForceRemoveAllWizardComponents(IXWizard *)
0x1800144e0  mov     esi, eax
0x1800144e2  test    eax, eax
0x1800144e4  jns     short loc_18001451D
0x1800144e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144ed  cmp     rcx, rbx
0x1800144f0  jz      short loc_180014510
0x1800144f2  test    byte ptr [rcx+1Ch], 4
0x1800144f6  jz      short loc_180014510
0x1800144f8  mov     edx, 33h ; '3'
0x1800144fd  mov     r9d, eax
0x180014500  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180014507  mov     rcx, [rcx+10h]
0x18001450b  call    WPP_SF_d
0x180014510  cmp     [rbp+57h+var_64], r12d
0x180014514  jnz     loc_18001434D
0x18001451a  mov     r12d, edi
0x18001451d  mov     rax, [rbp+57h+hFile]
0x180014521  test    rax, rax
0x180014524  jz      short loc_18001458B
0x180014526  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x18001452f  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180014533  mov     r8d, 12h; nNumberOfBytesToWrite
0x180014539  lea     rdx, aRegistrykeys; "  <registryKeys>\r\n"
0x180014540  mov     rcx, rax; hFile
0x180014543  call    cs:__imp_WriteFile
0x180014549  test    eax, eax
0x18001454b  jnz     short loc_18001458B
0x18001454d  mov     rax, cs:WPP_GLOBAL_Control
0x180014554  cmp     rax, rbx
0x180014557  jz      short loc_18001458B
0x180014559  test    byte ptr [rax+1Ch], 4
0x18001455d  jz      short loc_18001458B
0x18001455f  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180014564  mov     edx, 34h ; '4'
0x180014569  mov     dword ptr [rsp+0C0h+lpOverlapped], eax
0x18001456d  lea     r9, aRegistrykeys; "  <registryKeys>\r\n"
0x180014574  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x18001457b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014582  mov     rcx, [rcx+10h]
0x180014586  call    WPP_SF_sD
0x18001458b  mov     rdx, r15; struct IXMLDOMElement *
0x18001458e  lea     rcx, [rbp+57h+var_50]; this
0x180014592  call    ??0CTagEnum@@QEAA@PEAUIXMLDOMElement@@@Z; CTagEnum::CTagEnum(IXMLDOMElement *)
0x180014597  nop
0x180014598  mov     [rbp+57h+var_58], 0
0x1800145a0  lea     rdx, [rbp+57h+var_58]; struct IXMLDOMElement **
0x1800145a4  lea     rcx, [rbp+57h+var_50]; this
0x1800145a8  call    ?HrNext@CTagEnum@@QEAAJPEAPEAUIXMLDOMElement@@@Z; CTagEnum::HrNext(IXMLDOMElement * *)
0x1800145ad  mov     esi, eax
0x1800145af  mov     r15, [rbp+57h+hFile]
0x1800145b3  test    eax, eax
0x1800145b5  jnz     short loc_180014623
0x1800145b7  mov     ebx, [rbp+57h+var_70]
0x1800145ba  mov     rax, [rbp+57h+arg_18]
0x1800145be  mov     [rsp+40h], rax
0x1800145c3  mov     [rsp+0C0h+var_88], r15
0x1800145c8  mov     eax, [rbp+57h+arg_8]
0x1800145cb  mov     dword ptr [rsp+0C0h+var_90], eax
0x1800145cf  mov     [rsp+0C0h+var_98], ebx
0x1800145d3  mov     dword ptr [rsp+0C0h+lpOverlapped], r13d
0x1800145d8  mov     r9d, r14d
0x1800145db  mov     r8d, [rbp+57h+var_6C]
0x1800145df  mov     rdx, [rbp+57h+var_58]
0x1800145e3  xor     ecx, ecx
0x1800145e5  call    ?HrProcessRegistryComponentXML@@YAJPEAUIXMLDOMElement@@0W4tagXW_XML_ONERROR_TYPE@@W4tagXW_XML_ACTION_TYPE@@KHKPEAXPEAUIXWizard@@@Z; HrProcessRegistryComponentXML(IXMLDOMElement *,IXMLDOMElement *,tagXW_XML_ONERROR_TYPE,tagXW_XML_ACTION_TYPE,ulong,int,ulong,void *,IXWizard *)
0x1800145ea  mov     esi, eax
0x1800145ec  mov     rcx, [rbp+57h+var_58]
0x1800145f0  mov     rax, [rcx]
0x1800145f3  mov     rax, [rax+10h]
0x1800145f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145fc  cmp     esi, edi
0x1800145fe  jnz     short loc_180014605
0x180014600  mov     r12d, edi
0x180014603  jmp     short loc_180014609
0x180014605  test    esi, esi
0x180014607  js      short loc_18001461A
0x180014609  lea     rdx, [rbp+57h+var_58]; struct IXMLDOMElement **
0x18001460d  lea     rcx, [rbp+57h+var_50]; this
0x180014611  call    ?HrNext@CTagEnum@@QEAAJPEAPEAUIXMLDOMElement@@@Z; CTagEnum::HrNext(IXMLDOMElement * *)
0x180014616  mov     esi, eax
0x180014618  test    eax, eax
0x18001461a  jz      short loc_1800145BA
0x18001461c  lea     rbx, WPP_GLOBAL_Control
0x180014623  xor     eax, eax
0x180014625  cmp     esi, edi
0x180014627  cmovnz  eax, esi
0x18001462a  test    r12d, r12d
0x18001462d  jz      short loc_180014658
0x18001462f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014636  cmp     rcx, rbx
0x180014639  jz      short loc_180014661
0x18001463b  test    byte ptr [rcx+1Ch], 10h
0x18001463f  jz      short loc_180014661
0x180014641  mov     edx, 35h ; '5'
0x180014646  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x18001464d  mov     rcx, [rcx+10h]
0x180014651  call    WPP_SF_
0x180014656  jmp     short loc_18001465A
0x180014658  mov     edi, eax
0x18001465a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014661  test    r15, r15
0x180014664  jz      short loc_1800146D2
0x180014666  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x18001466f  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180014673  mov     r8d, 13h; nNumberOfBytesToWrite
0x180014679  lea     rdx, aRegistrykeys_0; "  </registryKeys>\r\n"
0x180014680  mov     rcx, r15; hFile
0x180014683  call    cs:__imp_WriteFile
0x180014689  test    eax, eax
0x18001468b  jnz     short loc_1800146CB
0x18001468d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014694  cmp     rcx, rbx
0x180014697  jz      short loc_1800146F6
0x180014699  test    byte ptr [rcx+1Ch], 4
0x18001469d  jz      short loc_1800146D2
0x18001469f  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x1800146a4  mov     edx, 36h ; '6'
0x1800146a9  mov     dword ptr [rsp+0C0h+lpOverlapped], eax
0x1800146ad  lea     r9, aRegistrykeys_0; "  </registryKeys>\r\n"
0x1800146b4  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x1800146bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146c2  mov     rcx, [rcx+10h]
0x1800146c6  call    WPP_SF_sD
0x1800146cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146d2  cmp     rcx, rbx
0x1800146d5  jz      short loc_1800146F6
0x1800146d7  test    byte ptr [rcx+1Ch], 10h
0x1800146db  jz      short loc_1800146F6
0x1800146dd  mov     edx, 37h ; '7'
0x1800146e2  mov     r9d, edi
0x1800146e5  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x1800146ec  mov     rcx, [rcx+10h]
0x1800146f0  call    WPP_SF_d
0x1800146f5  nop
0x1800146f6  lea     rcx, [rbp+57h+var_50]; this
  ... truncated ...
```
