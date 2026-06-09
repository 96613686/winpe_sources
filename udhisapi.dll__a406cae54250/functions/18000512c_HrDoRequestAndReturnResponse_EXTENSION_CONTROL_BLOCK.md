# HrDoRequestAndReturnResponse(_EXTENSION_CONTROL_BLOCK *)

- ea: `0x18000512c`
- end: `0x180005579`
- name: `?HrDoRequestAndReturnResponse@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@@Z`
- size: `1101`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180003aa0`

## callees

- `0x1800038ec`
- `0x180003960`
- `0x1800039d4`
- `0x180004ba4`
- `0x180004c94`
- `0x18000512c`
- `0x180005580`
- `0x180005674`
- `0x180005b68`
- `0x180005e60`
- `0x1800063e0`
- `0x180006764`
- `0x180006cd0`
- `0x18000b608`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005302`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005311`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005320`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005302`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005311`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005320`
- `OLEAUT32!__imp_SysFreeString` at `0x18000536a`
- `OLEAUT32!__imp_SysFreeString` at `0x180005392`
- `OLEAUT32!__imp_SysFreeString` at `0x1800054b2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000536a`
- `OLEAUT32!__imp_SysFreeString` at `0x180005392`
- `OLEAUT32!__imp_SysFreeString` at `0x1800054b2`

## string_xrefs

- `0x1800052b3`: `HTTP_USERAGENT`
- `0x1800053c5`: `HrDoRequestAndReturnResponse(): Failed to get service desc info interface`

## pseudocode

```c
__int64 __fastcall HrDoRequestAndReturnResponse(struct _EXTENSION_CONTROL_BLOCK *a1)
{
  char *lpszQueryString; // rcx
  const unsigned __int16 *v3; // rdx
  int v4; // ebx
  const unsigned __int16 *v5; // r8
  int v6; // eax
  _QWORD *v7; // rcx
  const unsigned __int16 *v8; // rbx
  const unsigned __int16 *v9; // rsi
  __int64 v11; // [rsp+30h] [rbp-59h] BYREF
  BSTR bstrString[2]; // [rsp+38h] [rbp-51h] BYREF
  __int128 v13; // [rsp+48h] [rbp-41h] BYREF
  __int128 v14; // [rsp+58h] [rbp-31h]
  void *Block[2]; // [rsp+68h] [rbp-21h] BYREF
  char *v16; // [rsp+78h] [rbp-11h] BYREF
  __int128 v17; // [rsp+80h] [rbp-9h] BYREF
  __int64 v18; // [rsp+90h] [rbp+7h]
  BSTR v19[9]; // [rsp+98h] [rbp+Fh] BYREF
  int v20; // [rsp+F0h] [rbp+67h] BYREF
  struct IUPnPAutomationProxy *v21; // [rsp+F8h] [rbp+6Fh] BYREF
  struct IUPnPServiceDescriptionInfo *v22; // [rsp+100h] [rbp+77h] BYREF
  struct IXMLDOMNode *v23; // [rsp+108h] [rbp+7Fh] BYREF

  v23 = 0;
  lpszQueryString = a1->lpszQueryString;
  v21 = 0;
  v22 = 0;
  v4 = HrParseControlQueryString(lpszQueryString, &v21);
  if ( v4 < 0 )
    goto LABEL_33;
  v6 = (**(__int64 (__fastcall ***)(struct IUPnPAutomationProxy *, GUID *, struct IUPnPServiceDescriptionInfo **))v21)(
         v21,
         &IID_IUPnPServiceDescriptionInfo,
         &v22);
  v4 = v6;
  if ( v6 >= 0 )
  {
    v4 = HrReadRequest(a1, &v23);
    if ( v4 >= 0 )
    {
      v4 = HrValidateControlRequest(a1, v23, v22);
      if ( v4 >= 0 )
      {
        *(_OWORD *)v19 = 0;
        v4 = HrParseSOAPRequest(v23, (struct tagUPNP_SOAP_REQUEST *)v19);
        if ( v4 >= 0 )
        {
          v17 = 0;
          v18 = 0;
          v4 = HrDeserializeSOAPRequest((struct tagUPNP_SOAP_REQUEST *)v19, v22, (struct tagUPNP_CONTROL_REQUEST *)&v17);
          if ( v4 < 0 )
          {
LABEL_26:
            if ( v19[0] )
              SysFreeString(v19[0]);
            if ( v19[1] )
              (*(void (__fastcall **)(BSTR))(*(_QWORD *)v19[1] + 16LL))(v19[1]);
            goto LABEL_33;
          }
          v20 = 0;
          *(_OWORD *)bstrString = 0;
          v11 = 0;
          v13 = 0;
          v14 = 0;
          v4 = (**(__int64 (__fastcall ***)(struct IUPnPAutomationProxy *, GUID *, __int64 *))v21)(
                 v21,
                 &IID_IUPnPSupportEndpointInfo,
                 &v11);
          if ( v4 >= 0 )
          {
            v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v11 + 24LL))(v11, v17, &v20);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            v11 = 0;
            if ( v4 >= 0 )
            {
              if ( !v20 )
              {
                v4 = HrExecuteRequest(
                       v21,
                       (struct tagUPNP_CONTROL_REQUEST *)&v17,
                       (struct tagUPNP_CONTROL_RESPONSE *)bstrString,
                       0);
LABEL_21:
                if ( v4 >= 0 )
                {
                  v4 = HrSerializeAndSendResponse(
                         a1,
                         v21,
                         (struct tagUPNP_CONTROL_REQUEST *)&v17,
                         (struct tagUPNP_CONTROL_RESPONSE *)bstrString,
                         v22);
                  if ( bstrString[0] )
                  {
                    SysFreeString(bstrString[0]);
                    bstrString[0] = 0;
                  }
                  CleanupResponseData((union tagUPNP_CONTROL_RESPONSE_DATA *)&v13, (int)bstrString[1]);
                }
                goto LABEL_25;
              }
              v16 = 0;
              *(_OWORD *)Block = 0;
              v4 = HrCopyServerVariable(a1, "REMOTE_ADDR", (char **)Block);
              if ( !v4 )
              {
                v4 = HrCopyServerVariable(a1, "HTTP_USERAGENT", (char **)&Block[1]);
                if ( !v4 )
                {
                  HrCopyServerVariable(a1, "FriendlyName.dlna.org", &v16);
LABEL_14:
                  v4 = HrExecuteRequest(
                         v21,
                         (struct tagUPNP_CONTROL_REQUEST *)&v17,
                         (struct tagUPNP_CONTROL_RESPONSE *)bstrString,
                         (struct tagUPNP_ENDPOINT_INFO *)Block);
                  if ( Block[0] )
                    free(Block[0]);
                  if ( Block[1] )
                    free(Block[1]);
                  if ( v16 )
                    free(v16);
                  goto LABEL_21;
                }
              }
              if ( v4 >= 0 )
                goto LABEL_14;
            }
          }
LABEL_25:
          CleanupDeserializedRequest((struct tagUPNP_CONTROL_REQUEST *)&v17);
          goto LABEL_26;
        }
      }
    }
LABEL_33:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_34;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      101,
      (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
      (unsigned int)"HrDoRequestAndReturnResponse(): Failed to get service desc info interface",
      v6);
    goto LABEL_33;
  }
LABEL_34:
  if ( (unsigned int)(v4 + 2147220985) <= 1 || v4 == -2147220973 )
  {
    *(_OWORD *)bstrString = 0;
    v13 = 0;
    v14 = 0;
    if ( v4 == -2147220985 )
    {
      v8 = L"401";
      v9 = L"Invalid Action";
    }
    else if ( v4 == -2147220984 )
    {
      v8 = L"402";
      v9 = L"Invalid Args";
    }
    else
    {
      v8 = L"404";
      v9 = L"Invalid Var";
    }
    if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x400) != 0 )
      WPP_SF_SS(v7[2], 102, (_DWORD)v5, (_DWORD)v8, (__int64)v9);
    LODWORD(bstrString[1]) = 0;
    v4 = HrBuildFaultResponse((union tagUPNP_CONTROL_RESPONSE_DATA *)&v13, v3, v5, v8, v9);
    if ( v4 >= 0 )
      v4 = HrSerializeAndSendResponse(a1, v21, 0, (struct tagUPNP_CONTROL_RESPONSE *)bstrString, v22);
    if ( bstrString[0] )
    {
      SysFreeString(bstrString[0]);
      bstrString[0] = 0;
    }
    CleanupResponseData((union tagUPNP_CONTROL_RESPONSE_DATA *)&v13, (int)bstrString[1]);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(struct IUPnPServiceDescriptionInfo *))(*(_QWORD *)v22 + 16LL))(v22);
    v7 = WPP_GLOBAL_Control;
    v22 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(struct IUPnPAutomationProxy *))(*(_QWORD *)v21 + 16LL))(v21);
    v7 = WPP_GLOBAL_Control;
    v21 = 0;
  }
  if ( v23 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
    v7 = WPP_GLOBAL_Control;
    v23 = 0;
  }
  if ( v4 && v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
    WPP_SF_sd(
      v7[2],
      103,
      (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
      (unsigned int)"HrDoRequestAndReturnResponse(): Exiting",
      v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000512c  push    rbp
0x18000512e  push    rbx
0x18000512f  push    rsi
0x180005130  push    rdi
0x180005131  push    r14
0x180005133  push    r15
0x180005135  lea     rbp, [rsp-2Fh]
0x18000513a  sub     rsp, 0B8h
0x180005141  xor     r14d, r14d
0x180005144  lea     rdx, [rbp+57h+arg_8]; struct IUPnPAutomationProxy **
0x180005148  mov     rdi, rcx
0x18000514b  mov     [rbp+57h+arg_18], r14
0x18000514f  mov     rcx, [rcx+70h]; char *
0x180005153  mov     [rbp+57h+arg_8], r14
0x180005157  mov     [rbp+57h+arg_10], r14
0x18000515b  call    ?HrParseControlQueryString@@YAJPEADPEAPEAUIUPnPAutomationProxy@@@Z; HrParseControlQueryString(char *,IUPnPAutomationProxy * *)
0x180005160  lea     r15, WPP_GLOBAL_Control
0x180005167  mov     ebx, eax
0x180005169  test    eax, eax
0x18000516b  js      loc_1800053E1
0x180005171  mov     rcx, [rbp+57h+arg_8]
0x180005175  lea     r8, [rbp+57h+arg_10]
0x180005179  lea     rdx, IID_IUPnPServiceDescriptionInfo
0x180005180  mov     rax, [rcx]
0x180005183  mov     rax, [rax]
0x180005186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000518b  mov     ebx, eax
0x18000518d  test    eax, eax
0x18000518f  js      loc_1800053AF
0x180005195  lea     rdx, [rbp+57h+arg_18]; struct IXMLDOMNode **
0x180005199  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x18000519c  call    ?HrReadRequest@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@PEAPEAUIXMLDOMNode@@@Z; HrReadRequest(_EXTENSION_CONTROL_BLOCK *,IXMLDOMNode * *)
0x1800051a1  mov     ebx, eax
0x1800051a3  test    eax, eax
0x1800051a5  js      loc_1800053E1
0x1800051ab  mov     r8, [rbp+57h+arg_10]; struct IUPnPServiceDescriptionInfo *
0x1800051af  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x1800051b2  mov     rdx, [rbp+57h+arg_18]; struct IXMLDOMNode *
0x1800051b6  call    ?HrValidateControlRequest@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@PEAUIXMLDOMNode@@PEAUIUPnPServiceDescriptionInfo@@@Z; HrValidateControlRequest(_EXTENSION_CONTROL_BLOCK *,IXMLDOMNode *,IUPnPServiceDescriptionInfo *)
0x1800051bb  mov     ebx, eax
0x1800051bd  test    eax, eax
0x1800051bf  js      loc_1800053E1
0x1800051c5  mov     rcx, [rbp+57h+arg_18]; struct IXMLDOMNode *
0x1800051c9  lea     rdx, [rbp+57h+var_48]; struct tagUPNP_SOAP_REQUEST *
0x1800051cd  xorps   xmm0, xmm0
0x1800051d0  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x1800051d4  call    ?HrParseSOAPRequest@@YAJPEAUIXMLDOMNode@@PEAUtagUPNP_SOAP_REQUEST@@@Z; HrParseSOAPRequest(IXMLDOMNode *,tagUPNP_SOAP_REQUEST *)
0x1800051d9  mov     ebx, eax
0x1800051db  test    eax, eax
0x1800051dd  js      loc_1800053E1
0x1800051e3  mov     rdx, [rbp+57h+arg_10]; struct IUPnPServiceDescriptionInfo *
0x1800051e7  lea     r8, [rbp+57h+var_60]; struct tagUPNP_CONTROL_REQUEST *
0x1800051eb  xorps   xmm0, xmm0
0x1800051ee  lea     rcx, [rbp+57h+var_48]; struct tagUPNP_SOAP_REQUEST *
0x1800051f2  xor     eax, eax
0x1800051f4  movups  [rbp+57h+var_60], xmm0
0x1800051f8  mov     [rbp+57h+var_50], rax
0x1800051fc  call    ?HrDeserializeSOAPRequest@@YAJPEAUtagUPNP_SOAP_REQUEST@@PEAUIUPnPServiceDescriptionInfo@@PEAUtagUPNP_CONTROL_REQUEST@@@Z; HrDeserializeSOAPRequest(tagUPNP_SOAP_REQUEST *,IUPnPServiceDescriptionInfo *,tagUPNP_CONTROL_REQUEST *)
0x180005201  mov     ebx, eax
0x180005203  test    eax, eax
0x180005205  js      loc_180005389
0x18000520b  mov     rcx, [rbp+57h+arg_8]
0x18000520f  lea     r8, [rbp+57h+var_B0]
0x180005213  xorps   xmm0, xmm0
0x180005216  mov     [rbp+57h+arg_0], r14d
0x18000521a  movups  xmmword ptr [rbp+57h+bstrString], xmm0
0x18000521e  mov     [rbp+57h+var_B0], r14
0x180005222  lea     rdx, IID_IUPnPSupportEndpointInfo
0x180005229  movups  [rbp+57h+var_98], xmm0
0x18000522d  movups  [rbp+57h+var_88], xmm0
0x180005231  mov     rax, [rcx]
0x180005234  mov     rax, [rax]
0x180005237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000523c  mov     ebx, eax
0x18000523e  test    eax, eax
0x180005240  js      loc_180005380
0x180005246  mov     rcx, [rbp+57h+var_B0]
0x18000524a  lea     r8, [rbp+57h+arg_0]
0x18000524e  mov     rdx, qword ptr [rbp+57h+var_60]
0x180005252  mov     rax, [rcx]
0x180005255  mov     rax, [rax+18h]
0x180005259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000525e  mov     rcx, [rbp+57h+var_B0]
0x180005262  mov     ebx, eax
0x180005264  mov     rax, [rcx]
0x180005267  mov     rax, [rax+10h]
0x18000526b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005270  mov     [rbp+57h+var_B0], r14
0x180005274  test    ebx, ebx
0x180005276  js      loc_180005380
0x18000527c  cmp     [rbp+57h+arg_0], r14d
0x180005280  jz      loc_180005328
0x180005286  xorps   xmm0, xmm0
0x180005289  lea     r8, [rbp+57h+Block]; char **
0x18000528d  xor     eax, eax
0x18000528f  lea     rdx, aRemoteAddr; "REMOTE_ADDR"
0x180005296  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x180005299  mov     [rbp+57h+var_68], rax
0x18000529d  movups  xmmword ptr [rbp+57h+Block], xmm0
0x1800052a1  call    ?HrCopyServerVariable@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@PEADPEAPEAD@Z; HrCopyServerVariable(_EXTENSION_CONTROL_BLOCK *,char *,char * *)
0x1800052a6  mov     ebx, eax
0x1800052a8  test    eax, eax
0x1800052aa  jnz     short loc_1800052DA
0x1800052ac  lea     r8, [rbp+57h+Block+8]; char **
0x1800052b0  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x1800052b3  lea     rdx, aHttpUseragent; "HTTP_USERAGENT"
0x1800052ba  call    ?HrCopyServerVariable@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@PEADPEAPEAD@Z; HrCopyServerVariable(_EXTENSION_CONTROL_BLOCK *,char *,char * *)
0x1800052bf  mov     ebx, eax
0x1800052c1  test    eax, eax
0x1800052c3  jnz     short loc_1800052DA
0x1800052c5  lea     r8, [rbp+57h+var_68]; char **
0x1800052c9  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x1800052cc  lea     rdx, aFriendlynameDl; "FriendlyName.dlna.org"
0x1800052d3  call    ?HrCopyServerVariable@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@PEADPEAPEAD@Z; HrCopyServerVariable(_EXTENSION_CONTROL_BLOCK *,char *,char * *)
0x1800052d8  jmp     short loc_1800052E2
0x1800052da  test    ebx, ebx
0x1800052dc  js      loc_180005380
0x1800052e2  mov     rcx, [rbp+57h+arg_8]; struct IUPnPAutomationProxy *
0x1800052e6  lea     r9, [rbp+57h+Block]; struct tagUPNP_ENDPOINT_INFO *
0x1800052ea  lea     r8, [rbp+57h+bstrString]; struct tagUPNP_CONTROL_RESPONSE *
0x1800052ee  lea     rdx, [rbp+57h+var_60]; struct tagUPNP_CONTROL_REQUEST *
0x1800052f2  call    ?HrExecuteRequest@@YAJPEAUIUPnPAutomationProxy@@PEAUtagUPNP_CONTROL_REQUEST@@PEAUtagUPNP_CONTROL_RESPONSE@@PEAUtagUPNP_ENDPOINT_INFO@@@Z; HrExecuteRequest(IUPnPAutomationProxy *,tagUPNP_CONTROL_REQUEST *,tagUPNP_CONTROL_RESPONSE *,tagUPNP_ENDPOINT_INFO *)
0x1800052f7  mov     rcx, [rbp+57h+Block]; Block
0x1800052fb  mov     ebx, eax
0x1800052fd  test    rcx, rcx
0x180005300  jz      short loc_180005308
0x180005302  call    cs:__imp_free
0x180005308  mov     rcx, [rbp+57h+Block+8]; Block
0x18000530c  test    rcx, rcx
0x18000530f  jz      short loc_180005317
0x180005311  call    cs:__imp_free
0x180005317  mov     rcx, [rbp+57h+var_68]; Block
0x18000531b  test    rcx, rcx
0x18000531e  jz      short loc_18000533E
0x180005320  call    cs:__imp_free
0x180005326  jmp     short loc_18000533E
0x180005328  mov     rcx, [rbp+57h+arg_8]; struct IUPnPAutomationProxy *
0x18000532c  lea     r8, [rbp+57h+bstrString]; struct tagUPNP_CONTROL_RESPONSE *
0x180005330  xor     r9d, r9d; struct tagUPNP_ENDPOINT_INFO *
0x180005333  lea     rdx, [rbp+57h+var_60]; struct tagUPNP_CONTROL_REQUEST *
0x180005337  call    ?HrExecuteRequest@@YAJPEAUIUPnPAutomationProxy@@PEAUtagUPNP_CONTROL_REQUEST@@PEAUtagUPNP_CONTROL_RESPONSE@@PEAUtagUPNP_ENDPOINT_INFO@@@Z; HrExecuteRequest(IUPnPAutomationProxy *,tagUPNP_CONTROL_REQUEST *,tagUPNP_CONTROL_RESPONSE *,tagUPNP_ENDPOINT_INFO *)
0x18000533c  mov     ebx, eax
0x18000533e  test    ebx, ebx
0x180005340  js      short loc_180005380
0x180005342  mov     rax, [rbp+57h+arg_10]
0x180005346  lea     r9, [rbp+57h+bstrString]; struct tagUPNP_CONTROL_RESPONSE *
0x18000534a  mov     rdx, [rbp+57h+arg_8]; struct IUPnPAutomationProxy *
0x18000534e  lea     r8, [rbp+57h+var_60]; struct tagUPNP_CONTROL_REQUEST *
0x180005352  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x180005355  mov     [rsp+0E0h+var_C0], rax; struct IUPnPServiceDescriptionInfo *
0x18000535a  call    ?HrSerializeAndSendResponse@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@PEAUIUPnPAutomationProxy@@PEAUtagUPNP_CONTROL_REQUEST@@PEAUtagUPNP_CONTROL_RESPONSE@@PEAUIUPnPServiceDescriptionInfo@@@Z; HrSerializeAndSendResponse(_EXTENSION_CONTROL_BLOCK *,IUPnPAutomationProxy *,tagUPNP_CONTROL_REQUEST *,tagUPNP_CONTROL_RESPONSE *,IUPnPServiceDescriptionInfo *)
0x18000535f  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180005363  mov     ebx, eax
0x180005365  test    rcx, rcx
0x180005368  jz      short loc_180005374
0x18000536a  call    cs:__imp_SysFreeString
0x180005370  mov     [rbp+57h+bstrString], r14
0x180005374  mov     edx, dword ptr [rbp+57h+bstrString+8]; int
0x180005377  lea     rcx, [rbp+57h+var_98]; union tagUPNP_CONTROL_RESPONSE_DATA *
0x18000537b  call    ?CleanupResponseData@@YAXPEATtagUPNP_CONTROL_RESPONSE_DATA@@H@Z; CleanupResponseData(tagUPNP_CONTROL_RESPONSE_DATA *,int)
0x180005380  lea     rcx, [rbp+57h+var_60]; struct tagUPNP_CONTROL_REQUEST *
0x180005384  call    ?CleanupDeserializedRequest@@YAXPEAUtagUPNP_CONTROL_REQUEST@@@Z; CleanupDeserializedRequest(tagUPNP_CONTROL_REQUEST *)
0x180005389  mov     rcx, [rbp+57h+var_48]; bstrString
0x18000538d  test    rcx, rcx
0x180005390  jz      short loc_180005398
0x180005392  call    cs:__imp_SysFreeString
0x180005398  mov     rcx, [rbp+57h+var_48+8]
0x18000539c  test    rcx, rcx
0x18000539f  jz      short loc_1800053E1
0x1800053a1  mov     rax, [rcx]
0x1800053a4  mov     rax, [rax+10h]
0x1800053a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053ad  jmp     short loc_1800053E1
0x1800053af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053b6  cmp     rcx, r15
0x1800053b9  jz      short loc_1800053E8
0x1800053bb  test    byte ptr [rcx+1Ch], 1
0x1800053bf  jz      short loc_1800053E8
0x1800053c1  mov     rcx, [rcx+10h]
0x1800053c5  lea     r9, aHrdorequestand_0; "HrDoRequestAndReturnResponse(): Failed "...
0x1800053cc  mov     edx, 65h ; 'e'
0x1800053d1  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800053d5  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x1800053dc  call    WPP_SF_sd
0x1800053e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053e8  lea     eax, [rbx+7FFBFDF9h]
0x1800053ee  cmp     eax, 1
0x1800053f1  jbe     short loc_1800053FF
0x1800053f3  cmp     ebx, 80040213h
0x1800053f9  jnz     loc_1800054CF
0x1800053ff  xorps   xmm0, xmm0
0x180005402  movups  xmmword ptr [rbp+57h+bstrString], xmm0
0x180005406  movups  [rbp+57h+var_98], xmm0
0x18000540a  movups  [rbp+57h+var_88], xmm0
0x18000540e  cmp     ebx, 80040207h
0x180005414  jnz     short loc_180005426
0x180005416  lea     rbx, a401; "401"
0x18000541d  lea     rsi, aInvalidAction; "Invalid Action"
0x180005424  jmp     short loc_18000544C
0x180005426  cmp     ebx, 80040208h
0x18000542c  jnz     short loc_18000543E
0x18000542e  lea     rbx, a402; "402"
0x180005435  lea     rsi, aInvalidArgs; "Invalid Args"
0x18000543c  jmp     short loc_18000544C
0x18000543e  lea     rbx, a404; "404"
0x180005445  lea     rsi, aInvalidVar; "Invalid Var"
0x18000544c  cmp     rcx, r15
0x18000544f  jz      short loc_180005470
0x180005451  test    dword ptr [rcx+1Ch], 400h
0x180005458  jz      short loc_180005470
0x18000545a  mov     rcx, [rcx+10h]
0x18000545e  mov     edx, 66h ; 'f'
0x180005463  mov     r9, rbx
0x180005466  mov     [rsp+0E0h+var_C0], rsi
0x18000546b  call    WPP_SF_SS
0x180005470  mov     r9, rbx; unsigned __int16 *
0x180005473  mov     dword ptr [rbp+57h+bstrString+8], r14d
0x180005477  lea     rcx, [rbp+57h+var_98]; union tagUPNP_CONTROL_RESPONSE_DATA *
0x18000547b  mov     [rsp+0E0h+var_C0], rsi; unsigned __int16 *
0x180005480  call    ?HrBuildFaultResponse@@YAJPEATtagUPNP_CONTROL_RESPONSE_DATA@@PEBG111@Z; HrBuildFaultResponse(tagUPNP_CONTROL_RESPONSE_DATA *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180005485  mov     ebx, eax
0x180005487  test    eax, eax
0x180005489  js      short loc_1800054A9
0x18000548b  mov     rax, [rbp+57h+arg_10]
0x18000548f  lea     r9, [rbp+57h+bstrString]; struct tagUPNP_CONTROL_RESPONSE *
0x180005493  mov     rdx, [rbp+57h+arg_8]; struct IUPnPAutomationProxy *
0x180005497  xor     r8d, r8d; struct tagUPNP_CONTROL_REQUEST *
0x18000549a  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x18000549d  mov     [rsp+0E0h+var_C0], rax; struct IUPnPServiceDescriptionInfo *
0x1800054a2  call    ?HrSerializeAndSendResponse@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@PEAUIUPnPAutomationProxy@@PEAUtagUPNP_CONTROL_REQUEST@@PEAUtagUPNP_CONTROL_RESPONSE@@PEAUIUPnPServiceDescriptionInfo@@@Z; HrSerializeAndSendResponse(_EXTENSION_CONTROL_BLOCK *,IUPnPAutomationProxy *,tagUPNP_CONTROL_REQUEST *,tagUPNP_CONTROL_RESPONSE *,IUPnPServiceDescriptionInfo *)
0x1800054a7  mov     ebx, eax
0x1800054a9  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800054ad  test    rcx, rcx
0x1800054b0  jz      short loc_1800054BC
0x1800054b2  call    cs:__imp_SysFreeString
0x1800054b8  mov     [rbp+57h+bstrString], r14
0x1800054bc  mov     edx, dword ptr [rbp+57h+bstrString+8]; int
0x1800054bf  lea     rcx, [rbp+57h+var_98]; union tagUPNP_CONTROL_RESPONSE_DATA *
0x1800054c3  call    ?CleanupResponseData@@YAXPEATtagUPNP_CONTROL_RESPONSE_DATA@@H@Z; CleanupResponseData(tagUPNP_CONTROL_RESPONSE_DATA *,int)
0x1800054c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054cf  mov     rdx, [rbp+57h+arg_10]
0x1800054d3  test    rdx, rdx
0x1800054d6  jz      short loc_1800054F2
0x1800054d8  mov     rax, [rdx]
0x1800054db  mov     rcx, rdx
0x1800054de  mov     rax, [rax+10h]
0x1800054e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054ee  mov     [rbp+57h+arg_10], r14
0x1800054f2  mov     rdx, [rbp+57h+arg_8]
0x1800054f6  test    rdx, rdx
0x1800054f9  jz      short loc_180005515
0x1800054fb  mov     rax, [rdx]
0x1800054fe  mov     rcx, rdx
0x180005501  mov     rax, [rax+10h]
0x180005505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000550a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005511  mov     [rbp+57h+arg_8], r14
0x180005515  mov     rdx, [rbp+57h+arg_18]
0x180005519  test    rdx, rdx
0x18000551c  jz      short loc_180005538
0x18000551e  mov     rax, [rdx]
0x180005521  mov     rcx, rdx
0x180005524  mov     rax, [rax+10h]
0x180005528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000552d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005534  mov     [rbp+57h+arg_18], r14
0x180005538  test    ebx, ebx
0x18000553a  jz      short loc_180005567
0x18000553c  cmp     rcx, r15
0x18000553f  jz      short loc_180005567
0x180005541  test    byte ptr [rcx+1Ch], 1
0x180005545  jz      short loc_180005567
0x180005547  mov     rcx, [rcx+10h]
0x18000554b  lea     r9, aHrdorequestand; "HrDoRequestAndReturnResponse(): Exiting"
0x180005552  mov     edx, 67h ; 'g'
0x180005557  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18000555b  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180005562  call    WPP_SF_sd
0x180005567  mov     eax, ebx
0x180005569  add     rsp, 0B8h
0x180005570  pop     r15
0x180005572  pop     r14
0x180005574  pop     rdi
0x180005575  pop     rsi
0x180005576  pop     rbx
0x180005577  pop     rbp
0x180005578  retn
```
