# CRootCause::Update(IXMLDOMNode *)

- ea: `0x180006770`
- end: `0x180006938`
- name: `?Update@CRootCause@@QEAAJPEAUIXMLDOMNode@@@Z`
- size: `456`
- prototype: `int(CRootCause *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180004c48`

## callees

- `0x1800040b4`
- `0x180006770`
- `0x180006a60`
- `0x18000b13c`
- `0x18000b608`
- `0x18000d010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180006807`
- `msvcrt!_wcsicmp` at `0x18000682c`
- `msvcrt!_wcsicmp` at `0x180006807`
- `msvcrt!_wcsicmp` at `0x18000682c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000687c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000687c`

## string_xrefs

- `0x1800068e3`: `CRootCause::SchdpUpdateNotification`
- `0x1800067c2`: `CRootCause::SchdpUpdateDiagnosisResult`
- `0x180006913`: `CRootCause::Update`

## pseudocode

```c
__int64 __fastcall CRootCause::Update(CRootCause *this, struct IXMLDOMNode *a2)
{
  int Node; // eax
  struct IXMLDOMNode *v5; // rsi
  int v6; // ebx
  int v7; // r8d
  int v8; // edx
  int v9; // ecx
  int v10; // r8d
  int v11; // eax
  wchar_t *v12; // rsi
  int v13; // r8d
  struct IXMLDOMDocument2 *v14; // rcx
  wchar_t *String1; // [rsp+60h] [rbp+18h] BYREF
  struct IXMLDOMNode *v17; // [rsp+68h] [rbp+20h] BYREF

  v17 = 0;
  String1 = 0;
  Node = SdpXmlGetNode(L"./Status", 0, a2, &v17);
  v5 = v17;
  v6 = Node;
  if ( Node < 0 )
  {
    v7 = 355;
LABEL_3:
    SdpDebugTrace(1u, L"CRootCause::SchdpUpdateDiagnosisResult", v7, Node);
    goto LABEL_11;
  }
  Node = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))v17->lpVtbl->get_text)(v17, &String1);
  v6 = Node;
  if ( Node < 0 )
  {
    v7 = 358;
    goto LABEL_3;
  }
  if ( _wcsicmp(String1, L"Not Detected") )
  {
    if ( !_wcsicmp(String1, L"Detected") )
    {
      *((_DWORD *)this + 13) = 1;
      if ( (Microsoft_Windows_Diagnosis_ScheduledEnableBits & 2) != 0 )
        McTemplateU0zzz_EventWriteTransfer(v9, v8, *(_QWORD *)this, *((_QWORD *)this + 1), *((_QWORD *)this + 2));
    }
  }
  else
  {
    *((_DWORD *)this + 13) = 2;
  }
LABEL_11:
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v5->lpVtbl->Release)(v5);
  if ( String1 )
    SysFreeString(String1);
  if ( v6 < 0 )
  {
    v10 = 616;
LABEL_27:
    SdpDebugTrace(1u, L"CRootCause::Update", v10, v6);
    return (unsigned int)v6;
  }
  String1 = 0;
  v11 = SdpXmlGetNode(L"./Parameters", 0, a2, (struct IXMLDOMNode **)&String1);
  v12 = String1;
  v6 = v11;
  if ( v11 < 0 )
  {
    v13 = 308;
LABEL_22:
    SdpDebugTrace(1u, L"CRootCause::SchdpUpdateNotification", v13, v11);
    goto LABEL_23;
  }
  v14 = (struct IXMLDOMDocument2 *)*((_QWORD *)this + 4);
  if ( v14 )
  {
    v11 = CNotification::Update(v14, (struct IXMLDOMNode *)String1);
    v6 = v11;
    if ( v11 < 0 )
    {
      v13 = 312;
      goto LABEL_22;
    }
  }
LABEL_23:
  if ( v12 )
    (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v6 < 0 )
  {
    v10 = 619;
    goto LABEL_27;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006770  mov     rax, rsp
0x180006773  mov     [rax+8], rbx
0x180006777  mov     [rax+10h], rbp
0x18000677b  push    rsi
0x18000677c  push    rdi
0x18000677d  push    r15
0x18000677f  sub     rsp, 30h
0x180006783  and     qword ptr [rax+20h], 0
0x180006788  lea     r9, [rax+20h]; struct IXMLDOMNode **
0x18000678c  and     qword ptr [rax+18h], 0
0x180006791  mov     rbp, rdx
0x180006794  mov     rdi, rcx
0x180006797  mov     r8, rdx; struct IXMLDOMNode *
0x18000679a  xor     edx, edx; struct IXMLDOMDocument2 *
0x18000679c  lea     rcx, aStatus; "./Status"
0x1800067a3  call    ?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x1800067a8  mov     rsi, [rsp+48h+arg_18]
0x1800067ad  mov     ebx, eax
0x1800067af  mov     r15d, 1
0x1800067b5  test    eax, eax
0x1800067b7  jns     short loc_1800067D6
0x1800067b9  mov     r8d, 163h; int
0x1800067bf  mov     r9d, eax; int
0x1800067c2  lea     rdx, aCrootcauseSchd_2; "CRootCause::SchdpUpdateDiagnosisResult"
0x1800067c9  mov     ecx, r15d; Level
0x1800067cc  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800067d1  jmp     loc_18000685E
0x1800067d6  mov     rax, [rsi]
0x1800067d9  lea     rdx, [rsp+48h+String1]
0x1800067de  mov     rcx, rsi
0x1800067e1  mov     rax, [rax+0D0h]
0x1800067e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067ed  mov     ebx, eax
0x1800067ef  test    eax, eax
0x1800067f1  jns     short loc_1800067FB
0x1800067f3  mov     r8d, 166h
0x1800067f9  jmp     short loc_1800067BF
0x1800067fb  mov     rcx, [rsp+48h+String1]; String1
0x180006800  lea     rdx, aNotDetected; "Not Detected"
0x180006807  call    cs:__imp__wcsicmp
0x18000680e  nop     dword ptr [rax+rax+00h]
0x180006813  test    eax, eax
0x180006815  jnz     short loc_180006820
0x180006817  mov     dword ptr [rdi+34h], 2
0x18000681e  jmp     short loc_18000685E
0x180006820  mov     rcx, [rsp+48h+String1]; String1
0x180006825  lea     rdx, aDetected; "Detected"
0x18000682c  call    cs:__imp__wcsicmp
0x180006833  nop     dword ptr [rax+rax+00h]
0x180006838  test    eax, eax
0x18000683a  jnz     short loc_18000685E
0x18000683c  mov     [rdi+34h], r15d
0x180006840  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScheduledEnableBits, 2
0x180006847  jz      short loc_18000685E
0x180006849  mov     rax, [rdi+10h]
0x18000684d  mov     r9, [rdi+8]
0x180006851  mov     r8, [rdi]
0x180006854  mov     [rsp+48h+var_28], rax
0x180006859  call    McTemplateU0zzz_EventWriteTransfer
0x18000685e  test    rsi, rsi
0x180006861  jz      short loc_180006872
0x180006863  mov     rax, [rsi]
0x180006866  mov     rcx, rsi
0x180006869  mov     rax, [rax+10h]
0x18000686d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006872  mov     rcx, [rsp+48h+String1]; bstrString
0x180006877  test    rcx, rcx
0x18000687a  jz      short loc_180006888
0x18000687c  call    cs:__imp_SysFreeString
0x180006883  nop     dword ptr [rax+rax+00h]
0x180006888  test    ebx, ebx
0x18000688a  jns     short loc_180006894
0x18000688c  mov     r8d, 268h
0x180006892  jmp     short loc_180006910
0x180006894  and     [rsp+48h+String1], 0
0x18000689a  lea     r9, [rsp+48h+String1]; struct IXMLDOMNode **
0x18000689f  mov     r8, rbp; struct IXMLDOMNode *
0x1800068a2  lea     rcx, aParameters; "./Parameters"
0x1800068a9  xor     edx, edx; struct IXMLDOMDocument2 *
0x1800068ab  call    ?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x1800068b0  mov     rsi, [rsp+48h+String1]
0x1800068b5  mov     ebx, eax
0x1800068b7  test    eax, eax
0x1800068b9  jns     short loc_1800068C3
0x1800068bb  mov     r8d, 134h
0x1800068c1  jmp     short loc_1800068E0
0x1800068c3  mov     rcx, [rdi+20h]; this
0x1800068c7  test    rcx, rcx
0x1800068ca  jz      short loc_1800068F2
0x1800068cc  mov     rdx, rsi; struct IXMLDOMNode *
0x1800068cf  call    ?Update@CNotification@@QEAAJPEAUIXMLDOMNode@@@Z; CNotification::Update(IXMLDOMNode *)
0x1800068d4  mov     ebx, eax
0x1800068d6  test    eax, eax
0x1800068d8  jns     short loc_1800068F2
0x1800068da  mov     r8d, 138h; int
0x1800068e0  mov     r9d, eax; int
0x1800068e3  lea     rdx, aCrootcauseSchd; "CRootCause::SchdpUpdateNotification"
0x1800068ea  mov     ecx, r15d; Level
0x1800068ed  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800068f2  test    rsi, rsi
0x1800068f5  jz      short loc_180006906
0x1800068f7  mov     rax, [rsi]
0x1800068fa  mov     rcx, rsi
0x1800068fd  mov     rax, [rax+10h]
0x180006901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006906  test    ebx, ebx
0x180006908  jns     short loc_180006922
0x18000690a  mov     r8d, 26Bh; int
0x180006910  mov     r9d, ebx; int
0x180006913  lea     rdx, aCrootcauseUpda; "CRootCause::Update"
0x18000691a  mov     ecx, r15d; Level
0x18000691d  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180006922  mov     rbp, [rsp+48h+arg_8]
0x180006927  mov     eax, ebx
0x180006929  mov     rbx, [rsp+48h+arg_0]
0x18000692e  add     rsp, 30h
0x180006932  pop     r15
0x180006934  pop     rdi
0x180006935  pop     rsi
0x180006936  retn
```
