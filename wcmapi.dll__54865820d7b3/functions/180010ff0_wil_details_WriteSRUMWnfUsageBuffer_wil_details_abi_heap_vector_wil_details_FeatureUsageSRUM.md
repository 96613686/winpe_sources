# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180010ff0`
- end: `0x1800111c6`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000b1c0`

## callees

- `0x180008a90`
- `0x18000953c`
- `0x180010ff0`
- `0x180014480`
- `0x1800144f8`
- `0x18001c800`

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
0x180010ff0  push    rbp
0x180010ff2  push    rbx
0x180010ff3  push    rsi
0x180010ff4  push    rdi
0x180010ff5  push    r12
0x180010ff7  push    r14
0x180010ff9  lea     rbp, [rsp-0F68h]
0x180011001  mov     eax, 1068h
0x180011006  call    _alloca_probe
0x18001100b  sub     rsp, rax
0x18001100e  mov     rax, cs:__security_cookie
0x180011015  xor     rax, rsp
0x180011018  mov     [rbp+0F90h+var_40], rax
0x18001101f  mov     rax, [rcx+8]
0x180011023  xor     ebx, ebx
0x180011025  sub     rax, [rcx]
0x180011028  xor     edi, edi
0x18001102a  mov     r14, rcx
0x18001102d  cmp     rax, 0Ch
0x180011031  jb      loc_180011191
0x180011037  xor     esi, esi
0x180011039  mov     r12, 0AAAAAAAAAAAAAAABh
0x180011043  xor     edx, edx; Val
0x180011045  lea     rcx, [rsp+1090h+var_1040]; void *
0x18001104a  mov     r8d, 1000h; Size
0x180011050  call    memset_0
0x180011055  lea     rax, [rsp+1090h+var_1050]
0x18001105a  mov     [rsp+1090h+var_1050], 1000h
0x180011062  mov     [rsp+1090h+var_1068], rax
0x180011067  lea     r9, [rsp+1090h+var_104C]
0x18001106c  lea     rax, [rsp+1090h+var_1040]
0x180011071  mov     [rsp+1090h+var_104C], 0
0x180011079  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180011080  mov     [rsp+1090h+var_1070], rax
0x180011085  call    wil_details_NtQueryWnfStateData
0x18001108a  mov     ebx, eax
0x18001108c  test    eax, eax
0x18001108e  jnz     loc_18001117A
0x180011094  mov     r9d, [rsp+1090h+var_1050]
0x180011099  mov     rax, r12
0x18001109c  mul     r9
0x18001109f  shr     rdx, 3
0x1800110a3  lea     rcx, [rdx+rdx*2]
0x1800110a7  shl     rcx, 2
0x1800110ab  cmp     r9, rcx
0x1800110ae  jz      short loc_1800110B8
0x1800110b0  xor     r9d, r9d
0x1800110b3  mov     [rsp+1090h+var_1050], r9d
0x1800110b8  mov     r8, [r14]
0x1800110bb  mov     rax, r12
0x1800110be  mov     ecx, r9d
0x1800110c1  mul     rcx
0x1800110c4  mov     rcx, [r14+8]
0x1800110c8  mov     rax, r12
0x1800110cb  mov     r10, rdx
0x1800110ce  sub     rcx, r8
0x1800110d1  mul     rcx
0x1800110d4  shr     r10, 3
0x1800110d8  shr     rdx, 3
0x1800110dc  lea     rax, [rdx+rdx*2]
0x1800110e0  lea     rdi, [r8+rax*4]
0x1800110e4  jmp     short loc_18001114F
0x1800110e6  mov     eax, r10d
0x1800110e9  lea     rcx, [rax+rax*2]
0x1800110ed  lea     rdx, [rdx+rcx*4]
0x1800110f1  lea     rax, [rsp+1090h+var_1040]
0x1800110f6  cmp     rax, rdx
0x1800110f9  jz      short loc_180011120
0x1800110fb  mov     r11d, [r8]
0x1800110fe  lea     rcx, [rsp+1090h+var_1040]
0x180011103  cmp     [rcx], r11d
0x180011106  jnz     short loc_180011117
0x180011108  movzx   eax, word ptr [r8+4]
0x18001110d  cmp     [rcx+4], ax
0x180011111  jz      loc_1800111B8
0x180011117  add     rcx, 0Ch
0x18001111b  cmp     rcx, rdx
0x18001111e  jnz     short loc_180011103
0x180011120  mov     eax, r9d
0x180011123  add     rax, 0Ch
0x180011127  cmp     rax, 1000h
0x18001112d  ja      short loc_18001114B
0x18001112f  movsd   xmm0, qword ptr [r8]
0x180011134  add     r9d, 0Ch
0x180011138  movsd   qword ptr [rdx], xmm0
0x18001113c  inc     r10d
0x18001113f  mov     eax, [r8+8]
0x180011143  mov     [rdx+8], eax
0x180011146  mov     [rsp+1090h+var_1050], r9d
0x18001114b  add     r8, 0Ch
0x18001114f  lea     rdx, [rsp+1090h+var_1040]
0x180011154  cmp     r8, rdi
0x180011157  jnz     short loc_1800110E6
0x180011159  mov     eax, [rsp+1090h+var_104C]
0x18001115d  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180011164  mov     [rsp+1090h+var_1060], 1
0x18001116c  mov     r8d, r9d
0x18001116f  mov     dword ptr [rsp+1090h+var_1068], eax
0x180011173  call    wil_details_NtUpdateWnfStateData
0x180011178  mov     edi, eax
0x18001117a  cmp     edi, 0C0000001h
0x180011180  jnz     short loc_180011191
0x180011182  inc     esi
0x180011184  cmp     esi, 64h ; 'd'
0x180011187  jge     short loc_180011191
0x180011189  test    ebx, ebx
0x18001118b  jz      loc_180011043
0x180011191  test    ebx, ebx
0x180011193  cmovz   ebx, edi
0x180011196  mov     eax, ebx
0x180011198  mov     rcx, [rbp+0F90h+var_40]
0x18001119f  xor     rcx, rsp; StackCookie
0x1800111a2  call    __security_check_cookie
0x1800111a7  add     rsp, 1068h
0x1800111ae  pop     r14
0x1800111b0  pop     r12
0x1800111b2  pop     rdi
0x1800111b3  pop     rsi
0x1800111b4  pop     rbx
0x1800111b5  pop     rbp
0x1800111b6  retn
0x1800111b8  mov     eax, [r8+8]
0x1800111bc  add     [rcx+8], eax
0x1800111bf  mov     r9d, [rsp+1090h+var_1050]
0x1800111c4  jmp     short loc_18001114B
```
