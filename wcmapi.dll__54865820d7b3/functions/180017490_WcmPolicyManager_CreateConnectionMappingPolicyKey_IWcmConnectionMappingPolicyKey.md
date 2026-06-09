# WcmPolicyManager::CreateConnectionMappingPolicyKey(IWcmConnectionMappingPolicyKey * *)

- ea: `0x180017490`
- end: `0x18001757f`
- name: `?CreateConnectionMappingPolicyKey@WcmPolicyManager@@UEAAJPEAPEAUIWcmConnectionMappingPolicyKey@@@Z`
- size: `239`
- prototype: `__int64 __fastcall(WcmPolicyManager *__hidden this, struct IWcmConnectionMappingPolicyKey **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x180008aec`
- `0x180017490`
- `0x180018594`
- `0x18001e010`

## string_xrefs

- `0x1800174c0`: `WcmPolicyManager::CreateConnectionMappingPolicyKey`
- `0x18001755c`: `WcmPolicyManager::CreateConnectionMappingPolicyKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WcmPolicyManager::CreateConnectionMappingPolicyKey(
        WcmPolicyManager *this,
        struct IWcmConnectionMappingPolicyKey **a2)
{
  unsigned int v3; // edi
  WcmConnectionMappingPolicyKey *v4; // rax
  WcmConnectionMappingPolicyKey *v5; // rbx

  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids,
      "WcmPolicyManager::CreateConnectionMappingPolicyKey");
  }
  v3 = -2147024882;
  *a2 = 0;
  v4 = (WcmConnectionMappingPolicyKey *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
    v5 = WcmConnectionMappingPolicyKey::WcmConnectionMappingPolicyKey(v4);
  else
    v5 = 0;
  if ( v5 )
  {
    v3 = (**(__int64 (__fastcall ***)(WcmConnectionMappingPolicyKey *, GUID *, struct IWcmConnectionMappingPolicyKey **))v5)(
           v5,
           &GUID_5eb9f8cb_c6f9_4d24_9a2c_c36709f89e28,
           a2);
    (*(void (__fastcall **)(WcmConnectionMappingPolicyKey *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sL(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)&WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids,
      (unsigned int)"WcmPolicyManager::CreateConnectionMappingPolicyKey",
      v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180017490  push    rbx
0x180017492  push    rbp
0x180017493  push    rsi
0x180017494  push    rdi
0x180017495  sub     rsp, 38h
0x180017499  mov     rsi, rdx
0x18001749c  lea     rbp, WPP_GLOBAL_Control
0x1800174a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800174aa  cmp     rcx, rbp
0x1800174ad  jz      short loc_1800174D7
0x1800174af  cmp     byte ptr [rcx+19h], 5
0x1800174b3  jb      short loc_1800174D7
0x1800174b5  test    byte ptr [rcx+1Ch], 1
0x1800174b9  jz      short loc_1800174D7
0x1800174bb  mov     edx, 0Ah
0x1800174c0  lea     r9, aWcmpolicymanag_0; "WcmPolicyManager::CreateConnectionMappi"...
0x1800174c7  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x1800174ce  mov     rcx, [rcx+10h]
0x1800174d2  call    WPP_SF_s
0x1800174d7  mov     edi, 8007000Eh
0x1800174dc  mov     qword ptr [rsi], 0
0x1800174e3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800174ea  mov     ecx, 70h ; 'p'; unsigned __int64
0x1800174ef  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800174f4  mov     [rsp+58h+arg_8], rax
0x1800174f9  test    rax, rax
0x1800174fc  jz      short loc_18001750B
0x1800174fe  mov     rcx, rax; this
0x180017501  call    ??0WcmConnectionMappingPolicyKey@@QEAA@XZ; WcmConnectionMappingPolicyKey::WcmConnectionMappingPolicyKey(void)
0x180017506  mov     rbx, rax
0x180017509  jmp     short loc_18001750D
0x18001750b  xor     ebx, ebx
0x18001750d  test    rbx, rbx
0x180017510  jz      short loc_18001753B
0x180017512  mov     rax, [rbx]
0x180017515  mov     r8, rsi
0x180017518  lea     rdx, _GUID_5eb9f8cb_c6f9_4d24_9a2c_c36709f89e28
0x18001751f  mov     rcx, rbx
0x180017522  mov     rax, [rax]
0x180017525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001752a  mov     edi, eax
0x18001752c  mov     rcx, [rbx]
0x18001752f  mov     rax, [rcx+10h]
0x180017533  mov     rcx, rbx
0x180017536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001753b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017542  cmp     rcx, rbp
0x180017545  jz      short loc_180017573
0x180017547  cmp     byte ptr [rcx+19h], 5
0x18001754b  jb      short loc_180017573
0x18001754d  test    byte ptr [rcx+1Ch], 1
0x180017551  jz      short loc_180017573
0x180017553  mov     edx, 0Bh
0x180017558  mov     [rsp+58h+var_38], edi
0x18001755c  lea     r9, aWcmpolicymanag_0; "WcmPolicyManager::CreateConnectionMappi"...
0x180017563  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x18001756a  mov     rcx, [rcx+10h]
0x18001756e  call    WPP_SF_sL
0x180017573  mov     eax, edi
0x180017575  add     rsp, 38h
0x180017579  pop     rdi
0x18001757a  pop     rsi
0x18001757b  pop     rbp
0x18001757c  pop     rbx
0x18001757d  retn
```
