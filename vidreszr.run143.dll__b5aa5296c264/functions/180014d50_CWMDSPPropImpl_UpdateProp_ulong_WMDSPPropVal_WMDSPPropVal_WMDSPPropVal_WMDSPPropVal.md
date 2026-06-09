# CWMDSPPropImpl::UpdateProp(ulong,WMDSPPropVal,WMDSPPropVal,WMDSPPropVal,WMDSPPropVal)

- ea: `0x180014d50`
- end: `0x180014e98`
- name: `?UpdateProp@CWMDSPPropImpl@@MEAAXKTWMDSPPropVal@@000@Z`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180014d50`
- `0x180014ea0`
- `0x180014f90`

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
0x180014d50  push    rbx
0x180014d52  push    rbp
0x180014d53  push    rsi
0x180014d54  push    rdi
0x180014d55  push    r12
0x180014d57  push    r14
0x180014d59  push    r15
0x180014d5b  sub     rsp, 20h
0x180014d5f  mov     rax, [rcx+18h]
0x180014d63  mov     rbx, rcx
0x180014d66  mov     r10d, edx
0x180014d69  mov     r15, r9
0x180014d6c  mov     rbp, r8
0x180014d6f  lea     rdi, [r10+r10*8]
0x180014d73  lea     r14, [rax+rdi*8]
0x180014d77  mov     rax, [rcx+10h]
0x180014d7b  lea     rsi, [r10+r10*2]
0x180014d7f  shl     rsi, 5
0x180014d83  lea     rdx, [r14+8]
0x180014d87  movzx   r12d, word ptr [rsi+rax+14h]
0x180014d8d  movzx   ecx, r12w
0x180014d91  call    WMDSPPropValEqual
0x180014d96  test    eax, eax
0x180014d98  jnz     short loc_180014DB5
0x180014d9a  mov     r8, rbp
0x180014d9d  lea     rdx, [r14+8]
0x180014da1  movzx   ecx, r12w
0x180014da5  call    WMDSPPropValCopy
0x180014daa  mov     rax, [rbx+18h]
0x180014dae  mov     dword ptr [rax+rdi*8], 1
0x180014db5  mov     rax, [rbx+18h]
0x180014db9  mov     r8, r15
0x180014dbc  lea     rbp, [rax+rdi*8]
0x180014dc0  mov     rax, [rbx+10h]
0x180014dc4  lea     rdx, [rbp+18h]
0x180014dc8  movzx   r14d, word ptr [rsi+rax+14h]
0x180014dce  movzx   ecx, r14w
0x180014dd2  call    WMDSPPropValEqual
0x180014dd7  test    eax, eax
0x180014dd9  jnz     short loc_180014DF6
0x180014ddb  mov     r8, r15
0x180014dde  lea     rdx, [rbp+18h]
0x180014de2  movzx   ecx, r14w
0x180014de6  call    WMDSPPropValCopy
0x180014deb  mov     rax, [rbx+18h]
0x180014def  mov     dword ptr [rax+rdi*8], 1
0x180014df6  mov     rax, [rbx+18h]
0x180014dfa  mov     r8, [rsp+58h+arg_20]
0x180014e02  lea     rbp, [rax+rdi*8]
0x180014e06  mov     rax, [rbx+10h]
0x180014e0a  lea     rdx, [rbp+28h]
0x180014e0e  movzx   r14d, word ptr [rsi+rax+14h]
0x180014e14  movzx   ecx, r14w
0x180014e18  call    WMDSPPropValEqual
0x180014e1d  test    eax, eax
0x180014e1f  jnz     short loc_180014E41
0x180014e21  mov     r8, [rsp+58h+arg_20]
0x180014e29  lea     rdx, [rbp+28h]
0x180014e2d  movzx   ecx, r14w
0x180014e31  call    WMDSPPropValCopy
0x180014e36  mov     rax, [rbx+18h]
0x180014e3a  mov     dword ptr [rax+rdi*8], 1
0x180014e41  mov     rax, [rbx+18h]
0x180014e45  mov     r8, [rsp+58h+arg_28]
0x180014e4d  lea     rbp, [rax+rdi*8]
0x180014e51  mov     rax, [rbx+10h]
0x180014e55  lea     rdx, [rbp+38h]
0x180014e59  movzx   esi, word ptr [rsi+rax+14h]
0x180014e5e  movzx   ecx, si
0x180014e61  call    WMDSPPropValEqual
0x180014e66  test    eax, eax
0x180014e68  jnz     short loc_180014E89
0x180014e6a  mov     r8, [rsp+58h+arg_28]
0x180014e72  lea     rdx, [rbp+38h]
0x180014e76  movzx   ecx, si
0x180014e79  call    WMDSPPropValCopy
0x180014e7e  mov     rax, [rbx+18h]
0x180014e82  mov     dword ptr [rax+rdi*8], 1
0x180014e89  add     rsp, 20h
0x180014e8d  pop     r15
0x180014e8f  pop     r14
0x180014e91  pop     r12
0x180014e93  pop     rdi
0x180014e94  pop     rsi
0x180014e95  pop     rbp
0x180014e96  pop     rbx
0x180014e97  retn
```
