# CWMDSPPropImpl::UpdateProp(ulong,WMDSPPropVal,WMDSPPropVal,WMDSPPropVal,WMDSPPropVal)

- ea: `0x18000e080`
- end: `0x18000e1c8`
- name: `?UpdateProp@CWMDSPPropImpl@@MEAAXKTWMDSPPropVal@@000@Z`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18000e080`
- `0x18000e1d0`
- `0x18000e2e8`

## pseudocode

```c
__int64 __fastcall CWMDSPPropImpl::UpdateProp(__int64 a1, unsigned int a2, int *a3, int *a4, int *a5, int *a6)
{
  __int64 v9; // rdi
  __int64 v10; // r14
  __int64 v11; // rsi
  unsigned __int16 v12; // r12
  __int64 v13; // rbp
  unsigned __int16 v14; // r14
  __int64 v15; // rbp
  unsigned __int16 v16; // r14
  __int64 v17; // rbp
  unsigned __int16 v18; // si
  __int64 result; // rax

  v9 = 9LL * a2;
  v10 = *(_QWORD *)(a1 + 24) + 72LL * a2;
  v11 = 96LL * a2;
  v12 = *(_WORD *)(v11 + *(_QWORD *)(a1 + 16) + 20);
  if ( !(unsigned int)WMDSPPropValEqual(v12, v10 + 8) )
  {
    WMDSPPropValCopy(v12, (OLECHAR **)(v10 + 8), a3);
    *(_DWORD *)(*(_QWORD *)(a1 + 24) + 8 * v9) = 1;
  }
  v13 = *(_QWORD *)(a1 + 24) + 8 * v9;
  v14 = *(_WORD *)(v11 + *(_QWORD *)(a1 + 16) + 20);
  if ( !(unsigned int)WMDSPPropValEqual(v14, v13 + 24) )
  {
    WMDSPPropValCopy(v14, (OLECHAR **)(v13 + 24), a4);
    *(_DWORD *)(*(_QWORD *)(a1 + 24) + 8 * v9) = 1;
  }
  v15 = *(_QWORD *)(a1 + 24) + 8 * v9;
  v16 = *(_WORD *)(v11 + *(_QWORD *)(a1 + 16) + 20);
  if ( !(unsigned int)WMDSPPropValEqual(v16, v15 + 40) )
  {
    WMDSPPropValCopy(v16, (OLECHAR **)(v15 + 40), a5);
    *(_DWORD *)(*(_QWORD *)(a1 + 24) + 8 * v9) = 1;
  }
  v17 = *(_QWORD *)(a1 + 24) + 8 * v9;
  v18 = *(_WORD *)(v11 + *(_QWORD *)(a1 + 16) + 20);
  result = WMDSPPropValEqual(v18, v17 + 56);
  if ( !(_DWORD)result )
  {
    WMDSPPropValCopy(v18, (OLECHAR **)(v17 + 56), a6);
    result = *(_QWORD *)(a1 + 24);
    *(_DWORD *)(result + 8 * v9) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000e080  push    rbx
0x18000e082  push    rbp
0x18000e083  push    rsi
0x18000e084  push    rdi
0x18000e085  push    r12
0x18000e087  push    r14
0x18000e089  push    r15
0x18000e08b  sub     rsp, 20h
0x18000e08f  mov     rax, [rcx+18h]
0x18000e093  mov     rbx, rcx
0x18000e096  mov     r10d, edx
0x18000e099  mov     r15, r9
0x18000e09c  mov     rbp, r8
0x18000e09f  lea     rdi, [r10+r10*8]
0x18000e0a3  lea     r14, [rax+rdi*8]
0x18000e0a7  mov     rax, [rcx+10h]
0x18000e0ab  lea     rsi, [r10+r10*2]
0x18000e0af  shl     rsi, 5
0x18000e0b3  lea     rdx, [r14+8]
0x18000e0b7  movzx   r12d, word ptr [rsi+rax+14h]
0x18000e0bd  movzx   ecx, r12w
0x18000e0c1  call    WMDSPPropValEqual
0x18000e0c6  test    eax, eax
0x18000e0c8  jnz     short loc_18000E0E5
0x18000e0ca  mov     r8, rbp
0x18000e0cd  lea     rdx, [r14+8]
0x18000e0d1  movzx   ecx, r12w
0x18000e0d5  call    WMDSPPropValCopy
0x18000e0da  mov     rax, [rbx+18h]
0x18000e0de  mov     dword ptr [rax+rdi*8], 1
0x18000e0e5  mov     rax, [rbx+18h]
0x18000e0e9  mov     r8, r15
0x18000e0ec  lea     rbp, [rax+rdi*8]
0x18000e0f0  mov     rax, [rbx+10h]
0x18000e0f4  lea     rdx, [rbp+18h]
0x18000e0f8  movzx   r14d, word ptr [rsi+rax+14h]
0x18000e0fe  movzx   ecx, r14w
0x18000e102  call    WMDSPPropValEqual
0x18000e107  test    eax, eax
0x18000e109  jnz     short loc_18000E126
0x18000e10b  mov     r8, r15
0x18000e10e  lea     rdx, [rbp+18h]
0x18000e112  movzx   ecx, r14w
0x18000e116  call    WMDSPPropValCopy
0x18000e11b  mov     rax, [rbx+18h]
0x18000e11f  mov     dword ptr [rax+rdi*8], 1
0x18000e126  mov     rax, [rbx+18h]
0x18000e12a  mov     r8, [rsp+58h+arg_20]
0x18000e132  lea     rbp, [rax+rdi*8]
0x18000e136  mov     rax, [rbx+10h]
0x18000e13a  lea     rdx, [rbp+28h]
0x18000e13e  movzx   r14d, word ptr [rsi+rax+14h]
0x18000e144  movzx   ecx, r14w
0x18000e148  call    WMDSPPropValEqual
0x18000e14d  test    eax, eax
0x18000e14f  jnz     short loc_18000E171
0x18000e151  mov     r8, [rsp+58h+arg_20]
0x18000e159  lea     rdx, [rbp+28h]
0x18000e15d  movzx   ecx, r14w
0x18000e161  call    WMDSPPropValCopy
0x18000e166  mov     rax, [rbx+18h]
0x18000e16a  mov     dword ptr [rax+rdi*8], 1
0x18000e171  mov     rax, [rbx+18h]
0x18000e175  mov     r8, [rsp+58h+arg_28]
0x18000e17d  lea     rbp, [rax+rdi*8]
0x18000e181  mov     rax, [rbx+10h]
0x18000e185  lea     rdx, [rbp+38h]
0x18000e189  movzx   esi, word ptr [rsi+rax+14h]
0x18000e18e  movzx   ecx, si
0x18000e191  call    WMDSPPropValEqual
0x18000e196  test    eax, eax
0x18000e198  jnz     short loc_18000E1B9
0x18000e19a  mov     r8, [rsp+58h+arg_28]
0x18000e1a2  lea     rdx, [rbp+38h]
0x18000e1a6  movzx   ecx, si
0x18000e1a9  call    WMDSPPropValCopy
0x18000e1ae  mov     rax, [rbx+18h]
0x18000e1b2  mov     dword ptr [rax+rdi*8], 1
0x18000e1b9  add     rsp, 20h
0x18000e1bd  pop     r15
0x18000e1bf  pop     r14
0x18000e1c1  pop     r12
0x18000e1c3  pop     rdi
0x18000e1c4  pop     rsi
0x18000e1c5  pop     rbp
0x18000e1c6  pop     rbx
0x18000e1c7  retn
```
