# ComposeSsdpRequest(_SSDP_REQUEST const *,char * *)

- ea: `0x180008eb8`
- end: `0x1800090fc`
- name: `?ComposeSsdpRequest@@YAHPEBU_SSDP_REQUEST@@PEAPEAD@Z`
- size: `580`
- prototype: `__int64 __fastcall(const struct _SSDP_REQUEST *, char **)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006350`
- `0x180008bf0`
- `0x180018804`

## callees

- `0x180008eb8`
- `0x180019ed0`
- `0x18001d0b4`
- `0x180029df0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800090c9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800090c9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008f69`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008f69`

## pseudocode

```c
__int64 __fastcall ComposeSsdpRequest(const struct _SSDP_REQUEST *a1, char **a2)
{
  __int64 v2; // rbx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rax
  size_t v12; // rbx
  char *v13; // rax
  char *v14; // rsi
  bool v16; // cc
  char *v17; // rcx
  const char *v18; // rdx
  __int64 i; // rdi
  const char *v20; // r8
  unsigned int v21; // [rsp+28h] [rbp-28h]
  unsigned __int64 v22; // [rsp+80h] [rbp+30h] BYREF
  char *Buffer; // [rsp+90h] [rbp+40h] BYREF

  v2 = 0;
  if ( *(_DWORD *)a1 <= 3u )
  {
    v5 = *((_QWORD *)a1 + 1);
    if ( v5 )
    {
      v6 = -1;
      do
        ++v6;
      while ( *(_BYTE *)(v5 + v6) );
      v7 = -1;
      do
        ++v7;
      while ( *((_BYTE *)(&SsdpMethodStr)[*(int *)a1] + v7) );
      v2 = v6 + v7 + 13;
    }
  }
  if ( *((_DWORD *)a1 + 18) )
  {
    v8 = 0;
    do
    {
      if ( (unsigned int)v8 >= 0x14 )
        break;
      v9 = *(_QWORD *)(*((_QWORD *)a1 + 10) + 8 * v8);
      if ( v9 )
      {
        v10 = -1;
        do
          ++v10;
        while ( *((_BYTE *)(&SsdpHeaderStr)[v8] + v10) );
        v11 = -1;
        do
          ++v11;
        while ( *(_BYTE *)(v9 + v11) );
        v2 += v10 + v11 + 4;
      }
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < *((_DWORD *)a1 + 18) );
  }
  v12 = v2 + 3;
  v13 = (char *)malloc(v12);
  v14 = v13;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids);
    return 0;
  }
  v16 = *(_DWORD *)a1 <= 3u;
  v17 = v13;
  Buffer = v13;
  v22 = v12;
  if ( v16 )
  {
    v18 = (const char *)*((_QWORD *)a1 + 1);
    if ( v18 )
    {
      if ( (int)StringCbPrintfExA(
                  v13,
                  v12,
                  &Buffer,
                  &v22,
                  0,
                  "%s %s %s",
                  (const char *)(&SsdpMethodStr)[*(int *)a1],
                  v18,
                  "HTTP/1.1\r\n") < 0 )
      {
LABEL_35:
        free(v14);
        return 0;
      }
      v12 = v22;
      v17 = Buffer;
    }
  }
  for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 18) && (unsigned int)i < 0x14; i = (unsigned int)(i + 1) )
  {
    v20 = *(const char **)(*((_QWORD *)a1 + 10) + 8 * i);
    if ( v20 )
    {
      if ( (int)StringCbPrintfExA(
                  v17,
                  v12,
                  &Buffer,
                  &v22,
                  0,
                  "%s%s%s%s",
                  (const char *)(&SsdpHeaderStr)[i],
                  ": ",
                  v20,
                  "\r\n") < 0 )
        goto LABEL_35;
      v12 = v22;
      v17 = Buffer;
    }
  }
  if ( (int)StringCbCopyExA(v17, v12, "\r\n", &Buffer, &v22, v21) < 0 )
    goto LABEL_35;
  if ( a2 )
    *a2 = v14;
  return 1;
}

```

## disassembly

```asm
0x180008eb8  mov     [rsp-28h+arg_8], rbx
0x180008ebd  push    rbp
0x180008ebe  push    rsi
0x180008ebf  push    rdi
0x180008ec0  push    r14
0x180008ec2  push    r15
0x180008ec4  mov     rbp, rsp
0x180008ec7  sub     rsp, 50h
0x180008ecb  xor     ebx, ebx
0x180008ecd  lea     rdi, __ImageBase
0x180008ed4  or      r9, 0FFFFFFFFFFFFFFFFh
0x180008ed8  mov     r15, rdx
0x180008edb  cmp     dword ptr [rcx], 3
0x180008ede  mov     r14, rcx
0x180008ee1  ja      short loc_180008F14
0x180008ee3  mov     rax, [rcx+8]
0x180008ee7  test    rax, rax
0x180008eea  jz      short loc_180008F14
0x180008eec  mov     rcx, r9
0x180008eef  inc     rcx
0x180008ef2  cmp     [rax+rcx], bl
0x180008ef5  jnz     short loc_180008EEF
0x180008ef7  movsxd  rax, dword ptr [r14]
0x180008efa  mov     rdx, ds:rva ?SsdpMethodStr@@3PAPEADA[rdi+rax*8]; char * near * SsdpMethodStr ...
0x180008f02  mov     rax, r9
0x180008f05  inc     rax
0x180008f08  cmp     [rdx+rax], bl
0x180008f0b  jnz     short loc_180008F05
0x180008f0d  lea     rbx, [rax+0Dh]
0x180008f11  add     rbx, rcx
0x180008f14  cmp     dword ptr [r14+48h], 0
0x180008f19  jbe     short loc_180008F62
0x180008f1b  xor     ecx, ecx
0x180008f1d  cmp     ecx, 14h
0x180008f20  jnb     short loc_180008F62
0x180008f22  mov     rax, [r14+50h]
0x180008f26  mov     r8, [rax+rcx*8]
0x180008f2a  test    r8, r8
0x180008f2d  jz      short loc_180008F5A
0x180008f2f  mov     rax, ds:rva ?SsdpHeaderStr@@3PAPEADA[rdi+rcx*8]; char * near * SsdpHeaderStr ...
0x180008f37  mov     rdx, r9
0x180008f3a  inc     rdx
0x180008f3d  cmp     byte ptr [rax+rdx], 0
0x180008f41  jnz     short loc_180008F3A
0x180008f43  mov     rax, r9
0x180008f46  inc     rax
0x180008f49  cmp     byte ptr [r8+rax], 0
0x180008f4e  jnz     short loc_180008F46
0x180008f50  add     rax, rdx
0x180008f53  add     rbx, 4
0x180008f57  add     rbx, rax
0x180008f5a  inc     ecx
0x180008f5c  cmp     ecx, [r14+48h]
0x180008f60  jb      short loc_180008F1D
0x180008f62  add     rbx, 3
0x180008f66  mov     rcx, rbx; Size
0x180008f69  call    cs:__imp_malloc
0x180008f70  nop     dword ptr [rax+rax+00h]
0x180008f75  mov     rsi, rax
0x180008f78  test    rax, rax
0x180008f7b  jnz     short loc_180008FB0
0x180008f7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f84  lea     rax, WPP_GLOBAL_Control
0x180008f8b  cmp     rcx, rax
0x180008f8e  jz      short loc_180008FA9
0x180008f90  test    byte ptr [rcx+1Ch], 1
0x180008f94  jz      short loc_180008FA9
0x180008f96  mov     rcx, [rcx+10h]
0x180008f9a  lea     edx, [rsi+0Bh]
0x180008f9d  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x180008fa4  call    WPP_SF_
0x180008fa9  xor     eax, eax
0x180008fab  jmp     loc_1800090E7
0x180008fb0  cmp     dword ptr [r14], 3
0x180008fb4  mov     rcx, rsi
0x180008fb7  mov     [rbp+Buffer], rcx
0x180008fbb  mov     [rbp+arg_0], rbx
0x180008fbf  ja      short loc_180009023
0x180008fc1  mov     rdx, [r14+8]
0x180008fc5  test    rdx, rdx
0x180008fc8  jz      short loc_180009023
0x180008fca  movsxd  rax, dword ptr [r14]
0x180008fcd  lea     rcx, aHttp11_0; "HTTP/1.1\r\n"
0x180008fd4  mov     [rsp+50h+var_10], rcx
0x180008fd9  lea     r9, [rbp+arg_0]; unsigned __int64 *
0x180008fdd  mov     [rsp+50h+var_18], rdx
0x180008fe2  lea     r8, [rbp+Buffer]; char **
0x180008fe6  mov     rdx, rbx; cbDest
0x180008fe9  mov     rcx, rsi; Buffer
0x180008fec  mov     rax, ds:rva ?SsdpMethodStr@@3PAPEADA[rdi+rax*8]; char * near * SsdpMethodStr ...
0x180008ff4  mov     [rsp+50h+var_20], rax
0x180008ff9  lea     rax, aSSS; "%s %s %s"
0x180009000  mov     [rsp+50h+var_28], rax; unsigned int
0x180009005  mov     qword ptr [rsp+50h+var_30], 0; DWORD
0x18000900e  call    ?StringCbPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCbPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x180009013  test    eax, eax
0x180009015  js      loc_1800090C6
0x18000901b  mov     rbx, [rbp+arg_0]
0x18000901f  mov     rcx, [rbp+Buffer]; char *
0x180009023  xor     edi, edi
0x180009025  lea     r10, Delimiter; "\r\n"
0x18000902c  cmp     edi, [r14+48h]
0x180009030  jnb     short loc_1800090AA
0x180009032  cmp     edi, 14h
0x180009035  jnb     short loc_1800090AA
0x180009037  mov     rax, [r14+50h]
0x18000903b  mov     r8, [rax+rdi*8]
0x18000903f  test    r8, r8
0x180009042  jz      short loc_1800090A6
0x180009044  mov     [rsp+50h+var_8], r10
0x180009049  lea     rax, asc_18003E29C; ": "
0x180009050  mov     [rsp+50h+var_10], r8
0x180009055  lea     r9, [rbp+arg_0]; unsigned __int64 *
0x180009059  mov     [rsp+50h+var_18], rax
0x18000905e  lea     r8, [rbp+Buffer]; char **
0x180009062  lea     rax, __ImageBase
0x180009069  mov     rdx, rbx; cbDest
0x18000906c  mov     rax, ds:rva ?SsdpHeaderStr@@3PAPEADA[rax+rdi*8]; char * near * SsdpHeaderStr ...
0x180009074  mov     [rsp+50h+var_20], rax
0x180009079  lea     rax, aSSSS; "%s%s%s%s"
0x180009080  mov     [rsp+50h+var_28], rax; char *
0x180009085  mov     qword ptr [rsp+50h+var_30], 0; DWORD
0x18000908e  call    ?StringCbPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCbPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x180009093  test    eax, eax
0x180009095  js      short loc_1800090C6
0x180009097  mov     rbx, [rbp+arg_0]
0x18000909b  lea     r10, Delimiter; "\r\n"
0x1800090a2  mov     rcx, [rbp+Buffer]
0x1800090a6  inc     edi
0x1800090a8  jmp     short loc_18000902C
0x1800090aa  lea     rax, [rbp+arg_0]
0x1800090ae  mov     r8, r10; char *
0x1800090b1  lea     r9, [rbp+Buffer]; char **
0x1800090b5  mov     qword ptr [rsp+50h+var_30], rax; unsigned __int64 *
0x1800090ba  mov     rdx, rbx; unsigned __int64
0x1800090bd  call    ?StringCbCopyExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCbCopyExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x1800090c2  test    eax, eax
0x1800090c4  jns     short loc_1800090DA
0x1800090c6  mov     rcx, rsi; Block
0x1800090c9  call    cs:__imp_free
0x1800090d0  nop     dword ptr [rax+rax+00h]
0x1800090d5  jmp     loc_180008FA9
0x1800090da  test    r15, r15
0x1800090dd  jz      short loc_1800090E2
0x1800090df  mov     [r15], rsi
0x1800090e2  mov     eax, 1
0x1800090e7  mov     rbx, [rsp+50h+arg_8]
0x1800090ef  add     rsp, 50h
0x1800090f3  pop     r15
0x1800090f5  pop     r14
0x1800090f7  pop     rdi
0x1800090f8  pop     rsi
0x1800090f9  pop     rbp
0x1800090fa  retn
```
