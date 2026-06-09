# CreateProxyRequest

- ea: `0x1800038cc`
- end: `0x180003b06`
- name: `CreateProxyRequest`
- size: `570`
- prototype: `__int64 __fastcall(__int64, ULONG, int, __int64, ULONG **)`
- caller_count: `15`
- callee_count: `7`
- tags: ``

## callers

- `0x180007ba0`
- `0x180008d20`
- `0x180009010`
- `0x18000b170`
- `0x18000b52c`
- `0x18000b734`
- `0x18000d360`
- `0x18000f930`
- `0x180013bd0`
- `0x180013d60`
- `0x180013f90`
- `0x180014140`
- `0x180014330`
- `0x180014520`
- `0x1800160e0`

## callees

- `0x1800038cc`
- `0x180004474`
- `0x18001c854`
- `0x18001ea48`
- `0x18002c8d4`
- `0x1800342d4`
- `0x18003dc84`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800039d8`
- `KERNEL32!HeapAlloc` at `0x1800039d8`

## string_xrefs

- `0x1800038fb`: `CreateProxyRequest: enter...`

## pseudocode

```c
__int64 __fastcall CreateProxyRequest(__int64 a1, ULONG a2, int a3, __int64 a4, ULONG **a5)
{
  __int64 v8; // r14
  int v9; // r13d
  __int64 v10; // rcx
  ULONG v11; // esi
  ULONG v12; // r15d
  ULONG v13; // eax
  ULONG v14; // ecx
  ULONG v15; // ebx
  bool v16; // cf
  _DWORD *v17; // rax
  ULONG *v18; // r11
  ULONG v19; // ebx
  const wchar_t *v20; // r8
  const wchar_t *v21; // r8
  int v23; // [rsp+30h] [rbp-48h]
  int v24; // [rsp+34h] [rbp-44h]
  ULONG pulResult; // [rsp+98h] [rbp+20h] BYREF

  pulResult = 0;
  v8 = *(_QWORD *)(a4 + 32);
  TRACELogPrint(524290, "CreateProxyRequest: enter...");
  v9 = *(_DWORD *)(a1 + 24);
  v10 = *(_QWORD *)(a1 + 16);
  v23 = *(_DWORD *)(v10 + 28);
  v24 = *(_DWORD *)(a1 + 72);
  if ( *(_DWORD *)a1 != 1229734732 || (unsigned int)FMsgDisabled(*(unsigned int *)(v10 + 48), a1 + 168, 24) )
    return 2147483721LL;
  v11 = (*(_DWORD *)(v8 + 32) + 7) & 0xFFFFFFF8;
  v12 = (*(_DWORD *)(v8 + 16) + 7) & 0xFFFFFFF8;
  if ( (int)DWordAdd4(68, a3, v12, v11, (__int64)&pulResult) < 0 )
    return 2147483716LL;
  v13 = pulResult;
  v14 = pulResult + 7;
  v15 = -1;
  v16 = pulResult + 7 < pulResult;
  if ( pulResult + 7 >= pulResult )
    v15 = pulResult + 7;
  pulResult = v15;
  if ( !v16 )
  {
    v15 &= 0xFFFFFFF8;
    pulResult = v15;
  }
  if ( v14 < v13 )
    return 2147483716LL;
  v17 = HeapAlloc(ghTapisrvHeap, 8u, v15);
  if ( !v17 )
    return 2147483716LL;
  *v17 = v15;
  v17[1] = v23;
  v17[3] = *(_DWORD *)(a1 + 24);
  v17[4] = 24;
  v17[5] = v24;
  v17[6] = *(_DWORD *)(a4 + 72);
  if ( ULongSub(v15, 0x28u, &pulResult) < 0 )
    goto LABEL_19;
  v19 = pulResult;
  v18[10] = pulResult;
  v18[11] = *(_DWORD *)(v8 + 32);
  if ( ULongSub(v19, v11, v18 + 12) < 0 )
    goto LABEL_19;
  v20 = *(const wchar_t **)(v8 + 40);
  if ( v20 )
    StringCbCopyW((STRSAFE_LPWSTR)((char *)v18 + v18[12] + 40), v11, v20);
  v18[13] = *(_DWORD *)(v8 + 16);
  if ( v11 > v19 || ULongSub(v19 - v11, v12, v18 + 14) < 0 )
  {
LABEL_19:
    ServerFree(v18);
    return 2147483716LL;
  }
  v21 = *(const wchar_t **)(v8 + 24);
  if ( v21 )
    StringCbCopyW((STRSAFE_LPWSTR)((char *)v18 + v18[14] + 40), v12, v21);
  v18[15] = 0;
  v18[16] = a2;
  *a5 = v18;
  *(_DWORD *)a4 = v9;
  return 0;
}

```

## disassembly

```asm
0x1800038cc  mov     rax, rsp
0x1800038cf  mov     [rax+8], rbx
0x1800038d3  mov     [rax+18h], rsi
0x1800038d7  mov     [rax+10h], edx
0x1800038da  push    rdi
0x1800038db  push    r12
0x1800038dd  push    r13
0x1800038df  push    r14
0x1800038e1  push    r15
0x1800038e3  sub     rsp, 50h
0x1800038e7  mov     r12, r9
0x1800038ea  mov     ebx, r8d
0x1800038ed  mov     rdi, rcx
0x1800038f0  mov     dword ptr [rax+20h], 0
0x1800038f7  mov     r14, [r9+20h]
0x1800038fb  lea     rdx, aCreateproxyreq; "CreateProxyRequest: enter..."
0x180003902  mov     ecx, 80002h
0x180003907  call    TRACELogPrint
0x18000390c  nop
0x18000390d  mov     r13d, [rdi+18h]
0x180003911  mov     [rsp+78h+var_40], r13d
0x180003916  mov     rcx, [rdi+10h]
0x18000391a  mov     eax, [rcx+1Ch]
0x18000391d  mov     [rsp+78h+var_48], eax
0x180003921  mov     [rsp+78h+var_3C], eax
0x180003925  mov     eax, [rdi+48h]
0x180003928  mov     [rsp+78h+var_44], eax
0x18000392c  mov     [rsp+78h+var_38], eax
0x180003930  cmp     dword ptr [rdi], 494C434Ch
0x180003936  jnz     loc_180003AE0
0x18000393c  lea     rdx, [rdi+0A8h]
0x180003943  xor     r9d, r9d
0x180003946  lea     r8d, [r9+18h]
0x18000394a  mov     ecx, [rcx+30h]
0x18000394d  call    FMsgDisabled
0x180003952  test    eax, eax
0x180003954  jnz     loc_180003AE0
0x18000395a  mov     esi, [r14+20h]
0x18000395e  add     esi, 7
0x180003961  mov     eax, 0FFFFFFF8h
0x180003966  and     esi, eax
0x180003968  mov     r15d, [r14+10h]
0x18000396c  add     r15d, 7
0x180003970  and     r15d, eax
0x180003973  lea     rax, [rsp+78h+pulResult]
0x18000397b  mov     [rsp+78h+var_58], rax
0x180003980  mov     r9d, esi
0x180003983  mov     r8d, r15d
0x180003986  mov     edx, ebx
0x180003988  mov     ecx, 44h ; 'D'
0x18000398d  call    DWordAdd4
0x180003992  test    eax, eax
0x180003994  js      loc_180003AD9
0x18000399a  mov     eax, [rsp+78h+pulResult]
0x1800039a1  lea     ecx, [rax+7]
0x1800039a4  or      ebx, 0FFFFFFFFh
0x1800039a7  cmp     ecx, eax
0x1800039a9  cmovnb  ebx, ecx
0x1800039ac  mov     [rsp+78h+pulResult], ebx
0x1800039b3  jb      short loc_1800039BF
0x1800039b5  and     ebx, 0FFFFFFF8h
0x1800039b8  mov     [rsp+78h+pulResult], ebx
0x1800039bf  mov     edx, ebx
0x1800039c1  cmp     ecx, eax
0x1800039c3  jb      loc_180003AD9
0x1800039c9  mov     r8d, ebx; dwBytes
0x1800039cc  mov     edx, 8; dwFlags
0x1800039d1  mov     rcx, cs:ghTapisrvHeap; hHeap
0x1800039d8  call    cs:__imp_HeapAlloc
0x1800039de  mov     r11, rax
0x1800039e1  test    rax, rax
0x1800039e4  jz      loc_180003AD9
0x1800039ea  mov     [rax], ebx
0x1800039ec  mov     eax, [rsp+78h+var_48]
0x1800039f0  mov     [r11+4], eax
0x1800039f4  mov     edx, [rdi+18h]
0x1800039f7  mov     [r11+0Ch], edx
0x1800039fb  mov     dword ptr [r11+10h], 18h
0x180003a03  mov     eax, [rsp+78h+var_44]
0x180003a07  mov     [r11+14h], eax
0x180003a0b  mov     edx, [r12+48h]
0x180003a10  mov     [r11+18h], edx
0x180003a14  lea     r8, [rsp+78h+pulResult]; pulResult
0x180003a1c  mov     edx, 28h ; '('; ulSubtrahend
0x180003a21  mov     ecx, ebx; ulMinuend
0x180003a23  call    ULongSub
0x180003a28  test    eax, eax
0x180003a2a  js      loc_180003AD1
0x180003a30  mov     ebx, [rsp+78h+pulResult]
0x180003a37  mov     [r11+28h], ebx
0x180003a3b  mov     eax, [r14+20h]
0x180003a3f  mov     [r11+2Ch], eax
0x180003a43  lea     r8, [r11+30h]; pulResult
0x180003a47  mov     edx, esi; ulSubtrahend
0x180003a49  mov     ecx, ebx; ulMinuend
0x180003a4b  call    ULongSub
0x180003a50  test    eax, eax
0x180003a52  js      short loc_180003AD1
0x180003a54  mov     r8, [r14+28h]; pszSrc
0x180003a58  test    r8, r8
0x180003a5b  jz      short loc_180003A6F
0x180003a5d  mov     edx, esi; cbDest
0x180003a5f  mov     ecx, [r11+30h]
0x180003a63  add     rcx, 28h ; '('
0x180003a67  add     rcx, r11; pszDest
0x180003a6a  call    StringCbCopyW
0x180003a6f  mov     eax, [r14+10h]
0x180003a73  mov     [r11+34h], eax
0x180003a77  cmp     esi, ebx
0x180003a79  ja      short loc_180003AD1
0x180003a7b  sub     ebx, esi
0x180003a7d  lea     r8, [r11+38h]; pulResult
0x180003a81  mov     edx, r15d; ulSubtrahend
0x180003a84  mov     ecx, ebx; ulMinuend
0x180003a86  call    ULongSub
0x180003a8b  test    eax, eax
0x180003a8d  js      short loc_180003AD1
0x180003a8f  mov     r8, [r14+18h]; pszSrc
0x180003a93  test    r8, r8
0x180003a96  jz      short loc_180003AAB
0x180003a98  mov     edx, r15d; cbDest
0x180003a9b  mov     ecx, [r11+38h]
0x180003a9f  add     rcx, 28h ; '('
0x180003aa3  add     rcx, r11; pszDest
0x180003aa6  call    StringCbCopyW
0x180003aab  mov     dword ptr [r11+3Ch], 0
0x180003ab3  mov     eax, [rsp+78h+arg_8]
0x180003aba  mov     [r11+40h], eax
0x180003abe  mov     rax, [rsp+78h+arg_20]
0x180003ac6  mov     [rax], r11
0x180003ac9  mov     [r12], r13d
0x180003acd  xor     eax, eax
0x180003acf  jmp     short loc_180003AEC
0x180003ad1  mov     rcx, r11; lpMem
0x180003ad4  call    ServerFree
0x180003ad9  mov     eax, 80000044h
0x180003ade  jmp     short loc_180003AEC
0x180003ae0  mov     eax, 80000049h
0x180003ae5  jmp     short loc_180003AEC
0x180003ae7  mov     eax, 80000049h
0x180003aec  lea     r11, [rsp+78h+var_28]
0x180003af1  mov     rbx, [r11+30h]
0x180003af5  mov     rsi, [r11+40h]
0x180003af9  mov     rsp, r11
0x180003afc  pop     r15
0x180003afe  pop     r14
0x180003b00  pop     r13
0x180003b02  pop     r12
0x180003b04  pop     rdi
0x180003b05  retn
```
