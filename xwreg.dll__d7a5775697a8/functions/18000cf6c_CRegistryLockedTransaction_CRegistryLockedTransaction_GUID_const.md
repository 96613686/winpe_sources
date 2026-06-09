# CRegistryLockedTransaction::CRegistryLockedTransaction(_GUID const *)

- ea: `0x18000cf6c`
- end: `0x18000d067`
- name: `??0CRegistryLockedTransaction@@QEAA@PEBU_GUID@@@Z`
- size: `251`
- prototype: `CRegistryLockedTransaction *(CRegistryLockedTransaction *__hidden this, const struct _GUID *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180007860`
- `0x18000af74`
- `0x18000c428`

## callees

- `0x1800011dc`
- `0x180007820`
- `0x18000cf6c`
- `0x18000d070`
- `0x180011c8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CRegistryLockedTransaction *__fastcall CRegistryLockedTransaction::CRegistryLockedTransaction(
        CRegistryLockedTransaction *this,
        struct _GUID *a2)
{
  CRegistryLockedTransaction *v3; // rbx
  _DWORD *v4; // rsi
  CPXWizardMutexLock *v5; // rax
  CPXWizardMutexLock *v6; // rax
  PVOID *v7; // rcx
  _DWORD *v11; // [rsp+50h] [rbp+18h]

  v3 = this;
  CRegistryTransaction::CRegistryTransaction((CRegistryLockedTransaction *)((char *)this + 8));
  try
  {
    v4 = (_DWORD *)((char *)v3 + 572);
    v11 = (_DWORD *)((char *)v3 + 572);
    *((_DWORD *)v3 + 143) = 0;
    *((_QWORD *)v3 + 70) = 0;
    *((_DWORD *)v3 + 142) = 0;
    *(_QWORD *)v3 = 0;
    v5 = (CPXWizardMutexLock *)operator new(0x18u);
    if ( v5 )
      v6 = CPXWizardMutexLock::CPXWizardMutexLock(v5, L"$XW_RL_", a2);
    else
      v6 = 0;
    *(_QWORD *)v3 = v6;
  }
  catch ( ... )
  {
    v3 = this;
    v4 = v11;
  }
  if ( *(_QWORD *)v3 )
    goto LABEL_10;
  *v4 = -2147024882;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b6864e106af034a19631ace060353c02_Traceguids, 2147942414LL);
LABEL_10:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
    WPP_SF_D(v7[2], 20, WPP_b6864e106af034a19631ace060353c02_Traceguids, (unsigned int)*v4);
  return v3;
}

```

## disassembly

```asm
0x18000cf6c  mov     [rsp+arg_8], rbx
0x18000cf71  mov     [rsp+arg_0], rcx
0x18000cf76  push    rsi
0x18000cf77  push    rdi
0x18000cf78  push    r14
0x18000cf7a  sub     rsp, 20h
0x18000cf7e  mov     r14, rdx
0x18000cf81  mov     rbx, rcx
0x18000cf84  add     rcx, 8; this
0x18000cf88  call    ??0CRegistryTransaction@@QEAA@XZ; CRegistryTransaction::CRegistryTransaction(void)
0x18000cf8d  nop
0x18000cf8e  lea     rsi, [rbx+23Ch]
0x18000cf95  mov     [rsp+38h+arg_10], rsi
0x18000cf9a  xor     edi, edi
0x18000cf9c  mov     [rsi], edi
0x18000cf9e  mov     [rbx+230h], rdi
0x18000cfa5  mov     [rbx+238h], edi
0x18000cfab  mov     [rbx], rdi
0x18000cfae  lea     ecx, [rdi+18h]; Size
0x18000cfb1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cfb6  test    rax, rax
0x18000cfb9  jz      short loc_18000CFCF
0x18000cfbb  mov     r8, r14; rguid
0x18000cfbe  lea     rdx, aXwRl; "$XW_RL_"
0x18000cfc5  mov     rcx, rax; this
0x18000cfc8  call    ??0CPXWizardMutexLock@@QEAA@QEAGPEBU_GUID@@@Z; CPXWizardMutexLock::CPXWizardMutexLock(ushort * const,_GUID const *)
0x18000cfcd  jmp     short loc_18000CFD2
0x18000cfcf  mov     rax, rdi
0x18000cfd2  mov     [rbx], rax
0x18000cfd5  jmp     short loc_18000CFE3
0x18000cfd7  xor     edi, edi
0x18000cfd9  mov     rbx, [rsp+38h+arg_0]
0x18000cfde  mov     rsi, [rsp+38h+arg_10]
0x18000cfe3  cmp     [rbx], rdi
0x18000cfe6  jnz     short loc_18000D024
0x18000cfe8  mov     dword ptr [rsi], 8007000Eh
0x18000cfee  lea     rdi, WPP_GLOBAL_Control
0x18000cff5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cffc  cmp     rcx, rdi
0x18000cfff  jz      short loc_18000D056
0x18000d001  test    byte ptr [rcx+1Ch], 4
0x18000d005  jz      short loc_18000D032
0x18000d007  mov     edx, 13h
0x18000d00c  mov     r9d, 8007000Eh
0x18000d012  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d019  mov     rcx, [rcx+10h]
0x18000d01d  call    WPP_SF_D
0x18000d022  jmp     short loc_18000D02B
0x18000d024  lea     rdi, WPP_GLOBAL_Control
0x18000d02b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d032  cmp     rcx, rdi
0x18000d035  jz      short loc_18000D056
0x18000d037  test    byte ptr [rcx+1Ch], 10h
0x18000d03b  jz      short loc_18000D056
0x18000d03d  mov     edx, 14h
0x18000d042  mov     r9d, [rsi]
0x18000d045  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d04c  mov     rcx, [rcx+10h]
0x18000d050  call    WPP_SF_D
0x18000d055  nop
0x18000d056  mov     rax, rbx
0x18000d059  mov     rbx, [rsp+38h+arg_8]
0x18000d05e  add     rsp, 20h
0x18000d062  pop     r14
0x18000d064  pop     rdi
0x18000d065  pop     rsi
0x18000d066  retn
```
