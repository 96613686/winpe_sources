# StateEntryFnAuthenticating

- ea: `0x18007e300`
- end: `0x18007e508`
- name: `StateEntryFnAuthenticating`
- size: `520`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000892c`
- `0x180008998`
- `0x18007b3e0`
- `0x18007e300`
- `0x180096010`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18007e3eb`
- `MobileNetworking!ReleaseWriteLock` at `0x18007e3eb`
- `MobileNetworking!ReleaseReadLock` at `0x18007e47b`
- `MobileNetworking!ReleaseReadLock` at `0x18007e48c`
- `MobileNetworking!ReleaseReadLock` at `0x18007e47b`
- `MobileNetworking!ReleaseReadLock` at `0x18007e48c`
- `MobileNetworking!AcquireReadLock` at `0x18007e3fa`
- `MobileNetworking!AcquireReadLock` at `0x18007e3fa`
- `MobileNetworking!AcquireWriteLock` at `0x18007e3c0`
- `MobileNetworking!AcquireWriteLock` at `0x18007e3c0`

## pseudocode

```c
__int64 __fastcall StateEntryFnAuthenticating(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v5; // rdi
  unsigned int v6; // eax
  unsigned int v7; // ebx
  PVOID *v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // eax
  __int64 v12; // [rsp+70h] [rbp+8h] BYREF

  v3 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids);
  v5 = *(_QWORD *)(a1 + 64);
  v12 = 0;
  LOBYTE(a3) = *(_BYTE *)(v5 + 296);
  v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int64 *))(qword_1800BB5A8 + 16))(
         v3,
         v5,
         a3,
         v5 + 297,
         &v12);
  v7 = v6;
  if ( !v6 )
  {
    AcquireWriteLock(v5, v5 + 24, "StateEntryFnAuthenticating", 116);
    *(_QWORD *)(v5 + 288) = v12;
    ReleaseWriteLock(v5, v5 + 24, "StateEntryFnAuthenticating", 118);
    AcquireReadLock(v5 + 24);
    if ( *(_QWORD *)(v5 + 288) )
    {
      v10 = (*(__int64 (**)(void))(qword_1800BB5A8 + 32))();
      v7 = v10;
      if ( !v10 )
      {
        ReleaseReadLock(v5 + 24);
        v6 = TmChangeTimer(*(HANDLE *)(a1 + 120), 0x1D4C0u);
        v7 = v6;
        if ( v6 )
        {
          v8 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            return v7;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_24;
          v9 = 20;
          goto LABEL_22;
        }
LABEL_23:
        v8 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_24;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids, v10);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids);
      v7 = 5023;
    }
    ReleaseReadLock(v5 + 24);
    goto LABEL_23;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v9 = 17;
LABEL_22:
    WPP_SF_d(v8[2], v9, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids, v6);
    goto LABEL_23;
  }
LABEL_24:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
    WPP_SF_d(v8[2], 21, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18007e300  push    rbx
0x18007e302  push    rbp
0x18007e303  push    rsi
0x18007e304  push    rdi
0x18007e305  push    r14
0x18007e307  push    r15
0x18007e309  sub     rsp, 38h
0x18007e30d  mov     rbx, r8
0x18007e310  mov     rbp, rcx
0x18007e313  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e31a  lea     r14, WPP_GLOBAL_Control
0x18007e321  lea     r15, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids
0x18007e328  cmp     rcx, r14
0x18007e32b  jz      short loc_18007E344
0x18007e32d  test    byte ptr [rcx+1Ch], 1
0x18007e331  jz      short loc_18007E344
0x18007e333  mov     rcx, [rcx+10h]
0x18007e337  mov     edx, 10h
0x18007e33c  mov     r8, r15
0x18007e33f  call    WPP_SF_
0x18007e344  mov     rdi, [rbp+40h]
0x18007e348  lea     rcx, [rsp+68h+arg_0]
0x18007e34d  mov     rax, cs:qword_1800BB5A8
0x18007e354  mov     rdx, rdi
0x18007e357  mov     [rsp+68h+arg_0], 0
0x18007e360  mov     [rsp+68h+var_48], rcx
0x18007e365  mov     rcx, rbx
0x18007e368  mov     r8b, [rdi+128h]
0x18007e36f  lea     r9, [rdi+129h]
0x18007e376  mov     rax, [rax+10h]
0x18007e37a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e37f  mov     ebx, eax
0x18007e381  test    eax, eax
0x18007e383  jz      short loc_18007E3A9
0x18007e385  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e38c  cmp     rcx, r14
0x18007e38f  jz      loc_18007E4F8
0x18007e395  test    byte ptr [rcx+1Ch], 2
0x18007e399  jz      loc_18007E4D9
0x18007e39f  mov     edx, 11h
0x18007e3a4  jmp     loc_18007E4C3
0x18007e3a9  lea     rsi, [rdi+18h]
0x18007e3ad  mov     r9d, 74h ; 't'
0x18007e3b3  mov     rdx, rsi
0x18007e3b6  lea     r8, aStateentryfnau; "StateEntryFnAuthenticating"
0x18007e3bd  mov     rcx, rdi
0x18007e3c0  call    cs:__imp_AcquireWriteLock
0x18007e3c7  nop     dword ptr [rax+rax+00h]
0x18007e3cc  mov     rax, [rsp+68h+arg_0]
0x18007e3d1  lea     r8, aStateentryfnau; "StateEntryFnAuthenticating"
0x18007e3d8  mov     r9d, 76h ; 'v'
0x18007e3de  mov     [rdi+120h], rax
0x18007e3e5  mov     rdx, rsi
0x18007e3e8  mov     rcx, rdi
0x18007e3eb  call    cs:__imp_ReleaseWriteLock
0x18007e3f2  nop     dword ptr [rax+rax+00h]
0x18007e3f7  mov     rcx, rsi
0x18007e3fa  call    cs:__imp_AcquireReadLock
0x18007e401  nop     dword ptr [rax+rax+00h]
0x18007e406  mov     rcx, [rdi+120h]
0x18007e40d  test    rcx, rcx
0x18007e410  jnz     short loc_18007E43C
0x18007e412  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e419  cmp     rcx, r14
0x18007e41c  jz      short loc_18007E435
0x18007e41e  test    byte ptr [rcx+1Ch], 2
0x18007e422  jz      short loc_18007E435
0x18007e424  mov     rcx, [rcx+10h]
0x18007e428  mov     edx, 12h
0x18007e42d  mov     r8, r15
0x18007e430  call    WPP_SF_
0x18007e435  mov     ebx, 139Fh
0x18007e43a  jmp     short loc_18007E478
0x18007e43c  mov     rax, cs:qword_1800BB5A8
0x18007e443  mov     rax, [rax+20h]
0x18007e447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e44c  mov     ebx, eax
0x18007e44e  test    eax, eax
0x18007e450  jz      short loc_18007E489
0x18007e452  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e459  cmp     rcx, r14
0x18007e45c  jz      short loc_18007E478
0x18007e45e  test    byte ptr [rcx+1Ch], 2
0x18007e462  jz      short loc_18007E478
0x18007e464  mov     rcx, [rcx+10h]
0x18007e468  mov     edx, 13h
0x18007e46d  mov     r9d, eax
0x18007e470  mov     r8, r15
0x18007e473  call    WPP_SF_d
0x18007e478  mov     rcx, rsi
0x18007e47b  call    cs:__imp_ReleaseReadLock
0x18007e482  nop     dword ptr [rax+rax+00h]
0x18007e487  jmp     short loc_18007E4D2
0x18007e489  mov     rcx, rsi
0x18007e48c  call    cs:__imp_ReleaseReadLock
0x18007e493  nop     dword ptr [rax+rax+00h]
0x18007e498  mov     rcx, [rbp+78h]; Timer
0x18007e49c  mov     edx, 1D4C0h; DueTime
0x18007e4a1  call    TmChangeTimer
0x18007e4a6  mov     ebx, eax
0x18007e4a8  test    eax, eax
0x18007e4aa  jz      short loc_18007E4D2
0x18007e4ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e4b3  cmp     rcx, r14
0x18007e4b6  jz      short loc_18007E4F8
0x18007e4b8  test    byte ptr [rcx+1Ch], 2
0x18007e4bc  jz      short loc_18007E4D9
0x18007e4be  mov     edx, 14h
0x18007e4c3  mov     rcx, [rcx+10h]
0x18007e4c7  mov     r9d, eax
0x18007e4ca  mov     r8, r15
0x18007e4cd  call    WPP_SF_d
0x18007e4d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e4d9  cmp     rcx, r14
0x18007e4dc  jz      short loc_18007E4F8
0x18007e4de  test    byte ptr [rcx+1Ch], 1
0x18007e4e2  jz      short loc_18007E4F8
0x18007e4e4  mov     rcx, [rcx+10h]
0x18007e4e8  mov     edx, 15h
0x18007e4ed  mov     r9d, ebx
0x18007e4f0  mov     r8, r15
0x18007e4f3  call    WPP_SF_d
0x18007e4f8  mov     eax, ebx
0x18007e4fa  add     rsp, 38h
0x18007e4fe  pop     r15
0x18007e500  pop     r14
0x18007e502  pop     rdi
0x18007e503  pop     rsi
0x18007e504  pop     rbp
0x18007e505  pop     rbx
0x18007e506  retn
```
