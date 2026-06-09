# SqosInstanceTeardownComplete

- ea: `0x140012990`
- end: `0x140012a63`
- name: `SqosInstanceTeardownComplete`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000666c`
- `0x1400083b4`
- `0x140011c5c`
- `0x140012990`

## import_xrefs

- `FLTMGR!FltDeleteInstanceContext` at `0x140012a1a`
- `FLTMGR!FltDeleteInstanceContext` at `0x140012a1a`
- `FLTMGR!FltReleaseContext` at `0x140012a08`
- `FLTMGR!FltReleaseContext` at `0x140012a08`
- `FLTMGR!FltGetInstanceContext` at `0x1400129e9`
- `FLTMGR!FltGetInstanceContext` at `0x1400129e9`

## pseudocode

```c
NTSTATUS __fastcall SqosInstanceTeardownComplete(__int64 a1, unsigned int a2)
{
  NTSTATUS result; // eax
  PFLT_CONTEXT Context; // [rsp+40h] [rbp+8h] BYREF

  Context = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 24, a2, *(_QWORD *)(a1 + 16), a2);
  }
  if ( FltGetInstanceContext(*(PFLT_INSTANCE *)(a1 + 24), &Context) >= 0 )
  {
    SqospRemoveDevice(Context);
    FltReleaseContext(Context);
  }
  result = FltDeleteInstanceContext(*(PFLT_INSTANCE *)(a1 + 24), 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      return WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_97d16c38264433ff5e04fa48b3a3652b_Traceguids, 0);
  }
  return result;
}

```

## disassembly

```asm
0x140012990  mov     [rsp+arg_8], rbx
0x140012995  push    rdi
0x140012996  sub     rsp, 30h
0x14001299a  mov     r8d, edx
0x14001299d  mov     [rsp+38h+Context], 0
0x1400129a6  mov     rbx, rcx
0x1400129a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400129b0  lea     rdi, WPP_GLOBAL_Control
0x1400129b7  cmp     rcx, rdi
0x1400129ba  jz      short loc_1400129E0
0x1400129bc  mov     eax, [rcx+2Ch]
0x1400129bf  test    al, 2
0x1400129c1  jz      short loc_1400129E0
0x1400129c3  cmp     byte ptr [rcx+29h], 5
0x1400129c7  jb      short loc_1400129E0
0x1400129c9  mov     r9, [rbx+10h]
0x1400129cd  mov     edx, 18h
0x1400129d2  mov     rcx, [rcx+18h]
0x1400129d6  mov     [rsp+38h+var_18], r8d
0x1400129db  call    WPP_SF_qD
0x1400129e0  mov     rcx, [rbx+18h]; Instance
0x1400129e4  lea     rdx, [rsp+38h+Context]; Context
0x1400129e9  call    cs:__imp_FltGetInstanceContext
0x1400129f0  nop     dword ptr [rax+rax+00h]
0x1400129f5  test    eax, eax
0x1400129f7  js      short loc_140012A14
0x1400129f9  mov     rcx, [rsp+38h+Context]
0x1400129fe  call    SqospRemoveDevice
0x140012a03  mov     rcx, [rsp+38h+Context]; Context
0x140012a08  call    cs:__imp_FltReleaseContext
0x140012a0f  nop     dword ptr [rax+rax+00h]
0x140012a14  mov     rcx, [rbx+18h]; Instance
0x140012a18  xor     edx, edx; OldContext
0x140012a1a  call    cs:__imp_FltDeleteInstanceContext
0x140012a21  nop     dword ptr [rax+rax+00h]
0x140012a26  mov     rcx, cs:WPP_GLOBAL_Control
0x140012a2d  cmp     rcx, rdi
0x140012a30  jz      short loc_140012A57
0x140012a32  mov     eax, [rcx+2Ch]
0x140012a35  test    al, 2
0x140012a37  jz      short loc_140012A57
0x140012a39  cmp     byte ptr [rcx+29h], 5
0x140012a3d  jb      short loc_140012A57
0x140012a3f  mov     rcx, [rcx+18h]
0x140012a43  lea     r8, WPP_97d16c38264433ff5e04fa48b3a3652b_Traceguids
0x140012a4a  mov     edx, 19h
0x140012a4f  xor     r9d, r9d
0x140012a52  call    WPP_SF_d
0x140012a57  mov     rbx, [rsp+38h+arg_8]
0x140012a5c  add     rsp, 30h
0x140012a60  pop     rdi
0x140012a61  retn
```
