# LCreateAgent

- ea: `0x180008d20`
- end: `0x180009002`
- name: `LCreateAgent`
- size: `738`
- prototype: `__int64 __fastcall(int, _DWORD *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180028100`

## callees

- `0x1800038cc`
- `0x1800063d4`
- `0x180006f24`
- `0x1800072e4`
- `0x180008d20`
- `0x180017adc`
- `0x180019fcc`
- `0x18001c114`
- `0x18001c854`
- `0x180040010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180008f57`
- `KERNEL32!HeapAlloc` at `0x180008f57`
- `KERNEL32!lstrlenW` at `0x180008e71`
- `KERNEL32!lstrlenW` at `0x180008e8b`
- `KERNEL32!lstrlenW` at `0x180008e71`
- `KERNEL32!lstrlenW` at `0x180008e8b`

## pseudocode

```c
__int64 __fastcall LCreateAgent(int a1, _DWORD *a2, unsigned int a3, __int64 a4)
{
  unsigned int v4; // r12d
  unsigned int v6; // r8d
  __int64 result; // rax
  unsigned int v11; // r8d
  int v12; // eax
  __int64 v13; // rdi
  int v14; // esi
  int Proxy; // eax
  bool v16; // zf
  unsigned int v17; // r15d
  unsigned int v18; // r8d
  __int64 v19; // r11
  unsigned int v20; // eax
  int v21; // eax
  LPVOID v22; // rax
  __int64 v23; // r9
  __int64 v24; // r8
  __int64 v25; // [rsp+70h] [rbp-1h] BYREF
  __int64 v26; // [rsp+78h] [rbp+7h] BYREF
  __int64 v27; // [rsp+80h] [rbp+Fh] BYREF
  int v28[2]; // [rsp+88h] [rbp+17h] BYREF
  HANDLE TargetHandle; // [rsp+90h] [rbp+1Fh] BYREF
  __int64 v30; // [rsp+D8h] [rbp+67h] BYREF

  v4 = 0;
  v6 = a2[5];
  TargetHandle = 0;
  *(_QWORD *)v28 = 0;
  v25 = 0;
  v27 = 0;
  v30 = 0;
  if ( v6 != -1 && (result = IsBadStringParam(a3, a4, v6), (_DWORD)result)
    || (v11 = a2[6], v11 != -1) && (result = IsBadStringParam(a3, a4, v11), (_DWORD)result) )
  {
    *a2 = -2147483576;
    return result;
  }
  v12 = LineProlog(
          a1,
          2,
          a2[4],
          (int)v28,
          0,
          &TargetHandle,
          (__int64)&v25 + 4,
          0,
          0,
          (__int64)&v30,
          a2[2],
          (__int64)&v25,
          (__int64)&v27);
  v13 = v30;
  v14 = v12;
  if ( v12 > 0 )
  {
    LODWORD(v30) = 0;
    v26 = 0;
    Proxy = FindProxy(v27, 0, 9u, &v26, &v30, 0x20002u);
    if ( Proxy )
    {
LABEL_8:
      v14 = Proxy;
      return LineEpilogAsync((_DWORD)a2, v14, (_DWORD)TargetHandle, HIDWORD(v25), v13, v25);
    }
    *(_QWORD *)(v13 + 80) = (unsigned int)a2[7];
    *(_QWORD *)(v13 + 88) = 4;
    *(_DWORD *)(v13 + 68) = a2[3];
    if ( v26 )
    {
      v16 = a2[5] == -1;
      v17 = 0;
      v30 = 0;
      if ( !v16 )
        v17 = 2 * lstrlenW((LPCWSTR)(a4 + (unsigned int)a2[5])) + 2;
      if ( a2[6] == -1 )
      {
        v18 = v17;
      }
      else
      {
        v4 = 2 * lstrlenW((LPCWSTR)(a4 + (unsigned int)a2[6])) + 2;
        v18 = v4 + v17;
      }
      Proxy = CreateProxyRequest(v26, 9u, v18 + 20, v13, (ULONG **)&v30);
      if ( Proxy )
        goto LABEL_8;
      v19 = v30;
      v20 = 20;
      if ( v17 )
      {
        *(_DWORD *)(v30 + 72) = v17;
        *(_DWORD *)(v19 + 76) = 20;
        StringCbCopyW((STRSAFE_LPWSTR)(v19 + 88), v17, (STRSAFE_LPCWSTR)(a4 + (unsigned int)a2[5]));
        v20 = v17 + 20;
      }
      if ( v4 )
      {
        *(_DWORD *)(v19 + 80) = v4;
        *(_DWORD *)(v19 + 84) = v20;
        StringCbCopyW((STRSAFE_LPWSTR)(v19 + v20 + 68LL), v4, (STRSAFE_LPCWSTR)(a4 + (unsigned int)a2[6]));
      }
      Proxy = SendProxyRequest(v26, v19, v13);
      if ( Proxy )
        goto LABEL_8;
      v21 = *(_DWORD *)(v13 + 72);
    }
    else
    {
      if ( !*((_DWORD *)GetLineLookupEntry(v30) + 9) )
      {
        v14 = -2147483575;
        return LineEpilogAsync((_DWORD)a2, v14, (_DWORD)TargetHandle, HIDWORD(v25), v13, v25);
      }
      v22 = HeapAlloc(ghTapisrvHeap, 8u, 0x2Cu);
      if ( !v22 )
      {
        v14 = -2147483580;
        return LineEpilogAsync((_DWORD)a2, v14, (_DWORD)TargetHandle, HIDWORD(v25), v13, v25);
      }
      *(_QWORD *)(v13 + 48) = LCreateAgent_PostProcess;
      *(_QWORD *)(v13 + 96) = v22;
      if ( a2[6] == -1 )
        v23 = 0;
      else
        v23 = a4 + (unsigned int)a2[6];
      if ( a2[5] == -1 )
        v24 = 0;
      else
        v24 = a4 + (unsigned int)a2[5];
      v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, __int64))(pRemoteSP + 1072))(
              *(unsigned int *)(v13 + 72),
              *(_QWORD *)v28,
              v24,
              v23,
              (__int64)v22 + 40);
    }
    *a2 = v21;
  }
  return LineEpilogAsync((_DWORD)a2, v14, (_DWORD)TargetHandle, HIDWORD(v25), v13, v25);
}

```

## disassembly

```asm
0x180008d20  mov     [rsp-8+arg_0], rbx
0x180008d25  mov     [rsp-8+arg_10], rsi
0x180008d2a  push    rbp
0x180008d2b  push    rdi
0x180008d2c  push    r12
0x180008d2e  push    r14
0x180008d30  push    r15
0x180008d32  lea     rbp, [rsp-2Fh]
0x180008d37  sub     rsp, 0A0h
0x180008d3e  xor     r12d, r12d
0x180008d41  mov     edi, r8d
0x180008d44  mov     r8d, [rdx+14h]
0x180008d48  or      r15d, 0FFFFFFFFh
0x180008d4c  mov     dword ptr [rbp+4Fh+var_50+4], r12d
0x180008d50  mov     r14, r9
0x180008d53  mov     [rbp+4Fh+TargetHandle], r12
0x180008d57  mov     rbx, rdx
0x180008d5a  mov     qword ptr [rbp+4Fh+var_38], r12
0x180008d5e  mov     rsi, rcx
0x180008d61  mov     dword ptr [rbp+4Fh+var_50], r12d
0x180008d65  mov     [rbp+4Fh+var_40], r12
0x180008d69  mov     [rbp+4Fh+arg_8], r12
0x180008d6d  cmp     r8d, r15d
0x180008d70  jz      short loc_180008D80
0x180008d72  mov     rdx, r9
0x180008d75  mov     ecx, edi
0x180008d77  call    IsBadStringParam
0x180008d7c  test    eax, eax
0x180008d7e  jnz     short loc_180008D97
0x180008d80  mov     r8d, [rbx+18h]
0x180008d84  cmp     r8d, r15d
0x180008d87  jz      short loc_180008DA2
0x180008d89  mov     rdx, r14
0x180008d8c  mov     ecx, edi
0x180008d8e  call    IsBadStringParam
0x180008d93  test    eax, eax
0x180008d95  jz      short loc_180008DA2
0x180008d97  mov     dword ptr [rbx], 80000048h
0x180008d9d  jmp     loc_180008FE6
0x180008da2  mov     r8d, [rbx+10h]; int
0x180008da6  lea     rax, [rbp+4Fh+var_40]
0x180008daa  mov     [rsp+0C0h+var_60], rax; __int64
0x180008daf  lea     r9, [rbp+4Fh+var_38]; int
0x180008db3  lea     rax, [rbp+4Fh+var_50]
0x180008db7  mov     edx, 2; int
0x180008dbc  mov     [rsp+0C0h+var_68], rax; __int64
0x180008dc1  mov     rcx, rsi; int
0x180008dc4  mov     eax, [rbx+8]
0x180008dc7  mov     [rsp+0C0h+var_70], eax; int
0x180008dcb  lea     rax, [rbp+4Fh+arg_8]
0x180008dcf  mov     [rsp+0C0h+var_78], rax; __int64
0x180008dd4  lea     rax, [rbp+4Fh+var_50+4]
0x180008dd8  mov     [rsp+0C0h+var_80], r12; __int64
0x180008ddd  mov     [rsp+0C0h+var_88], r12d; int
0x180008de2  mov     [rsp+0C0h+var_90], rax; __int64
0x180008de7  lea     rax, [rbp+4Fh+TargetHandle]
0x180008deb  mov     [rsp+0C0h+lpTargetHandle], rax; lpTargetHandle
0x180008df0  mov     [rsp+0C0h+var_A0], r12d; int
0x180008df5  call    LineProlog
0x180008dfa  mov     rdi, [rbp+4Fh+arg_8]
0x180008dfe  mov     esi, eax
0x180008e00  test    eax, eax
0x180008e02  jle     loc_180008FC8
0x180008e08  mov     rcx, [rbp+4Fh+var_40]
0x180008e0c  lea     rax, [rbp+4Fh+arg_8]
0x180008e10  xor     edx, edx
0x180008e12  mov     dword ptr [rsp+0C0h+lpTargetHandle], 20002h
0x180008e1a  lea     r9, [rbp+4Fh+var_48]
0x180008e1e  mov     dword ptr [rbp+4Fh+arg_8], r12d
0x180008e22  mov     [rbp+4Fh+var_48], r12
0x180008e26  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180008e2b  lea     r8d, [rdx+9]
0x180008e2f  call    FindProxy
0x180008e34  test    eax, eax
0x180008e36  jz      short loc_180008E3F
0x180008e38  mov     esi, eax
0x180008e3a  jmp     loc_180008FC8
0x180008e3f  mov     eax, [rbx+1Ch]
0x180008e42  mov     [rdi+50h], rax
0x180008e46  mov     qword ptr [rdi+58h], 4
0x180008e4e  mov     eax, [rbx+0Ch]
0x180008e51  mov     [rdi+44h], eax
0x180008e54  cmp     [rbp+4Fh+var_48], r12
0x180008e58  jz      loc_180008F39
0x180008e5e  cmp     dword ptr [rbx+14h], 0FFFFFFFFh
0x180008e62  mov     r15d, r12d
0x180008e65  mov     [rbp+4Fh+arg_8], r12
0x180008e69  jz      short loc_180008E7F
0x180008e6b  mov     ecx, [rbx+14h]
0x180008e6e  add     rcx, r14; lpString
0x180008e71  call    cs:__imp_lstrlenW
0x180008e77  lea     r15d, ds:2[rax*2]
0x180008e7f  cmp     dword ptr [rbx+18h], 0FFFFFFFFh
0x180008e83  jz      short loc_180008E9F
0x180008e85  mov     ecx, [rbx+18h]
0x180008e88  add     rcx, r14; lpString
0x180008e8b  call    cs:__imp_lstrlenW
0x180008e91  lea     r12d, ds:2[rax*2]
0x180008e99  lea     r8d, [r12+r15]
0x180008e9d  jmp     short loc_180008EA2
0x180008e9f  mov     r8d, r15d
0x180008ea2  mov     rcx, [rbp+4Fh+var_48]
0x180008ea6  lea     rax, [rbp+4Fh+arg_8]
0x180008eaa  add     r8d, 14h
0x180008eae  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180008eb3  mov     r9, rdi
0x180008eb6  mov     edx, 9
0x180008ebb  call    CreateProxyRequest
0x180008ec0  test    eax, eax
0x180008ec2  jnz     loc_180008E38
0x180008ec8  mov     r11, [rbp+4Fh+arg_8]
0x180008ecc  mov     eax, 14h
0x180008ed1  test    r15d, r15d
0x180008ed4  jz      short loc_180008EF5
0x180008ed6  mov     [r11+48h], r15d
0x180008eda  lea     rcx, [r11+58h]; pszDest
0x180008ede  mov     [r11+4Ch], eax
0x180008ee2  mov     r8d, [rbx+14h]
0x180008ee6  add     r8, r14; pszSrc
0x180008ee9  mov     edx, r15d; cbDest
0x180008eec  call    StringCbCopyW
0x180008ef1  lea     eax, [r15+14h]
0x180008ef5  test    r12d, r12d
0x180008ef8  jz      short loc_180008F1A
0x180008efa  mov     [r11+50h], r12d
0x180008efe  mov     ecx, eax
0x180008f00  mov     [r11+54h], eax
0x180008f04  add     rcx, 44h ; 'D'
0x180008f08  mov     r8d, [rbx+18h]
0x180008f0c  add     rcx, r11; pszDest
0x180008f0f  add     r8, r14; pszSrc
0x180008f12  mov     edx, r12d; cbDest
0x180008f15  call    StringCbCopyW
0x180008f1a  mov     rcx, [rbp+4Fh+var_48]
0x180008f1e  mov     r8, rdi
0x180008f21  mov     rdx, r11
0x180008f24  call    SendProxyRequest
0x180008f29  test    eax, eax
0x180008f2b  jnz     loc_180008E38
0x180008f31  mov     eax, [rdi+48h]
0x180008f34  jmp     loc_180008FBF
0x180008f39  mov     ecx, dword ptr [rbp+4Fh+arg_8]
0x180008f3c  call    GetLineLookupEntry
0x180008f41  cmp     [rax+24h], r12d
0x180008f45  jz      short loc_180008FC3
0x180008f47  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180008f4e  mov     edx, 8; dwFlags
0x180008f53  lea     r8d, [rdx+24h]; dwBytes
0x180008f57  call    cs:__imp_HeapAlloc
0x180008f5d  test    rax, rax
0x180008f60  jnz     short loc_180008F69
0x180008f62  mov     esi, 80000044h
0x180008f67  jmp     short loc_180008FC8
0x180008f69  lea     rcx, LCreateAgent_PostProcess
0x180008f70  mov     [rdi+30h], rcx
0x180008f74  mov     [rdi+60h], rax
0x180008f78  cmp     [rbx+18h], r15d
0x180008f7c  jnz     short loc_180008F83
0x180008f7e  mov     r9, r12
0x180008f81  jmp     short loc_180008F8A
0x180008f83  mov     r9d, [rbx+18h]
0x180008f87  add     r9, r14
0x180008f8a  cmp     [rbx+14h], r15d
0x180008f8e  jnz     short loc_180008F95
0x180008f90  mov     r8, r12
0x180008f93  jmp     short loc_180008F9C
0x180008f95  mov     r8d, [rbx+14h]
0x180008f99  add     r8, r14
0x180008f9c  mov     rdx, qword ptr [rbp+4Fh+var_38]
0x180008fa0  lea     rcx, [rax+28h]
0x180008fa4  mov     rax, cs:pRemoteSP
0x180008fab  mov     qword ptr [rsp+0C0h+var_A0], rcx
0x180008fb0  mov     ecx, [rdi+48h]
0x180008fb3  mov     rax, [rax+430h]
0x180008fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fbf  mov     [rbx], eax
0x180008fc1  jmp     short loc_180008FC8
0x180008fc3  mov     esi, 80000049h
0x180008fc8  mov     eax, dword ptr [rbp+4Fh+var_50]
0x180008fcb  mov     edx, esi
0x180008fcd  mov     r9d, dword ptr [rbp+4Fh+var_50+4]
0x180008fd1  mov     rcx, rbx
0x180008fd4  mov     r8, [rbp+4Fh+TargetHandle]
0x180008fd8  mov     dword ptr [rsp+0C0h+lpTargetHandle], eax
0x180008fdc  mov     qword ptr [rsp+0C0h+var_A0], rdi
0x180008fe1  call    LineEpilogAsync
0x180008fe6  lea     r11, [rsp+0C0h+var_20]
0x180008fee  mov     rbx, [r11+30h]
0x180008ff2  mov     rsi, [r11+40h]
0x180008ff6  mov     rsp, r11
0x180008ff9  pop     r15
0x180008ffb  pop     r14
0x180008ffd  pop     r12
0x180008fff  pop     rdi
0x180009000  pop     rbp
0x180009001  retn
```
