# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180019c10`
- end: `0x180019dda`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180015f60`

## callees

- `0x18000ad88`
- `0x18000c990`
- `0x18000d470`
- `0x180019c10`
- `0x18001a37c`
- `0x18001a7f9`

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
0x180019c10  push    rbp
0x180019c12  push    rbx
0x180019c13  push    rsi
0x180019c14  push    rdi
0x180019c15  push    r12
0x180019c17  push    r14
0x180019c19  lea     rbp, [rsp-0F68h]
0x180019c21  mov     eax, 1068h
0x180019c26  call    __chkstk_0
0x180019c2b  sub     rsp, rax
0x180019c2e  mov     rax, cs:__security_cookie
0x180019c35  xor     rax, rsp
0x180019c38  mov     [rbp+0F90h+var_40], rax
0x180019c3f  mov     rax, [rcx+8]
0x180019c43  xor     ebx, ebx
0x180019c45  sub     rax, [rcx]
0x180019c48  xor     edi, edi
0x180019c4a  mov     r14, rcx
0x180019c4d  cmp     rax, 0Ch
0x180019c51  jb      loc_180019DB4
0x180019c57  xor     esi, esi
0x180019c59  mov     r12, 0AAAAAAAAAAAAAAABh
0x180019c63  xor     edx, edx; Val
0x180019c65  lea     rcx, [rsp+1090h+var_1040]; void *
0x180019c6a  mov     r8d, 1000h; Size
0x180019c70  call    memset_0
0x180019c75  lea     rax, [rsp+1090h+var_1050]
0x180019c7a  mov     [rsp+1090h+var_1050], 1000h
0x180019c82  mov     [rsp+1090h+var_1068], rax
0x180019c87  lea     r9, [rsp+1090h+var_104C]
0x180019c8c  lea     rax, [rsp+1090h+var_1040]
0x180019c91  mov     [rsp+1090h+var_104C], 0
0x180019c99  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180019ca0  mov     [rsp+1090h+var_1070], rax
0x180019ca5  call    wil_details_NtQueryWnfStateData
0x180019caa  mov     ebx, eax
0x180019cac  test    eax, eax
0x180019cae  jnz     loc_180019D9D
0x180019cb4  mov     r9d, [rsp+1090h+var_1050]
0x180019cb9  mov     rax, r12
0x180019cbc  mul     r9
0x180019cbf  shr     rdx, 3
0x180019cc3  lea     rcx, [rdx+rdx*2]
0x180019cc7  shl     rcx, 2
0x180019ccb  cmp     r9, rcx
0x180019cce  jz      short loc_180019CD8
0x180019cd0  xor     r9d, r9d
0x180019cd3  mov     [rsp+1090h+var_1050], r9d
0x180019cd8  mov     r8, [r14]
0x180019cdb  mov     rax, r12
0x180019cde  mov     ecx, r9d
0x180019ce1  mul     rcx
0x180019ce4  mov     rcx, [r14+8]
0x180019ce8  mov     rax, r12
0x180019ceb  mov     r11, rdx
0x180019cee  sub     rcx, r8
0x180019cf1  mul     rcx
0x180019cf4  shr     r11, 3
0x180019cf8  shr     rdx, 3
0x180019cfc  lea     rax, [rdx+rdx*2]
0x180019d00  lea     rdi, [r8+rax*4]
0x180019d04  jmp     short loc_180019D72
0x180019d06  mov     eax, r11d
0x180019d09  lea     r10, [rsp+1090h+var_1040]
0x180019d0e  lea     rcx, [rax+rax*2]
0x180019d12  lea     r10, [r10+rcx*4]
0x180019d16  cmp     rdx, r10
0x180019d19  jz      short loc_180019D41
0x180019d1b  mov     eax, [r8]
0x180019d1e  cmp     [rdx], eax
0x180019d20  jnz     short loc_180019D2D
0x180019d22  movzx   eax, word ptr [r8+4]
0x180019d27  cmp     [rdx+4], ax
0x180019d2b  jz      short loc_180019D33
0x180019d2d  add     rdx, 0Ch
0x180019d31  jmp     short loc_180019D16
0x180019d33  mov     eax, [r8+8]
0x180019d37  add     [rdx+8], eax
0x180019d3a  mov     r9d, [rsp+1090h+var_1050]
0x180019d3f  jmp     short loc_180019D6E
0x180019d41  mov     eax, r9d
0x180019d44  add     rax, 0Ch
0x180019d48  cmp     rax, 1000h
0x180019d4e  ja      short loc_180019D6E
0x180019d50  movsd   xmm0, qword ptr [r8]
0x180019d55  add     r9d, 0Ch
0x180019d59  movsd   qword ptr [r10], xmm0
0x180019d5e  inc     r11d
0x180019d61  mov     eax, [r8+8]
0x180019d65  mov     [r10+8], eax
0x180019d69  mov     [rsp+1090h+var_1050], r9d
0x180019d6e  add     r8, 0Ch
0x180019d72  lea     rdx, [rsp+1090h+var_1040]
0x180019d77  cmp     r8, rdi
0x180019d7a  jnz     short loc_180019D06
0x180019d7c  mov     eax, [rsp+1090h+var_104C]
0x180019d80  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180019d87  mov     [rsp+1090h+var_1060], 1
0x180019d8f  mov     r8d, r9d
0x180019d92  mov     dword ptr [rsp+1090h+var_1068], eax
0x180019d96  call    wil_details_NtUpdateWnfStateData
0x180019d9b  mov     edi, eax
0x180019d9d  cmp     edi, 0C0000001h
0x180019da3  jnz     short loc_180019DB4
0x180019da5  inc     esi
0x180019da7  cmp     esi, 64h ; 'd'
0x180019daa  jge     short loc_180019DB4
0x180019dac  test    ebx, ebx
0x180019dae  jz      loc_180019C63
0x180019db4  test    ebx, ebx
0x180019db6  cmovz   ebx, edi
0x180019db9  mov     eax, ebx
0x180019dbb  mov     rcx, [rbp+0F90h+var_40]
0x180019dc2  xor     rcx, rsp; StackCookie
0x180019dc5  call    __security_check_cookie
0x180019dca  add     rsp, 1068h
0x180019dd1  pop     r14
0x180019dd3  pop     r12
0x180019dd5  pop     rdi
0x180019dd6  pop     rsi
0x180019dd7  pop     rbx
0x180019dd8  pop     rbp
0x180019dd9  retn
```
