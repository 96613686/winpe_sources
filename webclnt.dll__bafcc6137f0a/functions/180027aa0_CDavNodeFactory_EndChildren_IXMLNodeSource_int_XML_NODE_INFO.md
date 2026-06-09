# CDavNodeFactory::EndChildren(IXMLNodeSource *,int,_XML_NODE_INFO *)

- ea: `0x180027aa0`
- end: `0x180027f24`
- name: `?EndChildren@CDavNodeFactory@@UEAAJPEAUIXMLNodeSource@@HPEAU_XML_NODE_INFO@@@Z`
- size: `1156`
- prototype: `__int64 __fastcall(CDavNodeFactory *__hidden this, struct IXMLNodeSource *, int, struct _XML_NODE_INFO *)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, registry_config, broker_com_uri`

## callees

- `0x18000b7dc`
- `0x18000b89c`
- `0x180027aa0`
- `0x1800288e8`
- `0x18002899c`
- `0x18002e010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180027c1b`
- `msvcrt!_wcsnicmp` at `0x180027c1b`
- `msvcrt!_wcsicmp` at `0x180027b6f`
- `msvcrt!_wcsicmp` at `0x180027b6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027cb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027cb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027b0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027cda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027d64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027df2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027eb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027b0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027cda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027d64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027df2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027eb3`
- `DAVHLPR!DavUrlDecodeToNtPath` at `0x180027dac`
- `DAVHLPR!DavUrlDecodeToNtPath` at `0x180027dac`
- `KERNEL32!LocalFree` at `0x180027e41`
- `KERNEL32!LocalFree` at `0x180027f0b`
- `KERNEL32!LocalFree` at `0x180027e41`
- `KERNEL32!LocalFree` at `0x180027f0b`
- `KERNEL32!LocalAlloc` at `0x180027c9f`
- `KERNEL32!LocalAlloc` at `0x180027c9f`

## pseudocode

```c
__int64 __fastcall CDavNodeFactory::EndChildren(
        CDavNodeFactory *this,
        struct IXMLNodeSource *a2,
        int a3,
        struct _XML_NODE_INFO *a4)
{
  __int64 v4; // rax
  int v5; // r13d
  _WORD *v8; // r14
  __int64 (__fastcall *v9)(struct IXMLNodeSource *, __int64 *); // rax
  int v10; // r12d
  int v11; // r15d
  unsigned int v12; // ebx
  DWORD v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  _DWORD *v16; // rax
  _DWORD *v17; // rax
  const wchar_t *v18; // r15
  unsigned int *v19; // r12
  __int64 v20; // rcx
  const wchar_t *v21; // rdi
  int v22; // ecx
  const wchar_t *v23; // rax
  unsigned __int64 i; // rsi
  int v25; // r13d
  _DWORD *v26; // rax
  DWORD LastError; // ebx
  DWORD v28; // eax
  const wchar_t *v29; // rax
  DWORD v30; // eax
  int v31; // eax
  DWORD v32; // eax
  __int64 v33; // r8
  __int64 v34; // rdi
  void *v35; // rcx
  __int64 v36; // rdx
  int v37; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  int v42; // [rsp+30h] [rbp-28h]
  unsigned int v43; // [rsp+34h] [rbp-24h]
  __int64 v44; // [rsp+38h] [rbp-20h] BYREF
  __int64 v45; // [rsp+40h] [rbp-18h]
  unsigned __int64 v46; // [rsp+A8h] [rbp+50h] BYREF

  v4 = *(_QWORD *)a2;
  v5 = 0;
  v44 = 0;
  v8 = 0;
  v9 = *(__int64 (__fastcall **)(struct IXMLNodeSource *, __int64 *))(v4 + 32);
  v10 = 1;
  v11 = 1;
  LODWORD(v46) = 1;
  v12 = v9(a2, &v44);
  if ( (v12 & 0x80000000) == 0 )
  {
    if ( a3 == 1 )
    {
      *(_DWORD *)(v44 + 24) = 0;
      goto LABEL_74;
    }
    v14 = *((_DWORD *)a4 + 7) != 0 ? (unsigned int)(*((_DWORD *)a4 + 7) + 1) : 0;
    if ( *((unsigned int *)a4 + 6) - v14 != 8 || _wcsicmp((const wchar_t *)(*((_QWORD *)a4 + 2) + 2 * v14), rgPropstat) )
    {
LABEL_20:
      if ( *(_DWORD *)(v44 + 24) != 1 || *(_DWORD *)(v44 + 44) != 4 )
        goto LABEL_74;
      v45 = *(_QWORD *)(v44 + 48);
      v18 = *(const wchar_t **)(v45 + 96);
      v19 = (unsigned int *)(v45 + 88);
      if ( !v18 || (v20 = *v19, (v43 = v20) == 0) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v37 = *v19;
          CurrentThreadId = GetCurrentThreadId();
          WPP_SF_lqd(*((_QWORD *)WPP_GLOBAL_Control + 2), v39, v40, CurrentThreadId, v18, v37);
        }
        goto LABEL_73;
      }
      v21 = &v18[v20];
      if ( (unsigned int)v20 >= 7 && !_wcsnicmp(v18, L"http://", 7u) )
        v5 = 1;
      v22 = 0;
      v23 = v18;
      for ( i = 2; v23 < v21; ++v23 )
      {
        if ( *v23 == 47 && ++v22 == 3 )
          break;
      }
      if ( *(v21 - 1) == 47 )
      {
        v42 = 1;
        if ( v21 - 1 == v23 && v5 == 1 || *v19 == 1 || *v19 == 2 && *(v21 - 2) == 47 )
        {
          v25 = 1;
          goto LABEL_39;
        }
        v25 = 0;
        v21 -= 2;
      }
      else
      {
        v42 = 0;
        v25 = 0;
      }
      while ( *v21 != 47 && v21 != v18 )
        --v21;
      v29 = v21 + 1;
      if ( *v21 != 47 )
        v29 = v21;
      v21 = v29;
      i = ((__int64)v18 + 2LL * *v19 + 2 - (__int64)v29) >> 1;
      if ( i <= 1 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v30 = GetCurrentThreadId();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids, v30);
        }
LABEL_73:
        v11 = v46;
        v12 = -2147221001;
        v10 = v46;
        goto LABEL_74;
      }
LABEL_39:
      v26 = LocalAlloc(0x40u, 2 * i);
      v8 = v26;
      if ( v26 )
      {
        if ( v25 )
        {
          *v26 = 47;
        }
        else
        {
          v46 = i;
          v31 = DavUrlDecodeToNtPath(v21, i - 1, v26, &v46);
          v12 = v31;
          if ( v31 > 0 )
            v12 = (unsigned __int16)v31 | 0x80070000;
          if ( v12 )
          {
            v10 = 1;
            v11 = 1;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v32 = GetCurrentThreadId();
              WPP_SF_lD(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v33, v32, v12);
            }
            goto LABEL_74;
          }
          if ( v42 )
            v8[v46 - 1] = 0;
        }
        v34 = v45;
        v35 = *(void **)(v45 + 96);
        if ( v35 )
        {
          LocalFree(v35);
          *(_QWORD *)(v34 + 96) = 0;
        }
        *v19 = 0;
        v36 = -1;
        *(_QWORD *)(*(_QWORD *)(v44 + 48) + 96LL) = v8;
        do
          ++v36;
        while ( v8[v36] );
        v11 = 0;
        v10 = 1;
        *(_DWORD *)(*(_QWORD *)(v44 + 48) + 88LL) = v36;
        if ( v43 < *(_DWORD *)(v44 + 64) )
        {
          *(_QWORD *)(v44 + 56) = v34;
          *(_DWORD *)(v44 + 64) = v43;
        }
        goto LABEL_74;
      }
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v28 = GetCurrentThreadId();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids,
          v28,
          LastError);
      }
      goto LABEL_73;
    }
    v15 = v44;
    if ( *(_DWORD *)(v44 + 32) )
    {
      if ( *(_DWORD *)(v44 + 32) != 1 || **(_DWORD **)(v44 + 48) != 1 )
        goto LABEL_16;
      *(_DWORD *)(v44 + 36) = 1;
    }
    else
    {
      v16 = *(_DWORD **)(v44 + 48);
      if ( *v16 != 1 )
        goto LABEL_16;
      *v16 = 0;
    }
    v15 = v44;
LABEL_16:
    if ( *(_DWORD *)(v15 + 36) == 1 )
    {
      v17 = *(_DWORD **)(v15 + 48);
      if ( !*v17 )
      {
        *v17 = 1;
        v15 = v44;
      }
    }
    *(_DWORD *)(v15 + 32) = 0;
    goto LABEL_20;
  }
  v44 = 0;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    return v12;
  v13 = GetCurrentThreadId();
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids, v13);
LABEL_74:
  if ( v44 )
  {
    *(_DWORD *)(v44 + 24) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  if ( v11 == v10 && v8 )
    LocalFree(v8);
  return v12;
}

```

## disassembly

```asm
0x180027aa0  push    rbp
0x180027aa2  push    rbx
0x180027aa3  push    rsi
0x180027aa4  push    rdi
0x180027aa5  push    r12
0x180027aa7  push    r13
0x180027aa9  push    r14
0x180027aab  push    r15
0x180027aad  mov     rbp, rsp
0x180027ab0  sub     rsp, 58h
0x180027ab4  mov     rax, [rdx]
0x180027ab7  xor     r13d, r13d
0x180027aba  mov     rcx, rdx
0x180027abd  mov     [rbp+var_20], r13
0x180027ac1  lea     rdx, [rbp+var_20]
0x180027ac5  mov     rdi, r9
0x180027ac8  mov     esi, r8d
0x180027acb  mov     r14d, r13d
0x180027ace  mov     rax, [rax+20h]
0x180027ad2  lea     r12d, [r13+1]
0x180027ad6  mov     r15d, r12d
0x180027ad9  mov     dword ptr [rbp+arg_8], r12d
0x180027add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ae2  mov     ebx, eax
0x180027ae4  test    eax, eax
0x180027ae6  jns     short loc_180027B36
0x180027ae8  mov     [rbp+var_20], r13
0x180027aec  mov     rcx, cs:WPP_GLOBAL_Control
0x180027af3  lea     rax, WPP_GLOBAL_Control
0x180027afa  cmp     rcx, rax
0x180027afd  jz      loc_180027F11
0x180027b03  test    byte ptr [rcx+1Ch], 8
0x180027b07  jz      loc_180027F11
0x180027b0d  call    cs:__imp_GetCurrentThreadId
0x180027b13  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b1a  lea     edx, [r13+0Ah]
0x180027b1e  mov     r9d, eax
0x180027b21  lea     r8, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids
0x180027b28  mov     rcx, [rcx+10h]
0x180027b2c  call    WPP_SF_d
0x180027b31  jmp     loc_180027EE1
0x180027b36  cmp     esi, r12d
0x180027b39  jnz     short loc_180027B48
0x180027b3b  mov     rax, [rbp+var_20]
0x180027b3f  mov     [rax+18h], r13d
0x180027b43  jmp     loc_180027EE1
0x180027b48  mov     eax, [rdi+1Ch]
0x180027b4b  lea     ecx, [rax+1]
0x180027b4e  neg     eax
0x180027b50  sbb     eax, eax
0x180027b52  and     ecx, eax
0x180027b54  mov     eax, [rdi+18h]
0x180027b57  sub     rax, rcx
0x180027b5a  cmp     rax, 8
0x180027b5e  jnz     short loc_180027BC2
0x180027b60  mov     rax, [rdi+10h]
0x180027b64  lea     rdx, ?rgPropstat@@3PAGA; "propstat"
0x180027b6b  lea     rcx, [rax+rcx*2]; String1
0x180027b6f  call    cs:__imp__wcsicmp
0x180027b75  test    eax, eax
0x180027b77  jnz     short loc_180027BC2
0x180027b79  mov     rcx, [rbp+var_20]
0x180027b7d  cmp     [rcx+20h], r13d
0x180027b81  jnz     short loc_180027B91
0x180027b83  mov     rax, [rcx+30h]
0x180027b87  cmp     [rax], r12d
0x180027b8a  jnz     short loc_180027BA8
0x180027b8c  mov     [rax], r13d
0x180027b8f  jmp     short loc_180027BA4
0x180027b91  cmp     [rcx+20h], r12d
0x180027b95  jnz     short loc_180027BA8
0x180027b97  mov     rax, [rcx+30h]
0x180027b9b  cmp     [rax], r12d
0x180027b9e  jnz     short loc_180027BA8
0x180027ba0  mov     [rcx+24h], r12d
0x180027ba4  mov     rcx, [rbp+var_20]
0x180027ba8  cmp     [rcx+24h], r12d
0x180027bac  jnz     short loc_180027BBE
0x180027bae  mov     rax, [rcx+30h]
0x180027bb2  cmp     [rax], r13d
0x180027bb5  jnz     short loc_180027BBE
0x180027bb7  mov     [rax], r12d
0x180027bba  mov     rcx, [rbp+var_20]
0x180027bbe  mov     [rcx+20h], r13d
0x180027bc2  mov     rax, [rbp+var_20]
0x180027bc6  cmp     [rax+18h], r12d
0x180027bca  jnz     loc_180027EE1
0x180027bd0  cmp     dword ptr [rax+2Ch], 4
0x180027bd4  jnz     loc_180027EE1
0x180027bda  mov     rax, [rax+30h]
0x180027bde  mov     [rbp+var_18], rax
0x180027be2  mov     r15, [rax+60h]
0x180027be6  lea     r12, [rax+58h]
0x180027bea  test    r15, r15
0x180027bed  jz      loc_180027E96
0x180027bf3  mov     ecx, [r12]
0x180027bf7  mov     [rbp+var_24], ecx
0x180027bfa  test    ecx, ecx
0x180027bfc  jz      loc_180027E96
0x180027c02  mov     r8d, 7; MaxCount
0x180027c08  lea     rdi, [r15+rcx*2]
0x180027c0c  cmp     ecx, r8d
0x180027c0f  jb      short loc_180027C2E
0x180027c11  lea     rdx, aHttp; "http://"
0x180027c18  mov     rcx, r15; String1
0x180027c1b  call    cs:__imp__wcsnicmp
0x180027c21  test    eax, eax
0x180027c23  mov     edx, 1
0x180027c28  cmovz   r13d, edx
0x180027c2c  jmp     short loc_180027C33
0x180027c2e  mov     edx, 1
0x180027c33  xor     ecx, ecx
0x180027c35  mov     rax, r15
0x180027c38  lea     esi, [rcx+2]
0x180027c3b  lea     r8d, [rcx+2Fh]
0x180027c3f  cmp     r15, rdi
0x180027c42  jnb     short loc_180027C59
0x180027c44  cmp     [rax], r8w
0x180027c48  jnz     short loc_180027C51
0x180027c4a  inc     ecx
0x180027c4c  cmp     ecx, 3
0x180027c4f  jz      short loc_180027C59
0x180027c51  add     rax, rsi
0x180027c54  cmp     rax, rdi
0x180027c57  jb      short loc_180027C44
0x180027c59  lea     rcx, [rdi-2]
0x180027c5d  cmp     [rcx], r8w
0x180027c61  jnz     loc_180027D07
0x180027c67  mov     [rbp+var_28], edx
0x180027c6a  cmp     rcx, rax
0x180027c6d  jnz     short loc_180027C74
0x180027c6f  cmp     r13d, edx
0x180027c72  jz      short loc_180027C93
0x180027c74  cmp     [r12], edx
0x180027c78  jz      short loc_180027C93
0x180027c7a  cmp     [r12], esi
0x180027c7e  jnz     short loc_180027C87
0x180027c80  cmp     [rdi-4], r8w
0x180027c85  jz      short loc_180027C93
0x180027c87  xor     r13d, r13d
0x180027c8a  sub     rdi, 4
0x180027c8e  jmp     loc_180027D18
0x180027c93  mov     r13d, edx
0x180027c96  lea     rdx, [rsi+rsi]; uBytes
0x180027c9a  mov     ecx, 40h ; '@'; uFlags
0x180027c9f  call    cs:__imp_LocalAlloc
0x180027ca5  mov     r14, rax
0x180027ca8  test    rax, rax
0x180027cab  jnz     loc_180027D91
0x180027cb1  call    cs:__imp_GetLastError
0x180027cb7  mov     ebx, eax
0x180027cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180027cc0  lea     rax, WPP_GLOBAL_Control
0x180027cc7  cmp     rcx, rax
0x180027cca  jz      loc_180027D89
0x180027cd0  test    byte ptr [rcx+1Ch], 8
0x180027cd4  jz      loc_180027D89
0x180027cda  call    cs:__imp_GetCurrentThreadId
0x180027ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ce7  lea     edx, [r14+0Dh]
0x180027ceb  mov     r9d, eax
0x180027cee  mov     dword ptr [rsp+58h+var_38], ebx
0x180027cf2  lea     r8, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids
0x180027cf9  mov     rcx, [rcx+10h]
0x180027cfd  call    WPP_SF_Dd
0x180027d02  jmp     loc_180027D89
0x180027d07  mov     [rbp+var_28], r14d
0x180027d0b  xor     r13d, r13d
0x180027d0e  jmp     short loc_180027D18
0x180027d10  cmp     rdi, r15
0x180027d13  jz      short loc_180027D1E
0x180027d15  sub     rdi, rsi
0x180027d18  cmp     [rdi], r8w
0x180027d1c  jnz     short loc_180027D10
0x180027d1e  cmp     [rdi], r8w
0x180027d22  lea     rax, [rdi+2]
0x180027d26  cmovnz  rax, rdi
0x180027d2a  mov     rdi, rax
0x180027d2d  mov     eax, [r12]
0x180027d31  lea     rsi, ds:2[rax*2]
0x180027d39  sub     rsi, rdi
0x180027d3c  add     rsi, r15
0x180027d3f  sar     rsi, 1
0x180027d42  cmp     rsi, rdx
0x180027d45  ja      loc_180027C96
0x180027d4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d52  lea     rax, WPP_GLOBAL_Control
0x180027d59  cmp     rcx, rax
0x180027d5c  jz      short loc_180027D89
0x180027d5e  test    byte ptr [rcx+1Ch], 8
0x180027d62  jz      short loc_180027D89
0x180027d64  call    cs:__imp_GetCurrentThreadId
0x180027d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d71  lea     r8, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids
0x180027d78  mov     edx, 0Ch
0x180027d7d  mov     r9d, eax
0x180027d80  mov     rcx, [rcx+10h]
0x180027d84  call    WPP_SF_d
0x180027d89  xor     r13d, r13d
0x180027d8c  jmp     loc_180027ED5
0x180027d91  test    r13d, r13d
0x180027d94  jnz     loc_180027E2B
0x180027d9a  lea     rdx, [rsi-1]
0x180027d9e  mov     [rbp+arg_8], rsi
0x180027da2  lea     r9, [rbp+arg_8]
0x180027da6  mov     r8, r14
0x180027da9  mov     rcx, rdi
0x180027dac  call    cs:__imp_DavUrlDecodeToNtPath
0x180027db2  xor     r13d, r13d
0x180027db5  mov     ebx, eax
0x180027db7  test    eax, eax
0x180027db9  jle     short loc_180027DC4
0x180027dbb  movzx   ebx, ax
0x180027dbe  or      ebx, 80070000h
0x180027dc4  test    ebx, ebx
0x180027dc6  jz      short loc_180027E19
0x180027dc8  mov     r12d, 1
0x180027dce  mov     r15d, r12d
0x180027dd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180027dd8  lea     rax, WPP_GLOBAL_Control
0x180027ddf  cmp     rcx, rax
0x180027de2  jz      loc_180027EE1
0x180027de8  test    byte ptr [rcx+1Ch], 8
0x180027dec  jz      loc_180027EE1
0x180027df2  call    cs:__imp_GetCurrentThreadId
0x180027df8  mov     rcx, cs:WPP_GLOBAL_Control
0x180027dff  lea     edx, [r12+0Dh]
0x180027e04  mov     r9d, eax
0x180027e07  mov     dword ptr [rsp+58h+var_38], ebx
0x180027e0b  mov     rcx, [rcx+10h]
0x180027e0f  call    WPP_SF_lD
0x180027e14  jmp     loc_180027EE1
0x180027e19  cmp     [rbp+var_28], r13d
0x180027e1d  jz      short loc_180027E34
0x180027e1f  mov     rax, [rbp+arg_8]
0x180027e23  mov     [r14+rax*2-2], r13w
0x180027e29  jmp     short loc_180027E34
0x180027e2b  mov     dword ptr [rax], 2Fh ; '/'
0x180027e31  xor     r13d, r13d
0x180027e34  mov     rdi, [rbp+var_18]
0x180027e38  mov     rcx, [rdi+60h]; hMem
0x180027e3c  test    rcx, rcx
0x180027e3f  jz      short loc_180027E4B
0x180027e41  call    cs:__imp_LocalFree
0x180027e47  mov     [rdi+60h], r13
0x180027e4b  mov     [r12], r13d
0x180027e4f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180027e53  mov     rax, [rbp+var_20]
0x180027e57  mov     rcx, [rax+30h]
0x180027e5b  mov     [rcx+60h], r14
0x180027e5f  inc     rdx
0x180027e62  cmp     [r14+rdx*2], r13w
0x180027e67  jnz     short loc_180027E5F
0x180027e69  mov     rax, [rbp+var_20]
0x180027e6d  mov     r15d, r13d
0x180027e70  mov     r12d, 1
0x180027e76  mov     rcx, [rax+30h]
0x180027e7a  mov     [rcx+58h], edx
0x180027e7d  mov     rax, [rbp+var_20]
0x180027e81  mov     ecx, [rbp+var_24]
0x180027e84  cmp     ecx, [rax+40h]
0x180027e87  jnb     short loc_180027EE1
0x180027e89  mov     [rax+38h], rdi
0x180027e8d  mov     rax, [rbp+var_20]
0x180027e91  mov     [rax+40h], ecx
0x180027e94  jmp     short loc_180027EE1
0x180027e96  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e9d  lea     rax, WPP_GLOBAL_Control
0x180027ea4  cmp     rcx, rax
0x180027ea7  jz      short loc_180027ED5
0x180027ea9  test    byte ptr [rcx+1Ch], 8
0x180027ead  jz      short loc_180027ED5
0x180027eaf  mov     ebx, [r12]
0x180027eb3  call    cs:__imp_GetCurrentThreadId
0x180027eb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ec0  mov     r9d, eax
0x180027ec3  mov     [rsp+58h+var_30], ebx
0x180027ec7  mov     [rsp+58h+var_38], r15
0x180027ecc  mov     rcx, [rcx+10h]
0x180027ed0  call    WPP_SF_lqd
0x180027ed5  mov     r15d, dword ptr [rbp+arg_8]
0x180027ed9  mov     ebx, 800401F7h
0x180027ede  mov     r12d, r15d
0x180027ee1  mov     rax, [rbp+var_20]
0x180027ee5  test    rax, rax
0x180027ee8  jz      short loc_180027EFE
0x180027eea  mov     [rax+18h], r13d
0x180027eee  mov     rcx, [rbp+var_20]
0x180027ef2  mov     rax, [rcx]
0x180027ef5  mov     rax, [rax+10h]
0x180027ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027efe  cmp     r15d, r12d
0x180027f01  jnz     short loc_180027F11
0x180027f03  test    r14, r14
0x180027f06  jz      short loc_180027F11
0x180027f08  mov     rcx, r14; hMem
0x180027f0b  call    cs:__imp_LocalFree
0x180027f11  mov     eax, ebx
0x180027f13  add     rsp, 58h
0x180027f17  pop     r15
  ... truncated ...
```
