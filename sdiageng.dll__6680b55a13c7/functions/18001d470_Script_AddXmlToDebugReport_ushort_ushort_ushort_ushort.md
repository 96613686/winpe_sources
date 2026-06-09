# Script::AddXmlToDebugReport(ushort *,ushort *,ushort *,ushort *)

- ea: `0x18001d470`
- end: `0x18001d53e`
- name: `?AddXmlToDebugReport@Script@@QEAAJPEAG000@Z`
- size: `206`
- prototype: `__int64 __fastcall(Script *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180018510`
- `0x18001bcf8`

## callees

- `0x180004d58`
- `0x18001d470`
- `0x180026fa0`

## string_xrefs

- `0x18001d525`: `Script::AddXmlToDebugReport`

## pseudocode

```c
__int64 __fastcall Script::AddXmlToDebugReport(
        Script *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  int v6; // r9d
  int v7; // r8d
  unsigned int v8; // ebx
  struct IXMLDOMDocument2 *v9; // rdx
  int updated; // eax

  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = 660;
    v8 = -2147024809;
LABEL_13:
    SdpDebugTrace(1u, L"Script::AddXmlToDebugReport", v7, v6);
    return v8;
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    v7 = 661;
    v8 = -2147024809;
    goto LABEL_13;
  }
  if ( !a4 )
  {
    v6 = -2147024809;
    v7 = 662;
    v8 = -2147024809;
    goto LABEL_13;
  }
  if ( !a5 )
  {
    v6 = -2147024809;
    v7 = 663;
    v8 = -2147024809;
    goto LABEL_13;
  }
  v9 = (struct IXMLDOMDocument2 *)*((_QWORD *)this + 6);
  if ( !v9 )
  {
    v8 = -2147467261;
    v7 = 665;
    v6 = -2147467261;
    goto LABEL_13;
  }
  updated = SdpUpdateReportData(*(struct Settings **)this, v9, a5, a2, a3, a4, L"Debug");
  v8 = updated;
  if ( updated < 0 )
  {
    v6 = updated;
    v7 = 678;
    goto LABEL_13;
  }
  return v8;
}

```

## disassembly

```asm
0x18001d470  push    rbx
0x18001d472  sub     rsp, 40h
0x18001d476  mov     rax, r8
0x18001d479  mov     r10, rdx
0x18001d47c  test    rdx, rdx
0x18001d47f  jnz     short loc_18001D495
0x18001d481  mov     r9d, 80070057h
0x18001d487  mov     r8d, 294h
0x18001d48d  mov     ebx, r9d
0x18001d490  jmp     loc_18001D525
0x18001d495  test    rax, rax
0x18001d498  jnz     short loc_18001D4AB
0x18001d49a  mov     r9d, 80070057h
0x18001d4a0  mov     r8d, 295h
0x18001d4a6  mov     ebx, r9d
0x18001d4a9  jmp     short loc_18001D525
0x18001d4ab  test    r9, r9
0x18001d4ae  jnz     short loc_18001D4C1
0x18001d4b0  mov     r9d, 80070057h
0x18001d4b6  mov     r8d, 296h
0x18001d4bc  mov     ebx, r9d
0x18001d4bf  jmp     short loc_18001D525
0x18001d4c1  mov     r8, [rsp+48h+arg_20]; unsigned __int16 *
0x18001d4c6  test    r8, r8
0x18001d4c9  jnz     short loc_18001D4DC
0x18001d4cb  mov     r9d, 80070057h
0x18001d4d1  mov     r8d, 297h
0x18001d4d7  mov     ebx, r9d
0x18001d4da  jmp     short loc_18001D525
0x18001d4dc  mov     rdx, [rcx+30h]; struct IXMLDOMDocument2 *
0x18001d4e0  test    rdx, rdx
0x18001d4e3  jnz     short loc_18001D4F5
0x18001d4e5  mov     ebx, 80004003h
0x18001d4ea  mov     r8d, 299h
0x18001d4f0  mov     r9d, ebx
0x18001d4f3  jmp     short loc_18001D525
0x18001d4f5  mov     rcx, [rcx]; struct Settings *
0x18001d4f8  lea     r11, aDebug; "Debug"
0x18001d4ff  mov     [rsp+48h+var_18], r11; unsigned __int16 *
0x18001d504  mov     [rsp+48h+var_20], r9; unsigned __int16 *
0x18001d509  mov     r9, r10; unsigned __int16 *
0x18001d50c  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18001d511  call    ?SdpUpdateReportData@@YAJPEAVSettings@@PEAUIXMLDOMDocument2@@PEAG2222@Z; SdpUpdateReportData(Settings *,IXMLDOMDocument2 *,ushort *,ushort *,ushort *,ushort *,ushort *)
0x18001d516  mov     ebx, eax
0x18001d518  test    eax, eax
0x18001d51a  jns     short loc_18001D536
0x18001d51c  mov     r9d, eax; int
0x18001d51f  mov     r8d, 2A6h; int
0x18001d525  lea     rdx, aScriptAddxmlto; "Script::AddXmlToDebugReport"
0x18001d52c  mov     ecx, 1; Level
0x18001d531  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001d536  mov     eax, ebx
0x18001d538  add     rsp, 40h
0x18001d53c  pop     rbx
0x18001d53d  retn
```
