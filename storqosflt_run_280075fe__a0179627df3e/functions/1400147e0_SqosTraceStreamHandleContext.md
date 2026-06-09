# SqosTraceStreamHandleContext

- ea: `0x1400147e0`
- end: `0x1400148df`
- name: `SqosTraceStreamHandleContext`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140006188`

## callees

- `0x140008880`
- `0x1400147e0`

## import_xrefs

- `FLTMGR!FltReleaseFileNameInformation` at `0x1400148ce`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400148ce`
- `FLTMGR!FltGetFileNameInformation` at `0x140014834`
- `FLTMGR!FltGetFileNameInformation` at `0x140014834`

## string_xrefs

- `0x140014884`: `Created`

## pseudocode

```c
void __fastcall SqosTraceStreamHandleContext(struct _FLT_CALLBACK_DATA *a1, __int64 a2, __int64 a3, char a4)
{
  UNICODE_STRING *p_Name; // r10
  const char *v8; // r9
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-18h] BYREF

  FileNameInformation = 0;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    FltGetFileNameInformation(a1, 0x401u, &FileNameInformation);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      p_Name = (UNICODE_STRING *)&NAME_NOT_AVAILABLE;
      if ( FileNameInformation )
        p_Name = &FileNameInformation->Name;
      v8 = "Created";
      if ( !a4 )
        v8 = "Modified";
      WPP_SF_sqZ_guid_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        *(unsigned __int8 *)(a3 + 32),
        *(unsigned __int8 *)(*(_QWORD *)(a3 + 16) + 124LL),
        (_DWORD)v8,
        *(_QWORD *)(a2 + 32),
        (__int64)p_Name,
        *(_QWORD *)(a3 + 16) + 88LL,
        *(_BYTE *)(*(_QWORD *)(a3 + 16) + 124LL),
        *(_BYTE *)(a3 + 32));
    }
    if ( FileNameInformation )
      FltReleaseFileNameInformation(FileNameInformation);
  }
}

```

## disassembly

```asm
0x1400147e0  mov     [rsp+arg_0], rbx
0x1400147e5  mov     [rsp+arg_8], rsi
0x1400147ea  push    rdi
0x1400147eb  sub     rsp, 60h
0x1400147ef  mov     rax, cs:WPP_GLOBAL_Control
0x1400147f6  movzx   edi, r9b
0x1400147fa  mov     [rsp+68h+FileNameInformation], 0
0x140014803  mov     rbx, r8
0x140014806  mov     rsi, rdx
0x140014809  mov     r10d, [rax+2Ch]
0x14001480d  test    r10b, 10h
0x140014811  jnz     short loc_140014824
0x140014813  mov     rbx, [rsp+68h+arg_0]
0x140014818  mov     rsi, [rsp+68h+arg_8]
0x14001481d  add     rsp, 60h
0x140014821  pop     rdi
0x140014822  retn
0x140014824  cmp     byte ptr [rax+29h], 4
0x140014828  jb      short loc_140014813
0x14001482a  lea     r8, [rsp+68h+FileNameInformation]; FileNameInformation
0x14001482f  mov     edx, 401h; NameOptions
0x140014834  call    cs:__imp_FltGetFileNameInformation
0x14001483b  nop     dword ptr [rax+rax+00h]
0x140014840  mov     rcx, cs:WPP_GLOBAL_Control
0x140014847  lea     rax, WPP_GLOBAL_Control
0x14001484e  cmp     rcx, rax
0x140014851  jz      short loc_1400148C0
0x140014853  mov     eax, [rcx+2Ch]
0x140014856  test    al, 10h
0x140014858  jz      short loc_1400148C0
0x14001485a  cmp     byte ptr [rcx+29h], 4
0x14001485e  jb      short loc_1400148C0
0x140014860  mov     rax, [rsp+68h+FileNameInformation]
0x140014865  lea     r10, NAME_NOT_AVAILABLE
0x14001486c  test    rax, rax
0x14001486f  jz      short loc_140014875
0x140014871  lea     r10, [rax+8]
0x140014875  mov     rax, [rbx+10h]
0x140014879  lea     r11, aModified; "Modified"
0x140014880  movzx   edx, byte ptr [rbx+20h]
0x140014884  lea     r9, aCreated; "Created"
0x14001488b  mov     rcx, [rcx+18h]
0x14001488f  mov     [rsp+68h+var_28], edx
0x140014893  movzx   r8d, byte ptr [rax+7Ch]
0x140014898  add     rax, 58h ; 'X'
0x14001489c  mov     [rsp+68h+var_30], r8d
0x1400148a1  test    dil, dil
0x1400148a4  mov     [rsp+68h+var_38], rax
0x1400148a9  mov     rax, [rsi+20h]
0x1400148ad  cmovz   r9, r11
0x1400148b1  mov     [rsp+68h+var_40], r10
0x1400148b6  mov     [rsp+68h+var_48], rax
0x1400148bb  call    WPP_SF_sqZ_guid_DD
0x1400148c0  mov     rcx, [rsp+68h+FileNameInformation]; FileNameInformation
0x1400148c5  test    rcx, rcx
0x1400148c8  jz      loc_140014813
0x1400148ce  call    cs:__imp_FltReleaseFileNameInformation
0x1400148d5  nop     dword ptr [rax+rax+00h]
0x1400148da  jmp     loc_140014813
```
