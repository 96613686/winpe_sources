# CRootCause::SchdpUpdateVerificationResult(ushort *)

- ea: `0x1800062c4`
- end: `0x1800066ec`
- name: `?SchdpUpdateVerificationResult@CRootCause@@AEAAJPEAG@Z`
- size: `1064`
- prototype: `int(CRootCause *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180005974`

## callees

- `0x180005714`
- `0x1800062c4`
- `0x18000b13c`
- `0x18000b234`
- `0x18000b300`
- `0x18000b608`
- `0x18000b750`
- `0x18000b884`
- `0x18000d010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180006513`
- `msvcrt!_wcsicmp` at `0x180006544`
- `msvcrt!_wcsicmp` at `0x18000657d`
- `msvcrt!_wcsicmp` at `0x180006513`
- `msvcrt!_wcsicmp` at `0x180006544`
- `msvcrt!_wcsicmp` at `0x18000657d`
- `OLEAUT32!__imp_SysFreeString` at `0x180006418`
- `OLEAUT32!__imp_SysFreeString` at `0x180006431`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066c5`
- `OLEAUT32!__imp_SysFreeString` at `0x180006418`
- `OLEAUT32!__imp_SysFreeString` at `0x180006431`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066c5`

## string_xrefs

- `0x18000632d`: `CRootCause::SchdpUpdateVerificationResult`
- `0x18000635e`: `CRootCause::SchdpUpdateVerificationResult`
- `0x1800065c5`: `CRootCause::SchdpUpdateVerificationResult`
- `0x1800065ed`: `CRootCause::SchdpUpdateVerificationResult`
- `0x180006624`: `CRootCause::SchdpUpdateVerificationResult`

## pseudocode

```c
__int64 __fastcall CRootCause::SchdpUpdateVerificationResult(const wchar_t **this, unsigned __int16 *a2)
{
  struct IXMLDOMNodeList *v3; // r12
  struct IXMLDOMNode *v4; // rsi
  struct IXMLDOMNode *v5; // r15
  struct IXMLDOMNode *v6; // r14
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // r8d
  int v10; // r9d
  int Nodes; // eax
  int v12; // eax
  int v13; // eax
  int Node; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  __int64 v18; // rcx
  void *v19; // rdx
  BSTR bstrString; // [rsp+20h] [rbp-30h] BYREF
  BSTR String1; // [rsp+28h] [rbp-28h] BYREF
  struct IXMLDOMNode *v23; // [rsp+30h] [rbp-20h] BYREF
  struct IXMLDOMNode *v24; // [rsp+38h] [rbp-18h] BYREF
  struct IXMLDOMNode *v25; // [rsp+40h] [rbp-10h] BYREF
  struct IXMLDOMDocument2 *v26; // [rsp+48h] [rbp-8h] BYREF
  int v27; // [rsp+A0h] [rbp+50h] BYREF
  struct IXMLDOMNodeList *v28; // [rsp+A8h] [rbp+58h] BYREF

  v26 = 0;
  v3 = 0;
  v28 = 0;
  v4 = 0;
  v25 = 0;
  v5 = 0;
  v24 = 0;
  v6 = 0;
  v23 = 0;
  v27 = 0;
  bstrString = 0;
  String1 = 0;
  v7 = SdpXmlCreate(a2, (LPVOID *)&v26);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 422;
LABEL_3:
    v10 = v7;
LABEL_4:
    SdpDebugTrace(1u, L"CRootCause::SchdpUpdateVerificationResult", v9, v10);
    goto LABEL_48;
  }
  Nodes = SdpXmlGetNodes(L"/Rootcauses/Rootcause", v26, 0, &v28);
  v8 = Nodes;
  if ( Nodes < 0 )
  {
    SdpDebugTrace(1u, L"CRootCause::SchdpUpdateVerificationResult", 428, Nodes);
    v3 = v28;
    goto LABEL_48;
  }
  v3 = v28;
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, int *))v28->lpVtbl->get_length)(v28, &v27);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 431;
    goto LABEL_3;
  }
  if ( v27 )
  {
    LODWORD(v28) = 0;
    if ( v27 > 0 )
    {
      while ( 1 )
      {
        if ( v4 )
        {
          ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
          v25 = 0;
        }
        if ( v5 )
        {
          ((void (__fastcall *)(struct IXMLDOMNode *))v5->lpVtbl->Release)(v5);
          v5 = 0;
          v24 = 0;
        }
        if ( v6 )
        {
          ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
          v6 = 0;
          v23 = 0;
        }
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
        if ( String1 )
        {
          SysFreeString(String1);
          String1 = 0;
        }
        v12 = SdpXmlNextNode(v3, &v25);
        v8 = v12;
        if ( v12 < 0 )
        {
          SdpDebugTrace(1u, L"CRootCause::SchdpUpdateVerificationResult", 450, v12);
          v4 = v25;
          goto LABEL_48;
        }
        v4 = v25;
        v13 = SdpXmlCheckNode(v25, L"Rootcause");
        v8 = v13;
        if ( v13 < 0 )
        {
          v10 = v13;
LABEL_46:
          v9 = 451;
          goto LABEL_4;
        }
        if ( v13 == 1 || !v4 )
        {
          v8 = -2147467259;
          v10 = -2147467259;
          goto LABEL_46;
        }
        Node = SdpXmlGetNode(L"./ID", 0, v4, &v24);
        v8 = Node;
        if ( Node < 0 )
        {
          SdpDebugTrace(1u, L"CRootCause::SchdpUpdateVerificationResult", 457, Node);
          v5 = v24;
          goto LABEL_48;
        }
        v5 = v24;
        v15 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v24->lpVtbl->get_text)(v24, &bstrString);
        v8 = v15;
        if ( v15 < 0 )
        {
          v10 = v15;
          v9 = 460;
          goto LABEL_4;
        }
        v16 = SdpXmlGetNode(L"./Status", 0, v4, &v23);
        v8 = v16;
        if ( v16 < 0 )
        {
          SdpDebugTrace(1u, L"CRootCause::SchdpUpdateVerificationResult", 466, v16);
          v6 = v23;
          goto LABEL_48;
        }
        v6 = v23;
        v17 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v23->lpVtbl->get_text)(v23, &String1);
        v8 = v17;
        if ( v17 < 0 )
        {
          v10 = v17;
          v9 = 469;
          goto LABEL_4;
        }
        if ( !_wcsicmp(bstrString, *this) )
          break;
        LODWORD(v28) = (_DWORD)v28 + 1;
        if ( (int)v28 >= v27 )
          goto LABEL_48;
      }
      if ( !_wcsicmp(String1, L"Fixed") )
      {
        *((_DWORD *)this + 13) = 3;
        if ( (Microsoft_Windows_Diagnosis_ScheduledEnableBits & 2) == 0 )
          goto LABEL_48;
        v19 = &SCHEDULED_DIAGNOSTICS_EVENT_VERIFICATION_ROOTCAUSE_FIXED;
        goto LABEL_39;
      }
      if ( !_wcsicmp(String1, L"Not Fixed") )
        *((_DWORD *)this + 13) = 4;
      if ( (Microsoft_Windows_Diagnosis_ScheduledEnableBits & 2) != 0 )
      {
        v19 = &SCHEDULED_DIAGNOSTICS_EVENT_VERIFICATION_ROOTCAUSE_EXISTS;
LABEL_39:
        McTemplateU0z_EventWriteTransfer(v18, v19, *this);
      }
    }
  }
LABEL_48:
  if ( v26 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v26->lpVtbl->Release)(v26);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v3->lpVtbl->Release)(v3);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v5->lpVtbl->Release)(v5);
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( String1 )
    SysFreeString(String1);
  return v8;
}

```

## disassembly

```asm
0x1800062c4  mov     [rsp-38h+arg_0], rbx
0x1800062c9  push    rbp
0x1800062ca  push    rsi
0x1800062cb  push    rdi
0x1800062cc  push    r12
0x1800062ce  push    r13
0x1800062d0  push    r14
0x1800062d2  push    r15
0x1800062d4  mov     rbp, rsp
0x1800062d7  sub     rsp, 50h
0x1800062db  mov     r13, rcx
0x1800062de  mov     rax, rdx
0x1800062e1  xor     ecx, ecx
0x1800062e3  lea     rdx, [rbp+var_8]; struct IXMLDOMDocument2 **
0x1800062e7  mov     [rbp+var_8], rcx
0x1800062eb  mov     r12d, ecx
0x1800062ee  mov     [rbp+arg_18], rcx
0x1800062f2  mov     esi, ecx
0x1800062f4  mov     [rbp+var_10], rcx
0x1800062f8  mov     r15d, ecx
0x1800062fb  mov     [rbp+var_18], rcx
0x1800062ff  mov     r14d, ecx
0x180006302  mov     [rbp+var_20], rcx
0x180006306  mov     [rbp+arg_10], ecx
0x180006309  mov     [rbp+bstrString], rcx
0x18000630d  mov     [rbp+String1], rcx
0x180006311  mov     rcx, rax; psz
0x180006314  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180006319  mov     ebx, eax
0x18000631b  test    eax, eax
0x18000631d  jns     short loc_18000633E
0x18000631f  mov     r8d, 1A6h; int
0x180006325  mov     r9d, eax; int
0x180006328  mov     ecx, 1; Level
0x18000632d  lea     rdx, aCrootcauseSchd_5; "CRootCause::SchdpUpdateVerificationResu"...
0x180006334  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180006339  jmp     loc_18000663C
0x18000633e  mov     rdx, [rbp+var_8]; struct IXMLDOMDocument2 *
0x180006342  lea     r9, [rbp+arg_18]; struct IXMLDOMNodeList **
0x180006346  xor     r8d, r8d; struct IXMLDOMNode *
0x180006349  lea     rcx, aRootcausesRoot; "/Rootcauses/Rootcause"
0x180006350  call    ?SdpXmlGetNodes@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@@Z; SdpXmlGetNodes(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *)
0x180006355  mov     ebx, eax
0x180006357  test    eax, eax
0x180006359  jns     short loc_18000637E
0x18000635b  mov     r9d, eax; int
0x18000635e  lea     rdx, aCrootcauseSchd_5; "CRootCause::SchdpUpdateVerificationResu"...
0x180006365  mov     r8d, 1ACh; int
0x18000636b  mov     ecx, 1; Level
0x180006370  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180006375  mov     r12, [rbp+arg_18]
0x180006379  jmp     loc_18000663C
0x18000637e  mov     r12, [rbp+arg_18]
0x180006382  lea     rdx, [rbp+arg_10]
0x180006386  mov     rcx, r12
0x180006389  mov     rax, [r12]
0x18000638d  mov     rax, [rax+40h]
0x180006391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006396  mov     ebx, eax
0x180006398  test    eax, eax
0x18000639a  jns     short loc_1800063A4
0x18000639c  mov     r8d, 1AFh
0x1800063a2  jmp     short loc_180006325
0x1800063a4  mov     eax, [rbp+arg_10]
0x1800063a7  test    eax, eax
0x1800063a9  jz      loc_18000663C
0x1800063af  and     dword ptr [rbp+arg_18], esi
0x1800063b2  test    eax, eax
0x1800063b4  jle     loc_18000663C
0x1800063ba  mov     edi, 1
0x1800063bf  xor     ebx, ebx
0x1800063c1  test    rsi, rsi
0x1800063c4  jz      short loc_1800063D9
0x1800063c6  mov     rax, [rsi]
0x1800063c9  mov     rcx, rsi
0x1800063cc  mov     rax, [rax+10h]
0x1800063d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063d5  mov     [rbp+var_10], rbx
0x1800063d9  test    r15, r15
0x1800063dc  jz      short loc_1800063F4
0x1800063de  mov     rax, [r15]
0x1800063e1  mov     rcx, r15
0x1800063e4  mov     rax, [rax+10h]
0x1800063e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ed  mov     r15, rbx
0x1800063f0  mov     [rbp+var_18], rbx
0x1800063f4  test    r14, r14
0x1800063f7  jz      short loc_18000640F
0x1800063f9  mov     rax, [r14]
0x1800063fc  mov     rcx, r14
0x1800063ff  mov     rax, [rax+10h]
0x180006403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006408  mov     r14, rbx
0x18000640b  mov     [rbp+var_20], rbx
0x18000640f  mov     rcx, [rbp+bstrString]; bstrString
0x180006413  test    rcx, rcx
0x180006416  jz      short loc_180006428
0x180006418  call    cs:__imp_SysFreeString
0x18000641f  nop     dword ptr [rax+rax+00h]
0x180006424  mov     [rbp+bstrString], rbx
0x180006428  mov     rcx, [rbp+String1]; bstrString
0x18000642c  test    rcx, rcx
0x18000642f  jz      short loc_180006441
0x180006431  call    cs:__imp_SysFreeString
0x180006438  nop     dword ptr [rax+rax+00h]
0x18000643d  mov     [rbp+String1], rbx
0x180006441  lea     rdx, [rbp+var_10]; struct IXMLDOMNode **
0x180006445  mov     rcx, r12; struct IXMLDOMNodeList *
0x180006448  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18000644d  mov     ebx, eax
0x18000644f  test    eax, eax
0x180006451  js      loc_180006621
0x180006457  mov     rsi, [rbp+var_10]
0x18000645b  lea     rdx, aRootcause; "Rootcause"
0x180006462  mov     rcx, rsi; struct IXMLDOMNode *
0x180006465  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18000646a  mov     ebx, eax
0x18000646c  test    eax, eax
0x18000646e  js      loc_180006611
0x180006474  cmp     eax, edi
0x180006476  jz      loc_180006607
0x18000647c  test    rsi, rsi
0x18000647f  jz      loc_180006607
0x180006485  lea     r9, [rbp+var_18]; struct IXMLDOMNode **
0x180006489  mov     r8, rsi; struct IXMLDOMNode *
0x18000648c  xor     edx, edx; struct IXMLDOMDocument2 *
0x18000648e  lea     rcx, aId; "./ID"
0x180006495  call    ?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x18000649a  mov     ebx, eax
0x18000649c  test    eax, eax
0x18000649e  js      loc_1800065EA
0x1800064a4  mov     r15, [rbp+var_18]
0x1800064a8  lea     rdx, [rbp+bstrString]
0x1800064ac  mov     rcx, r15
0x1800064af  mov     rax, [r15]
0x1800064b2  mov     rax, [rax+0D0h]
0x1800064b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064be  mov     ebx, eax
0x1800064c0  test    eax, eax
0x1800064c2  js      loc_1800065DF
0x1800064c8  lea     r9, [rbp+var_20]; struct IXMLDOMNode **
0x1800064cc  mov     r8, rsi; struct IXMLDOMNode *
0x1800064cf  xor     edx, edx; struct IXMLDOMDocument2 *
0x1800064d1  lea     rcx, aStatus; "./Status"
0x1800064d8  call    ?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x1800064dd  mov     ebx, eax
0x1800064df  test    eax, eax
0x1800064e1  js      loc_1800065C2
0x1800064e7  mov     r14, [rbp+var_20]
0x1800064eb  lea     rdx, [rbp+String1]
0x1800064ef  mov     rcx, r14
0x1800064f2  mov     rax, [r14]
0x1800064f5  mov     rax, [rax+0D0h]
0x1800064fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006501  mov     ebx, eax
0x180006503  test    eax, eax
0x180006505  js      loc_1800065B7
0x18000650b  mov     rdx, [r13+0]; String2
0x18000650f  mov     rcx, [rbp+bstrString]; String1
0x180006513  call    cs:__imp__wcsicmp
0x18000651a  nop     dword ptr [rax+rax+00h]
0x18000651f  test    eax, eax
0x180006521  jz      short loc_180006539
0x180006523  mov     ecx, dword ptr [rbp+arg_18]
0x180006526  add     ecx, edi
0x180006528  mov     dword ptr [rbp+arg_18], ecx
0x18000652b  cmp     ecx, [rbp+arg_10]
0x18000652e  jl      loc_1800063BF
0x180006534  jmp     loc_18000663C
0x180006539  mov     rcx, [rbp+String1]; String1
0x18000653d  lea     rdx, aFixed; "Fixed"
0x180006544  call    cs:__imp__wcsicmp
0x18000654b  nop     dword ptr [rax+rax+00h]
0x180006550  test    eax, eax
0x180006552  jnz     short loc_180006572
0x180006554  mov     dword ptr [r13+34h], 3
0x18000655c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScheduledEnableBits, 2
0x180006563  jz      loc_18000663C
0x180006569  lea     rdx, SCHEDULED_DIAGNOSTICS_EVENT_VERIFICATION_ROOTCAUSE_FIXED
0x180006570  jmp     short loc_1800065A9
0x180006572  mov     rcx, [rbp+String1]; String1
0x180006576  lea     rdx, aNotFixed; "Not Fixed"
0x18000657d  call    cs:__imp__wcsicmp
0x180006584  nop     dword ptr [rax+rax+00h]
0x180006589  test    eax, eax
0x18000658b  jnz     short loc_180006595
0x18000658d  mov     dword ptr [r13+34h], 4
0x180006595  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScheduledEnableBits, 2
0x18000659c  jz      loc_18000663C
0x1800065a2  lea     rdx, SCHEDULED_DIAGNOSTICS_EVENT_VERIFICATION_ROOTCAUSE_EXISTS
0x1800065a9  mov     r8, [r13+0]
0x1800065ad  call    McTemplateU0z_EventWriteTransfer
0x1800065b2  jmp     loc_18000663C
0x1800065b7  mov     r9d, eax
0x1800065ba  mov     r8d, 1D5h
0x1800065c0  jmp     short loc_18000661A
0x1800065c2  mov     r9d, eax; int
0x1800065c5  lea     rdx, aCrootcauseSchd_5; "CRootCause::SchdpUpdateVerificationResu"...
0x1800065cc  mov     r8d, 1D2h; int
0x1800065d2  mov     ecx, edi; Level
0x1800065d4  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800065d9  mov     r14, [rbp+var_20]
0x1800065dd  jmp     short loc_18000663C
0x1800065df  mov     r9d, eax
0x1800065e2  mov     r8d, 1CCh
0x1800065e8  jmp     short loc_18000661A
0x1800065ea  mov     r9d, eax; int
0x1800065ed  lea     rdx, aCrootcauseSchd_5; "CRootCause::SchdpUpdateVerificationResu"...
0x1800065f4  mov     r8d, 1C9h; int
0x1800065fa  mov     ecx, edi; Level
0x1800065fc  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180006601  mov     r15, [rbp+var_18]
0x180006605  jmp     short loc_18000663C
0x180006607  mov     ebx, 80004005h
0x18000660c  mov     r9d, ebx
0x18000660f  jmp     short loc_180006614
0x180006611  mov     r9d, eax
0x180006614  mov     r8d, 1C3h
0x18000661a  mov     ecx, edi
0x18000661c  jmp     loc_18000632D
0x180006621  mov     r9d, eax; int
0x180006624  lea     rdx, aCrootcauseSchd_5; "CRootCause::SchdpUpdateVerificationResu"...
0x18000662b  mov     r8d, 1C2h; int
0x180006631  mov     ecx, edi; Level
0x180006633  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180006638  mov     rsi, [rbp+var_10]
0x18000663c  mov     rcx, [rbp+var_8]
0x180006640  test    rcx, rcx
0x180006643  jz      short loc_180006651
0x180006645  mov     rax, [rcx]
0x180006648  mov     rax, [rax+10h]
0x18000664c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006651  test    r12, r12
0x180006654  jz      short loc_180006666
0x180006656  mov     rax, [r12]
0x18000665a  mov     rcx, r12
0x18000665d  mov     rax, [rax+10h]
0x180006661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006666  test    rsi, rsi
0x180006669  jz      short loc_18000667A
0x18000666b  mov     rax, [rsi]
0x18000666e  mov     rcx, rsi
0x180006671  mov     rax, [rax+10h]
0x180006675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000667a  test    r15, r15
0x18000667d  jz      short loc_18000668E
0x18000667f  mov     rax, [r15]
0x180006682  mov     rcx, r15
0x180006685  mov     rax, [rax+10h]
0x180006689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000668e  test    r14, r14
0x180006691  jz      short loc_1800066A2
0x180006693  mov     rax, [r14]
0x180006696  mov     rcx, r14
0x180006699  mov     rax, [rax+10h]
0x18000669d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066a2  mov     rcx, [rbp+bstrString]; bstrString
0x1800066a6  test    rcx, rcx
0x1800066a9  jz      short loc_1800066BC
0x1800066ab  call    cs:__imp_SysFreeString
0x1800066b2  nop     dword ptr [rax+rax+00h]
0x1800066b7  and     [rbp+bstrString], 0
0x1800066bc  mov     rcx, [rbp+String1]; bstrString
0x1800066c0  test    rcx, rcx
0x1800066c3  jz      short loc_1800066D1
0x1800066c5  call    cs:__imp_SysFreeString
0x1800066cc  nop     dword ptr [rax+rax+00h]
0x1800066d1  mov     eax, ebx
0x1800066d3  mov     rbx, [rsp+50h+arg_0]
0x1800066db  add     rsp, 50h
0x1800066df  pop     r15
0x1800066e1  pop     r14
0x1800066e3  pop     r13
0x1800066e5  pop     r12
0x1800066e7  pop     rdi
0x1800066e8  pop     rsi
0x1800066e9  pop     rbp
0x1800066ea  retn
```
