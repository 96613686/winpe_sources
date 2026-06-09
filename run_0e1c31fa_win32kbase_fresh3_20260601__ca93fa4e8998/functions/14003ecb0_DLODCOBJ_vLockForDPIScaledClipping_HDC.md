# DLODCOBJ::vLockForDPIScaledClipping(HDC__ *)

- ea: `0x14003ecb0`
- end: `0x14003f0f6`
- name: `?vLockForDPIScaledClipping@DLODCOBJ@@QEAAXPEAUHDC__@@@Z`
- size: `1094`
- prototype: `void __fastcall(DLODCOBJ *__hidden this, HDC)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x140009c80`

## callees

- `0x140006cf8`
- `0x140008160`
- `0x140019fd0`
- `0x14001d250`
- `0x14003bf24`
- `0x14003ecb0`
- `0x14003f390`
- `0x140040150`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14003f04e`
- `ntoskrnl!PsGetCurrentProcess` at `0x14003f04e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ee5f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003efd7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ee5f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003efd7`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003eead`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003eead`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003f05d`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003f07a`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003f05d`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003f07a`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14003f0c0`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14003f0c0`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14003f06b`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14003f06b`
- `ntoskrnl!KeIsAttachedProcess` at `0x14003ed21`
- `ntoskrnl!KeIsAttachedProcess` at `0x14003ed21`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x14003f0ac`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x14003f0ac`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14003ed12`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14003ed12`

## pseudocode

```c
void __fastcall DLODCOBJ::vLockForDPIScaledClipping(DLODCOBJ *this, HDC a2)
{
  __int64 v2; // rax
  __int16 v3; // esi^2
  __int64 v5; // rbp
  __int64 v6; // r13
  unsigned int v7; // r15d
  __int64 *CurrentThreadWin32ThreadAndEnterCriticalRegion; // r14
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rdi
  __int64 v14; // rcx
  int v15; // r12d
  __int64 v16; // rax
  unsigned int *v17; // r14
  unsigned int v18; // ecx
  struct _KTHREAD *CurrentThread; // rdi
  __int64 v20; // rax
  __int64 *v21; // rsi
  __int64 v22; // rdi
  __int64 v23; // rax
  unsigned int CurrentProcessId; // eax
  __int64 v25; // rdx
  unsigned int v26; // edi
  __int64 v27; // rax
  struct _ENTRY *v28; // rax
  struct _DC_ATTR *v29; // rax
  __int64 v30; // rcx
  int v31; // eax
  unsigned int v32; // eax
  __int64 v33; // rdx
  int v34; // ecx
  int v35; // ecx
  ThreadRestrictNewHandlesRegion *v36; // rcx
  __int64 CurrentProcess; // rax
  int ProcessSessionId; // edi
  __int64 CurrentThreadProcess; // rax
  unsigned int *v40; // [rsp+20h] [rbp-58h] BYREF
  int v41; // [rsp+28h] [rbp-50h]
  __int16 v42; // [rsp+2Ch] [rbp-4Ch]
  __int64 v43; // [rsp+30h] [rbp-48h]
  __int64 v44; // [rsp+90h] [rbp+18h] BYREF
  __int64 v45; // [rsp+98h] [rbp+20h]

  v2 = *(_QWORD *)this;
  v3 = WORD1(a2);
  if ( *(_QWORD *)this )
    goto LABEL_34;
  v5 = 0;
  v6 = *((_QWORD *)this + 2);
  v42 = 0;
  v7 = (unsigned __int16)a2 | ((unsigned int)a2 >> 8) & 0xFF0000;
  v43 = v6;
  v44 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v44);
  if ( (!(unsigned __int8)KeIsAttachedProcess()
     || (CurrentProcess = PsGetCurrentProcess(v10, v9, v11),
         ProcessSessionId = PsGetProcessSessionIdEx(CurrentProcess),
         CurrentThreadProcess = PsGetCurrentThreadProcess(),
         ProcessSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)))
    && CurrentThreadWin32ThreadAndEnterCriticalRegion
    && (v12 = *CurrentThreadWin32ThreadAndEnterCriticalRegion) != 0 )
  {
    v13 = v12 + 8;
    if ( v12 != -8 )
    {
      v45 = *(_QWORD *)(v12 + 72);
      goto LABEL_7;
    }
  }
  else
  {
    v13 = 0;
  }
  v45 = 0;
LABEL_7:
  v14 = *(_QWORD *)(v6 + 8);
  v15 = 1;
  v41 = 1;
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 40LL))(v14, v7);
  v40 = (unsigned int *)v16;
  v17 = (unsigned int *)v16;
  if ( !v16 )
  {
    v15 = 0;
    KeLeaveCriticalRegion();
    goto LABEL_10;
  }
  _m_prefetchw((const void *)(v16 + 8));
  v18 = *(_DWORD *)(v16 + 8) & 0xFFFFFFFE;
  if ( v18 != (v44 & 0xFFFFFFFC) && v18 && (!v45 || v18 != (unsigned int)UMPDGetThreadClientPID(v13)) )
    goto LABEL_50;
  if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v6 + 8) + 96LL))(*(_QWORD *)(v6 + 8), *v17)
                 + 14)
      & 0x20) != 0
    && (!v13
     || (v36 = *(ThreadRestrictNewHandlesRegion **)(v13 + 328)) == 0
     || !*((_BYTE *)v36 + 80)
     || !ThreadRestrictNewHandlesRegion::InRegion(v36, v7)) )
  {
    LOBYTE(v42) = 1;
LABEL_50:
    HANDLELOCK::vUnlock((HANDLELOCK *)&v40);
    v17 = v40;
    v15 = v41;
    v6 = v43;
  }
LABEL_10:
  if ( v15 )
  {
    if ( *((_BYTE *)v17 + 14) == 1 && *((_WORD *)v17 + 6) == v3 )
    {
      CurrentThread = KeGetCurrentThread();
      v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v6 + 8) + 96LL))(*(_QWORD *)(v6 + 8), *v17);
      v5 = v20;
      if ( !*(_WORD *)(v20 + 12) || *(struct _KTHREAD **)(v20 + 16) == CurrentThread )
      {
        _InterlockedIncrement16((volatile signed __int16 *)(v20 + 12));
        *(_QWORD *)(v20 + 16) = CurrentThread;
      }
      else
      {
        v5 = 0;
      }
    }
    v21 = *(__int64 **)(v6 + 8);
    v22 = *v21;
    v23 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v21 + 96))(v21, *v17);
    (*(void (__fastcall **)(__int64 *, __int64))(v22 + 48))(v21, v23);
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
  if ( !*(_QWORD *)this )
    goto LABEL_32;
  if ( (*(_DWORD *)(*(_QWORD *)this + 44LL) & 2) != 0 )
    goto LABEL_28;
  CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
  v25 = *(_QWORD *)this;
  v26 = CurrentProcessId & 0xFFFFFFFC;
  if ( **(_QWORD **)this )
  {
    v27 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 8LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 8LL));
  }
  else
  {
    v27 = v25 + 2152;
    *(_OWORD *)(v25 + 2152) = 0;
    *(_QWORD *)(v25 + 2168) = 0;
    *(_DWORD *)(v25 + 2160) = -2147483630;
    *(_QWORD *)(v25 + 2168) = 0;
  }
  if ( v26 != (*(_DWORD *)(v27 + 8) & 0xFFFFFFFE)
    || (v28 = DC::PentryFromPobj(*(DC **)this, *((struct Gre::Base::SESSION_GLOBALS **)this + 2))) == 0
    || (v29 = (struct _DC_ATTR *)GreDecodeUserModePointer(*((void **)v28 + 2))) == 0
    || (unsigned int)DC::SaveAttributes(*(DC **)this, v29) )
  {
    *(_DWORD *)(*(_QWORD *)this + 44LL) |= 2u;
    *((_DWORD *)this + 2) = 1;
LABEL_28:
    v30 = *(_QWORD *)this;
    v31 = *(_DWORD *)(*(_QWORD *)this + 520LL);
    if ( (v31 & 4) != 0 )
    {
      v32 = v31 & 0xFFFFFFFB;
      *(_DWORD *)(v30 + 520) = v32;
      v33 = *(_QWORD *)(v30 + 976);
      v34 = *(_DWORD *)(v33 + 340);
      if ( (v32 & 1) != 0 )
        v35 = v34 | 0x16090;
      else
        v35 = v34 | 0x6090;
      *(_DWORD *)(v33 + 340) = v35;
    }
    goto LABEL_32;
  }
  _InterlockedDecrement16((volatile signed __int16 *)(*(_QWORD *)this + 12LL));
  *(_QWORD *)this = 0;
LABEL_32:
  v2 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
    return;
  *((_BYTE *)this + 97) = 0;
LABEL_34:
  *(_DWORD *)(v2 + 40) |= 2u;
  *((_BYTE *)this + 96) = 1;
}

```

## disassembly

```asm
0x14003ecb0  mov     r11, rsp
0x14003ecb3  push    rbx
0x14003ecb4  push    rsi
0x14003ecb5  sub     rsp, 68h
0x14003ecb9  mov     rax, [rcx]
0x14003ecbc  mov     rsi, rdx
0x14003ecbf  mov     rbx, rcx
0x14003ecc2  test    rax, rax
0x14003ecc5  jnz     loc_14003EF82
0x14003eccb  mov     [r11+10h], rbp
0x14003eccf  mov     [r11-20h], r12
0x14003ecd3  xor     r12d, r12d
0x14003ecd6  mov     [r11-28h], r13
0x14003ecda  mov     ebp, r12d
0x14003ecdd  mov     r13, [rcx+10h]
0x14003ece1  lea     rcx, [r11+18h]
0x14003ece5  mov     [r11-30h], r14
0x14003ece9  mov     [r11-38h], r15
0x14003eced  mov     r15d, esi
0x14003ecf0  shr     r15d, 8
0x14003ecf4  movzx   eax, si
0x14003ecf7  and     r15d, 0FF0000h
0x14003ecfe  mov     [rsp+78h+var_4C], bp
0x14003ed03  or      r15d, eax
0x14003ed06  mov     [r11-18h], rdi
0x14003ed0a  mov     [r11-48h], r13
0x14003ed0e  mov     [r11+18h], r12
0x14003ed12  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x14003ed19  nop     dword ptr [rax+rax+00h]
0x14003ed1e  mov     r14, rax
0x14003ed21  call    cs:__imp_KeIsAttachedProcess
0x14003ed28  nop     dword ptr [rax+rax+00h]
0x14003ed2d  test    al, al
0x14003ed2f  jnz     loc_14003F04E
0x14003ed35  test    r14, r14
0x14003ed38  jz      loc_14003F08E
0x14003ed3e  mov     rax, [r14]
0x14003ed41  test    rax, rax
0x14003ed44  jz      loc_14003F08E
0x14003ed4a  lea     rdi, [rax+8]
0x14003ed4e  test    rdi, rdi
0x14003ed51  jz      loc_14003F091
0x14003ed57  mov     rax, [rdi+40h]
0x14003ed5b  mov     [rsp+78h+arg_18], rax
0x14003ed63  mov     rcx, [r13+8]
0x14003ed67  mov     r12d, 1
0x14003ed6d  mov     edx, r15d
0x14003ed70  mov     [rsp+78h+var_50], r12d
0x14003ed75  mov     rax, [rcx]
0x14003ed78  mov     rax, [rax+28h]
0x14003ed7c  call    _guard_dispatch_icall
0x14003ed81  mov     [rsp+78h+var_58], rax
0x14003ed86  mov     r14, rax
0x14003ed89  test    rax, rax
0x14003ed8c  jz      loc_14003EFD4
0x14003ed92  prefetchw byte ptr [rax+8]
0x14003ed96  mov     ecx, [rax+8]
0x14003ed99  mov     eax, dword ptr [rsp+78h+arg_10]
0x14003eda0  and     ecx, 0FFFFFFFEh
0x14003eda3  and     eax, 0FFFFFFFCh
0x14003eda6  mov     [rsp+78h+arg_0], ecx
0x14003edad  cmp     ecx, eax
0x14003edaf  jnz     loc_14003EFAB
0x14003edb5  mov     rcx, [r13+8]
0x14003edb9  mov     edx, [r14]
0x14003edbc  mov     rax, [rcx]
0x14003edbf  mov     rax, [rax+60h]
0x14003edc3  call    _guard_dispatch_icall
0x14003edc8  test    byte ptr [rax+0Eh], 20h
0x14003edcc  jnz     loc_14003F004
0x14003edd2  mov     r15, [rsp+78h+var_38]
0x14003edd7  test    r12d, r12d
0x14003edda  mov     r12, [rsp+78h+var_20]
0x14003eddf  jz      loc_14003EE6B
0x14003ede5  cmp     byte ptr [r14+0Eh], 1
0x14003edea  jnz     short loc_14003EE3A
0x14003edec  movzx   ecx, byte ptr [r14+0Dh]
0x14003edf1  movzx   eax, byte ptr [r14+0Ch]
0x14003edf6  shl     cx, 8
0x14003edfa  or      cx, ax
0x14003edfd  shr     esi, 10h
0x14003ee00  cmp     cx, si
0x14003ee03  jnz     short loc_14003EE3A
0x14003ee05  mov     rdi, gs:188h
0x14003ee0e  mov     rcx, [r13+8]
0x14003ee12  mov     edx, [r14]
0x14003ee15  mov     rax, [rcx]
0x14003ee18  mov     rax, [rax+60h]
0x14003ee1c  call    _guard_dispatch_icall
0x14003ee21  mov     rbp, rax
0x14003ee24  movzx   ecx, word ptr [rax+0Ch]
0x14003ee28  test    cx, cx
0x14003ee2b  jnz     loc_14003EFE8
0x14003ee31  lock inc word ptr [rax+0Ch]
0x14003ee36  mov     [rax+10h], rdi
0x14003ee3a  mov     rsi, [r13+8]
0x14003ee3e  mov     edx, [r14]
0x14003ee41  mov     rcx, rsi
0x14003ee44  mov     rdi, [rsi]
0x14003ee47  mov     rax, [rdi+60h]
0x14003ee4b  call    _guard_dispatch_icall
0x14003ee50  mov     rdx, rax
0x14003ee53  mov     rcx, rsi
0x14003ee56  mov     rax, [rdi+30h]
0x14003ee5a  call    _guard_dispatch_icall
0x14003ee5f  call    cs:__imp_KeLeaveCriticalRegion
0x14003ee66  nop     dword ptr [rax+rax+00h]
0x14003ee6b  mov     r14, [rsp+78h+var_30]
0x14003ee70  mov     r13, [rsp+78h+var_28]
0x14003ee75  mov     [rbx], rbp
0x14003ee78  test    rbp, rbp
0x14003ee7b  jz      loc_14003F09E
0x14003ee81  cmp     dword ptr [rbp+858h], 0
0x14003ee88  jnz     loc_14003F0D1
0x14003ee8e  mov     rax, [rbx]
0x14003ee91  mov     rbp, [rsp+78h+arg_8]
0x14003ee99  test    rax, rax
0x14003ee9c  jz      loc_14003EF71
0x14003eea2  mov     eax, [rax+2Ch]
0x14003eea5  test    al, 2
0x14003eea7  jnz     loc_14003EF3A
0x14003eead  call    cs:__imp_PsGetCurrentProcessId
0x14003eeb4  nop     dword ptr [rax+rax+00h]
0x14003eeb9  mov     rdx, [rbx]
0x14003eebc  mov     rdi, rax
0x14003eebf  and     edi, 0FFFFFFFCh
0x14003eec2  cmp     qword ptr [rdx], 0
0x14003eec6  jnz     loc_14003EF92
0x14003eecc  lea     rax, [rdx+868h]
0x14003eed3  xor     ecx, ecx
0x14003eed5  xorps   xmm0, xmm0
0x14003eed8  movups  xmmword ptr [rax], xmm0
0x14003eedb  mov     [rax+10h], rcx
0x14003eedf  mov     dword ptr [rdx+870h], 80000012h
0x14003eee9  mov     [rdx+878h], rcx
0x14003eef0  mov     eax, [rax+8]
0x14003eef3  and     eax, 0FFFFFFFEh
0x14003eef6  cmp     edi, eax
0x14003eef8  jnz     short loc_14003EF2C
0x14003eefa  mov     rdx, [rbx+10h]; struct Gre::Base::SESSION_GLOBALS *
0x14003eefe  mov     rcx, [rbx]; this
0x14003ef01  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x14003ef06  test    rax, rax
0x14003ef09  jz      short loc_14003EF2C
0x14003ef0b  mov     rcx, [rax+10h]; void *
0x14003ef0f  call    ?GreDecodeUserModePointer@@YAPEAXPEAX@Z; GreDecodeUserModePointer(void *)
0x14003ef14  test    rax, rax
0x14003ef17  jz      short loc_14003EF2C
0x14003ef19  mov     rcx, [rbx]; this
0x14003ef1c  mov     rdx, rax; struct _DC_ATTR *
0x14003ef1f  call    ?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x14003ef24  test    eax, eax
0x14003ef26  jz      loc_14003F0E2
0x14003ef2c  mov     rax, [rbx]
0x14003ef2f  or      dword ptr [rax+2Ch], 2
0x14003ef33  mov     dword ptr [rbx+8], 1
0x14003ef3a  mov     rcx, [rbx]
0x14003ef3d  mov     eax, [rcx+208h]
0x14003ef43  test    al, 4
0x14003ef45  jz      short loc_14003EF71
0x14003ef47  and     eax, 0FFFFFFFBh
0x14003ef4a  mov     [rcx+208h], eax
0x14003ef50  mov     rdx, [rcx+3D0h]
0x14003ef57  mov     ecx, [rdx+154h]
0x14003ef5d  test    al, 1
0x14003ef5f  jz      loc_14003EFF9
0x14003ef65  or      ecx, 16090h
0x14003ef6b  mov     [rdx+154h], ecx
0x14003ef71  mov     rax, [rbx]
0x14003ef74  mov     rdi, [rsp+78h+var_18]
0x14003ef79  test    rax, rax
0x14003ef7c  jz      short loc_14003EF8A
0x14003ef7e  mov     byte ptr [rbx+61h], 0
0x14003ef82  or      dword ptr [rax+28h], 2
0x14003ef86  mov     byte ptr [rbx+60h], 1
0x14003ef8a  add     rsp, 68h
0x14003ef8e  pop     rsi
0x14003ef8f  pop     rbx
0x14003ef90  retn
0x14003ef92  mov     rax, [rbx+10h]
0x14003ef96  mov     rcx, [rax+8]
0x14003ef9a  mov     rax, [rcx]
0x14003ef9d  mov     rax, [rax+8]
0x14003efa1  call    _guard_dispatch_icall
0x14003efa6  jmp     loc_14003EEF0
0x14003efab  test    ecx, ecx
0x14003efad  jz      loc_14003EDB5
0x14003efb3  cmp     [rsp+78h+arg_18], rbp
0x14003efbb  jz      short loc_14003F030
0x14003efbd  mov     rcx, rdi
0x14003efc0  call    UMPDGetThreadClientPID
0x14003efc5  cmp     [rsp+78h+arg_0], eax
0x14003efcc  jz      loc_14003EDB5
0x14003efd2  jmp     short loc_14003F030
0x14003efd4  xor     r12d, r12d
0x14003efd7  call    cs:__imp_KeLeaveCriticalRegion
0x14003efde  nop     dword ptr [rax+rax+00h]
0x14003efe3  jmp     loc_14003EDD2
0x14003efe8  cmp     [rax+10h], rdi
0x14003efec  jz      loc_14003EE31
0x14003eff2  xor     ebp, ebp
0x14003eff4  jmp     loc_14003EE3A
0x14003eff9  or      ecx, 6090h
0x14003efff  jmp     loc_14003EF6B
0x14003f004  test    rdi, rdi
0x14003f007  jz      short loc_14003F02B
0x14003f009  mov     rcx, [rdi+148h]; this
0x14003f010  test    rcx, rcx
0x14003f013  jz      short loc_14003F02B
0x14003f015  cmp     [rcx+50h], bpl
0x14003f019  jz      short loc_14003F02B
0x14003f01b  mov     edx, r15d; unsigned int
0x14003f01e  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x14003f023  test    al, al
0x14003f025  jnz     loc_14003EDD2
0x14003f02b  mov     byte ptr [rsp+78h+var_4C], r12b
0x14003f030  lea     rcx, [rsp+78h+var_58]; this
0x14003f035  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x14003f03a  mov     r14, [rsp+78h+var_58]
0x14003f03f  mov     r12d, [rsp+78h+var_50]
0x14003f044  mov     r13, [rsp+78h+var_48]
0x14003f049  jmp     loc_14003EDD2
0x14003f04e  call    cs:__imp_PsGetCurrentProcess
0x14003f055  nop     dword ptr [rax+rax+00h]
0x14003f05a  mov     rcx, rax
0x14003f05d  call    cs:__imp_PsGetProcessSessionIdEx
0x14003f064  nop     dword ptr [rax+rax+00h]
0x14003f069  mov     edi, eax
0x14003f06b  call    cs:__imp_PsGetCurrentThreadProcess
0x14003f072  nop     dword ptr [rax+rax+00h]
0x14003f077  mov     rcx, rax
0x14003f07a  call    cs:__imp_PsGetProcessSessionIdEx
0x14003f081  nop     dword ptr [rax+rax+00h]
0x14003f086  cmp     edi, eax
0x14003f088  jz      loc_14003ED35
0x14003f08e  mov     rdi, r12
0x14003f091  mov     [rsp+78h+arg_18], r12
0x14003f099  jmp     loc_14003ED63
0x14003f09e  call    ?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x14003f0a3  cmp     eax, 1
0x14003f0a6  jz      loc_14003EE8E
0x14003f0ac  call    cs:__imp_PsIsWin32KFilterAuditEnabled
0x14003f0b3  nop     dword ptr [rax+rax+00h]
0x14003f0b8  test    al, al
0x14003f0ba  jz      loc_14003EE8E
0x14003f0c0  call    cs:__imp_PsGetWin32KFilterSet
0x14003f0c7  nop     dword ptr [rax+rax+00h]
0x14003f0cc  jmp     loc_14003EE8E
0x14003f0d1  lock dec word ptr [rbp+0Ch]
0x14003f0d6  mov     qword ptr [rbx], 0
0x14003f0dd  jmp     loc_14003EE8E
0x14003f0e2  mov     rax, [rbx]
0x14003f0e5  lock dec word ptr [rax+0Ch]
0x14003f0ea  mov     qword ptr [rbx], 0
0x14003f0f1  jmp     loc_14003EF71
```
