# HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)

- ea: `0x140031190`
- end: `0x14003150e`
- name: `?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z`
- size: `894`
- prototype: `__int64 __fastcall(__int64, unsigned int, char, char)`
- caller_count: `35`
- callee_count: `7`
- tags: ``

## callers

- `0x14000f9b0`
- `0x140026644`
- `0x14002bbe0`
- `0x14002c940`
- `0x14002e5a0`
- `0x14002eef0`
- `0x14002f970`
- `0x140031020`
- `0x140039f10`
- `0x14003bb50`
- `0x14003c120`
- `0x14003da30`
- `0x14003ea80`
- `0x14003eb30`
- `0x14003ec5c`
- `0x14006f724`
- `0x1400dcd50`
- `0x1400efe00`
- `0x140101740`
- `0x1401028b0`
- `0x14013ca10`
- `0x140145720`
- `0x140160980`
- `0x14016f8e0`
- `0x1401955d0`
- `0x1401b3678`
- `0x1401bd8b4`
- `0x1401c2268`
- `0x1401e6d18`
- `0x1401e6dbc`
- `0x1401e6e9c`
- `0x1401e6fb8`
- `0x1401e7088`
- `0x1402dd13c`
- `0x1402dd9f0`

## callees

- `0x14001e034`
- `0x14002d170`
- `0x140031190`
- `0x140031784`
- `0x140079330`
- `0x14012e228`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140031456`
- `ntoskrnl!PsGetCurrentProcess` at `0x140031456`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140031347`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400313d8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140031347`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400313d8`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140031465`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140031482`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140031465`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140031482`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140031473`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140031473`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400311ef`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400311ef`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x1400311e0`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x1400311e0`

## pseudocode

```c
__int64 __fastcall HmgShareLock(__int64 a1, unsigned int a2, char a3, char a4)
{
  unsigned int v4; // r14d
  __int64 v8; // r13
  __int64 *CurrentThreadWin32ThreadAndEnterCriticalRegion; // rdi
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdi
  int v13; // ebp
  __int64 v14; // rax
  unsigned __int8 *v15; // rbx
  unsigned int v16; // ecx
  int v17; // eax
  int v18; // edx
  unsigned int v19; // esi
  bool v20; // zf
  __int64 v21; // rsi
  __int64 v22; // rax
  __int64 *v23; // rsi
  __int64 v24; // rdi
  __int64 v25; // rax
  ThreadRestrictNewHandlesRegion *v27; // rcx
  __int64 v28; // r8
  __int64 CurrentProcess; // rax
  int ProcessSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  __int64 v32; // [rsp+30h] [rbp-68h] BYREF
  __int64 v33; // [rsp+38h] [rbp-60h]
  unsigned __int8 *v34; // [rsp+40h] [rbp-58h] BYREF
  int v35; // [rsp+48h] [rbp-50h]
  __int16 v36; // [rsp+4Ch] [rbp-4Ch]
  __int64 v37; // [rsp+50h] [rbp-48h]

  v37 = a1;
  v36 = 0;
  v4 = (unsigned __int16)a2 | (a2 >> 8) & 0xFF0000;
  v32 = 0;
  v8 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v32);
  if ( (!(unsigned __int8)KeIsAttachedProcess()
     || (CurrentProcess = PsGetCurrentProcess(v10),
         ProcessSessionId = PsGetProcessSessionIdEx(CurrentProcess),
         CurrentThreadProcess = PsGetCurrentThreadProcess(),
         ProcessSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)))
    && CurrentThreadWin32ThreadAndEnterCriticalRegion
    && (v11 = *CurrentThreadWin32ThreadAndEnterCriticalRegion) != 0 )
  {
    v12 = v11 + 8;
    if ( v11 != -8 )
    {
      v33 = *(_QWORD *)(v11 + 72);
      goto LABEL_6;
    }
  }
  else
  {
    v12 = 0;
  }
  v33 = 0;
LABEL_6:
  v13 = 1;
  v35 = 1;
  v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 8) + 40LL))(*(_QWORD *)(a1 + 8), v4);
  v34 = (unsigned __int8 *)v14;
  v15 = (unsigned __int8 *)v14;
  if ( v14 )
  {
    _m_prefetchw((const void *)(v14 + 8));
    if ( (a4 & 1) == 0 )
    {
      v16 = *(_DWORD *)(v14 + 8) & 0xFFFFFFFE;
      if ( v16 != (v32 & 0xFFFFFFFC) && v16 && (!v33 || v16 != (unsigned int)UMPDGetThreadClientPID(v12)) )
      {
        if ( (a4 & 8) == 0 )
        {
LABEL_25:
          HANDLELOCK::vUnlock((HANDLELOCK *)&v34);
          v13 = v35;
          v15 = v34;
          goto LABEL_10;
        }
        v28 = 1;
LABEL_36:
        GrepCaptureLiveMemoryDump(400, 56, v28, 0, 0, 0);
        goto LABEL_25;
      }
    }
    if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 8) + 96LL))(
                       *(_QWORD *)(a1 + 8),
                       *(unsigned int *)v15)
                   + 14)
        & 0x20) != 0
      && (!v12
       || (v27 = *(ThreadRestrictNewHandlesRegion **)(v12 + 328)) == 0
       || !*((_BYTE *)v27 + 80)
       || !ThreadRestrictNewHandlesRegion::InRegion(v27, v4)) )
    {
      LOBYTE(v36) = 1;
      if ( (a4 & 8) == 0 )
        goto LABEL_25;
      v28 = 6;
      goto LABEL_36;
    }
  }
  else
  {
    if ( (a4 & 8) != 0 )
      GrepCaptureLiveMemoryDump(400, 56, 0, 0, 0, 0);
    v13 = 0;
    KeLeaveCriticalRegion();
  }
LABEL_10:
  if ( v13 )
  {
    if ( v15[14] == a3 )
    {
      v17 = v15[13];
      v18 = v15[12];
      v19 = HIWORD(a2);
      if ( (a4 & 0x10) != 0 )
        v20 = ((v19 ^ (v18 | (v17 << 8))) & 0xFFFFFF7F) == 0;
      else
        v20 = ((unsigned __int16)v18 | (unsigned __int16)((_WORD)v17 << 8)) == (_WORD)v19;
      v21 = v37;
      if ( v20 )
      {
        v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v37 + 8) + 96LL))(
                *(_QWORD *)(v37 + 8),
                *(unsigned int *)v15);
        v8 = v22;
        ++*(_DWORD *)(v22 + 8);
        switch ( a3 )
        {
          case 5:
            TrackObjectReferenceIncrement(a1, 3, *(_QWORD *)(v22 + 712));
            break;
          case 4:
            TrackObjectReferenceIncrement(a1, 2, *(_QWORD *)(v22 + 112));
            break;
          case 16:
            TrackObjectReferenceIncrement(a1, 0, *(_QWORD *)(v22 + 136));
            break;
        }
      }
    }
    else
    {
      v21 = v37;
    }
    v23 = *(__int64 **)(v21 + 8);
    v24 = *v23;
    v25 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v23 + 96))(v23, *(unsigned int *)v15);
    (*(void (__fastcall **)(__int64 *, __int64))(v24 + 48))(v23, v25);
    KeLeaveCriticalRegion();
  }
  return v8;
}

```

## disassembly

```asm
0x140031190  mov     [rsp+arg_10], rbx
0x140031195  mov     [rsp+arg_0], rcx
0x14003119a  push    rbp
0x14003119b  push    rsi
0x14003119c  push    rdi
0x14003119d  push    r12
0x14003119f  push    r13
0x1400311a1  push    r14
0x1400311a3  push    r15
0x1400311a5  sub     rsp, 60h
0x1400311a9  xor     ebp, ebp
0x1400311ab  mov     [rsp+98h+var_48], rcx
0x1400311b0  mov     r14d, edx
0x1400311b3  movzx   eax, dx
0x1400311b6  shr     r14d, 8
0x1400311ba  lea     rcx, [rsp+98h+var_68]
0x1400311bf  and     r14d, 0FF0000h
0x1400311c6  mov     [rsp+98h+var_4C], bp
0x1400311cb  or      r14d, eax
0x1400311ce  mov     [rsp+98h+var_68], rbp
0x1400311d3  mov     r12d, r9d
0x1400311d6  movzx   r15d, r8b
0x1400311da  mov     rsi, rdx
0x1400311dd  mov     r13d, ebp
0x1400311e0  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x1400311e7  nop     dword ptr [rax+rax+00h]
0x1400311ec  mov     rdi, rax
0x1400311ef  call    cs:__imp_KeIsAttachedProcess
0x1400311f6  nop     dword ptr [rax+rax+00h]
0x1400311fb  test    al, al
0x1400311fd  jnz     loc_140031456
0x140031203  test    rdi, rdi
0x140031206  jz      loc_140031496
0x14003120c  mov     rax, [rdi]
0x14003120f  test    rax, rax
0x140031212  jz      loc_140031496
0x140031218  lea     rdi, [rax+8]
0x14003121c  test    rdi, rdi
0x14003121f  jz      loc_140031499
0x140031225  mov     rax, [rdi+40h]
0x140031229  mov     [rsp+98h+var_60], rax
0x14003122e  mov     rcx, [rsp+98h+arg_0]
0x140031236  mov     ebp, 1
0x14003123b  mov     edx, r14d
0x14003123e  mov     [rsp+98h+var_50], ebp
0x140031242  mov     rcx, [rcx+8]
0x140031246  mov     rax, [rcx]
0x140031249  mov     rax, [rax+28h]
0x14003124d  call    _guard_dispatch_icall
0x140031252  mov     [rsp+98h+var_58], rax
0x140031257  mov     rbx, rax
0x14003125a  test    rax, rax
0x14003125d  jz      loc_1400313CC
0x140031263  prefetchw byte ptr [rax+8]
0x140031267  test    bpl, r12b
0x14003126a  jnz     short loc_140031288
0x14003126c  mov     ecx, [rax+8]
0x14003126f  mov     eax, dword ptr [rsp+98h+var_68]
0x140031273  and     ecx, 0FFFFFFFEh
0x140031276  and     eax, 0FFFFFFFCh
0x140031279  mov     [rsp+98h+arg_8], ecx
0x140031280  cmp     ecx, eax
0x140031282  jnz     loc_140031397
0x140031288  mov     rax, [rsp+98h+arg_0]
0x140031290  mov     edx, [rbx]
0x140031292  mov     rcx, [rax+8]
0x140031296  mov     rax, [rcx]
0x140031299  mov     rax, [rax+60h]
0x14003129d  call    _guard_dispatch_icall
0x1400312a2  test    byte ptr [rax+0Eh], 20h
0x1400312a6  jnz     loc_1400313FD
0x1400312ac  test    ebp, ebp
0x1400312ae  jz      loc_140031353
0x1400312b4  cmp     [rbx+0Eh], r15b
0x1400312b8  jnz     loc_1400314BE
0x1400312be  movzx   eax, byte ptr [rbx+0Dh]
0x1400312c2  movzx   edx, byte ptr [rbx+0Ch]
0x1400312c6  shr     esi, 10h
0x1400312c9  test    r12b, 10h
0x1400312cd  jnz     loc_1400313E9
0x1400312d3  movzx   ecx, ax
0x1400312d6  shl     cx, 8
0x1400312da  or      cx, dx
0x1400312dd  cmp     cx, si
0x1400312e0  mov     rsi, [rsp+98h+var_48]
0x1400312e5  setz    al
0x1400312e8  test    al, al
0x1400312ea  jz      short loc_140031323
0x1400312ec  mov     rcx, [rsi+8]
0x1400312f0  mov     edx, [rbx]
0x1400312f2  mov     rax, [rcx]
0x1400312f5  mov     rax, [rax+60h]
0x1400312f9  call    _guard_dispatch_icall
0x1400312fe  mov     r13, rax
0x140031301  inc     dword ptr [rax+8]
0x140031304  cmp     r15b, 5
0x140031308  jnz     short loc_14003136F
0x14003130a  mov     r8, [rax+2C8h]
0x140031311  mov     edx, 3
0x140031316  mov     rcx, [rsp+98h+arg_0]
0x14003131e  call    ?TrackObjectReferenceIncrement@@YAXAEAUSESSION_GLOBALS@Base@Gre@@W4ReferenceTrackerCountedType@@PEAX@Z; TrackObjectReferenceIncrement(Gre::Base::SESSION_GLOBALS &,ReferenceTrackerCountedType,void *)
0x140031323  mov     rsi, [rsi+8]
0x140031327  mov     edx, [rbx]
0x140031329  mov     rcx, rsi
0x14003132c  mov     rdi, [rsi]
0x14003132f  mov     rax, [rdi+60h]
0x140031333  call    _guard_dispatch_icall
0x140031338  mov     rdx, rax
0x14003133b  mov     rcx, rsi
0x14003133e  mov     rax, [rdi+30h]
0x140031342  call    _guard_dispatch_icall
0x140031347  call    cs:__imp_KeLeaveCriticalRegion
0x14003134e  nop     dword ptr [rax+rax+00h]
0x140031353  mov     rbx, [rsp+98h+arg_10]
0x14003135b  mov     rax, r13
0x14003135e  add     rsp, 60h
0x140031362  pop     r15
0x140031364  pop     r14
0x140031366  pop     r13
0x140031368  pop     r12
0x14003136a  pop     rdi
0x14003136b  pop     rsi
0x14003136c  pop     rbp
0x14003136d  retn
0x14003136f  cmp     r15b, 4
0x140031373  jz      loc_1400314A3
0x140031379  cmp     r15b, 10h
0x14003137d  jnz     short loc_140031323
0x14003137f  mov     r8, [rax+88h]
0x140031386  xor     edx, edx
0x140031388  mov     rcx, [rsp+98h+arg_0]
0x140031390  call    ?TrackObjectReferenceIncrement@@YAXAEAUSESSION_GLOBALS@Base@Gre@@W4ReferenceTrackerCountedType@@PEAX@Z; TrackObjectReferenceIncrement(Gre::Base::SESSION_GLOBALS &,ReferenceTrackerCountedType,void *)
0x140031395  jmp     short loc_140031323
0x140031397  test    ecx, ecx
0x140031399  jz      loc_140031288
0x14003139f  cmp     [rsp+98h+var_60], r13
0x1400313a4  jnz     loc_1400314C8
0x1400313aa  test    r12b, 8
0x1400313ae  jnz     loc_140031506
0x1400313b4  lea     rcx, [rsp+98h+var_58]; this
0x1400313b9  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x1400313be  mov     ebp, [rsp+98h+var_50]
0x1400313c2  mov     rbx, [rsp+98h+var_58]
0x1400313c7  jmp     loc_1400312AC
0x1400313cc  test    r12b, 8
0x1400313d0  jnz     loc_1400314E2
0x1400313d6  xor     ebp, ebp
0x1400313d8  call    cs:__imp_KeLeaveCriticalRegion
0x1400313df  nop     dword ptr [rax+rax+00h]
0x1400313e4  jmp     loc_1400312AC
0x1400313e9  mov     ecx, eax
0x1400313eb  shl     ecx, 8
0x1400313ee  or      ecx, edx
0x1400313f0  xor     ecx, esi
0x1400313f2  test    ecx, 0FFFFFF7Fh
0x1400313f8  jmp     loc_1400312E0
0x1400313fd  test    rdi, rdi
0x140031400  jz      short loc_140031424
0x140031402  mov     rcx, [rdi+148h]; this
0x140031409  test    rcx, rcx
0x14003140c  jz      short loc_140031424
0x14003140e  cmp     [rcx+50h], r13b
0x140031412  jz      short loc_140031424
0x140031414  mov     edx, r14d; unsigned int
0x140031417  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x14003141c  test    al, al
0x14003141e  jnz     loc_1400312AC
0x140031424  mov     byte ptr [rsp+98h+var_4C], bpl
0x140031429  test    r12b, 8
0x14003142d  jz      short loc_1400313B4
0x14003142f  mov     r8d, 6
0x140031435  mov     [rsp+98h+var_70], r13d
0x14003143a  xor     r9d, r9d
0x14003143d  mov     edx, 38h ; '8'
0x140031442  mov     [rsp+98h+var_78], r13
0x140031447  mov     ecx, 190h
0x14003144c  call    ?GrepCaptureLiveMemoryDump@@YAXK_K000W4GrepCaptureLiveMemoryDumpOptions@@@Z; GrepCaptureLiveMemoryDump(ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,GrepCaptureLiveMemoryDumpOptions)
0x140031451  jmp     loc_1400313B4
0x140031456  call    cs:__imp_PsGetCurrentProcess
0x14003145d  nop     dword ptr [rax+rax+00h]
0x140031462  mov     rcx, rax
0x140031465  call    cs:__imp_PsGetProcessSessionIdEx
0x14003146c  nop     dword ptr [rax+rax+00h]
0x140031471  mov     ebx, eax
0x140031473  call    cs:__imp_PsGetCurrentThreadProcess
0x14003147a  nop     dword ptr [rax+rax+00h]
0x14003147f  mov     rcx, rax
0x140031482  call    cs:__imp_PsGetProcessSessionIdEx
0x140031489  nop     dword ptr [rax+rax+00h]
0x14003148e  cmp     ebx, eax
0x140031490  jz      loc_140031203
0x140031496  mov     rdi, rbp
0x140031499  mov     [rsp+98h+var_60], rbp
0x14003149e  jmp     loc_14003122E
0x1400314a3  mov     r8, [rax+70h]
0x1400314a7  mov     edx, 2
0x1400314ac  mov     rcx, [rsp+98h+arg_0]
0x1400314b4  call    ?TrackObjectReferenceIncrement@@YAXAEAUSESSION_GLOBALS@Base@Gre@@W4ReferenceTrackerCountedType@@PEAX@Z; TrackObjectReferenceIncrement(Gre::Base::SESSION_GLOBALS &,ReferenceTrackerCountedType,void *)
0x1400314b9  jmp     loc_140031323
0x1400314be  mov     rsi, [rsp+98h+var_48]
0x1400314c3  jmp     loc_140031323
0x1400314c8  mov     rcx, rdi
0x1400314cb  call    UMPDGetThreadClientPID
0x1400314d0  cmp     [rsp+98h+arg_8], eax
0x1400314d7  jz      loc_140031288
0x1400314dd  jmp     loc_1400313AA
0x1400314e2  mov     [rsp+98h+var_70], r13d
0x1400314e7  xor     r9d, r9d
0x1400314ea  xor     r8d, r8d
0x1400314ed  mov     [rsp+98h+var_78], r13
0x1400314f2  mov     edx, 38h ; '8'
0x1400314f7  mov     ecx, 190h
0x1400314fc  call    ?GrepCaptureLiveMemoryDump@@YAXK_K000W4GrepCaptureLiveMemoryDumpOptions@@@Z; GrepCaptureLiveMemoryDump(ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,GrepCaptureLiveMemoryDumpOptions)
0x140031501  jmp     loc_1400313D6
0x140031506  mov     r8, rbp
0x140031509  jmp     loc_140031435
```
