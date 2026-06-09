# tagTHREADINFO::SetPriorityFloor(tagThreadPriorityFloor)

- ea: `0x1400a5c60`
- end: `0x1400a5fd7`
- name: `?SetPriorityFloor@tagTHREADINFO@@QEAAXW4tagThreadPriorityFloor@@@Z`
- size: `887`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400a5c60`
- `0x1400a5fe0`
- `0x1400a612c`
- `0x1400a6208`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400a5cda`
- `ntoskrnl!KeBugCheckEx` at `0x1400a5cda`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400a5ca8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400a5ca8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a5c93`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a5c93`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a5f6a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a5f6a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400a5f5e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400a5f5e`
- `ntoskrnl!PsAdjustWin32kPriorityFloor` at `0x1400a5e90`
- `ntoskrnl!PsAdjustWin32kPriorityFloor` at `0x1400a5e90`
- `ntoskrnl!PsGetThreadId` at `0x1400a5d3f`
- `ntoskrnl!PsGetThreadId` at `0x1400a5e1d`
- `ntoskrnl!PsGetThreadId` at `0x1400a5efd`
- `ntoskrnl!PsGetThreadId` at `0x1400a5d3f`
- `ntoskrnl!PsGetThreadId` at `0x1400a5e1d`
- `ntoskrnl!PsGetThreadId` at `0x1400a5efd`
- `WIN32K!W32GetUserSessionState` at `0x1400a5d58`
- `WIN32K!W32GetUserSessionState` at `0x1400a5e2c`
- `WIN32K!W32GetUserSessionState` at `0x1400a5f0c`
- `WIN32K!W32GetUserSessionState` at `0x1400a5d58`
- `WIN32K!W32GetUserSessionState` at `0x1400a5e2c`
- `WIN32K!W32GetUserSessionState` at `0x1400a5f0c`

## pseudocode

```c
void __fastcall tagTHREADINFO::SetPriorityFloor(_QWORD *a1, unsigned int a2)
{
  char v2; // r15
  __int64 v4; // rsi
  __int64 v5; // r13
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r12
  int v9; // esi
  bool v10; // bp
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 UserSessionState; // rax
  int v14; // edx
  int v15; // r8d
  bool v16; // si
  char ThreadId; // bl
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rax
  int v22; // edx
  int v23; // r8d
  _WORD *v24; // rax
  bool v25; // r13
  __int16 v26; // di
  int v27; // esi
  char v28; // bp
  char v29; // bl
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // rax
  int v34; // r8d
  int v35; // edx
  int BugCheckParameter4; // [rsp+20h] [rbp-88h]
  int v37; // [rsp+28h] [rbp-80h]
  int v38; // [rsp+38h] [rbp-70h]
  bool v39; // [rsp+B8h] [rbp+10h]
  bool v40; // [rsp+B8h] [rbp+10h]

  v2 = 1;
  if ( a2 > 1
    || (_mm_lfence(),
        v4 = a2,
        v5 = LOBYTE(asc_1402564D0[4 * a2]),
        KeEnterCriticalRegion(),
        ExAcquirePushLockExclusiveEx(a1 + 216, 0),
        v8 = (unsigned int)v5,
        *((_BYTE *)a1 + v5 + 1744) == 0xFF)
    || (v9 = *(_DWORD *)&asc_1402564D0[4 * v4 + 2], (v9 & *((_DWORD *)a1 + 435)) == v9) )
  {
    KeBugCheckEx(0x164u, 0x41u, 0, 0, 0);
  }
  v10 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v39 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    PsGetThreadId((PETHREAD)*a1);
    UserSessionState = W32GetUserSessionState(a1[57], v11, v12);
    LOBYTE(v14) = v10;
    LOBYTE(v15) = v39;
    WPP_RECORDER_AND_TRACE_SF_DDdd(*((_QWORD *)WPP_GLOBAL_Control + 3), v14, v15, *(_QWORD *)(UserSessionState + 69136));
  }
  *((_DWORD *)a1 + 435) |= v9;
  if ( ++*((_BYTE *)a1 + v5 + 1744) == 1 )
  {
    if ( *((unsigned __int16 *)a1 + 868) >= 1 << v5 )
    {
      v24 = a1 + 217;
    }
    else
    {
      v16 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v40 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        ThreadId = (unsigned __int8)PsGetThreadId((PETHREAD)*a1);
        v21 = W32GetUserSessionState(v19, v18, v20);
        LOBYTE(v22) = v16;
        LOBYTE(v23) = v40;
        WPP_RECORDER_AND_TRACE_SF_dD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v22,
          v23,
          *(_QWORD *)(v21 + 69136),
          4,
          13,
          16,
          (__int64)WPP_88dc8779c13439e164336e7011252f30_Traceguids,
          v5,
          ThreadId);
      }
      PsAdjustWin32kPriorityFloor(*a1, (unsigned int)v5, v6, v7);
      v24 = a1 + 217;
    }
    *((_WORD *)a1 + 868) = *v24 | (1 << v5);
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
  {
    v2 = 0;
  }
  v25 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v26 = *((_WORD *)a1 + 868);
    v27 = *((_DWORD *)a1 + 435);
    v28 = *((_BYTE *)a1 + v8 + 1744);
    v29 = (unsigned __int8)PsGetThreadId((PETHREAD)*a1);
    v33 = W32GetUserSessionState(v31, v30, v32);
    LOBYTE(v34) = v25;
    LOBYTE(v35) = v2;
    WPP_RECORDER_AND_TRACE_SF_DdddD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v35,
      v34,
      *(_QWORD *)(v33 + 69136),
      BugCheckParameter4,
      v37,
      17,
      v38,
      v29,
      v8,
      v28,
      v27,
      v26);
  }
  ExReleasePushLockExclusiveEx(a1 + 216, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1400a5c60  mov     [rsp+arg_0], rbx
0x1400a5c65  push    rbp
0x1400a5c66  push    rsi
0x1400a5c67  push    rdi
0x1400a5c68  push    r12
0x1400a5c6a  push    r13
0x1400a5c6c  push    r14
0x1400a5c6e  push    r15
0x1400a5c70  sub     rsp, 70h
0x1400a5c74  mov     r15d, 1
0x1400a5c7a  mov     r14, rcx
0x1400a5c7d  cmp     edx, r15d
0x1400a5c80  ja      short loc_1400A5CC2
0x1400a5c82  lfence
0x1400a5c85  mov     esi, edx
0x1400a5c87  lea     rdi, asc_1402564D0; "\r"
0x1400a5c8e  movzx   r13d, byte ptr [rdi+rsi*8]
0x1400a5c93  call    cs:__imp_KeEnterCriticalRegion
0x1400a5c9a  nop     dword ptr [rax+rax+00h]
0x1400a5c9f  xor     edx, edx
0x1400a5ca1  lea     rcx, [r14+6C0h]
0x1400a5ca8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400a5caf  nop     dword ptr [rax+rax+00h]
0x1400a5cb4  cmp     byte ptr [r13+r14+6D0h], 0FFh
0x1400a5cbd  mov     r12d, r13d
0x1400a5cc0  jnz     short loc_1400A5CE7
0x1400a5cc2  xor     r9d, r9d; BugCheckParameter3
0x1400a5cc5  mov     [rsp+0A8h+BugCheckParameter4], 0; BugCheckParameter4
0x1400a5cce  xor     r8d, r8d; BugCheckParameter2
0x1400a5cd1  mov     ecx, 164h; BugCheckCode
0x1400a5cd6  lea     edx, [r9+41h]; BugCheckParameter1
0x1400a5cda  call    cs:__imp_KeBugCheckEx
0x1400a5ce7  mov     esi, [rdi+rsi*8+4]
0x1400a5ceb  mov     eax, [r14+6CCh]
0x1400a5cf2  and     eax, esi
0x1400a5cf4  cmp     eax, esi
0x1400a5cf6  jz      short loc_1400A5CC2
0x1400a5cf8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5cff  lea     rbx, WPP_GLOBAL_Control
0x1400a5d06  cmp     rcx, rbx
0x1400a5d09  jz      short loc_1400A5D18
0x1400a5d0b  test    dword ptr [rcx+2Ch], 1000h
0x1400a5d12  jnz     loc_1400A5FA4
0x1400a5d18  xor     bpl, bpl
0x1400a5d1b  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400a5d22  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400a5d29  setnz   al
0x1400a5d2c  mov     [rsp+0A8h+arg_8], al
0x1400a5d33  test    bpl, bpl
0x1400a5d36  jz      loc_1400A5F8F
0x1400a5d3c  mov     rcx, [r14]; Thread
0x1400a5d3f  call    cs:__imp_PsGetThreadId
0x1400a5d46  nop     dword ptr [rax+rax+00h]
0x1400a5d4b  mov     rcx, [r14+1C8h]
0x1400a5d52  mov     rdi, rax
0x1400a5d55  mov     ebx, [rcx+38h]
0x1400a5d58  call    cs:__imp_W32GetUserSessionState
0x1400a5d5f  nop     dword ptr [rax+rax+00h]
0x1400a5d64  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5d6b  mov     dl, bpl
0x1400a5d6e  mov     r8b, [rsp+0A8h+arg_8]
0x1400a5d76  mov     [rsp+0A8h+var_50], r13d
0x1400a5d7b  mov     r9, [rax+10E10h]
0x1400a5d82  mov     rcx, [rcx+18h]
0x1400a5d86  mov     [rsp+0A8h+var_58], esi
0x1400a5d8a  mov     [rsp+0A8h+var_60], edi
0x1400a5d8e  mov     [rsp+0A8h+var_68], ebx
0x1400a5d92  mov     [rsp+0A8h+var_78], 0Fh
0x1400a5d99  call    WPP_RECORDER_AND_TRACE_SF_DDdd
0x1400a5d9e  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400a5da5  lea     rbx, WPP_GLOBAL_Control
0x1400a5dac  or      [r14+6CCh], esi
0x1400a5db3  add     [r13+r14+6D0h], r15b
0x1400a5dbb  cmp     [r13+r14+6D0h], r15b
0x1400a5dc3  jnz     loc_1400A5EAA
0x1400a5dc9  mov     cl, r13b
0x1400a5dcc  lea     rbp, [r14+6C8h]
0x1400a5dd3  movzx   eax, word ptr [rbp+0]
0x1400a5dd7  mov     edi, r15d
0x1400a5dda  shl     edi, cl
0x1400a5ddc  cmp     eax, edi
0x1400a5dde  jge     loc_1400A5F9C
0x1400a5de4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5deb  cmp     rcx, rbx
0x1400a5dee  jz      short loc_1400A5DFD
0x1400a5df0  test    dword ptr [rcx+2Ch], 1000h
0x1400a5df7  jnz     loc_1400A5FB6
0x1400a5dfd  xor     sil, sil
0x1400a5e00  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400a5e07  setnz   al
0x1400a5e0a  mov     [rsp+0A8h+arg_8], al
0x1400a5e11  test    sil, sil
0x1400a5e14  jnz     short loc_1400A5E1A
0x1400a5e16  test    al, al
0x1400a5e18  jz      short loc_1400A5E8A
0x1400a5e1a  mov     rcx, [r14]; Thread
0x1400a5e1d  call    cs:__imp_PsGetThreadId
0x1400a5e24  nop     dword ptr [rax+rax+00h]
0x1400a5e29  mov     rbx, rax
0x1400a5e2c  call    cs:__imp_W32GetUserSessionState
0x1400a5e33  nop     dword ptr [rax+rax+00h]
0x1400a5e38  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5e3f  mov     dl, sil
0x1400a5e42  mov     r8b, [rsp+0A8h+arg_8]
0x1400a5e4a  mov     [rsp+0A8h+var_60], ebx
0x1400a5e4e  mov     r9, [rax+10E10h]
0x1400a5e55  lea     rax, WPP_88dc8779c13439e164336e7011252f30_Traceguids
0x1400a5e5c  mov     rcx, [rcx+18h]
0x1400a5e60  mov     [rsp+0A8h+var_68], r13d
0x1400a5e65  mov     [rsp+0A8h+var_70], rax
0x1400a5e6a  mov     [rsp+0A8h+var_78], 10h
0x1400a5e71  mov     [rsp+0A8h+var_80], 0Dh
0x1400a5e79  mov     byte ptr [rsp+0A8h+BugCheckParameter4], 4
0x1400a5e7e  call    WPP_RECORDER_AND_TRACE_SF_dD
0x1400a5e83  lea     rbx, WPP_GLOBAL_Control
0x1400a5e8a  mov     rcx, [r14]
0x1400a5e8d  mov     edx, r13d
0x1400a5e90  call    cs:__imp_PsAdjustWin32kPriorityFloor
0x1400a5e97  nop     dword ptr [rax+rax+00h]
0x1400a5e9c  lea     rax, [r14+6C8h]
0x1400a5ea3  or      di, [rax]
0x1400a5ea6  mov     [rbp+0], di
0x1400a5eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5eb1  cmp     rcx, rbx
0x1400a5eb4  jz      short loc_1400A5EC3
0x1400a5eb6  test    dword ptr [rcx+2Ch], 1000h
0x1400a5ebd  jnz     loc_1400A5FC8
0x1400a5ec3  xor     r15b, r15b
0x1400a5ec6  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a5ecd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a5ed4  setnz   r13b
0x1400a5ed8  test    r15b, r15b
0x1400a5edb  jnz     short loc_1400A5EE2
0x1400a5edd  test    r13b, r13b
0x1400a5ee0  jz      short loc_1400A5F55
0x1400a5ee2  mov     rcx, [r14]; Thread
0x1400a5ee5  movzx   edi, word ptr [r14+6C8h]
0x1400a5eed  mov     esi, [r14+6CCh]
0x1400a5ef4  movzx   ebp, byte ptr [r12+r14+6D0h]
0x1400a5efd  call    cs:__imp_PsGetThreadId
0x1400a5f04  nop     dword ptr [rax+rax+00h]
0x1400a5f09  mov     rbx, rax
0x1400a5f0c  call    cs:__imp_W32GetUserSessionState
0x1400a5f13  nop     dword ptr [rax+rax+00h]
0x1400a5f18  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5f1f  mov     r8b, r13b
0x1400a5f22  mov     [rsp+0A8h+var_48], edi
0x1400a5f26  mov     dl, r15b
0x1400a5f29  mov     [rsp+0A8h+var_50], esi
0x1400a5f2d  mov     r9, [rax+10E10h]
0x1400a5f34  mov     rcx, [rcx+18h]
0x1400a5f38  mov     [rsp+0A8h+var_58], ebp
0x1400a5f3c  movzx   r10d, r12b
0x1400a5f40  mov     [rsp+0A8h+var_60], r10d
0x1400a5f45  mov     [rsp+0A8h+var_68], ebx
0x1400a5f49  mov     [rsp+0A8h+var_78], 11h
0x1400a5f50  call    WPP_RECORDER_AND_TRACE_SF_DdddD
0x1400a5f55  xor     edx, edx
0x1400a5f57  lea     rcx, [r14+6C0h]
0x1400a5f5e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400a5f65  nop     dword ptr [rax+rax+00h]
0x1400a5f6a  call    cs:__imp_KeLeaveCriticalRegion
0x1400a5f71  nop     dword ptr [rax+rax+00h]
0x1400a5f76  mov     rbx, [rsp+0A8h+arg_0]
0x1400a5f7e  add     rsp, 70h
0x1400a5f82  pop     r15
0x1400a5f84  pop     r14
0x1400a5f86  pop     r13
0x1400a5f88  pop     r12
0x1400a5f8a  pop     rdi
0x1400a5f8b  pop     rsi
0x1400a5f8c  pop     rbp
0x1400a5f8d  retn
0x1400a5f8f  test    al, al
0x1400a5f91  jz      loc_1400A5DAC
0x1400a5f97  jmp     loc_1400A5D3C
0x1400a5f9c  mov     rax, rbp
0x1400a5f9f  jmp     loc_1400A5EA3
0x1400a5fa4  cmp     byte ptr [rcx+29h], 4
0x1400a5fa8  jb      loc_1400A5D18
0x1400a5fae  mov     bpl, r15b
0x1400a5fb1  jmp     loc_1400A5D1B
0x1400a5fb6  cmp     byte ptr [rcx+29h], 4
0x1400a5fba  jb      loc_1400A5DFD
0x1400a5fc0  mov     sil, r15b
0x1400a5fc3  jmp     loc_1400A5E00
0x1400a5fc8  cmp     byte ptr [rcx+29h], 4
0x1400a5fcc  jnb     loc_1400A5EC6
0x1400a5fd2  jmp     loc_1400A5EC3
```
