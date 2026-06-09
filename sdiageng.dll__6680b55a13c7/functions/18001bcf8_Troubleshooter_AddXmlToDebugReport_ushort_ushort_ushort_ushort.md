# Troubleshooter::AddXmlToDebugReport(ushort *,ushort *,ushort *,ushort *)

- ea: `0x18001bcf8`
- end: `0x18001bda6`
- name: `?AddXmlToDebugReport@Troubleshooter@@QEAAJPEAG000@Z`
- size: `174`
- prototype: `__int64 __fastcall(Troubleshooter *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014438`
- `0x180018510`

## callees

- `0x18001bcf8`
- `0x18001d470`
- `0x180026fa0`

## string_xrefs

- `0x18001bd8d`: `Troubleshooter::AddXmlToDebugReport`

## pseudocode

```c
__int64 __fastcall Troubleshooter::AddXmlToDebugReport(
        Troubleshooter *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  int v5; // r9d
  int v6; // r8d
  unsigned int v7; // ebx
  Script *v8; // rcx
  int v9; // eax

  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 284;
    v7 = -2147024809;
LABEL_13:
    SdpDebugTrace(1u, L"Troubleshooter::AddXmlToDebugReport", v6, v5);
    return v7;
  }
  if ( !a3 )
  {
    v5 = -2147024809;
    v6 = 285;
    v7 = -2147024809;
    goto LABEL_13;
  }
  if ( !a4 )
  {
    v5 = -2147024809;
    v6 = 286;
    v7 = -2147024809;
    goto LABEL_13;
  }
  if ( !a5 )
  {
    v5 = -2147024809;
    v6 = 287;
    v7 = -2147024809;
    goto LABEL_13;
  }
  v8 = (Script *)*((_QWORD *)this + 1);
  if ( !v8 )
  {
    v7 = -2147467261;
    v6 = 289;
    v5 = -2147467261;
    goto LABEL_13;
  }
  v9 = Script::AddXmlToDebugReport(v8, a2, a3, a4, a5);
  v7 = v9;
  if ( v9 < 0 )
  {
    v5 = v9;
    v6 = 291;
    goto LABEL_13;
  }
  return v7;
}

```

## disassembly

```asm
0x18001bcf8  push    rbx
0x18001bcfa  sub     rsp, 30h
0x18001bcfe  test    rdx, rdx
0x18001bd01  jnz     short loc_18001BD14
0x18001bd03  mov     r9d, 80070057h
0x18001bd09  mov     r8d, 11Ch
0x18001bd0f  mov     ebx, r9d
0x18001bd12  jmp     short loc_18001BD8D
0x18001bd14  test    r8, r8
0x18001bd17  jnz     short loc_18001BD2A
0x18001bd19  mov     r9d, 80070057h
0x18001bd1f  mov     r8d, 11Dh
0x18001bd25  mov     ebx, r9d
0x18001bd28  jmp     short loc_18001BD8D
0x18001bd2a  test    r9, r9
0x18001bd2d  jnz     short loc_18001BD40
0x18001bd2f  mov     r9d, 80070057h
0x18001bd35  mov     r8d, 11Eh
0x18001bd3b  mov     ebx, r9d
0x18001bd3e  jmp     short loc_18001BD8D
0x18001bd40  mov     rax, [rsp+38h+arg_20]
0x18001bd45  test    rax, rax
0x18001bd48  jnz     short loc_18001BD5B
0x18001bd4a  mov     r9d, 80070057h
0x18001bd50  mov     r8d, 11Fh
0x18001bd56  mov     ebx, r9d
0x18001bd59  jmp     short loc_18001BD8D
0x18001bd5b  mov     rcx, [rcx+8]; this
0x18001bd5f  test    rcx, rcx
0x18001bd62  jnz     short loc_18001BD74
0x18001bd64  mov     ebx, 80004003h
0x18001bd69  mov     r8d, 121h; unsigned __int16 *
0x18001bd6f  mov     r9d, ebx; unsigned __int16 *
0x18001bd72  jmp     short loc_18001BD8D
0x18001bd74  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18001bd79  call    ?AddXmlToDebugReport@Script@@QEAAJPEAG000@Z; Script::AddXmlToDebugReport(ushort *,ushort *,ushort *,ushort *)
0x18001bd7e  mov     ebx, eax
0x18001bd80  test    eax, eax
0x18001bd82  jns     short loc_18001BD9E
0x18001bd84  mov     r9d, eax; int
0x18001bd87  mov     r8d, 123h; int
0x18001bd8d  lea     rdx, aTroubleshooter_2; "Troubleshooter::AddXmlToDebugReport"
0x18001bd94  mov     ecx, 1; Level
0x18001bd99  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001bd9e  mov     eax, ebx
0x18001bda0  add     rsp, 30h
0x18001bda4  pop     rbx
0x18001bda5  retn
```
