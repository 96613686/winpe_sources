# NtUserMsgWaitForMultipleObjectsEx

- ea: `0x1400e8320`
- end: `0x1400e88b3`
- name: `NtUserMsgWaitForMultipleObjectsEx`
- size: `1427`
- prototype: `__int64 __fastcall(unsigned int, volatile void *, int, int, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400b6698`
- `0x1400e8320`
- `0x1400e88c0`
- `0x1400e8c20`
- `0x1400e8c74`
- `0x1400e8cd0`
- `0x1400e8fb0`
- `0x140258a50`
- `0x1402a7178`
- `0x140343200`
- `0x140343500`

## import_xrefs

- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x1400e87f5`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x1400e87f5`
- `ntoskrnl!ZwCancelWaitCompletionPacket` at `0x1400e83fb`
- `ntoskrnl!ZwCancelWaitCompletionPacket` at `0x1400e8417`
- `ntoskrnl!ZwCancelWaitCompletionPacket` at `0x1400e83fb`
- `ntoskrnl!ZwCancelWaitCompletionPacket` at `0x1400e8417`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400e8646`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400e8646`
- `ntoskrnl!KeSetEvent` at `0x1400e8432`
- `ntoskrnl!KeSetEvent` at `0x1400e8432`
- `ntoskrnl!ProbeForRead` at `0x1400e866e`
- `ntoskrnl!ProbeForRead` at `0x1400e866e`
- `ntoskrnl!PsGetProcessPeb` at `0x1400e844e`
- `ntoskrnl!PsGetProcessPeb` at `0x1400e844e`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400e843f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400e843f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e835c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e83da`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e8720`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e87a2`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e8835`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e835c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e83da`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e8720`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e87a2`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e8835`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1400e85c1`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1400e85c1`
- `win32kbase!EnterCrit` at `0x1400e8350`
- `win32kbase!EnterCrit` at `0x1400e8350`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400e86b8`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400e86b8`
- `win32kbase!Win32FreePool` at `0x1400e8699`
- `win32kbase!Win32FreePool` at `0x1400e8699`
- `win32kbase!Win32FreePool` at `0x1400e86f1`

## pseudocode

```c
__int64 __fastcall NtUserMsgWaitForMultipleObjectsEx(unsigned int a1, volatile void *a2, int a3, int a4, int a5)
{
  unsigned __int16 v5; // bx
  __int64 v7; // rsi
  _QWORD *CurrentThreadWin32Thread; // rax
  __int64 v9; // rax
  unsigned int v10; // edi
  __int64 v11; // r12
  __int64 *v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rdx
  __int64 CurrentProcess; // rax
  void *v16; // rbx
  _OWORD *v17; // rcx
  _OWORD *v18; // rax
  __int64 v19; // rdx
  _OWORD *v20; // rdx
  _OWORD *v21; // rax
  __int64 v22; // rcx
  _QWORD *v23; // rax
  _QWORD *v24; // rbx
  int *v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // r10
  int v30; // eax
  __int64 CurrentProcessWow64Process; // rax
  ULONG v32; // r8d
  __int64 *v34; // rax
  __int64 v35; // rbx
  _QWORD *v36; // rax
  _QWORD *v37; // rcx
  int v38; // ecx
  __int64 *v39; // rax
  __int64 *v40; // rax
  __int64 v41; // rcx
  __int64 v42; // [rsp+40h] [rbp-928h] BYREF
  __int64 v43; // [rsp+48h] [rbp-920h]
  int v44; // [rsp+50h] [rbp-918h]
  int v45; // [rsp+54h] [rbp-914h]
  int v46; // [rsp+58h] [rbp-910h]
  void *v47; // [rsp+60h] [rbp-908h]
  __int64 ProcessPeb; // [rsp+68h] [rbp-900h]
  __int64 InputEvent; // [rsp+70h] [rbp-8F8h]
  _BYTE v50[24]; // [rsp+78h] [rbp-8F0h] BYREF
  _BYTE v51[32]; // [rsp+90h] [rbp-8D8h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-8B8h]
  __int64 v53; // [rsp+B8h] [rbp-8B0h]
  __int64 v54; // [rsp+C0h] [rbp-8A8h]
  _BYTE v55[1160]; // [rsp+4E0h] [rbp-488h] BYREF

  v5 = a4;
  HIDWORD(v43) = a4;
  v44 = a3;
  v7 = a1;
  EnterCrit(0, 0);
  CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread();
  if ( CurrentThreadWin32Thread )
    CurrentThreadWin32Thread = (_QWORD *)*CurrentThreadWin32Thread;
  if ( (a5 & 0xFFFFFFE0) != 0 || (unsigned int)v7 > 0x3F )
  {
    v10 = -1;
    UserSetLastError(87);
    goto LABEL_32;
  }
  v9 = CurrentThreadWin32Thread[60];
  if ( v9 && ((a5 & 1) == 0 || !(_DWORD)v7) )
  {
    v38 = *(_DWORD *)(v9 + 4);
    if ( (a5 & 4) != 0 )
    {
      LODWORD(v42) = *(_DWORD *)(v9 + 8);
      v39 = &v42;
    }
    else
    {
      HIDWORD(v42) = 0;
      v39 = (__int64 *)((char *)&v42 + 4);
    }
    if ( ((unsigned __int16)(v38 | *(_DWORD *)v39) & v5) != 0 )
    {
      v10 = v7;
      goto LABEL_32;
    }
  }
  v10 = -1;
  InputEvent = xxxGetInputEvent(v5 | ((unsigned __int16)a5 << 16));
  if ( InputEvent )
  {
    v45 = -1;
    v47 = 0;
    if ( (a5 & 1) != 0 )
    {
      v11 = 0;
      v12 = (__int64 *)PsGetCurrentThreadWin32Thread();
      if ( v12 )
        v13 = *v12;
      else
        v13 = 0;
      if ( (unsigned int)ZwCancelWaitCompletionPacket(*(_QWORD *)(v13 + 1640), 0) == 259 )
      {
        LOBYTE(v14) = 1;
        ZwCancelWaitCompletionPacket(*(_QWORD *)(v13 + 1640), v14);
        KeSetEvent(*(PRKEVENT *)(v13 + 760), 1, 0);
      }
    }
    else
    {
      v40 = (__int64 *)PsGetCurrentThreadWin32Thread();
      if ( v40 )
        v41 = *v40;
      else
        v41 = 0;
      v11 = *(_QWORD *)(v41 + 1624);
      if ( !v11 )
        goto LABEL_32;
    }
    CurrentProcess = PsGetCurrentProcess();
    ProcessPeb = PsGetProcessPeb(CurrentProcess);
    v16 = *(void **)(ProcessPeb + 32);
    memset_0(v51, 0, 0x448u);
    RtlCopyFromUser(v51, v16, 0x448u);
    v17 = v55;
    v18 = v51;
    v19 = 8;
    do
    {
      *v17 = *v18;
      v17[1] = v18[1];
      v17[2] = v18[2];
      v17[3] = v18[3];
      v17[4] = v18[4];
      v17[5] = v18[5];
      v17[6] = v18[6];
      v17[7] = v18[7];
      v17 += 8;
      v18 += 8;
      --v19;
    }
    while ( v19 );
    *v17 = *v18;
    v17[1] = v18[1];
    v17[2] = v18[2];
    v17[3] = v18[3];
    *((_QWORD *)v17 + 8) = *((_QWORD *)v18 + 8);
    v20 = v51;
    v21 = v55;
    v22 = 8;
    do
    {
      *v20 = *v21;
      v20[1] = v21[1];
      v20[2] = v21[2];
      v20[3] = v21[3];
      v20[4] = v21[4];
      v20[5] = v21[5];
      v20[6] = v21[6];
      v20[7] = v21[7];
      v20 += 8;
      v21 += 8;
      --v22;
    }
    while ( v22 );
    *v20 = *v21;
    v20[1] = v21[1];
    v20[2] = v21[2];
    v20[3] = v21[3];
    *((_QWORD *)v20 + 8) = *((_QWORD *)v21 + 8);
    if ( (_DWORD)v7 )
    {
      CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
      v32 = 1;
      if ( !CurrentProcessWow64Process )
        v32 = 4;
      ProbeForRead(a2, 8 * v7, v32);
    }
    v23 = (_QWORD *)Win32AllocPoolWithQuotaZInit(8LL * (unsigned int)(v7 + 1), 2037609301);
    v24 = v23;
    v47 = v23;
    if ( v23 )
    {
      memmove(v23, (const void *)a2, 8 * v7);
      v26 = 0;
      LODWORD(v43) = 0;
      v27 = v54;
      v28 = v53;
      v29 = v52;
      while ( (unsigned int)v26 < (unsigned int)v7 )
      {
        v25 = (int *)&v24[v26];
        v30 = *v25;
        if ( *v25 == -11 )
        {
          *(_QWORD *)v25 = v28;
        }
        else if ( v30 == -12 )
        {
          *(_QWORD *)v25 = v27;
        }
        else if ( v30 == -10 )
        {
          *(_QWORD *)v25 = v29;
        }
        v26 = (unsigned int)(v26 + 1);
        LODWORD(v43) = v26;
      }
      if ( (a5 & 8) != 0 )
        SetWaitForQueueAttach(1, v25, v27, v28);
      if ( (a5 & 1) != 0 )
        v11 = InputEvent;
      v24[v7] = v11;
      Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(
        v50,
        v24,
        Win32FreePool,
        v28);
      v10 = xxxMsgWaitForMultipleObjectsEx(v7, (_DWORD)v24, v44, HIDWORD(v43), a5);
      v34 = (__int64 *)PsGetCurrentThreadWin32Thread();
      if ( v34 )
        v35 = *v34;
      else
        v35 = 0;
      _InterlockedExchange(
        (volatile __int32 *)(*(_QWORD *)(v35 + 480) + 20LL),
        (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24);
      if ( !*(_DWORD *)(v35 + 1304) )
        xxxUpdateInputHangInfo(0, 1);
      _InterlockedExchange((volatile __int32 *)(*(_QWORD *)(v35 + 480) + 16LL), 0);
      *(_QWORD *)(v35 + 1360) &= ~0x400uLL;
      Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>::~Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>(v50);
      if ( (a5 & 1) != 0 )
      {
        v36 = (_QWORD *)PsGetCurrentThreadWin32Thread();
        if ( v36 )
          v37 = (_QWORD *)*v36;
        else
          v37 = 0;
        ZwAssociateWaitCompletionPacket(v37[205], v37[202], v37[204], 0, 0xFFFFFFFF80000000uLL, 0, 0, 0, v42, v43);
      }
    }
    else
    {
      v46 = -1;
      UserSetLastError(8);
    }
  }
LABEL_32:
  UserSessionSwitchLeaveCrit();
  return v10;
}

```

## disassembly

```asm
0x1400e8320  push    rbx
0x1400e8322  push    rsi
0x1400e8323  push    rdi
0x1400e8324  push    r12
0x1400e8326  push    r13
0x1400e8328  push    r14
0x1400e832a  push    r15
0x1400e832c  sub     rsp, 930h
0x1400e8333  mov     ebx, r9d
0x1400e8336  mov     [rsp+968h+var_91C], ebx
0x1400e833a  mov     [rsp+968h+var_918], r8d
0x1400e833f  mov     r13, rdx
0x1400e8342  mov     esi, ecx
0x1400e8344  mov     r15d, [rsp+968h+arg_20]
0x1400e834c  xor     edx, edx
0x1400e834e  xor     ecx, ecx
0x1400e8350  call    cs:__imp_EnterCrit
0x1400e8357  nop     dword ptr [rax+rax+00h]
0x1400e835c  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400e8363  nop     dword ptr [rax+rax+00h]
0x1400e8368  test    rax, rax
0x1400e836b  jz      short loc_1400E8370
0x1400e836d  mov     rax, [rax]
0x1400e8370  test    r15d, 0FFFFFFE0h
0x1400e8377  jnz     loc_1400E8877
0x1400e837d  cmp     esi, 3Fh ; '?'
0x1400e8380  ja      loc_1400E8877
0x1400e8386  mov     r14d, r15d
0x1400e8389  and     r14d, 1
0x1400e838d  mov     rax, [rax+1E0h]
0x1400e8394  test    rax, rax
0x1400e8397  jnz     loc_1400E8806
0x1400e839d  mov     edi, 0FFFFFFFFh
0x1400e83a2  movzx   ecx, r15w
0x1400e83a6  shl     ecx, 10h
0x1400e83a9  movzx   eax, bx
0x1400e83ac  or      ecx, eax
0x1400e83ae  call    xxxGetInputEvent
0x1400e83b3  mov     [rsp+968h+var_8F8], rax
0x1400e83b8  test    rax, rax
0x1400e83bb  jz      loc_1400E86B8
0x1400e83c1  mov     [rsp+968h+var_914], edi
0x1400e83c5  mov     [rsp+968h+var_908], 0
0x1400e83ce  test    r14d, r14d
0x1400e83d1  jz      loc_1400E8835
0x1400e83d7  xor     r12d, r12d
0x1400e83da  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400e83e1  nop     dword ptr [rax+rax+00h]
0x1400e83e6  test    rax, rax
0x1400e83e9  jz      loc_1400E888B
0x1400e83ef  mov     rbx, [rax]
0x1400e83f2  xor     edx, edx
0x1400e83f4  mov     rcx, [rbx+668h]
0x1400e83fb  call    cs:__imp_ZwCancelWaitCompletionPacket
0x1400e8402  nop     dword ptr [rax+rax+00h]
0x1400e8407  cmp     eax, 103h
0x1400e840c  jnz     short loc_1400E843F
0x1400e840e  mov     dl, 1
0x1400e8410  mov     rcx, [rbx+668h]
0x1400e8417  call    cs:__imp_ZwCancelWaitCompletionPacket
0x1400e841e  nop     dword ptr [rax+rax+00h]
0x1400e8423  xor     r8d, r8d; Wait
0x1400e8426  mov     edx, 1; Increment
0x1400e842b  mov     rcx, [rbx+2F8h]; Event
0x1400e8432  call    cs:__imp_KeSetEvent
0x1400e8439  nop     dword ptr [rax+rax+00h]
0x1400e843e  nop
0x1400e843f  call    cs:__imp_PsGetCurrentProcess
0x1400e8446  nop     dword ptr [rax+rax+00h]
0x1400e844b  mov     rcx, rax
0x1400e844e  call    cs:__imp_PsGetProcessPeb
0x1400e8455  nop     dword ptr [rax+rax+00h]
0x1400e845a  mov     [rsp+968h+var_900], rax
0x1400e845f  mov     rax, [rsp+968h+var_900]
0x1400e8464  mov     rbx, [rax+20h]
0x1400e8468  xor     edx, edx; Val
0x1400e846a  mov     r8d, 448h; Size
0x1400e8470  lea     rcx, [rsp+968h+var_8D8]; void *
0x1400e8478  call    memset_0
0x1400e847d  mov     r8d, 448h; Size
0x1400e8483  mov     rdx, rbx; Src
0x1400e8486  lea     rcx, [rsp+968h+var_8D8]; void *
0x1400e848e  call    RtlCopyFromUser
0x1400e8493  lea     rcx, [rsp+968h+var_488]
0x1400e849b  lea     rax, [rsp+968h+var_8D8]
0x1400e84a3  mov     edx, 8
0x1400e84a8  movups  xmm0, xmmword ptr [rax]
0x1400e84ab  movups  xmmword ptr [rcx], xmm0
0x1400e84ae  movups  xmm1, xmmword ptr [rax+10h]
0x1400e84b2  movups  xmmword ptr [rcx+10h], xmm1
0x1400e84b6  movups  xmm0, xmmword ptr [rax+20h]
0x1400e84ba  movups  xmmword ptr [rcx+20h], xmm0
0x1400e84be  movups  xmm1, xmmword ptr [rax+30h]
0x1400e84c2  movups  xmmword ptr [rcx+30h], xmm1
0x1400e84c6  movups  xmm0, xmmword ptr [rax+40h]
0x1400e84ca  movups  xmmword ptr [rcx+40h], xmm0
0x1400e84ce  movups  xmm1, xmmword ptr [rax+50h]
0x1400e84d2  movups  xmmword ptr [rcx+50h], xmm1
0x1400e84d6  movups  xmm0, xmmword ptr [rax+60h]
0x1400e84da  movups  xmmword ptr [rcx+60h], xmm0
0x1400e84de  movups  xmm1, xmmword ptr [rax+70h]
0x1400e84e2  movups  xmmword ptr [rcx+70h], xmm1
0x1400e84e6  lea     rcx, [rcx+80h]
0x1400e84ed  lea     rax, [rax+80h]
0x1400e84f4  sub     rdx, 1
0x1400e84f8  jnz     short loc_1400E84A8
0x1400e84fa  movups  xmm0, xmmword ptr [rax]
0x1400e84fd  movups  xmmword ptr [rcx], xmm0
0x1400e8500  movups  xmm1, xmmword ptr [rax+10h]
0x1400e8504  movups  xmmword ptr [rcx+10h], xmm1
0x1400e8508  movups  xmm0, xmmword ptr [rax+20h]
0x1400e850c  movups  xmmword ptr [rcx+20h], xmm0
0x1400e8510  movups  xmm1, xmmword ptr [rax+30h]
0x1400e8514  movups  xmmword ptr [rcx+30h], xmm1
0x1400e8518  mov     rax, [rax+40h]
0x1400e851c  mov     [rcx+40h], rax
0x1400e8520  lea     rdx, [rsp+968h+var_8D8]
0x1400e8528  lea     rax, [rsp+968h+var_488]
0x1400e8530  mov     ecx, 8
0x1400e8535  movups  xmm0, xmmword ptr [rax]
0x1400e8538  movups  xmmword ptr [rdx], xmm0
0x1400e853b  movups  xmm1, xmmword ptr [rax+10h]
0x1400e853f  movups  xmmword ptr [rdx+10h], xmm1
0x1400e8543  movups  xmm0, xmmword ptr [rax+20h]
0x1400e8547  movups  xmmword ptr [rdx+20h], xmm0
0x1400e854b  movups  xmm1, xmmword ptr [rax+30h]
0x1400e854f  movups  xmmword ptr [rdx+30h], xmm1
0x1400e8553  movups  xmm0, xmmword ptr [rax+40h]
0x1400e8557  movups  xmmword ptr [rdx+40h], xmm0
0x1400e855b  movups  xmm1, xmmword ptr [rax+50h]
0x1400e855f  movups  xmmword ptr [rdx+50h], xmm1
0x1400e8563  movups  xmm0, xmmword ptr [rax+60h]
0x1400e8567  movups  xmmword ptr [rdx+60h], xmm0
0x1400e856b  movups  xmm1, xmmword ptr [rax+70h]
0x1400e856f  movups  xmmword ptr [rdx+70h], xmm1
0x1400e8573  lea     rdx, [rdx+80h]
0x1400e857a  lea     rax, [rax+80h]
0x1400e8581  sub     rcx, 1
0x1400e8585  jnz     short loc_1400E8535
0x1400e8587  movups  xmm0, xmmword ptr [rax]
0x1400e858a  movups  xmmword ptr [rdx], xmm0
0x1400e858d  movups  xmm1, xmmword ptr [rax+10h]
0x1400e8591  movups  xmmword ptr [rdx+10h], xmm1
0x1400e8595  movups  xmm0, xmmword ptr [rax+20h]
0x1400e8599  movups  xmmword ptr [rdx+20h], xmm0
0x1400e859d  movups  xmm1, xmmword ptr [rax+30h]
0x1400e85a1  movups  xmmword ptr [rdx+30h], xmm1
0x1400e85a5  mov     rcx, [rax+40h]
0x1400e85a9  mov     [rdx+40h], rcx
0x1400e85ad  test    esi, esi
0x1400e85af  jnz     loc_1400E8646
0x1400e85b5  lea     ecx, [rsi+1]
0x1400e85b8  shl     rcx, 3
0x1400e85bc  mov     edx, 79737355h
0x1400e85c1  call    cs:__imp_Win32AllocPoolWithQuotaZInit
0x1400e85c8  nop     dword ptr [rax+rax+00h]
0x1400e85cd  mov     rbx, rax
0x1400e85d0  mov     [rsp+968h+var_908], rax
0x1400e85d5  test    rax, rax
0x1400e85d8  jz      loc_1400E867F
0x1400e85de  mov     rdi, rsi
0x1400e85e1  shl     rdi, 3
0x1400e85e5  mov     r8, rdi; Size
0x1400e85e8  mov     rdx, r13; Src
0x1400e85eb  mov     rcx, rax; void *
0x1400e85ee  call    memmove
0x1400e85f3  xor     ecx, ecx
0x1400e85f5  mov     [rsp+968h+var_920], ecx
0x1400e85f9  mov     r8, [rsp+968h+var_8A8]
0x1400e8601  mov     r9, [rsp+968h+var_8B0]
0x1400e8609  mov     r10, [rsp+968h+var_8B8]
0x1400e8611  cmp     ecx, esi
0x1400e8613  jnb     short loc_1400E8632
0x1400e8615  lea     rdx, [rbx+rcx*8]
0x1400e8619  mov     eax, [rdx]
0x1400e861b  cmp     eax, 0FFFFFFF5h
0x1400e861e  jz      short loc_1400E8637
0x1400e8620  cmp     eax, 0FFFFFFF4h
0x1400e8623  jz      short loc_1400E8641
0x1400e8625  cmp     eax, 0FFFFFFF6h
0x1400e8628  jz      short loc_1400E863C
0x1400e862a  inc     ecx
0x1400e862c  mov     [rsp+968h+var_920], ecx
0x1400e8630  jmp     short loc_1400E8611
0x1400e8632  jmp     loc_1400E86DA
0x1400e8637  mov     [rdx], r9
0x1400e863a  jmp     short loc_1400E862A
0x1400e863c  mov     [rdx], r10
0x1400e863f  jmp     short loc_1400E862A
0x1400e8641  mov     [rdx], r8
0x1400e8644  jmp     short loc_1400E862A
0x1400e8646  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1400e864d  nop     dword ptr [rax+rax+00h]
0x1400e8652  mov     ecx, 4
0x1400e8657  mov     r8d, 1
0x1400e865d  test    rax, rax
0x1400e8660  cmovz   r8d, ecx; Alignment
0x1400e8664  mov     rdx, rsi
0x1400e8667  shl     rdx, 3; Length
0x1400e866b  mov     rcx, r13; Address
0x1400e866e  call    cs:__imp_ProbeForRead
0x1400e8675  nop     dword ptr [rax+rax+00h]
0x1400e867a  jmp     loc_1400E85B5
0x1400e867f  mov     [rsp+968h+var_910], edi
0x1400e8683  mov     ecx, 8
0x1400e8688  call    UserSetLastError
0x1400e868d  jmp     short loc_1400E86B8
0x1400e868f  mov     rcx, [rsp+968h+var_908]
0x1400e8694  test    rcx, rcx
0x1400e8697  jz      short loc_1400E86A5
0x1400e8699  call    cs:__imp_Win32FreePool
0x1400e86a0  nop     dword ptr [rax+rax+00h]
0x1400e86a5  mov     edi, [rsp+968h+var_914]
0x1400e86a9  mov     [rsp+968h+var_910], edi
0x1400e86ad  mov     ecx, 57h ; 'W'
0x1400e86b2  call    UserSetLastError
0x1400e86b7  nop
0x1400e86b8  call    cs:__imp_UserSessionSwitchLeaveCrit
0x1400e86bf  nop     dword ptr [rax+rax+00h]
0x1400e86c4  mov     eax, edi
0x1400e86c6  add     rsp, 930h
0x1400e86cd  pop     r15
0x1400e86cf  pop     r14
0x1400e86d1  pop     r13
0x1400e86d3  pop     r12
0x1400e86d5  pop     rdi
0x1400e86d6  pop     rsi
0x1400e86d7  pop     rbx
0x1400e86d8  retn
0x1400e86da  test    r15b, 8
0x1400e86de  jnz     loc_1400E88A4
0x1400e86e4  test    r14d, r14d
0x1400e86e7  cmovnz  r12, [rsp+968h+var_8F8]
0x1400e86ed  mov     [rdi+rbx], r12
0x1400e86f1  mov     r8, cs:__imp_Win32FreePool
0x1400e86f8  mov     rdx, rbx
0x1400e86fb  lea     rcx, [rsp+968h+var_8F0]
0x1400e8700  call    ??0?$Win32RawLockedItemNoCleanup@U_ACCESS_ALLOWED_ACE@@$0A@@@QEAA@PEAU_ACCESS_ALLOWED_ACE@@P6AXPEAX@Z@Z; Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(_ACCESS_ALLOWED_ACE *,void (*)(void *))
0x1400e8705  mov     dword ptr [rsp+968h+var_948], r15d
0x1400e870a  mov     r9d, [rsp+968h+var_91C]
0x1400e870f  mov     r8d, [rsp+968h+var_918]
0x1400e8714  mov     rdx, rbx
0x1400e8717  mov     ecx, esi
0x1400e8719  call    xxxMsgWaitForMultipleObjectsEx
0x1400e871e  mov     edi, eax
0x1400e8720  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400e8727  nop     dword ptr [rax+rax+00h]
0x1400e872c  test    rax, rax
0x1400e872f  jz      loc_1400E8892
0x1400e8735  mov     rbx, [rax]
0x1400e8738  mov     rax, 0FFFFF78000000320h
0x1400e8742  mov     rax, [rax]
0x1400e8745  mov     rcx, 0FFFFF78000000004h
0x1400e874f  mov     ecx, [rcx]
0x1400e8751  imul    rcx, rax
0x1400e8755  shr     rcx, 18h
0x1400e8759  mov     rax, [rbx+1E0h]
0x1400e8760  xchg    ecx, [rax+14h]
0x1400e8763  cmp     dword ptr [rbx+518h], 0
0x1400e876a  jnz     short loc_1400E8778
0x1400e876c  mov     edx, 1
0x1400e8771  xor     ecx, ecx
0x1400e8773  call    ?xxxUpdateInputHangInfo@@YAXPEAUtagWND@@W4INPUTHANGTIME@@@Z; xxxUpdateInputHangInfo(tagWND *,INPUTHANGTIME)
0x1400e8778  mov     rcx, [rbx+1E0h]
0x1400e877f  xor     eax, eax
0x1400e8781  xchg    eax, [rcx+10h]
0x1400e8784  and     qword ptr [rbx+550h], 0FFFFFFFFFFFFFBFFh
0x1400e878f  lea     rcx, [rsp+968h+var_8F0]
0x1400e8794  call    ??1?$Win32RawLockedItem@UtagEVENT_PACKET_TARGETS@@$0A@@@QEAA@XZ; Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>::~Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>(void)
0x1400e8799  test    r14d, r14d
0x1400e879c  jz      loc_1400E86B8
0x1400e87a2  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400e87a9  nop     dword ptr [rax+rax+00h]
0x1400e87ae  test    rax, rax
0x1400e87b1  jz      loc_1400E8899
0x1400e87b7  mov     rcx, [rax]
0x1400e87ba  mov     [rsp+968h+var_930], 0
0x1400e87c3  mov     [rsp+968h+var_938], 0
0x1400e87cc  mov     [rsp+968h+var_940], 0
0x1400e87d4  mov     [rsp+968h+var_948], 0FFFFFFFF80000000h
0x1400e87dd  xor     r9d, r9d
0x1400e87e0  mov     r8, [rcx+660h]
0x1400e87e7  mov     rdx, [rcx+650h]
0x1400e87ee  mov     rcx, [rcx+668h]
0x1400e87f5  call    cs:__imp_ZwAssociateWaitCompletionPacket
0x1400e87fc  nop     dword ptr [rax+rax+00h]
0x1400e8801  jmp     loc_1400E86B8
0x1400e8806  test    r14d, r14d
0x1400e8809  jnz     short loc_1400E886D
0x1400e880b  mov     ecx, [rax+4]
0x1400e880e  test    r15b, 4
0x1400e8812  jz      short loc_1400E885E
0x1400e8814  mov     eax, [rax+8]
0x1400e8817  mov     [rsp+968h+var_928], eax
0x1400e881b  lea     rax, [rsp+968h+var_928]
0x1400e8820  mov     eax, [rax]
0x1400e8822  or      ax, cx
0x1400e8825  test    bx, ax
0x1400e8828  jz      loc_1400E839D
0x1400e882e  mov     edi, esi
  ... truncated ...
```
