# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000a144`
- end: `0x14000a30f`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400035f0`

## callees

- `0x140002480`
- `0x140002fa0`
- `0x14000a144`
- `0x14000a640`
- `0x14000a6b8`
- `0x1400269f0`

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
0x14000a144  push    rbp
0x14000a146  push    rbx
0x14000a147  push    rsi
0x14000a148  push    rdi
0x14000a149  push    r12
0x14000a14b  push    r14
0x14000a14d  lea     rbp, [rsp-0F68h]
0x14000a155  mov     eax, 1068h
0x14000a15a  call    _alloca_probe
0x14000a15f  sub     rsp, rax
0x14000a162  mov     rax, cs:__security_cookie
0x14000a169  xor     rax, rsp
0x14000a16c  mov     [rbp+0F90h+var_40], rax
0x14000a173  mov     rax, [rcx+8]
0x14000a177  xor     ebx, ebx
0x14000a179  sub     rax, [rcx]
0x14000a17c  xor     edi, edi
0x14000a17e  mov     r14, rcx
0x14000a181  cmp     rax, 0Ch
0x14000a185  jb      loc_14000A2E8
0x14000a18b  xor     esi, esi
0x14000a18d  mov     r12, 0AAAAAAAAAAAAAAABh
0x14000a197  xor     edx, edx; Val
0x14000a199  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000a19e  mov     r8d, 1000h; Size
0x14000a1a4  call    memset_0
0x14000a1a9  lea     rax, [rsp+1090h+var_1050]
0x14000a1ae  mov     [rsp+1090h+var_1050], 1000h
0x14000a1b6  mov     [rsp+1090h+var_1068], rax
0x14000a1bb  lea     r9, [rsp+1090h+var_104C]
0x14000a1c0  lea     rax, [rsp+1090h+var_1040]
0x14000a1c5  mov     [rsp+1090h+var_104C], 0
0x14000a1cd  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000a1d4  mov     [rsp+1090h+var_1070], rax
0x14000a1d9  call    wil_details_NtQueryWnfStateData
0x14000a1de  mov     ebx, eax
0x14000a1e0  test    eax, eax
0x14000a1e2  jnz     loc_14000A2D1
0x14000a1e8  mov     r9d, [rsp+1090h+var_1050]
0x14000a1ed  mov     rax, r12
0x14000a1f0  mul     r9
0x14000a1f3  shr     rdx, 3
0x14000a1f7  lea     rcx, [rdx+rdx*2]
0x14000a1fb  shl     rcx, 2
0x14000a1ff  cmp     r9, rcx
0x14000a202  jz      short loc_14000A20C
0x14000a204  xor     r9d, r9d
0x14000a207  mov     [rsp+1090h+var_1050], r9d
0x14000a20c  mov     r8, [r14]
0x14000a20f  mov     rax, r12
0x14000a212  mov     ecx, r9d
0x14000a215  mul     rcx
0x14000a218  mov     rcx, [r14+8]
0x14000a21c  mov     rax, r12
0x14000a21f  mov     r11, rdx
0x14000a222  sub     rcx, r8
0x14000a225  mul     rcx
0x14000a228  shr     r11, 3
0x14000a22c  shr     rdx, 3
0x14000a230  lea     rax, [rdx+rdx*2]
0x14000a234  lea     rdi, [r8+rax*4]
0x14000a238  jmp     short loc_14000A2A6
0x14000a23a  mov     eax, r11d
0x14000a23d  lea     r10, [rsp+1090h+var_1040]
0x14000a242  lea     rcx, [rax+rax*2]
0x14000a246  lea     r10, [r10+rcx*4]
0x14000a24a  cmp     rdx, r10
0x14000a24d  jz      short loc_14000A275
0x14000a24f  mov     eax, [r8]
0x14000a252  cmp     [rdx], eax
0x14000a254  jnz     short loc_14000A261
0x14000a256  movzx   eax, word ptr [r8+4]
0x14000a25b  cmp     [rdx+4], ax
0x14000a25f  jz      short loc_14000A267
0x14000a261  add     rdx, 0Ch
0x14000a265  jmp     short loc_14000A24A
0x14000a267  mov     eax, [r8+8]
0x14000a26b  add     [rdx+8], eax
0x14000a26e  mov     r9d, [rsp+1090h+var_1050]
0x14000a273  jmp     short loc_14000A2A2
0x14000a275  mov     eax, r9d
0x14000a278  add     rax, 0Ch
0x14000a27c  cmp     rax, 1000h
0x14000a282  ja      short loc_14000A2A2
0x14000a284  movsd   xmm0, qword ptr [r8]
0x14000a289  add     r9d, 0Ch
0x14000a28d  movsd   qword ptr [r10], xmm0
0x14000a292  inc     r11d
0x14000a295  mov     eax, [r8+8]
0x14000a299  mov     [r10+8], eax
0x14000a29d  mov     [rsp+1090h+var_1050], r9d
0x14000a2a2  add     r8, 0Ch
0x14000a2a6  lea     rdx, [rsp+1090h+var_1040]
0x14000a2ab  cmp     r8, rdi
0x14000a2ae  jnz     short loc_14000A23A
0x14000a2b0  mov     eax, [rsp+1090h+var_104C]
0x14000a2b4  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000a2bb  mov     [rsp+1090h+var_1060], 1
0x14000a2c3  mov     r8d, r9d
0x14000a2c6  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000a2ca  call    wil_details_NtUpdateWnfStateData
0x14000a2cf  mov     edi, eax
0x14000a2d1  cmp     edi, 0C0000001h
0x14000a2d7  jnz     short loc_14000A2E8
0x14000a2d9  inc     esi
0x14000a2db  cmp     esi, 64h ; 'd'
0x14000a2de  jge     short loc_14000A2E8
0x14000a2e0  test    ebx, ebx
0x14000a2e2  jz      loc_14000A197
0x14000a2e8  test    ebx, ebx
0x14000a2ea  cmovz   ebx, edi
0x14000a2ed  mov     eax, ebx
0x14000a2ef  mov     rcx, [rbp+0F90h+var_40]
0x14000a2f6  xor     rcx, rsp; StackCookie
0x14000a2f9  call    __security_check_cookie
0x14000a2fe  add     rsp, 1068h
0x14000a305  pop     r14
0x14000a307  pop     r12
0x14000a309  pop     rdi
0x14000a30a  pop     rsi
0x14000a30b  pop     rbx
0x14000a30c  pop     rbp
0x14000a30d  retn
```
