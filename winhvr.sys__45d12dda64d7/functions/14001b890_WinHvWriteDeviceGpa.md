# WinHvWriteDeviceGpa

- ea: `0x14001b890`
- end: `0x14001ba37`
- name: `WinHvWriteDeviceGpa`
- size: `423`
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
- `0x14001b890`

## pseudocode

```c
__int64 __fastcall WinHvWriteDeviceGpa(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        _DWORD *a7)
{
  __int64 v11; // rcx
  __int64 *v12; // r14
  __int64 v13; // rax
  __int64 v14; // rsi
  __int64 v15; // rdi
  unsigned int v16; // ebx
  unsigned int v17; // r12d
  unsigned int v18; // r15d
  unsigned __int64 v19; // rdx
  void *v20; // rcx
  int v21; // eax
  _QWORD v23[8]; // [rsp+20h] [rbp-40h] BYREF
  __int64 *v24; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v25; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v26; // [rsp+B8h] [rbp+58h] BYREF

  v24 = 0;
  v25 = 0;
  memset(v23, 0, sizeof(v23));
  v26 = 0;
  WinHvpSetupHypercall(&v24, &v25, (__int64)v23);
  v12 = v24;
  v13 = a5;
  *v24 = a1;
  v12[1] = a2;
  v12[2] = 0;
  v12[3] = a3;
  v14 = v25;
  *((_DWORD *)v12 + 9) = 0;
  v12[5] = v13;
  *(_QWORD *)v14 = 0;
  if ( a4 <= 0x800 )
  {
    v17 = (a4 + 7) & 0xFFFFFFF8;
    if ( (unsigned __int64)v17 + 56 > 0x1000 )
    {
      v16 = -1073741811;
      goto LABEL_22;
    }
    v15 = 0;
  }
  else
  {
    v15 = WinHvpSetupReadWriteDeviceGpaPfnBuffer(v11, v12 + 6, &v26);
    if ( !v15 )
    {
      v16 = -1073741670;
      goto LABEL_22;
    }
    *((_DWORD *)v12 + 9) |= 1u;
    v17 = v26;
  }
  v18 = a4;
  v16 = 0;
  do
  {
    if ( !v18 )
      break;
    v19 = 4096;
    if ( v18 < 0x1000 )
      v19 = v18;
    *((_DWORD *)v12 + 8) = v19;
    if ( v19 >= 4096 - (unsigned __int64)(v12[3] & 0xFFF) )
      LODWORD(v19) = 4096 - (v12[3] & 0xFFF);
    v20 = (void *)v15;
    *((_DWORD *)v12 + 8) = v19;
    if ( !v15 )
      v20 = v12 + 6;
    memmove(v20, (const void *)(a6 + a4 - v18), (unsigned int)v19);
    v21 = WinHvpVariableHeaderHypercall(303, v17, *(_QWORD *)(v23[5] + 24LL), *(_QWORD *)(v23[5] + 40LL));
    v16 = v21;
    if ( v21 >= 0 && !*(_DWORD *)(v14 + 4) )
      *(_DWORD *)(v14 + 4) = *((_DWORD *)v12 + 8);
    v12[3] += *(unsigned int *)(v14 + 4);
    v18 -= *(_DWORD *)(v14 + 4);
  }
  while ( v21 >= 0 );
  *a7 = *(_DWORD *)v14;
  if ( v15 )
    WinHvpFreePoolWithTag(v15, 1433815127);
LABEL_22:
  ((void (__fastcall *)(_QWORD))v23[7])(v23[0]);
  return v16;
}

```

## disassembly

```asm
0x14001b890  mov     [rsp-38h+arg_10], rbx
0x14001b895  push    rbp
0x14001b896  push    rsi
0x14001b897  push    rdi
0x14001b898  push    r12
0x14001b89a  push    r13
0x14001b89c  push    r14
0x14001b89e  push    r15
0x14001b8a0  mov     rbp, rsp
0x14001b8a3  sub     rsp, 60h
0x14001b8a7  xor     r15d, r15d
0x14001b8aa  mov     rsi, r8
0x14001b8ad  mov     rdi, rdx
0x14001b8b0  mov     [rbp+arg_0], r15
0x14001b8b4  mov     rbx, rcx
0x14001b8b7  mov     [rbp+arg_8], r15
0x14001b8bb  xor     edx, edx; Val
0x14001b8bd  lea     rcx, [rbp+var_40]; void *
0x14001b8c1  lea     r8d, [r15+40h]; Size
0x14001b8c5  mov     r13d, r9d
0x14001b8c8  call    memset
0x14001b8cd  lea     r8, [rbp+var_40]
0x14001b8d1  mov     [rbp+arg_18], r15d
0x14001b8d5  lea     rdx, [rbp+arg_8]
0x14001b8d9  lea     rcx, [rbp+arg_0]
0x14001b8dd  call    WinHvpSetupHypercall
0x14001b8e2  mov     r14, [rbp+arg_0]
0x14001b8e6  mov     rax, [rbp+arg_20]
0x14001b8ea  mov     [r14], rbx
0x14001b8ed  mov     [r14+8], rdi
0x14001b8f1  mov     [r14+10h], r15
0x14001b8f5  mov     [r14+18h], rsi
0x14001b8f9  mov     rsi, [rbp+arg_8]
0x14001b8fd  mov     [r14+24h], r15d
0x14001b901  mov     [r14+28h], rax
0x14001b905  mov     [rsi], r15
0x14001b908  cmp     r13d, 800h
0x14001b90f  jbe     short loc_14001B93B
0x14001b911  lea     rdx, [r14+30h]
0x14001b915  lea     r8, [rbp+arg_18]
0x14001b919  call    WinHvpSetupReadWriteDeviceGpaPfnBuffer
0x14001b91e  mov     rdi, rax
0x14001b921  test    rax, rax
0x14001b924  jnz     short loc_14001B930
0x14001b926  mov     ebx, 0C000009Ah
0x14001b92b  jmp     loc_14001BA0F
0x14001b930  or      dword ptr [r14+24h], 1
0x14001b935  mov     r12d, [rbp+arg_18]
0x14001b939  jmp     short loc_14001B958
0x14001b93b  lea     eax, [r13+7]
0x14001b93f  and     eax, 0FFFFFFF8h
0x14001b942  mov     r12d, eax
0x14001b945  add     rax, 38h ; '8'
0x14001b949  cmp     rax, 1000h
0x14001b94f  ja      loc_14001BA0A
0x14001b955  mov     rdi, r15
0x14001b958  mov     r15d, r13d
0x14001b95b  xor     ebx, ebx
0x14001b95d  test    r15d, r15d
0x14001b960  jz      loc_14001B9EE
0x14001b966  mov     edx, 1000h
0x14001b96b  mov     ecx, 1000h
0x14001b970  cmp     r15d, edx
0x14001b973  cmovb   edx, r15d
0x14001b977  mov     [r14+20h], edx
0x14001b97b  mov     eax, [r14+18h]
0x14001b97f  and     eax, 0FFFh
0x14001b984  sub     rcx, rax
0x14001b987  cmp     rdx, rcx
0x14001b98a  cmovnb  edx, ecx
0x14001b98d  mov     rcx, rdi
0x14001b990  mov     [r14+20h], edx
0x14001b994  test    rdi, rdi
0x14001b997  jnz     short loc_14001B99D
0x14001b999  lea     rcx, [r14+30h]; void *
0x14001b99d  mov     r8d, edx; Size
0x14001b9a0  mov     edx, r13d
0x14001b9a3  sub     edx, r15d
0x14001b9a6  add     rdx, [rbp+arg_28]; Src
0x14001b9aa  call    memmove
0x14001b9af  mov     r8, [rbp+var_18]
0x14001b9b3  mov     edx, r12d
0x14001b9b6  mov     ecx, 12Fh
0x14001b9bb  mov     r9, [r8+28h]
0x14001b9bf  mov     r8, [r8+18h]
0x14001b9c3  call    WinHvpVariableHeaderHypercall
0x14001b9c8  mov     ebx, eax
0x14001b9ca  test    eax, eax
0x14001b9cc  js      short loc_14001B9DB
0x14001b9ce  cmp     dword ptr [rsi+4], 0
0x14001b9d2  jnz     short loc_14001B9DB
0x14001b9d4  mov     ecx, [r14+20h]
0x14001b9d8  mov     [rsi+4], ecx
0x14001b9db  mov     ecx, [rsi+4]
0x14001b9de  add     [r14+18h], rcx
0x14001b9e2  sub     r15d, [rsi+4]
0x14001b9e6  test    eax, eax
0x14001b9e8  jns     loc_14001B95D
0x14001b9ee  mov     rax, [rbp+arg_30]
0x14001b9f2  mov     ecx, [rsi]
0x14001b9f4  mov     [rax], ecx
0x14001b9f6  test    rdi, rdi
0x14001b9f9  jz      short loc_14001BA0F
0x14001b9fb  mov     edx, 55764857h
0x14001ba00  mov     rcx, rdi
0x14001ba03  call    WinHvpFreePoolWithTag
0x14001ba08  jmp     short loc_14001BA0F
0x14001ba0a  mov     ebx, 0C000000Dh
0x14001ba0f  mov     rcx, [rbp+var_40]
0x14001ba13  mov     rax, [rbp+var_8]
0x14001ba17  call    _guard_dispatch_icall
0x14001ba1c  mov     eax, ebx
0x14001ba1e  mov     rbx, [rsp+60h+arg_10]
0x14001ba26  add     rsp, 60h
0x14001ba2a  pop     r15
0x14001ba2c  pop     r14
0x14001ba2e  pop     r13
0x14001ba30  pop     r12
0x14001ba32  pop     rdi
0x14001ba33  pop     rsi
0x14001ba34  pop     rbp
0x14001ba35  retn
```
