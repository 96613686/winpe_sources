# SlbNatDeleteInternalAddress

- ea: `0x1400314d4`
- end: `0x140031597`
- name: `SlbNatDeleteInternalAddress`
- size: `195`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14002e380`
- `0x140031300`

## callees

- `0x14000d678`
- `0x140013fbc`
- `0x14001ede0`
- `0x1400314d4`
- `0x140033514`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003156f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003156f`

## pseudocode

```c
void __fastcall SlbNatDeleteInternalAddress(PVOID P, __int64 a2)
{
  int v4; // r8d
  int v5; // [rsp+20h] [rbp-58h]
  _OWORD v6[2]; // [rsp+40h] [rbp-38h] BYREF

  if ( (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
  {
    memset(v6, 0, 28);
    INETADDR_SETSOCKADDR(2, (__int64)v6, (IN6_ADDR *)P + 1, 0, 0);
    if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
      McTemplateK0zqbr1q_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        (unsigned int)WINNATM_INTERNAL_ADDRESS_REMOVAL,
        v4,
        a2 + 80,
        v5,
        (__int64)v6,
        *((_DWORD *)P + 8));
  }
  SlbNatIpsRemoveInterfaceMapping(*((_DWORD *)P + 8), a2, *(_QWORD *)(a2 + 16));
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x1400314d4  mov     [rsp+arg_10], rbx
0x1400314d9  push    rdi
0x1400314da  sub     rsp, 70h
0x1400314de  mov     rax, cs:__security_cookie
0x1400314e5  xor     rax, rsp
0x1400314e8  mov     [rsp+78h+var_18], rax
0x1400314ed  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x1400314f4  mov     rdi, rdx
0x1400314f7  mov     rbx, rcx
0x1400314fa  jz      short loc_14003155E
0x1400314fc  xor     eax, eax
0x1400314fe  lea     r8, [rcx+10h]
0x140031502  xorps   xmm0, xmm0
0x140031505  mov     [rsp+78h+var_58], ax
0x14003150a  movups  [rsp+78h+var_38], xmm0
0x14003150f  xor     r9d, r9d
0x140031512  lea     rdx, [rsp+78h+var_38]
0x140031517  lea     ecx, [rax+2]
0x14003151a  movups  [rsp+78h+var_38+0Ch], xmm0
0x14003151f  call    INETADDR_SETSOCKADDR
0x140031524  cmp     cs:dword_140026104, 1
0x14003152b  jnz     short loc_14003155E
0x14003152d  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x140031534  jz      short loc_14003155E
0x140031536  mov     eax, [rbx+20h]
0x140031539  lea     r9, [rdi+50h]
0x14003153d  mov     [rsp+78h+var_48], eax
0x140031541  lea     rdx, WINNATM_INTERNAL_ADDRESS_REMOVAL
0x140031548  lea     rax, [rsp+78h+var_38]
0x14003154d  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140031554  mov     [rsp+78h+var_50], rax
0x140031559  call    McTemplateK0zqbr1q_EtwWriteTransfer
0x14003155e  mov     r8, [rdi+10h]
0x140031562  mov     ecx, [rbx+20h]
0x140031565  call    SlbNatIpsRemoveInterfaceMapping
0x14003156a  xor     edx, edx; Tag
0x14003156c  mov     rcx, rbx; P
0x14003156f  call    cs:__imp_ExFreePoolWithTag
0x140031576  nop     dword ptr [rax+rax+00h]
0x14003157b  mov     rcx, [rsp+78h+var_18]
0x140031580  xor     rcx, rsp; StackCookie
0x140031583  call    __security_check_cookie
0x140031588  mov     rbx, [rsp+78h+arg_10]
0x140031590  add     rsp, 70h
0x140031594  pop     rdi
0x140031595  retn
```
