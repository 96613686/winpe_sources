# HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)

- ea: `0x140024930`
- end: `0x140024cae`
- name: `?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z`
- size: `894`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `35`
- callee_count: `7`
- tags: ``

## callers

- `0x140019704`
- `0x14001f380`
- `0x1400200e0`
- `0x140021d40`
- `0x140022690`
- `0x140023110`
- `0x1400247c0`
- `0x14002ebe8`
- `0x140032924`
- `0x14003a23c`
- `0x14003b3b0`
- `0x14003dac0`
- `0x14003de9c`
- `0x14003e2a0`
- `0x14003f490`
- `0x14003f570`
- `0x14003f914`
- `0x140066150`
- `0x140066990`
- `0x14013a860`
- `0x140143bb0`
- `0x14015e370`
- `0x14016d840`
- `0x14016dbb0`
- `0x1401925f0`
- `0x1401b2468`
- `0x1401bc784`
- `0x1401c1138`
- `0x1401e64b8`
- `0x1401e655c`
- `0x1401e663c`
- `0x1401e6758`
- `0x1401e6828`
- `0x1402dd07c`
- `0x1402dd930`

## callees

- `0x140020910`
- `0x140024930`
- `0x140024f24`
- `0x140026270`
- `0x140043e04`
- `0x1400f0fb8`
- `0x140238240`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140024bf6`
- `ntoskrnl!PsGetCurrentProcess` at `0x140024bf6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024ae7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024b78`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024ae7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024b78`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140024c05`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140024c22`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140024c05`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140024c22`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140024c13`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140024c13`
- `ntoskrnl!KeIsAttachedProcess` at `0x14002498f`
- `ntoskrnl!KeIsAttachedProcess` at `0x14002498f`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x140024980`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x140024980`

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
        GrepCaptureLiveMemoryDump(400, 56, v30);
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
      GrepCaptureLiveMemoryDump(400, 56, 0);
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
0x140024930  mov     [rsp+arg_10], rbx
0x140024935  mov     [rsp+arg_0], rcx
0x14002493a  push    rbp
0x14002493b  push    rsi
0x14002493c  push    rdi
0x14002493d  push    r12
0x14002493f  push    r13
0x140024941  push    r14
0x140024943  push    r15
0x140024945  sub     rsp, 60h
0x140024949  xor     ebp, ebp
0x14002494b  mov     [rsp+98h+var_48], rcx
0x140024950  mov     r14d, edx
0x140024953  movzx   eax, dx
0x140024956  shr     r14d, 8
0x14002495a  lea     rcx, [rsp+98h+var_68]
0x14002495f  and     r14d, 0FF0000h
0x140024966  mov     [rsp+98h+var_4C], bp
0x14002496b  or      r14d, eax
0x14002496e  mov     [rsp+98h+var_68], rbp
0x140024973  mov     r12d, r9d
0x140024976  movzx   r15d, r8b
0x14002497a  mov     rsi, rdx
0x14002497d  mov     r13d, ebp
0x140024980  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x140024987  nop     dword ptr [rax+rax+00h]
0x14002498c  mov     rdi, rax
0x14002498f  call    cs:__imp_KeIsAttachedProcess
0x140024996  nop     dword ptr [rax+rax+00h]
0x14002499b  test    al, al
0x14002499d  jnz     loc_140024BF6
0x1400249a3  test    rdi, rdi
0x1400249a6  jz      loc_140024C36
0x1400249ac  mov     rax, [rdi]
0x1400249af  test    rax, rax
0x1400249b2  jz      loc_140024C36
0x1400249b8  lea     rdi, [rax+8]
0x1400249bc  test    rdi, rdi
0x1400249bf  jz      loc_140024C39
0x1400249c5  mov     rax, [rdi+40h]
0x1400249c9  mov     [rsp+98h+var_60], rax
0x1400249ce  mov     rcx, [rsp+98h+arg_0]
0x1400249d6  mov     ebp, 1
0x1400249db  mov     edx, r14d
0x1400249de  mov     [rsp+98h+var_50], ebp
0x1400249e2  mov     rcx, [rcx+8]
0x1400249e6  mov     rax, [rcx]
0x1400249e9  mov     rax, [rax+28h]
0x1400249ed  call    _guard_dispatch_icall
0x1400249f2  mov     [rsp+98h+var_58], rax
0x1400249f7  mov     rbx, rax
0x1400249fa  test    rax, rax
0x1400249fd  jz      loc_140024B6C
0x140024a03  prefetchw byte ptr [rax+8]
0x140024a07  test    bpl, r12b
0x140024a0a  jnz     short loc_140024A28
0x140024a0c  mov     ecx, [rax+8]
0x140024a0f  mov     eax, dword ptr [rsp+98h+var_68]
0x140024a13  and     ecx, 0FFFFFFFEh
0x140024a16  and     eax, 0FFFFFFFCh
0x140024a19  mov     [rsp+98h+arg_8], ecx
0x140024a20  cmp     ecx, eax
0x140024a22  jnz     loc_140024B37
0x140024a28  mov     rax, [rsp+98h+arg_0]
0x140024a30  mov     edx, [rbx]
0x140024a32  mov     rcx, [rax+8]
0x140024a36  mov     rax, [rcx]
0x140024a39  mov     rax, [rax+60h]
0x140024a3d  call    _guard_dispatch_icall
0x140024a42  test    byte ptr [rax+0Eh], 20h
0x140024a46  jnz     loc_140024B9D
0x140024a4c  test    ebp, ebp
0x140024a4e  jz      loc_140024AF3
0x140024a54  cmp     [rbx+0Eh], r15b
0x140024a58  jnz     loc_140024C5E
0x140024a5e  movzx   eax, byte ptr [rbx+0Dh]
0x140024a62  movzx   edx, byte ptr [rbx+0Ch]
0x140024a66  shr     esi, 10h
0x140024a69  test    r12b, 10h
0x140024a6d  jnz     loc_140024B89
0x140024a73  movzx   ecx, ax
0x140024a76  shl     cx, 8
0x140024a7a  or      cx, dx
0x140024a7d  cmp     cx, si
0x140024a80  mov     rsi, [rsp+98h+var_48]
0x140024a85  setz    al
0x140024a88  test    al, al
0x140024a8a  jz      short loc_140024AC3
0x140024a8c  mov     rcx, [rsi+8]
0x140024a90  mov     edx, [rbx]
0x140024a92  mov     rax, [rcx]
0x140024a95  mov     rax, [rax+60h]
0x140024a99  call    _guard_dispatch_icall
0x140024a9e  mov     r13, rax
0x140024aa1  inc     dword ptr [rax+8]
0x140024aa4  cmp     r15b, 5
0x140024aa8  jnz     short loc_140024B0F
0x140024aaa  mov     r8, [rax+2D8h]
0x140024ab1  mov     edx, 3
0x140024ab6  mov     rcx, [rsp+98h+arg_0]
0x140024abe  call    ?TrackObjectReferenceIncrement@@YAXAEAUSESSION_GLOBALS@Base@Gre@@W4ReferenceTrackerCountedType@@PEAX@Z; TrackObjectReferenceIncrement(Gre::Base::SESSION_GLOBALS &,ReferenceTrackerCountedType,void *)
0x140024ac3  mov     rsi, [rsi+8]
0x140024ac7  mov     edx, [rbx]
0x140024ac9  mov     rcx, rsi
0x140024acc  mov     rdi, [rsi]
0x140024acf  mov     rax, [rdi+60h]
0x140024ad3  call    _guard_dispatch_icall
0x140024ad8  mov     rdx, rax
0x140024adb  mov     rcx, rsi
0x140024ade  mov     rax, [rdi+30h]
0x140024ae2  call    _guard_dispatch_icall
0x140024ae7  call    cs:__imp_KeLeaveCriticalRegion
0x140024aee  nop     dword ptr [rax+rax+00h]
0x140024af3  mov     rbx, [rsp+98h+arg_10]
0x140024afb  mov     rax, r13
0x140024afe  add     rsp, 60h
0x140024b02  pop     r15
0x140024b04  pop     r14
0x140024b06  pop     r13
0x140024b08  pop     r12
0x140024b0a  pop     rdi
0x140024b0b  pop     rsi
0x140024b0c  pop     rbp
0x140024b0d  retn
0x140024b0f  cmp     r15b, 4
0x140024b13  jz      loc_140024C43
0x140024b19  cmp     r15b, 10h
0x140024b1d  jnz     short loc_140024AC3
0x140024b1f  mov     r8, [rax+88h]
0x140024b26  xor     edx, edx
0x140024b28  mov     rcx, [rsp+98h+arg_0]
0x140024b30  call    ?TrackObjectReferenceIncrement@@YAXAEAUSESSION_GLOBALS@Base@Gre@@W4ReferenceTrackerCountedType@@PEAX@Z; TrackObjectReferenceIncrement(Gre::Base::SESSION_GLOBALS &,ReferenceTrackerCountedType,void *)
0x140024b35  jmp     short loc_140024AC3
0x140024b37  test    ecx, ecx
0x140024b39  jz      loc_140024A28
0x140024b3f  cmp     [rsp+98h+var_60], r13
0x140024b44  jnz     loc_140024C68
0x140024b4a  test    r12b, 8
0x140024b4e  jnz     loc_140024CA6
0x140024b54  lea     rcx, [rsp+98h+var_58]; this
0x140024b59  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x140024b5e  mov     ebp, [rsp+98h+var_50]
0x140024b62  mov     rbx, [rsp+98h+var_58]
0x140024b67  jmp     loc_140024A4C
0x140024b6c  test    r12b, 8
0x140024b70  jnz     loc_140024C82
0x140024b76  xor     ebp, ebp
0x140024b78  call    cs:__imp_KeLeaveCriticalRegion
0x140024b7f  nop     dword ptr [rax+rax+00h]
0x140024b84  jmp     loc_140024A4C
0x140024b89  mov     ecx, eax
0x140024b8b  shl     ecx, 8
0x140024b8e  or      ecx, edx
0x140024b90  xor     ecx, esi
0x140024b92  test    ecx, 0FFFFFF7Fh
0x140024b98  jmp     loc_140024A80
0x140024b9d  test    rdi, rdi
0x140024ba0  jz      short loc_140024BC4
0x140024ba2  mov     rcx, [rdi+148h]; this
0x140024ba9  test    rcx, rcx
0x140024bac  jz      short loc_140024BC4
0x140024bae  cmp     [rcx+50h], r13b
0x140024bb2  jz      short loc_140024BC4
0x140024bb4  mov     edx, r14d; unsigned int
0x140024bb7  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x140024bbc  test    al, al
0x140024bbe  jnz     loc_140024A4C
0x140024bc4  mov     byte ptr [rsp+98h+var_4C], bpl
0x140024bc9  test    r12b, 8
0x140024bcd  jz      short loc_140024B54
0x140024bcf  mov     r8d, 6
0x140024bd5  mov     [rsp+98h+var_70], r13d
0x140024bda  xor     r9d, r9d
0x140024bdd  mov     edx, 38h ; '8'
0x140024be2  mov     [rsp+98h+var_78], r13
0x140024be7  mov     ecx, 190h
0x140024bec  call    ?GrepCaptureLiveMemoryDump@@YAXK_K000W4GrepCaptureLiveMemoryDumpOptions@@@Z; GrepCaptureLiveMemoryDump(ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,GrepCaptureLiveMemoryDumpOptions)
0x140024bf1  jmp     loc_140024B54
0x140024bf6  call    cs:__imp_PsGetCurrentProcess
0x140024bfd  nop     dword ptr [rax+rax+00h]
0x140024c02  mov     rcx, rax
0x140024c05  call    cs:__imp_PsGetProcessSessionIdEx
0x140024c0c  nop     dword ptr [rax+rax+00h]
0x140024c11  mov     ebx, eax
0x140024c13  call    cs:__imp_PsGetCurrentThreadProcess
0x140024c1a  nop     dword ptr [rax+rax+00h]
0x140024c1f  mov     rcx, rax
0x140024c22  call    cs:__imp_PsGetProcessSessionIdEx
0x140024c29  nop     dword ptr [rax+rax+00h]
0x140024c2e  cmp     ebx, eax
0x140024c30  jz      loc_1400249A3
0x140024c36  mov     rdi, rbp
0x140024c39  mov     [rsp+98h+var_60], rbp
0x140024c3e  jmp     loc_1400249CE
0x140024c43  mov     r8, [rax+70h]
0x140024c47  mov     edx, 2
0x140024c4c  mov     rcx, [rsp+98h+arg_0]
0x140024c54  call    ?TrackObjectReferenceIncrement@@YAXAEAUSESSION_GLOBALS@Base@Gre@@W4ReferenceTrackerCountedType@@PEAX@Z; TrackObjectReferenceIncrement(Gre::Base::SESSION_GLOBALS &,ReferenceTrackerCountedType,void *)
0x140024c59  jmp     loc_140024AC3
0x140024c5e  mov     rsi, [rsp+98h+var_48]
0x140024c63  jmp     loc_140024AC3
0x140024c68  mov     rcx, rdi
0x140024c6b  call    UMPDGetThreadClientPID
0x140024c70  cmp     [rsp+98h+arg_8], eax
0x140024c77  jz      loc_140024A28
0x140024c7d  jmp     loc_140024B4A
0x140024c82  mov     [rsp+98h+var_70], r13d
0x140024c87  xor     r9d, r9d
0x140024c8a  xor     r8d, r8d
0x140024c8d  mov     [rsp+98h+var_78], r13
0x140024c92  mov     edx, 38h ; '8'
0x140024c97  mov     ecx, 190h
0x140024c9c  call    ?GrepCaptureLiveMemoryDump@@YAXK_K000W4GrepCaptureLiveMemoryDumpOptions@@@Z; GrepCaptureLiveMemoryDump(ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,GrepCaptureLiveMemoryDumpOptions)
0x140024ca1  jmp     loc_140024B76
0x140024ca6  mov     r8, rbp
0x140024ca9  jmp     loc_140024BD5
```
