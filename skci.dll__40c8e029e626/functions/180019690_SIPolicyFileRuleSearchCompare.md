# SIPolicyFileRuleSearchCompare

- ea: `0x180019690`
- end: `0x180019718`
- name: `SIPolicyFileRuleSearchCompare`
- size: `136`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800211b4`
- `0x180033950`

## pseudocode

```c
int __fastcall SIPolicyFileRuleSearchCompare(_QWORD *a1, unsigned int *a2)
{
  __int128 *v4; // rax
  __int128 v5; // xmm1
  __int128 *v6; // rax
  __int128 v7; // xmm0
  __int128 *v8; // rax
  __int128 v9; // xmm1
  __int64 v10; // rax
  int v12; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v13[4]; // [rsp+24h] [rbp-B4h] BYREF
  __int128 v14; // [rsp+28h] [rbp-B0h]
  __int128 v15; // [rsp+38h] [rbp-A0h]
  __int128 v16; // [rsp+48h] [rbp-90h]
  __int128 v17; // [rsp+58h] [rbp-80h]

  memset_0(v13, 0, 0xA4u);
  v12 = *(_DWORD *)a1;
  v4 = (__int128 *)a1[2];
  v14 = *(_OWORD *)a1[1];
  v5 = *v4;
  v6 = (__int128 *)a1[3];
  v15 = v5;
  v7 = *v6;
  v8 = (__int128 *)a1[4];
  v16 = v7;
  v9 = *v8;
  v10 = *a2;
  v17 = v9;
  return SIPolicyFileRuleCompare((__int64)&v12, a1[6] + 168 * v10);
}

```

## disassembly

```asm
0x180019690  mov     [rsp+arg_0], rbx
0x180019695  push    rdi
0x180019696  sub     rsp, 0D0h
0x18001969d  mov     rbx, rdx
0x1800196a0  mov     rdi, rcx
0x1800196a3  xor     edx, edx; Val
0x1800196a5  lea     rcx, [rsp+0D8h+var_B4]; void *
0x1800196aa  mov     r8d, 0A4h; Size
0x1800196b0  call    memset_0
0x1800196b5  mov     eax, [rdi]
0x1800196b7  lea     rcx, [rsp+0D8h+var_B8]
0x1800196bc  mov     [rsp+0D8h+var_B8], eax
0x1800196c0  mov     rax, [rdi+8]
0x1800196c4  movups  xmm0, xmmword ptr [rax]
0x1800196c7  mov     rax, [rdi+10h]
0x1800196cb  movdqu  [rsp+0D8h+var_B0], xmm0
0x1800196d1  movups  xmm1, xmmword ptr [rax]
0x1800196d4  mov     rax, [rdi+18h]
0x1800196d8  movdqu  [rsp+0D8h+var_A0], xmm1
0x1800196de  movups  xmm0, xmmword ptr [rax]
0x1800196e1  mov     rax, [rdi+20h]
0x1800196e5  movdqu  [rsp+0D8h+var_90], xmm0
0x1800196eb  movups  xmm1, xmmword ptr [rax]
0x1800196ee  mov     eax, [rbx]
0x1800196f0  imul    rdx, rax, 0A8h
0x1800196f7  movdqu  [rsp+0D8h+var_80], xmm1
0x1800196fd  add     rdx, [rdi+30h]
0x180019701  call    SIPolicyFileRuleCompare
0x180019706  mov     rbx, [rsp+0D8h+arg_0]
0x18001970e  add     rsp, 0D0h
0x180019715  pop     rdi
0x180019716  retn
```
