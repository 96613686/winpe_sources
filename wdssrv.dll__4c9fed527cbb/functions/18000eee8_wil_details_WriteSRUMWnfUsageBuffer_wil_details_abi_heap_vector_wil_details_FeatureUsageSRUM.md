# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000eee8`
- end: `0x18000f0d5`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180006480`

## callees

- `0x18000eee8`
- `0x18000f83c`
- `0x18000f8e4`
- `0x18001c12a`
- `0x18001c150`
- `0x18001c210`

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
0x18000eee8  mov     rax, rsp
0x18000eeeb  mov     [rax+8], rbx
0x18000eeef  mov     [rax+10h], rsi
0x18000eef3  mov     [rax+18h], rdi
0x18000eef7  push    rbp
0x18000eef8  push    r12
0x18000eefa  push    r14
0x18000eefc  lea     rbp, [rax-0F78h]
0x18000ef03  mov     eax, 1060h
0x18000ef08  call    _alloca_probe
0x18000ef0d  sub     rsp, rax
0x18000ef10  mov     rax, cs:__security_cookie
0x18000ef17  xor     rax, rsp
0x18000ef1a  mov     [rbp+0F70h+var_20], rax
0x18000ef21  mov     rax, [rcx+8]
0x18000ef25  xor     ebx, ebx
0x18000ef27  sub     rax, [rcx]
0x18000ef2a  xor     edi, edi
0x18000ef2c  mov     r14, rcx
0x18000ef2f  cmp     rax, 0Ch
0x18000ef33  jb      loc_18000F090
0x18000ef39  xor     esi, esi
0x18000ef3b  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000ef45  xor     edx, edx; Val
0x18000ef47  lea     rcx, [rsp+1070h+var_1020]; void *
0x18000ef4c  mov     r8d, 1000h; Size
0x18000ef52  call    memset_0
0x18000ef57  and     [rsp+1070h+var_102C], 0
0x18000ef5c  lea     rax, [rsp+1070h+var_1030]
0x18000ef61  mov     qword ptr [rsp+1070h+var_1048], rax
0x18000ef66  lea     r9, [rsp+1070h+var_102C]
0x18000ef6b  lea     rax, [rsp+1070h+var_1020]
0x18000ef70  mov     [rsp+1070h+var_1030], 1000h
0x18000ef78  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000ef7f  mov     [rsp+1070h+var_1050], rax
0x18000ef84  call    wil_details_NtQueryWnfStateData
0x18000ef89  mov     ebx, eax
0x18000ef8b  test    eax, eax
0x18000ef8d  jnz     loc_18000F079
0x18000ef93  mov     r9d, [rsp+1070h+var_1030]
0x18000ef98  mov     rax, r12
0x18000ef9b  mul     r9
0x18000ef9e  shr     rdx, 3
0x18000efa2  lea     rcx, [rdx+rdx*2]
0x18000efa6  shl     rcx, 2
0x18000efaa  cmp     r9, rcx
0x18000efad  jz      short loc_18000EFB7
0x18000efaf  xor     r9d, r9d
0x18000efb2  mov     [rsp+1070h+var_1030], r9d
0x18000efb7  mov     r8, [r14]
0x18000efba  mov     rax, r12
0x18000efbd  mov     ecx, r9d
0x18000efc0  mul     rcx
0x18000efc3  mov     rcx, [r14+8]
0x18000efc7  mov     rax, r12
0x18000efca  mov     r10, rdx
0x18000efcd  sub     rcx, r8
0x18000efd0  mul     rcx
0x18000efd3  shr     r10, 3
0x18000efd7  shr     rdx, 3
0x18000efdb  lea     rax, [rdx+rdx*2]
0x18000efdf  lea     rdi, [r8+rax*4]
0x18000efe3  jmp     short loc_18000F04E
0x18000efe5  mov     eax, r10d
0x18000efe8  lea     rcx, [rax+rax*2]
0x18000efec  lea     rdx, [rdx+rcx*4]
0x18000eff0  lea     rax, [rsp+1070h+var_1020]
0x18000eff5  lea     rcx, [rsp+1070h+var_1020]
0x18000effa  cmp     rax, rdx
0x18000effd  jz      short loc_18000F01F
0x18000efff  mov     r11d, [r8]
0x18000f002  cmp     [rcx], r11d
0x18000f005  jnz     short loc_18000F016
0x18000f007  movzx   eax, word ptr [r8+4]
0x18000f00c  cmp     [rcx+4], ax
0x18000f010  jz      loc_18000F0C4
0x18000f016  add     rcx, 0Ch
0x18000f01a  cmp     rcx, rdx
0x18000f01d  jnz     short loc_18000F002
0x18000f01f  mov     eax, r9d
0x18000f022  add     rax, 0Ch
0x18000f026  cmp     rax, 1000h
0x18000f02c  ja      short loc_18000F04A
0x18000f02e  movsd   xmm0, qword ptr [r8]
0x18000f033  add     r9d, 0Ch
0x18000f037  movsd   qword ptr [rdx], xmm0
0x18000f03b  inc     r10d
0x18000f03e  mov     eax, [r8+8]
0x18000f042  mov     [rdx+8], eax
0x18000f045  mov     [rsp+1070h+var_1030], r9d
0x18000f04a  add     r8, 0Ch
0x18000f04e  lea     rdx, [rsp+1070h+var_1020]
0x18000f053  cmp     r8, rdi
0x18000f056  jnz     short loc_18000EFE5
0x18000f058  mov     eax, [rsp+1070h+var_102C]
0x18000f05c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000f063  mov     [rsp+1070h+var_1040], 1
0x18000f06b  mov     r8d, r9d
0x18000f06e  mov     [rsp+1070h+var_1048], eax
0x18000f072  call    wil_details_NtUpdateWnfStateData
0x18000f077  mov     edi, eax
0x18000f079  inc     esi
0x18000f07b  cmp     edi, 0C0000001h
0x18000f081  jnz     short loc_18000F090
0x18000f083  cmp     esi, 64h ; 'd'
0x18000f086  jge     short loc_18000F090
0x18000f088  test    ebx, ebx
0x18000f08a  jz      loc_18000EF45
0x18000f090  test    ebx, ebx
0x18000f092  cmovz   ebx, edi
0x18000f095  mov     eax, ebx
0x18000f097  mov     rcx, [rbp+0F70h+var_20]
0x18000f09e  xor     rcx, rsp; StackCookie
0x18000f0a1  call    __security_check_cookie
0x18000f0a6  lea     r11, [rsp+1070h+var_10]
0x18000f0ae  mov     rbx, [r11+20h]
0x18000f0b2  mov     rsi, [r11+28h]
0x18000f0b6  mov     rdi, [r11+30h]
0x18000f0ba  mov     rsp, r11
0x18000f0bd  pop     r14
0x18000f0bf  pop     r12
0x18000f0c1  pop     rbp
0x18000f0c2  retn
0x18000f0c4  mov     eax, [r8+8]
0x18000f0c8  add     [rcx+8], eax
0x18000f0cb  mov     r9d, [rsp+1070h+var_1030]
0x18000f0d0  jmp     loc_18000F04A
```
