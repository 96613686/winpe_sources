# DiagPackage::AddXmlToDebugReport(ushort *,ushort *,ushort *,ushort *)

- ea: `0x180014438`
- end: `0x18001453d`
- name: `?AddXmlToDebugReport@DiagPackage@@QEAAJPEAG000@Z`
- size: `261`
- prototype: `__int64 __fastcall(DiagPackage *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180014544`

## callees

- `0x180014438`
- `0x180018510`
- `0x18001bcf8`
- `0x180026fa0`

## string_xrefs

- `0x180014524`: `DiagPackage::AddXmlToDebugReport`

## pseudocode

```c
__int64 __fastcall DiagPackage::AddXmlToDebugReport(
        DiagPackage *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  int v5; // r9d
  int v6; // r8d
  unsigned int v7; // ebx
  __int64 v8; // rax
  Troubleshooter *v9; // rax
  int v10; // eax
  Rootcause *v11; // rcx

  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 2308;
    v7 = -2147024809;
LABEL_20:
    SdpDebugTrace(1u, L"DiagPackage::AddXmlToDebugReport", v6, v5);
    return v7;
  }
  if ( !a3 )
  {
    v5 = -2147024809;
    v6 = 2309;
    v7 = -2147024809;
    goto LABEL_20;
  }
  if ( !a4 )
  {
    v5 = -2147024809;
    v6 = 2310;
    v7 = -2147024809;
    goto LABEL_20;
  }
  if ( !a5 )
  {
    v5 = -2147024809;
    v6 = 2311;
    v7 = -2147024809;
    goto LABEL_20;
  }
  v8 = *((_QWORD *)this + 1);
  if ( !v8 )
  {
    v5 = -2147467261;
    v6 = 2313;
    v7 = -2147467261;
    goto LABEL_20;
  }
  if ( *(_DWORD *)(v8 + 88) == 3 && (v9 = (Troubleshooter *)*((_QWORD *)this + 2)) != 0 )
  {
    v10 = Troubleshooter::AddXmlToDebugReport(v9, a2, a3, a4, a5);
    v7 = v10;
    if ( v10 < 0 )
    {
      v6 = 2324;
LABEL_19:
      v5 = v10;
      goto LABEL_20;
    }
  }
  else
  {
    v11 = (Rootcause *)*((_QWORD *)this + 12);
    if ( !v11 )
    {
      v5 = -2147467261;
      v6 = 2332;
      v7 = -2147467261;
      goto LABEL_20;
    }
    v10 = Rootcause::AddXmlToDebugReport(v11, a2, a3, a4, a5);
    v7 = v10;
    if ( v10 < 0 )
    {
      v6 = 2334;
      goto LABEL_19;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180014438  push    rbx
0x18001443a  sub     rsp, 30h
0x18001443e  mov     r10, rdx
0x180014441  test    rdx, rdx
0x180014444  jnz     short loc_18001445A
0x180014446  mov     r9d, 80070057h
0x18001444c  mov     r8d, 904h
0x180014452  mov     ebx, r9d
0x180014455  jmp     loc_180014524
0x18001445a  test    r8, r8
0x18001445d  jnz     short loc_180014473
0x18001445f  mov     r9d, 80070057h
0x180014465  mov     r8d, 905h
0x18001446b  mov     ebx, r9d
0x18001446e  jmp     loc_180014524
0x180014473  test    r9, r9
0x180014476  jnz     short loc_18001448C
0x180014478  mov     r9d, 80070057h
0x18001447e  mov     r8d, 906h
0x180014484  mov     ebx, r9d
0x180014487  jmp     loc_180014524
0x18001448c  mov     rdx, [rsp+38h+arg_20]
0x180014491  test    rdx, rdx
0x180014494  jnz     short loc_1800144A7
0x180014496  mov     r9d, 80070057h
0x18001449c  mov     r8d, 907h
0x1800144a2  mov     ebx, r9d
0x1800144a5  jmp     short loc_180014524
0x1800144a7  mov     rax, [rcx+8]
0x1800144ab  test    rax, rax
0x1800144ae  jnz     short loc_1800144C1
0x1800144b0  mov     r9d, 80004003h; unsigned __int16 *
0x1800144b6  mov     r8d, 909h; unsigned __int16 *
0x1800144bc  mov     ebx, r9d
0x1800144bf  jmp     short loc_180014524
0x1800144c1  cmp     dword ptr [rax+58h], 3
0x1800144c5  jnz     short loc_1800144EE
0x1800144c7  mov     rax, [rcx+10h]
0x1800144cb  test    rax, rax
0x1800144ce  jz      short loc_1800144EE
0x1800144d0  mov     [rsp+38h+var_18], rdx; unsigned __int16 *
0x1800144d5  mov     rcx, rax; this
0x1800144d8  mov     rdx, r10; unsigned __int16 *
0x1800144db  call    ?AddXmlToDebugReport@Troubleshooter@@QEAAJPEAG000@Z; Troubleshooter::AddXmlToDebugReport(ushort *,ushort *,ushort *,ushort *)
0x1800144e0  mov     ebx, eax
0x1800144e2  test    eax, eax
0x1800144e4  jns     short loc_180014535
0x1800144e6  mov     r8d, 914h
0x1800144ec  jmp     short loc_180014521
0x1800144ee  mov     rcx, [rcx+60h]; this
0x1800144f2  test    rcx, rcx
0x1800144f5  jnz     short loc_180014508
0x1800144f7  mov     r9d, 80004003h; unsigned __int16 *
0x1800144fd  mov     r8d, 91Ch; unsigned __int16 *
0x180014503  mov     ebx, r9d
0x180014506  jmp     short loc_180014524
0x180014508  mov     [rsp+38h+var_18], rdx; unsigned __int16 *
0x18001450d  mov     rdx, r10; unsigned __int16 *
0x180014510  call    ?AddXmlToDebugReport@Rootcause@@QEAAJPEAG000@Z; Rootcause::AddXmlToDebugReport(ushort *,ushort *,ushort *,ushort *)
0x180014515  mov     ebx, eax
0x180014517  test    eax, eax
0x180014519  jns     short loc_180014535
0x18001451b  mov     r8d, 91Eh; int
0x180014521  mov     r9d, eax; int
0x180014524  lea     rdx, aDiagpackageAdd; "DiagPackage::AddXmlToDebugReport"
0x18001452b  mov     ecx, 1; Level
0x180014530  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180014535  mov     eax, ebx
0x180014537  add     rsp, 30h
0x18001453b  pop     rbx
0x18001453c  retn
```
