# WinHvLowMemoryPolicyAutoDeposit

- ea: `0x1400048f0`
- end: `0x1400049e6`
- name: `WinHvLowMemoryPolicyAutoDeposit`
- size: `246`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140001ef0`
- `0x140002358`
- `0x1400048b8`
- `0x140005810`
- `0x140008fa0`
- `0x140009190`

## callees

- `0x1400048f0`
- `0x14001b010`
- `0x140022e50`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000490d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000490d`

## pseudocode

```c
__int64 __fastcall WinHvLowMemoryPolicyAutoDeposit(__int64 a1, __int64 a2, int a3, int a4)
{
  int v7; // r9d
  char v8; // si
  char v9; // di
  int v10; // ecx
  int v11; // r9d
  _QWORD v13[7]; // [rsp+30h] [rbp-38h] BYREF

  v13[0] = 0;
  if ( KeGetCurrentIrql() >= 2u )
    return (unsigned int)a4;
  v8 = 1;
  v9 = a4 != -1070268285 && a4 > -1070268288 && a4 < -1070268282;
  if ( (unsigned int)(a4 + 1070268299) > 0x10 || (v10 = 90113, !_bittest(&v10, a4 + 1070268299)) )
    v8 = 0;
  LOBYTE(v7) = v8;
  WinHvpDepositMemory(a2, 1088, a3, v7, v9, (__int64)v13);
  if ( v13[0] )
    return 0;
  if ( v9
    && a3 >= 0
    && (LOBYTE(v11) = v8, WinHvpDepositMemory(a2, 1088, a3 | 0x80000000, v11, v9, (__int64)v13), v13[0])
    && (int)WinHvSetPartitionProperty(a2, 327710, 5) >= 0 )
  {
    return 0;
  }
  else
  {
    return (unsigned int)a4;
  }
}

```

## disassembly

```asm
0x1400048f0  push    rbx
0x1400048f2  push    rbp
0x1400048f3  push    rsi
0x1400048f4  push    rdi
0x1400048f5  push    r14
0x1400048f7  sub     rsp, 40h
0x1400048fb  mov     ebx, r9d
0x1400048fe  mov     [rsp+68h+var_38], 0
0x140004907  mov     ebp, r8d
0x14000490a  mov     r14, rdx
0x14000490d  call    cs:__imp_KeGetCurrentIrql
0x140004914  nop     dword ptr [rax+rax+00h]
0x140004919  cmp     al, 2
0x14000491b  jnb     loc_1400049D8
0x140004921  mov     sil, 1
0x140004924  cmp     ebx, 0C0350083h
0x14000492a  jz      short loc_140004941
0x14000492c  cmp     ebx, 0C0350080h
0x140004932  jle     short loc_140004941
0x140004934  cmp     ebx, 0C0350086h
0x14000493a  jge     short loc_140004941
0x14000493c  mov     dil, sil
0x14000493f  jmp     short loc_140004944
0x140004941  xor     dil, dil
0x140004944  lea     eax, [rbx+3FCAFF8Bh]
0x14000494a  cmp     eax, 10h
0x14000494d  ja      short loc_140004959
0x14000494f  mov     ecx, 16001h
0x140004954  bt      ecx, eax
0x140004957  jb      short loc_14000495C
0x140004959  xor     sil, sil
0x14000495c  lea     rax, [rsp+68h+var_38]
0x140004961  mov     r9b, sil
0x140004964  mov     [rsp+68h+var_40], rax
0x140004969  mov     r8d, ebp
0x14000496c  mov     edx, 440h
0x140004971  mov     [rsp+68h+var_48], dil
0x140004976  mov     rcx, r14
0x140004979  call    WinHvpDepositMemory
0x14000497e  cmp     [rsp+68h+var_38], 0
0x140004984  jnz     short loc_1400049D4
0x140004986  test    dil, dil
0x140004989  jz      short loc_1400049D8
0x14000498b  test    ebp, ebp
0x14000498d  js      short loc_1400049D8
0x14000498f  lea     rax, [rsp+68h+var_38]
0x140004994  bts     ebp, 1Fh
0x140004998  mov     [rsp+68h+var_40], rax
0x14000499d  mov     r8d, ebp
0x1400049a0  mov     r9b, sil
0x1400049a3  mov     [rsp+68h+var_48], dil
0x1400049a8  mov     edx, 440h
0x1400049ad  mov     rcx, r14
0x1400049b0  call    WinHvpDepositMemory
0x1400049b5  cmp     [rsp+68h+var_38], 0
0x1400049bb  jz      short loc_1400049D8
0x1400049bd  mov     edx, 5001Eh
0x1400049c2  mov     r8d, 5
0x1400049c8  mov     rcx, r14
0x1400049cb  call    WinHvSetPartitionProperty
0x1400049d0  test    eax, eax
0x1400049d2  js      short loc_1400049D8
0x1400049d4  xor     eax, eax
0x1400049d6  jmp     short loc_1400049DA
0x1400049d8  mov     eax, ebx
0x1400049da  add     rsp, 40h
0x1400049de  pop     r14
0x1400049e0  pop     rdi
0x1400049e1  pop     rsi
0x1400049e2  pop     rbp
0x1400049e3  pop     rbx
0x1400049e4  retn
```
