# HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)

- ea: `0x14001b910`
- end: `0x14001bc8e`
- name: `?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z`
- size: `894`
- prototype: ``
- caller_count: `35`
- callee_count: `7`
- tags: ``

## callers

- `0x140010594`
- `0x1400160c0`
- `0x140016f70`
- `0x140018d20`
- `0x140019670`
- `0x14001a0f0`
- `0x14001b7a0`
- `0x140025bf8`
- `0x1400296a4`
- `0x140036160`
- `0x14003653c`
- `0x140036940`
- `0x140037ba0`
- `0x140037c80`
- `0x140038024`
- `0x1400b2d50`
- `0x1400b3bb0`
- `0x1400fe910`
- `0x1400ffa80`
- `0x14013a280`
- `0x1401435d0`
- `0x14015d980`
- `0x14016d0a0`
- `0x14016d410`
- `0x140192770`
- `0x1401b29c8`
- `0x1401bcce4`
- `0x1401c1698`
- `0x1401e6bd8`
- `0x1401e6c7c`
- `0x1401e6d5c`
- `0x1401e6e78`
- `0x1401e6f48`
- `0x1402df07c`
- `0x1402df930`

## callees

- `0x140006cf8`
- `0x1400178f0`
- `0x14001b910`
- `0x14001bf04`
- `0x14001d250`
- `0x14003bf24`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14001bbd6`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001bbd6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001bac7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001bb58`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001bac7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001bb58`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001bbe5`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001bc02`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001bbe5`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001bc02`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001bbf3`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001bbf3`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001b96f`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001b96f`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14001b960`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14001b960`

## pseudocode

```c
__int64 __fastcall HmgShareLock(__int64 a1, unsigned int a2, char a3, char a4)
{
  unsigned int v4; // r14d
  __int64 v8; // r13
  __int64 *CurrentThreadWin32ThreadAndEnterCriticalRegion; // rdi
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // rdi
  int v15; // ebp
  __int64 v16; // rax
  unsigned __int8 *v17; // rbx
  unsigned int v18; // ecx
  int v19; // eax
  int v20; // edx
  unsigned int v21; // esi
  bool v22; // zf
  __int64 v23; // rsi
  __int64 v24; // rax
  __int64 *v25; // rsi
  __int64 v26; // rdi
  __int64 v27; // rax
  ThreadRestrictNewHandlesRegion *v29; // rcx
  __int64 v30; // r8
  __int64 CurrentProcess; // rax
  int ProcessSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  __int64 v34; // [rsp+30h] [rbp-68h] BYREF
  __int64 v35; // [rsp+38h] [rbp-60h]
  unsigned __int8 *v36; // [rsp+40h] [rbp-58h] BYREF
  int v37; // [rsp+48h] [rbp-50h]
  __int16 v38; // [rsp+4Ch] [rbp-4Ch]
  __int64 v39; // [rsp+50h] [rbp-48h]

  v39 = a1;
  v38 = 0;
  v4 = (unsigned __int16)a2 | (a2 >> 8) & 0xFF0000;
  v34 = 0;
  v8 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v34);
  if ( (!(unsigned __int8)KeIsAttachedProcess()
     || (CurrentProcess = PsGetCurrentProcess(v11, v10, v12),
         ProcessSessionId = PsGetProcessSessionIdEx(CurrentProcess),
         CurrentThreadProcess = PsGetCurrentThreadProcess(),
         ProcessSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)))
    && CurrentThreadWin32ThreadAndEnterCriticalRegion
    && (v13 = *CurrentThreadWin32ThreadAndEnterCriticalRegion) != 0 )
  {
    v14 = v13 + 8;
    if ( v13 != -8 )
    {
      v35 = *(_QWORD *)(v13 + 72);
      goto LABEL_6;
    }
  }
  else
  {
    v14 = 0;
  }
  v35 = 0;
LABEL_6:
  v15 = 1;
  v37 = 1;
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 8) + 40LL))(*(_QWORD *)(a1 + 8), v4);
  v36 = (unsigned __int8 *)v16;
  v17 = (unsigned __int8 *)v16;
  if ( v16 )
  {
    _m_prefetchw((const void *)(v16 + 8));
    if ( (a4 & 1) == 0 )
    {
      v18 = *(_DWORD *)(v16 + 8) & 0xFFFFFFFE;
      if ( v18 != (v34 & 0xFFFFFFFC) && v18 && (!v35 || v18 != (unsigned int)UMPDGetThreadClientPID(v14)) )
      {
        if ( (a4 & 8) == 0 )
        {
LABEL_25:
          HANDLELOCK::vUnlock((HANDLELOCK *)&v36);
          v15 = v37;
          v17 = v36;
          goto LABEL_10;
        }
        v30 = 1;
LABEL_36:
        GrepCaptureLiveMemoryDump(400, 56, v30, 0, 0, 0);
        goto LABEL_25;
      }
    }
    if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 8) + 96LL))(
                       *(_QWORD *)(a1 + 8),
                       *(unsigned int *)v17)
                   + 14)
        & 0x20) != 0
      && (!v14
       || (v29 = *(ThreadRestrictNewHandlesRegion **)(v14 + 328)) == 0
       || !*((_BYTE *)v29 + 80)
       || !ThreadRestrictNewHandlesRegion::InRegion(v29, v4)) )
    {
      LOBYTE(v38) = 1;
      if ( (a4 & 8) == 0 )
        goto LABEL_25;
      v30 = 6;
      goto LABEL_36;
    }
  }
  else
  {
    if ( (a4 & 8) != 0 )
      GrepCaptureLiveMemoryDump(400, 56, 0, 0, 0, 0);
    v15 = 0;
    KeLeaveCriticalRegion();
  }
LABEL_10:
  if ( v15 )
  {
    if ( v17[14] == a3 )
    {
      v19 = v17[13];
      v20 = v17[12];
      v21 = HIWORD(a2);
      if ( (a4 & 0x10) != 0 )
        v22 = ((v21 ^ (v20 | (v19 << 8))) & 0xFFFFFF7F) == 0;
      else
        v22 = ((unsigned __int16)v20 | (unsigned __int16)((_WORD)v19 << 8)) == (_WORD)v21;
      v23 = v39;
      if ( v22 )
      {
        v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v39 + 8) + 96LL))(
                *(_QWORD *)(v39 + 8),
                *(unsigned int *)v17);
        v8 = v24;
        ++*(_DWORD *)(v24 + 8);
        switch ( a3 )
        {
          case 5:
            TrackObjectReferenceIncrement(a1, 3, *(_QWORD *)(v24 + 728));
            break;
          case 4:
            TrackObjectReferenceIncrement(a1, 2, *(_QWORD *)(v24 + 112));
            break;
          case 16:
            TrackObjectReferenceIncrement(a1, 0, *(_QWORD *)(v24 + 136));
            break;
        }
      }
    }
    else
    {
      v23 = v39;
    }
    v25 = *(__int64 **)(v23 + 8);
    v26 = *v25;
    v27 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v25 + 96))(v25, *(unsigned int *)v17);
    (*(void (__fastcall **)(__int64 *, __int64))(v26 + 48))(v25, v27);
    KeLeaveCriticalRegion();
  }
  return v8;
}

```

## disassembly

```asm
0x14001b910  mov     [rsp+arg_10], rbx
0x14001b915  mov     [rsp+arg_0], rcx
0x14001b91a  push    rbp
0x14001b91b  push    rsi
0x14001b91c  push    rdi
0x14001b91d  push    r12
0x14001b91f  push    r13
0x14001b921  push    r14
0x14001b923  push    r15
0x14001b925  sub     rsp, 60h
0x14001b929  xor     ebp, ebp
0x14001b92b  mov     [rsp+98h+var_48], rcx
0x14001b930  mov     r14d, edx
0x14001b933  movzx   eax, dx
0x14001b936  shr     r14d, 8
0x14001b93a  lea     rcx, [rsp+98h+var_68]
0x14001b93f  and     r14d, 0FF0000h
0x14001b946  mov     [rsp+98h+var_4C], bp
0x14001b94b  or      r14d, eax
0x14001b94e  mov     [rsp+98h+var_68], rbp
0x14001b953  mov     r12d, r9d
0x14001b956  movzx   r15d, r8b
0x14001b95a  mov     rsi, rdx
0x14001b95d  mov     r13d, ebp
0x14001b960  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x14001b967  nop     dword ptr [rax+rax+00h]
0x14001b96c  mov     rdi, rax
0x14001b96f  call    cs:__imp_KeIsAttachedProcess
0x14001b976  nop     dword ptr [rax+rax+00h]
0x14001b97b  test    al, al
0x14001b97d  jnz     loc_14001BBD6
0x14001b983  test    rdi, rdi
0x14001b986  jz      loc_14001BC16
0x14001b98c  mov     rax, [rdi]
0x14001b98f  test    rax, rax
0x14001b992  jz      loc_14001BC16
0x14001b998  lea     rdi, [rax+8]
0x14001b99c  test    rdi, rdi
0x14001b99f  jz      loc_14001BC19
0x14001b9a5  mov     rax, [rdi+40h]
0x14001b9a9  mov     [rsp+98h+var_60], rax
0x14001b9ae  mov     rcx, [rsp+98h+arg_0]
0x14001b9b6  mov     ebp, 1
0x14001b9bb  mov     edx, r14d
0x14001b9be  mov     [rsp+98h+var_50], ebp
0x14001b9c2  mov     rcx, [rcx+8]
0x14001b9c6  mov     rax, [rcx]
0x14001b9c9  mov     rax, [rax+28h]
0x14001b9cd  call    _guard_dispatch_icall
0x14001b9d2  mov     [rsp+98h+var_58], rax
0x14001b9d7  mov     rbx, rax
0x14001b9da  test    rax, rax
0x14001b9dd  jz      loc_14001BB4C
0x14001b9e3  prefetchw byte ptr [rax+8]
0x14001b9e7  test    bpl, r12b
0x14001b9ea  jnz     short loc_14001BA08
0x14001b9ec  mov     ecx, [rax+8]
0x14001b9ef  mov     eax, dword ptr [rsp+98h+var_68]
0x14001b9f3  and     ecx, 0FFFFFFFEh
0x14001b9f6  and     eax, 0FFFFFFFCh
0x14001b9f9  mov     [rsp+98h+arg_8], ecx
0x14001ba00  cmp     ecx, eax
0x14001ba02  jnz     loc_14001BB17
0x14001ba08  mov     rax, [rsp+98h+arg_0]
0x14001ba10  mov     edx, [rbx]
0x14001ba12  mov     rcx, [rax+8]
0x14001ba16  mov     rax, [rcx]
0x14001ba19  mov     rax, [rax+60h]
0x14001ba1d  call    _guard_dispatch_icall
0x14001ba22  test    byte ptr [rax+0Eh], 20h
0x14001ba26  jnz     loc_14001BB7D
0x14001ba2c  test    ebp, ebp
0x14001ba2e  jz      loc_14001BAD3
0x14001ba34  cmp     [rbx+0Eh], r15b
0x14001ba38  jnz     loc_14001BC3E
0x14001ba3e  movzx   eax, byte ptr [rbx+0Dh]
0x14001ba42  movzx   edx, byte ptr [rbx+0Ch]
0x14001ba46  shr     esi, 10h
0x14001ba49  test    r12b, 10h
0x14001ba4d  jnz     loc_14001BB69
0x14001ba53  movzx   ecx, ax
0x14001ba56  shl     cx, 8
0x14001ba5a  or      cx, dx
0x14001ba5d  cmp     cx, si
0x14001ba60  mov     rsi, [rsp+98h+var_48]
0x14001ba65  setz    al
0x14001ba68  test    al, al
0x14001ba6a  jz      short loc_14001BAA3
0x14001ba6c  mov     rcx, [rsi+8]
0x14001ba70  mov     edx, [rbx]
0x14001ba72  mov     rax, [rcx]
0x14001ba75  mov     rax, [rax+60h]
0x14001ba79  call    _guard_dispatch_icall
0x14001ba7e  mov     r13, rax
0x14001ba81  inc     dword ptr [rax+8]
0x14001ba84  cmp     r15b, 5
0x14001ba88  jnz     short loc_14001BAEF
0x14001ba8a  mov     r8, [rax+2D8h]
0x14001ba91  mov     edx, 3
0x14001ba96  mov     rcx, [rsp+98h+arg_0]
0x14001ba9e  call    ?TrackObjectReferenceIncrement@@YAXAEAUSESSION_GLOBALS@Base@Gre@@W4ReferenceTrackerCountedType@@PEAX@Z; TrackObjectReferenceIncrement(Gre::Base::SESSION_GLOBALS &,ReferenceTrackerCountedType,void *)
0x14001baa3  mov     rsi, [rsi+8]
0x14001baa7  mov     edx, [rbx]
0x14001baa9  mov     rcx, rsi
0x14001baac  mov     rdi, [rsi]
0x14001baaf  mov     rax, [rdi+60h]
0x14001bab3  call    _guard_dispatch_icall
0x14001bab8  mov     rdx, rax
0x14001babb  mov     rcx, rsi
0x14001babe  mov     rax, [rdi+30h]
0x14001bac2  call    _guard_dispatch_icall
0x14001bac7  call    cs:__imp_KeLeaveCriticalRegion
0x14001bace  nop     dword ptr [rax+rax+00h]
0x14001bad3  mov     rbx, [rsp+98h+arg_10]
0x14001badb  mov     rax, r13
0x14001bade  add     rsp, 60h
0x14001bae2  pop     r15
0x14001bae4  pop     r14
0x14001bae6  pop     r13
0x14001bae8  pop     r12
0x14001baea  pop     rdi
0x14001baeb  pop     rsi
0x14001baec  pop     rbp
0x14001baed  retn
0x14001baef  cmp     r15b, 4
0x14001baf3  jz      loc_14001BC23
0x14001baf9  cmp     r15b, 10h
0x14001bafd  jnz     short loc_14001BAA3
0x14001baff  mov     r8, [rax+88h]
0x14001bb06  xor     edx, edx
0x14001bb08  mov     rcx, [rsp+98h+arg_0]
0x14001bb10  call    ?TrackObjectReferenceIncrement@@YAXAEAUSESSION_GLOBALS@Base@Gre@@W4ReferenceTrackerCountedType@@PEAX@Z; TrackObjectReferenceIncrement(Gre::Base::SESSION_GLOBALS &,ReferenceTrackerCountedType,void *)
0x14001bb15  jmp     short loc_14001BAA3
0x14001bb17  test    ecx, ecx
0x14001bb19  jz      loc_14001BA08
0x14001bb1f  cmp     [rsp+98h+var_60], r13
0x14001bb24  jnz     loc_14001BC48
0x14001bb2a  test    r12b, 8
0x14001bb2e  jnz     loc_14001BC86
0x14001bb34  lea     rcx, [rsp+98h+var_58]; this
0x14001bb39  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x14001bb3e  mov     ebp, [rsp+98h+var_50]
0x14001bb42  mov     rbx, [rsp+98h+var_58]
0x14001bb47  jmp     loc_14001BA2C
0x14001bb4c  test    r12b, 8
0x14001bb50  jnz     loc_14001BC62
0x14001bb56  xor     ebp, ebp
0x14001bb58  call    cs:__imp_KeLeaveCriticalRegion
0x14001bb5f  nop     dword ptr [rax+rax+00h]
0x14001bb64  jmp     loc_14001BA2C
0x14001bb69  mov     ecx, eax
0x14001bb6b  shl     ecx, 8
0x14001bb6e  or      ecx, edx
0x14001bb70  xor     ecx, esi
0x14001bb72  test    ecx, 0FFFFFF7Fh
0x14001bb78  jmp     loc_14001BA60
0x14001bb7d  test    rdi, rdi
0x14001bb80  jz      short loc_14001BBA4
0x14001bb82  mov     rcx, [rdi+148h]; this
0x14001bb89  test    rcx, rcx
0x14001bb8c  jz      short loc_14001BBA4
0x14001bb8e  cmp     [rcx+50h], r13b
0x14001bb92  jz      short loc_14001BBA4
0x14001bb94  mov     edx, r14d; unsigned int
0x14001bb97  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x14001bb9c  test    al, al
0x14001bb9e  jnz     loc_14001BA2C
0x14001bba4  mov     byte ptr [rsp+98h+var_4C], bpl
0x14001bba9  test    r12b, 8
0x14001bbad  jz      short loc_14001BB34
0x14001bbaf  mov     r8d, 6
0x14001bbb5  mov     [rsp+98h+var_70], r13d
0x14001bbba  xor     r9d, r9d
0x14001bbbd  mov     edx, 38h ; '8'
0x14001bbc2  mov     [rsp+98h+var_78], r13
0x14001bbc7  mov     ecx, 190h
0x14001bbcc  call    ?GrepCaptureLiveMemoryDump@@YAXK_K000W4GrepCaptureLiveMemoryDumpOptions@@@Z; GrepCaptureLiveMemoryDump(ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,GrepCaptureLiveMemoryDumpOptions)
0x14001bbd1  jmp     loc_14001BB34
0x14001bbd6  call    cs:__imp_PsGetCurrentProcess
0x14001bbdd  nop     dword ptr [rax+rax+00h]
0x14001bbe2  mov     rcx, rax
0x14001bbe5  call    cs:__imp_PsGetProcessSessionIdEx
0x14001bbec  nop     dword ptr [rax+rax+00h]
0x14001bbf1  mov     ebx, eax
0x14001bbf3  call    cs:__imp_PsGetCurrentThreadProcess
0x14001bbfa  nop     dword ptr [rax+rax+00h]
0x14001bbff  mov     rcx, rax
0x14001bc02  call    cs:__imp_PsGetProcessSessionIdEx
0x14001bc09  nop     dword ptr [rax+rax+00h]
0x14001bc0e  cmp     ebx, eax
0x14001bc10  jz      loc_14001B983
0x14001bc16  mov     rdi, rbp
0x14001bc19  mov     [rsp+98h+var_60], rbp
0x14001bc1e  jmp     loc_14001B9AE
0x14001bc23  mov     r8, [rax+70h]
0x14001bc27  mov     edx, 2
0x14001bc2c  mov     rcx, [rsp+98h+arg_0]
0x14001bc34  call    ?TrackObjectReferenceIncrement@@YAXAEAUSESSION_GLOBALS@Base@Gre@@W4ReferenceTrackerCountedType@@PEAX@Z; TrackObjectReferenceIncrement(Gre::Base::SESSION_GLOBALS &,ReferenceTrackerCountedType,void *)
0x14001bc39  jmp     loc_14001BAA3
0x14001bc3e  mov     rsi, [rsp+98h+var_48]
0x14001bc43  jmp     loc_14001BAA3
0x14001bc48  mov     rcx, rdi
0x14001bc4b  call    UMPDGetThreadClientPID
0x14001bc50  cmp     [rsp+98h+arg_8], eax
0x14001bc57  jz      loc_14001BA08
0x14001bc5d  jmp     loc_14001BB2A
0x14001bc62  mov     [rsp+98h+var_70], r13d
0x14001bc67  xor     r9d, r9d
0x14001bc6a  xor     r8d, r8d
0x14001bc6d  mov     [rsp+98h+var_78], r13
0x14001bc72  mov     edx, 38h ; '8'
0x14001bc77  mov     ecx, 190h
0x14001bc7c  call    ?GrepCaptureLiveMemoryDump@@YAXK_K000W4GrepCaptureLiveMemoryDumpOptions@@@Z; GrepCaptureLiveMemoryDump(ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,GrepCaptureLiveMemoryDumpOptions)
0x14001bc81  jmp     loc_14001BB56
0x14001bc86  mov     r8, rbp
0x14001bc89  jmp     loc_14001BBB5
```
