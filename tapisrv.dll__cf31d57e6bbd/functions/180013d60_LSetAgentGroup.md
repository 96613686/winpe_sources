# LSetAgentGroup

- ea: `0x180013d60`
- end: `0x180013f7f`
- name: `LSetAgentGroup`
- size: `543`
- prototype: `__int64 __fastcall(__int64, unsigned int *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180028100`

## callees

- `0x1800038cc`
- `0x1800063d4`
- `0x180006f24`
- `0x180007244`
- `0x180007394`
- `0x180013d60`
- `0x180017adc`
- `0x180019fcc`
- `0x18001c114`
- `0x18003fb7c`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall LSetAgentGroup(__int64 a1, unsigned int *a2, unsigned int a3, __int64 a4)
{
  unsigned int v5; // r8d
  int v8; // eax
  __int64 v9; // r15
  int v10; // edi
  __int64 v11; // rbx
  unsigned int v12; // r8d
  unsigned int *v13; // rsi
  __int64 v14; // rbx
  int Proxy; // eax
  __int64 v16; // r12
  int v17; // r8d
  __int64 v18; // rbx
  unsigned int v19; // eax
  unsigned int v21; // [rsp+50h] [rbp-41h]
  __int64 v22; // [rsp+70h] [rbp-21h] BYREF
  __int64 v23; // [rsp+78h] [rbp-19h] BYREF
  __int64 v24; // [rsp+80h] [rbp-11h] BYREF
  int v25[2]; // [rsp+88h] [rbp-9h] BYREF
  HANDLE TargetHandle; // [rsp+90h] [rbp-1h] BYREF
  __int64 v27; // [rsp+F8h] [rbp+67h] BYREF

  v5 = a2[3];
  v21 = a2[2];
  TargetHandle = 0;
  *(_QWORD *)v25 = 0;
  v22 = 0;
  v23 = 0;
  v27 = 0;
  v8 = LineProlog(
         a1,
         2,
         v5,
         (unsigned int *)v25,
         0,
         &TargetHandle,
         (_DWORD *)&v22 + 1,
         0,
         0,
         &v27,
         v21,
         (unsigned int *)&v22,
         (char **)&v23);
  v9 = v27;
  v10 = v8;
  if ( v8 > 0 )
  {
    v11 = a2[5];
    v12 = a2[5];
    LODWORD(v27) = 0;
    v24 = 0;
    if ( (unsigned int)IsBadStructParam(a3, a4, v12)
      || (v13 = (unsigned int *)(v11 + a4), v14 = *v13, (unsigned int)v14 < 0x18) )
    {
      v10 = -2147483571;
    }
    else
    {
      if ( !IsBadSizeOffset(v14, 0x18u, v13[4], v13[5], guiAlignmentFaultEnabled != 0 ? 4 : 0)
        && v13[3] <= (v14 - 24) / 0x18uLL )
      {
        Proxy = FindProxy(v23, a2[4], 1u, &v24, &v27, 0);
        if ( Proxy )
        {
LABEL_9:
          v10 = Proxy;
          return LineEpilogAsync(a2, v10, (__int64)TargetHandle, HIDWORD(v22), v9, v22);
        }
        v16 = v24;
        if ( v24 )
        {
          v17 = *v13 + 4;
          v27 = 0;
          Proxy = CreateProxyRequest(v24, 1u, v17, v9, (ULONG **)&v27);
          if ( Proxy )
            goto LABEL_9;
          v18 = v27;
          *(_DWORD *)(v27 + 68) = a2[4];
          memcpy_0((void *)(v18 + 72), v13, *v13);
          Proxy = SendProxyRequest(v16, v18, v9);
          if ( Proxy )
            goto LABEL_9;
          v19 = *(_DWORD *)(v9 + 72);
        }
        else
        {
          if ( !*((_DWORD *)GetLineLookupEntry(v27) + 9) )
          {
            v10 = -2147483575;
            return LineEpilogAsync(a2, v10, (__int64)TargetHandle, HIDWORD(v22), v9, v22);
          }
          v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned int *))(pRemoteSP + 552))(
                  *(unsigned int *)(v9 + 72),
                  *(_QWORD *)v25,
                  a2[4],
                  v13);
        }
        *a2 = v19;
        return LineEpilogAsync(a2, v10, (__int64)TargetHandle, HIDWORD(v22), v9, v22);
      }
      v10 = -2147483560;
    }
  }
  return LineEpilogAsync(a2, v10, (__int64)TargetHandle, HIDWORD(v22), v9, v22);
}

```

## disassembly

```asm
0x180013d60  push    rbp
0x180013d62  push    rbx
0x180013d63  push    rsi
0x180013d64  push    rdi
0x180013d65  push    r12
0x180013d67  push    r13
0x180013d69  push    r14
0x180013d6b  push    r15
0x180013d6d  lea     rbp, [rsp-17h]
0x180013d72  sub     rsp, 0A8h
0x180013d79  xor     r13d, r13d
0x180013d7c  lea     rax, [rbp+4Fh+var_68]
0x180013d80  mov     [rsp+0E0h+var_80], rax; __int64
0x180013d85  mov     r12d, r8d
0x180013d88  mov     r8d, [rdx+0Ch]; int
0x180013d8c  lea     rax, [rbp+4Fh+var_70]
0x180013d90  mov     [rsp+0E0h+var_88], rax; __int64
0x180013d95  mov     rsi, r9
0x180013d98  mov     eax, [rdx+8]
0x180013d9b  lea     r9, [rbp+4Fh+var_58]; int
0x180013d9f  mov     [rsp+0E0h+var_90], eax; int
0x180013da3  mov     r14, rdx
0x180013da6  lea     rax, [rbp+4Fh+arg_8]
0x180013daa  mov     dword ptr [rbp+4Fh+var_70+4], r13d
0x180013dae  mov     [rsp+0E0h+var_98], rax; __int64
0x180013db3  lea     edx, [r13+2]; int
0x180013db7  mov     [rsp+0E0h+var_A0], r13; __int64
0x180013dbc  lea     rax, [rbp+4Fh+var_70+4]
0x180013dc0  mov     [rsp+0E0h+var_A8], r13d; int
0x180013dc5  mov     [rsp+0E0h+var_B0], rax; __int64
0x180013dca  lea     rax, [rbp+4Fh+TargetHandle]
0x180013dce  mov     [rsp+0E0h+lpTargetHandle], rax; lpTargetHandle
0x180013dd3  mov     [rsp+0E0h+var_C0], r13d; int
0x180013dd8  mov     [rbp+4Fh+TargetHandle], r13
0x180013ddc  mov     qword ptr [rbp+4Fh+var_58], r13
0x180013de0  mov     dword ptr [rbp+4Fh+var_70], r13d
0x180013de4  mov     [rbp+4Fh+var_68], r13
0x180013de8  mov     [rbp+4Fh+arg_8], r13
0x180013dec  call    LineProlog
0x180013df1  mov     r15, [rbp+4Fh+arg_8]
0x180013df5  mov     edi, eax
0x180013df7  test    eax, eax
0x180013df9  jle     loc_180013F4D
0x180013dff  mov     ebx, [r14+14h]
0x180013e03  mov     rdx, rsi
0x180013e06  mov     r8d, ebx
0x180013e09  mov     dword ptr [rbp+4Fh+arg_8], r13d
0x180013e0d  mov     ecx, r12d
0x180013e10  mov     [rbp+4Fh+var_60], r13
0x180013e14  call    IsBadStructParam
0x180013e19  test    eax, eax
0x180013e1b  jz      short loc_180013E27
0x180013e1d  mov     edi, 8000004Dh
0x180013e22  jmp     loc_180013F4D
0x180013e27  add     rsi, rbx
0x180013e2a  mov     ebx, [rsi]
0x180013e2c  cmp     ebx, 18h
0x180013e2f  jb      short loc_180013E1D
0x180013e31  mov     eax, cs:guiAlignmentFaultEnabled
0x180013e37  mov     edx, 18h
0x180013e3c  mov     r9d, [rsi+14h]
0x180013e40  neg     eax
0x180013e42  mov     r8d, [rsi+10h]
0x180013e46  sbb     ecx, ecx
0x180013e48  and     ecx, 4
0x180013e4b  mov     [rsp+0E0h+var_C0], ecx
0x180013e4f  mov     ecx, ebx
0x180013e51  call    IsBadSizeOffset
0x180013e56  test    eax, eax
0x180013e58  jz      short loc_180013E64
0x180013e5a  mov     edi, 80000058h
0x180013e5f  jmp     loc_180013F4D
0x180013e64  lea     rcx, [rbx-18h]
0x180013e68  mov     rax, 0AAAAAAAAAAAAAAABh
0x180013e72  mul     rcx
0x180013e75  mov     eax, [rsi+0Ch]
0x180013e78  shr     rdx, 4
0x180013e7c  cmp     rax, rdx
0x180013e7f  ja      short loc_180013E5A
0x180013e81  mov     edx, [r14+10h]
0x180013e85  lea     rax, [rbp+4Fh+arg_8]
0x180013e89  mov     rcx, [rbp+4Fh+var_68]
0x180013e8d  lea     r9, [rbp+4Fh+var_60]
0x180013e91  mov     ebx, 1
0x180013e96  mov     dword ptr [rsp+0E0h+lpTargetHandle], r13d
0x180013e9b  mov     r8d, ebx
0x180013e9e  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180013ea3  call    FindProxy
0x180013ea8  test    eax, eax
0x180013eaa  jz      short loc_180013EB3
0x180013eac  mov     edi, eax
0x180013eae  jmp     loc_180013F4D
0x180013eb3  mov     r12, [rbp+4Fh+var_60]
0x180013eb7  test    r12, r12
0x180013eba  jz      short loc_180013F13
0x180013ebc  mov     r8d, [rsi]
0x180013ebf  lea     rax, [rbp+4Fh+arg_8]
0x180013ec3  add     r8d, 4
0x180013ec7  mov     [rbp+4Fh+arg_8], r13
0x180013ecb  mov     r9, r15
0x180013ece  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180013ed3  mov     edx, ebx
0x180013ed5  mov     rcx, r12
0x180013ed8  call    CreateProxyRequest
0x180013edd  test    eax, eax
0x180013edf  jnz     short loc_180013EAC
0x180013ee1  mov     rbx, [rbp+4Fh+arg_8]
0x180013ee5  mov     rdx, rsi; Src
0x180013ee8  mov     eax, [r14+10h]
0x180013eec  mov     [rbx+44h], eax
0x180013eef  lea     rcx, [rbx+48h]; void *
0x180013ef3  mov     r8d, [rsi]; Size
0x180013ef6  call    memcpy_0
0x180013efb  mov     r8, r15
0x180013efe  mov     rdx, rbx
0x180013f01  mov     rcx, r12
0x180013f04  call    SendProxyRequest
0x180013f09  test    eax, eax
0x180013f0b  jnz     short loc_180013EAC
0x180013f0d  mov     eax, [r15+48h]
0x180013f11  jmp     short loc_180013F43
0x180013f13  mov     ecx, dword ptr [rbp+4Fh+arg_8]
0x180013f16  call    GetLineLookupEntry
0x180013f1b  cmp     [rax+24h], r13d
0x180013f1f  jz      short loc_180013F48
0x180013f21  mov     rax, cs:pRemoteSP
0x180013f28  mov     r9, rsi
0x180013f2b  mov     r8d, [r14+10h]
0x180013f2f  mov     rdx, qword ptr [rbp+4Fh+var_58]
0x180013f33  mov     ecx, [r15+48h]
0x180013f37  mov     rax, [rax+228h]
0x180013f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f43  mov     [r14], eax
0x180013f46  jmp     short loc_180013F4D
0x180013f48  mov     edi, 80000049h
0x180013f4d  mov     eax, dword ptr [rbp+4Fh+var_70]
0x180013f50  mov     edx, edi
0x180013f52  mov     r9d, dword ptr [rbp+4Fh+var_70+4]
0x180013f56  mov     rcx, r14
0x180013f59  mov     r8, [rbp+4Fh+TargetHandle]
0x180013f5d  mov     dword ptr [rsp+0E0h+lpTargetHandle], eax
0x180013f61  mov     qword ptr [rsp+0E0h+var_C0], r15
0x180013f66  call    LineEpilogAsync
0x180013f6b  add     rsp, 0A8h
0x180013f72  pop     r15
0x180013f74  pop     r14
0x180013f76  pop     r13
0x180013f78  pop     r12
0x180013f7a  pop     rdi
0x180013f7b  pop     rsi
0x180013f7c  pop     rbx
0x180013f7d  pop     rbp
0x180013f7e  retn
```
