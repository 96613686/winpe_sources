# SrvAdminDeregisterFile

- ea: `0x140006b20`
- end: `0x140006f5f`
- name: `SrvAdminDeregisterFile`
- size: `1087`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, installer_update`

## callees

- `0x140005190`
- `0x140006b20`
- `0x140006f70`
- `0x140007160`
- `0x140007360`
- `0x140009960`
- `0x14000bfa0`
- `0x140016c84`
- `0x1400261ac`
- `0x140029b40`
- `0x140029e84`
- `0x14002a4c0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140006b3a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140006b3a`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b78d`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b7a0`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b7b3`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b848`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b85b`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b86e`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b78d`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b7a0`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b7b3`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b848`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b85b`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002b86e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140006efc`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140006efc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b829`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b8e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b829`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b8e4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140006c18`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140006c18`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140006c9a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140006dcf`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140006dfe`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140006c9a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140006dcf`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140006dfe`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006b74`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006d83`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006b74`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006d83`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140006da4`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140006deb`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140006e97`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140006da4`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140006deb`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140006e97`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140006db8`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140006db8`

## pseudocode

```c
__int64 __fastcall SrvAdminDeregisterFile(__int64 a1, __int64 a2, int a3)
{
  __int64 v5; // rsi
  __int64 v6; // rbx
  __int64 v7; // r9
  __int64 v8; // r14
  unsigned int v9; // edi
  unsigned __int64 v10; // r15
  KIRQL v11; // r12
  __int64 v12; // r8
  unsigned int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  _DWORD **v16; // r15
  int v17; // eax
  void (*v18)(void); // rax
  _DWORD *v19; // rdi
  __int64 v20; // rdi
  int v21; // eax
  __int64 v23; // rax
  __int64 v24; // rax
  void *v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  void *v28; // rcx
  void *v29; // rcx
  void *v30; // rcx
  void *v31; // rcx
  void *v32; // rcx

  ExAcquireResourceSharedLite(&SrvAdminInstanceListLock, 1u);
  v5 = SrvAdminInstanceList;
  if ( (__int64 *)SrvAdminInstanceList == &SrvAdminInstanceList )
  {
LABEL_35:
    ExReleaseResourceLite(&SrvAdminInstanceListLock);
    return 3221225987LL;
  }
  while ( *(unsigned __int8 *)(v5 + 16) != a3 )
  {
    v5 = *(_QWORD *)v5;
    if ( (__int64 *)v5 == &SrvAdminInstanceList )
      goto LABEL_35;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v5 + 24));
  ExReleaseResourceLite(&SrvAdminInstanceListLock);
  if ( !v5 )
    return 3221225987LL;
  v6 = RfsTable64Remove(*(PEX_SPIN_LOCK *)(v5 + 80));
  if ( v6 )
  {
    if ( *(_QWORD *)(v6 + 40) != -1 && *(_QWORD *)(v6 + 48) != -1 )
    {
      v23 = RfsTable64Lookup(*(PEX_SPIN_LOCK *)(v5 + 64));
      if ( v23 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v23 + 152));
        SrvAdminDereferenceSession(v23);
      }
      v24 = RfsTable64Lookup(*(PEX_SPIN_LOCK *)(v5 + 88));
      if ( v24 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v24 + 48));
        SrvAdminDereferenceTreeConnect(v24);
      }
    }
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      SATrace(
        (unsigned __int16 *)(v6 + 16),
        0,
        0,
        v7,
        0,
        0,
        0,
        1,
        *(_QWORD *)(v6 + 40),
        *(_QWORD *)(v6 + 48),
        a2,
        *(unsigned int *)(v6 + 36),
        2);
    v8 = *(_QWORD *)(v5 + 72);
    v9 = *(_DWORD *)(v6 + 36);
    v10 = *(_QWORD *)(v8 + 16);
    if ( (*(_BYTE *)(v8 + 88) & 0x40) != 0 )
    {
      v11 = ExAcquireSpinLockShared((PEX_SPIN_LOCK)v8);
    }
    else
    {
      v11 = 0;
      ExAcquirePushLockSharedEx(v8, 0);
    }
    if ( (v9 & 3) == 1 )
    {
      v12 = 0;
      while ( 1 )
      {
        v13 = *(_DWORD *)(v8 + 4 * v12 + 24);
        v14 = v13 & (v9 >> *(_DWORD *)(v8 + 4 * v12 + 48));
        if ( (unsigned int)v14 > v13 )
          break;
        v15 = *(_DWORD *)(v10 + 8 * v14);
        v16 = (_DWORD **)(v10 + 8 * v14);
        v17 = v15 & 3;
        if ( v17 != 2 )
        {
          if ( v17 || **v16 != v9 )
            break;
          v18 = *(void (**)(void))(v8 + 96);
          if ( v18 )
          {
            if ( ((unsigned __int8)*v16 & 3) != 0 )
            {
              v19 = 0;
            }
            else
            {
              v18();
              v19 = *v16;
            }
            if ( (*(_BYTE *)(v8 + 88) & 0x40) != 0 )
              ExReleaseSpinLockShared((PEX_SPIN_LOCK)v8, v11);
            else
              ExReleasePushLockSharedEx(v8, 0);
          }
          else
          {
            if ( (*(_BYTE *)(v8 + 88) & 0x40) != 0 )
              ExReleaseSpinLockShared((PEX_SPIN_LOCK)v8, v11);
            else
              ExReleasePushLockSharedEx(v8, 0);
            v19 = *v16;
          }
          if ( v19 )
          {
            _InterlockedDecrement(v19 + 29);
            SrvAdminDereferenceShare(v19);
          }
          goto LABEL_24;
        }
        v12 = (unsigned int)(v12 + 1);
        v10 = (unsigned __int64)*v16 & 0xFFFFFFFFFFFFFFFCuLL;
      }
    }
    if ( (*(_BYTE *)(v8 + 88) & 0x40) != 0 )
      ExReleaseSpinLockShared((PEX_SPIN_LOCK)v8, v11);
    else
      ExReleasePushLockSharedEx(v8, 0);
LABEL_24:
    *(_QWORD *)(v6 + 72) = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 8), 0xFFFFFFFF) == 1 )
    {
      v20 = *(_QWORD *)(v6 + 128);
      if ( v20 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v20 + 24), 0xFFFFFFFF) == 1 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids, v20);
          }
          if ( *(_BYTE *)(v20 + 520) )
          {
            ExDeleteResourceLite((PERESOURCE)(v20 + 96));
            ExDeleteResourceLite((PERESOURCE)(v20 + 200));
            ExDeleteResourceLite((PERESOURCE)(v20 + 304));
            *(_BYTE *)(v20 + 520) = 0;
          }
          v25 = *(void **)(v20 + 64);
          if ( v25 )
          {
            RfsTable64Cleanup(v25);
            *(_QWORD *)(v20 + 64) = 0;
          }
          v26 = *(void **)(v20 + 72);
          if ( v26 )
          {
            RfsTableCleanup(v26);
            *(_QWORD *)(v20 + 72) = 0;
          }
          v27 = *(void **)(v20 + 80);
          if ( v27 )
          {
            RfsTable64Cleanup(v27);
            *(_QWORD *)(v20 + 80) = 0;
          }
          v28 = *(void **)(v20 + 88);
          if ( v28 )
          {
            RfsTable64Cleanup(v28);
            *(_QWORD *)(v20 + 88) = 0;
          }
          SrvNetUpdateMemStatistics(*(unsigned int *)(v20 - 12), *(unsigned int *)(v20 - 16), 0);
          ExFreePoolWithTag((PVOID)(v20 - 16), 0);
        }
        *(_QWORD *)(v6 + 128) = 0;
      }
      v21 = *(_DWORD *)(v6 + 60);
      if ( v21 == 2 )
      {
        ExFreeToPagedLookasideList(&SrvAdminPagedList256, (PVOID)v6);
        SrvNetUpdateMemStatistics(256, 256, 0);
      }
      else if ( v21 == 1 )
      {
        SrvNetUpdateMemStatistics(*(unsigned int *)(v6 - 12), *(unsigned int *)(v6 - 16), 0);
        ExFreePoolWithTag((PVOID)(v6 - 16), 0);
      }
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 24), 0xFFFFFFFF) == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids, v5);
    }
    if ( *(_BYTE *)(v5 + 520) )
    {
      ExDeleteResourceLite((PERESOURCE)(v5 + 96));
      ExDeleteResourceLite((PERESOURCE)(v5 + 200));
      ExDeleteResourceLite((PERESOURCE)(v5 + 304));
      *(_BYTE *)(v5 + 520) = 0;
    }
    v29 = *(void **)(v5 + 64);
    if ( v29 )
    {
      RfsTable64Cleanup(v29);
      *(_QWORD *)(v5 + 64) = 0;
    }
    v30 = *(void **)(v5 + 72);
    if ( v30 )
    {
      RfsTableCleanup(v30);
      *(_QWORD *)(v5 + 72) = 0;
    }
    v31 = *(void **)(v5 + 80);
    if ( v31 )
    {
      RfsTable64Cleanup(v31);
      *(_QWORD *)(v5 + 80) = 0;
    }
    v32 = *(void **)(v5 + 88);
    if ( v32 )
    {
      RfsTable64Cleanup(v32);
      *(_QWORD *)(v5 + 88) = 0;
    }
    SrvNetUpdateMemStatistics(*(unsigned int *)(v5 - 12), *(unsigned int *)(v5 - 16), 0);
    ExFreePoolWithTag((PVOID)(v5 - 16), 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140006b20  push    rbx
0x140006b22  push    rsi
0x140006b23  push    rdi
0x140006b24  sub     rsp, 80h
0x140006b2b  mov     rdi, rdx
0x140006b2e  lea     rcx, SrvAdminInstanceListLock; Resource
0x140006b35  mov     dl, 1; Wait
0x140006b37  mov     ebx, r8d
0x140006b3a  call    cs:__imp_ExAcquireResourceSharedLite
0x140006b41  nop     dword ptr [rax+rax+00h]
0x140006b46  mov     rsi, cs:SrvAdminInstanceList
0x140006b4d  lea     rcx, SrvAdminInstanceList
0x140006b54  cmp     rsi, rcx
0x140006b57  jz      loc_140006D7C
0x140006b5d  movzx   eax, byte ptr [rsi+10h]
0x140006b61  cmp     eax, ebx
0x140006b63  jnz     loc_140006D70
0x140006b69  lock inc dword ptr [rsi+18h]
0x140006b6d  lea     rcx, SrvAdminInstanceListLock; Resource
0x140006b74  call    cs:__imp_ExReleaseResourceLite
0x140006b7b  nop     dword ptr [rax+rax+00h]
0x140006b80  test    rsi, rsi
0x140006b83  jz      loc_140006D8F
0x140006b89  mov     rcx, [rsi+50h]; SpinLock
0x140006b8d  mov     rdx, rdi
0x140006b90  mov     [rsp+98h+arg_0], rbp
0x140006b98  mov     [rsp+98h+arg_10], r13
0x140006ba0  mov     [rsp+98h+var_20], r14
0x140006ba5  call    RfsTable64Remove
0x140006baa  mov     rbx, rax
0x140006bad  xor     r14d, r14d
0x140006bb0  lea     rax, WPP_GLOBAL_Control
0x140006bb7  mov     ebp, 0FFFFFFFFh
0x140006bbc  test    rbx, rbx
0x140006bbf  jz      loc_140006D32
0x140006bc5  mov     rdx, [rbx+28h]
0x140006bc9  mov     [rsp+98h+var_28], r15
0x140006bce  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140006bd2  jz      short loc_140006BDF
0x140006bd4  cmp     qword ptr [rbx+30h], 0FFFFFFFFFFFFFFFFh
0x140006bd9  jnz     loc_140006E0F
0x140006bdf  mov     rax, cs:WPP_GLOBAL_Control
0x140006be6  mov     ecx, [rax+2Ch]
0x140006be9  test    cl, 20h
0x140006bec  jnz     loc_140006E36
0x140006bf2  mov     r14, [rsi+48h]
0x140006bf6  mov     edi, [rbx+24h]
0x140006bf9  mov     rcx, r14; SpinLock
0x140006bfc  mov     [rsp+98h+arg_8], r12
0x140006c04  test    byte ptr [r14+58h], 40h
0x140006c09  mov     r15, [r14+10h]
0x140006c0d  jnz     loc_140006DB8
0x140006c13  xor     r12b, r12b
0x140006c16  xor     edx, edx
0x140006c18  call    cs:__imp_ExAcquirePushLockSharedEx
0x140006c1f  nop     dword ptr [rax+rax+00h]
0x140006c24  mov     eax, edi
0x140006c26  and     al, 3
0x140006c28  cmp     al, 1
0x140006c2a  jnz     loc_140006DDD
0x140006c30  xor     r8d, r8d
0x140006c33  mov     eax, [r14+r8*4+18h]
0x140006c38  mov     edx, edi
0x140006c3a  mov     ecx, [r14+r8*4+30h]
0x140006c3f  shr     edx, cl
0x140006c41  and     edx, eax
0x140006c43  cmp     edx, eax
0x140006c45  ja      loc_140006DDD
0x140006c4b  mov     eax, [r15+rdx*8]
0x140006c4f  lea     r15, [r15+rdx*8]
0x140006c53  and     eax, 3
0x140006c56  cmp     eax, 2
0x140006c59  jz      loc_140006E84
0x140006c5f  test    eax, eax
0x140006c61  jnz     loc_140006DDD
0x140006c67  mov     rcx, [r15]
0x140006c6a  cmp     [rcx], edi
0x140006c6c  jnz     loc_140006DDD
0x140006c72  mov     rax, [r14+60h]
0x140006c76  test    rax, rax
0x140006c79  jz      loc_140006D96
0x140006c7f  test    cl, 3
0x140006c82  jz      loc_140006D63
0x140006c88  xor     edi, edi
0x140006c8a  test    byte ptr [r14+58h], 40h
0x140006c8f  mov     rcx, r14; SpinLock
0x140006c92  jnz     loc_140006E93
0x140006c98  xor     edx, edx
0x140006c9a  call    cs:__imp_ExReleasePushLockSharedEx
0x140006ca1  nop     dword ptr [rax+rax+00h]
0x140006ca6  test    rdi, rdi
0x140006ca9  jz      short loc_140006CB7
0x140006cab  lock dec dword ptr [rdi+74h]
0x140006caf  mov     rcx, rdi
0x140006cb2  call    SrvAdminDereferenceShare
0x140006cb7  xor     r14d, r14d
0x140006cba  mov     eax, ebp
0x140006cbc  mov     [rbx+48h], r14
0x140006cc0  lock xadd [rbx+8], eax
0x140006cc5  mov     r15, [rsp+98h+var_28]
0x140006cca  mov     r12, [rsp+98h+arg_8]
0x140006cd2  cmp     eax, 1
0x140006cd5  jnz     short loc_140006D2B
0x140006cd7  mov     rdi, [rbx+80h]
0x140006cde  test    rdi, rdi
0x140006ce1  jz      short loc_140006CFA
0x140006ce3  mov     eax, ebp
0x140006ce5  lock xadd [rdi+18h], eax
0x140006cea  cmp     eax, 1
0x140006ced  jz      loc_140006EA8
0x140006cf3  mov     [rbx+80h], r14
0x140006cfa  mov     eax, [rbx+3Ch]
0x140006cfd  cmp     eax, 2
0x140006d00  jz      loc_140006EF2
0x140006d06  cmp     eax, 1
0x140006d09  jnz     short loc_140006D2B
0x140006d0b  mov     ecx, [rbx-0Ch]
0x140006d0e  xor     r8d, r8d
0x140006d11  mov     edx, [rbx-10h]
0x140006d14  call    SrvNetUpdateMemStatistics
0x140006d19  xor     edx, edx; Tag
0x140006d1b  lea     rcx, [rbx-10h]; P
0x140006d1f  call    cs:__imp_ExFreePoolWithTag
0x140006d26  nop     dword ptr [rax+rax+00h]
0x140006d2b  lea     rax, WPP_GLOBAL_Control
0x140006d32  lock xadd [rsi+18h], ebp
0x140006d37  cmp     ebp, 1
0x140006d3a  mov     rbp, [rsp+98h+arg_0]
0x140006d42  jz      loc_140006F1C
0x140006d48  mov     r14, [rsp+98h+var_20]
0x140006d4d  xor     eax, eax
0x140006d4f  mov     r13, [rsp+98h+arg_10]
0x140006d57  add     rsp, 80h
0x140006d5e  pop     rdi
0x140006d5f  pop     rsi
0x140006d60  pop     rbx
0x140006d61  retn
0x140006d63  call    _guard_dispatch_icall
0x140006d68  mov     rdi, [r15]
0x140006d6b  jmp     loc_140006C8A
0x140006d70  mov     rsi, [rsi]
0x140006d73  cmp     rsi, rcx
0x140006d76  jnz     loc_140006B5D
0x140006d7c  lea     rcx, SrvAdminInstanceListLock; Resource
0x140006d83  call    cs:__imp_ExReleaseResourceLite
0x140006d8a  nop     dword ptr [rax+rax+00h]
0x140006d8f  mov     eax, 0C0000203h
0x140006d94  jmp     short loc_140006D57
0x140006d96  test    byte ptr [r14+58h], 40h
0x140006d9b  mov     rcx, r14; SpinLock
0x140006d9e  jz      short loc_140006DCD
0x140006da0  movzx   edx, r12b; OldIrql
0x140006da4  call    cs:__imp_ExReleaseSpinLockShared
0x140006dab  nop     dword ptr [rax+rax+00h]
0x140006db0  mov     rdi, [r15]
0x140006db3  jmp     loc_140006CA6
0x140006db8  call    cs:__imp_ExAcquireSpinLockShared
0x140006dbf  nop     dword ptr [rax+rax+00h]
0x140006dc4  movzx   r12d, al
0x140006dc8  jmp     loc_140006C24
0x140006dcd  xor     edx, edx
0x140006dcf  call    cs:__imp_ExReleasePushLockSharedEx
0x140006dd6  nop     dword ptr [rax+rax+00h]
0x140006ddb  jmp     short loc_140006DB0
0x140006ddd  test    byte ptr [r14+58h], 40h
0x140006de2  mov     rcx, r14; SpinLock
0x140006de5  jz      short loc_140006DFC
0x140006de7  movzx   edx, r12b; OldIrql
0x140006deb  call    cs:__imp_ExReleaseSpinLockShared
0x140006df2  nop     dword ptr [rax+rax+00h]
0x140006df7  jmp     loc_140006CB7
0x140006dfc  xor     edx, edx
0x140006dfe  call    cs:__imp_ExReleasePushLockSharedEx
0x140006e05  nop     dword ptr [rax+rax+00h]
0x140006e0a  jmp     loc_140006CB7
0x140006e0f  mov     rcx, [rsi+40h]; SpinLock
0x140006e13  call    RfsTable64Lookup
0x140006e18  test    rax, rax
0x140006e1b  jz      loc_14002B758
0x140006e21  lock dec dword ptr [rax+98h]
0x140006e28  mov     rcx, rax
0x140006e2b  call    SrvAdminDereferenceSession
0x140006e30  nop
0x140006e31  jmp     loc_14002B758
0x140006e36  mov     eax, [rbx+24h]
0x140006e39  lea     rcx, [rbx+10h]
0x140006e3d  mov     [rsp+98h+var_38], 2
0x140006e42  xor     r8d, r8d
0x140006e45  mov     [rsp+98h+var_40], rax
0x140006e4a  xor     edx, edx
0x140006e4c  mov     rax, [rbx+30h]
0x140006e50  mov     [rsp+98h+var_48], rdi
0x140006e55  mov     [rsp+98h+var_50], rax
0x140006e5a  mov     rax, [rbx+28h]
0x140006e5e  mov     [rsp+98h+var_58], rax
0x140006e63  mov     [rsp+98h+var_60], 1
0x140006e6b  mov     [rsp+98h+var_68], r14
0x140006e70  mov     [rsp+98h+var_70], r14
0x140006e75  mov     [rsp+98h+var_78], r14
0x140006e7a  call    SATrace
0x140006e7f  jmp     loc_140006BF2
0x140006e84  mov     r15, [r15]
0x140006e87  inc     r8d
0x140006e8a  and     r15, 0FFFFFFFFFFFFFFFCh
0x140006e8e  jmp     loc_140006C33
0x140006e93  movzx   edx, r12b; OldIrql
0x140006e97  call    cs:__imp_ExReleaseSpinLockShared
0x140006e9e  nop     dword ptr [rax+rax+00h]
0x140006ea3  jmp     loc_140006CA6
0x140006ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x140006eaf  lea     rax, WPP_GLOBAL_Control
0x140006eb6  cmp     rcx, rax
0x140006eb9  jz      loc_14002B780
0x140006ebf  mov     eax, [rcx+2Ch]
0x140006ec2  test    al, 20h
0x140006ec4  jz      loc_14002B780
0x140006eca  cmp     byte ptr [rcx+29h], 2
0x140006ece  jb      loc_14002B780
0x140006ed4  mov     rcx, [rcx+18h]
0x140006ed8  lea     r8, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids
0x140006edf  mov     edx, 0Ah
0x140006ee4  mov     r9, rdi
0x140006ee7  call    WPP_SF_q
0x140006eec  nop
0x140006eed  jmp     loc_14002B780
0x140006ef2  mov     rdx, rbx; Entry
0x140006ef5  lea     rcx, SrvAdminPagedList256; Lookaside
0x140006efc  call    cs:__imp_ExFreeToPagedLookasideList
0x140006f03  nop     dword ptr [rax+rax+00h]
0x140006f08  mov     edx, 100h
0x140006f0d  xor     r8d, r8d
0x140006f10  mov     ecx, edx
0x140006f12  call    SrvNetUpdateMemStatistics
0x140006f17  jmp     loc_140006D2B
0x140006f1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140006f23  cmp     rcx, rax
0x140006f26  jz      loc_14002B83B
0x140006f2c  mov     eax, [rcx+2Ch]
0x140006f2f  test    al, 20h
0x140006f31  jz      loc_14002B83B
0x140006f37  cmp     byte ptr [rcx+29h], 2
0x140006f3b  jb      loc_14002B83B
0x140006f41  mov     rcx, [rcx+18h]
0x140006f45  lea     r8, WPP_27d13c4d37b53b1d8513b182aee48cfa_Traceguids
0x140006f4c  mov     edx, 0Ah
0x140006f51  mov     r9, rsi
0x140006f54  call    WPP_SF_q
0x140006f59  nop
0x140006f5a  jmp     loc_14002B83B
0x14002b758  mov     rdx, [rbx+30h]
0x14002b75c  mov     rcx, [rsi+58h]; SpinLock
0x14002b760  call    RfsTable64Lookup
0x14002b765  test    rax, rax
0x14002b768  jz      loc_140006BDF
0x14002b76e  lock dec dword ptr [rax+30h]
0x14002b772  mov     rcx, rax
0x14002b775  call    SrvAdminDereferenceTreeConnect
0x14002b77a  nop
0x14002b77b  jmp     loc_140006BDF
0x14002b780  cmp     [rdi+208h], r14b
0x14002b787  jz      short loc_14002B7C6
0x14002b789  lea     rcx, [rdi+60h]; Resource
0x14002b78d  call    cs:__imp_ExDeleteResourceLite
0x14002b794  nop     dword ptr [rax+rax+00h]
0x14002b799  lea     rcx, [rdi+0C8h]; Resource
0x14002b7a0  call    cs:__imp_ExDeleteResourceLite
0x14002b7a7  nop     dword ptr [rax+rax+00h]
0x14002b7ac  lea     rcx, [rdi+130h]; Resource
0x14002b7b3  call    cs:__imp_ExDeleteResourceLite
0x14002b7ba  nop     dword ptr [rax+rax+00h]
0x14002b7bf  mov     [rdi+208h], r14b
0x14002b7c6  mov     rcx, [rdi+40h]; P
0x14002b7ca  test    rcx, rcx
0x14002b7cd  jz      short loc_14002B7D8
0x14002b7cf  call    RfsTable64Cleanup
0x14002b7d4  mov     [rdi+40h], r14
0x14002b7d8  mov     rcx, [rdi+48h]; P
0x14002b7dc  test    rcx, rcx
0x14002b7df  jz      short loc_14002B7F1
0x14002b7e1  lea     rdx, SrvAdminFreeShare
0x14002b7e8  call    RfsTableCleanup
0x14002b7ed  mov     [rdi+48h], r14
0x14002b7f1  mov     rcx, [rdi+50h]; P
0x14002b7f5  test    rcx, rcx
0x14002b7f8  jz      short loc_14002B803
0x14002b7fa  call    RfsTable64Cleanup
0x14002b7ff  mov     [rdi+50h], r14
0x14002b803  mov     rcx, [rdi+58h]; P
0x14002b807  test    rcx, rcx
0x14002b80a  jz      short loc_14002B815
0x14002b80c  call    RfsTable64Cleanup
0x14002b811  mov     [rdi+58h], r14
0x14002b815  mov     ecx, [rdi-0Ch]
0x14002b818  xor     r8d, r8d
0x14002b81b  mov     edx, [rdi-10h]
0x14002b81e  call    SrvNetUpdateMemStatistics
0x14002b823  xor     edx, edx; Tag
0x14002b825  lea     rcx, [rdi-10h]; P
0x14002b829  call    cs:__imp_ExFreePoolWithTag
0x14002b830  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
