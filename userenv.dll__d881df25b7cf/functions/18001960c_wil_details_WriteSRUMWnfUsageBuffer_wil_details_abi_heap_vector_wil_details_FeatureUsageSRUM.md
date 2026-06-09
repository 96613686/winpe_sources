# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18001960c`
- end: `0x1800197e2`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180015880`

## callees

- `0x18000e640`
- `0x18000efe0`
- `0x18001960c`
- `0x18001a11c`
- `0x18001a194`
- `0x18001c7a0`

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
0x18001960c  push    rbp
0x18001960e  push    rbx
0x18001960f  push    rsi
0x180019610  push    rdi
0x180019611  push    r12
0x180019613  push    r14
0x180019615  lea     rbp, [rsp-0F68h]
0x18001961d  mov     eax, 1068h
0x180019622  call    _alloca_probe
0x180019627  sub     rsp, rax
0x18001962a  mov     rax, cs:__security_cookie
0x180019631  xor     rax, rsp
0x180019634  mov     [rbp+0F90h+var_40], rax
0x18001963b  mov     rax, [rcx+8]
0x18001963f  xor     ebx, ebx
0x180019641  sub     rax, [rcx]
0x180019644  xor     edi, edi
0x180019646  mov     r14, rcx
0x180019649  cmp     rax, 0Ch
0x18001964d  jb      loc_1800197AD
0x180019653  xor     esi, esi
0x180019655  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001965f  xor     edx, edx; Val
0x180019661  lea     rcx, [rsp+1090h+var_1040]; void *
0x180019666  mov     r8d, 1000h; Size
0x18001966c  call    memset_0
0x180019671  lea     rax, [rsp+1090h+var_1050]
0x180019676  mov     [rsp+1090h+var_1050], 1000h
0x18001967e  mov     [rsp+1090h+var_1068], rax
0x180019683  lea     r9, [rsp+1090h+var_104C]
0x180019688  lea     rax, [rsp+1090h+var_1040]
0x18001968d  mov     [rsp+1090h+var_104C], 0
0x180019695  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001969c  mov     [rsp+1090h+var_1070], rax
0x1800196a1  call    wil_details_NtQueryWnfStateData
0x1800196a6  mov     ebx, eax
0x1800196a8  test    eax, eax
0x1800196aa  jnz     loc_180019796
0x1800196b0  mov     r9d, [rsp+1090h+var_1050]
0x1800196b5  mov     rax, r12
0x1800196b8  mul     r9
0x1800196bb  shr     rdx, 3
0x1800196bf  lea     rcx, [rdx+rdx*2]
0x1800196c3  shl     rcx, 2
0x1800196c7  cmp     r9, rcx
0x1800196ca  jz      short loc_1800196D4
0x1800196cc  xor     r9d, r9d
0x1800196cf  mov     [rsp+1090h+var_1050], r9d
0x1800196d4  mov     r8, [r14]
0x1800196d7  mov     rax, r12
0x1800196da  mov     ecx, r9d
0x1800196dd  mul     rcx
0x1800196e0  mov     rcx, [r14+8]
0x1800196e4  mov     rax, r12
0x1800196e7  mov     r10, rdx
0x1800196ea  sub     rcx, r8
0x1800196ed  mul     rcx
0x1800196f0  shr     r10, 3
0x1800196f4  shr     rdx, 3
0x1800196f8  lea     rax, [rdx+rdx*2]
0x1800196fc  lea     rdi, [r8+rax*4]
0x180019700  jmp     short loc_18001976B
0x180019702  mov     eax, r10d
0x180019705  lea     rcx, [rax+rax*2]
0x180019709  lea     rdx, [rdx+rcx*4]
0x18001970d  lea     rax, [rsp+1090h+var_1040]
0x180019712  cmp     rax, rdx
0x180019715  jz      short loc_18001973C
0x180019717  mov     r11d, [r8]
0x18001971a  lea     rcx, [rsp+1090h+var_1040]
0x18001971f  cmp     [rcx], r11d
0x180019722  jnz     short loc_180019733
0x180019724  movzx   eax, word ptr [r8+4]
0x180019729  cmp     [rcx+4], ax
0x18001972d  jz      loc_1800197D4
0x180019733  add     rcx, 0Ch
0x180019737  cmp     rcx, rdx
0x18001973a  jnz     short loc_18001971F
0x18001973c  mov     eax, r9d
0x18001973f  add     rax, 0Ch
0x180019743  cmp     rax, 1000h
0x180019749  ja      short loc_180019767
0x18001974b  movsd   xmm0, qword ptr [r8]
0x180019750  add     r9d, 0Ch
0x180019754  movsd   qword ptr [rdx], xmm0
0x180019758  inc     r10d
0x18001975b  mov     eax, [r8+8]
0x18001975f  mov     [rdx+8], eax
0x180019762  mov     [rsp+1090h+var_1050], r9d
0x180019767  add     r8, 0Ch
0x18001976b  lea     rdx, [rsp+1090h+var_1040]
0x180019770  cmp     r8, rdi
0x180019773  jnz     short loc_180019702
0x180019775  mov     eax, [rsp+1090h+var_104C]
0x180019779  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180019780  mov     [rsp+1090h+var_1060], 1
0x180019788  mov     r8d, r9d
0x18001978b  mov     dword ptr [rsp+1090h+var_1068], eax
0x18001978f  call    wil_details_NtUpdateWnfStateData
0x180019794  mov     edi, eax
0x180019796  cmp     edi, 0C0000001h
0x18001979c  jnz     short loc_1800197AD
0x18001979e  inc     esi
0x1800197a0  cmp     esi, 64h ; 'd'
0x1800197a3  jge     short loc_1800197AD
0x1800197a5  test    ebx, ebx
0x1800197a7  jz      loc_18001965F
0x1800197ad  test    ebx, ebx
0x1800197af  cmovz   ebx, edi
0x1800197b2  mov     eax, ebx
0x1800197b4  mov     rcx, [rbp+0F90h+var_40]
0x1800197bb  xor     rcx, rsp; StackCookie
0x1800197be  call    __security_check_cookie
0x1800197c3  add     rsp, 1068h
0x1800197ca  pop     r14
0x1800197cc  pop     r12
0x1800197ce  pop     rdi
0x1800197cf  pop     rsi
0x1800197d0  pop     rbx
0x1800197d1  pop     rbp
0x1800197d2  retn
0x1800197d4  mov     eax, [r8+8]
0x1800197d8  add     [rcx+8], eax
0x1800197db  mov     r9d, [rsp+1090h+var_1050]
0x1800197e0  jmp     short loc_180019767
```
