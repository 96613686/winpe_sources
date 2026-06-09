# CRegistryLockedTransaction::HrReleaseKey(void)

- ea: `0x18000d548`
- end: `0x18000d686`
- name: `?HrReleaseKey@CRegistryLockedTransaction@@QEAAJXZ`
- size: `318`
- prototype: `__int64 __fastcall(CRegistryLockedTransaction *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800095a0`
- `0x18000d1ec`
- `0x18000d294`

## callees

- `0x180007820`
- `0x18000d548`
- `0x18000d858`
- `0x180011ecc`

## pseudocode

```c
__int64 __fastcall CRegistryLockedTransaction::HrReleaseKey(CRegistryLockedTransaction *this)
{
  __int64 v1; // r9
  unsigned int v4; // edi
  int v5; // eax
  int v6; // eax

  v1 = *((unsigned int *)this + 143);
  if ( (int)v1 >= 0 )
  {
    v4 = 0;
    if ( *((_DWORD *)this + 141) )
    {
      v5 = CRegistryLockedTransaction::HrSetBackupAndRestorePrivileges(this, 0);
      v4 = v5;
      if ( v5 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            WPP_b6864e106af034a19631ace060353c02_Traceguids,
            (unsigned int)v5);
      }
      else
      {
        *((_DWORD *)this + 141) = 0;
      }
    }
    if ( *((_DWORD *)this + 140) )
    {
      v6 = CPXWizardMutexLock::ReleaseLock(*(CPXWizardMutexLock **)this);
      v4 = v6;
      if ( v6 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            37,
            WPP_b6864e106af034a19631ace060353c02_Traceguids,
            (unsigned int)v6);
      }
      else
      {
        *((_DWORD *)this + 140) = 0;
      }
    }
    *((_DWORD *)this + 142) = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_b6864e106af034a19631ace060353c02_Traceguids, v4);
    return v4;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_b6864e106af034a19631ace060353c02_Traceguids, v1);
    return *((unsigned int *)this + 143);
  }
}

```

## disassembly

```asm
0x18000d548  mov     [rsp+arg_0], rbx
0x18000d54d  mov     [rsp+arg_8], rsi
0x18000d552  push    rdi
0x18000d553  sub     rsp, 20h
0x18000d557  mov     r9d, [rcx+23Ch]
0x18000d55e  mov     rbx, rcx
0x18000d561  test    r9d, r9d
0x18000d564  jns     short loc_18000D59F
0x18000d566  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d56d  lea     rsi, WPP_GLOBAL_Control
0x18000d574  cmp     rcx, rsi
0x18000d577  jz      short loc_18000D594
0x18000d579  test    byte ptr [rcx+1Ch], 4
0x18000d57d  jz      short loc_18000D594
0x18000d57f  mov     rcx, [rcx+10h]
0x18000d583  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d58a  mov     edx, 23h ; '#'
0x18000d58f  call    WPP_SF_D
0x18000d594  mov     eax, [rbx+23Ch]
0x18000d59a  jmp     loc_18000D676
0x18000d59f  xor     edi, edi
0x18000d5a1  lea     rsi, WPP_GLOBAL_Control
0x18000d5a8  cmp     [rcx+234h], edi
0x18000d5ae  jz      short loc_18000D5F3
0x18000d5b0  xor     edx, edx; int
0x18000d5b2  call    ?HrSetBackupAndRestorePrivileges@CRegistryLockedTransaction@@AEAAJH@Z; CRegistryLockedTransaction::HrSetBackupAndRestorePrivileges(int)
0x18000d5b7  mov     edi, eax
0x18000d5b9  test    eax, eax
0x18000d5bb  js      short loc_18000D5C9
0x18000d5bd  mov     dword ptr [rbx+234h], 0
0x18000d5c7  jmp     short loc_18000D5F3
0x18000d5c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5d0  cmp     rcx, rsi
0x18000d5d3  jz      short loc_18000D5F3
0x18000d5d5  test    byte ptr [rcx+1Ch], 4
0x18000d5d9  jz      short loc_18000D5F3
0x18000d5db  mov     rcx, [rcx+10h]
0x18000d5df  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d5e6  mov     edx, 24h ; '$'
0x18000d5eb  mov     r9d, eax
0x18000d5ee  call    WPP_SF_D
0x18000d5f3  cmp     dword ptr [rbx+230h], 0
0x18000d5fa  jz      short loc_18000D640
0x18000d5fc  mov     rcx, [rbx]; this
0x18000d5ff  call    ?ReleaseLock@CPXWizardMutexLock@@QEAAJXZ; CPXWizardMutexLock::ReleaseLock(void)
0x18000d604  mov     edi, eax
0x18000d606  test    eax, eax
0x18000d608  js      short loc_18000D616
0x18000d60a  mov     dword ptr [rbx+230h], 0
0x18000d614  jmp     short loc_18000D640
0x18000d616  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d61d  cmp     rcx, rsi
0x18000d620  jz      short loc_18000D640
0x18000d622  test    byte ptr [rcx+1Ch], 4
0x18000d626  jz      short loc_18000D640
0x18000d628  mov     rcx, [rcx+10h]
0x18000d62c  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d633  mov     edx, 25h ; '%'
0x18000d638  mov     r9d, eax
0x18000d63b  call    WPP_SF_D
0x18000d640  mov     dword ptr [rbx+238h], 0
0x18000d64a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d651  cmp     rcx, rsi
0x18000d654  jz      short loc_18000D674
0x18000d656  test    byte ptr [rcx+1Ch], 10h
0x18000d65a  jz      short loc_18000D674
0x18000d65c  mov     rcx, [rcx+10h]
0x18000d660  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d667  mov     edx, 26h ; '&'
0x18000d66c  mov     r9d, edi
0x18000d66f  call    WPP_SF_D
0x18000d674  mov     eax, edi
0x18000d676  mov     rbx, [rsp+28h+arg_0]
0x18000d67b  mov     rsi, [rsp+28h+arg_8]
0x18000d680  add     rsp, 20h
0x18000d684  pop     rdi
0x18000d685  retn
```
