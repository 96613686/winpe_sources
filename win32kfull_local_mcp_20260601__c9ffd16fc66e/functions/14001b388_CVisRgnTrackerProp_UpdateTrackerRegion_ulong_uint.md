# CVisRgnTrackerProp::UpdateTrackerRegion(ulong,uint)

- ea: `0x14001b388`
- end: `0x14001b757`
- name: `?UpdateTrackerRegion@CVisRgnTrackerProp@@AEAAXKI@Z`
- size: `975`
- prototype: `void(CVisRgnTrackerProp *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001b2cc`

## callees

- `0x1400191c8`
- `0x14001b230`
- `0x14001b388`
- `0x14001b82c`
- `0x14001b9c0`
- `0x1400299a0`
- `0x1400e2cb0`
- `0x1401db5bc`
- `0x1402576f0`
- `0x140342fa0`
- `0x140343500`

## import_xrefs

- `ntoskrnl!PsGetProcessWin32Process` at `0x14001b6c6`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14001b6c6`
- `win32kbase!GreEqualRgn` at `0x14001b55e`
- `win32kbase!GreEqualRgn` at `0x14001b55e`
- `win32kbase!EtwTraceDwmVisRgnUpdate` at `0x14001b4e6`
- `win32kbase!EtwTraceDwmVisRgnUpdate` at `0x14001b4e6`
- `win32kbase!GreGetRegionData` at `0x14001b5d0`
- `win32kbase!GreGetRegionData` at `0x14001b5f6`
- `win32kbase!GreGetRegionData` at `0x14001b5d0`
- `win32kbase!GreGetRegionData` at `0x14001b5f6`
- `win32kbase!GreSetRegionOwner` at `0x14001b4b4`
- `win32kbase!GreSetRegionOwner` at `0x14001b542`
- `win32kbase!GreSetRegionOwner` at `0x14001b6e9`
- `win32kbase!GreSetRegionOwner` at `0x14001b4b4`
- `win32kbase!GreSetRegionOwner` at `0x14001b542`
- `win32kbase!GreSetRegionOwner` at `0x14001b6e9`
- `win32kbase!CreateEmptyRgn` at `0x14001b3c1`
- `win32kbase!CreateEmptyRgn` at `0x14001b682`
- `win32kbase!CreateEmptyRgn` at `0x14001b3c1`
- `win32kbase!CreateEmptyRgn` at `0x14001b682`
- `win32kbase!GreCombineRgn` at `0x14001b6a0`
- `win32kbase!GreCombineRgn` at `0x14001b6a0`
- `win32kbase!GreDeleteObject` at `0x14001b49b`
- `win32kbase!GreDeleteObject` at `0x14001b592`
- `win32kbase!GreDeleteObject` at `0x14001b65a`
- `win32kbase!GreDeleteObject` at `0x14001b737`
- `win32kbase!GreDeleteObject` at `0x14001b49b`
- `win32kbase!GreDeleteObject` at `0x14001b592`
- `win32kbase!GreDeleteObject` at `0x14001b65a`
- `win32kbase!GreDeleteObject` at `0x14001b737`
- `win32kbase!DereferenceDwmProcess` at `0x14001b720`
- `win32kbase!DereferenceDwmProcess` at `0x14001b720`
- `win32kbase!ReferenceDwmProcess` at `0x14001b6b4`
- `win32kbase!ReferenceDwmProcess` at `0x14001b6b4`
- `win32kbase!ReferenceDwmApiPort` at `0x14001b629`
- `win32kbase!ReferenceDwmApiPort` at `0x14001b700`
- `win32kbase!ReferenceDwmApiPort` at `0x14001b629`
- `win32kbase!ReferenceDwmApiPort` at `0x14001b700`

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
0x14001b388  mov     [rsp+arg_18], rbx
0x14001b38d  push    rbp
0x14001b38e  push    rsi
0x14001b38f  push    rdi
0x14001b390  push    r12
0x14001b392  push    r13
0x14001b394  push    r14
0x14001b396  push    r15
0x14001b398  sub     rsp, 260h
0x14001b39f  mov     rax, cs:__security_cookie
0x14001b3a6  xor     rax, rsp
0x14001b3a9  mov     [rsp+298h+var_48], rax
0x14001b3b1  mov     r13d, r8d
0x14001b3b4  mov     ebx, edx
0x14001b3b6  mov     r15, rcx
0x14001b3b9  mov     r14d, r8d
0x14001b3bc  mov     r12, [rcx+r13*8+30h]
0x14001b3c1  call    cs:__imp_CreateEmptyRgn
0x14001b3c8  nop     dword ptr [rax+rax+00h]
0x14001b3cd  mov     rdi, rax
0x14001b3d0  test    rax, rax
0x14001b3d3  jz      loc_14001B4C0
0x14001b3d9  mov     rbp, [r15+10h]
0x14001b3dd  xor     esi, esi
0x14001b3df  mov     rcx, rbp; struct tagWND *
0x14001b3e2  cmp     r13d, 2
0x14001b3e6  jnz     loc_14001B51E
0x14001b3ec  call    _IsTopLevelWindow
0x14001b3f1  test    eax, eax
0x14001b3f3  jnz     loc_14001B574
0x14001b3f9  mov     rax, [rbp+28h]
0x14001b3fd  movzx   ebx, byte ptr [rax+1Fh]
0x14001b401  and     ebx, 4
0x14001b404  or      ebx, 1
0x14001b407  add     ebx, ebx
0x14001b409  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14001b40e  test    rax, rax
0x14001b411  jz      short loc_14001B44E
0x14001b413  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14001b418  cmp     [rax+1E8h], rsi
0x14001b41f  jz      short loc_14001B44E
0x14001b421  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14001b426  mov     rcx, [rax+1E8h]
0x14001b42d  mov     rax, [rcx+8]
0x14001b431  mov     rcx, [rax]
0x14001b434  mov     eax, [rcx+40h]
0x14001b437  test    al, 1
0x14001b439  jz      short loc_14001B44E
0x14001b43b  mov     rax, [rbp+28h]
0x14001b43f  mov     ecx, [rax+120h]
0x14001b445  test    cl, 0Fh
0x14001b448  jz      loc_14001B745
0x14001b44e  mov     r8d, ebx; unsigned int
0x14001b451  mov     rdx, rdi; HRGN
0x14001b454  mov     rcx, rbp; struct tagWND *
0x14001b457  call    ?GetWindowRgn@@YAHPEAUtagWND@@PEAUHRGN__@@K@Z; GetWindowRgn(tagWND *,HRGN__ *,ulong)
0x14001b45c  xor     bl, bl
0x14001b45e  cmp     eax, 1
0x14001b461  jnz     loc_14001B52A
0x14001b467  mov     rcx, rbp
0x14001b46a  call    _GetTopLevelWindow
0x14001b46f  test    rax, rax
0x14001b472  jz      loc_14001B52A
0x14001b478  mov     rcx, rax; struct tagWND *
0x14001b47b  call    ?_GhostWindowFromHungWindow@@YAPEAUtagWND@@PEBU1@@Z; _GhostWindowFromHungWindow(tagWND const *)
0x14001b480  test    rax, rax
0x14001b483  movzx   ebx, bl
0x14001b486  mov     eax, 1
0x14001b48b  cmovnz  ebx, eax
0x14001b48e  jmp     loc_14001B52A
0x14001b493  test    rdi, rdi
0x14001b496  jz      short loc_14001B4A7
0x14001b498  mov     rcx, rdi
0x14001b49b  call    cs:__imp_GreDeleteObject
0x14001b4a2  nop     dword ptr [rax+rax+00h]
0x14001b4a7  test    rsi, rsi
0x14001b4aa  jz      short loc_14001B4C0
0x14001b4ac  mov     edx, 80000012h
0x14001b4b1  mov     rcx, rsi
0x14001b4b4  call    cs:__imp_GreSetRegionOwner
0x14001b4bb  nop     dword ptr [rax+rax+00h]
0x14001b4c0  mov     rcx, [r15+10h]
0x14001b4c4  xor     r9d, r9d
0x14001b4c7  cmp     r12, [r15+r14*8+30h]
0x14001b4cc  setnz   r9b
0x14001b4d0  mov     rdx, [rcx+68h]
0x14001b4d4  test    rdx, rdx
0x14001b4d7  jz      loc_14001B673
0x14001b4dd  mov     rdx, [rdx]
0x14001b4e0  mov     rcx, [rcx]
0x14001b4e3  mov     r8d, r13d
0x14001b4e6  call    cs:__imp_EtwTraceDwmVisRgnUpdate
0x14001b4ed  nop     dword ptr [rax+rax+00h]
0x14001b4f2  mov     rcx, [rsp+298h+var_48]
0x14001b4fa  xor     rcx, rsp; StackCookie
0x14001b4fd  call    __security_check_cookie
0x14001b502  mov     rbx, [rsp+298h+arg_18]
0x14001b50a  add     rsp, 260h
0x14001b511  pop     r15
0x14001b513  pop     r14
0x14001b515  pop     r13
0x14001b517  pop     r12
0x14001b519  pop     rdi
0x14001b51a  pop     rsi
0x14001b51b  pop     rbp
0x14001b51c  retn
0x14001b51e  mov     r8, rdi; HRGN
0x14001b521  mov     edx, ebx; unsigned int
0x14001b523  call    ?GetVisRgn@@YA_NPEAUtagWND@@KPEAUHRGN__@@@Z; GetVisRgn(tagWND *,ulong,HRGN__ *)
0x14001b528  mov     bl, al
0x14001b52a  test    bl, bl
0x14001b52c  jnz     loc_14001B493
0x14001b532  test    r12, r12
0x14001b535  jz      short loc_14001B54E
0x14001b537  mov     edx, 80000002h
0x14001b53c  mov     rcx, r12
0x14001b53f  mov     rsi, r12
0x14001b542  call    cs:__imp_GreSetRegionOwner
0x14001b549  nop     dword ptr [rax+rax+00h]
0x14001b54e  test    rdi, rdi
0x14001b551  jz      short loc_14001B5A2
0x14001b553  test    rsi, rsi
0x14001b556  jz      short loc_14001B5AB
0x14001b558  mov     rdx, rsi
0x14001b55b  mov     rcx, rdi
0x14001b55e  call    cs:__imp_GreEqualRgn
0x14001b565  nop     dword ptr [rax+rax+00h]
0x14001b56a  test    eax, eax
0x14001b56c  jnz     loc_14001B498
0x14001b572  jmp     short loc_14001B5AB
0x14001b574  mov     r8d, 20h ; ' '; unsigned int
0x14001b57a  mov     rdx, rdi; HRGN
0x14001b57d  mov     rcx, rbp; struct tagWND *
0x14001b580  call    ?GetWindowRgn@@YAHPEAUtagWND@@PEAUHRGN__@@K@Z; GetWindowRgn(tagWND *,HRGN__ *,ulong)
0x14001b585  test    eax, eax
0x14001b587  jnz     loc_14001B45C
0x14001b58d  mov     rcx, rdi
0x14001b590  xor     bl, bl
0x14001b592  call    cs:__imp_GreDeleteObject
0x14001b599  nop     dword ptr [rax+rax+00h]
0x14001b59e  xor     edi, edi
0x14001b5a0  jmp     short loc_14001B52A
0x14001b5a2  test    rsi, rsi
0x14001b5a5  jz      loc_14001B4C0
0x14001b5ab  mov     ebx, 220h
0x14001b5b0  lea     rcx, [rsp+298h+var_268]; void *
0x14001b5b5  mov     r8d, ebx; Size
0x14001b5b8  xor     edx, edx; Val
0x14001b5ba  call    memset_0
0x14001b5bf  test    rdi, rdi
0x14001b5c2  jz      loc_14001B678
0x14001b5c8  xor     r8d, r8d
0x14001b5cb  xor     edx, edx
0x14001b5cd  mov     rcx, rdi
0x14001b5d0  call    cs:__imp_GreGetRegionData
0x14001b5d7  nop     dword ptr [rax+rax+00h]
0x14001b5dc  cmp     eax, ebx
0x14001b5de  ja      loc_14001B682
0x14001b5e4  test    eax, eax
0x14001b5e6  jz      loc_14001B678
0x14001b5ec  lea     r8, [rsp+298h+var_268]
0x14001b5f1  mov     edx, eax
0x14001b5f3  mov     rcx, rdi
0x14001b5f6  call    cs:__imp_GreGetRegionData
0x14001b5fd  nop     dword ptr [rax+rax+00h]
0x14001b602  test    eax, eax
0x14001b604  jz      loc_14001B498
0x14001b60a  cmp     [rsp+298h+var_260], 0
0x14001b60f  jnz     short loc_14001B622
0x14001b611  xorps   xmm0, xmm0
0x14001b614  mov     [rsp+298h+var_260], 1
0x14001b61c  movdqa  [rsp+298h+var_248], xmm0
0x14001b622  mov     rax, [r15+10h]
0x14001b626  mov     rbx, [rax]
0x14001b629  call    cs:__imp_ReferenceDwmApiPort
0x14001b630  nop     dword ptr [rax+rax+00h]
0x14001b635  mov     r8d, [rsp+298h+var_260]
0x14001b63a  lea     r9, [rsp+298h+var_248]
0x14001b63f  mov     [rsp+298h+var_278], r8d; int
0x14001b644  mov     rdx, rbx
0x14001b647  mov     r8d, r13d
0x14001b64a  mov     rcx, rax; Object
0x14001b64d  call    DwmAsyncUpdateVisRgn
0x14001b652  test    rsi, rsi
0x14001b655  jz      short loc_14001B666
0x14001b657  mov     rcx, rsi
0x14001b65a  call    cs:__imp_GreDeleteObject
0x14001b661  nop     dword ptr [rax+rax+00h]
0x14001b666  mov     [r15+r14*8+30h], rdi
0x14001b66b  mov     rsi, rdi
0x14001b66e  jmp     loc_14001B4A7
0x14001b673  jmp     loc_14001B4E0
0x14001b678  mov     [rsp+298h+var_260], 0
0x14001b680  jmp     short loc_14001B622
0x14001b682  call    cs:__imp_CreateEmptyRgn
0x14001b689  nop     dword ptr [rax+rax+00h]
0x14001b68e  mov     r9d, 5
0x14001b694  xor     r8d, r8d
0x14001b697  mov     rcx, rax
0x14001b69a  mov     rdx, rdi
0x14001b69d  mov     rbp, rax
0x14001b6a0  call    cs:__imp_GreCombineRgn
0x14001b6a7  nop     dword ptr [rax+rax+00h]
0x14001b6ac  test    eax, eax
0x14001b6ae  jz      loc_14001B498
0x14001b6b4  call    cs:__imp_ReferenceDwmProcess
0x14001b6bb  nop     dword ptr [rax+rax+00h]
0x14001b6c0  mov     rcx, rax
0x14001b6c3  mov     r14, rax
0x14001b6c6  call    cs:__imp_PsGetProcessWin32Process
0x14001b6cd  nop     dword ptr [rax+rax+00h]
0x14001b6d2  test    rax, rax
0x14001b6d5  jz      short loc_14001B6E3
0x14001b6d7  mov     rcx, [rax]
0x14001b6da  neg     rcx
0x14001b6dd  sbb     r8, r8
0x14001b6e0  and     rax, r8
0x14001b6e3  mov     edx, [rax+38h]
0x14001b6e6  mov     rcx, rbp
0x14001b6e9  call    cs:__imp_GreSetRegionOwner
0x14001b6f0  nop     dword ptr [rax+rax+00h]
0x14001b6f5  test    eax, eax
0x14001b6f7  jz      short loc_14001B734
0x14001b6f9  mov     rax, [r15+10h]
0x14001b6fd  mov     rbx, [rax]
0x14001b700  call    cs:__imp_ReferenceDwmApiPort
0x14001b707  nop     dword ptr [rax+rax+00h]
0x14001b70c  mov     r9, rbp
0x14001b70f  mov     r8d, r13d
0x14001b712  mov     rcx, rax; Object
0x14001b715  mov     rdx, rbx
0x14001b718  call    DwmAsyncUpdateLargeVisRgn
0x14001b71d  mov     rcx, r14
0x14001b720  call    cs:__imp_DereferenceDwmProcess
0x14001b727  nop     dword ptr [rax+rax+00h]
0x14001b72c  mov     r14, r13
0x14001b72f  jmp     loc_14001B652
0x14001b734  mov     rcx, rbp
0x14001b737  call    cs:__imp_GreDeleteObject
0x14001b73e  nop     dword ptr [rax+rax+00h]
0x14001b743  jmp     short loc_14001B71D
0x14001b745  bt      ecx, 1Eh
0x14001b749  jnb     loc_14001B44E
0x14001b74f  or      ebx, 20h
0x14001b752  jmp     loc_14001B44E
```
