# WinHvSetSint2

- ea: `0x140006450`
- end: `0x140006558`
- name: `WinHvSetSint2`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140006410`

## callees

- `0x140006450`
- `0x140006590`
- `0x140009c50`

## import_xrefs

- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400064f0`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400064f0`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140006523`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140006523`
- `ntoskrnl!KeQueryGroupAffinity` at `0x14000649e`
- `ntoskrnl!KeQueryGroupAffinity` at `0x14000649e`

## pseudocode

```c
__int64 __fastcall WinHvSetSint2(unsigned int a1, unsigned int a2, __int64 a3, unsigned int a4)
{
  USHORT v5; // cx
  KAFFINITY v9; // rdi
  WORD v11; // ax
  struct _GROUP_AFFINITY *p_PreviousAffinity; // rbp
  char v13; // si
  __int64 v15; // rcx
  int v16; // ebx
  _GROUP_AFFINITY Affinity; // [rsp+28h] [rbp-50h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+38h] [rbp-40h] BYREF

  v5 = *(_WORD *)(a3 + 8);
  Affinity = 0;
  PreviousAffinity = 0;
  v9 = *(_QWORD *)a3 & KeQueryGroupAffinity(v5);
  if ( !v9 )
    return 0;
  v11 = *(_WORD *)(a3 + 8);
  p_PreviousAffinity = &PreviousAffinity;
  v13 = 0;
  Affinity = 0;
  Affinity.Group = v11;
  while ( _BitScanForward64((unsigned __int64 *)&v15, v9) )
  {
    v9 &= ~(1LL << v15);
    Affinity.Mask = 1LL << v15;
    KeSetSystemGroupAffinityThread(&Affinity, p_PreviousAffinity);
    v13 = 1;
    p_PreviousAffinity = 0;
    v16 = WinHvSetSintOnCurrentProcessor2(a1, a2, a4);
    if ( v16 < 0 )
      goto LABEL_8;
  }
  v16 = 0;
  if ( !v13 )
    return (unsigned int)v16;
LABEL_8:
  KeRevertToUserGroupAffinityThread(&PreviousAffinity);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140006450  mov     [rsp+arg_8], rbx
0x140006455  mov     [rsp+arg_18], rbp
0x14000645a  push    rsi
0x14000645b  push    rdi
0x14000645c  push    r12
0x14000645e  push    r14
0x140006460  push    r15
0x140006462  sub     rsp, 50h
0x140006466  mov     rax, cs:__security_cookie
0x14000646d  xor     rax, rsp
0x140006470  mov     [rsp+78h+var_30], rax
0x140006475  mov     r12d, ecx
0x140006478  mov     [rsp+78h+var_58], 0
0x140006480  movzx   ecx, word ptr [r8+8]; GroupNumber
0x140006485  xorps   xmm0, xmm0
0x140006488  xorps   xmm1, xmm1
0x14000648b  mov     r14d, r9d
0x14000648e  movups  xmmword ptr [rsp+78h+Affinity.Mask], xmm0
0x140006493  mov     rbx, r8
0x140006496  mov     r15d, edx
0x140006499  movups  xmmword ptr [rsp+78h+PreviousAffinity.Mask], xmm1
0x14000649e  call    cs:__imp_KeQueryGroupAffinity
0x1400064a5  nop     dword ptr [rax+rax+00h]
0x1400064aa  mov     rdi, rax
0x1400064ad  and     rdi, [rbx]
0x1400064b0  jnz     short loc_1400064B6
0x1400064b2  xor     eax, eax
0x1400064b4  jmp     short loc_140006531
0x1400064b6  movzx   eax, word ptr [rbx+8]
0x1400064ba  lea     rbp, [rsp+78h+PreviousAffinity]
0x1400064bf  xorps   xmm0, xmm0
0x1400064c2  xor     sil, sil
0x1400064c5  movups  xmmword ptr [rsp+78h+Affinity.Mask], xmm0
0x1400064ca  mov     [rsp+78h+Affinity.Group], ax
0x1400064cf  bsf     rcx, rdi
0x1400064d3  jz      short loc_140006517
0x1400064d5  mov     eax, ecx
0x1400064d7  mov     rdx, rbp; PreviousAffinity
0x1400064da  btr     rdi, rax
0x1400064de  mov     eax, 1
0x1400064e3  shl     rax, cl
0x1400064e6  lea     rcx, [rsp+78h+Affinity]; Affinity
0x1400064eb  mov     [rsp+78h+Affinity.Mask], rax
0x1400064f0  call    cs:__imp_KeSetSystemGroupAffinityThread
0x1400064f7  nop     dword ptr [rax+rax+00h]
0x1400064fc  mov     r8d, r14d
0x1400064ff  mov     edx, r15d
0x140006502  mov     ecx, r12d
0x140006505  mov     sil, 1
0x140006508  xor     ebp, ebp
0x14000650a  call    WinHvSetSintOnCurrentProcessor2
0x14000650f  mov     ebx, eax
0x140006511  test    eax, eax
0x140006513  jns     short loc_1400064CF
0x140006515  jmp     short loc_14000651E
0x140006517  xor     ebx, ebx
0x140006519  test    sil, sil
0x14000651c  jz      short loc_14000652F
0x14000651e  lea     rcx, [rsp+78h+PreviousAffinity]; PreviousAffinity
0x140006523  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x14000652a  nop     dword ptr [rax+rax+00h]
0x14000652f  mov     eax, ebx
0x140006531  mov     rcx, [rsp+78h+var_30]
0x140006536  xor     rcx, rsp; StackCookie
0x140006539  call    __security_check_cookie
0x14000653e  lea     r11, [rsp+78h+var_28]
0x140006543  mov     rbx, [r11+38h]
0x140006547  mov     rbp, [r11+48h]
0x14000654b  mov     rsp, r11
0x14000654e  pop     r15
0x140006550  pop     r14
0x140006552  pop     r12
0x140006554  pop     rdi
0x140006555  pop     rsi
0x140006556  retn
```
