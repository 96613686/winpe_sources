# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18002a70c`
- end: `0x18002a8e1`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180026a10`

## callees

- `0x1800050f0`
- `0x180005c94`
- `0x18002a70c`
- `0x18002a9a0`
- `0x18002aa18`
- `0x18002af30`

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
        v9 = (unsigned int)v7 / 0xC;
        v10 = *a1 + 12 * ((a1[1] - *a1) / 0xCuLL);
        while ( v8 != v10 )
        {
          v11 = &v17[3 * v9];
          if ( v17 == v11 )
          {
LABEL_12:
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
0x18002a70c  push    rbp
0x18002a70e  push    rbx
0x18002a70f  push    rsi
0x18002a710  push    rdi
0x18002a711  push    r12
0x18002a713  push    r14
0x18002a715  lea     rbp, [rsp-0F68h]
0x18002a71d  mov     eax, 1068h
0x18002a722  call    _alloca_probe
0x18002a727  sub     rsp, rax
0x18002a72a  mov     rax, cs:__security_cookie
0x18002a731  xor     rax, rsp
0x18002a734  mov     [rbp+0F90h+var_40], rax
0x18002a73b  mov     rax, [rcx+8]
0x18002a73f  xor     ebx, ebx
0x18002a741  sub     rax, [rcx]
0x18002a744  xor     edi, edi
0x18002a746  mov     r14, rcx
0x18002a749  cmp     rax, 0Ch
0x18002a74d  jb      loc_18002A8AD
0x18002a753  xor     esi, esi
0x18002a755  mov     r12, 0AAAAAAAAAAAAAAABh
0x18002a75f  xor     edx, edx; Val
0x18002a761  lea     rcx, [rsp+1090h+var_1040]; void *
0x18002a766  mov     r8d, 1000h; Size
0x18002a76c  call    memset_0
0x18002a771  lea     rax, [rsp+1090h+var_1050]
0x18002a776  mov     [rsp+1090h+var_1050], 1000h
0x18002a77e  mov     [rsp+1090h+var_1068], rax
0x18002a783  lea     r9, [rsp+1090h+var_104C]
0x18002a788  lea     rax, [rsp+1090h+var_1040]
0x18002a78d  mov     [rsp+1090h+var_104C], 0
0x18002a795  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002a79c  mov     [rsp+1090h+var_1070], rax
0x18002a7a1  call    wil_details_NtQueryWnfStateData
0x18002a7a6  mov     ebx, eax
0x18002a7a8  test    eax, eax
0x18002a7aa  jnz     loc_18002A896
0x18002a7b0  mov     r9d, [rsp+1090h+var_1050]
0x18002a7b5  mov     rax, r12
0x18002a7b8  mul     r9
0x18002a7bb  shr     rdx, 3
0x18002a7bf  lea     rcx, [rdx+rdx*2]
0x18002a7c3  shl     rcx, 2
0x18002a7c7  cmp     r9, rcx
0x18002a7ca  jz      short loc_18002A7D4
0x18002a7cc  xor     r9d, r9d
0x18002a7cf  mov     [rsp+1090h+var_1050], r9d
0x18002a7d4  mov     r8, [r14]
0x18002a7d7  mov     rax, r12
0x18002a7da  mov     ecx, r9d
0x18002a7dd  mul     rcx
0x18002a7e0  mov     rcx, [r14+8]
0x18002a7e4  mov     rax, r12
0x18002a7e7  mov     r10, rdx
0x18002a7ea  sub     rcx, r8
0x18002a7ed  mul     rcx
0x18002a7f0  shr     r10, 3
0x18002a7f4  shr     rdx, 3
0x18002a7f8  lea     rax, [rdx+rdx*2]
0x18002a7fc  lea     rdi, [r8+rax*4]
0x18002a800  jmp     short loc_18002A86B
0x18002a802  mov     eax, r10d
0x18002a805  lea     rcx, [rax+rax*2]
0x18002a809  lea     rdx, [rdx+rcx*4]
0x18002a80d  lea     rax, [rsp+1090h+var_1040]
0x18002a812  cmp     rax, rdx
0x18002a815  jz      short loc_18002A83C
0x18002a817  mov     r11d, [r8]
0x18002a81a  lea     rcx, [rsp+1090h+var_1040]
0x18002a81f  cmp     [rcx], r11d
0x18002a822  jnz     short loc_18002A833
0x18002a824  movzx   eax, word ptr [r8+4]
0x18002a829  cmp     [rcx+4], ax
0x18002a82d  jz      loc_18002A8D3
0x18002a833  add     rcx, 0Ch
0x18002a837  cmp     rcx, rdx
0x18002a83a  jnz     short loc_18002A81F
0x18002a83c  mov     eax, r9d
0x18002a83f  add     rax, 0Ch
0x18002a843  cmp     rax, 1000h
0x18002a849  ja      short loc_18002A867
0x18002a84b  movsd   xmm0, qword ptr [r8]
0x18002a850  add     r9d, 0Ch
0x18002a854  movsd   qword ptr [rdx], xmm0
0x18002a858  inc     r10d
0x18002a85b  mov     eax, [r8+8]
0x18002a85f  mov     [rdx+8], eax
0x18002a862  mov     [rsp+1090h+var_1050], r9d
0x18002a867  add     r8, 0Ch
0x18002a86b  lea     rdx, [rsp+1090h+var_1040]
0x18002a870  cmp     r8, rdi
0x18002a873  jnz     short loc_18002A802
0x18002a875  mov     eax, [rsp+1090h+var_104C]
0x18002a879  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002a880  mov     [rsp+1090h+var_1060], 1
0x18002a888  mov     r8d, r9d
0x18002a88b  mov     dword ptr [rsp+1090h+var_1068], eax
0x18002a88f  call    wil_details_NtUpdateWnfStateData
0x18002a894  mov     edi, eax
0x18002a896  cmp     edi, 0C0000001h
0x18002a89c  jnz     short loc_18002A8AD
0x18002a89e  inc     esi
0x18002a8a0  cmp     esi, 64h ; 'd'
0x18002a8a3  jge     short loc_18002A8AD
0x18002a8a5  test    ebx, ebx
0x18002a8a7  jz      loc_18002A75F
0x18002a8ad  test    ebx, ebx
0x18002a8af  cmovz   ebx, edi
0x18002a8b2  mov     eax, ebx
0x18002a8b4  mov     rcx, [rbp+0F90h+var_40]
0x18002a8bb  xor     rcx, rsp; StackCookie
0x18002a8be  call    __security_check_cookie
0x18002a8c3  add     rsp, 1068h
0x18002a8ca  pop     r14
0x18002a8cc  pop     r12
0x18002a8ce  pop     rdi
0x18002a8cf  pop     rsi
0x18002a8d0  pop     rbx
0x18002a8d1  pop     rbp
0x18002a8d2  retn
0x18002a8d3  mov     eax, [r8+8]
0x18002a8d7  add     [rcx+8], eax
0x18002a8da  mov     r9d, [rsp+1090h+var_1050]
0x18002a8df  jmp     short loc_18002A867
```
