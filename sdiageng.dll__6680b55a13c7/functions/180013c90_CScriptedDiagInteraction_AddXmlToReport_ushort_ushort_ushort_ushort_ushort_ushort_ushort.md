# CScriptedDiagInteraction::AddXmlToReport(ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,ushort *)

- ea: `0x180013c90`
- end: `0x180013d0a`
- name: `?AddXmlToReport@CScriptedDiagInteraction@@UEAAJPEAG000000@Z`
- size: `122`
- prototype: `__int64 __fastcall(CScriptedDiagInteraction *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000a2f4`
- `0x180013c90`
- `0x180026fa0`

## string_xrefs

- `0x180013cf1`: `CScriptedDiagInteraction::AddXmlToReport`

## pseudocode

```c
__int64 __fastcall CScriptedDiagInteraction::AddXmlToReport(
        CScriptedDiagInteraction *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8)
{
  DiagPackage **v8; // rcx
  unsigned int v9; // ebx
  int v10; // r8d
  int v11; // r9d
  int v12; // eax

  v8 = (DiagPackage **)*((_QWORD *)this + 2);
  if ( !v8 )
  {
    v9 = -2147467261;
    v10 = 233;
    v11 = -2147467261;
LABEL_5:
    SdpDebugTrace(1u, L"CScriptedDiagInteraction::AddXmlToReport", v10, v11);
    return v9;
  }
  v12 = CScriptedDiag::AddXmlToReport(v8, a2, a3, a4, a5, a6, a7, a8);
  v9 = v12;
  if ( v12 < 0 )
  {
    v11 = v12;
    v10 = 242;
    goto LABEL_5;
  }
  return v9;
}

```

## disassembly

```asm
0x180013c90  push    rbx
0x180013c92  sub     rsp, 40h
0x180013c96  mov     rcx, [rcx+10h]; this
0x180013c9a  test    rcx, rcx
0x180013c9d  jnz     short loc_180013CAF
0x180013c9f  mov     ebx, 80004003h
0x180013ca4  mov     r8d, 0E9h; unsigned __int16 *
0x180013caa  mov     r9d, ebx; unsigned __int16 *
0x180013cad  jmp     short loc_180013CF1
0x180013caf  mov     rax, [rsp+48h+arg_38]
0x180013cb7  mov     [rsp+48h+var_10], rax; unsigned __int16 *
0x180013cbc  mov     rax, [rsp+48h+arg_30]
0x180013cc4  mov     [rsp+48h+var_18], rax; unsigned __int16 *
0x180013cc9  mov     rax, [rsp+48h+arg_28]
0x180013cce  mov     [rsp+48h+var_20], rax; unsigned __int16 *
0x180013cd3  mov     rax, [rsp+48h+arg_20]
0x180013cd8  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180013cdd  call    ?AddXmlToReport@CScriptedDiag@@QEAAJPEAG000000@Z; CScriptedDiag::AddXmlToReport(ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,ushort *)
0x180013ce2  mov     ebx, eax
0x180013ce4  test    eax, eax
0x180013ce6  jns     short loc_180013D02
0x180013ce8  mov     r9d, eax; int
0x180013ceb  mov     r8d, 0F2h; int
0x180013cf1  lea     rdx, aCscripteddiagi; "CScriptedDiagInteraction::AddXmlToRepor"...
0x180013cf8  mov     ecx, 1; Level
0x180013cfd  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180013d02  mov     eax, ebx
0x180013d04  add     rsp, 40h
0x180013d08  pop     rbx
0x180013d09  retn
```
