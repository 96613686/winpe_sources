# WinHvReadDeviceGpa

- ea: `0x14001b700`
- end: `0x14001b888`
- name: `WinHvReadDeviceGpa`
- size: `392`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x140002240`
- `0x140004460`
- `0x1400055d4`
- `0x140009c90`
- `0x140009d40`
- `0x14000a040`
- `0x14000b040`
- `0x14001b700`

## pseudocode

```c
__int64 __fastcall WinHvReadDeviceGpa(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        _DWORD *a7)
{
  unsigned int v11; // r13d
  __int64 v12; // r15
  __int64 v13; // rcx
  __int64 *v14; // r14
  __int64 v15; // rax
  __int64 v16; // rbx
  int v17; // edi
  unsigned int v18; // esi
  unsigned __int64 v19; // rdx
  const void *v20; // rdx
  _QWORD v22[8]; // [rsp+20h] [rbp-40h] BYREF
  __int64 *v23; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v24; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v25; // [rsp+B8h] [rbp+58h] BYREF

  v23 = 0;
  v24 = 0;
  memset(v22, 0, sizeof(v22));
  v11 = 0;
  v25 = 0;
  v12 = 0;
  WinHvpSetupHypercall(&v23, &v24, (__int64)v22);
  v14 = v23;
  v15 = a5;
  *v23 = a1;
  v16 = v24;
  v14[1] = a2;
  v14[2] = 0;
  v14[3] = a3;
  *((_DWORD *)v14 + 9) = 0;
  v14[5] = v15;
  *(_QWORD *)v16 = 0;
  if ( a4 > 0x800 )
  {
    v12 = WinHvpSetupReadWriteDeviceGpaPfnBuffer(v13, v14 + 6, &v25);
    if ( !v12 )
    {
      v17 = -1073741670;
      goto LABEL_19;
    }
    *((_DWORD *)v14 + 9) |= 1u;
    v11 = v25;
  }
  v18 = a4;
  v17 = 0;
  do
  {
    if ( !v18 )
      break;
    v19 = 4096;
    if ( v18 < 0x1000 )
      v19 = v18;
    *((_DWORD *)v14 + 8) = v19;
    if ( v19 >= 4096 - (unsigned __int64)(v14[3] & 0xFFF) )
      LODWORD(v19) = 4096 - (v14[3] & 0xFFF);
    *((_DWORD *)v14 + 8) = v19;
    v17 = WinHvpVariableHeaderHypercall(302, v11, *(_QWORD *)(v22[5] + 24LL), *(_QWORD *)(v22[5] + 40LL));
    if ( v17 >= 0 && !*(_DWORD *)(v16 + 4) )
      *(_DWORD *)(v16 + 4) = *((_DWORD *)v14 + 8);
    v20 = (const void *)v12;
    if ( !v12 )
      v20 = (const void *)(v16 + 8);
    memmove((void *)(a6 + a4 - v18), v20, *(unsigned int *)(v16 + 4));
    v14[3] += *(unsigned int *)(v16 + 4);
    v18 -= *(_DWORD *)(v16 + 4);
  }
  while ( v17 >= 0 );
  *a7 = *(_DWORD *)v16;
  if ( v12 )
    WinHvpFreePoolWithTag(v12, 1433815127);
LABEL_19:
  ((void (__fastcall *)(_QWORD))v22[7])(v22[0]);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x14001b700  mov     [rsp-38h+arg_10], rbx
0x14001b705  push    rbp
0x14001b706  push    rsi
0x14001b707  push    rdi
0x14001b708  push    r12
0x14001b70a  push    r13
0x14001b70c  push    r14
0x14001b70e  push    r15
0x14001b710  mov     rbp, rsp
0x14001b713  sub     rsp, 60h
0x14001b717  mov     rdi, rdx
0x14001b71a  mov     [rbp+arg_0], 0
0x14001b722  xor     edx, edx; Val
0x14001b724  mov     [rbp+arg_8], 0
0x14001b72c  mov     rsi, r8
0x14001b72f  mov     rbx, rcx
0x14001b732  lea     rcx, [rbp+var_40]; void *
0x14001b736  mov     r12d, r9d
0x14001b739  lea     r8d, [rdx+40h]; Size
0x14001b73d  call    memset
0x14001b742  xor     r13d, r13d
0x14001b745  lea     r8, [rbp+var_40]
0x14001b749  lea     rdx, [rbp+arg_8]
0x14001b74d  mov     [rbp+arg_18], r13d
0x14001b751  lea     rcx, [rbp+arg_0]
0x14001b755  xor     r15d, r15d
0x14001b758  call    WinHvpSetupHypercall
0x14001b75d  mov     r14, [rbp+arg_0]
0x14001b761  mov     rax, [rbp+arg_20]
0x14001b765  mov     [r14], rbx
0x14001b768  mov     rbx, [rbp+arg_8]
0x14001b76c  mov     [r14+8], rdi
0x14001b770  mov     [r14+10h], r13
0x14001b774  mov     [r14+18h], rsi
0x14001b778  mov     [r14+24h], r13d
0x14001b77c  mov     [r14+28h], rax
0x14001b780  mov     [rbx], r13
0x14001b783  cmp     r12d, 800h
0x14001b78a  jbe     short loc_14001B7B4
0x14001b78c  lea     rdx, [r14+30h]
0x14001b790  lea     r8, [rbp+arg_18]
0x14001b794  call    WinHvpSetupReadWriteDeviceGpaPfnBuffer
0x14001b799  mov     r15, rax
0x14001b79c  test    rax, rax
0x14001b79f  jnz     short loc_14001B7AB
0x14001b7a1  mov     edi, 0C000009Ah
0x14001b7a6  jmp     loc_14001B860
0x14001b7ab  or      dword ptr [r14+24h], 1
0x14001b7b0  mov     r13d, [rbp+arg_18]
0x14001b7b4  mov     esi, r12d
0x14001b7b7  xor     edi, edi
0x14001b7b9  test    esi, esi
0x14001b7bb  jz      loc_14001B846
0x14001b7c1  mov     edx, 1000h
0x14001b7c6  mov     ecx, 1000h
0x14001b7cb  cmp     esi, edx
0x14001b7cd  cmovb   edx, esi
0x14001b7d0  mov     [r14+20h], edx
0x14001b7d4  mov     eax, [r14+18h]
0x14001b7d8  and     eax, 0FFFh
0x14001b7dd  sub     rcx, rax
0x14001b7e0  cmp     rdx, rcx
0x14001b7e3  cmovnb  edx, ecx
0x14001b7e6  mov     ecx, 12Eh
0x14001b7eb  mov     [r14+20h], edx
0x14001b7ef  mov     edx, r13d
0x14001b7f2  mov     r8, [rbp+var_18]
0x14001b7f6  mov     r9, [r8+28h]
0x14001b7fa  mov     r8, [r8+18h]
0x14001b7fe  call    WinHvpVariableHeaderHypercall
0x14001b803  mov     edi, eax
0x14001b805  test    eax, eax
0x14001b807  js      short loc_14001B816
0x14001b809  cmp     dword ptr [rbx+4], 0
0x14001b80d  jnz     short loc_14001B816
0x14001b80f  mov     ecx, [r14+20h]
0x14001b813  mov     [rbx+4], ecx
0x14001b816  mov     rdx, r15
0x14001b819  test    r15, r15
0x14001b81c  jnz     short loc_14001B822
0x14001b81e  lea     rdx, [rbx+8]; Src
0x14001b822  mov     r8d, [rbx+4]; Size
0x14001b826  mov     ecx, r12d
0x14001b829  sub     ecx, esi
0x14001b82b  add     rcx, [rbp+arg_28]; void *
0x14001b82f  call    memmove
0x14001b834  mov     eax, [rbx+4]
0x14001b837  add     [r14+18h], rax
0x14001b83b  sub     esi, [rbx+4]
0x14001b83e  test    edi, edi
0x14001b840  jns     loc_14001B7B9
0x14001b846  mov     rax, [rbp+arg_30]
0x14001b84a  mov     ecx, [rbx]
0x14001b84c  mov     [rax], ecx
0x14001b84e  test    r15, r15
0x14001b851  jz      short loc_14001B860
0x14001b853  mov     edx, 55764857h
0x14001b858  mov     rcx, r15
0x14001b85b  call    WinHvpFreePoolWithTag
0x14001b860  mov     rcx, [rbp+var_40]
0x14001b864  mov     rax, [rbp+var_8]
0x14001b868  call    _guard_dispatch_icall
0x14001b86d  mov     rbx, [rsp+60h+arg_10]
0x14001b875  mov     eax, edi
0x14001b877  add     rsp, 60h
0x14001b87b  pop     r15
0x14001b87d  pop     r14
0x14001b87f  pop     r13
0x14001b881  pop     r12
0x14001b883  pop     rdi
0x14001b884  pop     rsi
0x14001b885  pop     rbp
0x14001b886  retn
```
