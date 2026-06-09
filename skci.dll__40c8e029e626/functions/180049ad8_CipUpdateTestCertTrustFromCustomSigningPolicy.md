# CipUpdateTestCertTrustFromCustomSigningPolicy

- ea: `0x180049ad8`
- end: `0x180049c24`
- name: `CipUpdateTestCertTrustFromCustomSigningPolicy`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180010bd4`

## callees

- `0x18003391a`
- `0x180049ad8`

## pseudocode

```c
__int64 CipUpdateTestCertTrustFromCustomSigningPolicy()
{
  int v0; // ebx
  __int64 result; // rax
  __int64 v2; // rsi
  unsigned int v3; // r12d
  __int64 v4; // r14
  __int64 v5; // rcx
  __int64 v6; // rbp
  unsigned int i; // edi
  int v8; // edx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rcx

  v0 = 0;
  result = (__int64)g_CiScenarios;
  while ( v0 < g_CiSignerTypeMax )
  {
    v2 = 0;
    v3 = g_CiScenarios[v0 + 32];
    while ( (unsigned int)v2 < v3 )
    {
      v4 = g_CiSigners;
      v5 = *(unsigned int *)(*(_QWORD *)&g_CiScenarios[2 * v0 + 26] + 4 * v2);
      v6 = 5 * v5;
      if ( !*(_DWORD *)(g_CiSigners + 40 * v5) && *(_DWORD *)(g_CiSigners + 40 * v5 + 8) == 32 )
      {
        for ( i = 0; i < 2; ++i )
        {
          if ( !memcmp_0(*(const void **)(v4 + 8 * v6 + 16), &qword_180037DC0[4 * i], 0x20u) )
          {
            g_CiOptions |= 0x800000u;
            result = (__int64)g_CiScenarios;
            goto LABEL_14;
          }
        }
      }
      v2 = (unsigned int)(v2 + 1);
      result = (__int64)g_CiScenarios;
    }
    ++v0;
  }
LABEL_14:
  v8 = 0;
LABEL_15:
  if ( v8 < g_CiSignerTypeMax )
  {
    v9 = 0;
    while ( 1 )
    {
      if ( (unsigned int)v9 >= g_CiScenarios[v8 + 20] )
      {
        ++v8;
        goto LABEL_15;
      }
      result = 5LL * *(unsigned int *)(*(_QWORD *)&g_CiScenarios[2 * v8 + 14] + 4 * v9);
      if ( *(_DWORD *)(g_CiSigners + 40LL * *(unsigned int *)(*(_QWORD *)&g_CiScenarios[2 * v8 + 14] + 4 * v9)) == 10
        && *(_DWORD *)(g_CiSigners + 40LL * *(unsigned int *)(*(_QWORD *)&g_CiScenarios[2 * v8 + 14] + 4 * v9) + 28) == 11
        && *(_DWORD *)(g_CiSigners + 40LL * *(unsigned int *)(*(_QWORD *)&g_CiScenarios[2 * v8 + 14] + 4 * v9) + 24) == 1 )
      {
        v10 = *(_QWORD *)(g_CiSigners + 40LL * *(unsigned int *)(*(_QWORD *)&g_CiScenarios[2 * v8 + 14] + 4 * v9) + 32);
        v11 = *(_QWORD *)v10 - 0x3782010401062B0ALL;
        if ( *(_QWORD *)v10 == 0x3782010401062B0ALL )
        {
          result = 778;
          v11 = *(unsigned __int16 *)(v10 + 8) - 778LL;
          if ( *(_WORD *)(v10 + 8) == 778 )
          {
            result = 6;
            v11 = *(unsigned __int8 *)(v10 + 10) - 6LL;
          }
        }
        if ( !v11 )
          break;
      }
      v9 = (unsigned int)(v9 + 1);
      result = (__int64)g_CiScenarios;
    }
    g_CiOptions |= 0x1000000u;
  }
  return result;
}

```

## disassembly

```asm
0x180049ad8  push    rbx
0x180049ada  push    rbp
0x180049adb  push    rsi
0x180049adc  push    rdi
0x180049add  push    r12
0x180049adf  push    r14
0x180049ae1  push    r15
0x180049ae3  sub     rsp, 20h
0x180049ae7  xor     ebx, ebx
0x180049ae9  lea     rax, g_CiScenarios
0x180049af0  cmp     ebx, cs:g_CiSignerTypeMax
0x180049af6  jge     loc_180049B7D
0x180049afc  movsxd  r15, ebx
0x180049aff  xor     esi, esi
0x180049b01  mov     r12d, [rax+r15*4+80h]
0x180049b09  cmp     esi, r12d
0x180049b0c  jnb     short loc_180049B6A
0x180049b0e  mov     rax, [rax+r15*8+68h]
0x180049b13  mov     r14, cs:g_CiSigners
0x180049b1a  mov     ecx, [rax+rsi*4]
0x180049b1d  lea     rbp, [rcx+rcx*4]
0x180049b21  cmp     dword ptr [r14+rbp*8], 0
0x180049b26  jnz     short loc_180049B5F
0x180049b28  cmp     dword ptr [r14+rbp*8+8], 20h ; ' '
0x180049b2e  jnz     short loc_180049B5F
0x180049b30  xor     edi, edi
0x180049b32  cmp     edi, 2
0x180049b35  jnb     short loc_180049B5F
0x180049b37  mov     rcx, [r14+rbp*8+10h]; Buf1
0x180049b3c  lea     rax, qword_180037DC0
0x180049b43  mov     edx, edi
0x180049b45  mov     r8d, 20h ; ' '; Size
0x180049b4b  shl     rdx, 5
0x180049b4f  add     rdx, rax; Buf2
0x180049b52  call    memcmp_0
0x180049b57  test    eax, eax
0x180049b59  jz      short loc_180049B6E
0x180049b5b  inc     edi
0x180049b5d  jmp     short loc_180049B32
0x180049b5f  inc     esi
0x180049b61  lea     rax, g_CiScenarios
0x180049b68  jmp     short loc_180049B09
0x180049b6a  inc     ebx
0x180049b6c  jmp     short loc_180049AF0
0x180049b6e  bts     cs:g_CiOptions, 17h
0x180049b76  lea     rax, g_CiScenarios
0x180049b7d  xor     edx, edx
0x180049b7f  cmp     edx, cs:g_CiSignerTypeMax
0x180049b85  jge     loc_180049C14
0x180049b8b  movsxd  r10, edx
0x180049b8e  xor     r8d, r8d
0x180049b91  mov     r11d, [rax+r10*4+50h]
0x180049b96  cmp     r8d, r11d
0x180049b99  jnb     short loc_180049C05
0x180049b9b  mov     rax, [rax+r10*8+38h]
0x180049ba0  mov     ecx, [rax+r8*4]
0x180049ba4  lea     rax, [rcx+rcx*4]
0x180049ba8  mov     rcx, cs:g_CiSigners
0x180049baf  cmp     dword ptr [rcx+rax*8], 0Ah
0x180049bb3  jnz     short loc_180049BF9
0x180049bb5  cmp     dword ptr [rcx+rax*8+1Ch], 0Bh
0x180049bba  jnz     short loc_180049BF9
0x180049bbc  cmp     dword ptr [rcx+rax*8+18h], 1
0x180049bc1  jnz     short loc_180049BF9
0x180049bc3  mov     r9, [rcx+rax*8+20h]
0x180049bc8  mov     rcx, [r9]
0x180049bcb  sub     rcx, cs:qword_180037E30
0x180049bd2  jnz     short loc_180049BF4
0x180049bd4  movzx   ecx, word ptr [r9+8]
0x180049bd9  movzx   eax, cs:word_180037E38
0x180049be0  sub     rcx, rax
0x180049be3  jnz     short loc_180049BF4
0x180049be5  movzx   ecx, byte ptr [r9+0Ah]
0x180049bea  movzx   eax, cs:byte_180037E3A
0x180049bf1  sub     rcx, rax
0x180049bf4  test    rcx, rcx
0x180049bf7  jz      short loc_180049C0C
0x180049bf9  inc     r8d
0x180049bfc  lea     rax, g_CiScenarios
0x180049c03  jmp     short loc_180049B96
0x180049c05  inc     edx
0x180049c07  jmp     loc_180049B7F
0x180049c0c  bts     cs:g_CiOptions, 18h
0x180049c14  add     rsp, 20h
0x180049c18  pop     r15
0x180049c1a  pop     r14
0x180049c1c  pop     r12
0x180049c1e  pop     rdi
0x180049c1f  pop     rsi
0x180049c20  pop     rbp
0x180049c21  pop     rbx
0x180049c22  retn
```
