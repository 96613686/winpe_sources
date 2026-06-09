# CWerComReport::_get_DynamicSignatureParameters(IWerKeyValueList * *)

- ea: `0x1800100b4`
- end: `0x1800101b3`
- name: `?_get_DynamicSignatureParameters@CWerComReport@@QEAAJPEAPEAUIWerKeyValueList@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, struct IWerKeyValueList **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800113e0`

## callees

- `0x180001634`
- `0x180002850`
- `0x180006c9c`
- `0x1800073d4`
- `0x1800100b4`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CWerComReport::_get_DynamicSignatureParameters(CWerComReport *this, struct IWerKeyValueList **a2)
{
  CManagedObj *v4; // rax
  CManagedObj *v5; // rdi
  __int64 v6; // rbx
  int v7; // eax
  unsigned int v8; // ebx

  v4 = (CManagedObj *)operator new(0x30u);
  v5 = v4;
  if ( v4 )
  {
    v6 = *((_QWORD *)this + 4);
    CManagedObj::CManagedObj(v4);
    *(_QWORD *)v5 = &CWerComReportKeyValueList<&long WerComListConstCountFunc<54>(void *,unsigned long *),&long WerpGetDynamicParameter(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::`vftable'{for `CManagedObj'};
    *((_QWORD *)v5 + 3) = &CWerComReportKeyValueList<&long WerComListConstCountFunc<54>(void *,unsigned long *),&long WerpGetDynamicParameter(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::`vftable'{for `IWerKeyValueList'};
    _InterlockedIncrement((volatile signed __int32 *)v5 + 2);
    *((_QWORD *)v5 + 4) = v6;
    *((_QWORD *)v5 + 5) = this;
    (*(void (__fastcall **)(CWerComReport *))(*(_QWORD *)this + 8LL))(this);
    v7 = (**(__int64 (__fastcall ***)(CManagedObj *, GUID *, struct IWerKeyValueList **))v5)(
           v5,
           &IID_IWerKeyValueList,
           a2);
    v8 = v7;
    if ( v7 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
        (unsigned int)v7);
    }
    (*(void (__fastcall **)(CManagedObj *))(*(_QWORD *)v5 + 16LL))(v5);
    return v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800100b4  push    rbx
0x1800100b6  push    rbp
0x1800100b7  push    rsi
0x1800100b8  push    rdi
0x1800100b9  sub     rsp, 28h
0x1800100bd  mov     rsi, rcx
0x1800100c0  mov     rbp, rdx
0x1800100c3  mov     ecx, 30h ; '0'; Size
0x1800100c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800100cd  mov     rdi, rax
0x1800100d0  test    rax, rax
0x1800100d3  jz      loc_180010177
0x1800100d9  mov     rbx, [rsi+20h]
0x1800100dd  mov     rcx, rax; this
0x1800100e0  call    ??0CManagedObj@@QEAA@XZ; CManagedObj::CManagedObj(void)
0x1800100e5  lea     rax, ??_7?$CWerComReportKeyValueList@$1??$WerComListConstCountFunc@$0DG@@@YAJPEAXPEAK@Z$1?WerpGetDynamicParameter@@YAJ0KPEAPEBG2@Z@@6BCManagedObj@@@; const CWerComReportKeyValueList<&WerComListConstCountFunc<54>(void *,ulong *),&WerpGetDynamicParameter(void *,ulong,ushort const * *,ushort const * *)>::`vftable'{for `CManagedObj'}
0x1800100ec  mov     [rdi], rax
0x1800100ef  lea     rax, ??_7?$CWerComReportKeyValueList@$1??$WerComListConstCountFunc@$0DG@@@YAJPEAXPEAK@Z$1?WerpGetDynamicParameter@@YAJ0KPEAPEBG2@Z@@6BIWerKeyValueList@@@; const CWerComReportKeyValueList<&WerComListConstCountFunc<54>(void *,ulong *),&WerpGetDynamicParameter(void *,ulong,ushort const * *,ushort const * *)>::`vftable'{for `IWerKeyValueList'}
0x1800100f6  mov     [rdi+18h], rax
0x1800100fa  lock inc dword ptr [rdi+8]
0x1800100fe  mov     [rdi+20h], rbx
0x180010102  mov     rcx, rsi
0x180010105  mov     [rdi+28h], rsi
0x180010109  mov     rax, [rsi]
0x18001010c  mov     rax, [rax+8]
0x180010110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010115  mov     rax, [rdi]
0x180010118  lea     rdx, IID_IWerKeyValueList
0x18001011f  mov     r8, rbp
0x180010122  mov     rcx, rdi
0x180010125  mov     rax, [rax]
0x180010128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001012d  mov     ebx, eax
0x18001012f  test    eax, eax
0x180010131  jns     short loc_180010164
0x180010133  mov     rcx, cs:WPP_GLOBAL_Control
0x18001013a  lea     rdx, WPP_GLOBAL_Control
0x180010141  cmp     rcx, rdx
0x180010144  jz      short loc_180010164
0x180010146  test    byte ptr [rcx+1Ch], 1
0x18001014a  jz      short loc_180010164
0x18001014c  mov     rcx, [rcx+10h]
0x180010150  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x180010157  mov     edx, 24h ; '$'
0x18001015c  mov     r9d, eax
0x18001015f  call    WPP_SF_d
0x180010164  mov     rax, [rdi]
0x180010167  mov     rcx, rdi
0x18001016a  mov     rax, [rax+10h]
0x18001016e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010173  mov     eax, ebx
0x180010175  jmp     short loc_1800101AA
0x180010177  mov     rcx, cs:WPP_GLOBAL_Control
0x18001017e  lea     rdx, WPP_GLOBAL_Control
0x180010185  cmp     rcx, rdx
0x180010188  jz      short loc_1800101A5
0x18001018a  test    byte ptr [rcx+1Ch], 1
0x18001018e  jz      short loc_1800101A5
0x180010190  mov     rcx, [rcx+10h]
0x180010194  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18001019b  mov     edx, 23h ; '#'
0x1800101a0  call    WPP_SF_
0x1800101a5  mov     eax, 8007000Eh
0x1800101aa  add     rsp, 28h
0x1800101ae  pop     rdi
0x1800101af  pop     rsi
0x1800101b0  pop     rbp
0x1800101b1  pop     rbx
0x1800101b2  retn
```
