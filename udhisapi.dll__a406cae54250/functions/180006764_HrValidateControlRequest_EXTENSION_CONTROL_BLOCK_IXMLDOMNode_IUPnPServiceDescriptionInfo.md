# HrValidateControlRequest(_EXTENSION_CONTROL_BLOCK *,IXMLDOMNode *,IUPnPServiceDescriptionInfo *)

- ea: `0x180006764`
- end: `0x18000685f`
- name: `?HrValidateControlRequest@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@PEAUIXMLDOMNode@@PEAUIUPnPServiceDescriptionInfo@@@Z`
- size: `251`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *, struct IXMLDOMNode *, struct IUPnPServiceDescriptionInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000512c`

## callees

- `0x1800038ec`
- `0x180006764`
- `0x1800083f0`
- `0x180009070`
- `0x180009420`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800067c9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800067c9`

## pseudocode

```c
__int64 __fastcall HrValidateControlRequest(
        struct _EXTENSION_CONTROL_BLOCK *a1,
        struct IXMLDOMNode *a2,
        struct IUPnPServiceDescriptionInfo *a3)
{
  int SOAPActionHeader; // ebx
  void *v7; // rdi
  _QWORD *v8; // rcx
  void *Block; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 || !a1 || !a3 )
    goto LABEL_12;
  SOAPActionHeader = HrValidateContentType(a1);
  if ( SOAPActionHeader >= 0 )
  {
    Block = 0;
    SOAPActionHeader = HrGetSOAPActionHeader(a1, (unsigned __int16 **)&Block);
    if ( SOAPActionHeader >= 0 )
    {
      v7 = Block;
      if ( Block )
      {
        SOAPActionHeader = HrValidateSOAPStructure(a2, a3, (unsigned __int16 *)Block);
        free(v7);
      }
      else
      {
        SOAPActionHeader = -2147467259;
      }
    }
  }
  if ( SOAPActionHeader != -2147467259 )
  {
    if ( !SOAPActionHeader )
      return (unsigned int)SOAPActionHeader;
  }
  else
  {
LABEL_12:
    SOAPActionHeader = -2147180027;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
        (unsigned int)"HrValidateSOAPRequest(): Exiting",
        SOAPActionHeader);
      v8 = WPP_GLOBAL_Control;
    }
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
      WPP_SF_sd(
        v8[2],
        75,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (unsigned int)"HrValidateControlRequest(): Exiting",
        SOAPActionHeader);
  }
  return (unsigned int)SOAPActionHeader;
}

```

## disassembly

```asm
0x180006764  push    rbx
0x180006766  push    rbp
0x180006767  push    rsi
0x180006768  push    rdi
0x180006769  sub     rsp, 38h
0x18000676d  mov     rsi, r8
0x180006770  mov     rbp, rdx
0x180006773  mov     rdi, rcx
0x180006776  test    rdx, rdx
0x180006779  jz      short loc_1800067E4
0x18000677b  test    rcx, rcx
0x18000677e  jz      short loc_1800067E4
0x180006780  test    r8, r8
0x180006783  jz      short loc_1800067E4
0x180006785  call    ?HrValidateContentType@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@@Z; HrValidateContentType(_EXTENSION_CONTROL_BLOCK *)
0x18000678a  mov     ebx, eax
0x18000678c  test    eax, eax
0x18000678e  js      short loc_1800067D6
0x180006790  lea     rdx, [rsp+58h+Block]; unsigned __int16 **
0x180006795  mov     [rsp+58h+Block], 0
0x18000679e  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x1800067a1  call    ?HrGetSOAPActionHeader@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@PEAPEAG@Z; HrGetSOAPActionHeader(_EXTENSION_CONTROL_BLOCK *,ushort * *)
0x1800067a6  mov     ebx, eax
0x1800067a8  test    eax, eax
0x1800067aa  js      short loc_1800067D6
0x1800067ac  mov     rdi, [rsp+58h+Block]
0x1800067b1  test    rdi, rdi
0x1800067b4  jz      short loc_1800067D1
0x1800067b6  mov     r8, rdi; unsigned __int16 *
0x1800067b9  mov     rdx, rsi; struct IUPnPServiceDescriptionInfo *
0x1800067bc  mov     rcx, rbp; struct IXMLDOMNode *
0x1800067bf  call    ?HrValidateSOAPStructure@@YAJPEAUIXMLDOMNode@@PEAUIUPnPServiceDescriptionInfo@@PEAG@Z; HrValidateSOAPStructure(IXMLDOMNode *,IUPnPServiceDescriptionInfo *,ushort *)
0x1800067c4  mov     rcx, rdi; Block
0x1800067c7  mov     ebx, eax
0x1800067c9  call    cs:__imp_free
0x1800067cf  jmp     short loc_1800067D6
0x1800067d1  mov     ebx, 80004005h
0x1800067d6  cmp     ebx, 80004005h
0x1800067dc  jz      short loc_1800067E4
0x1800067de  test    ebx, ebx
0x1800067e0  jz      short loc_180006854
0x1800067e2  jmp     short loc_1800067E9
0x1800067e4  mov     ebx, 8004A205h
0x1800067e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067f0  lea     rdi, WPP_GLOBAL_Control
0x1800067f7  cmp     rcx, rdi
0x1800067fa  jz      short loc_180006854
0x1800067fc  test    byte ptr [rcx+1Ch], 1
0x180006800  jz      short loc_180006829
0x180006802  mov     rcx, [rcx+10h]
0x180006806  lea     r9, aHrvalidatesoap_1; "HrValidateSOAPRequest(): Exiting"
0x18000680d  mov     edx, 3Bh ; ';'
0x180006812  mov     [rsp+58h+var_38], ebx
0x180006816  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x18000681d  call    WPP_SF_sd
0x180006822  mov     rcx, cs:WPP_GLOBAL_Control
0x180006829  cmp     rcx, rdi
0x18000682c  jz      short loc_180006854
0x18000682e  test    byte ptr [rcx+1Ch], 1
0x180006832  jz      short loc_180006854
0x180006834  mov     rcx, [rcx+10h]
0x180006838  lea     r9, aHrvalidatecont; "HrValidateControlRequest(): Exiting"
0x18000683f  mov     edx, 4Bh ; 'K'
0x180006844  mov     [rsp+58h+var_38], ebx
0x180006848  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x18000684f  call    WPP_SF_sd
0x180006854  mov     eax, ebx
0x180006856  add     rsp, 38h
0x18000685a  pop     rdi
0x18000685b  pop     rsi
0x18000685c  pop     rbp
0x18000685d  pop     rbx
0x18000685e  retn
```
