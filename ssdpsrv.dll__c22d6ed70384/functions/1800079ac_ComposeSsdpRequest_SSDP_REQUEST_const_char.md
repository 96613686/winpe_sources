# ComposeSsdpRequest(_SSDP_REQUEST const *,char * *)

- ea: `0x1800079ac`
- end: `0x180007be3`
- name: `?ComposeSsdpRequest@@YAHPEBU_SSDP_REQUEST@@PEAPEAD@Z`
- size: `567`
- prototype: `__int64 __fastcall(const struct _SSDP_REQUEST *, char **)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800050b0`
- `0x18000770c`
- `0x180016410`

## callees

- `0x1800079ac`
- `0x180018e90`
- `0x18001bc88`
- `0x180028000`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007bb7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007bb7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007a5d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007a5d`

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
0x1800079ac  mov     [rsp-28h+arg_8], rbx
0x1800079b1  push    rbp
0x1800079b2  push    rsi
0x1800079b3  push    rdi
0x1800079b4  push    r14
0x1800079b6  push    r15
0x1800079b8  mov     rbp, rsp
0x1800079bb  sub     rsp, 50h
0x1800079bf  xor     ebx, ebx
0x1800079c1  lea     rdi, __ImageBase
0x1800079c8  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800079cc  mov     r15, rdx
0x1800079cf  cmp     dword ptr [rcx], 3
0x1800079d2  mov     r14, rcx
0x1800079d5  ja      short loc_180007A08
0x1800079d7  mov     rax, [rcx+8]
0x1800079db  test    rax, rax
0x1800079de  jz      short loc_180007A08
0x1800079e0  mov     rcx, r9
0x1800079e3  inc     rcx
0x1800079e6  cmp     [rax+rcx], bl
0x1800079e9  jnz     short loc_1800079E3
0x1800079eb  movsxd  rax, dword ptr [r14]
0x1800079ee  mov     rdx, ds:rva ?SsdpMethodStr@@3PAPEADA[rdi+rax*8]; char * near * SsdpMethodStr ...
0x1800079f6  mov     rax, r9
0x1800079f9  inc     rax
0x1800079fc  cmp     [rdx+rax], bl
0x1800079ff  jnz     short loc_1800079F9
0x180007a01  lea     rbx, [rax+0Dh]
0x180007a05  add     rbx, rcx
0x180007a08  cmp     dword ptr [r14+48h], 0
0x180007a0d  jbe     short loc_180007A56
0x180007a0f  xor     ecx, ecx
0x180007a11  cmp     ecx, 14h
0x180007a14  jnb     short loc_180007A56
0x180007a16  mov     rax, [r14+50h]
0x180007a1a  mov     r8, [rax+rcx*8]
0x180007a1e  test    r8, r8
0x180007a21  jz      short loc_180007A4E
0x180007a23  mov     rax, ds:rva ?SsdpHeaderStr@@3PAPEADA[rdi+rcx*8]; char * near * SsdpHeaderStr ...
0x180007a2b  mov     rdx, r9
0x180007a2e  inc     rdx
0x180007a31  cmp     byte ptr [rax+rdx], 0
0x180007a35  jnz     short loc_180007A2E
0x180007a37  mov     rax, r9
0x180007a3a  inc     rax
0x180007a3d  cmp     byte ptr [r8+rax], 0
0x180007a42  jnz     short loc_180007A3A
0x180007a44  add     rax, rdx
0x180007a47  add     rbx, 4
0x180007a4b  add     rbx, rax
0x180007a4e  inc     ecx
0x180007a50  cmp     ecx, [r14+48h]
0x180007a54  jb      short loc_180007A11
0x180007a56  add     rbx, 3
0x180007a5a  mov     rcx, rbx; Size
0x180007a5d  call    cs:__imp_malloc
0x180007a63  mov     rsi, rax
0x180007a66  test    rax, rax
0x180007a69  jnz     short loc_180007A9E
0x180007a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a72  lea     rax, WPP_GLOBAL_Control
0x180007a79  cmp     rcx, rax
0x180007a7c  jz      short loc_180007A97
0x180007a7e  test    byte ptr [rcx+1Ch], 1
0x180007a82  jz      short loc_180007A97
0x180007a84  mov     rcx, [rcx+10h]
0x180007a88  lea     edx, [rsi+0Bh]
0x180007a8b  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x180007a92  call    WPP_SF_
0x180007a97  xor     eax, eax
0x180007a99  jmp     loc_180007BCF
0x180007a9e  cmp     dword ptr [r14], 3
0x180007aa2  mov     rcx, rsi
0x180007aa5  mov     [rbp+Buffer], rcx
0x180007aa9  mov     [rbp+arg_0], rbx
0x180007aad  ja      short loc_180007B11
0x180007aaf  mov     rdx, [r14+8]
0x180007ab3  test    rdx, rdx
0x180007ab6  jz      short loc_180007B11
0x180007ab8  movsxd  rax, dword ptr [r14]
0x180007abb  lea     rcx, aHttp11_0; "HTTP/1.1\r\n"
0x180007ac2  mov     [rsp+50h+var_10], rcx
0x180007ac7  lea     r9, [rbp+arg_0]; unsigned __int64 *
0x180007acb  mov     [rsp+50h+var_18], rdx
0x180007ad0  lea     r8, [rbp+Buffer]; char **
0x180007ad4  mov     rdx, rbx; cbDest
0x180007ad7  mov     rcx, rsi; Buffer
0x180007ada  mov     rax, ds:rva ?SsdpMethodStr@@3PAPEADA[rdi+rax*8]; char * near * SsdpMethodStr ...
0x180007ae2  mov     [rsp+50h+var_20], rax
0x180007ae7  lea     rax, aSSS; "%s %s %s"
0x180007aee  mov     [rsp+50h+var_28], rax; unsigned int
0x180007af3  mov     qword ptr [rsp+50h+var_30], 0; DWORD
0x180007afc  call    ?StringCbPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCbPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x180007b01  test    eax, eax
0x180007b03  js      loc_180007BB4
0x180007b09  mov     rbx, [rbp+arg_0]
0x180007b0d  mov     rcx, [rbp+Buffer]; char *
0x180007b11  xor     edi, edi
0x180007b13  lea     r10, asc_18003914C; "\r\n"
0x180007b1a  cmp     edi, [r14+48h]
0x180007b1e  jnb     short loc_180007B98
0x180007b20  cmp     edi, 14h
0x180007b23  jnb     short loc_180007B98
0x180007b25  mov     rax, [r14+50h]
0x180007b29  mov     r8, [rax+rdi*8]
0x180007b2d  test    r8, r8
0x180007b30  jz      short loc_180007B94
0x180007b32  mov     [rsp+50h+var_8], r10
0x180007b37  lea     rax, asc_18003B28C; ": "
0x180007b3e  mov     [rsp+50h+var_10], r8
0x180007b43  lea     r9, [rbp+arg_0]; unsigned __int64 *
0x180007b47  mov     [rsp+50h+var_18], rax
0x180007b4c  lea     r8, [rbp+Buffer]; char **
0x180007b50  lea     rax, __ImageBase
0x180007b57  mov     rdx, rbx; cbDest
0x180007b5a  mov     rax, ds:rva ?SsdpHeaderStr@@3PAPEADA[rax+rdi*8]; char * near * SsdpHeaderStr ...
0x180007b62  mov     [rsp+50h+var_20], rax
0x180007b67  lea     rax, aSSSS; "%s%s%s%s"
0x180007b6e  mov     [rsp+50h+var_28], rax; char *
0x180007b73  mov     qword ptr [rsp+50h+var_30], 0; DWORD
0x180007b7c  call    ?StringCbPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCbPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x180007b81  test    eax, eax
0x180007b83  js      short loc_180007BB4
0x180007b85  mov     rbx, [rbp+arg_0]
0x180007b89  lea     r10, asc_18003914C; "\r\n"
0x180007b90  mov     rcx, [rbp+Buffer]
0x180007b94  inc     edi
0x180007b96  jmp     short loc_180007B1A
0x180007b98  lea     rax, [rbp+arg_0]
0x180007b9c  mov     r8, r10; char *
0x180007b9f  lea     r9, [rbp+Buffer]; char **
0x180007ba3  mov     qword ptr [rsp+50h+var_30], rax; unsigned __int64 *
0x180007ba8  mov     rdx, rbx; unsigned __int64
0x180007bab  call    ?StringCbCopyExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCbCopyExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x180007bb0  test    eax, eax
0x180007bb2  jns     short loc_180007BC2
0x180007bb4  mov     rcx, rsi; Block
0x180007bb7  call    cs:__imp_free
0x180007bbd  jmp     loc_180007A97
0x180007bc2  test    r15, r15
0x180007bc5  jz      short loc_180007BCA
0x180007bc7  mov     [r15], rsi
0x180007bca  mov     eax, 1
0x180007bcf  mov     rbx, [rsp+50h+arg_8]
0x180007bd7  add     rsp, 50h
0x180007bdb  pop     r15
0x180007bdd  pop     r14
0x180007bdf  pop     rdi
0x180007be0  pop     rsi
0x180007be1  pop     rbp
0x180007be2  retn
```
