# CVisRgnTrackerProp::UpdateTrackerRegion(ulong,uint)

- ea: `0x14001f460`
- end: `0x14001f82f`
- name: `?UpdateTrackerRegion@CVisRgnTrackerProp@@AEAAXKI@Z`
- size: `975`
- prototype: `void(CVisRgnTrackerProp *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001f3a4`

## callees

- `0x14001e768`
- `0x14001f460`
- `0x140020cf0`
- `0x140020d30`
- `0x140020e0c`
- `0x140085998`
- `0x1400bcaa0`
- `0x14016ad40`
- `0x140255e20`
- `0x140341ff0`
- `0x140342540`

## import_xrefs

- `ntoskrnl!PsGetProcessWin32Process` at `0x14001f79e`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14001f79e`
- `win32kbase!GreEqualRgn` at `0x14001f636`
- `win32kbase!GreEqualRgn` at `0x14001f636`
- `win32kbase!EtwTraceDwmVisRgnUpdate` at `0x14001f5be`
- `win32kbase!EtwTraceDwmVisRgnUpdate` at `0x14001f5be`
- `win32kbase!GreGetRegionData` at `0x14001f6a8`
- `win32kbase!GreGetRegionData` at `0x14001f6ce`
- `win32kbase!GreGetRegionData` at `0x14001f6a8`
- `win32kbase!GreGetRegionData` at `0x14001f6ce`
- `win32kbase!GreSetRegionOwner` at `0x14001f58c`
- `win32kbase!GreSetRegionOwner` at `0x14001f61a`
- `win32kbase!GreSetRegionOwner` at `0x14001f7c1`
- `win32kbase!GreSetRegionOwner` at `0x14001f58c`
- `win32kbase!GreSetRegionOwner` at `0x14001f61a`
- `win32kbase!GreSetRegionOwner` at `0x14001f7c1`
- `win32kbase!CreateEmptyRgn` at `0x14001f499`
- `win32kbase!CreateEmptyRgn` at `0x14001f75a`
- `win32kbase!CreateEmptyRgn` at `0x14001f499`
- `win32kbase!CreateEmptyRgn` at `0x14001f75a`
- `win32kbase!GreCombineRgn` at `0x14001f778`
- `win32kbase!GreCombineRgn` at `0x14001f778`
- `win32kbase!GreDeleteObject` at `0x14001f573`
- `win32kbase!GreDeleteObject` at `0x14001f66a`
- `win32kbase!GreDeleteObject` at `0x14001f732`
- `win32kbase!GreDeleteObject` at `0x14001f80f`
- `win32kbase!GreDeleteObject` at `0x14001f573`
- `win32kbase!GreDeleteObject` at `0x14001f66a`
- `win32kbase!GreDeleteObject` at `0x14001f732`
- `win32kbase!GreDeleteObject` at `0x14001f80f`
- `win32kbase!DereferenceDwmProcess` at `0x14001f7f8`
- `win32kbase!DereferenceDwmProcess` at `0x14001f7f8`
- `win32kbase!ReferenceDwmProcess` at `0x14001f78c`
- `win32kbase!ReferenceDwmProcess` at `0x14001f78c`
- `win32kbase!ReferenceDwmApiPort` at `0x14001f701`
- `win32kbase!ReferenceDwmApiPort` at `0x14001f7d8`
- `win32kbase!ReferenceDwmApiPort` at `0x14001f701`
- `win32kbase!ReferenceDwmApiPort` at `0x14001f7d8`

## pseudocode

```c
void __fastcall CVisRgnTrackerProp::UpdateTrackerRegion(CVisRgnTrackerProp *this, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r13
  unsigned int v5; // ebx
  __int64 v7; // r14
  HRGN v8; // r12
  HRGN EmptyRgn; // rax
  HRGN v10; // rdi
  struct tagWND *v11; // rbp
  HRGN v12; // rsi
  unsigned int v13; // ebx
  int v14; // ecx
  int WindowRgn; // eax
  bool VisRgn; // bl
  const struct tagWND *TopLevelWindow; // rax
  _QWORD *v18; // rcx
  _QWORD *v19; // rdx
  unsigned int RegionData; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  void *v25; // rax
  __int64 v26; // rbp
  __int64 v27; // r14
  __int64 ProcessWin32Process; // rax
  void *v29; // rax
  char v30[8]; // [rsp+30h] [rbp-268h] BYREF
  int v31; // [rsp+38h] [rbp-260h]
  __int128 v32; // [rsp+50h] [rbp-248h]

  v4 = (unsigned int)a3;
  v5 = a2;
  v7 = (unsigned int)a3;
  v8 = (HRGN)*((_QWORD *)this + (unsigned int)a3 + 6);
  EmptyRgn = (HRGN)CreateEmptyRgn(this, a2, a3, a4);
  v10 = EmptyRgn;
  if ( !EmptyRgn )
    goto LABEL_16;
  v11 = (struct tagWND *)*((_QWORD *)this + 2);
  v12 = 0;
  if ( (_DWORD)v4 != 2 )
  {
    VisRgn = GetVisRgn(v11, v5, EmptyRgn);
    goto LABEL_20;
  }
  if ( (unsigned int)IsTopLevelWindow(v11) )
  {
    WindowRgn = GetWindowRgn(v11, v10, 0x20u);
    if ( !WindowRgn )
    {
      VisRgn = 0;
      GreDeleteObject(v10);
      v10 = 0;
      goto LABEL_20;
    }
  }
  else
  {
    v13 = 2 * (*(_BYTE *)(*((_QWORD *)v11 + 5) + 31LL) & 4 | 1);
    if ( PtiCurrent() )
    {
      if ( *((_QWORD *)PtiCurrent() + 61) )
      {
        if ( (*(_DWORD *)(**(_QWORD **)(*((_QWORD *)PtiCurrent() + 61) + 8LL) + 64LL) & 1) != 0 )
        {
          v14 = *(_DWORD *)(*((_QWORD *)v11 + 5) + 288LL);
          if ( (v14 & 0xF) == 0 && (v14 & 0x40000000) != 0 )
            v13 |= 0x20u;
        }
      }
    }
    WindowRgn = GetWindowRgn(v11, v10, v13);
  }
  VisRgn = 0;
  if ( WindowRgn == 1 )
  {
    TopLevelWindow = (const struct tagWND *)GetTopLevelWindow(v11);
    if ( TopLevelWindow )
      VisRgn = _GhostWindowFromHungWindow(TopLevelWindow) != 0;
  }
LABEL_20:
  if ( VisRgn )
  {
    if ( !v10 )
      goto LABEL_14;
    goto LABEL_13;
  }
  if ( v8 )
  {
    v12 = v8;
    GreSetRegionOwner(v8, 2147483650LL);
  }
  if ( v10 )
  {
    if ( v12 && (unsigned int)GreEqualRgn(v10, v12) )
      goto LABEL_13;
  }
  else if ( !v12 )
  {
    goto LABEL_16;
  }
  memset_0(v30, 0, 0x220u);
  if ( !v10 )
    goto LABEL_41;
  RegionData = GreGetRegionData(v10, 0, 0);
  if ( RegionData <= 0x220 )
  {
    if ( RegionData )
    {
      if ( (unsigned int)GreGetRegionData(v10, RegionData, v30) )
      {
        if ( !v31 )
        {
          v31 = 1;
          v32 = 0;
        }
        goto LABEL_36;
      }
      goto LABEL_13;
    }
LABEL_41:
    v31 = 0;
LABEL_36:
    v25 = (void *)ReferenceDwmApiPort();
    DwmAsyncUpdateVisRgn(v25, v31);
LABEL_37:
    if ( v12 )
      GreDeleteObject(v12);
    *((_QWORD *)this + v7 + 6) = v10;
    v12 = v10;
    goto LABEL_14;
  }
  v26 = CreateEmptyRgn(v22, v21, v23, v24);
  if ( (unsigned int)GreCombineRgn(v26, v10, 0, 5) )
  {
    v27 = ReferenceDwmProcess();
    ProcessWin32Process = PsGetProcessWin32Process(v27);
    if ( ProcessWin32Process )
      ProcessWin32Process &= -(__int64)(*(_QWORD *)ProcessWin32Process != 0);
    if ( (unsigned int)GreSetRegionOwner(v26, *(unsigned int *)(ProcessWin32Process + 56)) )
    {
      v29 = (void *)ReferenceDwmApiPort();
      DwmAsyncUpdateLargeVisRgn(v29);
    }
    else
    {
      GreDeleteObject(v26);
    }
    DereferenceDwmProcess(v27);
    v7 = v4;
    goto LABEL_37;
  }
LABEL_13:
  GreDeleteObject(v10);
LABEL_14:
  if ( v12 )
    GreSetRegionOwner(v12, 2147483666LL);
LABEL_16:
  v18 = (_QWORD *)*((_QWORD *)this + 2);
  v19 = (_QWORD *)v18[13];
  if ( v19 )
    v19 = (_QWORD *)*v19;
  EtwTraceDwmVisRgnUpdate(*v18, v19, (unsigned int)v4, v8 != *((HRGN *)this + v7 + 6));
}

```

## disassembly

```asm
0x14001f460  mov     [rsp+arg_18], rbx
0x14001f465  push    rbp
0x14001f466  push    rsi
0x14001f467  push    rdi
0x14001f468  push    r12
0x14001f46a  push    r13
0x14001f46c  push    r14
0x14001f46e  push    r15
0x14001f470  sub     rsp, 260h
0x14001f477  mov     rax, cs:__security_cookie
0x14001f47e  xor     rax, rsp
0x14001f481  mov     [rsp+298h+var_48], rax
0x14001f489  mov     r13d, r8d
0x14001f48c  mov     ebx, edx
0x14001f48e  mov     r15, rcx
0x14001f491  mov     r14d, r8d
0x14001f494  mov     r12, [rcx+r13*8+30h]
0x14001f499  call    cs:__imp_CreateEmptyRgn
0x14001f4a0  nop     dword ptr [rax+rax+00h]
0x14001f4a5  mov     rdi, rax
0x14001f4a8  test    rax, rax
0x14001f4ab  jz      loc_14001F598
0x14001f4b1  mov     rbp, [r15+10h]
0x14001f4b5  xor     esi, esi
0x14001f4b7  mov     rcx, rbp; struct tagWND *
0x14001f4ba  cmp     r13d, 2
0x14001f4be  jnz     loc_14001F5F6
0x14001f4c4  call    _IsTopLevelWindow
0x14001f4c9  test    eax, eax
0x14001f4cb  jnz     loc_14001F64C
0x14001f4d1  mov     rax, [rbp+28h]
0x14001f4d5  movzx   ebx, byte ptr [rax+1Fh]
0x14001f4d9  and     ebx, 4
0x14001f4dc  or      ebx, 1
0x14001f4df  add     ebx, ebx
0x14001f4e1  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14001f4e6  test    rax, rax
0x14001f4e9  jz      short loc_14001F526
0x14001f4eb  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14001f4f0  cmp     [rax+1E8h], rsi
0x14001f4f7  jz      short loc_14001F526
0x14001f4f9  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14001f4fe  mov     rcx, [rax+1E8h]
0x14001f505  mov     rax, [rcx+8]
0x14001f509  mov     rcx, [rax]
0x14001f50c  mov     eax, [rcx+40h]
0x14001f50f  test    al, 1
0x14001f511  jz      short loc_14001F526
0x14001f513  mov     rax, [rbp+28h]
0x14001f517  mov     ecx, [rax+120h]
0x14001f51d  test    cl, 0Fh
0x14001f520  jz      loc_14001F81D
0x14001f526  mov     r8d, ebx; unsigned int
0x14001f529  mov     rdx, rdi; HRGN
0x14001f52c  mov     rcx, rbp; struct tagWND *
0x14001f52f  call    ?GetWindowRgn@@YAHPEAUtagWND@@PEAUHRGN__@@K@Z; GetWindowRgn(tagWND *,HRGN__ *,ulong)
0x14001f534  xor     bl, bl
0x14001f536  cmp     eax, 1
0x14001f539  jnz     loc_14001F602
0x14001f53f  mov     rcx, rbp
0x14001f542  call    _GetTopLevelWindow
0x14001f547  test    rax, rax
0x14001f54a  jz      loc_14001F602
0x14001f550  mov     rcx, rax; struct tagWND *
0x14001f553  call    ?_GhostWindowFromHungWindow@@YAPEAUtagWND@@PEBU1@@Z; _GhostWindowFromHungWindow(tagWND const *)
0x14001f558  test    rax, rax
0x14001f55b  movzx   ebx, bl
0x14001f55e  mov     eax, 1
0x14001f563  cmovnz  ebx, eax
0x14001f566  jmp     loc_14001F602
0x14001f56b  test    rdi, rdi
0x14001f56e  jz      short loc_14001F57F
0x14001f570  mov     rcx, rdi
0x14001f573  call    cs:__imp_GreDeleteObject
0x14001f57a  nop     dword ptr [rax+rax+00h]
0x14001f57f  test    rsi, rsi
0x14001f582  jz      short loc_14001F598
0x14001f584  mov     edx, 80000012h
0x14001f589  mov     rcx, rsi
0x14001f58c  call    cs:__imp_GreSetRegionOwner
0x14001f593  nop     dword ptr [rax+rax+00h]
0x14001f598  mov     rcx, [r15+10h]
0x14001f59c  xor     r9d, r9d
0x14001f59f  cmp     r12, [r15+r14*8+30h]
0x14001f5a4  setnz   r9b
0x14001f5a8  mov     rdx, [rcx+68h]
0x14001f5ac  test    rdx, rdx
0x14001f5af  jz      loc_14001F74B
0x14001f5b5  mov     rdx, [rdx]
0x14001f5b8  mov     rcx, [rcx]
0x14001f5bb  mov     r8d, r13d
0x14001f5be  call    cs:__imp_EtwTraceDwmVisRgnUpdate
0x14001f5c5  nop     dword ptr [rax+rax+00h]
0x14001f5ca  mov     rcx, [rsp+298h+var_48]
0x14001f5d2  xor     rcx, rsp; StackCookie
0x14001f5d5  call    __security_check_cookie
0x14001f5da  mov     rbx, [rsp+298h+arg_18]
0x14001f5e2  add     rsp, 260h
0x14001f5e9  pop     r15
0x14001f5eb  pop     r14
0x14001f5ed  pop     r13
0x14001f5ef  pop     r12
0x14001f5f1  pop     rdi
0x14001f5f2  pop     rsi
0x14001f5f3  pop     rbp
0x14001f5f4  retn
0x14001f5f6  mov     r8, rdi; HRGN
0x14001f5f9  mov     edx, ebx; unsigned int
0x14001f5fb  call    ?GetVisRgn@@YA_NPEAUtagWND@@KPEAUHRGN__@@@Z; GetVisRgn(tagWND *,ulong,HRGN__ *)
0x14001f600  mov     bl, al
0x14001f602  test    bl, bl
0x14001f604  jnz     loc_14001F56B
0x14001f60a  test    r12, r12
0x14001f60d  jz      short loc_14001F626
0x14001f60f  mov     edx, 80000002h
0x14001f614  mov     rcx, r12
0x14001f617  mov     rsi, r12
0x14001f61a  call    cs:__imp_GreSetRegionOwner
0x14001f621  nop     dword ptr [rax+rax+00h]
0x14001f626  test    rdi, rdi
0x14001f629  jz      short loc_14001F67A
0x14001f62b  test    rsi, rsi
0x14001f62e  jz      short loc_14001F683
0x14001f630  mov     rdx, rsi
0x14001f633  mov     rcx, rdi
0x14001f636  call    cs:__imp_GreEqualRgn
0x14001f63d  nop     dword ptr [rax+rax+00h]
0x14001f642  test    eax, eax
0x14001f644  jnz     loc_14001F570
0x14001f64a  jmp     short loc_14001F683
0x14001f64c  mov     r8d, 20h ; ' '; unsigned int
0x14001f652  mov     rdx, rdi; HRGN
0x14001f655  mov     rcx, rbp; struct tagWND *
0x14001f658  call    ?GetWindowRgn@@YAHPEAUtagWND@@PEAUHRGN__@@K@Z; GetWindowRgn(tagWND *,HRGN__ *,ulong)
0x14001f65d  test    eax, eax
0x14001f65f  jnz     loc_14001F534
0x14001f665  mov     rcx, rdi
0x14001f668  xor     bl, bl
0x14001f66a  call    cs:__imp_GreDeleteObject
0x14001f671  nop     dword ptr [rax+rax+00h]
0x14001f676  xor     edi, edi
0x14001f678  jmp     short loc_14001F602
0x14001f67a  test    rsi, rsi
0x14001f67d  jz      loc_14001F598
0x14001f683  mov     ebx, 220h
0x14001f688  lea     rcx, [rsp+298h+var_268]; void *
0x14001f68d  mov     r8d, ebx; Size
0x14001f690  xor     edx, edx; Val
0x14001f692  call    memset_0
0x14001f697  test    rdi, rdi
0x14001f69a  jz      loc_14001F750
0x14001f6a0  xor     r8d, r8d
0x14001f6a3  xor     edx, edx
0x14001f6a5  mov     rcx, rdi
0x14001f6a8  call    cs:__imp_GreGetRegionData
0x14001f6af  nop     dword ptr [rax+rax+00h]
0x14001f6b4  cmp     eax, ebx
0x14001f6b6  ja      loc_14001F75A
0x14001f6bc  test    eax, eax
0x14001f6be  jz      loc_14001F750
0x14001f6c4  lea     r8, [rsp+298h+var_268]
0x14001f6c9  mov     edx, eax
0x14001f6cb  mov     rcx, rdi
0x14001f6ce  call    cs:__imp_GreGetRegionData
0x14001f6d5  nop     dword ptr [rax+rax+00h]
0x14001f6da  test    eax, eax
0x14001f6dc  jz      loc_14001F570
0x14001f6e2  cmp     [rsp+298h+var_260], 0
0x14001f6e7  jnz     short loc_14001F6FA
0x14001f6e9  xorps   xmm0, xmm0
0x14001f6ec  mov     [rsp+298h+var_260], 1
0x14001f6f4  movdqa  [rsp+298h+var_248], xmm0
0x14001f6fa  mov     rax, [r15+10h]
0x14001f6fe  mov     rbx, [rax]
0x14001f701  call    cs:__imp_ReferenceDwmApiPort
0x14001f708  nop     dword ptr [rax+rax+00h]
0x14001f70d  mov     r8d, [rsp+298h+var_260]
0x14001f712  lea     r9, [rsp+298h+var_248]
0x14001f717  mov     [rsp+298h+var_278], r8d; int
0x14001f71c  mov     rdx, rbx
0x14001f71f  mov     r8d, r13d
0x14001f722  mov     rcx, rax; Object
0x14001f725  call    DwmAsyncUpdateVisRgn
0x14001f72a  test    rsi, rsi
0x14001f72d  jz      short loc_14001F73E
0x14001f72f  mov     rcx, rsi
0x14001f732  call    cs:__imp_GreDeleteObject
0x14001f739  nop     dword ptr [rax+rax+00h]
0x14001f73e  mov     [r15+r14*8+30h], rdi
0x14001f743  mov     rsi, rdi
0x14001f746  jmp     loc_14001F57F
0x14001f74b  jmp     loc_14001F5B8
0x14001f750  mov     [rsp+298h+var_260], 0
0x14001f758  jmp     short loc_14001F6FA
0x14001f75a  call    cs:__imp_CreateEmptyRgn
0x14001f761  nop     dword ptr [rax+rax+00h]
0x14001f766  mov     r9d, 5
0x14001f76c  xor     r8d, r8d
0x14001f76f  mov     rcx, rax
0x14001f772  mov     rdx, rdi
0x14001f775  mov     rbp, rax
0x14001f778  call    cs:__imp_GreCombineRgn
0x14001f77f  nop     dword ptr [rax+rax+00h]
0x14001f784  test    eax, eax
0x14001f786  jz      loc_14001F570
0x14001f78c  call    cs:__imp_ReferenceDwmProcess
0x14001f793  nop     dword ptr [rax+rax+00h]
0x14001f798  mov     rcx, rax
0x14001f79b  mov     r14, rax
0x14001f79e  call    cs:__imp_PsGetProcessWin32Process
0x14001f7a5  nop     dword ptr [rax+rax+00h]
0x14001f7aa  test    rax, rax
0x14001f7ad  jz      short loc_14001F7BB
0x14001f7af  mov     rcx, [rax]
0x14001f7b2  neg     rcx
0x14001f7b5  sbb     r8, r8
0x14001f7b8  and     rax, r8
0x14001f7bb  mov     edx, [rax+38h]
0x14001f7be  mov     rcx, rbp
0x14001f7c1  call    cs:__imp_GreSetRegionOwner
0x14001f7c8  nop     dword ptr [rax+rax+00h]
0x14001f7cd  test    eax, eax
0x14001f7cf  jz      short loc_14001F80C
0x14001f7d1  mov     rax, [r15+10h]
0x14001f7d5  mov     rbx, [rax]
0x14001f7d8  call    cs:__imp_ReferenceDwmApiPort
0x14001f7df  nop     dword ptr [rax+rax+00h]
0x14001f7e4  mov     r9, rbp
0x14001f7e7  mov     r8d, r13d
0x14001f7ea  mov     rcx, rax; Object
0x14001f7ed  mov     rdx, rbx
0x14001f7f0  call    DwmAsyncUpdateLargeVisRgn
0x14001f7f5  mov     rcx, r14
0x14001f7f8  call    cs:__imp_DereferenceDwmProcess
0x14001f7ff  nop     dword ptr [rax+rax+00h]
0x14001f804  mov     r14, r13
0x14001f807  jmp     loc_14001F72A
0x14001f80c  mov     rcx, rbp
0x14001f80f  call    cs:__imp_GreDeleteObject
0x14001f816  nop     dword ptr [rax+rax+00h]
0x14001f81b  jmp     short loc_14001F7F5
0x14001f81d  bt      ecx, 1Eh
0x14001f821  jnb     loc_14001F526
0x14001f827  or      ebx, 20h
0x14001f82a  jmp     loc_14001F526
```
