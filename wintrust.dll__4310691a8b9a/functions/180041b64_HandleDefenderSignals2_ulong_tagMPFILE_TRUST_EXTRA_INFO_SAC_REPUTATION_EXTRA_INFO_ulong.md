# HandleDefenderSignals2(ulong,tagMPFILE_TRUST_EXTRA_INFO *,SAC_REPUTATION_EXTRA_INFO_ *,ulong)

- ea: `0x180041b64`
- end: `0x180041d3e`
- name: `?HandleDefenderSignals2@@YAJKPEAUtagMPFILE_TRUST_EXTRA_INFO@@PEAUSAC_REPUTATION_EXTRA_INFO_@@K@Z`
- size: `474`
- prototype: `__int64 __fastcall(unsigned int, struct tagMPFILE_TRUST_EXTRA_INFO *, struct SAC_REPUTATION_EXTRA_INFO_ *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040550`

## callees

- `0x18002b22c`
- `0x18002c090`
- `0x18002c34c`
- `0x180041b64`
- `0x18004de52`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041c1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041cc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041c1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041cc4`

## string_xrefs

- `0x180041d1f`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`

## pseudocode

```c
__int64 __fastcall HandleDefenderSignals2(
        unsigned int a1,
        struct tagMPFILE_TRUST_EXTRA_INFO *a2,
        struct SAC_REPUTATION_EXTRA_INFO_ *a3)
{
  __int128 v5; // xmm6
  unsigned int v6; // r12d
  int v7; // eax
  __int64 v8; // rcx
  size_t v9; // r14
  __int64 unique_hlocal; // rax
  HLOCAL v11; // rcx
  void *v12; // r15
  __int64 v13; // rdi
  __int64 v14; // rax
  HLOCAL v15; // rcx
  _OWORD *v16; // rax
  __int128 v17; // xmm0
  __int64 v19; // rdx
  void *v20; // [rsp+20h] [rbp-38h] BYREF
  _OWORD *v21; // [rsp+28h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+30h] [rbp-28h] BYREF
  HLOCAL v23; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]

  v21 = 0;
  v20 = 0;
  v5 = 0;
  v6 = 0;
  if ( !a1 )
    return 0;
  while ( 1 )
  {
    v7 = *((_DWORD *)a2 + 6 * v6 + 1);
    if ( v7 == 1 )
    {
      v8 = *((_QWORD *)a2 + 3 * v6 + 2);
      if ( !*(_DWORD *)(v8 + 4) && *(_DWORD *)(v8 + 8) == 200 )
        v5 = *(_OWORD *)(v8 + 12);
      *((_DWORD *)a3 + 3) = 1;
      *((_DWORD *)a3 + 4) = *(_DWORD *)(v8 + 4);
      *((_DWORD *)a3 + 5) = *(_DWORD *)(v8 + 8);
      *(_OWORD *)((char *)a3 + 24) = v5;
      goto LABEL_26;
    }
    v9 = *((unsigned int *)a2 + 6 * v6 + 2);
    if ( v7 == 2 )
    {
      if ( !*((_QWORD *)a3 + 8) )
      {
        unique_hlocal = wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, (unsigned int)v9);
        wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
          &v20,
          unique_hlocal);
        v11 = hMem;
        hMem = 0;
        if ( v11 )
          LocalFree(v11);
        v12 = v20;
        if ( !v20 )
        {
          v19 = 1570;
          goto LABEL_29;
        }
        memcpy_0(v20, *((const void **)a2 + 3 * v6 + 2), v9);
        *((_QWORD *)a3 + 8) = v12;
        *((_DWORD *)a3 + 14) = v9;
        v20 = 0;
      }
      goto LABEL_26;
    }
    if ( v7 == 3 )
    {
      if ( (_DWORD)v9 == 8 )
        *((_QWORD *)a3 + 6) = **((unsigned __int8 **)a2 + 3 * v6 + 2);
      goto LABEL_26;
    }
    if ( v7 == 4 && (unsigned int)v9 >= 0x30 )
    {
      v13 = *((_QWORD *)a2 + 3 * v6 + 2);
      if ( *(_DWORD *)v13 == 1 && !*(_DWORD *)(v13 + 4) && *(_DWORD *)(v13 + 8) == 32780 && !*((_QWORD *)a3 + 10) )
        break;
    }
LABEL_26:
    if ( ++v6 >= a1 )
      return 0;
  }
  v14 = wil::make_unique_hlocal_nothrow<unsigned char [0]>(&v23, 32);
  wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
    &v21,
    v14);
  v15 = v23;
  v23 = 0;
  if ( v15 )
    LocalFree(v15);
  v16 = v21;
  if ( v21 )
  {
    v17 = *(_OWORD *)(v13 + 16);
    v21 = 0;
    *v16 = v17;
    v16[1] = *(_OWORD *)(v13 + 32);
    *((_QWORD *)a3 + 10) = v16;
    *((_DWORD *)a3 + 18) = 32;
    goto LABEL_26;
  }
  v19 = 1594;
LABEL_29:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v19,
    (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
    (const char *)0x8007000ELL,
    (int)v20);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180041b64  mov     [rsp-40h+arg_0], ecx
0x180041b68  push    rbp
0x180041b69  push    rbx
0x180041b6a  push    rsi
0x180041b6b  push    rdi
0x180041b6c  push    r12
0x180041b6e  push    r13
0x180041b70  push    r14
0x180041b72  push    r15
0x180041b74  mov     rbp, rsp
0x180041b77  sub     rsp, 58h
0x180041b7b  xor     r15d, r15d
0x180041b7e  movaps  [rsp+58h+var_18], xmm6
0x180041b83  mov     [rbp+var_30], r15
0x180041b87  mov     rbx, r8
0x180041b8a  mov     [rbp+var_38], r15
0x180041b8e  mov     rsi, rdx
0x180041b91  xorps   xmm6, xmm6
0x180041b94  mov     r12d, r15d
0x180041b97  test    ecx, ecx
0x180041b99  jz      loc_180041CFE
0x180041b9f  mov     eax, r12d
0x180041ba2  lea     rdi, [rax+rax*2]
0x180041ba6  mov     eax, [rsi+rdi*8+4]
0x180041baa  cmp     eax, 1
0x180041bad  jnz     short loc_180041BE4
0x180041baf  mov     rcx, [rsi+rdi*8+10h]
0x180041bb4  cmp     [rcx+4], r15d
0x180041bb8  jnz     short loc_180041BC7
0x180041bba  cmp     dword ptr [rcx+8], 0C8h
0x180041bc1  jnz     short loc_180041BC7
0x180041bc3  movups  xmm6, xmmword ptr [rcx+0Ch]
0x180041bc7  mov     dword ptr [rbx+0Ch], 1
0x180041bce  mov     eax, [rcx+4]
0x180041bd1  mov     [rbx+10h], eax
0x180041bd4  mov     eax, [rcx+8]
0x180041bd7  mov     [rbx+14h], eax
0x180041bda  movdqu  xmmword ptr [rbx+18h], xmm6
0x180041bdf  jmp     loc_180041CF1
0x180041be4  mov     r14d, [rsi+rdi*8+8]
0x180041be9  cmp     eax, 2
0x180041bec  jnz     short loc_180041C58
0x180041bee  cmp     [rbx+40h], r15
0x180041bf2  jnz     loc_180041CF1
0x180041bf8  mov     edx, r14d
0x180041bfb  lea     rcx, [rbp+hMem]
0x180041bff  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180041c04  mov     rdx, rax
0x180041c07  lea     rcx, [rbp+var_38]
0x180041c0b  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &&)
0x180041c10  mov     rcx, [rbp+hMem]; hMem
0x180041c14  mov     [rbp+hMem], r15
0x180041c18  test    rcx, rcx
0x180041c1b  jz      short loc_180041C23
0x180041c1d  call    cs:__imp_LocalFree
0x180041c23  mov     r15, [rbp+var_38]
0x180041c27  test    r15, r15
0x180041c2a  jz      loc_180041D16
0x180041c30  mov     rdx, [rsi+rdi*8+10h]; Src
0x180041c35  mov     r8, r14; Size
0x180041c38  mov     rcx, r15; void *
0x180041c3b  call    memcpy_0
0x180041c40  mov     [rbx+40h], r15
0x180041c44  xor     r15d, r15d
0x180041c47  mov     [rbx+38h], r14d
0x180041c4b  mov     [rbp+var_38], 0
0x180041c53  jmp     loc_180041CF1
0x180041c58  cmp     eax, 3
0x180041c5b  jnz     short loc_180041C75
0x180041c5d  cmp     r14d, 8
0x180041c61  jnz     loc_180041CF1
0x180041c67  mov     rax, [rsi+rdi*8+10h]
0x180041c6c  movzx   ecx, byte ptr [rax]
0x180041c6f  mov     [rbx+30h], rcx
0x180041c73  jmp     short loc_180041CF1
0x180041c75  cmp     eax, 4
0x180041c78  jnz     short loc_180041CF1
0x180041c7a  cmp     r14d, 30h ; '0'
0x180041c7e  jb      short loc_180041CF1
0x180041c80  mov     rdi, [rsi+rdi*8+10h]
0x180041c85  cmp     dword ptr [rdi], 1
0x180041c88  jnz     short loc_180041CF1
0x180041c8a  cmp     [rdi+4], r15d
0x180041c8e  jnz     short loc_180041CF1
0x180041c90  cmp     dword ptr [rdi+8], 800Ch
0x180041c97  jnz     short loc_180041CF1
0x180041c99  cmp     [rbx+50h], r15
0x180041c9d  jnz     short loc_180041CF1
0x180041c9f  lea     edx, [rax+1Ch]
0x180041ca2  lea     rcx, [rbp+var_20]
0x180041ca6  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180041cab  mov     rdx, rax
0x180041cae  lea     rcx, [rbp+var_30]
0x180041cb2  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &&)
0x180041cb7  mov     rcx, [rbp+var_20]; hMem
0x180041cbb  mov     [rbp+var_20], r15
0x180041cbf  test    rcx, rcx
0x180041cc2  jz      short loc_180041CCA
0x180041cc4  call    cs:__imp_LocalFree
0x180041cca  mov     rax, [rbp+var_30]
0x180041cce  test    rax, rax
0x180041cd1  jz      short loc_180041D37
0x180041cd3  movups  xmm0, xmmword ptr [rdi+10h]
0x180041cd7  mov     [rbp+var_30], r15
0x180041cdb  movups  xmmword ptr [rax], xmm0
0x180041cde  movups  xmm1, xmmword ptr [rdi+20h]
0x180041ce2  movups  xmmword ptr [rax+10h], xmm1
0x180041ce6  mov     [rbx+50h], rax
0x180041cea  mov     dword ptr [rbx+48h], 20h ; ' '
0x180041cf1  inc     r12d
0x180041cf4  cmp     r12d, [rbp+arg_0]
0x180041cf8  jb      loc_180041B9F
0x180041cfe  xor     eax, eax
0x180041d00  movaps  xmm6, [rsp+58h+var_18]
0x180041d05  add     rsp, 58h
0x180041d09  pop     r15
0x180041d0b  pop     r14
0x180041d0d  pop     r13
0x180041d0f  pop     r12
0x180041d11  pop     rdi
0x180041d12  pop     rsi
0x180041d13  pop     rbx
0x180041d14  pop     rbp
0x180041d15  retn
0x180041d16  mov     edx, 622h; void *
0x180041d1b  mov     rcx, [rbp+40h]; this
0x180041d1f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x180041d26  mov     ebx, 8007000Eh
0x180041d2b  mov     r9d, ebx; char *
0x180041d2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041d33  mov     eax, ebx
0x180041d35  jmp     short loc_180041D00
0x180041d37  mov     edx, 63Ah
0x180041d3c  jmp     short loc_180041D1B
```
