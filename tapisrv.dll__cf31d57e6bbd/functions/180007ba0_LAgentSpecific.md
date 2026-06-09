# LAgentSpecific

- ea: `0x180007ba0`
- end: `0x180007dea`
- name: `LAgentSpecific`
- size: `586`
- prototype: `__int64 __fastcall(int, _DWORD *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180028100`

## callees

- `0x18000289c`
- `0x1800038cc`
- `0x1800063d4`
- `0x180006f24`
- `0x180007244`
- `0x180007ba0`
- `0x180017adc`
- `0x180019fcc`
- `0x18001c114`
- `0x18003fb7c`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall LAgentSpecific(int a1, _DWORD *a2, unsigned int a3, __int64 a4)
{
  unsigned int v4; // r9d
  unsigned int v6; // r8d
  __int64 result; // rax
  int v10; // eax
  __int64 v11; // r14
  int v12; // esi
  unsigned int v13; // edx
  size_t v14; // r15
  int Proxy; // eax
  __int64 v16; // r12
  _DWORD *v17; // rbx
  int v18; // eax
  char *v19; // rax
  char *v20; // rbx
  __int64 v21; // [rsp+70h] [rbp-11h] BYREF
  __int64 v22; // [rsp+78h] [rbp-9h] BYREF
  __int64 v23; // [rsp+80h] [rbp-1h] BYREF
  int v24[2]; // [rsp+88h] [rbp+7h] BYREF
  HANDLE TargetHandle; // [rsp+90h] [rbp+Fh] BYREF
  __int64 v26; // [rsp+E8h] [rbp+67h] BYREF
  __int64 v27; // [rsp+F8h] [rbp+77h]

  v27 = a4;
  v4 = a2[8];
  v6 = a2[9];
  TargetHandle = 0;
  *(_QWORD *)v24 = 0;
  v21 = 0;
  v22 = 0;
  v26 = 0;
  result = IsBadSizeOffset(a3, 0, v6, v4, 4);
  if ( (_DWORD)result )
  {
    *a2 = -2147483576;
    return result;
  }
  v10 = LineProlog(
          a1,
          2,
          a2[4],
          (int)v24,
          0,
          &TargetHandle,
          (__int64)&v21 + 4,
          0,
          0,
          (__int64)&v26,
          a2[2],
          (__int64)&v21,
          (__int64)&v22);
  v11 = v26;
  v12 = v10;
  if ( v10 > 0 )
  {
    v13 = a2[5];
    v14 = (unsigned int)a2[9];
    LODWORD(v26) = 0;
    v23 = 0;
    Proxy = FindProxy(v22, v13, 6u, &v23, &v26, 0);
    if ( Proxy )
    {
LABEL_5:
      v12 = Proxy;
      return LineEpilogAsync((_DWORD)a2, v12, (_DWORD)TargetHandle, HIDWORD(v21), v11, v21);
    }
    v16 = v23;
    *(_QWORD *)(v11 + 80) = (unsigned int)a2[7];
    *(_QWORD *)(v11 + 88) = v14;
    *(_DWORD *)(v11 + 68) = a2[3];
    if ( v16 )
    {
      v26 = 0;
      Proxy = CreateProxyRequest(v16, 6u, (int)v14 + 12, v11, (ULONG **)&v26);
      if ( Proxy )
        goto LABEL_5;
      v17 = (_DWORD *)v26;
      *(_DWORD *)(v26 + 68) = a2[5];
      v17[18] = a2[6];
      v17[19] = v14;
      memcpy_0(v17 + 20, (const void *)(v27 + (unsigned int)a2[8]), v14);
      Proxy = SendProxyRequest(v16, v17, v11);
      if ( Proxy )
        goto LABEL_5;
      v18 = *(_DWORD *)(v11 + 72);
    }
    else
    {
      if ( !*((_DWORD *)GetLineLookupEntry(v26) + 9) )
      {
        v12 = -2147483575;
        return LineEpilogAsync((_DWORD)a2, v12, (_DWORD)TargetHandle, HIDWORD(v21), v11, v21);
      }
      v19 = (char *)AllocAsyncEventMsg(v14);
      if ( !v19 )
      {
        v12 = -2147483580;
        return LineEpilogAsync((_DWORD)a2, v12, (_DWORD)TargetHandle, HIDWORD(v21), v11, v21);
      }
      *(_QWORD *)(v11 + 48) = LDevSpecific_PostProcess;
      v20 = v19 + 40;
      *(_QWORD *)(v11 + 96) = v19;
      memcpy_0(v19 + 40, (const void *)(v27 + (unsigned int)a2[8]), v14);
      v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, char *, _DWORD))(pRemoteSP + 144))(
              *(unsigned int *)(v11 + 72),
              *(_QWORD *)v24,
              (unsigned int)a2[5],
              (unsigned int)a2[6],
              v20,
              v14);
    }
    *a2 = v18;
  }
  return LineEpilogAsync((_DWORD)a2, v12, (_DWORD)TargetHandle, HIDWORD(v21), v11, v21);
}

```

## disassembly

```asm
0x180007ba0  mov     [rsp-8+arg_0], rbx
0x180007ba5  mov     [rsp-8+arg_18], r9
0x180007baa  push    rbp
0x180007bab  push    rsi
0x180007bac  push    rdi
0x180007bad  push    r12
0x180007baf  push    r13
0x180007bb1  push    r14
0x180007bb3  push    r15
0x180007bb5  lea     rbp, [rsp-1Fh]
0x180007bba  sub     rsp, 0A0h
0x180007bc1  mov     r9d, [rdx+20h]
0x180007bc5  xor     r12d, r12d
0x180007bc8  mov     eax, r8d
0x180007bcb  mov     dword ptr [rbp+4Fh+var_60+4], r12d
0x180007bcf  mov     r8d, [rdx+24h]
0x180007bd3  mov     rdi, rdx
0x180007bd6  mov     rbx, rcx
0x180007bd9  mov     [rbp+4Fh+TargetHandle], r12
0x180007bdd  xor     edx, edx
0x180007bdf  mov     qword ptr [rbp+4Fh+var_48], r12
0x180007be3  mov     ecx, eax
0x180007be5  mov     dword ptr [rbp+4Fh+var_60], r12d
0x180007be9  mov     [rbp+4Fh+var_58], r12
0x180007bed  mov     [rbp+4Fh+arg_8], r12
0x180007bf1  mov     [rsp+0D0h+var_B0], 4
0x180007bf9  call    IsBadSizeOffset
0x180007bfe  test    eax, eax
0x180007c00  jz      short loc_180007C0D
0x180007c02  mov     dword ptr [rdi], 80000048h
0x180007c08  jmp     loc_180007DCF
0x180007c0d  mov     r8d, [rdi+10h]; int
0x180007c11  lea     rax, [rbp+4Fh+var_58]
0x180007c15  mov     [rsp+0D0h+var_70], rax; __int64
0x180007c1a  lea     r9, [rbp+4Fh+var_48]; int
0x180007c1e  lea     rax, [rbp+4Fh+var_60]
0x180007c22  mov     edx, 2; int
0x180007c27  mov     [rsp+0D0h+var_78], rax; __int64
0x180007c2c  mov     rcx, rbx; int
0x180007c2f  mov     eax, [rdi+8]
0x180007c32  mov     [rsp+0D0h+var_80], eax; int
0x180007c36  lea     rax, [rbp+4Fh+arg_8]
0x180007c3a  mov     [rsp+0D0h+var_88], rax; __int64
0x180007c3f  lea     rax, [rbp+4Fh+var_60+4]
0x180007c43  mov     [rsp+0D0h+var_90], r12; __int64
0x180007c48  mov     [rsp+0D0h+var_98], r12d; int
0x180007c4d  mov     [rsp+0D0h+var_A0], rax; __int64
0x180007c52  lea     rax, [rbp+4Fh+TargetHandle]
0x180007c56  mov     [rsp+0D0h+lpTargetHandle], rax; lpTargetHandle
0x180007c5b  mov     [rsp+0D0h+var_B0], r12d; int
0x180007c60  call    LineProlog
0x180007c65  mov     r14, [rbp+4Fh+arg_8]
0x180007c69  mov     esi, eax
0x180007c6b  test    eax, eax
0x180007c6d  jle     loc_180007DB1
0x180007c73  mov     edx, [rdi+14h]
0x180007c76  lea     rax, [rbp+4Fh+arg_8]
0x180007c7a  mov     rcx, [rbp+4Fh+var_58]
0x180007c7e  lea     r9, [rbp+4Fh+var_50]
0x180007c82  mov     r15d, [rdi+24h]
0x180007c86  mov     ebx, 6
0x180007c8b  mov     r8d, ebx
0x180007c8e  mov     dword ptr [rsp+0D0h+lpTargetHandle], r12d
0x180007c93  mov     dword ptr [rbp+4Fh+arg_8], r12d
0x180007c97  mov     [rbp+4Fh+var_50], r12
0x180007c9b  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180007ca0  call    FindProxy
0x180007ca5  test    eax, eax
0x180007ca7  jz      short loc_180007CB0
0x180007ca9  mov     esi, eax
0x180007cab  jmp     loc_180007DB1
0x180007cb0  mov     eax, [rdi+1Ch]
0x180007cb3  mov     r12, [rbp+4Fh+var_50]
0x180007cb7  mov     [r14+50h], rax
0x180007cbb  mov     [r14+58h], r15
0x180007cbf  mov     eax, [rdi+0Ch]
0x180007cc2  mov     [r14+44h], eax
0x180007cc6  test    r12, r12
0x180007cc9  jz      short loc_180007D34
0x180007ccb  lea     rax, [rbp+4Fh+arg_8]
0x180007ccf  mov     [rbp+4Fh+arg_8], 0
0x180007cd7  lea     r8d, [r15+0Ch]
0x180007cdb  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180007ce0  mov     r9, r14
0x180007ce3  mov     edx, ebx
0x180007ce5  mov     rcx, r12
0x180007ce8  call    CreateProxyRequest
0x180007ced  test    eax, eax
0x180007cef  jnz     short loc_180007CA9
0x180007cf1  mov     eax, [rdi+14h]
0x180007cf4  mov     r8, r15; Size
0x180007cf7  mov     rbx, [rbp+4Fh+arg_8]
0x180007cfb  mov     [rbx+44h], eax
0x180007cfe  lea     rcx, [rbx+50h]; void *
0x180007d02  mov     eax, [rdi+18h]
0x180007d05  mov     [rbx+48h], eax
0x180007d08  mov     [rbx+4Ch], r15d
0x180007d0c  mov     edx, [rdi+20h]
0x180007d0f  add     rdx, [rbp+4Fh+arg_18]; Src
0x180007d13  call    memcpy_0
0x180007d18  mov     r8, r14
0x180007d1b  mov     rdx, rbx
0x180007d1e  mov     rcx, r12
0x180007d21  call    SendProxyRequest
0x180007d26  test    eax, eax
0x180007d28  jnz     loc_180007CA9
0x180007d2e  mov     eax, [r14+48h]
0x180007d32  jmp     short loc_180007DA8
0x180007d34  mov     ecx, dword ptr [rbp+4Fh+arg_8]
0x180007d37  call    GetLineLookupEntry
0x180007d3c  cmp     dword ptr [rax+24h], 0
0x180007d40  jz      short loc_180007DAC
0x180007d42  mov     ecx, r15d
0x180007d45  call    AllocAsyncEventMsg
0x180007d4a  test    rax, rax
0x180007d4d  jnz     short loc_180007D56
0x180007d4f  mov     esi, 80000044h
0x180007d54  jmp     short loc_180007DB1
0x180007d56  lea     rcx, LDevSpecific_PostProcess
0x180007d5d  mov     r8, r15; Size
0x180007d60  mov     [r14+30h], rcx
0x180007d64  lea     rbx, [rax+28h]
0x180007d68  mov     [r14+60h], rax
0x180007d6c  mov     rcx, rbx; void *
0x180007d6f  mov     edx, [rdi+20h]
0x180007d72  add     rdx, [rbp+4Fh+arg_18]; Src
0x180007d76  call    memcpy_0
0x180007d7b  mov     rax, cs:pRemoteSP
0x180007d82  mov     r9d, [rdi+18h]
0x180007d86  mov     r8d, [rdi+14h]
0x180007d8a  mov     rdx, qword ptr [rbp+4Fh+var_48]
0x180007d8e  mov     rax, [rax+90h]
0x180007d95  mov     ecx, [r14+48h]
0x180007d99  mov     dword ptr [rsp+0D0h+lpTargetHandle], r15d
0x180007d9e  mov     qword ptr [rsp+0D0h+var_B0], rbx
0x180007da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007da8  mov     [rdi], eax
0x180007daa  jmp     short loc_180007DB1
0x180007dac  mov     esi, 80000049h
0x180007db1  mov     eax, dword ptr [rbp+4Fh+var_60]
0x180007db4  mov     edx, esi
0x180007db6  mov     r9d, dword ptr [rbp+4Fh+var_60+4]
0x180007dba  mov     rcx, rdi
0x180007dbd  mov     r8, [rbp+4Fh+TargetHandle]
0x180007dc1  mov     dword ptr [rsp+0D0h+lpTargetHandle], eax
0x180007dc5  mov     qword ptr [rsp+0D0h+var_B0], r14
0x180007dca  call    LineEpilogAsync
0x180007dcf  mov     rbx, [rsp+0D0h+arg_0]
0x180007dd7  add     rsp, 0A0h
0x180007dde  pop     r15
0x180007de0  pop     r14
0x180007de2  pop     r13
0x180007de4  pop     r12
0x180007de6  pop     rdi
0x180007de7  pop     rsi
0x180007de8  pop     rbp
0x180007de9  retn
```
