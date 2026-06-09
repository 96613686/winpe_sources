# LSetAgentActivity

- ea: `0x180013bd0`
- end: `0x180013d5a`
- name: `LSetAgentActivity`
- size: `394`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180028100`

## callees

- `0x1800038cc`
- `0x1800063d4`
- `0x180006f24`
- `0x180013bd0`
- `0x180017adc`
- `0x180019fcc`
- `0x18001c114`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall LSetAgentActivity(__int64 a1, unsigned int *a2)
{
  unsigned int v2; // r8d
  int v4; // eax
  ULONG *v5; // rsi
  int v6; // edi
  unsigned int v7; // edx
  int Proxy; // eax
  ULONG *v9; // rdx
  __int64 v10; // rcx
  unsigned int v11; // eax
  unsigned int v13; // [rsp+58h] [rbp-11h]
  unsigned int v14; // [rsp+78h] [rbp+Fh] BYREF
  unsigned int v15[3]; // [rsp+7Ch] [rbp+13h] BYREF
  char *v16; // [rsp+88h] [rbp+1Fh] BYREF
  int v17[2]; // [rsp+90h] [rbp+27h] BYREF
  HANDLE TargetHandle; // [rsp+98h] [rbp+2Fh] BYREF
  ULONG *v19; // [rsp+D0h] [rbp+67h] BYREF

  v2 = a2[3];
  v13 = a2[2];
  v15[0] = 0;
  TargetHandle = 0;
  *(_QWORD *)v17 = 0;
  v14 = 0;
  v16 = 0;
  v19 = 0;
  v4 = LineProlog(a1, 2, v2, (unsigned int *)v17, 0, &TargetHandle, v15, 0, 0, &v19, v13, &v14, &v16);
  v5 = v19;
  v6 = v4;
  if ( v4 > 0 )
  {
    v7 = a2[4];
    LODWORD(v19) = 0;
    *(_QWORD *)&v15[1] = 0;
    Proxy = FindProxy((__int64)v16, v7, 3u, &v15[1], &v19, 0);
    if ( Proxy )
    {
LABEL_3:
      v6 = Proxy;
      return LineEpilogAsync(a2, v6, (__int64)TargetHandle, v15[0], (__int64)v5, v14);
    }
    if ( *(_QWORD *)&v15[1] )
    {
      v19 = 0;
      Proxy = CreateProxyRequest(*(__int64 *)&v15[1], 3u, 8, (__int64)v5, &v19);
      if ( Proxy )
        goto LABEL_3;
      v9 = v19;
      v10 = *(_QWORD *)&v15[1];
      v19[17] = a2[4];
      v9[18] = a2[5];
      Proxy = SendProxyRequest(v10, v9, v5);
      if ( Proxy )
        goto LABEL_3;
      v11 = v5[18];
    }
    else
    {
      if ( !*((_DWORD *)GetLineLookupEntry((unsigned int)v19) + 9) )
      {
        v6 = -2147483575;
        return LineEpilogAsync(a2, v6, (__int64)TargetHandle, v15[0], (__int64)v5, v14);
      }
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(pRemoteSP + 544))(
              v5[18],
              *(_QWORD *)v17,
              a2[4],
              a2[5]);
    }
    *a2 = v11;
  }
  return LineEpilogAsync(a2, v6, (__int64)TargetHandle, v15[0], (__int64)v5, v14);
}

```

## disassembly

```asm
0x180013bd0  mov     r11, rsp
0x180013bd3  mov     [r11+8], rbx
0x180013bd7  mov     [r11+18h], rsi
0x180013bdb  push    rbp
0x180013bdc  push    rdi
0x180013bdd  push    r15
0x180013bdf  lea     rbp, [r11-57h]
0x180013be3  sub     rsp, 0A0h
0x180013bea  mov     r8d, [rdx+0Ch]; int
0x180013bee  lea     rax, [rbp+4Fh+var_30]
0x180013bf2  mov     [r11-58h], rax
0x180013bf6  lea     r9, [rbp+4Fh+var_28]; int
0x180013bfa  xor     r15d, r15d
0x180013bfd  lea     rax, [rbp+4Fh+var_40]
0x180013c01  mov     [r11-60h], rax
0x180013c05  mov     rbx, rdx
0x180013c08  mov     eax, [rdx+8]
0x180013c0b  mov     [rsp+0B0h+var_60], eax; int
0x180013c0f  lea     rax, [rbp+4Fh+arg_8]
0x180013c13  mov     [r11-70h], rax
0x180013c17  lea     edx, [r15+2]; int
0x180013c1b  mov     [r11-78h], r15
0x180013c1f  lea     rax, [rbp+4Fh+var_3C]
0x180013c23  mov     [r11-80h], r15d
0x180013c27  mov     [rsp+0B0h+var_80], rax; __int64
0x180013c2c  lea     rax, [rbp+4Fh+TargetHandle]
0x180013c30  mov     [rsp+0B0h+lpTargetHandle], rax; lpTargetHandle
0x180013c35  mov     [rsp+0B0h+var_90], r15d; int
0x180013c3a  mov     dword ptr [rbp+4Fh+var_3C], r15d
0x180013c3e  mov     [rbp+4Fh+TargetHandle], r15
0x180013c42  mov     qword ptr [rbp+4Fh+var_28], r15
0x180013c46  mov     [rbp+4Fh+var_40], r15d
0x180013c4a  mov     [rbp+4Fh+var_30], r15
0x180013c4e  mov     [rbp+4Fh+arg_8], r15
0x180013c52  call    LineProlog
0x180013c57  mov     rsi, [rbp+4Fh+arg_8]
0x180013c5b  mov     edi, eax
0x180013c5d  test    eax, eax
0x180013c5f  jle     loc_180013D24
0x180013c65  mov     edx, [rbx+10h]
0x180013c68  lea     rax, [rbp+4Fh+arg_8]
0x180013c6c  mov     rcx, [rbp+4Fh+var_30]
0x180013c70  lea     r9, [rbp+4Fh+var_3C+4]
0x180013c74  mov     dword ptr [rsp+0B0h+lpTargetHandle], r15d
0x180013c79  lea     r8d, [r15+3]
0x180013c7d  mov     qword ptr [rsp+0B0h+var_90], rax
0x180013c82  mov     dword ptr [rbp+4Fh+arg_8], r15d
0x180013c86  mov     qword ptr [rbp+4Fh+var_3C+4], r15
0x180013c8a  call    FindProxy
0x180013c8f  test    eax, eax
0x180013c91  jz      short loc_180013C9A
0x180013c93  mov     edi, eax
0x180013c95  jmp     loc_180013D24
0x180013c9a  cmp     qword ptr [rbp+4Fh+var_3C+4], r15
0x180013c9e  jz      short loc_180013CEB
0x180013ca0  mov     rcx, qword ptr [rbp+4Fh+var_3C+4]
0x180013ca4  lea     rax, [rbp+4Fh+arg_8]
0x180013ca8  mov     edx, 3
0x180013cad  mov     [rbp+4Fh+arg_8], r15
0x180013cb1  mov     r9, rsi
0x180013cb4  mov     qword ptr [rsp+0B0h+var_90], rax
0x180013cb9  lea     r8d, [rdx+5]
0x180013cbd  call    CreateProxyRequest
0x180013cc2  test    eax, eax
0x180013cc4  jnz     short loc_180013C93
0x180013cc6  mov     eax, [rbx+10h]
0x180013cc9  mov     r8, rsi
0x180013ccc  mov     rdx, [rbp+4Fh+arg_8]
0x180013cd0  mov     rcx, qword ptr [rbp+4Fh+var_3C+4]
0x180013cd4  mov     [rdx+44h], eax
0x180013cd7  mov     eax, [rbx+14h]
0x180013cda  mov     [rdx+48h], eax
0x180013cdd  call    SendProxyRequest
0x180013ce2  test    eax, eax
0x180013ce4  jnz     short loc_180013C93
0x180013ce6  mov     eax, [rsi+48h]
0x180013ce9  jmp     short loc_180013D1B
0x180013ceb  mov     ecx, dword ptr [rbp+4Fh+arg_8]
0x180013cee  call    GetLineLookupEntry
0x180013cf3  cmp     [rax+24h], r15d
0x180013cf7  jz      short loc_180013D1F
0x180013cf9  mov     rax, cs:pRemoteSP
0x180013d00  mov     r9d, [rbx+14h]
0x180013d04  mov     r8d, [rbx+10h]
0x180013d08  mov     rdx, qword ptr [rbp+4Fh+var_28]
0x180013d0c  mov     rax, [rax+220h]
0x180013d13  mov     ecx, [rsi+48h]
0x180013d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d1b  mov     [rbx], eax
0x180013d1d  jmp     short loc_180013D24
0x180013d1f  mov     edi, 80000049h
0x180013d24  mov     eax, [rbp+4Fh+var_40]
0x180013d27  mov     edx, edi
0x180013d29  mov     r9d, dword ptr [rbp+4Fh+var_3C]
0x180013d2d  mov     rcx, rbx
0x180013d30  mov     r8, [rbp+4Fh+TargetHandle]
0x180013d34  mov     dword ptr [rsp+0B0h+lpTargetHandle], eax
0x180013d38  mov     qword ptr [rsp+0B0h+var_90], rsi
0x180013d3d  call    LineEpilogAsync
0x180013d42  lea     r11, [rsp+0B0h+var_10]
0x180013d4a  mov     rbx, [r11+20h]
0x180013d4e  mov     rsi, [r11+30h]
0x180013d52  mov     rsp, r11
0x180013d55  pop     r15
0x180013d57  pop     rdi
0x180013d58  pop     rbp
0x180013d59  retn
```
