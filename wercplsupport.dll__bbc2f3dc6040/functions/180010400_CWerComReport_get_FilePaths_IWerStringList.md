# CWerComReport::_get_FilePaths(IWerStringList * *)

- ea: `0x180010400`
- end: `0x1800104ff`
- name: `?_get_FilePaths@CWerComReport@@QEAAJPEAPEAUIWerStringList@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, struct IWerStringList **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180011500`

## callees

- `0x180001634`
- `0x180002850`
- `0x180006c9c`
- `0x1800073d4`
- `0x180010400`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CWerComReport::_get_FilePaths(CWerComReport *this, struct IWerStringList **a2)
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
    *(_QWORD *)v5 = &CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long WerpGetFilePathByIndex(void *,unsigned long,unsigned short const * *)>::`vftable'{for `CManagedObj'};
    *((_QWORD *)v5 + 3) = &CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long WerpGetFilePathByIndex(void *,unsigned long,unsigned short const * *)>::`vftable'{for `IWerStringList'};
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
        52,
        WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
        (unsigned int)v7);
    }
    (*(void (__fastcall **)(CManagedObj *))(*(_QWORD *)v5 + 16LL))(v5);
    return v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180010400  push    rbx
0x180010402  push    rbp
0x180010403  push    rsi
0x180010404  push    rdi
0x180010405  sub     rsp, 28h
0x180010409  mov     rsi, rcx
0x18001040c  mov     rbp, rdx
0x18001040f  mov     ecx, 30h ; '0'; Size
0x180010414  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010419  mov     rdi, rax
0x18001041c  test    rax, rax
0x18001041f  jz      loc_1800104C3
0x180010425  mov     rbx, [rsi+20h]
0x180010429  mov     rcx, rax; this
0x18001042c  call    ??0CManagedObj@@QEAA@XZ; CManagedObj::CManagedObj(void)
0x180010431  lea     rax, ??_7?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?WerpGetFilePathByIndex@@YAJ0KPEAPEBG@Z@@6BCManagedObj@@@; const CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&WerpGetFilePathByIndex(void *,ulong,ushort const * *)>::`vftable'{for `CManagedObj'}
0x180010438  mov     [rdi], rax
0x18001043b  lea     rax, ??_7?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?WerpGetFilePathByIndex@@YAJ0KPEAPEBG@Z@@6BIWerStringList@@@; const CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&WerpGetFilePathByIndex(void *,ulong,ushort const * *)>::`vftable'{for `IWerStringList'}
0x180010442  mov     [rdi+18h], rax
0x180010446  lock inc dword ptr [rdi+8]
0x18001044a  mov     [rdi+20h], rbx
0x18001044e  mov     rcx, rsi
0x180010451  mov     [rdi+28h], rsi
0x180010455  mov     rax, [rsi]
0x180010458  mov     rax, [rax+8]
0x18001045c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010461  mov     rax, [rdi]
0x180010464  lea     rdx, IID_IWerStringList
0x18001046b  mov     r8, rbp
0x18001046e  mov     rcx, rdi
0x180010471  mov     rax, [rax]
0x180010474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010479  mov     ebx, eax
0x18001047b  test    eax, eax
0x18001047d  jns     short loc_1800104B0
0x18001047f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010486  lea     rdx, WPP_GLOBAL_Control
0x18001048d  cmp     rcx, rdx
0x180010490  jz      short loc_1800104B0
0x180010492  test    byte ptr [rcx+1Ch], 1
0x180010496  jz      short loc_1800104B0
0x180010498  mov     rcx, [rcx+10h]
0x18001049c  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x1800104a3  mov     edx, 34h ; '4'
0x1800104a8  mov     r9d, eax
0x1800104ab  call    WPP_SF_d
0x1800104b0  mov     rax, [rdi]
0x1800104b3  mov     rcx, rdi
0x1800104b6  mov     rax, [rax+10h]
0x1800104ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104bf  mov     eax, ebx
0x1800104c1  jmp     short loc_1800104F6
0x1800104c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104ca  lea     rdx, WPP_GLOBAL_Control
0x1800104d1  cmp     rcx, rdx
0x1800104d4  jz      short loc_1800104F1
0x1800104d6  test    byte ptr [rcx+1Ch], 1
0x1800104da  jz      short loc_1800104F1
0x1800104dc  mov     rcx, [rcx+10h]
0x1800104e0  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x1800104e7  mov     edx, 33h ; '3'
0x1800104ec  call    WPP_SF_
0x1800104f1  mov     eax, 8007000Eh
0x1800104f6  add     rsp, 28h
0x1800104fa  pop     rdi
0x1800104fb  pop     rsi
0x1800104fc  pop     rbp
0x1800104fd  pop     rbx
0x1800104fe  retn
```
