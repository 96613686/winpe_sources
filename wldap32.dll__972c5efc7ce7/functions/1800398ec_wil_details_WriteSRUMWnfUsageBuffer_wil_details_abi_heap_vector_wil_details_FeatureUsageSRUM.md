# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800398ec`
- end: `0x180039ab7`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800356e0`

## callees

- `0x180034510`
- `0x180034e6c`
- `0x1800398ec`
- `0x180039bc8`
- `0x180039c40`
- `0x18004c700`

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
0x1800398ec  push    rbp
0x1800398ee  push    rbx
0x1800398ef  push    rsi
0x1800398f0  push    rdi
0x1800398f1  push    r12
0x1800398f3  push    r14
0x1800398f5  lea     rbp, [rsp-0F68h]
0x1800398fd  mov     eax, 1068h
0x180039902  call    _alloca_probe
0x180039907  sub     rsp, rax
0x18003990a  mov     rax, cs:__security_cookie
0x180039911  xor     rax, rsp
0x180039914  mov     [rbp+0F90h+var_40], rax
0x18003991b  mov     rax, [rcx+8]
0x18003991f  xor     ebx, ebx
0x180039921  sub     rax, [rcx]
0x180039924  xor     edi, edi
0x180039926  mov     r14, rcx
0x180039929  cmp     rax, 0Ch
0x18003992d  jb      loc_180039A90
0x180039933  xor     esi, esi
0x180039935  mov     r12, 0AAAAAAAAAAAAAAABh
0x18003993f  xor     edx, edx; Val
0x180039941  lea     rcx, [rsp+1090h+var_1040]; void *
0x180039946  mov     r8d, 1000h; Size
0x18003994c  call    memset_0
0x180039951  lea     rax, [rsp+1090h+var_1050]
0x180039956  mov     [rsp+1090h+var_1050], 1000h
0x18003995e  mov     [rsp+1090h+var_1068], rax
0x180039963  lea     r9, [rsp+1090h+var_104C]
0x180039968  lea     rax, [rsp+1090h+var_1040]
0x18003996d  mov     [rsp+1090h+var_104C], 0
0x180039975  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18003997c  mov     [rsp+1090h+var_1070], rax
0x180039981  call    wil_details_NtQueryWnfStateData
0x180039986  mov     ebx, eax
0x180039988  test    eax, eax
0x18003998a  jnz     loc_180039A79
0x180039990  mov     r9d, [rsp+1090h+var_1050]
0x180039995  mov     rax, r12
0x180039998  mul     r9
0x18003999b  shr     rdx, 3
0x18003999f  lea     rcx, [rdx+rdx*2]
0x1800399a3  shl     rcx, 2
0x1800399a7  cmp     r9, rcx
0x1800399aa  jz      short loc_1800399B4
0x1800399ac  xor     r9d, r9d
0x1800399af  mov     [rsp+1090h+var_1050], r9d
0x1800399b4  mov     r8, [r14]
0x1800399b7  mov     rax, r12
0x1800399ba  mov     ecx, r9d
0x1800399bd  mul     rcx
0x1800399c0  mov     rcx, [r14+8]
0x1800399c4  mov     rax, r12
0x1800399c7  mov     r11, rdx
0x1800399ca  sub     rcx, r8
0x1800399cd  mul     rcx
0x1800399d0  shr     r11, 3
0x1800399d4  shr     rdx, 3
0x1800399d8  lea     rax, [rdx+rdx*2]
0x1800399dc  lea     rdi, [r8+rax*4]
0x1800399e0  jmp     short loc_180039A4E
0x1800399e2  mov     eax, r11d
0x1800399e5  lea     r10, [rsp+1090h+var_1040]
0x1800399ea  lea     rcx, [rax+rax*2]
0x1800399ee  lea     r10, [r10+rcx*4]
0x1800399f2  cmp     rdx, r10
0x1800399f5  jz      short loc_180039A1D
0x1800399f7  mov     eax, [r8]
0x1800399fa  cmp     [rdx], eax
0x1800399fc  jnz     short loc_180039A09
0x1800399fe  movzx   eax, word ptr [r8+4]
0x180039a03  cmp     [rdx+4], ax
0x180039a07  jz      short loc_180039A0F
0x180039a09  add     rdx, 0Ch
0x180039a0d  jmp     short loc_1800399F2
0x180039a0f  mov     eax, [r8+8]
0x180039a13  add     [rdx+8], eax
0x180039a16  mov     r9d, [rsp+1090h+var_1050]
0x180039a1b  jmp     short loc_180039A4A
0x180039a1d  mov     eax, r9d
0x180039a20  add     rax, 0Ch
0x180039a24  cmp     rax, 1000h
0x180039a2a  ja      short loc_180039A4A
0x180039a2c  movsd   xmm0, qword ptr [r8]
0x180039a31  add     r9d, 0Ch
0x180039a35  movsd   qword ptr [r10], xmm0
0x180039a3a  inc     r11d
0x180039a3d  mov     eax, [r8+8]
0x180039a41  mov     [r10+8], eax
0x180039a45  mov     [rsp+1090h+var_1050], r9d
0x180039a4a  add     r8, 0Ch
0x180039a4e  lea     rdx, [rsp+1090h+var_1040]
0x180039a53  cmp     r8, rdi
0x180039a56  jnz     short loc_1800399E2
0x180039a58  mov     eax, [rsp+1090h+var_104C]
0x180039a5c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180039a63  mov     [rsp+1090h+var_1060], 1
0x180039a6b  mov     r8d, r9d
0x180039a6e  mov     dword ptr [rsp+1090h+var_1068], eax
0x180039a72  call    wil_details_NtUpdateWnfStateData
0x180039a77  mov     edi, eax
0x180039a79  cmp     edi, 0C0000001h
0x180039a7f  jnz     short loc_180039A90
0x180039a81  inc     esi
0x180039a83  cmp     esi, 64h ; 'd'
0x180039a86  jge     short loc_180039A90
0x180039a88  test    ebx, ebx
0x180039a8a  jz      loc_18003993F
0x180039a90  test    ebx, ebx
0x180039a92  cmovz   ebx, edi
0x180039a95  mov     eax, ebx
0x180039a97  mov     rcx, [rbp+0F90h+var_40]
0x180039a9e  xor     rcx, rsp; StackCookie
0x180039aa1  call    __security_check_cookie
0x180039aa6  add     rsp, 1068h
0x180039aad  pop     r14
0x180039aaf  pop     r12
0x180039ab1  pop     rdi
0x180039ab2  pop     rsi
0x180039ab3  pop     rbx
0x180039ab4  pop     rbp
0x180039ab5  retn
```
