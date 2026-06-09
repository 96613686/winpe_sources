# BaseConnection::~BaseConnection(void)

- ea: `0x18005d7f4`
- end: `0x18005d914`
- name: `??1BaseConnection@@MEAA@XZ`
- size: `288`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000c6b4`
- `0x18005d920`
- `0x180077d5f`

## callees

- `0x180007794`
- `0x18005d7f4`
- `0x18005d958`
- `0x18005dfcc`
- `0x1800768d4`
- `0x180076b60`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005d8c7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005d8c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall BaseConnection::~BaseConnection(struct _RTL_CRITICAL_SECTION *this)
{
  void (__fastcall ***SpinCount)(_QWORD, __int64); // rcx
  __int64 v3; // [rsp+20h] [rbp-48h] BYREF
  __int128 v4; // [rsp+28h] [rbp-40h]
  __int128 v5; // [rsp+38h] [rbp-30h]
  __int64 v6; // [rsp+48h] [rbp-20h]
  int v7; // [rsp+50h] [rbp-18h]
  int v8; // [rsp+54h] [rbp-14h]

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&BaseConnection::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_123f18666a7d3e7863aedd9beb21868e_Traceguids);
  v4 = 0;
  v3 = 0;
  v5 = 0;
  v6 = 0;
  v7 = -1;
  v8 = 0;
  if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v3,
      L"BaseConnection::~BaseConnection",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))BaseTraceFunction);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash>::GetImpl'::`2'::impl) )
  {
    SpinCount = (void (__fastcall ***)(_QWORD, __int64))this[2].SpinCount;
    if ( SpinCount )
    {
      (**SpinCount)(SpinCount, 1);
      this[2].SpinCount = 0;
    }
    DeleteCriticalSection(this + 4);
  }
  else
  {
    BaseConnection::Cleanup((BaseConnection *)this);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_123f18666a7d3e7863aedd9beb21868e_Traceguids);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v3);
}

```

## disassembly

```asm
0x18005d7f4  mov     [rsp+arg_0], rbx
0x18005d7f9  push    rsi
0x18005d7fa  sub     rsp, 60h
0x18005d7fe  mov     rbx, rcx
0x18005d801  lea     rax, ??_7BaseConnection@@6B@; const BaseConnection::`vftable'
0x18005d808  mov     [rcx], rax
0x18005d80b  lea     rsi, WPP_GLOBAL_Control
0x18005d812  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d819  cmp     rcx, rsi
0x18005d81c  jz      short loc_18005D839
0x18005d81e  test    byte ptr [rcx+1Ch], 4
0x18005d822  jz      short loc_18005D839
0x18005d824  mov     edx, 1Ah
0x18005d829  lea     r8, WPP_123f18666a7d3e7863aedd9beb21868e_Traceguids
0x18005d830  mov     rcx, [rcx+10h]
0x18005d834  call    WPP_SF_
0x18005d839  xorps   xmm0, xmm0
0x18005d83c  movdqu  [rsp+68h+var_40], xmm0
0x18005d842  mov     [rsp+68h+var_48], 0
0x18005d84b  movdqu  [rsp+68h+var_30], xmm0
0x18005d851  mov     [rsp+68h+var_20], 0
0x18005d85a  mov     [rsp+68h+var_18], 0FFFFFFFFh
0x18005d862  mov     [rsp+68h+var_14], 0
0x18005d86a  cmp     qword ptr cs:xmmword_1800AABC0+8, 0
0x18005d872  jz      short loc_18005D88F
0x18005d874  lea     r9, ?BaseTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18005d87b  xor     r8d, r8d; unsigned int *
0x18005d87e  lea     rdx, aBaseconnection_3; "BaseConnection::~BaseConnection"
0x18005d885  lea     rcx, [rsp+68h+var_48]; this
0x18005d88a  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18005d88f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash> `wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash>::GetImpl(void)'::`2'::impl
0x18005d896  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash>::__private_IsEnabled(void)
0x18005d89b  test    al, al
0x18005d89d  jz      short loc_18005D8CF
0x18005d89f  mov     rcx, [rbx+70h]
0x18005d8a3  test    rcx, rcx
0x18005d8a6  jz      short loc_18005D8C0
0x18005d8a8  mov     rax, [rcx]
0x18005d8ab  mov     edx, 1
0x18005d8b0  mov     rax, [rax]
0x18005d8b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d8b8  mov     qword ptr [rbx+70h], 0
0x18005d8c0  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x18005d8c7  call    cs:__imp_DeleteCriticalSection
0x18005d8cd  jmp     short loc_18005D8D7
0x18005d8cf  mov     rcx, rbx; this
0x18005d8d2  call    ?Cleanup@BaseConnection@@IEAAXXZ; BaseConnection::Cleanup(void)
0x18005d8d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d8de  cmp     rcx, rsi
0x18005d8e1  jz      short loc_18005D8FE
0x18005d8e3  test    byte ptr [rcx+1Ch], 4
0x18005d8e7  jz      short loc_18005D8FE
0x18005d8e9  mov     edx, 1Bh
0x18005d8ee  lea     r8, WPP_123f18666a7d3e7863aedd9beb21868e_Traceguids
0x18005d8f5  mov     rcx, [rcx+10h]
0x18005d8f9  call    WPP_SF_
0x18005d8fe  lea     rcx, [rsp+68h+var_48]; this
0x18005d903  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18005d908  nop
0x18005d909  mov     rbx, [rsp+68h+arg_0]
0x18005d90e  add     rsp, 60h
0x18005d912  pop     rsi
0x18005d913  retn
```
