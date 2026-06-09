# DLODCOBJ::vLockForDPIScaledClipping(HDC__ *)

- ea: `0x140047bc0`
- end: `0x140048006`
- name: `?vLockForDPIScaledClipping@DLODCOBJ@@QEAAXPEAUHDC__@@@Z`
- size: `1094`
- prototype: `void __fastcall(DLODCOBJ *__hidden this, HDC)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x140012df0`

## callees

- `0x140010e60`
- `0x140022ff0`
- `0x140026270`
- `0x140043e04`
- `0x140047bc0`
- `0x1400482a0`
- `0x140049060`
- `0x1400f0fb8`
- `0x140238240`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140047f5e`
- `ntoskrnl!PsGetCurrentProcess` at `0x140047f5e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047d6f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047ee7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047d6f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047ee7`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140047dbd`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140047dbd`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140047f6d`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140047f8a`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140047f6d`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140047f8a`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x140047fd0`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x140047fd0`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140047f7b`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140047f7b`
- `ntoskrnl!KeIsAttachedProcess` at `0x140047c31`
- `ntoskrnl!KeIsAttachedProcess` at `0x140047c31`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x140047fbc`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x140047fbc`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x140047c22`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x140047c22`

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
0x140047bc0  mov     r11, rsp
0x140047bc3  push    rbx
0x140047bc4  push    rsi
0x140047bc5  sub     rsp, 68h
0x140047bc9  mov     rax, [rcx]
0x140047bcc  mov     rsi, rdx
0x140047bcf  mov     rbx, rcx
0x140047bd2  test    rax, rax
0x140047bd5  jnz     loc_140047E92
0x140047bdb  mov     [r11+10h], rbp
0x140047bdf  mov     [r11-20h], r12
0x140047be3  xor     r12d, r12d
0x140047be6  mov     [r11-28h], r13
0x140047bea  mov     ebp, r12d
0x140047bed  mov     r13, [rcx+10h]
0x140047bf1  lea     rcx, [r11+18h]
0x140047bf5  mov     [r11-30h], r14
0x140047bf9  mov     [r11-38h], r15
0x140047bfd  mov     r15d, esi
0x140047c00  shr     r15d, 8
0x140047c04  movzx   eax, si
0x140047c07  and     r15d, 0FF0000h
0x140047c0e  mov     [rsp+78h+var_4C], bp
0x140047c13  or      r15d, eax
0x140047c16  mov     [r11-18h], rdi
0x140047c1a  mov     [r11-48h], r13
0x140047c1e  mov     [r11+18h], r12
0x140047c22  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x140047c29  nop     dword ptr [rax+rax+00h]
0x140047c2e  mov     r14, rax
0x140047c31  call    cs:__imp_KeIsAttachedProcess
0x140047c38  nop     dword ptr [rax+rax+00h]
0x140047c3d  test    al, al
0x140047c3f  jnz     loc_140047F5E
0x140047c45  test    r14, r14
0x140047c48  jz      loc_140047F9E
0x140047c4e  mov     rax, [r14]
0x140047c51  test    rax, rax
0x140047c54  jz      loc_140047F9E
0x140047c5a  lea     rdi, [rax+8]
0x140047c5e  test    rdi, rdi
0x140047c61  jz      loc_140047FA1
0x140047c67  mov     rax, [rdi+40h]
0x140047c6b  mov     [rsp+78h+arg_18], rax
0x140047c73  mov     rcx, [r13+8]
0x140047c77  mov     r12d, 1
0x140047c7d  mov     edx, r15d
0x140047c80  mov     [rsp+78h+var_50], r12d
0x140047c85  mov     rax, [rcx]
0x140047c88  mov     rax, [rax+28h]
0x140047c8c  call    _guard_dispatch_icall
0x140047c91  mov     [rsp+78h+var_58], rax
0x140047c96  mov     r14, rax
0x140047c99  test    rax, rax
0x140047c9c  jz      loc_140047EE4
0x140047ca2  prefetchw byte ptr [rax+8]
0x140047ca6  mov     ecx, [rax+8]
0x140047ca9  mov     eax, dword ptr [rsp+78h+arg_10]
0x140047cb0  and     ecx, 0FFFFFFFEh
0x140047cb3  and     eax, 0FFFFFFFCh
0x140047cb6  mov     [rsp+78h+arg_0], ecx
0x140047cbd  cmp     ecx, eax
0x140047cbf  jnz     loc_140047EBB
0x140047cc5  mov     rcx, [r13+8]
0x140047cc9  mov     edx, [r14]
0x140047ccc  mov     rax, [rcx]
0x140047ccf  mov     rax, [rax+60h]
0x140047cd3  call    _guard_dispatch_icall
0x140047cd8  test    byte ptr [rax+0Eh], 20h
0x140047cdc  jnz     loc_140047F14
0x140047ce2  mov     r15, [rsp+78h+var_38]
0x140047ce7  test    r12d, r12d
0x140047cea  mov     r12, [rsp+78h+var_20]
0x140047cef  jz      loc_140047D7B
0x140047cf5  cmp     byte ptr [r14+0Eh], 1
0x140047cfa  jnz     short loc_140047D4A
0x140047cfc  movzx   ecx, byte ptr [r14+0Dh]
0x140047d01  movzx   eax, byte ptr [r14+0Ch]
0x140047d06  shl     cx, 8
0x140047d0a  or      cx, ax
0x140047d0d  shr     esi, 10h
0x140047d10  cmp     cx, si
0x140047d13  jnz     short loc_140047D4A
0x140047d15  mov     rdi, gs:188h
0x140047d1e  mov     rcx, [r13+8]
0x140047d22  mov     edx, [r14]
0x140047d25  mov     rax, [rcx]
0x140047d28  mov     rax, [rax+60h]
0x140047d2c  call    _guard_dispatch_icall
0x140047d31  mov     rbp, rax
0x140047d34  movzx   ecx, word ptr [rax+0Ch]
0x140047d38  test    cx, cx
0x140047d3b  jnz     loc_140047EF8
0x140047d41  lock inc word ptr [rax+0Ch]
0x140047d46  mov     [rax+10h], rdi
0x140047d4a  mov     rsi, [r13+8]
0x140047d4e  mov     edx, [r14]
0x140047d51  mov     rcx, rsi
0x140047d54  mov     rdi, [rsi]
0x140047d57  mov     rax, [rdi+60h]
0x140047d5b  call    _guard_dispatch_icall
0x140047d60  mov     rdx, rax
0x140047d63  mov     rcx, rsi
0x140047d66  mov     rax, [rdi+30h]
0x140047d6a  call    _guard_dispatch_icall
0x140047d6f  call    cs:__imp_KeLeaveCriticalRegion
0x140047d76  nop     dword ptr [rax+rax+00h]
0x140047d7b  mov     r14, [rsp+78h+var_30]
0x140047d80  mov     r13, [rsp+78h+var_28]
0x140047d85  mov     [rbx], rbp
0x140047d88  test    rbp, rbp
0x140047d8b  jz      loc_140047FAE
0x140047d91  cmp     dword ptr [rbp+858h], 0
0x140047d98  jnz     loc_140047FE1
0x140047d9e  mov     rax, [rbx]
0x140047da1  mov     rbp, [rsp+78h+arg_8]
0x140047da9  test    rax, rax
0x140047dac  jz      loc_140047E81
0x140047db2  mov     eax, [rax+2Ch]
0x140047db5  test    al, 2
0x140047db7  jnz     loc_140047E4A
0x140047dbd  call    cs:__imp_PsGetCurrentProcessId
0x140047dc4  nop     dword ptr [rax+rax+00h]
0x140047dc9  mov     rdx, [rbx]
0x140047dcc  mov     rdi, rax
0x140047dcf  and     edi, 0FFFFFFFCh
0x140047dd2  cmp     qword ptr [rdx], 0
0x140047dd6  jnz     loc_140047EA2
0x140047ddc  lea     rax, [rdx+868h]
0x140047de3  xor     ecx, ecx
0x140047de5  xorps   xmm0, xmm0
0x140047de8  movups  xmmword ptr [rax], xmm0
0x140047deb  mov     [rax+10h], rcx
0x140047def  mov     dword ptr [rdx+870h], 80000012h
0x140047df9  mov     [rdx+878h], rcx
0x140047e00  mov     eax, [rax+8]
0x140047e03  and     eax, 0FFFFFFFEh
0x140047e06  cmp     edi, eax
0x140047e08  jnz     short loc_140047E3C
0x140047e0a  mov     rdx, [rbx+10h]; struct Gre::Base::SESSION_GLOBALS *
0x140047e0e  mov     rcx, [rbx]; this
0x140047e11  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x140047e16  test    rax, rax
0x140047e19  jz      short loc_140047E3C
0x140047e1b  mov     rcx, [rax+10h]; void *
0x140047e1f  call    ?GreDecodeUserModePointer@@YAPEAXPEAX@Z; GreDecodeUserModePointer(void *)
0x140047e24  test    rax, rax
0x140047e27  jz      short loc_140047E3C
0x140047e29  mov     rcx, [rbx]; this
0x140047e2c  mov     rdx, rax; struct _DC_ATTR *
0x140047e2f  call    ?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x140047e34  test    eax, eax
0x140047e36  jz      loc_140047FF2
0x140047e3c  mov     rax, [rbx]
0x140047e3f  or      dword ptr [rax+2Ch], 2
0x140047e43  mov     dword ptr [rbx+8], 1
0x140047e4a  mov     rcx, [rbx]
0x140047e4d  mov     eax, [rcx+208h]
0x140047e53  test    al, 4
0x140047e55  jz      short loc_140047E81
0x140047e57  and     eax, 0FFFFFFFBh
0x140047e5a  mov     [rcx+208h], eax
0x140047e60  mov     rdx, [rcx+3D0h]
0x140047e67  mov     ecx, [rdx+154h]
0x140047e6d  test    al, 1
0x140047e6f  jz      loc_140047F09
0x140047e75  or      ecx, 16090h
0x140047e7b  mov     [rdx+154h], ecx
0x140047e81  mov     rax, [rbx]
0x140047e84  mov     rdi, [rsp+78h+var_18]
0x140047e89  test    rax, rax
0x140047e8c  jz      short loc_140047E9A
0x140047e8e  mov     byte ptr [rbx+61h], 0
0x140047e92  or      dword ptr [rax+28h], 2
0x140047e96  mov     byte ptr [rbx+60h], 1
0x140047e9a  add     rsp, 68h
0x140047e9e  pop     rsi
0x140047e9f  pop     rbx
0x140047ea0  retn
0x140047ea2  mov     rax, [rbx+10h]
0x140047ea6  mov     rcx, [rax+8]
0x140047eaa  mov     rax, [rcx]
0x140047ead  mov     rax, [rax+8]
0x140047eb1  call    _guard_dispatch_icall
0x140047eb6  jmp     loc_140047E00
0x140047ebb  test    ecx, ecx
0x140047ebd  jz      loc_140047CC5
0x140047ec3  cmp     [rsp+78h+arg_18], rbp
0x140047ecb  jz      short loc_140047F40
0x140047ecd  mov     rcx, rdi
0x140047ed0  call    UMPDGetThreadClientPID
0x140047ed5  cmp     [rsp+78h+arg_0], eax
0x140047edc  jz      loc_140047CC5
0x140047ee2  jmp     short loc_140047F40
0x140047ee4  xor     r12d, r12d
0x140047ee7  call    cs:__imp_KeLeaveCriticalRegion
0x140047eee  nop     dword ptr [rax+rax+00h]
0x140047ef3  jmp     loc_140047CE2
0x140047ef8  cmp     [rax+10h], rdi
0x140047efc  jz      loc_140047D41
0x140047f02  xor     ebp, ebp
0x140047f04  jmp     loc_140047D4A
0x140047f09  or      ecx, 6090h
0x140047f0f  jmp     loc_140047E7B
0x140047f14  test    rdi, rdi
0x140047f17  jz      short loc_140047F3B
0x140047f19  mov     rcx, [rdi+148h]; this
0x140047f20  test    rcx, rcx
0x140047f23  jz      short loc_140047F3B
0x140047f25  cmp     [rcx+50h], bpl
0x140047f29  jz      short loc_140047F3B
0x140047f2b  mov     edx, r15d; unsigned int
0x140047f2e  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x140047f33  test    al, al
0x140047f35  jnz     loc_140047CE2
0x140047f3b  mov     byte ptr [rsp+78h+var_4C], r12b
0x140047f40  lea     rcx, [rsp+78h+var_58]; this
0x140047f45  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x140047f4a  mov     r14, [rsp+78h+var_58]
0x140047f4f  mov     r12d, [rsp+78h+var_50]
0x140047f54  mov     r13, [rsp+78h+var_48]
0x140047f59  jmp     loc_140047CE2
0x140047f5e  call    cs:__imp_PsGetCurrentProcess
0x140047f65  nop     dword ptr [rax+rax+00h]
0x140047f6a  mov     rcx, rax
0x140047f6d  call    cs:__imp_PsGetProcessSessionIdEx
0x140047f74  nop     dword ptr [rax+rax+00h]
0x140047f79  mov     edi, eax
0x140047f7b  call    cs:__imp_PsGetCurrentThreadProcess
0x140047f82  nop     dword ptr [rax+rax+00h]
0x140047f87  mov     rcx, rax
0x140047f8a  call    cs:__imp_PsGetProcessSessionIdEx
0x140047f91  nop     dword ptr [rax+rax+00h]
0x140047f96  cmp     edi, eax
0x140047f98  jz      loc_140047C45
0x140047f9e  mov     rdi, r12
0x140047fa1  mov     [rsp+78h+arg_18], r12
0x140047fa9  jmp     loc_140047C73
0x140047fae  call    ?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x140047fb3  cmp     eax, 1
0x140047fb6  jz      loc_140047D9E
0x140047fbc  call    cs:__imp_PsIsWin32KFilterAuditEnabled
0x140047fc3  nop     dword ptr [rax+rax+00h]
0x140047fc8  test    al, al
0x140047fca  jz      loc_140047D9E
0x140047fd0  call    cs:__imp_PsGetWin32KFilterSet
0x140047fd7  nop     dword ptr [rax+rax+00h]
0x140047fdc  jmp     loc_140047D9E
0x140047fe1  lock dec word ptr [rbp+0Ch]
0x140047fe6  mov     qword ptr [rbx], 0
0x140047fed  jmp     loc_140047D9E
0x140047ff2  mov     rax, [rbx]
0x140047ff5  lock dec word ptr [rax+0Ch]
0x140047ffa  mov     qword ptr [rbx], 0
0x140048001  jmp     loc_140047E81
```
