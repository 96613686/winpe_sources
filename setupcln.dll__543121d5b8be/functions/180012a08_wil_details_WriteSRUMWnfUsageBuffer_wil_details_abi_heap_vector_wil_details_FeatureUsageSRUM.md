# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180012a08`
- end: `0x180012bdd`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000c8e0`

## callees

- `0x180012a08`
- `0x180012be4`
- `0x180012c5c`
- `0x1800131a2`
- `0x1800131e0`
- `0x1800132a0`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int WnfStateData; // ebx
  unsigned int updated; // edi
  int v4; // esi
  int v5; // edx
  int v6; // r8d
  unsigned int v7; // r9d
  __int64 v8; // r8
  unsigned int v9; // r10d
  unsigned __int64 v10; // rdi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
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
        v9 = v7 / 0xC;
        v10 = *a1 + 12 * ((a1[1] - *a1) / 0xCuLL);
        while ( v8 != v10 )
        {
          v11 = &v17[3 * v9];
          if ( v17 == v11 )
          {
LABEL_12:
            if ( (unsigned __int64)v7 + 12 <= 0x1000 )
            {
              v7 += 12;
              *(_QWORD *)v11 = *(_QWORD *)v8;
              ++v9;
              v11[2] = *(_DWORD *)(v8 + 8);
              v15 = v7;
            }
          }
          else
          {
            v12 = v17;
            while ( *v12 != *(_DWORD *)v8 || *((_WORD *)v12 + 2) != *(_WORD *)(v8 + 4) )
            {
              v12 += 3;
              if ( v12 == v11 )
                goto LABEL_12;
            }
            v12[2] += *(_DWORD *)(v8 + 8);
            v7 = v15;
          }
          v8 += 12;
        }
        updated = wil_details_NtUpdateWnfStateData(
                    (unsigned int)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                    (unsigned int)v17,
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
0x180012a08  push    rbp
0x180012a0a  push    rbx
0x180012a0b  push    rsi
0x180012a0c  push    rdi
0x180012a0d  push    r12
0x180012a0f  push    r14
0x180012a11  lea     rbp, [rsp-0F68h]
0x180012a19  mov     eax, 1068h
0x180012a1e  call    _alloca_probe
0x180012a23  sub     rsp, rax
0x180012a26  mov     rax, cs:__security_cookie
0x180012a2d  xor     rax, rsp
0x180012a30  mov     [rbp+0F90h+var_40], rax
0x180012a37  mov     rax, [rcx+8]
0x180012a3b  xor     ebx, ebx
0x180012a3d  sub     rax, [rcx]
0x180012a40  xor     edi, edi
0x180012a42  mov     r14, rcx
0x180012a45  cmp     rax, 0Ch
0x180012a49  jb      loc_180012BA9
0x180012a4f  xor     esi, esi
0x180012a51  mov     r12, 0AAAAAAAAAAAAAAABh
0x180012a5b  xor     edx, edx; Val
0x180012a5d  lea     rcx, [rsp+1090h+var_1040]; void *
0x180012a62  mov     r8d, 1000h; Size
0x180012a68  call    memset_0
0x180012a6d  lea     rax, [rsp+1090h+var_1050]
0x180012a72  mov     [rsp+1090h+var_1050], 1000h
0x180012a7a  mov     [rsp+1090h+var_1068], rax
0x180012a7f  lea     r9, [rsp+1090h+var_104C]
0x180012a84  lea     rax, [rsp+1090h+var_1040]
0x180012a89  mov     [rsp+1090h+var_104C], 0
0x180012a91  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180012a98  mov     [rsp+1090h+var_1070], rax
0x180012a9d  call    wil_details_NtQueryWnfStateData
0x180012aa2  mov     ebx, eax
0x180012aa4  test    eax, eax
0x180012aa6  jnz     loc_180012B92
0x180012aac  mov     r9d, [rsp+1090h+var_1050]
0x180012ab1  mov     rax, r12
0x180012ab4  mul     r9
0x180012ab7  shr     rdx, 3
0x180012abb  lea     rcx, [rdx+rdx*2]
0x180012abf  shl     rcx, 2
0x180012ac3  cmp     r9, rcx
0x180012ac6  jz      short loc_180012AD0
0x180012ac8  xor     r9d, r9d
0x180012acb  mov     [rsp+1090h+var_1050], r9d
0x180012ad0  mov     r8, [r14]
0x180012ad3  mov     rax, r12
0x180012ad6  mov     ecx, r9d
0x180012ad9  mul     rcx
0x180012adc  mov     rcx, [r14+8]
0x180012ae0  mov     rax, r12
0x180012ae3  mov     r10, rdx
0x180012ae6  sub     rcx, r8
0x180012ae9  mul     rcx
0x180012aec  shr     r10, 3
0x180012af0  shr     rdx, 3
0x180012af4  lea     rax, [rdx+rdx*2]
0x180012af8  lea     rdi, [r8+rax*4]
0x180012afc  jmp     short loc_180012B67
0x180012afe  mov     eax, r10d
0x180012b01  lea     rcx, [rax+rax*2]
0x180012b05  lea     rdx, [rdx+rcx*4]
0x180012b09  lea     rax, [rsp+1090h+var_1040]
0x180012b0e  cmp     rax, rdx
0x180012b11  jz      short loc_180012B38
0x180012b13  mov     r11d, [r8]
0x180012b16  lea     rcx, [rsp+1090h+var_1040]
0x180012b1b  cmp     [rcx], r11d
0x180012b1e  jnz     short loc_180012B2F
0x180012b20  movzx   eax, word ptr [r8+4]
0x180012b25  cmp     [rcx+4], ax
0x180012b29  jz      loc_180012BCF
0x180012b2f  add     rcx, 0Ch
0x180012b33  cmp     rcx, rdx
0x180012b36  jnz     short loc_180012B1B
0x180012b38  mov     eax, r9d
0x180012b3b  add     rax, 0Ch
0x180012b3f  cmp     rax, 1000h
0x180012b45  ja      short loc_180012B63
0x180012b47  movsd   xmm0, qword ptr [r8]
0x180012b4c  add     r9d, 0Ch
0x180012b50  movsd   qword ptr [rdx], xmm0
0x180012b54  inc     r10d
0x180012b57  mov     eax, [r8+8]
0x180012b5b  mov     [rdx+8], eax
0x180012b5e  mov     [rsp+1090h+var_1050], r9d
0x180012b63  add     r8, 0Ch
0x180012b67  lea     rdx, [rsp+1090h+var_1040]
0x180012b6c  cmp     r8, rdi
0x180012b6f  jnz     short loc_180012AFE
0x180012b71  mov     eax, [rsp+1090h+var_104C]
0x180012b75  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180012b7c  mov     [rsp+1090h+var_1060], 1
0x180012b84  mov     r8d, r9d
0x180012b87  mov     dword ptr [rsp+1090h+var_1068], eax
0x180012b8b  call    wil_details_NtUpdateWnfStateData
0x180012b90  mov     edi, eax
0x180012b92  cmp     edi, 0C0000001h
0x180012b98  jnz     short loc_180012BA9
0x180012b9a  inc     esi
0x180012b9c  cmp     esi, 64h ; 'd'
0x180012b9f  jge     short loc_180012BA9
0x180012ba1  test    ebx, ebx
0x180012ba3  jz      loc_180012A5B
0x180012ba9  test    ebx, ebx
0x180012bab  cmovz   ebx, edi
0x180012bae  mov     eax, ebx
0x180012bb0  mov     rcx, [rbp+0F90h+var_40]
0x180012bb7  xor     rcx, rsp; StackCookie
0x180012bba  call    __security_check_cookie
0x180012bbf  add     rsp, 1068h
0x180012bc6  pop     r14
0x180012bc8  pop     r12
0x180012bca  pop     rdi
0x180012bcb  pop     rsi
0x180012bcc  pop     rbx
0x180012bcd  pop     rbp
0x180012bce  retn
0x180012bcf  mov     eax, [r8+8]
0x180012bd3  add     [rcx+8], eax
0x180012bd6  mov     r9d, [rsp+1090h+var_1050]
0x180012bdb  jmp     short loc_180012B63
```
