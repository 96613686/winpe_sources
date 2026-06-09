# SkmiProcessLoadConfigForDriver

- ea: `0x14007c13c`
- end: `0x14007c377`
- name: `SkmiProcessLoadConfigForDriver`
- size: `571`
- prototype: `__int64 __fastcall(int, int, int, int, char, void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14006ec6c`
- `0x140079fbc`

## callees

- `0x14000d020`
- `0x14006c25c`
- `0x14006c7cc`
- `0x14006c84c`
- `0x14007c13c`
- `0x14007dc68`
- `0x14007f5e4`
- `0x1400d64a4`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiProcessLoadConfigForDriver(
        unsigned __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char a5,
        _QWORD *a6)
{
  _QWORD *v6; // r15
  int v11; // edx
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rax
  unsigned int *v14; // r8
  unsigned __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 result; // rax
  int ConfigIpValidationTables; // edi
  int v23; // eax
  unsigned int v24; // ecx
  int v25; // [rsp+70h] [rbp+8h] BYREF

  v6 = a6;
  v25 = 0;
  memset_0(a6, 0, 0x48u);
  v12 = a1 + *(unsigned int *)(a3 + 80);
  if ( v12 <= a1 )
    return 3221225595LL;
  v13 = RtlImageDirectoryEntryToData(a1, v11, 10, (int)&v25);
  v14 = (unsigned int *)v13;
  if ( !v13 )
    goto LABEL_25;
  if ( v13 < a1 )
    return 3221225595LL;
  v15 = v13 + 4;
  if ( v15 <= (unsigned __int64)v14 )
    return 3221225595LL;
  if ( v15 > v12 )
    return 3221225595LL;
  v16 = *v14;
  if ( v25 != (_DWORD)v16 || (unsigned int *)((char *)v14 + v16) <= v14 || (unsigned __int64)v14 + v16 > v12 )
    return 3221225595LL;
  if ( (a5 & 2) == 0 )
    goto LABEL_25;
  if ( (unsigned int)v16 < 0xE6 )
    goto LABEL_25;
  _mm_lfence();
  v17 = *((unsigned __int16 *)v14 + 114);
  if ( !(_WORD)v17 )
    goto LABEL_25;
  if ( (unsigned __int16)v17 > *(_WORD *)(a3 + 6) )
    return 3221225595LL;
  v18 = a3 + *(unsigned __int16 *)(a3 + 20) - 16LL + 40 * v17;
  if ( v18 < a1 || v18 >= v12 || v18 + 40 < a1 || v18 + 40 > v12 )
    return 3221225595LL;
  _mm_lfence();
  v19 = a1 + *(unsigned int *)(v18 + 12) + v14[56];
  if ( !v19 )
    goto LABEL_25;
  if ( v19 < a1 )
    return 3221225595LL;
  if ( v19 >= v12 )
    return 3221225595LL;
  if ( v19 + 8 < v19 )
    return 3221225595LL;
  if ( v19 + 8 > v12 )
    return 3221225595LL;
  v20 = *(unsigned int *)(v19 + 4);
  if ( v20 + v19 <= v19 || v20 + v19 > v12 )
    return 3221225595LL;
  v6[5] = v19;
  *((_DWORD *)v6 + 12) = v20 + 8;
LABEL_25:
  if ( (a5 & 1) != 0 || (result = SkmiCaptureCfgInfo(a1, a2, a3, v6), (int)result >= 0) )
  {
    result = SkmiCaptureImageExceptionValues(a1, a3, v6 + 4, (char *)v6 + 36);
    if ( (int)result >= 0 )
    {
      if ( (SkmiFlags & 0x80000) != 0
        && (ConfigIpValidationTables = SkmiCaptureLoadConfigIpValidationTables(a1, a2, a3, a4),
            ConfigIpValidationTables < 0) )
      {
        SKMI_SECURITY(4352);
        return (unsigned int)ConfigIpValidationTables;
      }
      else
      {
        if ( (SkmiFlags & 0x20000) != 0 )
          SkmiInitializeTracepoints(a4, a1, *((unsigned int *)v6 + 8), *((unsigned int *)v6 + 9));
        v23 = SkmiCaptureSyscallProviderImageData(a1, a2, a3, a4);
        v24 = 0;
        if ( v23 < 0 )
          return (unsigned int)v23;
        return v24;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14007c13c  push    rbx
0x14007c13e  push    rbp
0x14007c13f  push    rsi
0x14007c140  push    rdi
0x14007c141  push    r12
0x14007c143  push    r13
0x14007c145  push    r14
0x14007c147  push    r15
0x14007c149  sub     rsp, 28h
0x14007c14d  mov     r15, [rsp+68h+arg_28]
0x14007c155  xor     r13d, r13d
0x14007c158  mov     rsi, r8
0x14007c15b  mov     [rsp+68h+arg_0], r13d
0x14007c160  mov     r12, rdx
0x14007c163  mov     rbx, rcx
0x14007c166  xor     edx, edx; Val
0x14007c168  mov     rcx, r15; void *
0x14007c16b  lea     r8d, [r13+48h]; Size
0x14007c16f  mov     rbp, r9
0x14007c172  call    memset_0
0x14007c177  mov     edi, [rsi+50h]
0x14007c17a  add     rdi, rbx
0x14007c17d  cmp     rdi, rbx
0x14007c180  jbe     loc_14007C360
0x14007c186  lea     r8d, [r13+0Ah]
0x14007c18a  mov     rcx, rbx
0x14007c18d  lea     r9, [rsp+68h+arg_0]
0x14007c192  call    RtlImageDirectoryEntryToData
0x14007c197  mov     r8, rax
0x14007c19a  test    rax, rax
0x14007c19d  jz      loc_14007C2B9
0x14007c1a3  cmp     rax, rbx
0x14007c1a6  jb      loc_14007C360
0x14007c1ac  add     rax, 4
0x14007c1b0  cmp     rax, r8
0x14007c1b3  jbe     loc_14007C360
0x14007c1b9  cmp     rax, rdi
0x14007c1bc  ja      loc_14007C360
0x14007c1c2  mov     ecx, [r8]
0x14007c1c5  cmp     [rsp+68h+arg_0], ecx
0x14007c1c9  jnz     loc_14007C360
0x14007c1cf  lea     rdx, [r8+rcx]
0x14007c1d3  cmp     rdx, r8
0x14007c1d6  jbe     loc_14007C360
0x14007c1dc  cmp     rdx, rdi
0x14007c1df  ja      loc_14007C360
0x14007c1e5  test    [rsp+68h+arg_20], 2
0x14007c1ed  jz      loc_14007C2B9
0x14007c1f3  cmp     ecx, 0E6h
0x14007c1f9  jb      loc_14007C2B9
0x14007c1ff  lfence
0x14007c202  movzx   eax, word ptr [r8+0E4h]
0x14007c20a  test    ax, ax
0x14007c20d  jz      loc_14007C2B9
0x14007c213  cmp     ax, [rsi+6]
0x14007c217  ja      loc_14007C360
0x14007c21d  lea     rdx, [rax+rax*4]
0x14007c221  movzx   eax, word ptr [rsi+14h]
0x14007c225  add     rax, 0FFFFFFFFFFFFFFF0h
0x14007c229  add     rax, rsi
0x14007c22c  lea     rax, [rax+rdx*8]
0x14007c230  cmp     rax, rbx
0x14007c233  jb      loc_14007C360
0x14007c239  cmp     rax, rdi
0x14007c23c  jnb     loc_14007C360
0x14007c242  lea     rcx, [rax+28h]
0x14007c246  cmp     rcx, rbx
0x14007c249  jb      loc_14007C360
0x14007c24f  cmp     rcx, rdi
0x14007c252  ja      loc_14007C360
0x14007c258  lfence
0x14007c25b  mov     eax, [rax+0Ch]
0x14007c25e  mov     edx, [r8+0E0h]
0x14007c265  add     rax, rbx
0x14007c268  add     rdx, rax
0x14007c26b  jz      short loc_14007C2B9
0x14007c26d  cmp     rdx, rbx
0x14007c270  jb      loc_14007C360
0x14007c276  cmp     rdx, rdi
0x14007c279  jnb     loc_14007C360
0x14007c27f  lea     rax, [rdx+8]
0x14007c283  cmp     rax, rdx
0x14007c286  jbe     loc_14007C360
0x14007c28c  cmp     rax, rdi
0x14007c28f  ja      loc_14007C360
0x14007c295  mov     ecx, [rdx+4]
0x14007c298  lea     rax, [rcx+rdx]
0x14007c29c  cmp     rax, rdx
0x14007c29f  jbe     loc_14007C360
0x14007c2a5  cmp     rax, rdi
0x14007c2a8  ja      loc_14007C360
0x14007c2ae  lea     eax, [rcx+8]
0x14007c2b1  mov     [r15+28h], rdx
0x14007c2b5  mov     [r15+30h], eax
0x14007c2b9  test    [rsp+68h+arg_20], 1
0x14007c2c1  jnz     short loc_14007C2DC
0x14007c2c3  mov     r9, r15
0x14007c2c6  mov     r8, rsi
0x14007c2c9  mov     rdx, r12
0x14007c2cc  mov     rcx, rbx
0x14007c2cf  call    SkmiCaptureCfgInfo
0x14007c2d4  test    eax, eax
0x14007c2d6  js      loc_14007C365
0x14007c2dc  lea     r9, [r15+24h]
0x14007c2e0  mov     rdx, rsi
0x14007c2e3  lea     r8, [r15+20h]
0x14007c2e7  mov     rcx, rbx
0x14007c2ea  call    SkmiCaptureImageExceptionValues
0x14007c2ef  test    eax, eax
0x14007c2f1  js      short loc_14007C365
0x14007c2f3  test    cs:SkmiFlags, 80000h
0x14007c2fd  jz      short loc_14007C324
0x14007c2ff  mov     r9, rbp
0x14007c302  mov     r8, rsi
0x14007c305  mov     rdx, r12
0x14007c308  mov     rcx, rbx
0x14007c30b  call    SkmiCaptureLoadConfigIpValidationTables
0x14007c310  mov     edi, eax
0x14007c312  test    eax, eax
0x14007c314  jns     short loc_14007C324
0x14007c316  mov     ecx, 1100h
0x14007c31b  call    SKMI_SECURITY
0x14007c320  mov     eax, edi
0x14007c322  jmp     short loc_14007C365
0x14007c324  test    cs:SkmiFlags, 20000h
0x14007c32e  jz      short loc_14007C343
0x14007c330  mov     r9d, [r15+24h]
0x14007c334  mov     rdx, rbx
0x14007c337  mov     r8d, [r15+20h]
0x14007c33b  mov     rcx, rbp
0x14007c33e  call    SkmiInitializeTracepoints
0x14007c343  mov     r9, rbp
0x14007c346  mov     r8, rsi
0x14007c349  mov     rdx, r12
0x14007c34c  mov     rcx, rbx
0x14007c34f  call    SkmiCaptureSyscallProviderImageData
0x14007c354  test    eax, eax
0x14007c356  mov     ecx, r13d
0x14007c359  cmovs   ecx, eax
0x14007c35c  mov     eax, ecx
0x14007c35e  jmp     short loc_14007C365
0x14007c360  mov     eax, 0C000007Bh
0x14007c365  add     rsp, 28h
0x14007c369  pop     r15
0x14007c36b  pop     r14
0x14007c36d  pop     r13
0x14007c36f  pop     r12
0x14007c371  pop     rdi
0x14007c372  pop     rsi
0x14007c373  pop     rbp
0x14007c374  pop     rbx
0x14007c375  retn
```
