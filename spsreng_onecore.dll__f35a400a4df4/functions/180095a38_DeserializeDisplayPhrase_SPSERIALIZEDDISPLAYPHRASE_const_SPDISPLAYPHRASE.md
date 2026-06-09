# DeserializeDisplayPhrase(SPSERIALIZEDDISPLAYPHRASE const *,SPDISPLAYPHRASE * *)

- ea: `0x180095a38`
- end: `0x180095c01`
- name: `?DeserializeDisplayPhrase@@YAJPEBUSPSERIALIZEDDISPLAYPHRASE@@PEAPEAUSPDISPLAYPHRASE@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(const struct SPSERIALIZEDDISPLAYPHRASE *, struct SPDISPLAYPHRASE **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000af64`

## callees

- `0x180004312`
- `0x18002edf8`
- `0x180095a38`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095bdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095bdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180095af2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180095af2`

## pseudocode

```c
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
0x180095a38  mov     [rsp+arg_8], rbx
0x180095a3d  mov     [rsp+arg_10], rbp
0x180095a42  push    rsi
0x180095a43  push    rdi
0x180095a44  push    r12
0x180095a46  push    r14
0x180095a48  push    r15
0x180095a4a  sub     rsp, 20h
0x180095a4e  mov     rdi, rcx
0x180095a51  mov     r15, rdx
0x180095a54  mov     ecx, [rcx+4]
0x180095a57  lea     eax, [rcx+1]
0x180095a5a  cmp     eax, ecx
0x180095a5c  jb      loc_180095BE5
0x180095a62  shl     rax, 3
0x180095a66  mov     r12d, 0FFFFFFFFh
0x180095a6c  cmp     rax, r12
0x180095a6f  ja      loc_180095BE5
0x180095a75  lea     edx, [rax+2]
0x180095a78  mov     eax, [rdi]
0x180095a7a  cmp     eax, edx
0x180095a7c  jb      loc_180095BE5
0x180095a82  mov     r10d, ecx
0x180095a85  shl     rcx, 9
0x180095a89  cmp     rcx, r12
0x180095a8c  ja      loc_180095BE5
0x180095a92  lea     r8d, [rcx+rdx]
0x180095a96  cmp     r8d, edx
0x180095a99  jb      loc_180095BE5
0x180095a9f  cmp     eax, r8d
0x180095aa2  ja      loc_180095BE5
0x180095aa8  lea     ecx, [rax+10h]; unsigned int
0x180095aab  cmp     ecx, eax
0x180095aad  jb      loc_180095BE5
0x180095ab3  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x180095ab8  mov     [rsp+48h+arg_0], ecx
0x180095abc  mov     edx, 8; unsigned int
0x180095ac1  call    ?ULongSub@@YAJKKPEAK@Z; ULongSub(ulong,ulong,ulong *)
0x180095ac6  test    eax, eax
0x180095ac8  js      loc_180095BE5
0x180095ace  lea     rcx, [r10+r10*2]
0x180095ad2  shl     rcx, 2
0x180095ad6  cmp     rcx, r12
0x180095ad9  ja      loc_180095BE5
0x180095adf  mov     eax, [rsp+48h+arg_0]
0x180095ae3  lea     esi, [rcx+rax]
0x180095ae6  cmp     esi, eax
0x180095ae8  jb      loc_180095BE5
0x180095aee  mov     ecx, esi; cb
0x180095af0  mov     ebp, esi
0x180095af2  call    cs:__imp_CoTaskMemAlloc
0x180095af8  mov     rbx, rax
0x180095afb  test    rax, rax
0x180095afe  jnz     short loc_180095B0A
0x180095b00  mov     eax, 8007000Eh
0x180095b05  jmp     loc_180095BEA
0x180095b0a  mov     ecx, [rdi+4]
0x180095b0d  mov     [rax], ecx
0x180095b0f  add     rax, 10h
0x180095b13  mov     [rbx+8], rax
0x180095b17  lea     r14, [rcx+1]
0x180095b1b  lea     r14, [rcx+r14*2]
0x180095b1f  lea     r14, [rbx+r14*8]
0x180095b23  mov     eax, r14d
0x180095b26  sub     eax, ebx
0x180095b28  cmp     esi, eax
0x180095b2a  jb      loc_180095BDC
0x180095b30  lea     rax, [rcx+1]
0x180095b34  sub     rbp, r14
0x180095b37  lea     rax, [rcx+rax*2]
0x180095b3b  mov     rcx, r14; void *
0x180095b3e  lea     rdx, [rdi+rax*4]; Src
0x180095b42  lea     r8, [rbx+rbp]; Size
0x180095b46  call    memcpy_0
0x180095b4b  mov     r10d, [rbx]
0x180095b4e  mov     [rsp+48h+arg_0], 0
0x180095b56  lea     rdx, [r10+r10*2]
0x180095b5a  shl     rdx, 2; unsigned int
0x180095b5e  cmp     rdx, r12
0x180095b61  ja      short loc_180095BDC
0x180095b63  mov     ecx, [rdi]; unsigned int
0x180095b65  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x180095b6a  call    ?ULongSub@@YAJKKPEAK@Z; ULongSub(ulong,ulong,ulong *)
0x180095b6f  test    eax, eax
0x180095b71  js      short loc_180095BDC
0x180095b73  add     rdi, 8
0x180095b77  xor     edx, edx
0x180095b79  test    r10d, r10d
0x180095b7c  jz      short loc_180095BD5
0x180095b7e  mov     r9d, [rsp+48h+arg_0]
0x180095b83  cmp     dword ptr [rdi], 0
0x180095b86  jz      short loc_180095B94
0x180095b88  cmp     [rdi], r9d
0x180095b8b  ja      short loc_180095B94
0x180095b8d  mov     ecx, [rdi]
0x180095b8f  add     rcx, r14
0x180095b92  jmp     short loc_180095B96
0x180095b94  xor     ecx, ecx
0x180095b96  mov     rax, [rbx+8]
0x180095b9a  lea     r8, [rdx+rdx*2]
0x180095b9e  mov     [rax+r8*8], rcx
0x180095ba2  mov     eax, [rdi+4]
0x180095ba5  test    eax, eax
0x180095ba7  jz      short loc_180095BB4
0x180095ba9  cmp     eax, r9d
0x180095bac  ja      short loc_180095BB4
0x180095bae  lea     rcx, [r14+rax]
0x180095bb2  jmp     short loc_180095BB6
0x180095bb4  xor     ecx, ecx
0x180095bb6  mov     rax, [rbx+8]
0x180095bba  inc     edx
0x180095bbc  mov     [rax+r8*8+8], rcx
0x180095bc1  mov     al, [rdi+8]
0x180095bc4  add     rdi, 0Ch
0x180095bc8  mov     rcx, [rbx+8]
0x180095bcc  mov     [rcx+r8*8+10h], al
0x180095bd1  cmp     edx, [rbx]
0x180095bd3  jb      short loc_180095B83
0x180095bd5  mov     [r15], rbx
0x180095bd8  xor     eax, eax
0x180095bda  jmp     short loc_180095BEA
0x180095bdc  mov     rcx, rbx; pv
0x180095bdf  call    cs:__imp_CoTaskMemFree
0x180095be5  mov     eax, 80004005h
0x180095bea  mov     rbx, [rsp+48h+arg_8]
0x180095bef  mov     rbp, [rsp+48h+arg_10]
0x180095bf4  add     rsp, 20h
0x180095bf8  pop     r15
0x180095bfa  pop     r14
0x180095bfc  pop     r12
0x180095bfe  pop     rdi
0x180095bff  pop     rsi
0x180095c00  retn
```
