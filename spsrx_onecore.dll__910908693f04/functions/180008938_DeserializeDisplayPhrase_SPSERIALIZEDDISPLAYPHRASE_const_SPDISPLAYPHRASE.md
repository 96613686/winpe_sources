# DeserializeDisplayPhrase(SPSERIALIZEDDISPLAYPHRASE const *,SPDISPLAYPHRASE * *)

- ea: `0x180008938`
- end: `0x180008b01`
- name: `?DeserializeDisplayPhrase@@YAJPEBUSPSERIALIZEDDISPLAYPHRASE@@PEAPEAUSPDISPLAYPHRASE@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(const struct SPSERIALIZEDDISPLAYPHRASE *, struct SPDISPLAYPHRASE **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800040f0`

## callees

- `0x1800031c8`
- `0x180008938`
- `0x180008d84`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800089f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800089f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008adf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008adf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DeserializeDisplayPhrase(const struct SPSERIALIZEDDISPLAYPHRASE *a1, struct SPDISPLAYPHRASE **a2)
{
  __int64 v4; // rcx
  __int64 v5; // rax
  unsigned __int64 v6; // rax
  unsigned int v7; // edx
  unsigned int v8; // eax
  unsigned __int64 v9; // rcx
  __int64 v10; // r10
  int v11; // ecx
  unsigned int v12; // esi
  struct SPDISPLAYPHRASE *v13; // rax
  struct SPDISPLAYPHRASE *v14; // rbx
  __int64 v16; // rcx
  char *v17; // r14
  __int64 ulNumTokens; // r10
  int v19; // r10d
  unsigned int *v20; // rdi
  __int64 v21; // rdx
  unsigned int v22; // r9d
  const WCHAR *v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rax
  const WCHAR *v26; // rcx
  BYTE v27; // al
  unsigned int v28; // [rsp+50h] [rbp+8h] BYREF

  v4 = *((unsigned int *)a1 + 1);
  v5 = (unsigned int)(v4 + 1);
  if ( (unsigned int)v5 < (unsigned int)v4 )
    return 2147500037LL;
  v6 = 8 * v5;
  if ( v6 > 0xFFFFFFFF )
    return 2147500037LL;
  v7 = v6 + 2;
  v8 = *(_DWORD *)a1;
  if ( *(_DWORD *)a1 < v7 )
    return 2147500037LL;
  v9 = v4 << 9;
  if ( v9 > 0xFFFFFFFF )
    return 2147500037LL;
  if ( (unsigned int)v9 + v7 < v7 )
    return 2147500037LL;
  if ( v8 > (unsigned int)v9 + v7 )
    return 2147500037LL;
  if ( v8 + 16 < v8 )
    return 2147500037LL;
  v28 = v8 + 16;
  if ( (int)ULongSub(v8 + 16, 8u, &v28) < 0 )
    return 2147500037LL;
  v11 = 12 * v10;
  if ( (unsigned __int64)(12 * v10) > 0xFFFFFFFF )
    return 2147500037LL;
  v12 = v11 + v28;
  if ( v11 + v28 < v28 )
    return 2147500037LL;
  v13 = (struct SPDISPLAYPHRASE *)CoTaskMemAlloc(v12);
  v14 = v13;
  if ( !v13 )
    return 2147942414LL;
  v16 = *((unsigned int *)a1 + 1);
  v13->ulNumTokens = v16;
  v13->pTokens = (SPDISPLAYTOKEN *)&v13[1];
  v17 = (char *)&v13[v16 + 1] + 8 * v16;
  if ( v12 < 8 * ((int)v16 + 2 * ((int)v16 + 1))
    || (memcpy_0((char *)&v13[v16 + 1] + 8 * v16, (char *)a1 + 8 * v16 + 4 * v16 + 8, v12 - 8 * (v16 + 2 * (v16 + 1))),
        ulNumTokens = v14->ulNumTokens,
        v28 = 0,
        (unsigned __int64)(12 * ulNumTokens) > 0xFFFFFFFF)
    || (int)ULongSub(*(_DWORD *)a1, 12 * (int)ulNumTokens, &v28) < 0 )
  {
    CoTaskMemFree(v14);
    return 2147500037LL;
  }
  v20 = (unsigned int *)((char *)a1 + 8);
  v21 = 0;
  if ( v19 )
  {
    v22 = v28;
    do
    {
      if ( *v20 && *v20 <= v22 )
        v23 = (const WCHAR *)&v17[*v20];
      else
        v23 = 0;
      v24 = v21;
      v14->pTokens[v21].pszLexical = v23;
      v25 = v20[1];
      if ( (_DWORD)v25 && (unsigned int)v25 <= v22 )
        v26 = (const WCHAR *)&v17[v25];
      else
        v26 = 0;
      v21 = (unsigned int)(v21 + 1);
      v14->pTokens[v24].pszDisplay = v26;
      v27 = *((_BYTE *)v20 + 8);
      v20 += 3;
      v14->pTokens[v24].bDisplayAttributes = v27;
    }
    while ( (unsigned int)v21 < v14->ulNumTokens );
  }
  *a2 = v14;
  return 0;
}

```

## disassembly

```asm
0x180008938  mov     [rsp+arg_8], rbx
0x18000893d  mov     [rsp+arg_10], rbp
0x180008942  push    rsi
0x180008943  push    rdi
0x180008944  push    r12
0x180008946  push    r14
0x180008948  push    r15
0x18000894a  sub     rsp, 20h
0x18000894e  mov     rdi, rcx
0x180008951  mov     r15, rdx
0x180008954  mov     ecx, [rcx+4]
0x180008957  lea     eax, [rcx+1]
0x18000895a  cmp     eax, ecx
0x18000895c  jb      loc_180008AE5
0x180008962  shl     rax, 3
0x180008966  mov     r12d, 0FFFFFFFFh
0x18000896c  cmp     rax, r12
0x18000896f  ja      loc_180008AE5
0x180008975  lea     edx, [rax+2]
0x180008978  mov     eax, [rdi]
0x18000897a  cmp     eax, edx
0x18000897c  jb      loc_180008AE5
0x180008982  mov     r10d, ecx
0x180008985  shl     rcx, 9
0x180008989  cmp     rcx, r12
0x18000898c  ja      loc_180008AE5
0x180008992  lea     r8d, [rcx+rdx]
0x180008996  cmp     r8d, edx
0x180008999  jb      loc_180008AE5
0x18000899f  cmp     eax, r8d
0x1800089a2  ja      loc_180008AE5
0x1800089a8  lea     ecx, [rax+10h]; unsigned int
0x1800089ab  cmp     ecx, eax
0x1800089ad  jb      loc_180008AE5
0x1800089b3  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x1800089b8  mov     [rsp+48h+arg_0], ecx
0x1800089bc  mov     edx, 8; unsigned int
0x1800089c1  call    ?ULongSub@@YAJKKPEAK@Z; ULongSub(ulong,ulong,ulong *)
0x1800089c6  test    eax, eax
0x1800089c8  js      loc_180008AE5
0x1800089ce  lea     rcx, [r10+r10*2]
0x1800089d2  shl     rcx, 2
0x1800089d6  cmp     rcx, r12
0x1800089d9  ja      loc_180008AE5
0x1800089df  mov     eax, [rsp+48h+arg_0]
0x1800089e3  lea     esi, [rcx+rax]
0x1800089e6  cmp     esi, eax
0x1800089e8  jb      loc_180008AE5
0x1800089ee  mov     ecx, esi; cb
0x1800089f0  mov     ebp, esi
0x1800089f2  call    cs:__imp_CoTaskMemAlloc
0x1800089f8  mov     rbx, rax
0x1800089fb  test    rax, rax
0x1800089fe  jnz     short loc_180008A0A
0x180008a00  mov     eax, 8007000Eh
0x180008a05  jmp     loc_180008AEA
0x180008a0a  mov     ecx, [rdi+4]
0x180008a0d  mov     [rax], ecx
0x180008a0f  add     rax, 10h
0x180008a13  mov     [rbx+8], rax
0x180008a17  lea     r14, [rcx+1]
0x180008a1b  lea     r14, [rcx+r14*2]
0x180008a1f  lea     r14, [rbx+r14*8]
0x180008a23  mov     eax, r14d
0x180008a26  sub     eax, ebx
0x180008a28  cmp     esi, eax
0x180008a2a  jb      loc_180008ADC
0x180008a30  lea     rax, [rcx+1]
0x180008a34  sub     rbp, r14
0x180008a37  lea     rax, [rcx+rax*2]
0x180008a3b  mov     rcx, r14; void *
0x180008a3e  lea     rdx, [rdi+rax*4]; Src
0x180008a42  lea     r8, [rbx+rbp]; Size
0x180008a46  call    memcpy_0
0x180008a4b  mov     r10d, [rbx]
0x180008a4e  mov     [rsp+48h+arg_0], 0
0x180008a56  lea     rdx, [r10+r10*2]
0x180008a5a  shl     rdx, 2; unsigned int
0x180008a5e  cmp     rdx, r12
0x180008a61  ja      short loc_180008ADC
0x180008a63  mov     ecx, [rdi]; unsigned int
0x180008a65  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x180008a6a  call    ?ULongSub@@YAJKKPEAK@Z; ULongSub(ulong,ulong,ulong *)
0x180008a6f  test    eax, eax
0x180008a71  js      short loc_180008ADC
0x180008a73  add     rdi, 8
0x180008a77  xor     edx, edx
0x180008a79  test    r10d, r10d
0x180008a7c  jz      short loc_180008AD5
0x180008a7e  mov     r9d, [rsp+48h+arg_0]
0x180008a83  cmp     dword ptr [rdi], 0
0x180008a86  jz      short loc_180008A94
0x180008a88  cmp     [rdi], r9d
0x180008a8b  ja      short loc_180008A94
0x180008a8d  mov     ecx, [rdi]
0x180008a8f  add     rcx, r14
0x180008a92  jmp     short loc_180008A96
0x180008a94  xor     ecx, ecx
0x180008a96  mov     rax, [rbx+8]
0x180008a9a  lea     r8, [rdx+rdx*2]
0x180008a9e  mov     [rax+r8*8], rcx
0x180008aa2  mov     eax, [rdi+4]
0x180008aa5  test    eax, eax
0x180008aa7  jz      short loc_180008AB4
0x180008aa9  cmp     eax, r9d
0x180008aac  ja      short loc_180008AB4
0x180008aae  lea     rcx, [r14+rax]
0x180008ab2  jmp     short loc_180008AB6
0x180008ab4  xor     ecx, ecx
0x180008ab6  mov     rax, [rbx+8]
0x180008aba  inc     edx
0x180008abc  mov     [rax+r8*8+8], rcx
0x180008ac1  mov     al, [rdi+8]
0x180008ac4  add     rdi, 0Ch
0x180008ac8  mov     rcx, [rbx+8]
0x180008acc  mov     [rcx+r8*8+10h], al
0x180008ad1  cmp     edx, [rbx]
0x180008ad3  jb      short loc_180008A83
0x180008ad5  mov     [r15], rbx
0x180008ad8  xor     eax, eax
0x180008ada  jmp     short loc_180008AEA
0x180008adc  mov     rcx, rbx; pv
0x180008adf  call    cs:__imp_CoTaskMemFree
0x180008ae5  mov     eax, 80004005h
0x180008aea  mov     rbx, [rsp+48h+arg_8]
0x180008aef  mov     rbp, [rsp+48h+arg_10]
0x180008af4  add     rsp, 20h
0x180008af8  pop     r15
0x180008afa  pop     r14
0x180008afc  pop     r12
0x180008afe  pop     rdi
0x180008aff  pop     rsi
0x180008b00  retn
```
