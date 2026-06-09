# LGetAgentWithoutAddressIDXxx

- ea: `0x18000b52c`
- end: `0x18000b72d`
- name: `LGetAgentWithoutAddressIDXxx`
- size: `513`
- prototype: `_UNKNOWN **__fastcall(int, _DWORD *, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000b470`
- `0x18000b4a0`
- `0x18000b4d0`
- `0x18000f900`

## callees

- `0x18000289c`
- `0x1800038cc`
- `0x1800063d4`
- `0x180006f24`
- `0x18000b52c`
- `0x180017adc`
- `0x180019fcc`
- `0x18001c114`
- `0x180040010`

## pseudocode

```c
_UNKNOWN **__fastcall LGetAgentWithoutAddressIDXxx(
        int a1,
        _DWORD *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  _UNKNOWN **result; // rax
  bool v8; // cc
  int v10; // eax
  __int64 v11; // rsi
  int v12; // edi
  __int64 v13; // r14
  int Proxy; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  char *v18; // rax
  __int64 v19; // rdx
  _DWORD *v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // [rsp+78h] [rbp-9h] BYREF
  __int64 v24; // [rsp+80h] [rbp-1h] BYREF
  __int64 v25; // [rsp+88h] [rbp+7h] BYREF
  int v26[2]; // [rsp+90h] [rbp+Fh] BYREF
  HANDLE TargetHandle; // [rsp+98h] [rbp+17h] BYREF
  _UNKNOWN *retaddr; // [rsp+D0h] [rbp+4Fh] BYREF
  __int64 v29; // [rsp+E0h] [rbp+5Fh] BYREF
  unsigned int v30; // [rsp+E8h] [rbp+67h] BYREF

  result = &retaddr;
  v30 = a3;
  v8 = a2[7] <= 0x40000u;
  LODWORD(v23) = 0;
  TargetHandle = 0;
  *(_QWORD *)v26 = 0;
  LODWORD(v29) = 0;
  v25 = 0;
  v24 = 0;
  if ( !v8 )
  {
    *a2 = -2147483576;
    return result;
  }
  v10 = LineProlog(
          a1,
          2,
          a2[4],
          (int)v26,
          0,
          &TargetHandle,
          (__int64)&v23,
          0,
          0,
          (__int64)&v24,
          a2[2],
          (__int64)&v29,
          (__int64)&v25);
  v11 = v24;
  v12 = v10;
  if ( v10 > 0 )
  {
    v13 = (unsigned int)a2[7];
    v30 = 0;
    v24 = 0;
    if ( (unsigned int)v13 < a6 )
    {
      v12 = -2147483571;
      return (_UNKNOWN **)LineEpilogAsync((_DWORD)a2, v12, (_DWORD)TargetHandle, v23, v11, v29);
    }
    Proxy = FindProxy(v25, 0, a4, &v24, &v30, 0x20002u);
    if ( Proxy )
    {
LABEL_7:
      v12 = Proxy;
      return (_UNKNOWN **)LineEpilogAsync((_DWORD)a2, v12, (_DWORD)TargetHandle, v23, v11, v29);
    }
    *(_QWORD *)(v11 + 80) = (unsigned int)a2[6];
    *(_QWORD *)(v11 + 88) = v13;
    *(_DWORD *)(v11 + 68) = a2[3];
    if ( v24 )
    {
      v25 = 0;
      Proxy = CreateProxyRequest(v24, a4, 8, v11, (ULONG **)&v25);
      if ( Proxy )
        goto LABEL_7;
      v15 = v25;
      v16 = v24;
      *(_DWORD *)(v25 + 68) = a2[5];
      *(_DWORD *)(v15 + 72) = v13;
      Proxy = SendProxyRequest(v16, v15, v11);
      if ( Proxy )
        goto LABEL_7;
      v17 = *(_DWORD *)(v11 + 72);
    }
    else
    {
      if ( !*((_DWORD *)GetLineLookupEntry(v30) + 9) )
      {
        v12 = -2147483575;
        return (_UNKNOWN **)LineEpilogAsync((_DWORD)a2, v12, (_DWORD)TargetHandle, v23, v11, v29);
      }
      v18 = (char *)AllocAsyncEventMsg(v13);
      if ( !v18 )
      {
        v12 = -2147483580;
        return (_UNKNOWN **)LineEpilogAsync((_DWORD)a2, v12, (_DWORD)TargetHandle, v23, v11, v29);
      }
      v19 = *(_QWORD *)v26;
      v20 = v18 + 40;
      *(_QWORD *)(v11 + 48) = LGetAgentXxx_PostProcess;
      v21 = a5;
      *(_QWORD *)(v11 + 96) = v18;
      v22 = pRemoteSP;
      *v20 = v13;
      v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(v22 + 8 * v21 + 128))(
              *(unsigned int *)(v11 + 72),
              v19,
              (unsigned int)a2[5]);
    }
    *a2 = v17;
  }
  return (_UNKNOWN **)LineEpilogAsync((_DWORD)a2, v12, (_DWORD)TargetHandle, v23, v11, v29);
}

```

## disassembly

```asm
0x18000b52c  mov     rax, rsp
0x18000b52f  mov     [rax+8], rbx
0x18000b533  mov     [rax+20h], rsi
0x18000b537  mov     [rax+18h], r8d
0x18000b53b  push    rbp
0x18000b53c  push    rdi
0x18000b53d  push    r12
0x18000b53f  push    r13
0x18000b541  push    r14
0x18000b543  lea     rbp, [rax-4Fh]
0x18000b547  sub     rsp, 0A0h
0x18000b54e  xor     r13d, r13d
0x18000b551  mov     r12d, r9d
0x18000b554  cmp     dword ptr [rdx+1Ch], 40000h
0x18000b55b  mov     rbx, rdx
0x18000b55e  mov     dword ptr [rbp+47h+var_50], r13d
0x18000b562  mov     [rbp+47h+TargetHandle], r13
0x18000b566  mov     qword ptr [rbp+47h+var_38], r13
0x18000b56a  mov     dword ptr [rbp+47h+arg_8], r13d
0x18000b56e  mov     [rbp+47h+var_40], r13
0x18000b572  mov     [rbp+47h+var_48], r13
0x18000b576  jbe     short loc_18000B583
0x18000b578  mov     dword ptr [rdx], 80000048h
0x18000b57e  jmp     loc_18000B711
0x18000b583  mov     r8d, [rdx+10h]; int
0x18000b587  lea     rax, [rbp+47h+var_40]
0x18000b58b  mov     [rsp+0C0h+var_60], rax; __int64
0x18000b590  lea     r9, [rbp+47h+var_38]; int
0x18000b594  lea     rax, [rbp+47h+arg_8]
0x18000b598  mov     [rsp+0C0h+var_68], rax; __int64
0x18000b59d  mov     eax, [rdx+8]
0x18000b5a0  mov     edx, 2; int
0x18000b5a5  mov     [rsp+0C0h+var_70], eax; int
0x18000b5a9  lea     rax, [rbp+47h+var_48]
0x18000b5ad  mov     [rsp+0C0h+var_78], rax; __int64
0x18000b5b2  lea     rax, [rbp+47h+var_50]
0x18000b5b6  mov     [rsp+0C0h+var_80], r13; __int64
0x18000b5bb  mov     [rsp+0C0h+var_88], r13d; int
0x18000b5c0  mov     [rsp+0C0h+var_90], rax; __int64
0x18000b5c5  lea     rax, [rbp+47h+TargetHandle]
0x18000b5c9  mov     [rsp+0C0h+lpTargetHandle], rax; lpTargetHandle
0x18000b5ce  mov     [rsp+0C0h+var_A0], r13d; int
0x18000b5d3  call    LineProlog
0x18000b5d8  mov     rsi, [rbp+47h+var_48]
0x18000b5dc  mov     edi, eax
0x18000b5de  test    eax, eax
0x18000b5e0  jle     loc_18000B6F3
0x18000b5e6  mov     r14d, [rbx+1Ch]
0x18000b5ea  mov     [rbp+47h+arg_10], r13d
0x18000b5ee  mov     [rbp+47h+var_48], r13
0x18000b5f2  cmp     r14d, [rbp+47h+arg_28]
0x18000b5f6  jnb     short loc_18000B602
0x18000b5f8  mov     edi, 8000004Dh
0x18000b5fd  jmp     loc_18000B6F3
0x18000b602  mov     rcx, [rbp+47h+var_40]
0x18000b606  lea     rax, [rbp+47h+arg_10]
0x18000b60a  mov     dword ptr [rsp+0C0h+lpTargetHandle], 20002h
0x18000b612  lea     r9, [rbp+47h+var_48]
0x18000b616  mov     r8d, r12d
0x18000b619  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18000b61e  xor     edx, edx
0x18000b620  call    FindProxy
0x18000b625  test    eax, eax
0x18000b627  jz      short loc_18000B630
0x18000b629  mov     edi, eax
0x18000b62b  jmp     loc_18000B6F3
0x18000b630  mov     eax, [rbx+18h]
0x18000b633  mov     [rsi+50h], rax
0x18000b637  mov     [rsi+58h], r14
0x18000b63b  mov     eax, [rbx+0Ch]
0x18000b63e  mov     [rsi+44h], eax
0x18000b641  cmp     [rbp+47h+var_48], r13
0x18000b645  jz      short loc_18000B690
0x18000b647  mov     rcx, [rbp+47h+var_48]
0x18000b64b  lea     rax, [rbp+47h+var_40]
0x18000b64f  mov     r9, rsi
0x18000b652  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18000b657  mov     r8d, 8
0x18000b65d  mov     [rbp+47h+var_40], r13
0x18000b661  mov     edx, r12d
0x18000b664  call    CreateProxyRequest
0x18000b669  test    eax, eax
0x18000b66b  jnz     short loc_18000B629
0x18000b66d  mov     rdx, [rbp+47h+var_40]
0x18000b671  mov     r8, rsi
0x18000b674  mov     eax, [rbx+14h]
0x18000b677  mov     rcx, [rbp+47h+var_48]
0x18000b67b  mov     [rdx+44h], eax
0x18000b67e  mov     [rdx+48h], r14d
0x18000b682  call    SendProxyRequest
0x18000b687  test    eax, eax
0x18000b689  jnz     short loc_18000B629
0x18000b68b  mov     eax, [rsi+48h]
0x18000b68e  jmp     short loc_18000B6EA
0x18000b690  mov     ecx, [rbp+47h+arg_10]
0x18000b693  call    GetLineLookupEntry
0x18000b698  cmp     [rax+24h], r13d
0x18000b69c  jz      short loc_18000B6EE
0x18000b69e  mov     ecx, r14d
0x18000b6a1  call    AllocAsyncEventMsg
0x18000b6a6  test    rax, rax
0x18000b6a9  jnz     short loc_18000B6B2
0x18000b6ab  mov     edi, 80000044h
0x18000b6b0  jmp     short loc_18000B6F3
0x18000b6b2  mov     rdx, qword ptr [rbp+47h+var_38]
0x18000b6b6  lea     r9, [rax+28h]
0x18000b6ba  lea     rcx, LGetAgentXxx_PostProcess
0x18000b6c1  mov     [rsi+30h], rcx
0x18000b6c5  mov     ecx, [rbp+47h+arg_20]
0x18000b6c8  mov     [rsi+60h], rax
0x18000b6cc  mov     rax, cs:pRemoteSP
0x18000b6d3  mov     [r9], r14d
0x18000b6d6  mov     r8d, [rbx+14h]
0x18000b6da  mov     rax, [rax+rcx*8+80h]
0x18000b6e2  mov     ecx, [rsi+48h]
0x18000b6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6ea  mov     [rbx], eax
0x18000b6ec  jmp     short loc_18000B6F3
0x18000b6ee  mov     edi, 80000049h
0x18000b6f3  mov     eax, dword ptr [rbp+47h+arg_8]
0x18000b6f6  mov     edx, edi
0x18000b6f8  mov     r9d, dword ptr [rbp+47h+var_50]
0x18000b6fc  mov     rcx, rbx
0x18000b6ff  mov     r8, [rbp+47h+TargetHandle]
0x18000b703  mov     dword ptr [rsp+0C0h+lpTargetHandle], eax
0x18000b707  mov     qword ptr [rsp+0C0h+var_A0], rsi
0x18000b70c  call    LineEpilogAsync
0x18000b711  lea     r11, [rsp+0C0h+var_20]
0x18000b719  mov     rbx, [r11+30h]
0x18000b71d  mov     rsi, [r11+48h]
0x18000b721  mov     rsp, r11
0x18000b724  pop     r14
0x18000b726  pop     r13
0x18000b728  pop     r12
0x18000b72a  pop     rdi
0x18000b72b  pop     rbp
0x18000b72c  retn
```
