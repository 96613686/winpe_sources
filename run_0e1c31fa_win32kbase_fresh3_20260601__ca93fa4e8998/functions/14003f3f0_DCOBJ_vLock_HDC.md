# DCOBJ::vLock(HDC__ *)

- ea: `0x14003f3f0`
- end: `0x14003f7c9`
- name: `?vLock@DCOBJ@@QEAAXPEAUHDC__@@@Z`
- size: `985`
- prototype: `void __fastcall(DCOBJ *__hidden this, HDC)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x140014020`
- `0x140014a80`
- `0x14003ccb0`
- `0x14003dc70`
- `0x14003e100`

## callees

- `0x140006cf8`
- `0x140008160`
- `0x140019fd0`
- `0x14001d250`
- `0x140028974`
- `0x14003bf24`
- `0x14003f390`
- `0x14003f3f0`
- `0x140040150`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f584`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f6d1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f584`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003f6d1`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003f5c2`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003f5c2`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003f756`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003f756`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14003f791`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14003f791`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14003f747`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14003f747`
- `ntoskrnl!KeIsAttachedProcess` at `0x14003f44d`
- `ntoskrnl!KeIsAttachedProcess` at `0x14003f44d`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x14003f77d`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x14003f77d`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14003f43e`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14003f43e`

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
0x14003f3f0  mov     [rsp-40h+arg_8], rdx
0x14003f3f5  push    rbp
0x14003f3f6  push    rbx
0x14003f3f7  push    rsi
0x14003f3f8  push    rdi
0x14003f3f9  push    r12
0x14003f3fb  push    r13
0x14003f3fd  push    r14
0x14003f3ff  push    r15
0x14003f401  mov     rbp, rsp
0x14003f404  sub     rsp, 48h
0x14003f408  mov     r12, [rcx+10h]
0x14003f40c  xor     ebx, ebx
0x14003f40e  mov     r13d, edx
0x14003f411  movzx   eax, dx
0x14003f414  shr     r13d, 8
0x14003f418  mov     rsi, rcx
0x14003f41b  and     r13d, 0FF0000h
0x14003f422  mov     [rbp+var_1C], bx
0x14003f426  lea     rcx, [rbp+arg_0]
0x14003f42a  mov     [rbp+arg_18], r12
0x14003f42e  or      r13d, eax
0x14003f431  mov     [rbp+var_18], r12
0x14003f435  mov     r14d, ebx
0x14003f438  mov     [rbp+arg_0], rbx
0x14003f43c  mov     edi, ebx
0x14003f43e  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x14003f445  nop     dword ptr [rax+rax+00h]
0x14003f44a  mov     r15, rax
0x14003f44d  call    cs:__imp_KeIsAttachedProcess
0x14003f454  nop     dword ptr [rax+rax+00h]
0x14003f459  test    al, al
0x14003f45b  jnz     loc_14003F740
0x14003f461  test    r15, r15
0x14003f464  jz      short loc_14003F469
0x14003f466  mov     rdi, [r15]
0x14003f469  lea     rax, [rdi+8]
0x14003f46d  neg     rdi
0x14003f470  sbb     rbx, rbx
0x14003f473  and     rbx, rax
0x14003f476  jz      loc_14003F7A2
0x14003f47c  mov     r12, [rbx+40h]
0x14003f480  mov     [rbp+arg_10], r12
0x14003f484  mov     r12, [rbp+arg_18]
0x14003f488  mov     rcx, [r12+8]
0x14003f48d  mov     edi, 1
0x14003f492  mov     edx, r13d
0x14003f495  mov     [rbp+var_20], edi
0x14003f498  mov     rax, [rcx]
0x14003f49b  mov     rax, [rax+28h]
0x14003f49f  call    _guard_dispatch_icall
0x14003f4a4  xor     ecx, ecx
0x14003f4a6  mov     [rbp+var_28], rax
0x14003f4aa  mov     r15, rax
0x14003f4ad  test    rax, rax
0x14003f4b0  jz      loc_14003F6CF
0x14003f4b6  prefetchw byte ptr [rax+8]
0x14003f4ba  mov     r12d, [rax+8]
0x14003f4be  mov     eax, dword ptr [rbp+arg_0]
0x14003f4c1  and     r12d, 0FFFFFFFEh
0x14003f4c5  and     eax, 0FFFFFFFCh
0x14003f4c8  cmp     r12d, eax
0x14003f4cb  jnz     loc_14003F6AD
0x14003f4d1  mov     r12, [rbp+arg_18]
0x14003f4d5  mov     edx, [r15]
0x14003f4d8  mov     rcx, [r12+8]
0x14003f4dd  mov     rax, [rcx]
0x14003f4e0  mov     rax, [rax+60h]
0x14003f4e4  call    _guard_dispatch_icall
0x14003f4e9  test    byte ptr [rax+0Eh], 20h
0x14003f4ed  jnz     loc_14003F6FB
0x14003f4f3  xor     r13d, r13d
0x14003f4f6  test    edi, edi
0x14003f4f8  jz      loc_14003F590
0x14003f4fe  cmp     byte ptr [r15+0Eh], 1
0x14003f503  jnz     short loc_14003F55E
0x14003f505  movzx   eax, byte ptr [r15+0Ch]
0x14003f50a  movzx   ecx, byte ptr [r15+0Dh]
0x14003f50f  shl     cx, 8
0x14003f513  or      cx, ax
0x14003f516  mov     rax, [rbp+arg_8]
0x14003f51a  shr     eax, 10h
0x14003f51d  cmp     cx, ax
0x14003f520  jnz     short loc_14003F55E
0x14003f522  mov     rbx, gs:188h
0x14003f52b  mov     rcx, [r12+8]
0x14003f530  mov     edx, [r15]
0x14003f533  mov     rax, [rcx]
0x14003f536  mov     rax, [rax+60h]
0x14003f53a  call    _guard_dispatch_icall
0x14003f53f  mov     r14, rax
0x14003f542  movzx   ecx, word ptr [rax+0Ch]
0x14003f546  test    cx, cx
0x14003f549  jnz     loc_14003F6E2
0x14003f54f  mov     eax, 1
0x14003f554  lock add [r14+0Ch], ax
0x14003f55a  mov     [r14+10h], rbx
0x14003f55e  mov     rdi, [r12+8]
0x14003f563  mov     edx, [r15]
0x14003f566  mov     rcx, rdi
0x14003f569  mov     rbx, [rdi]
0x14003f56c  mov     rax, [rbx+60h]
0x14003f570  call    _guard_dispatch_icall
0x14003f575  mov     rdx, rax
0x14003f578  mov     rcx, rdi
0x14003f57b  mov     rax, [rbx+30h]
0x14003f57f  call    _guard_dispatch_icall
0x14003f584  call    cs:__imp_KeLeaveCriticalRegion
0x14003f58b  nop     dword ptr [rax+rax+00h]
0x14003f590  xor     edi, edi
0x14003f592  mov     [rsi], r14
0x14003f595  test    r14, r14
0x14003f598  jz      loc_14003F76F
0x14003f59e  cmp     [r14+858h], edi
0x14003f5a5  jnz     loc_14003F7AB
0x14003f5ab  mov     rax, [rsi]
0x14003f5ae  test    rax, rax
0x14003f5b1  jz      loc_14003F682
0x14003f5b7  mov     eax, [rax+2Ch]
0x14003f5ba  test    al, 2
0x14003f5bc  jnz     loc_14003F64E
0x14003f5c2  call    cs:__imp_PsGetCurrentProcessId
0x14003f5c9  nop     dword ptr [rax+rax+00h]
0x14003f5ce  mov     rdx, [rsi]
0x14003f5d1  mov     rbx, rax
0x14003f5d4  and     ebx, 0FFFFFFFCh
0x14003f5d7  cmp     [rdx], rdi
0x14003f5da  jnz     loc_14003F694
0x14003f5e0  lea     rax, [rdx+868h]
0x14003f5e7  xorps   xmm0, xmm0
0x14003f5ea  movups  xmmword ptr [rax], xmm0
0x14003f5ed  xor     ecx, ecx
0x14003f5ef  mov     [rax+10h], rcx
0x14003f5f3  mov     dword ptr [rdx+870h], 80000012h
0x14003f5fd  mov     [rdx+878h], rdi
0x14003f604  mov     eax, [rax+8]
0x14003f607  and     eax, 0FFFFFFFEh
0x14003f60a  cmp     ebx, eax
0x14003f60c  jnz     short loc_14003F640
0x14003f60e  mov     rdx, [rsi+10h]; struct Gre::Base::SESSION_GLOBALS *
0x14003f612  mov     rcx, [rsi]; this
0x14003f615  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x14003f61a  test    rax, rax
0x14003f61d  jz      short loc_14003F640
0x14003f61f  mov     rcx, [rax+10h]; void *
0x14003f623  call    ?GreDecodeUserModePointer@@YAPEAXPEAX@Z; GreDecodeUserModePointer(void *)
0x14003f628  test    rax, rax
0x14003f62b  jz      short loc_14003F640
0x14003f62d  mov     rcx, [rsi]; this
0x14003f630  mov     rdx, rax; struct _DC_ATTR *
0x14003f633  call    ?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x14003f638  test    eax, eax
0x14003f63a  jz      loc_14003F7B9
0x14003f640  mov     rax, [rsi]
0x14003f643  or      dword ptr [rax+2Ch], 2
0x14003f647  mov     dword ptr [rsi+8], 1
0x14003f64e  mov     rdx, [rsi]
0x14003f651  mov     ecx, [rdx+208h]
0x14003f657  test    cl, 4
0x14003f65a  jz      short loc_14003F682
0x14003f65c  and     ecx, 0FFFFFFFBh
0x14003f65f  mov     [rdx+208h], ecx
0x14003f665  mov     rdx, [rdx+3D0h]
0x14003f66c  mov     eax, [rdx+154h]
0x14003f672  test    cl, 1
0x14003f675  jz      short loc_14003F6F4
0x14003f677  or      eax, 16090h
0x14003f67c  mov     [rdx+154h], eax
0x14003f682  add     rsp, 48h
0x14003f686  pop     r15
0x14003f688  pop     r14
0x14003f68a  pop     r13
0x14003f68c  pop     r12
0x14003f68e  pop     rdi
0x14003f68f  pop     rsi
0x14003f690  pop     rbx
0x14003f691  pop     rbp
0x14003f692  retn
0x14003f694  mov     rax, [rsi+10h]
0x14003f698  mov     rcx, [rax+8]
0x14003f69c  mov     rax, [rcx]
0x14003f69f  mov     rax, [rax+8]
0x14003f6a3  call    _guard_dispatch_icall
0x14003f6a8  jmp     loc_14003F604
0x14003f6ad  test    r12d, r12d
0x14003f6b0  jz      loc_14003F4D1
0x14003f6b6  cmp     [rbp+arg_10], rcx
0x14003f6ba  jz      short loc_14003F727
0x14003f6bc  mov     rcx, rbx
0x14003f6bf  call    UMPDGetThreadClientPID
0x14003f6c4  cmp     r12d, eax
0x14003f6c7  jz      loc_14003F4D1
0x14003f6cd  jmp     short loc_14003F727
0x14003f6cf  mov     edi, ecx
0x14003f6d1  call    cs:__imp_KeLeaveCriticalRegion
0x14003f6d8  nop     dword ptr [rax+rax+00h]
0x14003f6dd  jmp     loc_14003F4F3
0x14003f6e2  cmp     [rax+10h], rbx
0x14003f6e6  jz      loc_14003F54F
0x14003f6ec  mov     r14, r13
0x14003f6ef  jmp     loc_14003F55E
0x14003f6f4  or      eax, 6090h
0x14003f6f9  jmp     short loc_14003F67C
0x14003f6fb  xor     eax, eax
0x14003f6fd  test    rbx, rbx
0x14003f700  jz      short loc_14003F723
0x14003f702  mov     rcx, [rbx+148h]; this
0x14003f709  test    rcx, rcx
0x14003f70c  jz      short loc_14003F723
0x14003f70e  cmp     [rcx+50h], al
0x14003f711  jz      short loc_14003F723
0x14003f713  mov     edx, r13d; unsigned int
0x14003f716  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x14003f71b  test    al, al
0x14003f71d  jnz     loc_14003F4F3
0x14003f723  mov     byte ptr [rbp+var_1C], dil
0x14003f727  lea     rcx, [rbp+var_28]; this
0x14003f72b  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x14003f730  mov     r15, [rbp+var_28]
0x14003f734  mov     edi, [rbp+var_20]
0x14003f737  mov     r12, [rbp+var_18]
0x14003f73b  jmp     loc_14003F4F3
0x14003f740  call    W32GetCurrentWin32kSessionId
0x14003f745  mov     ebx, eax
0x14003f747  call    cs:__imp_PsGetCurrentThreadProcess
0x14003f74e  nop     dword ptr [rax+rax+00h]
0x14003f753  mov     rcx, rax
0x14003f756  call    cs:__imp_PsGetProcessSessionIdEx
0x14003f75d  nop     dword ptr [rax+rax+00h]
0x14003f762  cmp     ebx, eax
0x14003f764  jz      loc_14003F461
0x14003f76a  jmp     loc_14003F469
0x14003f76f  call    ?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x14003f774  cmp     eax, 1
0x14003f777  jz      loc_14003F5AB
0x14003f77d  call    cs:__imp_PsIsWin32KFilterAuditEnabled
0x14003f784  nop     dword ptr [rax+rax+00h]
0x14003f789  test    al, al
0x14003f78b  jz      loc_14003F5AB
0x14003f791  call    cs:__imp_PsGetWin32KFilterSet
0x14003f798  nop     dword ptr [rax+rax+00h]
0x14003f79d  jmp     loc_14003F5AB
0x14003f7a2  mov     [rbp+arg_10], r14
0x14003f7a6  jmp     loc_14003F488
0x14003f7ab  lock dec word ptr [r14+0Ch]
0x14003f7b1  mov     [rsi], rdi
0x14003f7b4  jmp     loc_14003F5AB
0x14003f7b9  mov     rax, [rsi]
0x14003f7bc  lock dec word ptr [rax+0Ch]
0x14003f7c1  mov     [rsi], rdi
0x14003f7c4  jmp     loc_14003F682
```
