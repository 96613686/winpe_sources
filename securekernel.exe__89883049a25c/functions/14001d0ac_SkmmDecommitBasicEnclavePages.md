# SkmmDecommitBasicEnclavePages

- ea: `0x14001d0ac`
- end: `0x14001d307`
- name: `SkmmDecommitBasicEnclavePages`
- size: `603`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140021428`

## callees

- `0x140001d70`
- `0x14000f8b0`
- `0x14001d0ac`
- `0x14001d414`
- `0x14001df2c`
- `0x14001e4d8`
- `0x14001f020`
- `0x140020194`
- `0x140095cd8`
- `0x1400b0014`
- `0x1400ee8b0`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmmDecommitBasicEnclavePages(unsigned __int64 a1, unsigned __int64 a2)
{
  _QWORD *StackBase; // rbx
  __int64 v5; // rbx
  int v6; // edx
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // r14
  _QWORD *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // r15
  __int64 v12; // r12
  unsigned int v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // r8
  __int64 v18; // [rsp+38h] [rbp-C0h] BYREF
  _BYTE v19[2]; // [rsp+40h] [rbp-B8h] BYREF
  __int16 v20; // [rsp+42h] [rbp-B6h]
  __int64 v21; // [rsp+48h] [rbp-B0h]
  unsigned __int64 v22; // [rsp+58h] [rbp-A0h]
  unsigned __int64 v23; // [rsp+60h] [rbp-98h]
  int v24; // [rsp+68h] [rbp-90h]

  v18 = 0;
  memset_0(v19, 0, 0x68u);
  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
    v5 = StackBase[10];
  else
    v5 = 0;
  if ( (a1 & 0xFFF) != 0 || (a2 & 0xFFF) != 0 )
    return 3221225485LL;
  v6 = *(_DWORD *)(v5 + 568);
  v7 = a1 >> 12;
  if ( a1 >> 12 < (*(unsigned int *)(v5 + 560) | ((unsigned __int64)(v6 & 0xFFF) << 32)) )
    return 3221225496LL;
  v8 = v7 + (a2 >> 12) - 1;
  if ( v8 < v7 || v8 > (*(unsigned int *)(v5 + 564) | ((unsigned __int64)(v6 & 0xFFF000) << 20)) )
    return 3221225496LL;
  v9 = KeGetPcr()->NtTib.StackBase;
  if ( v9 )
  {
    v10 = v9[18];
    if ( v10 )
      --*(_WORD *)(v10 + xmmword_140167150);
  }
  v11 = v5 + 256;
  RtlAcquireSRWLockShared(v5 + 256);
  v12 = v5 + 536;
  SkmiLockVad(v5 + 536);
  if ( (unsigned __int8)SkpsBasicEnclaveThreadInRange(v5, a1, a1 + a2 - 1) )
  {
    v13 = -1073741780;
  }
  else
  {
    SkmiInvalidateVirtualPageRange(v5, 0, a1 >> 12, v7 + (a2 >> 12) - 1, 1, (__int64)&v18);
    SkmiFreeVirtualPageTables(v5, a1 >> 12, v7 + (a2 >> 12) - 1, 1);
    SkmiReturnCommitment(v5, v18);
    memset_0(v19, 0, 0x68u);
    v22 = a1;
    v20 = 13;
    v23 = a2;
    v21 = *(_QWORD *)(v5 + 48);
    v24 = 0x4000;
    SkCallNormalMode(v19);
    v13 = 0;
  }
  SkmiUnlockVad(v12);
  RtlReleaseSRWLockShared(v11);
  v14 = KeGetPcr()->NtTib.StackBase;
  if ( v14 )
  {
    v15 = v14[18];
    if ( v15 )
    {
      if ( (*(_WORD *)(v15 + xmmword_140167150))++ == 0xFFFF
        && *(_QWORD *)(v15 + xmmword_140167160) != (_QWORD)xmmword_140167160 + v14[17]
        && !*(_WORD *)(v15 + *((_QWORD *)&xmmword_140167150 + 1)) )
      {
        SkiCheckForKernelApcDelivery();
      }
    }
  }
  return v13;
}

```

## disassembly

```asm
0x14001d0ac  mov     [rsp+arg_10], rbx
0x14001d0b1  push    rbp
0x14001d0b2  push    rsi
0x14001d0b3  push    rdi
0x14001d0b4  push    r12
0x14001d0b6  push    r13
0x14001d0b8  push    r14
0x14001d0ba  push    r15
0x14001d0bc  sub     rsp, 0C0h
0x14001d0c3  mov     rax, cs:__security_cookie
0x14001d0ca  xor     rax, rsp
0x14001d0cd  mov     [rsp+0F8h+var_48], rax
0x14001d0d5  xor     r13d, r13d
0x14001d0d8  mov     rbp, rdx
0x14001d0db  mov     rsi, rcx
0x14001d0de  mov     [rsp+0F8h+var_C0], r13
0x14001d0e3  xor     edx, edx; Val
0x14001d0e5  lea     rcx, [rsp+0F8h+var_B8]; void *
0x14001d0ea  lea     r8d, [r13+68h]; Size
0x14001d0ee  call    memset_0
0x14001d0f3  mov     rbx, gs:8
0x14001d0fc  test    rbx, rbx
0x14001d0ff  jz      short loc_14001D107
0x14001d101  mov     rbx, [rbx+50h]
0x14001d105  jmp     short loc_14001D10A
0x14001d107  mov     rbx, r13
0x14001d10a  mov     eax, 0FFFh
0x14001d10f  test    eax, esi
0x14001d111  jnz     loc_14001D2D6
0x14001d117  test    eax, ebp
0x14001d119  jnz     loc_14001D2D6
0x14001d11f  mov     edx, [rbx+238h]
0x14001d125  mov     rdi, rsi
0x14001d128  mov     ecx, edx
0x14001d12a  shr     rdi, 0Ch
0x14001d12e  and     rcx, rax
0x14001d131  mov     eax, [rbx+230h]
0x14001d137  shl     rcx, 20h
0x14001d13b  or      rcx, rax
0x14001d13e  cmp     rdi, rcx
0x14001d141  jb      loc_14001D2CF
0x14001d147  mov     r14, rbp
0x14001d14a  shr     r14, 0Ch
0x14001d14e  dec     r14
0x14001d151  add     r14, rdi
0x14001d154  cmp     r14, rdi
0x14001d157  jb      loc_14001D2CF
0x14001d15d  mov     eax, [rbx+234h]
0x14001d163  and     edx, 0FFF000h
0x14001d169  shl     rdx, 14h
0x14001d16d  or      rdx, rax
0x14001d170  cmp     r14, rdx
0x14001d173  ja      loc_14001D2CF
0x14001d179  mov     rcx, gs:8
0x14001d182  test    rcx, rcx
0x14001d185  jz      short loc_14001D19F
0x14001d187  mov     rcx, [rcx+90h]
0x14001d18e  test    rcx, rcx
0x14001d191  jz      short loc_14001D19F
0x14001d193  mov     rax, qword ptr cs:xmmword_140167150
0x14001d19a  dec     word ptr [rcx+rax]
0x14001d19e  nop
0x14001d19f  lea     r15, [rbx+100h]
0x14001d1a6  mov     rcx, r15
0x14001d1a9  call    RtlAcquireSRWLockShared
0x14001d1ae  lea     r12, [rbx+218h]
0x14001d1b5  mov     rcx, r12
0x14001d1b8  call    SkmiLockVad
0x14001d1bd  lea     r8, [rbp-1]
0x14001d1c1  mov     rdx, rsi
0x14001d1c4  add     r8, rsi
0x14001d1c7  mov     rcx, rbx
0x14001d1ca  call    SkpsBasicEnclaveThreadInRange
0x14001d1cf  test    al, al
0x14001d1d1  jz      short loc_14001D1DD
0x14001d1d3  mov     ebx, 0C000002Ch
0x14001d1d8  jmp     loc_14001D262
0x14001d1dd  lea     rax, [rsp+0F8h+var_C0]
0x14001d1e2  mov     r9, r14
0x14001d1e5  mov     [rsp+0F8h+var_D0], rax
0x14001d1ea  mov     r8, rdi
0x14001d1ed  xor     edx, edx
0x14001d1ef  mov     [rsp+0F8h+var_D8], 1
0x14001d1f7  mov     rcx, rbx
0x14001d1fa  call    SkmiInvalidateVirtualPageRange
0x14001d1ff  mov     r9d, 1
0x14001d205  mov     r8, r14
0x14001d208  mov     rdx, rdi
0x14001d20b  mov     rcx, rbx
0x14001d20e  call    SkmiFreeVirtualPageTables
0x14001d213  mov     rdx, [rsp+0F8h+var_C0]
0x14001d218  mov     rcx, rbx
0x14001d21b  call    SkmiReturnCommitment
0x14001d220  xor     edx, edx; Val
0x14001d222  lea     rcx, [rsp+0F8h+var_B8]; void *
0x14001d227  lea     r8d, [rdx+68h]; Size
0x14001d22b  call    memset_0
0x14001d230  mov     eax, 0Dh
0x14001d235  mov     [rsp+0F8h+var_A0], rsi
0x14001d23a  mov     [rsp+0F8h+var_B6], ax
0x14001d23f  lea     rcx, [rsp+0F8h+var_B8]
0x14001d244  mov     [rsp+0F8h+var_98], rbp
0x14001d249  mov     rax, [rbx+30h]
0x14001d24d  mov     [rsp+0F8h+var_B0], rax
0x14001d252  mov     [rsp+0F8h+var_90], 4000h
0x14001d25a  call    SkCallNormalMode
0x14001d25f  mov     ebx, r13d
0x14001d262  mov     rcx, r12
0x14001d265  call    SkmiUnlockVad
0x14001d26a  mov     rcx, r15
0x14001d26d  call    RtlReleaseSRWLockShared
0x14001d272  mov     rcx, gs:8
0x14001d27b  test    rcx, rcx
0x14001d27e  jz      short loc_14001D2CB
0x14001d280  mov     r8, [rcx+90h]
0x14001d287  test    r8, r8
0x14001d28a  jz      short loc_14001D2CB
0x14001d28c  nop
0x14001d28d  mov     edx, 1
0x14001d292  mov     rax, qword ptr cs:xmmword_140167150
0x14001d299  add     [r8+rax], dx
0x14001d29e  jnz     short loc_14001D2CB
0x14001d2a0  mov     rcx, [rcx+88h]
0x14001d2a7  nop
0x14001d2a8  mov     rdx, qword ptr cs:xmmword_140167160
0x14001d2af  add     rcx, rdx
0x14001d2b2  cmp     [r8+rdx], rcx
0x14001d2b6  jz      short loc_14001D2CB
0x14001d2b8  mov     rcx, qword ptr cs:xmmword_140167150+8
0x14001d2bf  cmp     [r8+rcx], r13w
0x14001d2c4  jnz     short loc_14001D2CB
0x14001d2c6  call    SkiCheckForKernelApcDelivery
0x14001d2cb  mov     eax, ebx
0x14001d2cd  jmp     short loc_14001D2DB
0x14001d2cf  mov     eax, 0C0000018h
0x14001d2d4  jmp     short loc_14001D2DB
0x14001d2d6  mov     eax, 0C000000Dh
0x14001d2db  mov     rcx, [rsp+0F8h+var_48]
0x14001d2e3  xor     rcx, rsp; StackCookie
0x14001d2e6  call    __security_check_cookie
0x14001d2eb  mov     rbx, [rsp+0F8h+arg_10]
0x14001d2f3  add     rsp, 0C0h
0x14001d2fa  pop     r15
0x14001d2fc  pop     r14
0x14001d2fe  pop     r13
0x14001d300  pop     r12
0x14001d302  pop     rdi
0x14001d303  pop     rsi
0x14001d304  pop     rbp
0x14001d305  retn
```
