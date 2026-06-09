# Reporter::SetupResultReport(IXMLDOMDocument2 *,Reporter::_REPORT *)

- ea: `0x180022174`
- end: `0x180022344`
- name: `?SetupResultReport@Reporter@@AEAAJPEAUIXMLDOMDocument2@@PEAU_REPORT@1@@Z`
- size: `464`
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
- `0x180022174`
- `0x180026fa0`
- `0x18002827c`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Reporter::SetupResultReport(
        Reporter *this,
        struct IXMLDOMDocument2 *a2,
        struct Reporter::_REPORT *a3,
        unsigned __int16 *a4)
{
  unsigned int v7; // r8d
  int v8; // r9d
  unsigned int v9; // ebx
  Reporter *v10; // rcx
  int v11; // eax
  __int64 v12; // rsi
  int v13; // eax
  int v14; // eax
  struct IXMLDOMElement *v15; // r14
  int v16; // eax
  Reporter *v17; // rcx
  int IsAdminToReport; // eax
  struct IXMLDOMElement *v19; // rax
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  __int64 v21; // xmm1_8
  __int128 v23; // [rsp+30h] [rbp-20h] BYREF
  __int64 v24; // [rsp+40h] [rbp-10h]
  struct IXMLDOMElement *v25; // [rsp+90h] [rbp+40h] BYREF
  struct IXMLDOMElement *v26; // [rsp+98h] [rbp+48h] BYREF

  v25 = 0;
  v26 = 0;
  v24 = 0;
  v23 = 0;
  if ( !a3 )
  {
    v7 = 487;
LABEL_3:
    v8 = -2147024809;
    v9 = -2147024809;
    goto LABEL_4;
  }
  if ( !a2 )
  {
    v7 = 488;
    goto LABEL_3;
  }
  v11 = Reporter::AddXslInstruction(this, a2, (unsigned __int16 *)a3, a4);
  v9 = v11;
  if ( v11 >= 0 )
  {
    *((_QWORD *)&v23 + 1) = operator new[](0x20u);
    v12 = *((_QWORD *)&v23 + 1);
    if ( *((_QWORD *)&v23 + 1) )
    {
      v13 = SdpXmlCreateNode(a2, 0, L"Header", 0, &v25);
      v9 = v13;
      if ( v13 >= 0 )
      {
        v14 = SdpXmlCreateNode(a2, 0, L"Package", 0, &v26);
        v9 = v14;
        if ( v14 >= 0 )
        {
          v15 = v25;
          v16 = Reporter::AddTimeToReport(this, v25, a2);
          v9 = v16;
          if ( v16 >= 0 )
          {
            IsAdminToReport = Reporter::AddIsAdminToReport(v17, v15, a2);
            v9 = IsAdminToReport;
            if ( IsAdminToReport >= 0 )
            {
              v19 = v26;
              *(_QWORD *)(*((_QWORD *)&v23 + 1) + 8LL) = v15;
              *(_DWORD *)v12 = 0;
              *(_QWORD *)(v12 + 24) = v19;
              *(_DWORD *)(v12 + 16) = 3;
              lpVtbl = a2->lpVtbl;
              LODWORD(v24) = 2;
              *(_QWORD *)&v23 = a2;
              ((void (__fastcall *)(struct IXMLDOMDocument2 *))lpVtbl->AddRef)(a2);
              v21 = v24;
              *(_OWORD *)a3 = v23;
              v24 = 0;
              *((_QWORD *)a3 + 2) = v21;
              v23 = 0;
              goto LABEL_20;
            }
            v8 = IsAdminToReport;
            v7 = 528;
          }
          else
          {
            v8 = v16;
            v7 = 521;
          }
        }
        else
        {
          v8 = v14;
          v7 = 514;
        }
      }
      else
      {
        v8 = v13;
        v7 = 507;
      }
    }
    else
    {
      v9 = -2147024882;
      v7 = 496;
      v8 = -2147024882;
    }
  }
  else
  {
    v8 = v11;
    v7 = 493;
  }
LABEL_4:
  SdpDebugTrace(1u, L"Reporter::SetupResultReport", v7, v8);
LABEL_20:
  Reporter::FreeReport(v10, (struct Reporter::_REPORT *)&v23);
  return v9;
}

```

## disassembly

```asm
0x180022174  mov     [rsp-28h+arg_0], rbx
0x180022179  mov     [rsp-28h+arg_8], rsi
0x18002217e  push    rbp
0x18002217f  push    rdi
0x180022180  push    r12
0x180022182  push    r14
0x180022184  push    r15
0x180022186  mov     rbp, rsp
0x180022189  sub     rsp, 50h
0x18002218d  xor     eax, eax
0x18002218f  mov     [rbp+arg_10], 0
0x180022197  mov     [rbp+arg_18], 0
0x18002219f  xorps   xmm0, xmm0
0x1800221a2  mov     [rbp+var_10], rax
0x1800221a6  mov     r15, r8
0x1800221a9  mov     rdi, rdx
0x1800221ac  mov     r12, rcx
0x1800221af  movups  [rbp+var_20], xmm0
0x1800221b3  test    r8, r8
0x1800221b6  jnz     short loc_1800221DD
0x1800221b8  mov     r8d, 1E7h; int
0x1800221be  mov     r9d, 80070057h; int
0x1800221c4  mov     ebx, r9d
0x1800221c7  lea     rdx, aReporterSetupr; "Reporter::SetupResultReport"
0x1800221ce  mov     ecx, 1; Level
0x1800221d3  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800221d8  jmp     loc_180022320
0x1800221dd  test    rdi, rdi
0x1800221e0  jnz     short loc_1800221EA
0x1800221e2  mov     r8d, 1E8h; unsigned __int16 *
0x1800221e8  jmp     short loc_1800221BE
0x1800221ea  call    ?AddXslInstruction@Reporter@@AEAAJPEAUIXMLDOMDocument2@@PEAG1@Z; Reporter::AddXslInstruction(IXMLDOMDocument2 *,ushort *,ushort *)
0x1800221ef  mov     ebx, eax
0x1800221f1  test    eax, eax
0x1800221f3  jns     short loc_180022200
0x1800221f5  mov     r9d, eax
0x1800221f8  mov     r8d, 1EDh
0x1800221fe  jmp     short loc_1800221C7
0x180022200  mov     ecx, 20h ; ' '; unsigned __int64
0x180022205  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002220a  mov     qword ptr [rbp+var_20+8], rax
0x18002220e  mov     rsi, rax
0x180022211  test    rax, rax
0x180022214  jnz     short loc_180022226
0x180022216  mov     ebx, 8007000Eh
0x18002221b  mov     r8d, 1F0h
0x180022221  mov     r9d, ebx
0x180022224  jmp     short loc_1800221C7
0x180022226  lea     rax, [rbp+arg_10]
0x18002222a  xor     r9d, r9d; unsigned __int16 *
0x18002222d  lea     r8, aHeader; "Header"
0x180022234  mov     [rsp+50h+var_30], rax; struct IXMLDOMElement **
0x180022239  xor     edx, edx; struct IXMLDOMElement *
0x18002223b  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18002223e  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180022243  mov     ebx, eax
0x180022245  test    eax, eax
0x180022247  jns     short loc_180022257
0x180022249  mov     r9d, eax
0x18002224c  mov     r8d, 1FBh
0x180022252  jmp     loc_1800221C7
0x180022257  lea     rax, [rbp+arg_18]
0x18002225b  xor     r9d, r9d; unsigned __int16 *
0x18002225e  lea     r8, aPackage; "Package"
0x180022265  mov     [rsp+50h+var_30], rax; struct IXMLDOMElement **
0x18002226a  xor     edx, edx; struct IXMLDOMElement *
0x18002226c  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18002226f  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180022274  mov     ebx, eax
0x180022276  test    eax, eax
0x180022278  jns     short loc_180022288
0x18002227a  mov     r9d, eax
0x18002227d  mov     r8d, 202h
0x180022283  jmp     loc_1800221C7
0x180022288  mov     r14, [rbp+arg_10]
0x18002228c  mov     r8, rdi; struct IXMLDOMDocument2 *
0x18002228f  mov     rdx, r14; struct IXMLDOMElement *
0x180022292  mov     rcx, r12; this
0x180022295  call    ?AddTimeToReport@Reporter@@AEAAJPEAUIXMLDOMElement@@PEAUIXMLDOMDocument2@@@Z; Reporter::AddTimeToReport(IXMLDOMElement *,IXMLDOMDocument2 *)
0x18002229a  mov     ebx, eax
0x18002229c  test    eax, eax
0x18002229e  jns     short loc_1800222AE
0x1800222a0  mov     r9d, eax
0x1800222a3  mov     r8d, 209h
0x1800222a9  jmp     loc_1800221C7
0x1800222ae  mov     r8, rdi; struct IXMLDOMDocument2 *
0x1800222b1  mov     rdx, r14; struct IXMLDOMElement *
0x1800222b4  call    ?AddIsAdminToReport@Reporter@@AEAAJPEAUIXMLDOMElement@@PEAUIXMLDOMDocument2@@@Z; Reporter::AddIsAdminToReport(IXMLDOMElement *,IXMLDOMDocument2 *)
0x1800222b9  mov     ebx, eax
0x1800222bb  test    eax, eax
0x1800222bd  jns     short loc_1800222CD
0x1800222bf  mov     r9d, eax
0x1800222c2  mov     r8d, 210h
0x1800222c8  jmp     loc_1800221C7
0x1800222cd  mov     rax, [rbp+arg_18]
0x1800222d1  mov     rcx, rdi
0x1800222d4  mov     [rsi+8], r14
0x1800222d8  mov     dword ptr [rsi], 0
0x1800222de  mov     [rsi+18h], rax
0x1800222e2  mov     dword ptr [rsi+10h], 3
0x1800222e9  mov     rax, [rdi]
0x1800222ec  mov     dword ptr [rbp+var_10], 2
0x1800222f3  mov     qword ptr [rbp+var_20], rdi
0x1800222f7  mov     rax, [rax+8]
0x1800222fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022300  movups  xmm0, [rbp+var_20]
0x180022304  xor     eax, eax
0x180022306  movsd   xmm1, [rbp+var_10]
0x18002230b  movups  xmmword ptr [r15], xmm0
0x18002230f  mov     [rbp+var_10], rax
0x180022313  xorps   xmm0, xmm0
0x180022316  movsd   qword ptr [r15+10h], xmm1
0x18002231c  movups  [rbp+var_20], xmm0
0x180022320  lea     rdx, [rbp+var_20]; struct Reporter::_REPORT *
0x180022324  call    ?FreeReport@Reporter@@AEAAJPEAU_REPORT@1@@Z; Reporter::FreeReport(Reporter::_REPORT *)
0x180022329  lea     r11, [rsp+50h+var_s0]
0x18002232e  mov     eax, ebx
0x180022330  mov     rbx, [r11+30h]
0x180022334  mov     rsi, [r11+38h]
0x180022338  mov     rsp, r11
0x18002233b  pop     r15
0x18002233d  pop     r14
0x18002233f  pop     r12
0x180022341  pop     rdi
0x180022342  pop     rbp
0x180022343  retn
```
