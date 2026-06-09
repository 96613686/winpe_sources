# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18001704c`
- end: `0x180017216`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180013c40`

## callees

- `0x1800112dc`
- `0x180012880`
- `0x180013304`
- `0x18001704c`
- `0x180018cac`
- `0x180037750`

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
0x18001704c  push    rbp
0x18001704e  push    rbx
0x18001704f  push    rsi
0x180017050  push    rdi
0x180017051  push    r12
0x180017053  push    r14
0x180017055  lea     rbp, [rsp-0F68h]
0x18001705d  mov     eax, 1068h
0x180017062  call    _alloca_probe
0x180017067  sub     rsp, rax
0x18001706a  mov     rax, cs:__security_cookie
0x180017071  xor     rax, rsp
0x180017074  mov     [rbp+0F90h+var_40], rax
0x18001707b  mov     rax, [rcx+8]
0x18001707f  xor     ebx, ebx
0x180017081  sub     rax, [rcx]
0x180017084  xor     edi, edi
0x180017086  mov     r14, rcx
0x180017089  cmp     rax, 0Ch
0x18001708d  jb      loc_1800171F0
0x180017093  xor     esi, esi
0x180017095  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001709f  xor     edx, edx; Val
0x1800170a1  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800170a6  mov     r8d, 1000h; Size
0x1800170ac  call    memset_0
0x1800170b1  lea     rax, [rsp+1090h+var_1050]
0x1800170b6  mov     [rsp+1090h+var_1050], 1000h
0x1800170be  mov     [rsp+1090h+var_1068], rax
0x1800170c3  lea     r9, [rsp+1090h+var_104C]
0x1800170c8  lea     rax, [rsp+1090h+var_1040]
0x1800170cd  mov     [rsp+1090h+var_104C], 0
0x1800170d5  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800170dc  mov     [rsp+1090h+var_1070], rax
0x1800170e1  call    wil_details_NtQueryWnfStateData
0x1800170e6  mov     ebx, eax
0x1800170e8  test    eax, eax
0x1800170ea  jnz     loc_1800171D9
0x1800170f0  mov     r9d, [rsp+1090h+var_1050]
0x1800170f5  mov     rax, r12
0x1800170f8  mul     r9
0x1800170fb  shr     rdx, 3
0x1800170ff  lea     rcx, [rdx+rdx*2]
0x180017103  shl     rcx, 2
0x180017107  cmp     r9, rcx
0x18001710a  jz      short loc_180017114
0x18001710c  xor     r9d, r9d
0x18001710f  mov     [rsp+1090h+var_1050], r9d
0x180017114  mov     r8, [r14]
0x180017117  mov     rax, r12
0x18001711a  mov     ecx, r9d
0x18001711d  mul     rcx
0x180017120  mov     rcx, [r14+8]
0x180017124  mov     rax, r12
0x180017127  mov     r11, rdx
0x18001712a  sub     rcx, r8
0x18001712d  mul     rcx
0x180017130  shr     r11, 3
0x180017134  shr     rdx, 3
0x180017138  lea     rax, [rdx+rdx*2]
0x18001713c  lea     rdi, [r8+rax*4]
0x180017140  jmp     short loc_1800171AE
0x180017142  mov     eax, r11d
0x180017145  lea     r10, [rsp+1090h+var_1040]
0x18001714a  lea     rcx, [rax+rax*2]
0x18001714e  lea     r10, [r10+rcx*4]
0x180017152  cmp     rdx, r10
0x180017155  jz      short loc_18001717D
0x180017157  mov     eax, [r8]
0x18001715a  cmp     [rdx], eax
0x18001715c  jnz     short loc_180017169
0x18001715e  movzx   eax, word ptr [r8+4]
0x180017163  cmp     [rdx+4], ax
0x180017167  jz      short loc_18001716F
0x180017169  add     rdx, 0Ch
0x18001716d  jmp     short loc_180017152
0x18001716f  mov     eax, [r8+8]
0x180017173  add     [rdx+8], eax
0x180017176  mov     r9d, [rsp+1090h+var_1050]
0x18001717b  jmp     short loc_1800171AA
0x18001717d  mov     eax, r9d
0x180017180  add     rax, 0Ch
0x180017184  cmp     rax, 1000h
0x18001718a  ja      short loc_1800171AA
0x18001718c  movsd   xmm0, qword ptr [r8]
0x180017191  add     r9d, 0Ch
0x180017195  movsd   qword ptr [r10], xmm0
0x18001719a  inc     r11d
0x18001719d  mov     eax, [r8+8]
0x1800171a1  mov     [r10+8], eax
0x1800171a5  mov     [rsp+1090h+var_1050], r9d
0x1800171aa  add     r8, 0Ch
0x1800171ae  lea     rdx, [rsp+1090h+var_1040]
0x1800171b3  cmp     r8, rdi
0x1800171b6  jnz     short loc_180017142
0x1800171b8  mov     eax, [rsp+1090h+var_104C]
0x1800171bc  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800171c3  mov     [rsp+1090h+var_1060], 1
0x1800171cb  mov     r8d, r9d
0x1800171ce  mov     dword ptr [rsp+1090h+var_1068], eax
0x1800171d2  call    wil_details_NtUpdateWnfStateData
0x1800171d7  mov     edi, eax
0x1800171d9  cmp     edi, 0C0000001h
0x1800171df  jnz     short loc_1800171F0
0x1800171e1  inc     esi
0x1800171e3  cmp     esi, 64h ; 'd'
0x1800171e6  jge     short loc_1800171F0
0x1800171e8  test    ebx, ebx
0x1800171ea  jz      loc_18001709F
0x1800171f0  test    ebx, ebx
0x1800171f2  cmovz   ebx, edi
0x1800171f5  mov     eax, ebx
0x1800171f7  mov     rcx, [rbp+0F90h+var_40]
0x1800171fe  xor     rcx, rsp; StackCookie
0x180017201  call    __security_check_cookie
0x180017206  add     rsp, 1068h
0x18001720d  pop     r14
0x18001720f  pop     r12
0x180017211  pop     rdi
0x180017212  pop     rsi
0x180017213  pop     rbx
0x180017214  pop     rbp
0x180017215  retn
```
