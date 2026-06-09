# LGetAgentXxx

- ea: `0x18000b734`
- end: `0x18000b933`
- name: `LGetAgentXxx`
- size: `511`
- prototype: `_UNKNOWN **__fastcall(int, _DWORD *, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18000b140`
- `0x18000b440`
- `0x18000b500`

## callees

- `0x18000289c`
- `0x1800038cc`
- `0x1800063d4`
- `0x180006f24`
- `0x18000b734`
- `0x180017adc`
- `0x180019fcc`
- `0x18001c114`
- `0x180040010`

## pseudocode

```c
_UNKNOWN **__fastcall LGetAgentXxx(
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
    Proxy = FindProxy(v25, a2[5], a4, &v24, &v30, 0);
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
0x18000b734  mov     rax, rsp
0x18000b737  mov     [rax+8], rbx
0x18000b73b  mov     [rax+20h], rsi
0x18000b73f  mov     [rax+18h], r8d
0x18000b743  push    rbp
0x18000b744  push    rdi
0x18000b745  push    r12
0x18000b747  push    r13
0x18000b749  push    r14
0x18000b74b  lea     rbp, [rax-4Fh]
0x18000b74f  sub     rsp, 0A0h
0x18000b756  xor     r13d, r13d
0x18000b759  mov     r12d, r9d
0x18000b75c  cmp     dword ptr [rdx+1Ch], 40000h
0x18000b763  mov     rbx, rdx
0x18000b766  mov     dword ptr [rbp+47h+var_50], r13d
0x18000b76a  mov     [rbp+47h+TargetHandle], r13
0x18000b76e  mov     qword ptr [rbp+47h+var_38], r13
0x18000b772  mov     dword ptr [rbp+47h+arg_8], r13d
0x18000b776  mov     [rbp+47h+var_40], r13
0x18000b77a  mov     [rbp+47h+var_48], r13
0x18000b77e  jbe     short loc_18000B78B
0x18000b780  mov     dword ptr [rdx], 80000048h
0x18000b786  jmp     loc_18000B917
0x18000b78b  mov     r8d, [rdx+10h]; int
0x18000b78f  lea     rax, [rbp+47h+var_40]
0x18000b793  mov     [rsp+0C0h+var_60], rax; __int64
0x18000b798  lea     r9, [rbp+47h+var_38]; int
0x18000b79c  lea     rax, [rbp+47h+arg_8]
0x18000b7a0  mov     [rsp+0C0h+var_68], rax; __int64
0x18000b7a5  mov     eax, [rdx+8]
0x18000b7a8  mov     edx, 2; int
0x18000b7ad  mov     [rsp+0C0h+var_70], eax; int
0x18000b7b1  lea     rax, [rbp+47h+var_48]
0x18000b7b5  mov     [rsp+0C0h+var_78], rax; __int64
0x18000b7ba  lea     rax, [rbp+47h+var_50]
0x18000b7be  mov     [rsp+0C0h+var_80], r13; __int64
0x18000b7c3  mov     [rsp+0C0h+var_88], r13d; int
0x18000b7c8  mov     [rsp+0C0h+var_90], rax; __int64
0x18000b7cd  lea     rax, [rbp+47h+TargetHandle]
0x18000b7d1  mov     [rsp+0C0h+lpTargetHandle], rax; lpTargetHandle
0x18000b7d6  mov     [rsp+0C0h+var_A0], r13d; int
0x18000b7db  call    LineProlog
0x18000b7e0  mov     rsi, [rbp+47h+var_48]
0x18000b7e4  mov     edi, eax
0x18000b7e6  test    eax, eax
0x18000b7e8  jle     loc_18000B8F9
0x18000b7ee  mov     r14d, [rbx+1Ch]
0x18000b7f2  mov     [rbp+47h+arg_10], r13d
0x18000b7f6  mov     [rbp+47h+var_48], r13
0x18000b7fa  cmp     r14d, [rbp+47h+arg_28]
0x18000b7fe  jnb     short loc_18000B80A
0x18000b800  mov     edi, 8000004Dh
0x18000b805  jmp     loc_18000B8F9
0x18000b80a  mov     edx, [rbx+14h]
0x18000b80d  lea     rax, [rbp+47h+arg_10]
0x18000b811  mov     rcx, [rbp+47h+var_40]
0x18000b815  lea     r9, [rbp+47h+var_48]
0x18000b819  mov     dword ptr [rsp+0C0h+lpTargetHandle], r13d
0x18000b81e  mov     r8d, r12d
0x18000b821  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18000b826  call    FindProxy
0x18000b82b  test    eax, eax
0x18000b82d  jz      short loc_18000B836
0x18000b82f  mov     edi, eax
0x18000b831  jmp     loc_18000B8F9
0x18000b836  mov     eax, [rbx+18h]
0x18000b839  mov     [rsi+50h], rax
0x18000b83d  mov     [rsi+58h], r14
0x18000b841  mov     eax, [rbx+0Ch]
0x18000b844  mov     [rsi+44h], eax
0x18000b847  cmp     [rbp+47h+var_48], r13
0x18000b84b  jz      short loc_18000B896
0x18000b84d  mov     rcx, [rbp+47h+var_48]
0x18000b851  lea     rax, [rbp+47h+var_40]
0x18000b855  mov     r9, rsi
0x18000b858  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18000b85d  mov     r8d, 8
0x18000b863  mov     [rbp+47h+var_40], r13
0x18000b867  mov     edx, r12d
0x18000b86a  call    CreateProxyRequest
0x18000b86f  test    eax, eax
0x18000b871  jnz     short loc_18000B82F
0x18000b873  mov     rdx, [rbp+47h+var_40]
0x18000b877  mov     r8, rsi
0x18000b87a  mov     eax, [rbx+14h]
0x18000b87d  mov     rcx, [rbp+47h+var_48]
0x18000b881  mov     [rdx+44h], eax
0x18000b884  mov     [rdx+48h], r14d
0x18000b888  call    SendProxyRequest
0x18000b88d  test    eax, eax
0x18000b88f  jnz     short loc_18000B82F
0x18000b891  mov     eax, [rsi+48h]
0x18000b894  jmp     short loc_18000B8F0
0x18000b896  mov     ecx, [rbp+47h+arg_10]
0x18000b899  call    GetLineLookupEntry
0x18000b89e  cmp     [rax+24h], r13d
0x18000b8a2  jz      short loc_18000B8F4
0x18000b8a4  mov     ecx, r14d
0x18000b8a7  call    AllocAsyncEventMsg
0x18000b8ac  test    rax, rax
0x18000b8af  jnz     short loc_18000B8B8
0x18000b8b1  mov     edi, 80000044h
0x18000b8b6  jmp     short loc_18000B8F9
0x18000b8b8  mov     rdx, qword ptr [rbp+47h+var_38]
0x18000b8bc  lea     r9, [rax+28h]
0x18000b8c0  lea     rcx, LGetAgentXxx_PostProcess
0x18000b8c7  mov     [rsi+30h], rcx
0x18000b8cb  mov     ecx, [rbp+47h+arg_20]
0x18000b8ce  mov     [rsi+60h], rax
0x18000b8d2  mov     rax, cs:pRemoteSP
0x18000b8d9  mov     [r9], r14d
0x18000b8dc  mov     r8d, [rbx+14h]
0x18000b8e0  mov     rax, [rax+rcx*8+80h]
0x18000b8e8  mov     ecx, [rsi+48h]
0x18000b8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8f0  mov     [rbx], eax
0x18000b8f2  jmp     short loc_18000B8F9
0x18000b8f4  mov     edi, 80000049h
0x18000b8f9  mov     eax, dword ptr [rbp+47h+arg_8]
0x18000b8fc  mov     edx, edi
0x18000b8fe  mov     r9d, dword ptr [rbp+47h+var_50]
0x18000b902  mov     rcx, rbx
0x18000b905  mov     r8, [rbp+47h+TargetHandle]
0x18000b909  mov     dword ptr [rsp+0C0h+lpTargetHandle], eax
0x18000b90d  mov     qword ptr [rsp+0C0h+var_A0], rsi
0x18000b912  call    LineEpilogAsync
0x18000b917  lea     r11, [rsp+0C0h+var_20]
0x18000b91f  mov     rbx, [r11+30h]
0x18000b923  mov     rsi, [r11+48h]
0x18000b927  mov     rsp, r11
0x18000b92a  pop     r14
0x18000b92c  pop     r13
0x18000b92e  pop     r12
0x18000b930  pop     rdi
0x18000b931  pop     rbp
0x18000b932  retn
```
