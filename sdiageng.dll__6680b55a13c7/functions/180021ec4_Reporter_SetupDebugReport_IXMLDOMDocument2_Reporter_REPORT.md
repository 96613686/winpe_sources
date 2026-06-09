# Reporter::SetupDebugReport(IXMLDOMDocument2 *,Reporter::_REPORT *)

- ea: `0x180021ec4`
- end: `0x18002216e`
- name: `?SetupDebugReport@Reporter@@AEAAJPEAUIXMLDOMDocument2@@PEAU_REPORT@1@@Z`
- size: `682`
- prototype: `__int64 __fastcall(Reporter *this, struct IXMLDOMDocument2 *, struct Reporter::_REPORT *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x180021914`

## callees

- `0x1800012b0`
- `0x180020fc0`
- `0x18002114c`
- `0x1800215e4`
- `0x180021870`
- `0x180021ec4`
- `0x180026fa0`
- `0x18002827c`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Reporter::SetupDebugReport(
        Reporter *this,
        struct IXMLDOMDocument2 *a2,
        struct Reporter::_REPORT *a3,
        unsigned __int16 *a4)
{
  struct IXMLDOMElement *v4; // rdi
  struct IXMLDOMElement *v5; // rsi
  struct IXMLDOMElement *v6; // r15
  unsigned int v9; // r8d
  int v10; // r9d
  unsigned int v11; // ebx
  Reporter *v12; // rcx
  int v13; // eax
  __int64 v14; // r12
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int IsAdminToReport; // eax
  Reporter *v19; // rcx
  unsigned int v20; // r8d
  struct IXMLDOMElement *v21; // rax
  struct IXMLDOMElement *v22; // rax
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  __int64 v24; // xmm1_8
  struct IXMLDOMElement *v26; // [rsp+30h] [rbp-20h] BYREF
  __int128 v27; // [rsp+38h] [rbp-18h] BYREF
  __int64 v28; // [rsp+48h] [rbp-8h]
  struct IXMLDOMElement *v30; // [rsp+A0h] [rbp+50h] BYREF
  struct IXMLDOMElement *v31; // [rsp+A8h] [rbp+58h] BYREF

  v4 = 0;
  v5 = 0;
  v6 = 0;
  v31 = 0;
  v30 = 0;
  v26 = 0;
  v28 = 0;
  v27 = 0;
  if ( !a3 )
  {
    v9 = 369;
LABEL_3:
    v10 = -2147024809;
    v11 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"Reporter::SetupDebugReport", v9, v10);
    goto LABEL_24;
  }
  if ( !a2 )
  {
    v9 = 370;
    goto LABEL_3;
  }
  v13 = Reporter::AddXslInstruction(this, a2, (unsigned __int16 *)a3, a4);
  v11 = v13;
  if ( v13 < 0 )
  {
    v10 = v13;
    v9 = 375;
    goto LABEL_4;
  }
  *((_QWORD *)&v27 + 1) = operator new[](0x30u);
  v14 = *((_QWORD *)&v27 + 1);
  if ( !*((_QWORD *)&v27 + 1) )
  {
    v11 = -2147024882;
    v9 = 378;
    v10 = -2147024882;
    goto LABEL_4;
  }
  v15 = SdpXmlCreateNode(a2, 0, L"Header", 0, &v31);
  v11 = v15;
  if ( v15 < 0 )
  {
    SdpDebugTrace(1u, L"Reporter::SetupDebugReport", 0x185u, v15);
    v4 = v31;
    goto LABEL_24;
  }
  v16 = SdpXmlCreateNode(a2, 0, L"Scripts", 0, &v30);
  v11 = v16;
  if ( v16 < 0 )
  {
    SdpDebugTrace(1u, L"Reporter::SetupDebugReport", 0x18Cu, v16);
    v4 = v31;
    v5 = v30;
    goto LABEL_24;
  }
  v17 = SdpXmlCreateNode(a2, 0, L"Functions", 0, &v26);
  v11 = v17;
  if ( v17 < 0 )
  {
    SdpDebugTrace(1u, L"Reporter::SetupDebugReport", 0x193u, v17);
    v4 = v31;
LABEL_17:
    v5 = v30;
    v6 = v26;
    goto LABEL_24;
  }
  v4 = v31;
  IsAdminToReport = Reporter::AddTimeToReport(this, v31, a2);
  v11 = IsAdminToReport;
  if ( IsAdminToReport < 0 )
  {
    v20 = 410;
LABEL_20:
    SdpDebugTrace(1u, L"Reporter::SetupDebugReport", v20, IsAdminToReport);
    goto LABEL_17;
  }
  IsAdminToReport = Reporter::AddIsAdminToReport(v19, v4, a2);
  v11 = IsAdminToReport;
  if ( IsAdminToReport < 0 )
  {
    v20 = 417;
    goto LABEL_20;
  }
  v21 = v30;
  *(_QWORD *)(v14 + 8) = v4;
  v4 = 0;
  *(_DWORD *)v14 = 0;
  *(_QWORD *)(v14 + 24) = v21;
  v22 = v26;
  *(_DWORD *)(v14 + 16) = 2;
  *(_QWORD *)(v14 + 40) = v22;
  *(_DWORD *)(v14 + 32) = 1;
  lpVtbl = a2->lpVtbl;
  LODWORD(v28) = 3;
  *(_QWORD *)&v27 = a2;
  ((void (__fastcall *)(struct IXMLDOMDocument2 *))lpVtbl->AddRef)(a2);
  v24 = v28;
  *(_OWORD *)a3 = v27;
  v28 = 0;
  *((_QWORD *)a3 + 2) = v24;
  v27 = 0;
LABEL_24:
  Reporter::FreeReport(v12, (struct Reporter::_REPORT *)&v27);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v4->lpVtbl->Release)(v4);
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v5->lpVtbl->Release)(v5);
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v6->lpVtbl->Release)(v6);
  return v11;
}

```

## disassembly

```asm
0x180021ec4  mov     [rsp-38h+arg_8], rbx
0x180021ec9  mov     [rsp-38h+arg_0], rcx
0x180021ece  push    rbp
0x180021ecf  push    rsi
0x180021ed0  push    rdi
0x180021ed1  push    r12
0x180021ed3  push    r13
0x180021ed5  push    r14
0x180021ed7  push    r15
0x180021ed9  mov     rbp, rsp
0x180021edc  sub     rsp, 50h
0x180021ee0  xor     edi, edi
0x180021ee2  xor     esi, esi
0x180021ee4  xor     r15d, r15d
0x180021ee7  mov     [rbp+arg_18], rdi
0x180021eeb  xor     eax, eax
0x180021eed  mov     [rbp+arg_10], rsi
0x180021ef1  mov     [rbp+var_20], r15
0x180021ef5  xorps   xmm0, xmm0
0x180021ef8  mov     [rbp+var_8], rax
0x180021efc  mov     r13, r8
0x180021eff  mov     r14, rdx
0x180021f02  movups  [rbp+var_18], xmm0
0x180021f06  test    r8, r8
0x180021f09  jnz     short loc_180021F30
0x180021f0b  mov     r8d, 171h; int
0x180021f11  mov     r9d, 80070057h; int
0x180021f17  mov     ebx, r9d
0x180021f1a  lea     rdx, aReporterSetupd; "Reporter::SetupDebugReport"
0x180021f21  mov     ecx, 1; Level
0x180021f26  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180021f2b  jmp     loc_18002210F
0x180021f30  test    r14, r14
0x180021f33  jnz     short loc_180021F3D
0x180021f35  mov     r8d, 172h; unsigned __int16 *
0x180021f3b  jmp     short loc_180021F11
0x180021f3d  call    ?AddXslInstruction@Reporter@@AEAAJPEAUIXMLDOMDocument2@@PEAG1@Z; Reporter::AddXslInstruction(IXMLDOMDocument2 *,ushort *,ushort *)
0x180021f42  mov     ebx, eax
0x180021f44  test    eax, eax
0x180021f46  jns     short loc_180021F53
0x180021f48  mov     r9d, eax
0x180021f4b  mov     r8d, 177h
0x180021f51  jmp     short loc_180021F1A
0x180021f53  mov     ecx, 30h ; '0'; unsigned __int64
0x180021f58  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180021f5d  mov     qword ptr [rbp+var_18+8], rax
0x180021f61  mov     r12, rax
0x180021f64  test    rax, rax
0x180021f67  jnz     short loc_180021F79
0x180021f69  mov     ebx, 8007000Eh
0x180021f6e  mov     r8d, 17Ah
0x180021f74  mov     r9d, ebx
0x180021f77  jmp     short loc_180021F1A
0x180021f79  lea     rax, [rbp+arg_18]
0x180021f7d  xor     r9d, r9d; unsigned __int16 *
0x180021f80  lea     r8, aHeader; "Header"
0x180021f87  mov     [rsp+50h+var_30], rax; struct IXMLDOMElement **
0x180021f8c  xor     edx, edx; struct IXMLDOMElement *
0x180021f8e  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180021f91  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180021f96  mov     ebx, eax
0x180021f98  test    eax, eax
0x180021f9a  jns     short loc_180021FBF
0x180021f9c  mov     r9d, eax; int
0x180021f9f  lea     rdx, aReporterSetupd; "Reporter::SetupDebugReport"
0x180021fa6  mov     r8d, 185h; int
0x180021fac  mov     ecx, 1; Level
0x180021fb1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180021fb6  mov     rdi, [rbp+arg_18]
0x180021fba  jmp     loc_18002210F
0x180021fbf  lea     rax, [rbp+arg_10]
0x180021fc3  xor     r9d, r9d; unsigned __int16 *
0x180021fc6  lea     r8, aScripts; "Scripts"
0x180021fcd  mov     [rsp+50h+var_30], rax; struct IXMLDOMElement **
0x180021fd2  xor     edx, edx; struct IXMLDOMElement *
0x180021fd4  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180021fd7  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180021fdc  mov     ebx, eax
0x180021fde  test    eax, eax
0x180021fe0  jns     short loc_180022009
0x180021fe2  mov     r9d, eax; int
0x180021fe5  lea     rdx, aReporterSetupd; "Reporter::SetupDebugReport"
0x180021fec  mov     r8d, 18Ch; int
0x180021ff2  mov     ecx, 1; Level
0x180021ff7  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180021ffc  mov     rdi, [rbp+arg_18]
0x180022000  mov     rsi, [rbp+arg_10]
0x180022004  jmp     loc_18002210F
0x180022009  lea     rax, [rbp+var_20]
0x18002200d  xor     r9d, r9d; unsigned __int16 *
0x180022010  lea     r8, aFunctions; "Functions"
0x180022017  mov     [rsp+50h+var_30], rax; struct IXMLDOMElement **
0x18002201c  xor     edx, edx; struct IXMLDOMElement *
0x18002201e  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180022021  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180022026  mov     ebx, eax
0x180022028  test    eax, eax
0x18002202a  jns     short loc_180022057
0x18002202c  mov     r9d, eax; int
0x18002202f  lea     rdx, aReporterSetupd; "Reporter::SetupDebugReport"
0x180022036  mov     r8d, 193h; int
0x18002203c  mov     ecx, 1; Level
0x180022041  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180022046  mov     rdi, [rbp+arg_18]
0x18002204a  mov     rsi, [rbp+arg_10]
0x18002204e  mov     r15, [rbp+var_20]
0x180022052  jmp     loc_18002210F
0x180022057  mov     rdi, [rbp+arg_18]
0x18002205b  mov     r8, r14; struct IXMLDOMDocument2 *
0x18002205e  mov     rcx, [rbp+arg_0]; this
0x180022062  mov     rdx, rdi; struct IXMLDOMElement *
0x180022065  call    ?AddTimeToReport@Reporter@@AEAAJPEAUIXMLDOMElement@@PEAUIXMLDOMDocument2@@@Z; Reporter::AddTimeToReport(IXMLDOMElement *,IXMLDOMDocument2 *)
0x18002206a  mov     ebx, eax
0x18002206c  test    eax, eax
0x18002206e  jns     short loc_18002208C
0x180022070  mov     r8d, 19Ah; int
0x180022076  mov     r9d, eax; int
0x180022079  lea     rdx, aReporterSetupd; "Reporter::SetupDebugReport"
0x180022080  mov     ecx, 1; Level
0x180022085  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18002208a  jmp     short loc_18002204A
0x18002208c  mov     r8, r14; struct IXMLDOMDocument2 *
0x18002208f  mov     rdx, rdi; struct IXMLDOMElement *
0x180022092  call    ?AddIsAdminToReport@Reporter@@AEAAJPEAUIXMLDOMElement@@PEAUIXMLDOMDocument2@@@Z; Reporter::AddIsAdminToReport(IXMLDOMElement *,IXMLDOMDocument2 *)
0x180022097  mov     ebx, eax
0x180022099  test    eax, eax
0x18002209b  jns     short loc_1800220A5
0x18002209d  mov     r8d, 1A1h
0x1800220a3  jmp     short loc_180022076
0x1800220a5  mov     rax, [rbp+arg_10]
0x1800220a9  mov     rcx, r14
0x1800220ac  mov     [r12+8], rdi
0x1800220b1  xor     edi, edi
0x1800220b3  mov     [r12], esi
0x1800220b7  mov     [r12+18h], rax
0x1800220bc  mov     rax, [rbp+var_20]
0x1800220c0  mov     dword ptr [r12+10h], 2
0x1800220c9  mov     [r12+28h], rax
0x1800220ce  mov     dword ptr [r12+20h], 1
0x1800220d7  mov     rax, [r14]
0x1800220da  mov     dword ptr [rbp+var_8], 3
0x1800220e1  mov     qword ptr [rbp+var_18], r14
0x1800220e5  mov     rax, [rax+8]
0x1800220e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220ee  movups  xmm0, [rbp+var_18]
0x1800220f2  xor     eax, eax
0x1800220f4  movsd   xmm1, [rbp+var_8]
0x1800220f9  movups  xmmword ptr [r13+0], xmm0
0x1800220fe  mov     [rbp+var_8], rax
0x180022102  xorps   xmm0, xmm0
0x180022105  movsd   qword ptr [r13+10h], xmm1
0x18002210b  movups  [rbp+var_18], xmm0
0x18002210f  lea     rdx, [rbp+var_18]; struct Reporter::_REPORT *
0x180022113  call    ?FreeReport@Reporter@@AEAAJPEAU_REPORT@1@@Z; Reporter::FreeReport(Reporter::_REPORT *)
0x180022118  test    rdi, rdi
0x18002211b  jz      short loc_18002212C
0x18002211d  mov     rax, [rdi]
0x180022120  mov     rcx, rdi
0x180022123  mov     rax, [rax+10h]
0x180022127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002212c  test    rsi, rsi
0x18002212f  jz      short loc_180022140
0x180022131  mov     rax, [rsi]
0x180022134  mov     rcx, rsi
0x180022137  mov     rax, [rax+10h]
0x18002213b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022140  test    r15, r15
0x180022143  jz      short loc_180022154
0x180022145  mov     rax, [r15]
0x180022148  mov     rcx, r15
0x18002214b  mov     rax, [rax+10h]
0x18002214f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022154  mov     eax, ebx
0x180022156  mov     rbx, [rsp+50h+arg_8]
0x18002215e  add     rsp, 50h
0x180022162  pop     r15
0x180022164  pop     r14
0x180022166  pop     r13
0x180022168  pop     r12
0x18002216a  pop     rdi
0x18002216b  pop     rsi
0x18002216c  pop     rbp
0x18002216d  retn
```
