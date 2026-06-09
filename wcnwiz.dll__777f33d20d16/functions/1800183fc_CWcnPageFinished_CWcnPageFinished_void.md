# CWcnPageFinished::~CWcnPageFinished(void)

- ea: `0x1800183fc`
- end: `0x1800184d5`
- name: `??1CWcnPageFinished@@QEAA@XZ`
- size: `217`
- prototype: `void __fastcall(CWcnPageFinished *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800031d8`
- `0x180003750`

## callees

- `0x180003b18`
- `0x18000d630`
- `0x1800183fc`
- `0x18002de1c`

## import_xrefs

- `GDI32!DeleteObject` at `0x180018458`
- `GDI32!DeleteObject` at `0x180018471`
- `GDI32!DeleteObject` at `0x18001848a`
- `GDI32!DeleteObject` at `0x180018458`
- `GDI32!DeleteObject` at `0x180018471`
- `GDI32!DeleteObject` at `0x18001848a`

## pseudocode

```c
void __fastcall CWcnPageFinished::~CWcnPageFinished(CWcnPageFinished *this)
{
  _BYTE *v2; // r10
  const char *Indent; // rax
  __int64 v4; // r10
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  const char *v8; // rax
  __int64 v9; // r10

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v4 + 16), 12, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids, Indent);
    v2 = WPP_GLOBAL_Control;
  }
  v5 = (void *)*((_QWORD *)this + 25);
  if ( v5 )
  {
    DeleteObject(v5);
    v2 = WPP_GLOBAL_Control;
  }
  v6 = (void *)*((_QWORD *)this + 27);
  if ( v6 )
  {
    DeleteObject(v6);
    v2 = WPP_GLOBAL_Control;
  }
  v7 = (void *)*((_QWORD *)this + 28);
  if ( v7 )
  {
    DeleteObject(v7);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 6u )
  {
    v8 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v9 + 16), 13, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids, v8);
  }
  CXWizardPageClass<CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,0>::~CXWizardPageClass<CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,0>(this);
}

```

## disassembly

```asm
0x1800183fc  mov     [rsp+arg_0], rbx
0x180018401  push    rdi
0x180018402  sub     rsp, 20h
0x180018406  mov     rbx, rcx
0x180018409  mov     r10, cs:WPP_GLOBAL_Control
0x180018410  lea     rdi, WPP_GLOBAL_Control
0x180018417  cmp     r10, rdi
0x18001841a  jz      short loc_18001844C
0x18001841c  cmp     byte ptr [r10+19h], 6
0x180018421  jb      short loc_18001844C
0x180018423  mov     ecx, 1; int
0x180018428  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001842d  mov     rcx, [r10+10h]
0x180018431  lea     r8, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids
0x180018438  mov     edx, 0Ch
0x18001843d  mov     r9, rax
0x180018440  call    WPP_SF_s
0x180018445  mov     r10, cs:WPP_GLOBAL_Control
0x18001844c  mov     rcx, [rbx+0C8h]; ho
0x180018453  test    rcx, rcx
0x180018456  jz      short loc_180018465
0x180018458  call    cs:__imp_DeleteObject
0x18001845e  mov     r10, cs:WPP_GLOBAL_Control
0x180018465  mov     rcx, [rbx+0D8h]; ho
0x18001846c  test    rcx, rcx
0x18001846f  jz      short loc_18001847E
0x180018471  call    cs:__imp_DeleteObject
0x180018477  mov     r10, cs:WPP_GLOBAL_Control
0x18001847e  mov     rcx, [rbx+0E0h]; ho
0x180018485  test    rcx, rcx
0x180018488  jz      short loc_180018497
0x18001848a  call    cs:__imp_DeleteObject
0x180018490  mov     r10, cs:WPP_GLOBAL_Control
0x180018497  cmp     r10, rdi
0x18001849a  jz      short loc_1800184C3
0x18001849c  cmp     byte ptr [r10+19h], 6
0x1800184a1  jb      short loc_1800184C3
0x1800184a3  or      ecx, 0FFFFFFFFh; int
0x1800184a6  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800184ab  mov     rcx, [r10+10h]
0x1800184af  lea     r8, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids
0x1800184b6  mov     edx, 0Dh
0x1800184bb  mov     r9, rax
0x1800184be  call    WPP_SF_s
0x1800184c3  mov     rcx, rbx
0x1800184c6  mov     rbx, [rsp+28h+arg_0]
0x1800184cb  add     rsp, 20h
0x1800184cf  pop     rdi
0x1800184d0  jmp     ??1?$CXWizardPageClass@VCWcnPageProfileUseExisting@@$1?CLSID_WcnPageProfileUseExisting@@3U_GUID@@B$0A@@@QEAA@XZ; CXWizardPageClass<CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,0>::~CXWizardPageClass<CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,0>(void)
```
