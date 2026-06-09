# HandleDefenderSignals(ulong,tagMPFILE_TRUST_EXTRA_INFO *,SAC_REPUTATION_EXTRA_INFO_ *)

- ea: `0x18002b040`
- end: `0x18002b226`
- name: `?HandleDefenderSignals@@YAJKPEAUtagMPFILE_TRUST_EXTRA_INFO@@PEAUSAC_REPUTATION_EXTRA_INFO_@@@Z`
- size: `486`
- prototype: `__int64 __fastcall(unsigned int, struct tagMPFILE_TRUST_EXTRA_INFO *, struct SAC_REPUTATION_EXTRA_INFO_ *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040550`

## callees

- `0x18002b040`
- `0x18002b22c`
- `0x18002c090`
- `0x18002c34c`
- `0x18004de52`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b100`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b1a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b100`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b1a7`

## string_xrefs

- `0x18002b1e8`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`

## pseudocode

```c
__int64 __fastcall HandleDefenderSignals(
        unsigned int a1,
        struct tagMPFILE_TRUST_EXTRA_INFO *a2,
        struct SAC_REPUTATION_EXTRA_INFO_ *a3)
{
  unsigned int v3; // r12d
  unsigned int v6; // eax
  __int128 v7; // xmm6
  int v8; // eax
  __int64 v9; // rcx
  size_t v10; // r14
  __int64 unique_hlocal; // rax
  HLOCAL v12; // rcx
  void *v13; // r15
  __int64 v14; // rdi
  __int64 v15; // rax
  HLOCAL v16; // rcx
  _OWORD *v17; // rax
  __int128 v18; // xmm0
  __int64 v19; // rdx
  _OWORD *v21; // [rsp+20h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-28h] BYREF
  HLOCAL v23[2]; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  void *v26; // [rsp+A8h] [rbp+58h] BYREF

  v21 = 0;
  v3 = 0;
  v26 = 0;
  v6 = a1;
  v7 = 0;
  while ( v3 < v6 )
  {
    v8 = *((_DWORD *)a2 + 6 * v3 + 1);
    if ( v8 == 1 )
    {
      v9 = *((_QWORD *)a2 + 3 * v3 + 2);
      if ( !*(_DWORD *)(v9 + 4) && *(_DWORD *)(v9 + 8) == 200 )
        v7 = *(_OWORD *)(v9 + 12);
      *((_DWORD *)a3 + 3) = 1;
      *((_DWORD *)a3 + 4) = *(_DWORD *)(v9 + 4);
      *((_DWORD *)a3 + 5) = *(_DWORD *)(v9 + 8);
      *(_OWORD *)((char *)a3 + 24) = v7;
    }
    else
    {
      v10 = *((unsigned int *)a2 + 6 * v3 + 2);
      if ( v8 == 2 )
      {
        if ( !*((_QWORD *)a3 + 8) )
        {
          unique_hlocal = wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, (unsigned int)v10);
          wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
            &v26,
            unique_hlocal);
          v12 = hMem;
          hMem = 0;
          if ( v12 )
            LocalFree(v12);
          v13 = v26;
          if ( !v26 )
          {
            v19 = 1489;
LABEL_29:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v19,
              (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
              (const char *)0x8007000ELL,
              (int)v21);
            return 2147942414LL;
          }
          memcpy_0(v26, *((const void **)a2 + 3 * v3 + 2), v10);
          *((_QWORD *)a3 + 8) = v13;
          *((_DWORD *)a3 + 14) = v10;
          v26 = 0;
        }
      }
      else if ( v8 == 3 )
      {
        if ( (_DWORD)v10 == 8 )
          *((_QWORD *)a3 + 6) = **((unsigned __int8 **)a2 + 3 * v3 + 2);
      }
      else if ( v8 == 4 && (unsigned int)v10 >= 0x30 )
      {
        v14 = *((_QWORD *)a2 + 3 * v3 + 2);
        if ( *(_DWORD *)v14 == 1 && !*(_DWORD *)(v14 + 4) && *(_DWORD *)(v14 + 8) == 32780 && !*((_QWORD *)a3 + 10) )
        {
          v15 = wil::make_unique_hlocal_nothrow<unsigned char [0]>(v23, 32);
          wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
            &v21,
            v15);
          v16 = v23[0];
          v23[0] = 0;
          if ( v16 )
            LocalFree(v16);
          v17 = v21;
          if ( !v21 )
          {
            v19 = 1515;
            goto LABEL_29;
          }
          v18 = *(_OWORD *)(v14 + 16);
          v21 = 0;
          *v17 = v18;
          v17[1] = *(_OWORD *)(v14 + 32);
          *((_QWORD *)a3 + 10) = v17;
          *((_DWORD *)a3 + 18) = 32;
        }
      }
    }
    v6 = a1;
    ++v3;
  }
  return 0;
}

```

## disassembly

```asm
0x18002b040  mov     [rsp-38h+arg_8], rbx
0x18002b045  mov     [rsp-38h+arg_0], ecx
0x18002b049  push    rbp
0x18002b04a  push    rsi
0x18002b04b  push    rdi
0x18002b04c  push    r12
0x18002b04e  push    r13
0x18002b050  push    r14
0x18002b052  push    r15
0x18002b054  mov     rbp, rsp
0x18002b057  sub     rsp, 50h
0x18002b05b  xor     r15d, r15d
0x18002b05e  movaps  [rsp+50h+var_10], xmm6
0x18002b063  mov     [rbp+var_30], r15
0x18002b067  mov     r12d, r15d
0x18002b06a  mov     [rbp+arg_18], r15
0x18002b06e  mov     rbx, r8
0x18002b071  mov     rsi, rdx
0x18002b074  mov     eax, ecx
0x18002b076  xorps   xmm6, xmm6
0x18002b079  cmp     r12d, eax
0x18002b07c  jnb     loc_18002B207
0x18002b082  mov     eax, r12d
0x18002b085  lea     rdi, [rax+rax*2]
0x18002b089  mov     eax, [rsi+rdi*8+4]
0x18002b08d  cmp     eax, 1
0x18002b090  jnz     short loc_18002B0C7
0x18002b092  mov     rcx, [rsi+rdi*8+10h]
0x18002b097  cmp     [rcx+4], r15d
0x18002b09b  jnz     short loc_18002B0AA
0x18002b09d  cmp     dword ptr [rcx+8], 0C8h
0x18002b0a4  jnz     short loc_18002B0AA
0x18002b0a6  movups  xmm6, xmmword ptr [rcx+0Ch]
0x18002b0aa  mov     dword ptr [rbx+0Ch], 1
0x18002b0b1  mov     eax, [rcx+4]
0x18002b0b4  mov     [rbx+10h], eax
0x18002b0b7  mov     eax, [rcx+8]
0x18002b0ba  mov     [rbx+14h], eax
0x18002b0bd  movdqu  xmmword ptr [rbx+18h], xmm6
0x18002b0c2  jmp     loc_18002B1D4
0x18002b0c7  mov     r14d, [rsi+rdi*8+8]
0x18002b0cc  cmp     eax, 2
0x18002b0cf  jnz     short loc_18002B13B
0x18002b0d1  cmp     [rbx+40h], r15
0x18002b0d5  jnz     loc_18002B1D4
0x18002b0db  mov     edx, r14d
0x18002b0de  lea     rcx, [rbp+hMem]
0x18002b0e2  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18002b0e7  mov     rdx, rax
0x18002b0ea  lea     rcx, [rbp+arg_18]
0x18002b0ee  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &&)
0x18002b0f3  mov     rcx, [rbp+hMem]; hMem
0x18002b0f7  mov     [rbp+hMem], r15
0x18002b0fb  test    rcx, rcx
0x18002b0fe  jz      short loc_18002B106
0x18002b100  call    cs:__imp_LocalFree
0x18002b106  mov     r15, [rbp+arg_18]
0x18002b10a  test    r15, r15
0x18002b10d  jz      loc_18002B1DF
0x18002b113  mov     rdx, [rsi+rdi*8+10h]; Src
0x18002b118  mov     r8, r14; Size
0x18002b11b  mov     rcx, r15; void *
0x18002b11e  call    memcpy_0
0x18002b123  mov     [rbx+40h], r15
0x18002b127  xor     r15d, r15d
0x18002b12a  mov     [rbx+38h], r14d
0x18002b12e  mov     [rbp+arg_18], 0
0x18002b136  jmp     loc_18002B1D4
0x18002b13b  cmp     eax, 3
0x18002b13e  jnz     short loc_18002B158
0x18002b140  cmp     r14d, 8
0x18002b144  jnz     loc_18002B1D4
0x18002b14a  mov     rax, [rsi+rdi*8+10h]
0x18002b14f  movzx   ecx, byte ptr [rax]
0x18002b152  mov     [rbx+30h], rcx
0x18002b156  jmp     short loc_18002B1D4
0x18002b158  cmp     eax, 4
0x18002b15b  jnz     short loc_18002B1D4
0x18002b15d  cmp     r14d, 30h ; '0'
0x18002b161  jb      short loc_18002B1D4
0x18002b163  mov     rdi, [rsi+rdi*8+10h]
0x18002b168  cmp     dword ptr [rdi], 1
0x18002b16b  jnz     short loc_18002B1D4
0x18002b16d  cmp     [rdi+4], r15d
0x18002b171  jnz     short loc_18002B1D4
0x18002b173  cmp     dword ptr [rdi+8], 800Ch
0x18002b17a  jnz     short loc_18002B1D4
0x18002b17c  cmp     [rbx+50h], r15
0x18002b180  jnz     short loc_18002B1D4
0x18002b182  lea     edx, [rax+1Ch]
0x18002b185  lea     rcx, [rbp+var_20]
0x18002b189  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18002b18e  mov     rdx, rax
0x18002b191  lea     rcx, [rbp+var_30]
0x18002b195  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &&)
0x18002b19a  mov     rcx, [rbp+var_20]; hMem
0x18002b19e  mov     [rbp+var_20], r15
0x18002b1a2  test    rcx, rcx
0x18002b1a5  jz      short loc_18002B1AD
0x18002b1a7  call    cs:__imp_LocalFree
0x18002b1ad  mov     rax, [rbp+var_30]
0x18002b1b1  test    rax, rax
0x18002b1b4  jz      short loc_18002B200
0x18002b1b6  movups  xmm0, xmmword ptr [rdi+10h]
0x18002b1ba  mov     [rbp+var_30], r15
0x18002b1be  movups  xmmword ptr [rax], xmm0
0x18002b1c1  movups  xmm1, xmmword ptr [rdi+20h]
0x18002b1c5  movups  xmmword ptr [rax+10h], xmm1
0x18002b1c9  mov     [rbx+50h], rax
0x18002b1cd  mov     dword ptr [rbx+48h], 20h ; ' '
0x18002b1d4  mov     eax, [rbp+arg_0]
0x18002b1d7  inc     r12d
0x18002b1da  jmp     loc_18002B079
0x18002b1df  mov     edx, 5D1h; void *
0x18002b1e4  mov     rcx, [rbp+38h]; this
0x18002b1e8  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002b1ef  mov     ebx, 8007000Eh
0x18002b1f4  mov     r9d, ebx; char *
0x18002b1f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b1fc  mov     eax, ebx
0x18002b1fe  jmp     short loc_18002B209
0x18002b200  mov     edx, 5EBh
0x18002b205  jmp     short loc_18002B1E4
0x18002b207  xor     eax, eax
0x18002b209  mov     rbx, [rsp+50h+arg_8]
0x18002b211  movaps  xmm6, [rsp+50h+var_10]
0x18002b216  add     rsp, 50h
0x18002b21a  pop     r15
0x18002b21c  pop     r14
0x18002b21e  pop     r13
0x18002b220  pop     r12
0x18002b222  pop     rdi
0x18002b223  pop     rsi
0x18002b224  pop     rbp
0x18002b225  retn
```
