# CACSecurityPage::InitMSMSecConnectionProfile(void)

- ea: `0x180008b0c`
- end: `0x180008cd6`
- name: `?InitMSMSecConnectionProfile@CACSecurityPage@@AEAAJXZ`
- size: `458`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a7f8`

## callees

- `0x180001e26`
- `0x180008b0c`
- `0x18001bf0a`

## import_xrefs

- `wlanapi!FreeMSMSecConfig` at `0x180008ca8`
- `wlanapi!FreeMSMSecConfig` at `0x180008ca8`
- `wlanapi!MSMSecCreateDefaultProfileStatic` at `0x180008b69`
- `wlanapi!MSMSecCreateDefaultProfileStatic` at `0x180008b69`
- `wlanapi!WpAllocMemory` at `0x180008b88`
- `wlanapi!WpAllocMemory` at `0x180008c12`
- `wlanapi!WpAllocMemory` at `0x180008c45`
- `wlanapi!WpAllocMemory` at `0x180008c70`
- `wlanapi!WpAllocMemory` at `0x180008b88`
- `wlanapi!WpAllocMemory` at `0x180008c12`
- `wlanapi!WpAllocMemory` at `0x180008c45`
- `wlanapi!WpAllocMemory` at `0x180008c70`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::InitMSMSecConnectionProfile(CACSecurityPage *this)
{
  __int64 v1; // rax
  unsigned int v2; // edi
  __int64 v3; // r14
  _OWORD *v4; // rbx
  _DWORD *v5; // rcx
  int v6; // esi
  __int64 v7; // rax
  __int64 v8; // rcx
  void *v9; // rax
  void *v10; // rax
  void *v11; // rax
  __int128 v13; // [rsp+20h] [rbp-10h] BYREF
  __int64 v14; // [rsp+50h] [rbp+20h] BYREF

  v1 = *((_QWORD *)this + 5);
  v2 = 0;
  v14 = 0;
  v13 = 0;
  v3 = *(_QWORD *)(v1 + 552);
  v4 = *(_OWORD **)(*(_QWORD *)(v3 + 32) + 424LL);
  if ( v4 )
    return v2;
  v5 = (_DWORD *)*((_QWORD *)this + 3);
  LODWORD(v13) = *v5;
  *((_QWORD *)&v13 + 1) = v5 + 1;
  v6 = MSMSecCreateDefaultProfileStatic(1, &v13, &v14);
  if ( !v6 )
  {
    if ( !v14 )
      goto LABEL_11;
    v4 = (_OWORD *)WpAllocMemory(152);
    memset_0(v4, 0, 0x98u);
    v7 = v14;
    *v4 = *(_OWORD *)v14;
    v4[1] = *(_OWORD *)(v7 + 16);
    v4[2] = *(_OWORD *)(v7 + 32);
    v4[3] = *(_OWORD *)(v7 + 48);
    v4[4] = *(_OWORD *)(v7 + 64);
    v4[5] = *(_OWORD *)(v7 + 80);
    v4[6] = *(_OWORD *)(v7 + 96);
    v4[7] = *(_OWORD *)(v7 + 112);
    v4[8] = *(_OWORD *)(v7 + 128);
    *((_QWORD *)v4 + 18) = *(_QWORD *)(v7 + 144);
    v8 = 8LL * *((unsigned int *)v4 + 4);
    *((_QWORD *)v4 + 3) = 0;
    *((_QWORD *)v4 + 6) = 0;
    *((_QWORD *)v4 + 9) = 0;
    v9 = (void *)WpAllocMemory(v8);
    *((_QWORD *)v4 + 3) = v9;
    if ( !v9 )
      goto LABEL_12;
    memcpy_0(v9, *(const void **)(v14 + 24), 8LL * *((unsigned int *)v4 + 4));
    if ( *(_DWORD *)(v14 + 40) )
    {
      v10 = (void *)WpAllocMemory(*((unsigned int *)v4 + 10));
      *((_QWORD *)v4 + 6) = v10;
      if ( !v10 )
        goto LABEL_12;
      memcpy_0(v10, *(const void **)(v14 + 48), *((unsigned int *)v4 + 10));
    }
    if ( !*((_DWORD *)v4 + 16) )
    {
LABEL_11:
      *(_QWORD *)(*(_QWORD *)(v3 + 32) + 424LL) = v4;
      goto LABEL_12;
    }
    v11 = (void *)WpAllocMemory(*((unsigned int *)v4 + 16));
    *((_QWORD *)v4 + 9) = v11;
    if ( v11 )
    {
      memcpy_0(v11, *(const void **)(v14 + 72), *((unsigned int *)v4 + 16));
      goto LABEL_11;
    }
  }
LABEL_12:
  if ( v14 )
    FreeMSMSecConfig(&v14);
  if ( v6 )
  {
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
    else
      return (unsigned int)v6;
  }
  return v2;
}

```

## disassembly

```asm
0x180008b0c  mov     [rsp-18h+arg_8], rbx
0x180008b11  mov     [rsp-18h+arg_10], rsi
0x180008b16  push    rbp
0x180008b17  push    rdi
0x180008b18  push    r14
0x180008b1a  mov     rbp, rsp
0x180008b1d  sub     rsp, 30h
0x180008b21  mov     rax, [rcx+28h]
0x180008b25  xor     edi, edi
0x180008b27  mov     [rbp+arg_0], rdi
0x180008b2b  xorps   xmm0, xmm0
0x180008b2e  movups  [rbp+var_10], xmm0
0x180008b32  mov     r14, [rax+228h]
0x180008b39  mov     rax, [r14+20h]
0x180008b3d  mov     rbx, [rax+1A8h]
0x180008b44  test    rbx, rbx
0x180008b47  jnz     loc_180008CC1
0x180008b4d  mov     rcx, [rcx+18h]
0x180008b51  lea     r8, [rbp+arg_0]
0x180008b55  lea     rdx, [rbp+var_10]
0x180008b59  mov     eax, [rcx]
0x180008b5b  mov     dword ptr [rbp+var_10], eax
0x180008b5e  lea     rax, [rcx+4]
0x180008b62  lea     ecx, [rdi+1]
0x180008b65  mov     qword ptr [rbp+var_10+8], rax
0x180008b69  call    cs:__imp_MSMSecCreateDefaultProfileStatic
0x180008b6f  mov     esi, eax
0x180008b71  test    eax, eax
0x180008b73  jnz     loc_180008C9E
0x180008b79  cmp     [rbp+arg_0], rdi
0x180008b7d  jz      loc_180008C93
0x180008b83  mov     ecx, 98h
0x180008b88  call    cs:__imp_WpAllocMemory
0x180008b8e  xor     edx, edx; Val
0x180008b90  mov     r8d, 98h; Size
0x180008b96  mov     rcx, rax; void *
0x180008b99  mov     rbx, rax
0x180008b9c  call    memset_0
0x180008ba1  mov     rax, [rbp+arg_0]
0x180008ba5  movups  xmm0, xmmword ptr [rax]
0x180008ba8  movups  xmmword ptr [rbx], xmm0
0x180008bab  movups  xmm1, xmmword ptr [rax+10h]
0x180008baf  movups  xmmword ptr [rbx+10h], xmm1
0x180008bb3  movups  xmm0, xmmword ptr [rax+20h]
0x180008bb7  movups  xmmword ptr [rbx+20h], xmm0
0x180008bbb  movups  xmm1, xmmword ptr [rax+30h]
0x180008bbf  movups  xmmword ptr [rbx+30h], xmm1
0x180008bc3  movups  xmm0, xmmword ptr [rax+40h]
0x180008bc7  movups  xmmword ptr [rbx+40h], xmm0
0x180008bcb  movups  xmm1, xmmword ptr [rax+50h]
0x180008bcf  movups  xmmword ptr [rbx+50h], xmm1
0x180008bd3  movups  xmm0, xmmword ptr [rax+60h]
0x180008bd7  movups  xmmword ptr [rbx+60h], xmm0
0x180008bdb  movups  xmm1, xmmword ptr [rax+70h]
0x180008bdf  movups  xmmword ptr [rbx+70h], xmm1
0x180008be3  movups  xmm0, xmmword ptr [rax+80h]
0x180008bea  movups  xmmword ptr [rbx+80h], xmm0
0x180008bf1  mov     rax, [rax+90h]
0x180008bf8  mov     [rbx+90h], rax
0x180008bff  mov     ecx, [rbx+10h]
0x180008c02  shl     rcx, 3
0x180008c06  mov     [rbx+18h], rdi
0x180008c0a  mov     [rbx+30h], rdi
0x180008c0e  mov     [rbx+48h], rdi
0x180008c12  call    cs:__imp_WpAllocMemory
0x180008c18  mov     [rbx+18h], rax
0x180008c1c  test    rax, rax
0x180008c1f  jz      short loc_180008C9E
0x180008c21  mov     rdx, [rbp+arg_0]
0x180008c25  mov     rcx, rax; void *
0x180008c28  mov     r8d, [rbx+10h]
0x180008c2c  shl     r8, 3; Size
0x180008c30  mov     rdx, [rdx+18h]; Src
0x180008c34  call    memcpy_0
0x180008c39  mov     rax, [rbp+arg_0]
0x180008c3d  cmp     [rax+28h], edi
0x180008c40  jz      short loc_180008C68
0x180008c42  mov     ecx, [rbx+28h]
0x180008c45  call    cs:__imp_WpAllocMemory
0x180008c4b  mov     [rbx+30h], rax
0x180008c4f  test    rax, rax
0x180008c52  jz      short loc_180008C9E
0x180008c54  mov     rdx, [rbp+arg_0]
0x180008c58  mov     rcx, rax; void *
0x180008c5b  mov     r8d, [rbx+28h]; Size
0x180008c5f  mov     rdx, [rdx+30h]; Src
0x180008c63  call    memcpy_0
0x180008c68  cmp     [rbx+40h], edi
0x180008c6b  jz      short loc_180008C93
0x180008c6d  mov     ecx, [rbx+40h]
0x180008c70  call    cs:__imp_WpAllocMemory
0x180008c76  mov     [rbx+48h], rax
0x180008c7a  test    rax, rax
0x180008c7d  jz      short loc_180008C9E
0x180008c7f  mov     rdx, [rbp+arg_0]
0x180008c83  mov     rcx, rax; void *
0x180008c86  mov     r8d, [rbx+40h]; Size
0x180008c8a  mov     rdx, [rdx+48h]; Src
0x180008c8e  call    memcpy_0
0x180008c93  mov     rax, [r14+20h]
0x180008c97  mov     [rax+1A8h], rbx
0x180008c9e  cmp     [rbp+arg_0], rdi
0x180008ca2  jz      short loc_180008CAE
0x180008ca4  lea     rcx, [rbp+arg_0]
0x180008ca8  call    cs:__imp_FreeMSMSecConfig
0x180008cae  test    esi, esi
0x180008cb0  jz      short loc_180008CC1
0x180008cb2  jg      short loc_180008CB8
0x180008cb4  mov     edi, esi
0x180008cb6  jmp     short loc_180008CC1
0x180008cb8  movzx   edi, si
0x180008cbb  or      edi, 80070000h
0x180008cc1  mov     rbx, [rsp+30h+arg_8]
0x180008cc6  mov     eax, edi
0x180008cc8  mov     rsi, [rsp+30h+arg_10]
0x180008ccd  add     rsp, 30h
0x180008cd1  pop     r14
0x180008cd3  pop     rdi
0x180008cd4  pop     rbp
0x180008cd5  retn
```
