# LGetAgentCaps

- ea: `0x18000b170`
- end: `0x18000b42c`
- name: `LGetAgentCaps`
- size: `700`
- prototype: `_UNKNOWN **__fastcall(int, ULONG *, ULONG)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180028100`

## callees

- `0x18000289c`
- `0x1800038cc`
- `0x18000b170`
- `0x180017adc`
- `0x180019fcc`
- `0x18001c114`
- `0x180040010`

## pseudocode

```c
_UNKNOWN **__fastcall LGetAgentCaps(int a1, ULONG *a2, ULONG a3)
{
  _UNKNOWN **result; // rax
  int v5; // ebx
  unsigned int v6; // eax
  __int64 v7; // r15
  __int64 v8; // rsi
  void *v9; // r14
  __int64 v10; // rcx
  int v11; // eax
  ULONG *v12; // rdx
  ULONG v13; // eax
  _DWORD *v14; // rax
  __int64 v15; // [rsp+74h] [rbp-44h] BYREF
  __int64 v16; // [rsp+80h] [rbp-38h] BYREF
  __int64 v17; // [rsp+88h] [rbp-30h] BYREF
  HANDLE TargetHandle[2]; // [rsp+90h] [rbp-28h] BYREF
  _UNKNOWN *retaddr; // [rsp+B8h] [rbp+0h] BYREF
  ULONG *v20; // [rsp+C8h] [rbp+10h] BYREF
  int v21; // [rsp+D0h] [rbp+18h] BYREF

  result = &retaddr;
  v20 = a2;
  v21 = 0;
  TargetHandle[0] = 0;
  v15 = 0;
  v17 = 0;
  v16 = 0;
  if ( a2[9] > a3 )
  {
    *a2 = -2147483576;
    return result;
  }
  v5 = LineProlog(
         a1,
         3,
         a2[4],
         (int)&v21,
         a2[5],
         TargetHandle,
         (__int64)&v15 + 4,
         0,
         0,
         (__int64)&v16,
         a2[2],
         (__int64)&v15,
         (__int64)&v17);
  if ( v5 <= 0 )
    goto LABEL_30;
  if ( a2[7] == 0x20000 || a2[7] == 131073 )
  {
    v6 = 56;
  }
  else
  {
    if ( a2[7] != 131074 && a2[7] - 196608 >= 2 )
    {
      v5 = -2147483636;
LABEL_30:
      v8 = v16;
      return (_UNKNOWN **)LineEpilogAsync((_DWORD)a2, v5, TargetHandle[0], HIDWORD(v15), v8, v15);
    }
    v6 = 72;
  }
  v7 = a2[9];
  v8 = v16;
  if ( (unsigned int)v7 >= v6 )
  {
    v9 = 0;
    *(_QWORD *)(v16 + 80) = a2[8];
    *(_QWORD *)(v8 + 88) = v7;
    *(_DWORD *)(v8 + 68) = a2[3];
    v10 = *(_QWORD *)(v17 + 8);
    if ( v10 )
    {
      v9 = *(void **)(v10 + 56);
      TargetHandle[1] = v9;
      if ( a2[6] >= *(_DWORD *)(v10 + 228) )
      {
        v5 = -2147483631;
        return (_UNKNOWN **)LineEpilogAsync((_DWORD)a2, v5, TargetHandle[0], HIDWORD(v15), v8, v15);
      }
      if ( *(_DWORD *)v10 != 1162758476 )
      {
        v5 = -2147483605;
        return (_UNKNOWN **)LineEpilogAsync((_DWORD)a2, v5, TargetHandle[0], HIDWORD(v15), v8, v15);
      }
    }
    if ( v9 )
    {
      v20 = 0;
      v11 = CreateProxyRequest((__int64)v9, 4u, 8, v8, &v20);
      if ( v11 || (v12 = v20, v20[17] = a2[6], v12[18] = v7, (v11 = SendProxyRequest(v9, v12, v8)) != 0) )
      {
        v5 = v11;
        return (_UNKNOWN **)LineEpilogAsync((_DWORD)a2, v5, TargetHandle[0], HIDWORD(v15), v8, v15);
      }
      LODWORD(v9) = 1;
      v13 = *(_DWORD *)(v8 + 72);
    }
    else
    {
      if ( !*(_DWORD *)(v17 + 36) )
        goto LABEL_28;
      v14 = AllocAsyncEventMsg(v7);
      if ( !v14 )
      {
        v5 = -2147483580;
        return (_UNKNOWN **)LineEpilogAsync((_DWORD)a2, v5, TargetHandle[0], HIDWORD(v15), v8, v15);
      }
      LODWORD(v9) = 1;
      *(_QWORD *)(v8 + 48) = LGetAgentXxx_PostProcess;
      *(_QWORD *)(v8 + 96) = v14;
      v14[10] = v7;
      v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD *))(pRemoteSP + 304))(
              *(unsigned int *)(v8 + 72),
              (unsigned int)v21,
              a2[6],
              a2[7],
              v14 + 10);
    }
    *a2 = v13;
LABEL_28:
    if ( !(_DWORD)v9 )
      v5 = -2147483575;
    return (_UNKNOWN **)LineEpilogAsync((_DWORD)a2, v5, TargetHandle[0], HIDWORD(v15), v8, v15);
  }
  v5 = -2147483571;
  return (_UNKNOWN **)LineEpilogAsync((_DWORD)a2, v5, TargetHandle[0], HIDWORD(v15), v8, v15);
}

```

## disassembly

```asm
0x18000b170  mov     rax, rsp
0x18000b173  mov     [rax+8], rbx
0x18000b177  mov     [rax+20h], rsi
0x18000b17b  mov     [rax+10h], rdx
0x18000b17f  push    rdi
0x18000b180  push    r14
0x18000b182  push    r15
0x18000b184  sub     rsp, 0A0h
0x18000b18b  mov     rdi, rdx
0x18000b18e  mov     dword ptr [rax-40h], 0
0x18000b195  mov     dword ptr [rax+18h], 0
0x18000b19c  mov     qword ptr [rax-28h], 0
0x18000b1a4  mov     dword ptr [rax-44h], 0
0x18000b1ab  mov     qword ptr [rax-30h], 0
0x18000b1b3  mov     qword ptr [rax-38h], 0
0x18000b1bb  cmp     [rdx+24h], r8d
0x18000b1bf  jbe     short loc_18000B1CC
0x18000b1c1  mov     dword ptr [rdx], 80000048h
0x18000b1c7  jmp     loc_18000B413
0x18000b1cc  lea     rax, [rsp+0B8h+var_30]
0x18000b1d4  mov     [rsp+0B8h+var_58], rax; __int64
0x18000b1d9  lea     rax, [rsp+0B8h+var_44]
0x18000b1de  mov     [rsp+0B8h+var_60], rax; __int64
0x18000b1e3  mov     eax, [rdx+8]
0x18000b1e6  mov     [rsp+0B8h+var_68], eax; int
0x18000b1ea  lea     rax, [rsp+0B8h+var_38]
0x18000b1f2  mov     [rsp+0B8h+var_70], rax; __int64
0x18000b1f7  mov     [rsp+0B8h+var_78], 0; __int64
0x18000b200  mov     [rsp+0B8h+var_80], 0; int
0x18000b208  lea     rax, [rsp+0B8h+var_44+4]
0x18000b20d  mov     [rsp+0B8h+var_88], rax; __int64
0x18000b212  lea     rax, [rsp+0B8h+TargetHandle]
0x18000b21a  mov     [rsp+0B8h+lpTargetHandle], rax; lpTargetHandle
0x18000b21f  mov     eax, [rdx+14h]
0x18000b222  mov     [rsp+0B8h+var_98], eax; int
0x18000b226  lea     r9, [rsp+0B8h+arg_10]; int
0x18000b22e  mov     r8d, [rdx+10h]; int
0x18000b232  mov     edx, 3; int
0x18000b237  call    LineProlog
0x18000b23c  mov     ebx, eax
0x18000b23e  test    eax, eax
0x18000b240  jle     loc_18000B3E7
0x18000b246  mov     eax, [rdi+1Ch]
0x18000b249  sub     eax, 20000h
0x18000b24e  jz      short loc_18000B277
0x18000b250  sub     eax, 1
0x18000b253  jz      short loc_18000B277
0x18000b255  sub     eax, 1
0x18000b258  jz      short loc_18000B270
0x18000b25a  sub     eax, 0FFFEh
0x18000b25f  jz      short loc_18000B270
0x18000b261  cmp     eax, 1
0x18000b264  jz      short loc_18000B270
0x18000b266  mov     ebx, 8000000Ch
0x18000b26b  jmp     loc_18000B3E7
0x18000b270  mov     eax, 48h ; 'H'
0x18000b275  jmp     short loc_18000B27C
0x18000b277  mov     eax, 38h ; '8'
0x18000b27c  mov     r15d, [rdi+24h]
0x18000b280  mov     rsi, [rsp+0B8h+var_38]
0x18000b288  cmp     r15d, eax
0x18000b28b  jnb     short loc_18000B297
0x18000b28d  mov     ebx, 8000004Dh
0x18000b292  jmp     loc_18000B3EF
0x18000b297  xor     r14d, r14d
0x18000b29a  mov     eax, [rdi+20h]
0x18000b29d  mov     [rsi+50h], rax
0x18000b2a1  mov     [rsi+58h], r15
0x18000b2a5  mov     eax, [rdi+0Ch]
0x18000b2a8  mov     [rsi+44h], eax
0x18000b2ab  mov     rdx, [rsp+0B8h+var_30]
0x18000b2b3  mov     rcx, [rdx+8]
0x18000b2b7  test    rcx, rcx
0x18000b2ba  jz      short loc_18000B2F7
0x18000b2bc  mov     r14, [rcx+38h]
0x18000b2c0  mov     [rsp+0B8h+var_20], r14
0x18000b2c8  mov     eax, [rcx+0E4h]
0x18000b2ce  cmp     [rdi+18h], eax
0x18000b2d1  jb      short loc_18000B2E1
0x18000b2d3  mov     ebx, 80000011h
0x18000b2d8  mov     [rsp+0B8h+var_48], ebx
0x18000b2dc  jmp     loc_18000B3EF
0x18000b2e1  cmp     dword ptr [rcx], 454E494Ch
0x18000b2e7  jz      short loc_18000B2F7
0x18000b2e9  mov     ebx, 8000002Bh
0x18000b2ee  mov     [rsp+0B8h+var_48], ebx
0x18000b2f2  jmp     loc_18000B3EF
0x18000b2f7  test    r14, r14
0x18000b2fa  jz      short loc_18000B35E
0x18000b2fc  mov     [rsp+0B8h+arg_8], 0
0x18000b308  lea     rax, [rsp+0B8h+arg_8]
0x18000b310  mov     qword ptr [rsp+0B8h+var_98], rax
0x18000b315  mov     r9, rsi
0x18000b318  mov     edx, 4
0x18000b31d  lea     r8d, [rdx+4]
0x18000b321  mov     rcx, r14
0x18000b324  call    CreateProxyRequest
0x18000b329  test    eax, eax
0x18000b32b  jz      short loc_18000B334
0x18000b32d  mov     ebx, eax
0x18000b32f  jmp     loc_18000B3EF
0x18000b334  mov     eax, [rdi+18h]
0x18000b337  mov     rdx, [rsp+0B8h+arg_8]
0x18000b33f  mov     [rdx+44h], eax
0x18000b342  mov     [rdx+48h], r15d
0x18000b346  mov     r8, rsi
0x18000b349  mov     rcx, r14
0x18000b34c  call    SendProxyRequest
0x18000b351  test    eax, eax
0x18000b353  jnz     short loc_18000B32D
0x18000b355  lea     r14d, [rax+1]
0x18000b359  mov     eax, [rsi+48h]
0x18000b35c  jmp     short loc_18000B3BE
0x18000b35e  cmp     [rdx+24h], r14d
0x18000b362  jz      short loc_18000B3C0
0x18000b364  mov     ecx, r15d
0x18000b367  call    AllocAsyncEventMsg
0x18000b36c  test    rax, rax
0x18000b36f  jnz     short loc_18000B378
0x18000b371  mov     ebx, 80000044h
0x18000b376  jmp     short loc_18000B3EF
0x18000b378  mov     r14d, 1
0x18000b37e  lea     rcx, LGetAgentXxx_PostProcess
0x18000b385  mov     [rsi+30h], rcx
0x18000b389  mov     [rsi+60h], rax
0x18000b38d  lea     rcx, [rax+28h]
0x18000b391  mov     [rcx], r15d
0x18000b394  mov     rax, cs:pRemoteSP
0x18000b39b  mov     qword ptr [rsp+0B8h+var_98], rcx
0x18000b3a0  mov     r9d, [rdi+1Ch]
0x18000b3a4  mov     r8d, [rdi+18h]
0x18000b3a8  mov     edx, [rsp+0B8h+arg_10]
0x18000b3af  mov     ecx, [rsi+48h]
0x18000b3b2  mov     rax, [rax+130h]
0x18000b3b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3be  mov     [rdi], eax
0x18000b3c0  test    r14d, r14d
0x18000b3c3  jnz     short loc_18000B3EF
0x18000b3c5  mov     ebx, 80000049h
0x18000b3ca  jmp     short loc_18000B3EF
0x18000b3cc  mov     ebx, 80000049h
0x18000b3d1  mov     [rsp+0B8h+var_48], ebx
0x18000b3d5  mov     rdi, [rsp+0B8h+arg_8]
0x18000b3dd  mov     rsi, [rsp+0B8h+var_38]
0x18000b3e5  jmp     short loc_18000B3EF
0x18000b3e7  mov     rsi, [rsp+0B8h+var_38]
0x18000b3ef  mov     eax, dword ptr [rsp+0B8h+var_44]
0x18000b3f3  mov     dword ptr [rsp+0B8h+lpTargetHandle], eax
0x18000b3f7  mov     qword ptr [rsp+0B8h+var_98], rsi
0x18000b3fc  mov     r9d, dword ptr [rsp+0B8h+var_44+4]
0x18000b401  mov     r8, [rsp+0B8h+TargetHandle]
0x18000b409  mov     edx, ebx
0x18000b40b  mov     rcx, rdi
0x18000b40e  call    LineEpilogAsync
0x18000b413  lea     r11, [rsp+0B8h+var_18]
0x18000b41b  mov     rbx, [r11+20h]
0x18000b41f  mov     rsi, [r11+38h]
0x18000b423  mov     rsp, r11
0x18000b426  pop     r15
0x18000b428  pop     r14
0x18000b42a  pop     rdi
0x18000b42b  retn
```
