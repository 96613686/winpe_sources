# CWerComReport::_get_SignatureParameters(IWerKeyValueList * *)

- ea: `0x180010c08`
- end: `0x180010d07`
- name: `?_get_SignatureParameters@CWerComReport@@QEAAJPEAPEAUIWerKeyValueList@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, struct IWerKeyValueList **)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800119e0`

## callees

- `0x180001634`
- `0x180002850`
- `0x180006c9c`
- `0x1800073d4`
- `0x180010c08`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CWerComReport::_get_SignatureParameters(CWerComReport *this, struct IWerKeyValueList **a2)
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
    *(_QWORD *)v5 = &CWerComReportKeyValueList<&long WerpGetNumSigParams(void *,unsigned long *),&long WerpGetSigParamByIndex(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::`vftable'{for `CManagedObj'};
    *((_QWORD *)v5 + 3) = &CWerComReportKeyValueList<&long WerpGetNumSigParams(void *,unsigned long *),&long WerpGetSigParamByIndex(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::`vftable'{for `IWerKeyValueList'};
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
        34,
        WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
        (unsigned int)v7);
    }
    (*(void (__fastcall **)(CManagedObj *))(*(_QWORD *)v5 + 16LL))(v5);
    return v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180010c08  push    rbx
0x180010c0a  push    rbp
0x180010c0b  push    rsi
0x180010c0c  push    rdi
0x180010c0d  sub     rsp, 28h
0x180010c11  mov     rsi, rcx
0x180010c14  mov     rbp, rdx
0x180010c17  mov     ecx, 30h ; '0'; Size
0x180010c1c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010c21  mov     rdi, rax
0x180010c24  test    rax, rax
0x180010c27  jz      loc_180010CCB
0x180010c2d  mov     rbx, [rsi+20h]
0x180010c31  mov     rcx, rax; this
0x180010c34  call    ??0CManagedObj@@QEAA@XZ; CManagedObj::CManagedObj(void)
0x180010c39  lea     rax, ??_7?$CWerComReportKeyValueList@$1?WerpGetNumSigParams@@YAJPEAXPEAK@Z$1?WerpGetSigParamByIndex@@YAJ0KPEAPEBG2@Z@@6BCManagedObj@@@; const CWerComReportKeyValueList<&WerpGetNumSigParams(void *,ulong *),&WerpGetSigParamByIndex(void *,ulong,ushort const * *,ushort const * *)>::`vftable'{for `CManagedObj'}
0x180010c40  mov     [rdi], rax
0x180010c43  lea     rax, ??_7?$CWerComReportKeyValueList@$1?WerpGetNumSigParams@@YAJPEAXPEAK@Z$1?WerpGetSigParamByIndex@@YAJ0KPEAPEBG2@Z@@6BIWerKeyValueList@@@; const CWerComReportKeyValueList<&WerpGetNumSigParams(void *,ulong *),&WerpGetSigParamByIndex(void *,ulong,ushort const * *,ushort const * *)>::`vftable'{for `IWerKeyValueList'}
0x180010c4a  mov     [rdi+18h], rax
0x180010c4e  lock inc dword ptr [rdi+8]
0x180010c52  mov     [rdi+20h], rbx
0x180010c56  mov     rcx, rsi
0x180010c59  mov     [rdi+28h], rsi
0x180010c5d  mov     rax, [rsi]
0x180010c60  mov     rax, [rax+8]
0x180010c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c69  mov     rax, [rdi]
0x180010c6c  lea     rdx, IID_IWerKeyValueList
0x180010c73  mov     r8, rbp
0x180010c76  mov     rcx, rdi
0x180010c79  mov     rax, [rax]
0x180010c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c81  mov     ebx, eax
0x180010c83  test    eax, eax
0x180010c85  jns     short loc_180010CB8
0x180010c87  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c8e  lea     rdx, WPP_GLOBAL_Control
0x180010c95  cmp     rcx, rdx
0x180010c98  jz      short loc_180010CB8
0x180010c9a  test    byte ptr [rcx+1Ch], 1
0x180010c9e  jz      short loc_180010CB8
0x180010ca0  mov     rcx, [rcx+10h]
0x180010ca4  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x180010cab  mov     edx, 22h ; '"'
0x180010cb0  mov     r9d, eax
0x180010cb3  call    WPP_SF_d
0x180010cb8  mov     rax, [rdi]
0x180010cbb  mov     rcx, rdi
0x180010cbe  mov     rax, [rax+10h]
0x180010cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cc7  mov     eax, ebx
0x180010cc9  jmp     short loc_180010CFE
0x180010ccb  mov     rcx, cs:WPP_GLOBAL_Control
0x180010cd2  lea     rdx, WPP_GLOBAL_Control
0x180010cd9  cmp     rcx, rdx
0x180010cdc  jz      short loc_180010CF9
0x180010cde  test    byte ptr [rcx+1Ch], 1
0x180010ce2  jz      short loc_180010CF9
0x180010ce4  mov     rcx, [rcx+10h]
0x180010ce8  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x180010cef  mov     edx, 21h ; '!'
0x180010cf4  call    WPP_SF_
0x180010cf9  mov     eax, 8007000Eh
0x180010cfe  add     rsp, 28h
0x180010d02  pop     rdi
0x180010d03  pop     rsi
0x180010d04  pop     rbp
0x180010d05  pop     rbx
0x180010d06  retn
```
