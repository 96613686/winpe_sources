# CWerComReport::_get_FileNames(IWerStringList * *)

- ea: `0x1800102f8`
- end: `0x1800103f7`
- name: `?_get_FileNames@CWerComReport@@QEAAJPEAPEAUIWerStringList@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, struct IWerStringList **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800114a0`

## callees

- `0x180001634`
- `0x180002850`
- `0x180006c9c`
- `0x1800073d4`
- `0x1800102f8`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CWerComReport::_get_FileNames(CWerComReport *this, struct IWerStringList **a2)
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
    *(_QWORD *)v5 = &CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long GetFileNameByIndex(void *,unsigned long,unsigned short const * *)>::`vftable'{for `CManagedObj'};
    *((_QWORD *)v5 + 3) = &CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long GetFileNameByIndex(void *,unsigned long,unsigned short const * *)>::`vftable'{for `IWerStringList'};
    _InterlockedIncrement((volatile signed __int32 *)v5 + 2);
    *((_QWORD *)v5 + 4) = v6;
    *((_QWORD *)v5 + 5) = this;
    (*(void (__fastcall **)(CWerComReport *))(*(_QWORD *)this + 8LL))(this);
    v7 = (**(__int64 (__fastcall ***)(CManagedObj *, GUID *, struct IWerStringList **))v5)(v5, &IID_IWerStringList, a2);
    v8 = v7;
    if ( v7 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
        (unsigned int)v7);
    }
    (*(void (__fastcall **)(CManagedObj *))(*(_QWORD *)v5 + 16LL))(v5);
    return v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800102f8  push    rbx
0x1800102fa  push    rbp
0x1800102fb  push    rsi
0x1800102fc  push    rdi
0x1800102fd  sub     rsp, 28h
0x180010301  mov     rsi, rcx
0x180010304  mov     rbp, rdx
0x180010307  mov     ecx, 30h ; '0'; Size
0x18001030c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010311  mov     rdi, rax
0x180010314  test    rax, rax
0x180010317  jz      loc_1800103BB
0x18001031d  mov     rbx, [rsi+20h]
0x180010321  mov     rcx, rax; this
0x180010324  call    ??0CManagedObj@@QEAA@XZ; CManagedObj::CManagedObj(void)
0x180010329  lea     rax, ??_7?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?GetFileNameByIndex@@YAJ0KPEAPEBG@Z@@6BCManagedObj@@@; const CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&GetFileNameByIndex(void *,ulong,ushort const * *)>::`vftable'{for `CManagedObj'}
0x180010330  mov     [rdi], rax
0x180010333  lea     rax, ??_7?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?GetFileNameByIndex@@YAJ0KPEAPEBG@Z@@6BIWerStringList@@@; const CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&GetFileNameByIndex(void *,ulong,ushort const * *)>::`vftable'{for `IWerStringList'}
0x18001033a  mov     [rdi+18h], rax
0x18001033e  lock inc dword ptr [rdi+8]
0x180010342  mov     [rdi+20h], rbx
0x180010346  mov     rcx, rsi
0x180010349  mov     [rdi+28h], rsi
0x18001034d  mov     rax, [rsi]
0x180010350  mov     rax, [rax+8]
0x180010354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010359  mov     rax, [rdi]
0x18001035c  lea     rdx, IID_IWerStringList
0x180010363  mov     r8, rbp
0x180010366  mov     rcx, rdi
0x180010369  mov     rax, [rax]
0x18001036c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010371  mov     ebx, eax
0x180010373  test    eax, eax
0x180010375  jns     short loc_1800103A8
0x180010377  mov     rcx, cs:WPP_GLOBAL_Control
0x18001037e  lea     rdx, WPP_GLOBAL_Control
0x180010385  cmp     rcx, rdx
0x180010388  jz      short loc_1800103A8
0x18001038a  test    byte ptr [rcx+1Ch], 1
0x18001038e  jz      short loc_1800103A8
0x180010390  mov     rcx, [rcx+10h]
0x180010394  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18001039b  mov     edx, 32h ; '2'
0x1800103a0  mov     r9d, eax
0x1800103a3  call    WPP_SF_d
0x1800103a8  mov     rax, [rdi]
0x1800103ab  mov     rcx, rdi
0x1800103ae  mov     rax, [rax+10h]
0x1800103b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103b7  mov     eax, ebx
0x1800103b9  jmp     short loc_1800103EE
0x1800103bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103c2  lea     rdx, WPP_GLOBAL_Control
0x1800103c9  cmp     rcx, rdx
0x1800103cc  jz      short loc_1800103E9
0x1800103ce  test    byte ptr [rcx+1Ch], 1
0x1800103d2  jz      short loc_1800103E9
0x1800103d4  mov     rcx, [rcx+10h]
0x1800103d8  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x1800103df  mov     edx, 31h ; '1'
0x1800103e4  call    WPP_SF_
0x1800103e9  mov     eax, 8007000Eh
0x1800103ee  add     rsp, 28h
0x1800103f2  pop     rdi
0x1800103f3  pop     rsi
0x1800103f4  pop     rbp
0x1800103f5  pop     rbx
0x1800103f6  retn
```
