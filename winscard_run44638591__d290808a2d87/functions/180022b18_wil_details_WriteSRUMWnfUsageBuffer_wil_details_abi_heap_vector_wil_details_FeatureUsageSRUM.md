# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180022b18`
- end: `0x180022ce2`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001cc90`

## callees

- `0x18001be10`
- `0x18001c7a8`
- `0x180022b18`
- `0x180023e2c`
- `0x180023ea4`
- `0x18002eec0`

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
0x180022b18  push    rbp
0x180022b1a  push    rbx
0x180022b1b  push    rsi
0x180022b1c  push    rdi
0x180022b1d  push    r12
0x180022b1f  push    r14
0x180022b21  lea     rbp, [rsp-0F68h]
0x180022b29  mov     eax, 1068h
0x180022b2e  call    _alloca_probe
0x180022b33  sub     rsp, rax
0x180022b36  mov     rax, cs:__security_cookie
0x180022b3d  xor     rax, rsp
0x180022b40  mov     [rbp+0F90h+var_40], rax
0x180022b47  mov     rax, [rcx+8]
0x180022b4b  xor     ebx, ebx
0x180022b4d  sub     rax, [rcx]
0x180022b50  xor     edi, edi
0x180022b52  mov     r14, rcx
0x180022b55  cmp     rax, 0Ch
0x180022b59  jb      loc_180022CBC
0x180022b5f  xor     esi, esi
0x180022b61  mov     r12, 0AAAAAAAAAAAAAAABh
0x180022b6b  xor     edx, edx; Val
0x180022b6d  lea     rcx, [rsp+1090h+var_1040]; void *
0x180022b72  mov     r8d, 1000h; Size
0x180022b78  call    memset_0
0x180022b7d  lea     rax, [rsp+1090h+var_1050]
0x180022b82  mov     [rsp+1090h+var_1050], 1000h
0x180022b8a  mov     [rsp+1090h+var_1068], rax
0x180022b8f  lea     r9, [rsp+1090h+var_104C]
0x180022b94  lea     rax, [rsp+1090h+var_1040]
0x180022b99  mov     [rsp+1090h+var_104C], 0
0x180022ba1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180022ba8  mov     [rsp+1090h+var_1070], rax
0x180022bad  call    wil_details_NtQueryWnfStateData
0x180022bb2  mov     ebx, eax
0x180022bb4  test    eax, eax
0x180022bb6  jnz     loc_180022CA5
0x180022bbc  mov     r9d, [rsp+1090h+var_1050]
0x180022bc1  mov     rax, r12
0x180022bc4  mul     r9
0x180022bc7  shr     rdx, 3
0x180022bcb  lea     rcx, [rdx+rdx*2]
0x180022bcf  shl     rcx, 2
0x180022bd3  cmp     r9, rcx
0x180022bd6  jz      short loc_180022BE0
0x180022bd8  xor     r9d, r9d
0x180022bdb  mov     [rsp+1090h+var_1050], r9d
0x180022be0  mov     r8, [r14]
0x180022be3  mov     rax, r12
0x180022be6  mov     ecx, r9d
0x180022be9  mul     rcx
0x180022bec  mov     rcx, [r14+8]
0x180022bf0  mov     rax, r12
0x180022bf3  mov     r11, rdx
0x180022bf6  sub     rcx, r8
0x180022bf9  mul     rcx
0x180022bfc  shr     r11, 3
0x180022c00  shr     rdx, 3
0x180022c04  lea     rax, [rdx+rdx*2]
0x180022c08  lea     rdi, [r8+rax*4]
0x180022c0c  jmp     short loc_180022C7A
0x180022c0e  mov     eax, r11d
0x180022c11  lea     r10, [rsp+1090h+var_1040]
0x180022c16  lea     rcx, [rax+rax*2]
0x180022c1a  lea     r10, [r10+rcx*4]
0x180022c1e  cmp     rdx, r10
0x180022c21  jz      short loc_180022C49
0x180022c23  mov     eax, [r8]
0x180022c26  cmp     [rdx], eax
0x180022c28  jnz     short loc_180022C35
0x180022c2a  movzx   eax, word ptr [r8+4]
0x180022c2f  cmp     [rdx+4], ax
0x180022c33  jz      short loc_180022C3B
0x180022c35  add     rdx, 0Ch
0x180022c39  jmp     short loc_180022C1E
0x180022c3b  mov     eax, [r8+8]
0x180022c3f  add     [rdx+8], eax
0x180022c42  mov     r9d, [rsp+1090h+var_1050]
0x180022c47  jmp     short loc_180022C76
0x180022c49  mov     eax, r9d
0x180022c4c  add     rax, 0Ch
0x180022c50  cmp     rax, 1000h
0x180022c56  ja      short loc_180022C76
0x180022c58  movsd   xmm0, qword ptr [r8]
0x180022c5d  add     r9d, 0Ch
0x180022c61  movsd   qword ptr [r10], xmm0
0x180022c66  inc     r11d
0x180022c69  mov     eax, [r8+8]
0x180022c6d  mov     [r10+8], eax
0x180022c71  mov     [rsp+1090h+var_1050], r9d
0x180022c76  add     r8, 0Ch
0x180022c7a  lea     rdx, [rsp+1090h+var_1040]
0x180022c7f  cmp     r8, rdi
0x180022c82  jnz     short loc_180022C0E
0x180022c84  mov     eax, [rsp+1090h+var_104C]
0x180022c88  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180022c8f  mov     [rsp+1090h+var_1060], 1
0x180022c97  mov     r8d, r9d
0x180022c9a  mov     dword ptr [rsp+1090h+var_1068], eax
0x180022c9e  call    wil_details_NtUpdateWnfStateData
0x180022ca3  mov     edi, eax
0x180022ca5  cmp     edi, 0C0000001h
0x180022cab  jnz     short loc_180022CBC
0x180022cad  inc     esi
0x180022caf  cmp     esi, 64h ; 'd'
0x180022cb2  jge     short loc_180022CBC
0x180022cb4  test    ebx, ebx
0x180022cb6  jz      loc_180022B6B
0x180022cbc  test    ebx, ebx
0x180022cbe  cmovz   ebx, edi
0x180022cc1  mov     eax, ebx
0x180022cc3  mov     rcx, [rbp+0F90h+var_40]
0x180022cca  xor     rcx, rsp; StackCookie
0x180022ccd  call    __security_check_cookie
0x180022cd2  add     rsp, 1068h
0x180022cd9  pop     r14
0x180022cdb  pop     r12
0x180022cdd  pop     rdi
0x180022cde  pop     rsi
0x180022cdf  pop     rbx
0x180022ce0  pop     rbp
0x180022ce1  retn
```
