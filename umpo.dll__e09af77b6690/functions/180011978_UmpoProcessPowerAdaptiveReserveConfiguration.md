# UmpoProcessPowerAdaptiveReserveConfiguration

- ea: `0x180011978`
- end: `0x1800119d0`
- name: `UmpoProcessPowerAdaptiveReserveConfiguration`
- size: `88`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000b39c`

## callees

- `0x180004380`
- `0x180010946`
- `0x180011978`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall UmpoProcessPowerAdaptiveReserveConfiguration(__int64 a1)
{
  int v3; // [rsp+20h] [rbp-58h] BYREF
  __int64 v4; // [rsp+28h] [rbp-50h]
  _BYTE v5[72]; // [rsp+30h] [rbp-48h] BYREF

  memset_0(&v3, 0, 0x48u);
  v3 = 20;
  v4 = *(_QWORD *)(a1 + 8);
  if ( qword_180024728 )
    qword_180024728(a1 + 8, v5);
  return UmpoAlpcSendPowerMessage(&v3, 0x48u);
}

```

## disassembly

```asm
0x180011978  push    rbx
0x18001197a  sub     rsp, 70h
0x18001197e  xor     edx, edx; Val
0x180011980  mov     rbx, rcx
0x180011983  lea     rcx, [rsp+78h+var_58]; void *
0x180011988  lea     r8d, [rdx+48h]; Size
0x18001198c  call    memset_0
0x180011991  lea     rcx, [rbx+8]
0x180011995  mov     [rsp+78h+var_58], 14h
0x18001199d  mov     rax, [rcx]
0x1800119a0  mov     [rsp+78h+var_50], rax
0x1800119a5  mov     rax, cs:qword_180024728
0x1800119ac  test    rax, rax
0x1800119af  jz      short loc_1800119BB
0x1800119b1  lea     rdx, [rsp+78h+var_48]
0x1800119b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119bb  mov     edx, 48h ; 'H'
0x1800119c0  lea     rcx, [rsp+78h+var_58]
0x1800119c5  call    UmpoAlpcSendPowerMessage
0x1800119ca  add     rsp, 70h
0x1800119ce  pop     rbx
0x1800119cf  retn
```
