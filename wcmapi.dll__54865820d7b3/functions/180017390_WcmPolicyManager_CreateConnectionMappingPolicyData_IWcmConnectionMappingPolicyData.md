# WcmPolicyManager::CreateConnectionMappingPolicyData(IWcmConnectionMappingPolicyData * *)

- ea: `0x180017390`
- end: `0x18001747b`
- name: `?CreateConnectionMappingPolicyData@WcmPolicyManager@@UEAAJPEAPEAUIWcmConnectionMappingPolicyData@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(WcmPolicyManager *__hidden this, struct IWcmConnectionMappingPolicyData **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x180008aec`
- `0x180017390`
- `0x1800197b4`
- `0x18001e010`

## string_xrefs

- `0x1800173bf`: `WcmPolicyManager::CreateConnectionMappingPolicyData`
- `0x180017453`: `WcmPolicyManager::CreateConnectionMappingPolicyData`

## pseudocode

```c
__int64 __fastcall WcmPolicyManager::CreateConnectionMappingPolicyData(
        WcmPolicyManager *this,
        struct IWcmConnectionMappingPolicyData **a2)
{
  unsigned int v3; // ebx
  WcmConnectionMappingPolicyData *v4; // rax
  WcmConnectionMappingPolicyData *v5; // rax
  WcmConnectionMappingPolicyData *v6; // rdi

  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      &WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids,
      "WcmPolicyManager::CreateConnectionMappingPolicyData");
  }
  *a2 = 0;
  v3 = -2147024882;
  v4 = (WcmConnectionMappingPolicyData *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
  {
    v5 = WcmConnectionMappingPolicyData::WcmConnectionMappingPolicyData(v4);
    v6 = v5;
    if ( v5 )
    {
      v3 = (**(__int64 (__fastcall ***)(WcmConnectionMappingPolicyData *, GUID *, struct IWcmConnectionMappingPolicyData **))v5)(
             v5,
             &GUID_1d752b6b_9deb_4846_804e_51f38ad1ba75,
             a2);
      (*(void (__fastcall **)(WcmConnectionMappingPolicyData *))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sL(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)&WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids,
      (unsigned int)"WcmPolicyManager::CreateConnectionMappingPolicyData",
      v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180017390  push    rbx
0x180017392  push    rbp
0x180017393  push    rsi
0x180017394  push    rdi
0x180017395  sub     rsp, 38h
0x180017399  mov     rsi, rdx
0x18001739c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173a3  lea     rbp, WPP_GLOBAL_Control
0x1800173aa  cmp     rcx, rbp
0x1800173ad  jz      short loc_1800173D7
0x1800173af  cmp     byte ptr [rcx+19h], 5
0x1800173b3  jb      short loc_1800173D7
0x1800173b5  test    byte ptr [rcx+1Ch], 1
0x1800173b9  jz      short loc_1800173D7
0x1800173bb  mov     rcx, [rcx+10h]
0x1800173bf  lea     r9, aWcmpolicymanag_2; "WcmPolicyManager::CreateConnectionMappi"...
0x1800173c6  mov     edx, 0Ch
0x1800173cb  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x1800173d2  call    WPP_SF_s
0x1800173d7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800173de  mov     qword ptr [rsi], 0
0x1800173e5  mov     ecx, 60h ; '`'; unsigned __int64
0x1800173ea  mov     ebx, 8007000Eh
0x1800173ef  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800173f4  mov     [rsp+58h+arg_8], rax
0x1800173f9  test    rax, rax
0x1800173fc  jz      short loc_180017437
0x1800173fe  mov     rcx, rax; this
0x180017401  call    ??0WcmConnectionMappingPolicyData@@QEAA@XZ; WcmConnectionMappingPolicyData::WcmConnectionMappingPolicyData(void)
0x180017406  mov     rdi, rax
0x180017409  test    rax, rax
0x18001740c  jz      short loc_180017437
0x18001740e  mov     rax, [rax]
0x180017411  lea     rdx, _GUID_1d752b6b_9deb_4846_804e_51f38ad1ba75
0x180017418  mov     r8, rsi
0x18001741b  mov     rcx, rdi
0x18001741e  mov     rax, [rax]
0x180017421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017426  mov     rcx, [rdi]
0x180017429  mov     ebx, eax
0x18001742b  mov     rax, [rcx+10h]
0x18001742f  mov     rcx, rdi
0x180017432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017437  mov     rcx, cs:WPP_GLOBAL_Control
0x18001743e  cmp     rcx, rbp
0x180017441  jz      short loc_18001746F
0x180017443  cmp     byte ptr [rcx+19h], 5
0x180017447  jb      short loc_18001746F
0x180017449  test    byte ptr [rcx+1Ch], 1
0x18001744d  jz      short loc_18001746F
0x18001744f  mov     rcx, [rcx+10h]
0x180017453  lea     r9, aWcmpolicymanag_2; "WcmPolicyManager::CreateConnectionMappi"...
0x18001745a  mov     edx, 0Dh
0x18001745f  mov     [rsp+58h+var_38], ebx
0x180017463  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x18001746a  call    WPP_SF_sL
0x18001746f  mov     eax, ebx
0x180017471  add     rsp, 38h
0x180017475  pop     rdi
0x180017476  pop     rsi
0x180017477  pop     rbp
0x180017478  pop     rbx
0x180017479  retn
```
