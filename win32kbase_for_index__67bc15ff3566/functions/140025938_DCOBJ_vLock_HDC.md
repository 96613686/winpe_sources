# DCOBJ::vLock(HDC__ *)

- ea: `0x140025938`
- end: `0x140025d11`
- name: `?vLock@DCOBJ@@QEAAXPEAUHDC__@@@Z`
- size: `985`
- prototype: `void __fastcall(DCOBJ *__hidden this, HDC)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x140023910`
- `0x140024580`
- `0x140024a10`
- `0x140026210`
- `0x140026db0`

## callees

- `0x14001e034`
- `0x140025938`
- `0x140025d20`
- `0x14002f850`
- `0x1400371c0`
- `0x140079330`
- `0x14007a8c0`
- `0x140120e30`
- `0x14012e228`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025acc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025c19`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025acc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025c19`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140025b0a`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140025b0a`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140025c9e`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140025c9e`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x140025cd9`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x140025cd9`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140025c8f`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140025c8f`
- `ntoskrnl!KeIsAttachedProcess` at `0x140025995`
- `ntoskrnl!KeIsAttachedProcess` at `0x140025995`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x140025cc5`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x140025cc5`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x140025986`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x140025986`

## pseudocode

```c
void __fastcall DCOBJ::vLock(DCOBJ *this, HDC a2)
{
  __int64 v2; // r12
  unsigned int v4; // r13d
  __int64 v5; // r14
  __int64 v6; // rdi
  __int64 *CurrentThreadWin32ThreadAndEnterCriticalRegion; // r15
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rcx
  int v14; // edi
  __int64 v15; // rax
  unsigned int *v16; // r15
  unsigned int v17; // r12d
  struct _KTHREAD *CurrentThread; // rbx
  __int64 v19; // rax
  __int64 *v20; // rdi
  __int64 v21; // rbx
  __int64 v22; // rax
  unsigned int CurrentProcessId; // eax
  __int64 v24; // rdx
  unsigned int v25; // ebx
  __int64 v26; // rax
  struct _ENTRY *v27; // rax
  struct _DC_ATTR *v28; // rax
  __int64 v29; // rdx
  int v30; // ecx
  unsigned int v31; // ecx
  __int64 v32; // rdx
  int v33; // eax
  int v34; // eax
  ThreadRestrictNewHandlesRegion *v35; // rcx
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  unsigned int *v38; // [rsp+20h] [rbp-28h] BYREF
  int v39; // [rsp+28h] [rbp-20h]
  __int16 v40; // [rsp+2Ch] [rbp-1Ch]
  __int64 v41; // [rsp+30h] [rbp-18h]
  __int64 v42; // [rsp+90h] [rbp+48h] BYREF
  HDC v43; // [rsp+98h] [rbp+50h]
  __int64 v44; // [rsp+A0h] [rbp+58h]
  __int64 v45; // [rsp+A8h] [rbp+60h]

  v43 = a2;
  v2 = *((_QWORD *)this + 2);
  v40 = 0;
  v45 = v2;
  v4 = (unsigned __int16)a2 | ((unsigned int)a2 >> 8) & 0xFF0000;
  v41 = v2;
  v5 = 0;
  v42 = 0;
  v6 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v42);
  if ( !(unsigned __int8)KeIsAttachedProcess(v9, v8)
    || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
        CurrentThreadProcess = PsGetCurrentThreadProcess(),
        CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
  {
    if ( CurrentThreadWin32ThreadAndEnterCriticalRegion )
      v6 = *CurrentThreadWin32ThreadAndEnterCriticalRegion;
  }
  v10 = v6 + 8;
  v11 = -v6;
  v12 = v10 & -(__int64)(v11 != 0);
  if ( v12 )
  {
    v44 = *(_QWORD *)((v10 & -(__int64)(v11 != 0)) + 0x40);
    v2 = v45;
  }
  else
  {
    v44 = 0;
  }
  v13 = *(_QWORD *)(v2 + 8);
  v14 = 1;
  v39 = 1;
  v15 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 40LL))(v13, v4);
  v38 = (unsigned int *)v15;
  v16 = (unsigned int *)v15;
  if ( !v15 )
  {
    v14 = 0;
    KeLeaveCriticalRegion();
    goto LABEL_9;
  }
  _m_prefetchw((const void *)(v15 + 8));
  v17 = *(_DWORD *)(v15 + 8) & 0xFFFFFFFE;
  if ( v17 != (v42 & 0xFFFFFFFC) && v17 && (!v44 || v17 != (unsigned int)UMPDGetThreadClientPID(v12)) )
    goto LABEL_46;
  v2 = v45;
  if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v45 + 8) + 96LL))(
                     *(_QWORD *)(v45 + 8),
                     *v16)
                 + 14)
      & 0x20) != 0
    && (!v12
     || (v35 = *(ThreadRestrictNewHandlesRegion **)(v12 + 328)) == 0
     || !*((_BYTE *)v35 + 80)
     || !ThreadRestrictNewHandlesRegion::InRegion(v35, v4)) )
  {
    LOBYTE(v40) = 1;
LABEL_46:
    HANDLELOCK::vUnlock((HANDLELOCK *)&v38);
    v16 = v38;
    v14 = v39;
    v2 = v41;
  }
LABEL_9:
  if ( v14 )
  {
    if ( *((_BYTE *)v16 + 14) == 1 && *((_WORD *)v16 + 6) == WORD1(v43) )
    {
      CurrentThread = KeGetCurrentThread();
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v2 + 8) + 96LL))(*(_QWORD *)(v2 + 8), *v16);
      v5 = v19;
      if ( !*(_WORD *)(v19 + 12) || *(struct _KTHREAD **)(v19 + 16) == CurrentThread )
      {
        _InterlockedAdd16((volatile signed __int16 *)(v19 + 12), 1u);
        *(_QWORD *)(v19 + 16) = CurrentThread;
      }
      else
      {
        v5 = 0;
      }
    }
    v20 = *(__int64 **)(v2 + 8);
    v21 = *v20;
    v22 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v20 + 96))(v20, *v16);
    (*(void (__fastcall **)(__int64 *, __int64))(v21 + 48))(v20, v22);
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
      v24 = *(_QWORD *)this;
      v25 = CurrentProcessId & 0xFFFFFFFC;
      if ( **(_QWORD **)this )
      {
        v26 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 8LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 8LL));
      }
      else
      {
        v26 = v24 + 2152;
        *(_OWORD *)(v24 + 2152) = 0;
        *(_QWORD *)(v24 + 2168) = 0;
        *(_DWORD *)(v24 + 2160) = -2147483630;
        *(_QWORD *)(v24 + 2168) = 0;
      }
      if ( v25 == (*(_DWORD *)(v26 + 8) & 0xFFFFFFFE) )
      {
        v27 = DC::PentryFromPobj(*(DC **)this, *((struct Gre::Base::SESSION_GLOBALS **)this + 2));
        if ( v27 )
        {
          v28 = (struct _DC_ATTR *)GreDecodeUserModePointer(*((void **)v27 + 2));
          if ( v28 )
          {
            if ( !(unsigned int)DC::SaveAttributes(*(DC **)this, v28) )
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
    v29 = *(_QWORD *)this;
    v30 = *(_DWORD *)(*(_QWORD *)this + 520LL);
    if ( (v30 & 4) != 0 )
    {
      v31 = v30 & 0xFFFFFFFB;
      *(_DWORD *)(v29 + 520) = v31;
      v32 = *(_QWORD *)(v29 + 976);
      v33 = *(_DWORD *)(v32 + 340);
      if ( (v31 & 1) != 0 )
        v34 = v33 | 0x16090;
      else
        v34 = v33 | 0x6090;
      *(_DWORD *)(v32 + 340) = v34;
    }
  }
}

```

## disassembly

```asm
0x140025938  mov     [rsp-40h+arg_8], rdx
0x14002593d  push    rbp
0x14002593e  push    rbx
0x14002593f  push    rsi
0x140025940  push    rdi
0x140025941  push    r12
0x140025943  push    r13
0x140025945  push    r14
0x140025947  push    r15
0x140025949  mov     rbp, rsp
0x14002594c  sub     rsp, 48h
0x140025950  mov     r12, [rcx+10h]
0x140025954  xor     ebx, ebx
0x140025956  mov     r13d, edx
0x140025959  movzx   eax, dx
0x14002595c  shr     r13d, 8
0x140025960  mov     rsi, rcx
0x140025963  and     r13d, 0FF0000h
0x14002596a  mov     [rbp+var_1C], bx
0x14002596e  lea     rcx, [rbp+arg_0]
0x140025972  mov     [rbp+arg_18], r12
0x140025976  or      r13d, eax
0x140025979  mov     [rbp+var_18], r12
0x14002597d  mov     r14d, ebx
0x140025980  mov     [rbp+arg_0], rbx
0x140025984  mov     edi, ebx
0x140025986  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x14002598d  nop     dword ptr [rax+rax+00h]
0x140025992  mov     r15, rax
0x140025995  call    cs:__imp_KeIsAttachedProcess
0x14002599c  nop     dword ptr [rax+rax+00h]
0x1400259a1  test    al, al
0x1400259a3  jnz     loc_140025C88
0x1400259a9  test    r15, r15
0x1400259ac  jz      short loc_1400259B1
0x1400259ae  mov     rdi, [r15]
0x1400259b1  lea     rax, [rdi+8]
0x1400259b5  neg     rdi
0x1400259b8  sbb     rbx, rbx
0x1400259bb  and     rbx, rax
0x1400259be  jz      loc_140025CEA
0x1400259c4  mov     r12, [rbx+40h]
0x1400259c8  mov     [rbp+arg_10], r12
0x1400259cc  mov     r12, [rbp+arg_18]
0x1400259d0  mov     rcx, [r12+8]
0x1400259d5  mov     edi, 1
0x1400259da  mov     edx, r13d
0x1400259dd  mov     [rbp+var_20], edi
0x1400259e0  mov     rax, [rcx]
0x1400259e3  mov     rax, [rax+28h]
0x1400259e7  call    _guard_dispatch_icall
0x1400259ec  xor     ecx, ecx
0x1400259ee  mov     [rbp+var_28], rax
0x1400259f2  mov     r15, rax
0x1400259f5  test    rax, rax
0x1400259f8  jz      loc_140025C17
0x1400259fe  prefetchw byte ptr [rax+8]
0x140025a02  mov     r12d, [rax+8]
0x140025a06  mov     eax, dword ptr [rbp+arg_0]
0x140025a09  and     r12d, 0FFFFFFFEh
0x140025a0d  and     eax, 0FFFFFFFCh
0x140025a10  cmp     r12d, eax
0x140025a13  jnz     loc_140025BF5
0x140025a19  mov     r12, [rbp+arg_18]
0x140025a1d  mov     edx, [r15]
0x140025a20  mov     rcx, [r12+8]
0x140025a25  mov     rax, [rcx]
0x140025a28  mov     rax, [rax+60h]
0x140025a2c  call    _guard_dispatch_icall
0x140025a31  test    byte ptr [rax+0Eh], 20h
0x140025a35  jnz     loc_140025C43
0x140025a3b  xor     r13d, r13d
0x140025a3e  test    edi, edi
0x140025a40  jz      loc_140025AD8
0x140025a46  cmp     byte ptr [r15+0Eh], 1
0x140025a4b  jnz     short loc_140025AA6
0x140025a4d  movzx   eax, byte ptr [r15+0Ch]
0x140025a52  movzx   ecx, byte ptr [r15+0Dh]
0x140025a57  shl     cx, 8
0x140025a5b  or      cx, ax
0x140025a5e  mov     rax, [rbp+arg_8]
0x140025a62  shr     eax, 10h
0x140025a65  cmp     cx, ax
0x140025a68  jnz     short loc_140025AA6
0x140025a6a  mov     rbx, gs:188h
0x140025a73  mov     rcx, [r12+8]
0x140025a78  mov     edx, [r15]
0x140025a7b  mov     rax, [rcx]
0x140025a7e  mov     rax, [rax+60h]
0x140025a82  call    _guard_dispatch_icall
0x140025a87  mov     r14, rax
0x140025a8a  movzx   ecx, word ptr [rax+0Ch]
0x140025a8e  test    cx, cx
0x140025a91  jnz     loc_140025C2A
0x140025a97  mov     eax, 1
0x140025a9c  lock add [r14+0Ch], ax
0x140025aa2  mov     [r14+10h], rbx
0x140025aa6  mov     rdi, [r12+8]
0x140025aab  mov     edx, [r15]
0x140025aae  mov     rcx, rdi
0x140025ab1  mov     rbx, [rdi]
0x140025ab4  mov     rax, [rbx+60h]
0x140025ab8  call    _guard_dispatch_icall
0x140025abd  mov     rdx, rax
0x140025ac0  mov     rcx, rdi
0x140025ac3  mov     rax, [rbx+30h]
0x140025ac7  call    _guard_dispatch_icall
0x140025acc  call    cs:__imp_KeLeaveCriticalRegion
0x140025ad3  nop     dword ptr [rax+rax+00h]
0x140025ad8  xor     edi, edi
0x140025ada  mov     [rsi], r14
0x140025add  test    r14, r14
0x140025ae0  jz      loc_140025CB7
0x140025ae6  cmp     [r14+858h], edi
0x140025aed  jnz     loc_140025CF3
0x140025af3  mov     rax, [rsi]
0x140025af6  test    rax, rax
0x140025af9  jz      loc_140025BCA
0x140025aff  mov     eax, [rax+2Ch]
0x140025b02  test    al, 2
0x140025b04  jnz     loc_140025B96
0x140025b0a  call    cs:__imp_PsGetCurrentProcessId
0x140025b11  nop     dword ptr [rax+rax+00h]
0x140025b16  mov     rdx, [rsi]
0x140025b19  mov     rbx, rax
0x140025b1c  and     ebx, 0FFFFFFFCh
0x140025b1f  cmp     [rdx], rdi
0x140025b22  jnz     loc_140025BDC
0x140025b28  lea     rax, [rdx+868h]
0x140025b2f  xorps   xmm0, xmm0
0x140025b32  movups  xmmword ptr [rax], xmm0
0x140025b35  xor     ecx, ecx
0x140025b37  mov     [rax+10h], rcx
0x140025b3b  mov     dword ptr [rdx+870h], 80000012h
0x140025b45  mov     [rdx+878h], rdi
0x140025b4c  mov     eax, [rax+8]
0x140025b4f  and     eax, 0FFFFFFFEh
0x140025b52  cmp     ebx, eax
0x140025b54  jnz     short loc_140025B88
0x140025b56  mov     rdx, [rsi+10h]; struct Gre::Base::SESSION_GLOBALS *
0x140025b5a  mov     rcx, [rsi]; this
0x140025b5d  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x140025b62  test    rax, rax
0x140025b65  jz      short loc_140025B88
0x140025b67  mov     rcx, [rax+10h]; void *
0x140025b6b  call    ?GreDecodeUserModePointer@@YAPEAXPEAX@Z; GreDecodeUserModePointer(void *)
0x140025b70  test    rax, rax
0x140025b73  jz      short loc_140025B88
0x140025b75  mov     rcx, [rsi]; this
0x140025b78  mov     rdx, rax; struct _DC_ATTR *
0x140025b7b  call    ?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x140025b80  test    eax, eax
0x140025b82  jz      loc_140025D01
0x140025b88  mov     rax, [rsi]
0x140025b8b  or      dword ptr [rax+2Ch], 2
0x140025b8f  mov     dword ptr [rsi+8], 1
0x140025b96  mov     rdx, [rsi]
0x140025b99  mov     ecx, [rdx+208h]
0x140025b9f  test    cl, 4
0x140025ba2  jz      short loc_140025BCA
0x140025ba4  and     ecx, 0FFFFFFFBh
0x140025ba7  mov     [rdx+208h], ecx
0x140025bad  mov     rdx, [rdx+3D0h]
0x140025bb4  mov     eax, [rdx+154h]
0x140025bba  test    cl, 1
0x140025bbd  jz      short loc_140025C3C
0x140025bbf  or      eax, 16090h
0x140025bc4  mov     [rdx+154h], eax
0x140025bca  add     rsp, 48h
0x140025bce  pop     r15
0x140025bd0  pop     r14
0x140025bd2  pop     r13
0x140025bd4  pop     r12
0x140025bd6  pop     rdi
0x140025bd7  pop     rsi
0x140025bd8  pop     rbx
0x140025bd9  pop     rbp
0x140025bda  retn
0x140025bdc  mov     rax, [rsi+10h]
0x140025be0  mov     rcx, [rax+8]
0x140025be4  mov     rax, [rcx]
0x140025be7  mov     rax, [rax+8]
0x140025beb  call    _guard_dispatch_icall
0x140025bf0  jmp     loc_140025B4C
0x140025bf5  test    r12d, r12d
0x140025bf8  jz      loc_140025A19
0x140025bfe  cmp     [rbp+arg_10], rcx
0x140025c02  jz      short loc_140025C6F
0x140025c04  mov     rcx, rbx
0x140025c07  call    UMPDGetThreadClientPID
0x140025c0c  cmp     r12d, eax
0x140025c0f  jz      loc_140025A19
0x140025c15  jmp     short loc_140025C6F
0x140025c17  mov     edi, ecx
0x140025c19  call    cs:__imp_KeLeaveCriticalRegion
0x140025c20  nop     dword ptr [rax+rax+00h]
0x140025c25  jmp     loc_140025A3B
0x140025c2a  cmp     [rax+10h], rbx
0x140025c2e  jz      loc_140025A97
0x140025c34  mov     r14, r13
0x140025c37  jmp     loc_140025AA6
0x140025c3c  or      eax, 6090h
0x140025c41  jmp     short loc_140025BC4
0x140025c43  xor     eax, eax
0x140025c45  test    rbx, rbx
0x140025c48  jz      short loc_140025C6B
0x140025c4a  mov     rcx, [rbx+148h]; this
0x140025c51  test    rcx, rcx
0x140025c54  jz      short loc_140025C6B
0x140025c56  cmp     [rcx+50h], al
0x140025c59  jz      short loc_140025C6B
0x140025c5b  mov     edx, r13d; unsigned int
0x140025c5e  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x140025c63  test    al, al
0x140025c65  jnz     loc_140025A3B
0x140025c6b  mov     byte ptr [rbp+var_1C], dil
0x140025c6f  lea     rcx, [rbp+var_28]; this
0x140025c73  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x140025c78  mov     r15, [rbp+var_28]
0x140025c7c  mov     edi, [rbp+var_20]
0x140025c7f  mov     r12, [rbp+var_18]
0x140025c83  jmp     loc_140025A3B
0x140025c88  call    W32GetCurrentWin32kSessionId
0x140025c8d  mov     ebx, eax
0x140025c8f  call    cs:__imp_PsGetCurrentThreadProcess
0x140025c96  nop     dword ptr [rax+rax+00h]
0x140025c9b  mov     rcx, rax
0x140025c9e  call    cs:__imp_PsGetProcessSessionIdEx
0x140025ca5  nop     dword ptr [rax+rax+00h]
0x140025caa  cmp     ebx, eax
0x140025cac  jz      loc_1400259A9
0x140025cb2  jmp     loc_1400259B1
0x140025cb7  call    ?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x140025cbc  cmp     eax, 1
0x140025cbf  jz      loc_140025AF3
0x140025cc5  call    cs:__imp_PsIsWin32KFilterAuditEnabled
0x140025ccc  nop     dword ptr [rax+rax+00h]
0x140025cd1  test    al, al
0x140025cd3  jz      loc_140025AF3
0x140025cd9  call    cs:__imp_PsGetWin32KFilterSet
0x140025ce0  nop     dword ptr [rax+rax+00h]
0x140025ce5  jmp     loc_140025AF3
0x140025cea  mov     [rbp+arg_10], r14
0x140025cee  jmp     loc_1400259D0
0x140025cf3  lock dec word ptr [r14+0Ch]
0x140025cf9  mov     [rsi], rdi
0x140025cfc  jmp     loc_140025AF3
0x140025d01  mov     rax, [rsi]
0x140025d04  lock dec word ptr [rax+0Ch]
0x140025d09  mov     [rsi], rdi
0x140025d0c  jmp     loc_140025BCA
```
