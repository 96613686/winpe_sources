# HUBDESC_ParseConfigurationDescriptor

- ea: `0x14003bd60`
- end: `0x14003bf4d`
- name: `HUBDESC_ParseConfigurationDescriptor`
- size: `493`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140007e10`
- `0x1400292c4`
- `0x14002c2dc`
- `0x140030998`
- `0x140031754`

## callees

- `0x1400067ac`
- `0x14003bd60`

## pseudocode

```c
unsigned __int8 *__fastcall HUBDESC_ParseConfigurationDescriptor(
        __int64 a1,
        unsigned __int8 *a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        _BYTE *a8,
        __int64 a9)
{
  unsigned __int8 *v9; // r12
  unsigned __int8 *v13; // rdi
  unsigned int v14; // r15d
  unsigned __int64 v15; // rdx
  unsigned __int8 *v16; // rbx
  unsigned __int8 *v17; // rcx
  __int64 v18; // rax
  int v19; // r9d
  int v21; // [rsp+98h] [rbp+20h]

  v21 = a4;
  v9 = 0;
  if ( a8 )
    *a8 = 0;
  if ( *(_BYTE *)a1 < 9u )
    return v9;
  if ( *(_BYTE *)(a1 + 1) != 2 )
    return v9;
  v13 = 0;
  v14 = 0;
  if ( *(_WORD *)(a1 + 2) < 9u )
    return v9;
  while ( 1 )
  {
    v15 = a1 + *(unsigned __int16 *)(a1 + 2);
    v16 = 0;
    v17 = a2;
    if ( (unsigned __int64)a2 < v15 )
    {
      while ( v15 - (unsigned __int64)v17 >= 2 )
      {
        v18 = *v17;
        if ( !(_BYTE)v18 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_39;
          v19 = 11;
          goto LABEL_17;
        }
        if ( v17[1] == 4 )
        {
          v16 = v17;
          goto LABEL_13;
        }
        v17 += v18;
        if ( (unsigned __int64)v17 >= v15 )
          goto LABEL_39;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_39;
      v19 = 10;
LABEL_17:
      LOBYTE(v15) = 2;
      WPP_RECORDER_SF_(a9, v15, 5, v19, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
      goto LABEL_39;
    }
LABEL_13:
    if ( !v16 )
      goto LABEL_39;
    if ( a1 + *(unsigned __int16 *)(a1 + 2) - (unsigned __int64)v16 < 9 )
    {
      v16 = 0;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_39;
      v19 = 12;
      goto LABEL_17;
    }
    v13 = v16;
    if ( a3 != -1 )
    {
      if ( v16[2] == a3 )
        ++v14;
      else
        v13 = 0;
    }
    if ( a4 != -1 && v16[3] != a4 )
      v13 = 0;
    if ( a5 != -1 && v16[5] != a5 )
      v13 = 0;
    if ( a6 != -1 && v16[6] != a6 )
      v13 = 0;
    if ( a7 != -1 && v16[7] != a7 )
      v13 = 0;
    a2 = &v16[*v16];
LABEL_39:
    if ( v9 )
      break;
    if ( v13 )
    {
      v9 = v13;
      if ( !a8 )
        return v9;
      if ( v14 > 1 )
        goto LABEL_47;
    }
    if ( !v16 )
      return v9;
    a4 = v21;
  }
  if ( v14 > 1 && a8 )
LABEL_47:
    *a8 = 1;
  return v9;
}

```

## disassembly

```asm
0x14003bd60  mov     [rsp+arg_18], r9d
0x14003bd65  push    rbx
0x14003bd66  push    rbp
0x14003bd67  push    rsi
0x14003bd68  push    rdi
0x14003bd69  push    r12
0x14003bd6b  push    r13
0x14003bd6d  push    r14
0x14003bd6f  push    r15
0x14003bd71  sub     rsp, 38h
0x14003bd75  mov     rsi, [rsp+78h+arg_38]
0x14003bd7d  xor     r12d, r12d
0x14003bd80  mov     r13d, r8d
0x14003bd83  mov     r14, rdx
0x14003bd86  mov     rbp, rcx
0x14003bd89  test    rsi, rsi
0x14003bd8c  jz      short loc_14003BD91
0x14003bd8e  mov     [rsi], r12b
0x14003bd91  mov     r8d, 9
0x14003bd97  cmp     [rcx], r8b
0x14003bd9a  jb      loc_14003BF38
0x14003bda0  cmp     byte ptr [rcx+1], 2
0x14003bda4  jnz     loc_14003BF38
0x14003bdaa  xor     edi, edi
0x14003bdac  xor     r15d, r15d
0x14003bdaf  cmp     [rcx+2], r8w
0x14003bdb4  jb      loc_14003BF38
0x14003bdba  movzx   edx, word ptr [rbp+2]
0x14003bdbe  lea     r11, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003bdc5  add     rdx, rbp
0x14003bdc8  lea     r10, WPP_RECORDER_INITIALIZED
0x14003bdcf  xor     ebx, ebx
0x14003bdd1  mov     rcx, r14
0x14003bdd4  cmp     r14, rdx
0x14003bdd7  jnb     short loc_14003BE02
0x14003bdd9  mov     rax, rdx
0x14003bddc  sub     rax, rcx
0x14003bddf  cmp     rax, 2
0x14003bde3  jb      short loc_14003BE61
0x14003bde5  movzx   eax, byte ptr [rcx]
0x14003bde8  test    al, al
0x14003bdea  jz      short loc_14003BE4C
0x14003bdec  cmp     byte ptr [rcx+1], 4
0x14003bdf0  jz      short loc_14003BDFF
0x14003bdf2  add     rcx, rax
0x14003bdf5  cmp     rcx, rdx
0x14003bdf8  jb      short loc_14003BDD9
0x14003bdfa  jmp     loc_14003BEFA
0x14003bdff  mov     rbx, rcx
0x14003be02  test    rbx, rbx
0x14003be05  jz      loc_14003BEFA
0x14003be0b  movzx   eax, word ptr [rbp+2]
0x14003be0f  sub     rax, rbx
0x14003be12  add     rax, rbp
0x14003be15  cmp     rax, r8
0x14003be18  jnb     short loc_14003BE76
0x14003be1a  xor     ebx, ebx
0x14003be1c  cmp     cs:WPP_RECORDER_INITIALIZED, r10; __annotation("TMF:",
0x14003be23  jz      loc_14003BEFA
0x14003be29  lea     r9d, [rbx+0Ch]
0x14003be2d  mov     rcx, [rsp+78h+arg_40]
0x14003be35  mov     r8d, 5
0x14003be3b  mov     dl, 2
0x14003be3d  mov     [rsp+78h+var_58], r11
0x14003be42  call    WPP_RECORDER_SF_
0x14003be47  jmp     loc_14003BEFA
0x14003be4c  cmp     cs:WPP_RECORDER_INITIALIZED, r10; __annotation("TMF:",
0x14003be53  jz      loc_14003BEFA
0x14003be59  mov     r9d, 0Bh
0x14003be5f  jmp     short loc_14003BE2D
0x14003be61  cmp     cs:WPP_RECORDER_INITIALIZED, r10; __annotation("TMF:",
0x14003be68  jz      loc_14003BEFA
0x14003be6e  mov     r9d, 0Ah
0x14003be74  jmp     short loc_14003BE2D
0x14003be76  mov     rdi, rbx
0x14003be79  cmp     r13d, 0FFFFFFFFh
0x14003be7d  jz      short loc_14003BE8F
0x14003be7f  movzx   eax, byte ptr [rbx+2]
0x14003be83  cmp     eax, r13d
0x14003be86  jz      short loc_14003BE8C
0x14003be88  xor     edi, edi
0x14003be8a  jmp     short loc_14003BE8F
0x14003be8c  inc     r15d
0x14003be8f  cmp     r9d, 0FFFFFFFFh
0x14003be93  jz      short loc_14003BEA2
0x14003be95  movzx   ecx, byte ptr [rbx+3]
0x14003be99  xor     eax, eax
0x14003be9b  cmp     ecx, r9d
0x14003be9e  cmovnz  rdi, rax
0x14003bea2  cmp     [rsp+78h+arg_20], 0FFFFFFFFh
0x14003beaa  jz      short loc_14003BEBD
0x14003beac  movzx   ecx, byte ptr [rbx+5]
0x14003beb0  xor     eax, eax
0x14003beb2  cmp     ecx, [rsp+78h+arg_20]
0x14003beb9  cmovnz  rdi, rax
0x14003bebd  cmp     [rsp+78h+arg_28], 0FFFFFFFFh
0x14003bec5  jz      short loc_14003BED8
0x14003bec7  movzx   ecx, byte ptr [rbx+6]
0x14003becb  xor     eax, eax
0x14003becd  cmp     ecx, [rsp+78h+arg_28]
0x14003bed4  cmovnz  rdi, rax
0x14003bed8  cmp     [rsp+78h+arg_30], 0FFFFFFFFh
0x14003bee0  jz      short loc_14003BEF3
0x14003bee2  movzx   ecx, byte ptr [rbx+7]
0x14003bee6  xor     eax, eax
0x14003bee8  cmp     ecx, [rsp+78h+arg_30]
0x14003beef  cmovnz  rdi, rax
0x14003bef3  movzx   r14d, byte ptr [rbx]
0x14003bef7  add     r14, rbx
0x14003befa  test    r12, r12
0x14003befd  jnz     short loc_14003BF2A
0x14003beff  test    rdi, rdi
0x14003bf02  jz      short loc_14003BF12
0x14003bf04  mov     r12, rdi
0x14003bf07  test    rsi, rsi
0x14003bf0a  jz      short loc_14003BF38
0x14003bf0c  cmp     r15d, 1
0x14003bf10  ja      short loc_14003BF35
0x14003bf12  test    rbx, rbx
0x14003bf15  jz      short loc_14003BF38
0x14003bf17  mov     r9d, [rsp+78h+arg_18]
0x14003bf1f  mov     r8d, 9
0x14003bf25  jmp     loc_14003BDBA
0x14003bf2a  cmp     r15d, 1
0x14003bf2e  jbe     short loc_14003BF38
0x14003bf30  test    rsi, rsi
0x14003bf33  jz      short loc_14003BF38
0x14003bf35  mov     byte ptr [rsi], 1
0x14003bf38  mov     rax, r12
0x14003bf3b  add     rsp, 38h
0x14003bf3f  pop     r15
0x14003bf41  pop     r14
0x14003bf43  pop     r13
0x14003bf45  pop     r12
0x14003bf47  pop     rdi
0x14003bf48  pop     rsi
0x14003bf49  pop     rbp
0x14003bf4a  pop     rbx
0x14003bf4b  retn
```
