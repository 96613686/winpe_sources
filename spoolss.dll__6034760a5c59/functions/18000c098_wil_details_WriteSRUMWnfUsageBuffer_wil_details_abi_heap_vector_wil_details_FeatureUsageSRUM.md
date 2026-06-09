# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000c098`
- end: `0x18000c262`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180006520`

## callees

- `0x180005320`
- `0x180005cac`
- `0x18000c098`
- `0x18000f89c`
- `0x18000f914`
- `0x180014fd0`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int WnfStateData; // ebx
  unsigned int updated; // edi
  int v4; // esi
  int v5; // edx
  int v6; // r8d
  __int64 v7; // r9
  __int64 v8; // r8
  unsigned int v9; // r11d
  unsigned __int64 v10; // rdi
  _DWORD *v11; // r10
  _DWORD *v12; // rdx
  int v14; // [rsp+20h] [rbp-E0h]
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v17[1024]; // [rsp+50h] [rbp-B0h] BYREF

  WnfStateData = 0;
  updated = 0;
  if ( (unsigned __int64)(a1[1] - *a1) >= 0xC )
  {
    v4 = 0;
    do
    {
      memset_0(v17, 0, sizeof(v17));
      v15 = 4096;
      v16 = 0;
      WnfStateData = wil_details_NtQueryWnfStateData(
                       (unsigned int)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                       v5,
                       v6,
                       (unsigned int)&v16,
                       (__int64)v17,
                       (__int64)&v15);
      if ( !WnfStateData )
      {
        v7 = v15;
        if ( v15 != 12 * (v15 / 0xCuLL) )
        {
          v7 = 0;
          v15 = 0;
        }
        v8 = *a1;
        v9 = (unsigned int)v7 / 0xC;
        v10 = *a1 + 12 * ((a1[1] - *a1) / 0xCuLL);
        while ( 1 )
        {
          v12 = v17;
          if ( v8 == v10 )
            break;
          v11 = &v17[3 * v9];
          while ( v12 != v11 )
          {
            if ( *v12 == *(_DWORD *)v8 && *((_WORD *)v12 + 2) == *(_WORD *)(v8 + 4) )
            {
              v12[2] += *(_DWORD *)(v8 + 8);
              v7 = v15;
              goto LABEL_15;
            }
            v12 += 3;
          }
          if ( (unsigned __int64)(unsigned int)v7 + 12 <= 0x1000 )
          {
            v7 = (unsigned int)(v7 + 12);
            *(_QWORD *)v11 = *(_QWORD *)v8;
            ++v9;
            v11[2] = *(_DWORD *)(v8 + 8);
            v15 = v7;
          }
LABEL_15:
          v8 += 12;
        }
        updated = wil_details_NtUpdateWnfStateData(
                    (__int64)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                    (__int64)v17,
                    v7,
                    v7,
                    v14,
                    v16,
                    1);
      }
      if ( updated != -1073741823 )
        break;
      if ( ++v4 >= 100 )
        break;
    }
    while ( !WnfStateData );
  }
  if ( !WnfStateData )
    return updated;
  return WnfStateData;
}

```

## disassembly

```asm
0x18000c098  push    rbp
0x18000c09a  push    rbx
0x18000c09b  push    rsi
0x18000c09c  push    rdi
0x18000c09d  push    r12
0x18000c09f  push    r14
0x18000c0a1  lea     rbp, [rsp-0F68h]
0x18000c0a9  mov     eax, 1068h
0x18000c0ae  call    _alloca_probe
0x18000c0b3  sub     rsp, rax
0x18000c0b6  mov     rax, cs:__security_cookie
0x18000c0bd  xor     rax, rsp
0x18000c0c0  mov     [rbp+0F90h+var_40], rax
0x18000c0c7  mov     rax, [rcx+8]
0x18000c0cb  xor     ebx, ebx
0x18000c0cd  sub     rax, [rcx]
0x18000c0d0  xor     edi, edi
0x18000c0d2  mov     r14, rcx
0x18000c0d5  cmp     rax, 0Ch
0x18000c0d9  jb      loc_18000C23C
0x18000c0df  xor     esi, esi
0x18000c0e1  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000c0eb  xor     edx, edx; Val
0x18000c0ed  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000c0f2  mov     r8d, 1000h; Size
0x18000c0f8  call    memset_0
0x18000c0fd  lea     rax, [rsp+1090h+var_1050]
0x18000c102  mov     [rsp+1090h+var_1050], 1000h
0x18000c10a  mov     [rsp+1090h+var_1068], rax
0x18000c10f  lea     r9, [rsp+1090h+var_104C]
0x18000c114  lea     rax, [rsp+1090h+var_1040]
0x18000c119  mov     [rsp+1090h+var_104C], 0
0x18000c121  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000c128  mov     [rsp+1090h+var_1070], rax
0x18000c12d  call    wil_details_NtQueryWnfStateData
0x18000c132  mov     ebx, eax
0x18000c134  test    eax, eax
0x18000c136  jnz     loc_18000C225
0x18000c13c  mov     r9d, [rsp+1090h+var_1050]
0x18000c141  mov     rax, r12
0x18000c144  mul     r9
0x18000c147  shr     rdx, 3
0x18000c14b  lea     rcx, [rdx+rdx*2]
0x18000c14f  shl     rcx, 2
0x18000c153  cmp     r9, rcx
0x18000c156  jz      short loc_18000C160
0x18000c158  xor     r9d, r9d
0x18000c15b  mov     [rsp+1090h+var_1050], r9d
0x18000c160  mov     r8, [r14]
0x18000c163  mov     rax, r12
0x18000c166  mov     ecx, r9d
0x18000c169  mul     rcx
0x18000c16c  mov     rcx, [r14+8]
0x18000c170  mov     rax, r12
0x18000c173  mov     r11, rdx
0x18000c176  sub     rcx, r8
0x18000c179  mul     rcx
0x18000c17c  shr     r11, 3
0x18000c180  shr     rdx, 3
0x18000c184  lea     rax, [rdx+rdx*2]
0x18000c188  lea     rdi, [r8+rax*4]
0x18000c18c  jmp     short loc_18000C1FA
0x18000c18e  mov     eax, r11d
0x18000c191  lea     r10, [rsp+1090h+var_1040]
0x18000c196  lea     rcx, [rax+rax*2]
0x18000c19a  lea     r10, [r10+rcx*4]
0x18000c19e  cmp     rdx, r10
0x18000c1a1  jz      short loc_18000C1C9
0x18000c1a3  mov     eax, [r8]
0x18000c1a6  cmp     [rdx], eax
0x18000c1a8  jnz     short loc_18000C1B5
0x18000c1aa  movzx   eax, word ptr [r8+4]
0x18000c1af  cmp     [rdx+4], ax
0x18000c1b3  jz      short loc_18000C1BB
0x18000c1b5  add     rdx, 0Ch
0x18000c1b9  jmp     short loc_18000C19E
0x18000c1bb  mov     eax, [r8+8]
0x18000c1bf  add     [rdx+8], eax
0x18000c1c2  mov     r9d, [rsp+1090h+var_1050]
0x18000c1c7  jmp     short loc_18000C1F6
0x18000c1c9  mov     eax, r9d
0x18000c1cc  add     rax, 0Ch
0x18000c1d0  cmp     rax, 1000h
0x18000c1d6  ja      short loc_18000C1F6
0x18000c1d8  movsd   xmm0, qword ptr [r8]
0x18000c1dd  add     r9d, 0Ch
0x18000c1e1  movsd   qword ptr [r10], xmm0
0x18000c1e6  inc     r11d
0x18000c1e9  mov     eax, [r8+8]
0x18000c1ed  mov     [r10+8], eax
0x18000c1f1  mov     [rsp+1090h+var_1050], r9d
0x18000c1f6  add     r8, 0Ch
0x18000c1fa  lea     rdx, [rsp+1090h+var_1040]
0x18000c1ff  cmp     r8, rdi
0x18000c202  jnz     short loc_18000C18E
0x18000c204  mov     eax, [rsp+1090h+var_104C]
0x18000c208  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000c20f  mov     [rsp+1090h+var_1060], 1
0x18000c217  mov     r8d, r9d
0x18000c21a  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000c21e  call    wil_details_NtUpdateWnfStateData
0x18000c223  mov     edi, eax
0x18000c225  cmp     edi, 0C0000001h
0x18000c22b  jnz     short loc_18000C23C
0x18000c22d  inc     esi
0x18000c22f  cmp     esi, 64h ; 'd'
0x18000c232  jge     short loc_18000C23C
0x18000c234  test    ebx, ebx
0x18000c236  jz      loc_18000C0EB
0x18000c23c  test    ebx, ebx
0x18000c23e  cmovz   ebx, edi
0x18000c241  mov     eax, ebx
0x18000c243  mov     rcx, [rbp+0F90h+var_40]
0x18000c24a  xor     rcx, rsp; StackCookie
0x18000c24d  call    __security_check_cookie
0x18000c252  add     rsp, 1068h
0x18000c259  pop     r14
0x18000c25b  pop     r12
0x18000c25d  pop     rdi
0x18000c25e  pop     rsi
0x18000c25f  pop     rbx
0x18000c260  pop     rbp
0x18000c261  retn
```
