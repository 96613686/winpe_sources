# SrvNetUpdateVolatileForceDisableRdmaSupport

- ea: `0x1400156b4`
- end: `0x140015789`
- name: `SrvNetUpdateVolatileForceDisableRdmaSupport`
- size: `213`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140014cd0`
- `0x140014d20`
- `0x140014f70`

## callees

- `0x140009264`
- `0x140013ebc`
- `0x1400156b4`
- `0x1400157c0`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x140015700`
- `ntoskrnl!IoGetActivityIdThread` at `0x140015700`

## pseudocode

```c
unsigned __int8 __fastcall SrvNetUpdateVolatileForceDisableRdmaSupport(char a1)
{
  char v1; // r8
  int v2; // r14d
  unsigned __int8 v3; // di
  int v4; // ebp
  __int64 v5; // r8
  unsigned __int8 v6; // cl
  int v7; // r15d
  unsigned int v8; // r12d
  char v9; // bl
  int ActivityIdThread; // eax
  int v11; // edx
  int v12; // ecx

  v1 = SrvNetVolatileForceDisableRdmaSupport;
  SrvNetVolatileForceDisableRdmaSupport = a1;
  v2 = (unsigned __int8)SrvNetEnableRdmaSupport;
  v3 = a1 != v1;
  v4 = (unsigned __int8)SrvNetEvaluateRdmaEnabledPolicy();
  v7 = v6;
  v8 = (unsigned __int8)v5;
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
  {
    v9 = SrvNetIsSMBDirectSupported;
    ActivityIdThread = IoGetActivityIdThread();
    McTemplateK0tttttt_EtwWriteTransfer(v12, v11, ActivityIdThread, v8, v7, v2, v4, v9, v3);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_DDDDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      (unsigned __int8)SrvNetIsSMBDirectSupported,
      v5,
      v8,
      v7,
      v2,
      v4,
      (unsigned __int8)SrvNetIsSMBDirectSupported,
      v3);
  }
  return v3;
}

```

## disassembly

```asm
0x1400156b4  push    rbx
0x1400156b6  push    rbp
0x1400156b7  push    rsi
0x1400156b8  push    rdi
0x1400156b9  push    r12
0x1400156bb  push    r14
0x1400156bd  push    r15
0x1400156bf  sub     rsp, 50h
0x1400156c3  mov     r8b, cl
0x1400156c6  xchg    r8b, cs:SrvNetVolatileForceDisableRdmaSupport
0x1400156cd  movzx   r14d, cs:SrvNetEnableRdmaSupport
0x1400156d5  cmp     cl, r8b
0x1400156d8  setnz   dil
0x1400156dc  call    SrvNetEvaluateRdmaEnabledPolicy
0x1400156e1  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 10h
0x1400156e8  movzx   esi, dil
0x1400156ec  movzx   ebp, al
0x1400156ef  movzx   r15d, cl
0x1400156f3  movzx   r12d, r8b
0x1400156f7  jz      short loc_14001572D
0x1400156f9  movzx   ebx, cs:SrvNetIsSMBDirectSupported
0x140015700  call    cs:__imp_IoGetActivityIdThread
0x140015707  nop     dword ptr [rax+rax+00h]
0x14001570c  mov     [rsp+88h+var_48], esi
0x140015710  mov     r9d, r12d
0x140015713  mov     [rsp+88h+var_50], ebx
0x140015717  mov     r8, rax
0x14001571a  mov     [rsp+88h+var_58], ebp
0x14001571e  mov     [rsp+88h+var_60], r14d
0x140015723  mov     [rsp+88h+var_68], r15d
0x140015728  call    McTemplateK0tttttt_EtwWriteTransfer
0x14001572d  mov     rcx, cs:WPP_GLOBAL_Control
0x140015734  lea     rax, WPP_GLOBAL_Control
0x14001573b  cmp     rcx, rax
0x14001573e  jz      short loc_140015776
0x140015740  mov     eax, [rcx+2Ch]
0x140015743  test    al, 10h
0x140015745  jz      short loc_140015776
0x140015747  cmp     byte ptr [rcx+29h], 2
0x14001574b  jb      short loc_140015776
0x14001574d  movzx   edx, cs:SrvNetIsSMBDirectSupported
0x140015754  mov     r9d, r12d
0x140015757  mov     rcx, [rcx+18h]
0x14001575b  mov     [rsp+88h+var_48], esi
0x14001575f  mov     [rsp+88h+var_50], edx
0x140015763  mov     [rsp+88h+var_58], ebp
0x140015767  mov     [rsp+88h+var_60], r14d
0x14001576c  mov     [rsp+88h+var_68], r15d
0x140015771  call    WPP_SF_DDDDDD
0x140015776  mov     al, dil
0x140015779  add     rsp, 50h
0x14001577d  pop     r15
0x14001577f  pop     r14
0x140015781  pop     r12
0x140015783  pop     rdi
0x140015784  pop     rsi
0x140015785  pop     rbp
0x140015786  pop     rbx
0x140015787  retn
```
