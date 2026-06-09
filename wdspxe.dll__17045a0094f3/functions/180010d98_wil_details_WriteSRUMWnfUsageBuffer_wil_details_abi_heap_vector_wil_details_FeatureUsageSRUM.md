# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180010d98`
- end: `0x180010f85`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180009030`

## callees

- `0x180010d98`
- `0x180011138`
- `0x1800111e0`
- `0x180011a62`
- `0x180011a90`
- `0x180011b50`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int WnfStateData; // ebx
  unsigned int updated; // edi
  int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r8
  unsigned int v9; // r10d
  unsigned __int64 v10; // rdi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
  int v14; // [rsp+20h] [rbp-E0h]
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16[3]; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v17[1024]; // [rsp+50h] [rbp-B0h] BYREF

  WnfStateData = 0;
  updated = 0;
  if ( (unsigned __int64)(a1[1] - *a1) >= 0xC )
  {
    v4 = 0;
    do
    {
      memset_0(v17, 0, sizeof(v17));
      v16[0] = 0;
      v15 = 4096;
      WnfStateData = wil_details_NtQueryWnfStateData(
                       (__int64)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                       v5,
                       v6,
                       (__int64)v16,
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
        while ( v8 != v10 )
        {
          v11 = &v17[3 * v9];
          v12 = v17;
          if ( v17 == v11 )
          {
LABEL_11:
            if ( (unsigned __int64)(unsigned int)v7 + 12 <= 0x1000 )
            {
              v7 = (unsigned int)(v7 + 12);
              *(_QWORD *)v11 = *(_QWORD *)v8;
              ++v9;
              v11[2] = *(_DWORD *)(v8 + 8);
              v15 = v7;
            }
          }
          else
          {
            while ( *v12 != *(_DWORD *)v8 || *((_WORD *)v12 + 2) != *(_WORD *)(v8 + 4) )
            {
              v12 += 3;
              if ( v12 == v11 )
                goto LABEL_11;
            }
            v12[2] += *(_DWORD *)(v8 + 8);
            v7 = v15;
          }
          v8 += 12;
        }
        updated = wil_details_NtUpdateWnfStateData(
                    (__int64)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                    (__int64)v17,
                    v7,
                    v7,
                    v14,
                    v16[0],
                    1);
      }
      ++v4;
    }
    while ( updated == -1073741823 && v4 < 100 && !WnfStateData );
  }
  if ( !WnfStateData )
    return updated;
  return WnfStateData;
}

```

## disassembly

```asm
0x180010d98  mov     rax, rsp
0x180010d9b  mov     [rax+8], rbx
0x180010d9f  mov     [rax+10h], rsi
0x180010da3  mov     [rax+18h], rdi
0x180010da7  push    rbp
0x180010da8  push    r12
0x180010daa  push    r14
0x180010dac  lea     rbp, [rax-0F78h]
0x180010db3  mov     eax, 1060h
0x180010db8  call    _alloca_probe
0x180010dbd  sub     rsp, rax
0x180010dc0  mov     rax, cs:__security_cookie
0x180010dc7  xor     rax, rsp
0x180010dca  mov     [rbp+0F70h+var_20], rax
0x180010dd1  mov     rax, [rcx+8]
0x180010dd5  xor     ebx, ebx
0x180010dd7  sub     rax, [rcx]
0x180010dda  xor     edi, edi
0x180010ddc  mov     r14, rcx
0x180010ddf  cmp     rax, 0Ch
0x180010de3  jb      loc_180010F40
0x180010de9  xor     esi, esi
0x180010deb  mov     r12, 0AAAAAAAAAAAAAAABh
0x180010df5  xor     edx, edx; Val
0x180010df7  lea     rcx, [rsp+1070h+var_1020]; void *
0x180010dfc  mov     r8d, 1000h; Size
0x180010e02  call    memset_0
0x180010e07  and     [rsp+1070h+var_102C], 0
0x180010e0c  lea     rax, [rsp+1070h+var_1030]
0x180010e11  mov     qword ptr [rsp+1070h+var_1048], rax
0x180010e16  lea     r9, [rsp+1070h+var_102C]
0x180010e1b  lea     rax, [rsp+1070h+var_1020]
0x180010e20  mov     [rsp+1070h+var_1030], 1000h
0x180010e28  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180010e2f  mov     [rsp+1070h+var_1050], rax
0x180010e34  call    wil_details_NtQueryWnfStateData
0x180010e39  mov     ebx, eax
0x180010e3b  test    eax, eax
0x180010e3d  jnz     loc_180010F29
0x180010e43  mov     r9d, [rsp+1070h+var_1030]
0x180010e48  mov     rax, r12
0x180010e4b  mul     r9
0x180010e4e  shr     rdx, 3
0x180010e52  lea     rcx, [rdx+rdx*2]
0x180010e56  shl     rcx, 2
0x180010e5a  cmp     r9, rcx
0x180010e5d  jz      short loc_180010E67
0x180010e5f  xor     r9d, r9d
0x180010e62  mov     [rsp+1070h+var_1030], r9d
0x180010e67  mov     r8, [r14]
0x180010e6a  mov     rax, r12
0x180010e6d  mov     ecx, r9d
0x180010e70  mul     rcx
0x180010e73  mov     rcx, [r14+8]
0x180010e77  mov     rax, r12
0x180010e7a  mov     r10, rdx
0x180010e7d  sub     rcx, r8
0x180010e80  mul     rcx
0x180010e83  shr     r10, 3
0x180010e87  shr     rdx, 3
0x180010e8b  lea     rax, [rdx+rdx*2]
0x180010e8f  lea     rdi, [r8+rax*4]
0x180010e93  jmp     short loc_180010EFE
0x180010e95  mov     eax, r10d
0x180010e98  lea     rcx, [rax+rax*2]
0x180010e9c  lea     rdx, [rdx+rcx*4]
0x180010ea0  lea     rax, [rsp+1070h+var_1020]
0x180010ea5  lea     rcx, [rsp+1070h+var_1020]
0x180010eaa  cmp     rax, rdx
0x180010ead  jz      short loc_180010ECF
0x180010eaf  mov     r11d, [r8]
0x180010eb2  cmp     [rcx], r11d
0x180010eb5  jnz     short loc_180010EC6
0x180010eb7  movzx   eax, word ptr [r8+4]
0x180010ebc  cmp     [rcx+4], ax
0x180010ec0  jz      loc_180010F74
0x180010ec6  add     rcx, 0Ch
0x180010eca  cmp     rcx, rdx
0x180010ecd  jnz     short loc_180010EB2
0x180010ecf  mov     eax, r9d
0x180010ed2  add     rax, 0Ch
0x180010ed6  cmp     rax, 1000h
0x180010edc  ja      short loc_180010EFA
0x180010ede  movsd   xmm0, qword ptr [r8]
0x180010ee3  add     r9d, 0Ch
0x180010ee7  movsd   qword ptr [rdx], xmm0
0x180010eeb  inc     r10d
0x180010eee  mov     eax, [r8+8]
0x180010ef2  mov     [rdx+8], eax
0x180010ef5  mov     [rsp+1070h+var_1030], r9d
0x180010efa  add     r8, 0Ch
0x180010efe  lea     rdx, [rsp+1070h+var_1020]
0x180010f03  cmp     r8, rdi
0x180010f06  jnz     short loc_180010E95
0x180010f08  mov     eax, [rsp+1070h+var_102C]
0x180010f0c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180010f13  mov     [rsp+1070h+var_1040], 1
0x180010f1b  mov     r8d, r9d
0x180010f1e  mov     [rsp+1070h+var_1048], eax
0x180010f22  call    wil_details_NtUpdateWnfStateData
0x180010f27  mov     edi, eax
0x180010f29  inc     esi
0x180010f2b  cmp     edi, 0C0000001h
0x180010f31  jnz     short loc_180010F40
0x180010f33  cmp     esi, 64h ; 'd'
0x180010f36  jge     short loc_180010F40
0x180010f38  test    ebx, ebx
0x180010f3a  jz      loc_180010DF5
0x180010f40  test    ebx, ebx
0x180010f42  cmovz   ebx, edi
0x180010f45  mov     eax, ebx
0x180010f47  mov     rcx, [rbp+0F70h+var_20]
0x180010f4e  xor     rcx, rsp; StackCookie
0x180010f51  call    __security_check_cookie
0x180010f56  lea     r11, [rsp+1070h+var_10]
0x180010f5e  mov     rbx, [r11+20h]
0x180010f62  mov     rsi, [r11+28h]
0x180010f66  mov     rdi, [r11+30h]
0x180010f6a  mov     rsp, r11
0x180010f6d  pop     r14
0x180010f6f  pop     r12
0x180010f71  pop     rbp
0x180010f72  retn
0x180010f74  mov     eax, [r8+8]
0x180010f78  add     [rcx+8], eax
0x180010f7b  mov     r9d, [rsp+1070h+var_1030]
0x180010f80  jmp     loc_180010EFA
```
