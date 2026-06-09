# SecMgrStopSecurity(MSMSEC_INTF_CONTEXT *)

- ea: `0x1800058b8`
- end: `0x180005bea`
- name: `?SecMgrStopSecurity@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z`
- size: `818`
- prototype: `unsigned int __fastcall(struct MSMSEC_INTF_CONTEXT *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180015300`

## callees

- `0x18000431c`
- `0x180004518`
- `0x1800058b8`
- `0x180005bf0`
- `0x180005dac`
- `0x180005e80`
- `0x180006344`
- `0x18000892c`
- `0x180008998`
- `0x18000b6dc`
- `0x180011030`
- `0x180014998`
- `0x180055a38`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180005997`
- `MobileNetworking!ReleaseWriteLock` at `0x180005a3a`
- `MobileNetworking!ReleaseWriteLock` at `0x180005997`
- `MobileNetworking!ReleaseWriteLock` at `0x180005a3a`
- `MobileNetworking!AcquireWriteLock` at `0x1800059d6`
- `MobileNetworking!AcquireWriteLock` at `0x1800059d6`

## string_xrefs

- `0x18000598d`: `SecMgrStopSecurity`
- `0x1800059c9`: `SecMgrStopSecurity`
- `0x180005a30`: `SecMgrStopSecurity`

## pseudocode

```c
__int64 __fastcall SecMgrStopSecurity(struct MSMSEC_INTF_CONTEXT *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // esi
  PVOID v4; // rcx
  unsigned int *v5; // rbx
  int v6; // r8d
  int v7; // r8d
  int v8; // r8d
  PVOID *v9; // rcx
  PVOID *v10; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 128, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
  v2 = SecMgrLockAndCheckAdapterDeleted(a1);
  v3 = v2;
  if ( !v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
      WPP_SF_qDDDDDD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        130,
        *((unsigned __int8 *)a1 + 2364),
        a1,
        *((unsigned __int8 *)a1 + 2360),
        *((unsigned __int8 *)a1 + 2361),
        *((unsigned __int8 *)a1 + 2362),
        *((unsigned __int8 *)a1 + 2363),
        *((unsigned __int8 *)a1 + 2364),
        *((unsigned __int8 *)a1 + 2365));
    v5 = (unsigned int *)((char *)a1 + 2496);
    if ( (byte_1800AED45 & 1) != 0 )
      McTemplateU0qj_EventWriteTransfer(v4, MsmSecSecMgrStopSecurity, *v5, (char *)a1 + 32);
    if ( (unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)a1 + 681), 3) )
    {
      StopSecurityIntfActions(a1);
      SecMgrIntfStateTransition(a1, 4, 327679);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
        WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, v6, *v5, (__int64)"<<< Unlocking <<<");
      ReleaseWriteLock(a1, (char *)a1 + 2512, "SecMgrStopSecurity", 2080);
      SecMgrMarkDeletedAndDerefAllPorts(a1, 0, v7);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
        WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, v8, *v5, (__int64)">>> Locking >>>");
      AcquireWriteLock(a1, (char *)a1 + 2512, "SecMgrStopSecurity", 2092);
      SecMgrResetIntfOnStopSecurity(a1);
      SecMgrIntfStateTransition(a1, 1, 327679);
      v5 = (unsigned int *)((char *)a1 + 2496);
    }
    else
    {
      v3 = 5023;
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_18:
        ReleaseWriteLock(a1, (char *)a1 + 2512, "SecMgrStopSecurity", 2105);
LABEL_19:
        v10 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_20;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
LABEL_15:
        if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x100) != 0 )
          WPP_SF_Ls((unsigned int)v9[7], 11, (unsigned int)"<<< Unlocking <<<", *v5, (__int64)"<<< Unlocking <<<");
        goto LABEL_18;
      }
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        131,
        &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids,
        *((unsigned int *)a1 + 681),
        3);
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_15;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 129, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v2);
    goto LABEL_19;
  }
LABEL_20:
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x100) != 0 )
    WPP_SF_d(v10[7], 132, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1800058b8  push    rbx
0x1800058ba  push    rbp
0x1800058bb  push    rsi
0x1800058bc  push    rdi
0x1800058bd  push    r14
0x1800058bf  push    r15
0x1800058c1  sub     rsp, 58h
0x1800058c5  mov     rdi, rcx
0x1800058c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058cf  lea     r14, WPP_GLOBAL_Control
0x1800058d6  mov     r15d, 100h
0x1800058dc  cmp     rcx, r14
0x1800058df  jnz     loc_180005B40
0x1800058e5  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x1800058e8  call    ?SecMgrLockAndCheckAdapterDeleted@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrLockAndCheckAdapterDeleted(MSMSEC_INTF_CONTEXT *)
0x1800058ed  mov     esi, eax
0x1800058ef  test    eax, eax
0x1800058f1  jnz     loc_180005A72
0x1800058f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058fe  cmp     rcx, r14
0x180005901  jnz     loc_180005A92
0x180005907  test    cs:byte_1800AED45, 1
0x18000590e  lea     rbx, [rdi+9C0h]
0x180005915  jz      short loc_18000592A
0x180005917  mov     r8d, [rbx]
0x18000591a  lea     r9, [rdi+20h]
0x18000591e  lea     rdx, MsmSecSecMgrStopSecurity
0x180005925  call    McTemplateU0qj_EventWriteTransfer
0x18000592a  mov     ecx, [rdi+0AA4h]
0x180005930  mov     ebp, 3
0x180005935  mov     edx, ebp
0x180005937  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x18000593c  lea     r8, aUnlocking; "<<< Unlocking <<<"
0x180005943  test    eax, eax
0x180005945  jz      loc_180005AFC
0x18000594b  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x18000594e  call    ?StopSecurityIntfActions@@YAXPEAUMSMSEC_INTF_CONTEXT@@@Z; StopSecurityIntfActions(MSMSEC_INTF_CONTEXT *)
0x180005953  xor     r9d, r9d
0x180005956  lea     edx, [rbp+1]
0x180005959  mov     r8d, 4FFFFh
0x18000595f  mov     rcx, rdi
0x180005962  call    ?SecMgrIntfStateTransition@@YAXPEAUMSMSEC_INTF_CONTEXT@@W4MSMSEC_INTF_SEC_STATE@@KK@Z; SecMgrIntfStateTransition(MSMSEC_INTF_CONTEXT *,MSMSEC_INTF_SEC_STATE,ulong,ulong)
0x180005967  mov     rcx, cs:WPP_GLOBAL_Control
0x18000596e  cmp     rcx, r14
0x180005971  jz      short loc_18000597D
0x180005973  test    [rcx+44h], r15d
0x180005977  jnz     loc_180005B8B
0x18000597d  lea     rbp, [rdi+9D0h]
0x180005984  mov     r9d, 820h
0x18000598a  mov     rdx, rbp
0x18000598d  lea     r8, aSecmgrstopsecu; "SecMgrStopSecurity"
0x180005994  mov     rcx, rdi
0x180005997  call    cs:__imp_ReleaseWriteLock
0x18000599e  nop     dword ptr [rax+rax+00h]
0x1800059a3  xor     edx, edx; int
0x1800059a5  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x1800059a8  call    ?SecMgrMarkDeletedAndDerefAllPorts@@YAKPEAUMSMSEC_INTF_CONTEXT@@H@Z; SecMgrMarkDeletedAndDerefAllPorts(MSMSEC_INTF_CONTEXT *,int)
0x1800059ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059b4  cmp     rcx, r14
0x1800059b7  jz      short loc_1800059C3
0x1800059b9  test    [rcx+44h], r15d
0x1800059bd  jnz     loc_180005BAD
0x1800059c3  mov     r9d, 82Ch
0x1800059c9  lea     r8, aSecmgrstopsecu; "SecMgrStopSecurity"
0x1800059d0  mov     rdx, rbp
0x1800059d3  mov     rcx, rdi
0x1800059d6  call    cs:__imp_AcquireWriteLock
0x1800059dd  nop     dword ptr [rax+rax+00h]
0x1800059e2  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x1800059e5  call    ?SecMgrResetIntfOnStopSecurity@@YAXPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrResetIntfOnStopSecurity(MSMSEC_INTF_CONTEXT *)
0x1800059ea  xor     r9d, r9d
0x1800059ed  mov     r8d, 4FFFFh
0x1800059f3  mov     rcx, rdi
0x1800059f6  lea     edx, [r9+1]
0x1800059fa  call    ?SecMgrIntfStateTransition@@YAXPEAUMSMSEC_INTF_CONTEXT@@W4MSMSEC_INTF_SEC_STATE@@KK@Z; SecMgrIntfStateTransition(MSMSEC_INTF_CONTEXT *,MSMSEC_INTF_SEC_STATE,ulong,ulong)
0x1800059ff  lea     rbx, [rdi+9C0h]
0x180005a06  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a0d  lea     r8, aUnlocking; "<<< Unlocking <<<"
0x180005a14  cmp     rcx, r14
0x180005a17  jz      short loc_180005A23
0x180005a19  test    [rcx+44h], r15d
0x180005a1d  jnz     loc_180005BCF
0x180005a23  lea     rdx, [rdi+9D0h]
0x180005a2a  mov     r9d, 839h
0x180005a30  lea     r8, aSecmgrstopsecu; "SecMgrStopSecurity"
0x180005a37  mov     rcx, rdi
0x180005a3a  call    cs:__imp_ReleaseWriteLock
0x180005a41  nop     dword ptr [rax+rax+00h]
0x180005a46  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a4d  cmp     rcx, r14
0x180005a50  jz      short loc_180005A82
0x180005a52  test    [rcx+44h], r15d
0x180005a56  jz      short loc_180005A82
0x180005a58  mov     rcx, [rcx+38h]
0x180005a5c  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180005a63  mov     edx, 84h
0x180005a68  mov     r9d, esi
0x180005a6b  call    WPP_SF_d
0x180005a70  jmp     short loc_180005A82
0x180005a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a79  cmp     rcx, r14
0x180005a7c  jnz     loc_180005B64
0x180005a82  mov     eax, esi
0x180005a84  add     rsp, 58h
0x180005a88  pop     r15
0x180005a8a  pop     r14
0x180005a8c  pop     rdi
0x180005a8d  pop     rsi
0x180005a8e  pop     rbp
0x180005a8f  pop     rbx
0x180005a90  retn
0x180005a92  test    byte ptr [rcx+44h], 2
0x180005a96  jz      loc_180005907
0x180005a9c  movzx   r9d, byte ptr [rdi+93Bh]
0x180005aa4  mov     edx, 82h
0x180005aa9  movzx   eax, byte ptr [rdi+93Dh]
0x180005ab0  movzx   r8d, byte ptr [rdi+93Ch]
0x180005ab8  movzx   r10d, byte ptr [rdi+93Ah]
0x180005ac0  movzx   r11d, byte ptr [rdi+939h]
0x180005ac8  movzx   ebx, byte ptr [rdi+938h]
0x180005acf  mov     rcx, [rcx+38h]
0x180005ad3  mov     [rsp+88h+var_40], eax
0x180005ad7  mov     [rsp+88h+var_48], r8d
0x180005adc  mov     [rsp+88h+var_50], r9d
0x180005ae1  mov     r9, rdi
0x180005ae4  mov     [rsp+88h+var_58], r10d
0x180005ae9  mov     [rsp+88h+var_60], r11d
0x180005aee  mov     dword ptr [rsp+88h+var_68], ebx
0x180005af2  call    WPP_SF_qDDDDDD
0x180005af7  jmp     loc_180005907
0x180005afc  mov     esi, 139Fh
0x180005b01  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b08  cmp     rcx, r14
0x180005b0b  jz      loc_180005A23
0x180005b11  test    byte ptr [rcx+44h], 1
0x180005b15  jz      loc_180005A14
0x180005b1b  mov     r9d, [rdi+0AA4h]
0x180005b22  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180005b29  mov     rcx, [rcx+38h]
0x180005b2d  mov     edx, 83h
0x180005b32  mov     dword ptr [rsp+88h+var_68], ebp
0x180005b36  call    WPP_SF_dd
0x180005b3b  jmp     loc_180005A06
0x180005b40  test    [rcx+44h], r15d
0x180005b44  jz      loc_1800058E5
0x180005b4a  mov     rcx, [rcx+38h]
0x180005b4e  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180005b55  mov     edx, 80h
0x180005b5a  call    WPP_SF_
0x180005b5f  jmp     loc_1800058E5
0x180005b64  test    byte ptr [rcx+44h], 1
0x180005b68  jz      loc_180005A4D
0x180005b6e  mov     rcx, [rcx+38h]
0x180005b72  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180005b79  mov     edx, 81h
0x180005b7e  mov     r9d, eax
0x180005b81  call    WPP_SF_d
0x180005b86  jmp     loc_180005A46
0x180005b8b  mov     r9d, [rbx]
0x180005b8e  lea     rax, aUnlocking; "<<< Unlocking <<<"
0x180005b95  mov     rcx, [rcx+38h]
0x180005b99  mov     edx, 0Bh
0x180005b9e  mov     [rsp+88h+var_68], rax
0x180005ba3  call    WPP_SF_Ls
0x180005ba8  jmp     loc_18000597D
0x180005bad  mov     r9d, [rbx]
0x180005bb0  lea     rax, aLocking; ">>> Locking >>>"
0x180005bb7  mov     rcx, [rcx+38h]
0x180005bbb  mov     edx, 0Bh
0x180005bc0  mov     [rsp+88h+var_68], rax
0x180005bc5  call    WPP_SF_Ls
0x180005bca  jmp     loc_1800059C3
0x180005bcf  mov     r9d, [rbx]
0x180005bd2  mov     edx, 0Bh
0x180005bd7  mov     rcx, [rcx+38h]
0x180005bdb  mov     [rsp+88h+var_68], r8
0x180005be0  call    WPP_SF_Ls
0x180005be5  jmp     loc_180005A23
```
