# CRegistryLockedTransaction::HrBackupKey(HKEY__ * const,ulong)

- ea: `0x18000d294`
- end: `0x18000d434`
- name: `?HrBackupKey@CRegistryLockedTransaction@@QEAAJQEAUHKEY__@@K@Z`
- size: `416`
- prototype: `__int64 __fastcall(CRegistryLockedTransaction *this, HKEY, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007a84`

## callees

- `0x180007820`
- `0x18000aa70`
- `0x18000d294`
- `0x18000d43c`
- `0x18000d548`
- `0x18000d858`
- `0x180011fac`

## pseudocode

```c
__int64 __fastcall CRegistryLockedTransaction::HrBackupKey(CRegistryLockedTransaction *this, HKEY a2, int a3)
{
  __int64 v3; // r9
  int v7; // eax
  unsigned int v8; // esi
  int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx

  v3 = *((unsigned int *)this + 143);
  *((_DWORD *)this + 142) = 0;
  if ( (int)v3 >= 0 )
  {
    if ( !*((_DWORD *)this + 140) )
    {
      v7 = CPXWizardMutexLock::WaitForAdminLock(*(CPXWizardMutexLock **)this, (unsigned int)a2, a3);
      v8 = v7;
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_b6864e106af034a19631ace060353c02_Traceguids, 1000, v7);
        return v8;
      }
      *((_DWORD *)this + 140) = 1;
    }
    if ( !*((_DWORD *)this + 141) )
    {
      v8 = CRegistryLockedTransaction::HrSetBackupAndRestorePrivileges(this, 1);
      if ( (v8 & 0x80000000) != 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          return v8;
        v11 = 29;
LABEL_27:
        WPP_SF_D(v10[2], v11, WPP_b6864e106af034a19631ace060353c02_Traceguids, v8);
        return v8;
      }
      *((_DWORD *)this + 141) = 1;
    }
    v9 = CRegistryTransaction::HrBackupKey((CRegistryLockedTransaction *)((char *)this + 8), a2);
    v8 = v9;
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          WPP_b6864e106af034a19631ace060353c02_Traceguids,
          (unsigned int)v9);
      CRegistryLockedTransaction::HrReleaseKey(this);
    }
    else
    {
      *((_DWORD *)this + 142) = 1;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return v8;
    v11 = 31;
    goto LABEL_27;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_b6864e106af034a19631ace060353c02_Traceguids, v3);
  return *((unsigned int *)this + 143);
}

```

## disassembly

```asm
0x18000d294  mov     [rsp+arg_0], rbx
0x18000d299  mov     [rsp+arg_8], rsi
0x18000d29e  push    rdi
0x18000d29f  sub     rsp, 30h
0x18000d2a3  mov     r9d, [rcx+23Ch]
0x18000d2aa  mov     rdi, rdx
0x18000d2ad  mov     dword ptr [rcx+238h], 0
0x18000d2b7  mov     rbx, rcx
0x18000d2ba  test    r9d, r9d
0x18000d2bd  jns     short loc_18000D2F8
0x18000d2bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2c6  lea     rdi, WPP_GLOBAL_Control
0x18000d2cd  cmp     rcx, rdi
0x18000d2d0  jz      short loc_18000D2ED
0x18000d2d2  test    byte ptr [rcx+1Ch], 4
0x18000d2d6  jz      short loc_18000D2ED
0x18000d2d8  mov     rcx, [rcx+10h]
0x18000d2dc  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d2e3  mov     edx, 1Bh
0x18000d2e8  call    WPP_SF_D
0x18000d2ed  mov     eax, [rbx+23Ch]
0x18000d2f3  jmp     loc_18000D424
0x18000d2f8  cmp     dword ptr [rcx+230h], 0
0x18000d2ff  jnz     short loc_18000D319
0x18000d301  mov     rcx, [rcx]; this
0x18000d304  call    ?WaitForAdminLock@CPXWizardMutexLock@@QEAAJKH@Z; CPXWizardMutexLock::WaitForAdminLock(ulong,int)
0x18000d309  mov     esi, eax
0x18000d30b  test    eax, eax
0x18000d30d  js      short loc_18000D364
0x18000d30f  mov     dword ptr [rbx+230h], 1
0x18000d319  cmp     dword ptr [rbx+234h], 0
0x18000d320  jnz     short loc_18000D33C
0x18000d322  mov     edx, 1; int
0x18000d327  call    ?HrSetBackupAndRestorePrivileges@CRegistryLockedTransaction@@AEAAJH@Z; CRegistryLockedTransaction::HrSetBackupAndRestorePrivileges(int)
0x18000d32c  mov     esi, eax
0x18000d32e  test    eax, eax
0x18000d330  js      short loc_18000D3A6
0x18000d332  mov     dword ptr [rbx+234h], 1
0x18000d33c  lea     rcx, [rbx+8]; this
0x18000d340  mov     rdx, rdi; HKEY
0x18000d343  call    ?HrBackupKey@CRegistryTransaction@@QEAAJQEAUHKEY__@@@Z; CRegistryTransaction::HrBackupKey(HKEY__ * const)
0x18000d348  lea     rdi, WPP_GLOBAL_Control
0x18000d34f  mov     esi, eax
0x18000d351  test    eax, eax
0x18000d353  js      short loc_18000D3C6
0x18000d355  mov     dword ptr [rbx+238h], 1
0x18000d35f  jmp     loc_18000D3F8
0x18000d364  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d36b  lea     rdi, WPP_GLOBAL_Control
0x18000d372  cmp     rcx, rdi
0x18000d375  jz      loc_18000D422
0x18000d37b  test    byte ptr [rcx+1Ch], 10h
0x18000d37f  jz      loc_18000D422
0x18000d385  mov     rcx, [rcx+10h]
0x18000d389  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d390  mov     edx, 1Ch
0x18000d395  mov     [rsp+38h+var_18], esi
0x18000d399  mov     r9d, 3E8h
0x18000d39f  call    WPP_SF_DD
0x18000d3a4  jmp     short loc_18000D422
0x18000d3a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3ad  lea     rdi, WPP_GLOBAL_Control
0x18000d3b4  cmp     rcx, rdi
0x18000d3b7  jz      short loc_18000D422
0x18000d3b9  test    byte ptr [rcx+1Ch], 4
0x18000d3bd  jz      short loc_18000D422
0x18000d3bf  mov     edx, 1Dh
0x18000d3c4  jmp     short loc_18000D40F
0x18000d3c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3cd  cmp     rcx, rdi
0x18000d3d0  jz      short loc_18000D3F0
0x18000d3d2  test    byte ptr [rcx+1Ch], 4
0x18000d3d6  jz      short loc_18000D3F0
0x18000d3d8  mov     rcx, [rcx+10h]
0x18000d3dc  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d3e3  mov     edx, 1Eh
0x18000d3e8  mov     r9d, esi
0x18000d3eb  call    WPP_SF_D
0x18000d3f0  mov     rcx, rbx; this
0x18000d3f3  call    ?HrReleaseKey@CRegistryLockedTransaction@@QEAAJXZ; CRegistryLockedTransaction::HrReleaseKey(void)
0x18000d3f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3ff  cmp     rcx, rdi
0x18000d402  jz      short loc_18000D422
0x18000d404  test    byte ptr [rcx+1Ch], 10h
0x18000d408  jz      short loc_18000D422
0x18000d40a  mov     edx, 1Fh
0x18000d40f  mov     rcx, [rcx+10h]
0x18000d413  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d41a  mov     r9d, esi
0x18000d41d  call    WPP_SF_D
0x18000d422  mov     eax, esi
0x18000d424  mov     rbx, [rsp+38h+arg_0]
0x18000d429  mov     rsi, [rsp+38h+arg_8]
0x18000d42e  add     rsp, 30h
0x18000d432  pop     rdi
0x18000d433  retn
```
