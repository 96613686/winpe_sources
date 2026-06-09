# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18001fa28`
- end: `0x18001fbf2`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001d9d0`

## callees

- `0x180012ec4`
- `0x18001fa28`
- `0x18001fd10`
- `0x18002205f`
- `0x180022190`
- `0x180022220`

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
0x18001fa28  push    rbp
0x18001fa2a  push    rbx
0x18001fa2b  push    rsi
0x18001fa2c  push    rdi
0x18001fa2d  push    r12
0x18001fa2f  push    r14
0x18001fa31  lea     rbp, [rsp-0F68h]
0x18001fa39  mov     eax, 1068h
0x18001fa3e  call    _alloca_probe
0x18001fa43  sub     rsp, rax
0x18001fa46  mov     rax, cs:__security_cookie
0x18001fa4d  xor     rax, rsp
0x18001fa50  mov     [rbp+0F90h+var_40], rax
0x18001fa57  mov     rax, [rcx+8]
0x18001fa5b  xor     ebx, ebx
0x18001fa5d  sub     rax, [rcx]
0x18001fa60  xor     edi, edi
0x18001fa62  mov     r14, rcx
0x18001fa65  cmp     rax, 0Ch
0x18001fa69  jb      loc_18001FBCC
0x18001fa6f  xor     esi, esi
0x18001fa71  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001fa7b  xor     edx, edx; Val
0x18001fa7d  lea     rcx, [rsp+1090h+var_1040]; void *
0x18001fa82  mov     r8d, 1000h; Size
0x18001fa88  call    memset_0
0x18001fa8d  lea     rax, [rsp+1090h+var_1050]
0x18001fa92  mov     [rsp+1090h+var_1050], 1000h
0x18001fa9a  mov     [rsp+1090h+var_1068], rax
0x18001fa9f  lea     r9, [rsp+1090h+var_104C]
0x18001faa4  lea     rax, [rsp+1090h+var_1040]
0x18001faa9  mov     [rsp+1090h+var_104C], 0
0x18001fab1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001fab8  mov     [rsp+1090h+var_1070], rax
0x18001fabd  call    wil_details_NtQueryWnfStateData
0x18001fac2  mov     ebx, eax
0x18001fac4  test    eax, eax
0x18001fac6  jnz     loc_18001FBB5
0x18001facc  mov     r9d, [rsp+1090h+var_1050]
0x18001fad1  mov     rax, r12
0x18001fad4  mul     r9
0x18001fad7  shr     rdx, 3
0x18001fadb  lea     rcx, [rdx+rdx*2]
0x18001fadf  shl     rcx, 2
0x18001fae3  cmp     r9, rcx
0x18001fae6  jz      short loc_18001FAF0
0x18001fae8  xor     r9d, r9d
0x18001faeb  mov     [rsp+1090h+var_1050], r9d
0x18001faf0  mov     r8, [r14]
0x18001faf3  mov     rax, r12
0x18001faf6  mov     ecx, r9d
0x18001faf9  mul     rcx
0x18001fafc  mov     rcx, [r14+8]
0x18001fb00  mov     rax, r12
0x18001fb03  mov     r11, rdx
0x18001fb06  sub     rcx, r8
0x18001fb09  mul     rcx
0x18001fb0c  shr     r11, 3
0x18001fb10  shr     rdx, 3
0x18001fb14  lea     rax, [rdx+rdx*2]
0x18001fb18  lea     rdi, [r8+rax*4]
0x18001fb1c  jmp     short loc_18001FB8A
0x18001fb1e  mov     eax, r11d
0x18001fb21  lea     r10, [rsp+1090h+var_1040]
0x18001fb26  lea     rcx, [rax+rax*2]
0x18001fb2a  lea     r10, [r10+rcx*4]
0x18001fb2e  cmp     rdx, r10
0x18001fb31  jz      short loc_18001FB59
0x18001fb33  mov     eax, [r8]
0x18001fb36  cmp     [rdx], eax
0x18001fb38  jnz     short loc_18001FB45
0x18001fb3a  movzx   eax, word ptr [r8+4]
0x18001fb3f  cmp     [rdx+4], ax
0x18001fb43  jz      short loc_18001FB4B
0x18001fb45  add     rdx, 0Ch
0x18001fb49  jmp     short loc_18001FB2E
0x18001fb4b  mov     eax, [r8+8]
0x18001fb4f  add     [rdx+8], eax
0x18001fb52  mov     r9d, [rsp+1090h+var_1050]
0x18001fb57  jmp     short loc_18001FB86
0x18001fb59  mov     eax, r9d
0x18001fb5c  add     rax, 0Ch
0x18001fb60  cmp     rax, 1000h
0x18001fb66  ja      short loc_18001FB86
0x18001fb68  movsd   xmm0, qword ptr [r8]
0x18001fb6d  add     r9d, 0Ch
0x18001fb71  movsd   qword ptr [r10], xmm0
0x18001fb76  inc     r11d
0x18001fb79  mov     eax, [r8+8]
0x18001fb7d  mov     [r10+8], eax
0x18001fb81  mov     [rsp+1090h+var_1050], r9d
0x18001fb86  add     r8, 0Ch
0x18001fb8a  lea     rdx, [rsp+1090h+var_1040]
0x18001fb8f  cmp     r8, rdi
0x18001fb92  jnz     short loc_18001FB1E
0x18001fb94  mov     eax, [rsp+1090h+var_104C]
0x18001fb98  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001fb9f  mov     [rsp+1090h+var_1060], 1
0x18001fba7  mov     r8d, r9d
0x18001fbaa  mov     dword ptr [rsp+1090h+var_1068], eax
0x18001fbae  call    wil_details_NtUpdateWnfStateData
0x18001fbb3  mov     edi, eax
0x18001fbb5  cmp     edi, 0C0000001h
0x18001fbbb  jnz     short loc_18001FBCC
0x18001fbbd  inc     esi
0x18001fbbf  cmp     esi, 64h ; 'd'
0x18001fbc2  jge     short loc_18001FBCC
0x18001fbc4  test    ebx, ebx
0x18001fbc6  jz      loc_18001FA7B
0x18001fbcc  test    ebx, ebx
0x18001fbce  cmovz   ebx, edi
0x18001fbd1  mov     eax, ebx
0x18001fbd3  mov     rcx, [rbp+0F90h+var_40]
0x18001fbda  xor     rcx, rsp; StackCookie
0x18001fbdd  call    __security_check_cookie
0x18001fbe2  add     rsp, 1068h
0x18001fbe9  pop     r14
0x18001fbeb  pop     r12
0x18001fbed  pop     rdi
0x18001fbee  pop     rsi
0x18001fbef  pop     rbx
0x18001fbf0  pop     rbp
0x18001fbf1  retn
```
