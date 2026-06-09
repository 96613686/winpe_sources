# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180017cf8`
- end: `0x180017ecd`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800146d0`

## callees

- `0x18000d9b0`
- `0x18000e330`
- `0x180017cf8`
- `0x18001876c`
- `0x1800187e4`
- `0x18001ac50`

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
0x180017cf8  push    rbp
0x180017cfa  push    rbx
0x180017cfb  push    rsi
0x180017cfc  push    rdi
0x180017cfd  push    r12
0x180017cff  push    r14
0x180017d01  lea     rbp, [rsp-0F68h]
0x180017d09  mov     eax, 1068h
0x180017d0e  call    _alloca_probe
0x180017d13  sub     rsp, rax
0x180017d16  mov     rax, cs:__security_cookie
0x180017d1d  xor     rax, rsp
0x180017d20  mov     [rbp+0F90h+var_40], rax
0x180017d27  mov     rax, [rcx+8]
0x180017d2b  xor     ebx, ebx
0x180017d2d  sub     rax, [rcx]
0x180017d30  xor     edi, edi
0x180017d32  mov     r14, rcx
0x180017d35  cmp     rax, 0Ch
0x180017d39  jb      loc_180017E99
0x180017d3f  xor     esi, esi
0x180017d41  mov     r12, 0AAAAAAAAAAAAAAABh
0x180017d4b  xor     edx, edx; Val
0x180017d4d  lea     rcx, [rsp+1090h+var_1040]; void *
0x180017d52  mov     r8d, 1000h; Size
0x180017d58  call    memset_0
0x180017d5d  lea     rax, [rsp+1090h+var_1050]
0x180017d62  mov     [rsp+1090h+var_1050], 1000h
0x180017d6a  mov     [rsp+1090h+var_1068], rax
0x180017d6f  lea     r9, [rsp+1090h+var_104C]
0x180017d74  lea     rax, [rsp+1090h+var_1040]
0x180017d79  mov     [rsp+1090h+var_104C], 0
0x180017d81  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180017d88  mov     [rsp+1090h+var_1070], rax
0x180017d8d  call    wil_details_NtQueryWnfStateData
0x180017d92  mov     ebx, eax
0x180017d94  test    eax, eax
0x180017d96  jnz     loc_180017E82
0x180017d9c  mov     r9d, [rsp+1090h+var_1050]
0x180017da1  mov     rax, r12
0x180017da4  mul     r9
0x180017da7  shr     rdx, 3
0x180017dab  lea     rcx, [rdx+rdx*2]
0x180017daf  shl     rcx, 2
0x180017db3  cmp     r9, rcx
0x180017db6  jz      short loc_180017DC0
0x180017db8  xor     r9d, r9d
0x180017dbb  mov     [rsp+1090h+var_1050], r9d
0x180017dc0  mov     r8, [r14]
0x180017dc3  mov     rax, r12
0x180017dc6  mov     ecx, r9d
0x180017dc9  mul     rcx
0x180017dcc  mov     rcx, [r14+8]
0x180017dd0  mov     rax, r12
0x180017dd3  mov     r10, rdx
0x180017dd6  sub     rcx, r8
0x180017dd9  mul     rcx
0x180017ddc  shr     r10, 3
0x180017de0  shr     rdx, 3
0x180017de4  lea     rax, [rdx+rdx*2]
0x180017de8  lea     rdi, [r8+rax*4]
0x180017dec  jmp     short loc_180017E57
0x180017dee  mov     eax, r10d
0x180017df1  lea     rcx, [rax+rax*2]
0x180017df5  lea     rdx, [rdx+rcx*4]
0x180017df9  lea     rax, [rsp+1090h+var_1040]
0x180017dfe  cmp     rax, rdx
0x180017e01  jz      short loc_180017E28
0x180017e03  mov     r11d, [r8]
0x180017e06  lea     rcx, [rsp+1090h+var_1040]
0x180017e0b  cmp     [rcx], r11d
0x180017e0e  jnz     short loc_180017E1F
0x180017e10  movzx   eax, word ptr [r8+4]
0x180017e15  cmp     [rcx+4], ax
0x180017e19  jz      loc_180017EBF
0x180017e1f  add     rcx, 0Ch
0x180017e23  cmp     rcx, rdx
0x180017e26  jnz     short loc_180017E0B
0x180017e28  mov     eax, r9d
0x180017e2b  add     rax, 0Ch
0x180017e2f  cmp     rax, 1000h
0x180017e35  ja      short loc_180017E53
0x180017e37  movsd   xmm0, qword ptr [r8]
0x180017e3c  add     r9d, 0Ch
0x180017e40  movsd   qword ptr [rdx], xmm0
0x180017e44  inc     r10d
0x180017e47  mov     eax, [r8+8]
0x180017e4b  mov     [rdx+8], eax
0x180017e4e  mov     [rsp+1090h+var_1050], r9d
0x180017e53  add     r8, 0Ch
0x180017e57  lea     rdx, [rsp+1090h+var_1040]
0x180017e5c  cmp     r8, rdi
0x180017e5f  jnz     short loc_180017DEE
0x180017e61  mov     eax, [rsp+1090h+var_104C]
0x180017e65  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180017e6c  mov     [rsp+1090h+var_1060], 1
0x180017e74  mov     r8d, r9d
0x180017e77  mov     dword ptr [rsp+1090h+var_1068], eax
0x180017e7b  call    wil_details_NtUpdateWnfStateData
0x180017e80  mov     edi, eax
0x180017e82  cmp     edi, 0C0000001h
0x180017e88  jnz     short loc_180017E99
0x180017e8a  inc     esi
0x180017e8c  cmp     esi, 64h ; 'd'
0x180017e8f  jge     short loc_180017E99
0x180017e91  test    ebx, ebx
0x180017e93  jz      loc_180017D4B
0x180017e99  test    ebx, ebx
0x180017e9b  cmovz   ebx, edi
0x180017e9e  mov     eax, ebx
0x180017ea0  mov     rcx, [rbp+0F90h+var_40]
0x180017ea7  xor     rcx, rsp; StackCookie
0x180017eaa  call    __security_check_cookie
0x180017eaf  add     rsp, 1068h
0x180017eb6  pop     r14
0x180017eb8  pop     r12
0x180017eba  pop     rdi
0x180017ebb  pop     rsi
0x180017ebc  pop     rbx
0x180017ebd  pop     rbp
0x180017ebe  retn
0x180017ebf  mov     eax, [r8+8]
0x180017ec3  add     [rcx+8], eax
0x180017ec6  mov     r9d, [rsp+1090h+var_1050]
0x180017ecb  jmp     short loc_180017E53
```
