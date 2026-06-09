# DCOBJ::vLock(HDC__ *)

- ea: `0x140048300`
- end: `0x1400486d9`
- name: `?vLock@DCOBJ@@QEAAXPEAUHDC__@@@Z`
- size: `985`
- prototype: `void __fastcall(DCOBJ *__hidden this, HDC)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x14001d190`
- `0x14001dbf0`
- `0x140045bc0`
- `0x140046b80`
- `0x140047010`

## callees

- `0x140010e60`
- `0x140022ff0`
- `0x140026270`
- `0x140031bf4`
- `0x140043e04`
- `0x1400482a0`
- `0x140048300`
- `0x140049060`
- `0x1400f0fb8`
- `0x140238240`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048494`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400485e1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048494`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400485e1`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400484d2`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400484d2`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140048666`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140048666`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1400486a1`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1400486a1`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140048657`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140048657`
- `ntoskrnl!KeIsAttachedProcess` at `0x14004835d`
- `ntoskrnl!KeIsAttachedProcess` at `0x14004835d`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x14004868d`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x14004868d`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14004834e`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14004834e`

## pseudocode

```c
void __fastcall DCOBJ::vLock(DCOBJ *this, HDC a2)
{
  __int64 v2; // r12
  unsigned int v4; // r13d
  __int64 v5; // r14
  __int64 v6; // rdi
  __int64 *CurrentThreadWin32ThreadAndEnterCriticalRegion; // r15
  __int64 v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // rcx
  int v12; // edi
  __int64 v13; // rax
  unsigned int *v14; // r15
  unsigned int v15; // r12d
  struct _KTHREAD *CurrentThread; // rbx
  __int64 v17; // rax
  __int64 *v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // rax
  unsigned int CurrentProcessId; // eax
  __int64 v22; // rdx
  unsigned int v23; // ebx
  __int64 v24; // rax
  struct _ENTRY *v25; // rax
  struct _DC_ATTR *v26; // rax
  __int64 v27; // rdx
  int v28; // ecx
  unsigned int v29; // ecx
  __int64 v30; // rdx
  int v31; // eax
  int v32; // eax
  ThreadRestrictNewHandlesRegion *v33; // rcx
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  unsigned int *v36; // [rsp+20h] [rbp-28h] BYREF
  int v37; // [rsp+28h] [rbp-20h]
  __int16 v38; // [rsp+2Ch] [rbp-1Ch]
  __int64 v39; // [rsp+30h] [rbp-18h]
  __int64 v40; // [rsp+90h] [rbp+48h] BYREF
  HDC v41; // [rsp+98h] [rbp+50h]
  __int64 v42; // [rsp+A0h] [rbp+58h]
  __int64 v43; // [rsp+A8h] [rbp+60h]

  v41 = a2;
  v2 = *((_QWORD *)this + 2);
  v38 = 0;
  v43 = v2;
  v4 = (unsigned __int16)a2 | ((unsigned int)a2 >> 8) & 0xFF0000;
  v39 = v2;
  v5 = 0;
  v40 = 0;
  v6 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v40);
  if ( !(unsigned __int8)KeIsAttachedProcess()
    || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
        CurrentThreadProcess = PsGetCurrentThreadProcess(),
        CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
  {
    if ( CurrentThreadWin32ThreadAndEnterCriticalRegion )
      v6 = *CurrentThreadWin32ThreadAndEnterCriticalRegion;
  }
  v8 = v6 + 8;
  v9 = -v6;
  v10 = v8 & -(__int64)(v9 != 0);
  if ( v10 )
  {
    v42 = *(_QWORD *)((v8 & -(__int64)(v9 != 0)) + 0x40);
    v2 = v43;
  }
  else
  {
    v42 = 0;
  }
  v11 = *(_QWORD *)(v2 + 8);
  v12 = 1;
  v37 = 1;
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 40LL))(v11, v4);
  v36 = (unsigned int *)v13;
  v14 = (unsigned int *)v13;
  if ( !v13 )
  {
    v12 = 0;
    KeLeaveCriticalRegion();
    goto LABEL_9;
  }
  _m_prefetchw((const void *)(v13 + 8));
  v15 = *(_DWORD *)(v13 + 8) & 0xFFFFFFFE;
  if ( v15 != (v40 & 0xFFFFFFFC) && v15 && (!v42 || v15 != (unsigned int)UMPDGetThreadClientPID(v10)) )
    goto LABEL_46;
  v2 = v43;
  if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v43 + 8) + 96LL))(
                     *(_QWORD *)(v43 + 8),
                     *v14)
                 + 14)
      & 0x20) != 0
    && (!v10
     || (v33 = *(ThreadRestrictNewHandlesRegion **)(v10 + 328)) == 0
     || !*((_BYTE *)v33 + 80)
     || !ThreadRestrictNewHandlesRegion::InRegion(v33, v4)) )
  {
    LOBYTE(v38) = 1;
LABEL_46:
    HANDLELOCK::vUnlock((HANDLELOCK *)&v36);
    v14 = v36;
    v12 = v37;
    v2 = v39;
  }
LABEL_9:
  if ( v12 )
  {
    if ( *((_BYTE *)v14 + 14) == 1 && *((_WORD *)v14 + 6) == WORD1(v41) )
    {
      CurrentThread = KeGetCurrentThread();
      v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v2 + 8) + 96LL))(*(_QWORD *)(v2 + 8), *v14);
      v5 = v17;
      if ( !*(_WORD *)(v17 + 12) || *(struct _KTHREAD **)(v17 + 16) == CurrentThread )
      {
        _InterlockedAdd16((volatile signed __int16 *)(v17 + 12), 1u);
        *(_QWORD *)(v17 + 16) = CurrentThread;
      }
      else
      {
        v5 = 0;
      }
    }
    v18 = *(__int64 **)(v2 + 8);
    v19 = *v18;
    v20 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v18 + 96))(v18, *v14);
    (*(void (__fastcall **)(__int64 *, __int64))(v19 + 48))(v18, v20);
    KeLeaveCriticalRegion();
  }
  *(_QWORD *)this = v5;
  if ( v5 )
  {
    if ( *(_DWORD *)(v5 + 2136) )
    {
      _InterlockedDecrement16((volatile signed __int16 *)(v5 + 12));
      *(_QWORD *)this = 0;
    }
  }
  else if ( (unsigned int)GrepGetCurrentProcessBehaviorRestriction() != 1
         && (unsigned __int8)PsIsWin32KFilterAuditEnabled() )
  {
    PsGetWin32KFilterSet();
  }
  if ( *(_QWORD *)this )
  {
    if ( (*(_DWORD *)(*(_QWORD *)this + 44LL) & 2) == 0 )
    {
      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
      v22 = *(_QWORD *)this;
      v23 = CurrentProcessId & 0xFFFFFFFC;
      if ( **(_QWORD **)this )
      {
        v24 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 8LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 8LL));
      }
      else
      {
        v24 = v22 + 2152;
        *(_OWORD *)(v22 + 2152) = 0;
        *(_QWORD *)(v22 + 2168) = 0;
        *(_DWORD *)(v22 + 2160) = -2147483630;
        *(_QWORD *)(v22 + 2168) = 0;
      }
      if ( v23 == (*(_DWORD *)(v24 + 8) & 0xFFFFFFFE) )
      {
        v25 = DC::PentryFromPobj(*(DC **)this, *((struct Gre::Base::SESSION_GLOBALS **)this + 2));
        if ( v25 )
        {
          v26 = (struct _DC_ATTR *)GreDecodeUserModePointer(*((void **)v25 + 2));
          if ( v26 )
          {
            if ( !(unsigned int)DC::SaveAttributes(*(DC **)this, v26) )
            {
              _InterlockedDecrement16((volatile signed __int16 *)(*(_QWORD *)this + 12LL));
              *(_QWORD *)this = 0;
              return;
            }
          }
        }
      }
      *(_DWORD *)(*(_QWORD *)this + 44LL) |= 2u;
      *((_DWORD *)this + 2) = 1;
    }
    v27 = *(_QWORD *)this;
    v28 = *(_DWORD *)(*(_QWORD *)this + 520LL);
    if ( (v28 & 4) != 0 )
    {
      v29 = v28 & 0xFFFFFFFB;
      *(_DWORD *)(v27 + 520) = v29;
      v30 = *(_QWORD *)(v27 + 976);
      v31 = *(_DWORD *)(v30 + 340);
      if ( (v29 & 1) != 0 )
        v32 = v31 | 0x16090;
      else
        v32 = v31 | 0x6090;
      *(_DWORD *)(v30 + 340) = v32;
    }
  }
}

```

## disassembly

```asm
0x140048300  mov     [rsp-40h+arg_8], rdx
0x140048305  push    rbp
0x140048306  push    rbx
0x140048307  push    rsi
0x140048308  push    rdi
0x140048309  push    r12
0x14004830b  push    r13
0x14004830d  push    r14
0x14004830f  push    r15
0x140048311  mov     rbp, rsp
0x140048314  sub     rsp, 48h
0x140048318  mov     r12, [rcx+10h]
0x14004831c  xor     ebx, ebx
0x14004831e  mov     r13d, edx
0x140048321  movzx   eax, dx
0x140048324  shr     r13d, 8
0x140048328  mov     rsi, rcx
0x14004832b  and     r13d, 0FF0000h
0x140048332  mov     [rbp+var_1C], bx
0x140048336  lea     rcx, [rbp+arg_0]
0x14004833a  mov     [rbp+arg_18], r12
0x14004833e  or      r13d, eax
0x140048341  mov     [rbp+var_18], r12
0x140048345  mov     r14d, ebx
0x140048348  mov     [rbp+arg_0], rbx
0x14004834c  mov     edi, ebx
0x14004834e  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x140048355  nop     dword ptr [rax+rax+00h]
0x14004835a  mov     r15, rax
0x14004835d  call    cs:__imp_KeIsAttachedProcess
0x140048364  nop     dword ptr [rax+rax+00h]
0x140048369  test    al, al
0x14004836b  jnz     loc_140048650
0x140048371  test    r15, r15
0x140048374  jz      short loc_140048379
0x140048376  mov     rdi, [r15]
0x140048379  lea     rax, [rdi+8]
0x14004837d  neg     rdi
0x140048380  sbb     rbx, rbx
0x140048383  and     rbx, rax
0x140048386  jz      loc_1400486B2
0x14004838c  mov     r12, [rbx+40h]
0x140048390  mov     [rbp+arg_10], r12
0x140048394  mov     r12, [rbp+arg_18]
0x140048398  mov     rcx, [r12+8]
0x14004839d  mov     edi, 1
0x1400483a2  mov     edx, r13d
0x1400483a5  mov     [rbp+var_20], edi
0x1400483a8  mov     rax, [rcx]
0x1400483ab  mov     rax, [rax+28h]
0x1400483af  call    _guard_dispatch_icall
0x1400483b4  xor     ecx, ecx
0x1400483b6  mov     [rbp+var_28], rax
0x1400483ba  mov     r15, rax
0x1400483bd  test    rax, rax
0x1400483c0  jz      loc_1400485DF
0x1400483c6  prefetchw byte ptr [rax+8]
0x1400483ca  mov     r12d, [rax+8]
0x1400483ce  mov     eax, dword ptr [rbp+arg_0]
0x1400483d1  and     r12d, 0FFFFFFFEh
0x1400483d5  and     eax, 0FFFFFFFCh
0x1400483d8  cmp     r12d, eax
0x1400483db  jnz     loc_1400485BD
0x1400483e1  mov     r12, [rbp+arg_18]
0x1400483e5  mov     edx, [r15]
0x1400483e8  mov     rcx, [r12+8]
0x1400483ed  mov     rax, [rcx]
0x1400483f0  mov     rax, [rax+60h]
0x1400483f4  call    _guard_dispatch_icall
0x1400483f9  test    byte ptr [rax+0Eh], 20h
0x1400483fd  jnz     loc_14004860B
0x140048403  xor     r13d, r13d
0x140048406  test    edi, edi
0x140048408  jz      loc_1400484A0
0x14004840e  cmp     byte ptr [r15+0Eh], 1
0x140048413  jnz     short loc_14004846E
0x140048415  movzx   eax, byte ptr [r15+0Ch]
0x14004841a  movzx   ecx, byte ptr [r15+0Dh]
0x14004841f  shl     cx, 8
0x140048423  or      cx, ax
0x140048426  mov     rax, [rbp+arg_8]
0x14004842a  shr     eax, 10h
0x14004842d  cmp     cx, ax
0x140048430  jnz     short loc_14004846E
0x140048432  mov     rbx, gs:188h
0x14004843b  mov     rcx, [r12+8]
0x140048440  mov     edx, [r15]
0x140048443  mov     rax, [rcx]
0x140048446  mov     rax, [rax+60h]
0x14004844a  call    _guard_dispatch_icall
0x14004844f  mov     r14, rax
0x140048452  movzx   ecx, word ptr [rax+0Ch]
0x140048456  test    cx, cx
0x140048459  jnz     loc_1400485F2
0x14004845f  mov     eax, 1
0x140048464  lock add [r14+0Ch], ax
0x14004846a  mov     [r14+10h], rbx
0x14004846e  mov     rdi, [r12+8]
0x140048473  mov     edx, [r15]
0x140048476  mov     rcx, rdi
0x140048479  mov     rbx, [rdi]
0x14004847c  mov     rax, [rbx+60h]
0x140048480  call    _guard_dispatch_icall
0x140048485  mov     rdx, rax
0x140048488  mov     rcx, rdi
0x14004848b  mov     rax, [rbx+30h]
0x14004848f  call    _guard_dispatch_icall
0x140048494  call    cs:__imp_KeLeaveCriticalRegion
0x14004849b  nop     dword ptr [rax+rax+00h]
0x1400484a0  xor     edi, edi
0x1400484a2  mov     [rsi], r14
0x1400484a5  test    r14, r14
0x1400484a8  jz      loc_14004867F
0x1400484ae  cmp     [r14+858h], edi
0x1400484b5  jnz     loc_1400486BB
0x1400484bb  mov     rax, [rsi]
0x1400484be  test    rax, rax
0x1400484c1  jz      loc_140048592
0x1400484c7  mov     eax, [rax+2Ch]
0x1400484ca  test    al, 2
0x1400484cc  jnz     loc_14004855E
0x1400484d2  call    cs:__imp_PsGetCurrentProcessId
0x1400484d9  nop     dword ptr [rax+rax+00h]
0x1400484de  mov     rdx, [rsi]
0x1400484e1  mov     rbx, rax
0x1400484e4  and     ebx, 0FFFFFFFCh
0x1400484e7  cmp     [rdx], rdi
0x1400484ea  jnz     loc_1400485A4
0x1400484f0  lea     rax, [rdx+868h]
0x1400484f7  xorps   xmm0, xmm0
0x1400484fa  movups  xmmword ptr [rax], xmm0
0x1400484fd  xor     ecx, ecx
0x1400484ff  mov     [rax+10h], rcx
0x140048503  mov     dword ptr [rdx+870h], 80000012h
0x14004850d  mov     [rdx+878h], rdi
0x140048514  mov     eax, [rax+8]
0x140048517  and     eax, 0FFFFFFFEh
0x14004851a  cmp     ebx, eax
0x14004851c  jnz     short loc_140048550
0x14004851e  mov     rdx, [rsi+10h]; struct Gre::Base::SESSION_GLOBALS *
0x140048522  mov     rcx, [rsi]; this
0x140048525  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x14004852a  test    rax, rax
0x14004852d  jz      short loc_140048550
0x14004852f  mov     rcx, [rax+10h]; void *
0x140048533  call    ?GreDecodeUserModePointer@@YAPEAXPEAX@Z; GreDecodeUserModePointer(void *)
0x140048538  test    rax, rax
0x14004853b  jz      short loc_140048550
0x14004853d  mov     rcx, [rsi]; this
0x140048540  mov     rdx, rax; struct _DC_ATTR *
0x140048543  call    ?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x140048548  test    eax, eax
0x14004854a  jz      loc_1400486C9
0x140048550  mov     rax, [rsi]
0x140048553  or      dword ptr [rax+2Ch], 2
0x140048557  mov     dword ptr [rsi+8], 1
0x14004855e  mov     rdx, [rsi]
0x140048561  mov     ecx, [rdx+208h]
0x140048567  test    cl, 4
0x14004856a  jz      short loc_140048592
0x14004856c  and     ecx, 0FFFFFFFBh
0x14004856f  mov     [rdx+208h], ecx
0x140048575  mov     rdx, [rdx+3D0h]
0x14004857c  mov     eax, [rdx+154h]
0x140048582  test    cl, 1
0x140048585  jz      short loc_140048604
0x140048587  or      eax, 16090h
0x14004858c  mov     [rdx+154h], eax
0x140048592  add     rsp, 48h
0x140048596  pop     r15
0x140048598  pop     r14
0x14004859a  pop     r13
0x14004859c  pop     r12
0x14004859e  pop     rdi
0x14004859f  pop     rsi
0x1400485a0  pop     rbx
0x1400485a1  pop     rbp
0x1400485a2  retn
0x1400485a4  mov     rax, [rsi+10h]
0x1400485a8  mov     rcx, [rax+8]
0x1400485ac  mov     rax, [rcx]
0x1400485af  mov     rax, [rax+8]
0x1400485b3  call    _guard_dispatch_icall
0x1400485b8  jmp     loc_140048514
0x1400485bd  test    r12d, r12d
0x1400485c0  jz      loc_1400483E1
0x1400485c6  cmp     [rbp+arg_10], rcx
0x1400485ca  jz      short loc_140048637
0x1400485cc  mov     rcx, rbx
0x1400485cf  call    UMPDGetThreadClientPID
0x1400485d4  cmp     r12d, eax
0x1400485d7  jz      loc_1400483E1
0x1400485dd  jmp     short loc_140048637
0x1400485df  mov     edi, ecx
0x1400485e1  call    cs:__imp_KeLeaveCriticalRegion
0x1400485e8  nop     dword ptr [rax+rax+00h]
0x1400485ed  jmp     loc_140048403
0x1400485f2  cmp     [rax+10h], rbx
0x1400485f6  jz      loc_14004845F
0x1400485fc  mov     r14, r13
0x1400485ff  jmp     loc_14004846E
0x140048604  or      eax, 6090h
0x140048609  jmp     short loc_14004858C
0x14004860b  xor     eax, eax
0x14004860d  test    rbx, rbx
0x140048610  jz      short loc_140048633
0x140048612  mov     rcx, [rbx+148h]; this
0x140048619  test    rcx, rcx
0x14004861c  jz      short loc_140048633
0x14004861e  cmp     [rcx+50h], al
0x140048621  jz      short loc_140048633
0x140048623  mov     edx, r13d; unsigned int
0x140048626  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x14004862b  test    al, al
0x14004862d  jnz     loc_140048403
0x140048633  mov     byte ptr [rbp+var_1C], dil
0x140048637  lea     rcx, [rbp+var_28]; this
0x14004863b  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x140048640  mov     r15, [rbp+var_28]
0x140048644  mov     edi, [rbp+var_20]
0x140048647  mov     r12, [rbp+var_18]
0x14004864b  jmp     loc_140048403
0x140048650  call    W32GetCurrentWin32kSessionId
0x140048655  mov     ebx, eax
0x140048657  call    cs:__imp_PsGetCurrentThreadProcess
0x14004865e  nop     dword ptr [rax+rax+00h]
0x140048663  mov     rcx, rax
0x140048666  call    cs:__imp_PsGetProcessSessionIdEx
0x14004866d  nop     dword ptr [rax+rax+00h]
0x140048672  cmp     ebx, eax
0x140048674  jz      loc_140048371
0x14004867a  jmp     loc_140048379
0x14004867f  call    ?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x140048684  cmp     eax, 1
0x140048687  jz      loc_1400484BB
0x14004868d  call    cs:__imp_PsIsWin32KFilterAuditEnabled
0x140048694  nop     dword ptr [rax+rax+00h]
0x140048699  test    al, al
0x14004869b  jz      loc_1400484BB
0x1400486a1  call    cs:__imp_PsGetWin32KFilterSet
0x1400486a8  nop     dword ptr [rax+rax+00h]
0x1400486ad  jmp     loc_1400484BB
0x1400486b2  mov     [rbp+arg_10], r14
0x1400486b6  jmp     loc_140048398
0x1400486bb  lock dec word ptr [r14+0Ch]
0x1400486c1  mov     [rsi], rdi
0x1400486c4  jmp     loc_1400484BB
0x1400486c9  mov     rax, [rsi]
0x1400486cc  lock dec word ptr [rax+0Ch]
0x1400486d1  mov     [rsi], rdi
0x1400486d4  jmp     loc_140048592
```
