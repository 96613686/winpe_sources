# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18001b6a4`
- end: `0x18001b879`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180016650`

## callees

- `0x18001b6a4`
- `0x18001b940`
- `0x18001b9b8`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001bd80`

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
0x18001b6a4  push    rbp
0x18001b6a6  push    rbx
0x18001b6a7  push    rsi
0x18001b6a8  push    rdi
0x18001b6a9  push    r12
0x18001b6ab  push    r14
0x18001b6ad  lea     rbp, [rsp-0F68h]
0x18001b6b5  mov     eax, 1068h
0x18001b6ba  call    _alloca_probe
0x18001b6bf  sub     rsp, rax
0x18001b6c2  mov     rax, cs:__security_cookie
0x18001b6c9  xor     rax, rsp
0x18001b6cc  mov     [rbp+0F90h+var_40], rax
0x18001b6d3  mov     rax, [rcx+8]
0x18001b6d7  xor     ebx, ebx
0x18001b6d9  sub     rax, [rcx]
0x18001b6dc  xor     edi, edi
0x18001b6de  mov     r14, rcx
0x18001b6e1  cmp     rax, 0Ch
0x18001b6e5  jb      loc_18001B845
0x18001b6eb  xor     esi, esi
0x18001b6ed  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001b6f7  xor     edx, edx; Val
0x18001b6f9  lea     rcx, [rsp+1090h+var_1040]; void *
0x18001b6fe  mov     r8d, 1000h; Size
0x18001b704  call    memset_0
0x18001b709  lea     rax, [rsp+1090h+var_1050]
0x18001b70e  mov     [rsp+1090h+var_1050], 1000h
0x18001b716  mov     [rsp+1090h+var_1068], rax
0x18001b71b  lea     r9, [rsp+1090h+var_104C]
0x18001b720  lea     rax, [rsp+1090h+var_1040]
0x18001b725  mov     [rsp+1090h+var_104C], 0
0x18001b72d  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001b734  mov     [rsp+1090h+var_1070], rax
0x18001b739  call    wil_details_NtQueryWnfStateData
0x18001b73e  mov     ebx, eax
0x18001b740  test    eax, eax
0x18001b742  jnz     loc_18001B82E
0x18001b748  mov     r9d, [rsp+1090h+var_1050]
0x18001b74d  mov     rax, r12
0x18001b750  mul     r9
0x18001b753  shr     rdx, 3
0x18001b757  lea     rcx, [rdx+rdx*2]
0x18001b75b  shl     rcx, 2
0x18001b75f  cmp     r9, rcx
0x18001b762  jz      short loc_18001B76C
0x18001b764  xor     r9d, r9d
0x18001b767  mov     [rsp+1090h+var_1050], r9d
0x18001b76c  mov     r8, [r14]
0x18001b76f  mov     rax, r12
0x18001b772  mov     ecx, r9d
0x18001b775  mul     rcx
0x18001b778  mov     rcx, [r14+8]
0x18001b77c  mov     rax, r12
0x18001b77f  mov     r10, rdx
0x18001b782  sub     rcx, r8
0x18001b785  mul     rcx
0x18001b788  shr     r10, 3
0x18001b78c  shr     rdx, 3
0x18001b790  lea     rax, [rdx+rdx*2]
0x18001b794  lea     rdi, [r8+rax*4]
0x18001b798  jmp     short loc_18001B803
0x18001b79a  mov     eax, r10d
0x18001b79d  lea     rcx, [rax+rax*2]
0x18001b7a1  lea     rdx, [rdx+rcx*4]
0x18001b7a5  lea     rax, [rsp+1090h+var_1040]
0x18001b7aa  cmp     rax, rdx
0x18001b7ad  jz      short loc_18001B7D4
0x18001b7af  mov     r11d, [r8]
0x18001b7b2  lea     rcx, [rsp+1090h+var_1040]
0x18001b7b7  cmp     [rcx], r11d
0x18001b7ba  jnz     short loc_18001B7CB
0x18001b7bc  movzx   eax, word ptr [r8+4]
0x18001b7c1  cmp     [rcx+4], ax
0x18001b7c5  jz      loc_18001B86B
0x18001b7cb  add     rcx, 0Ch
0x18001b7cf  cmp     rcx, rdx
0x18001b7d2  jnz     short loc_18001B7B7
0x18001b7d4  mov     eax, r9d
0x18001b7d7  add     rax, 0Ch
0x18001b7db  cmp     rax, 1000h
0x18001b7e1  ja      short loc_18001B7FF
0x18001b7e3  movsd   xmm0, qword ptr [r8]
0x18001b7e8  add     r9d, 0Ch
0x18001b7ec  movsd   qword ptr [rdx], xmm0
0x18001b7f0  inc     r10d
0x18001b7f3  mov     eax, [r8+8]
0x18001b7f7  mov     [rdx+8], eax
0x18001b7fa  mov     [rsp+1090h+var_1050], r9d
0x18001b7ff  add     r8, 0Ch
0x18001b803  lea     rdx, [rsp+1090h+var_1040]
0x18001b808  cmp     r8, rdi
0x18001b80b  jnz     short loc_18001B79A
0x18001b80d  mov     eax, [rsp+1090h+var_104C]
0x18001b811  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001b818  mov     [rsp+1090h+var_1060], 1
0x18001b820  mov     r8d, r9d
0x18001b823  mov     dword ptr [rsp+1090h+var_1068], eax
0x18001b827  call    wil_details_NtUpdateWnfStateData
0x18001b82c  mov     edi, eax
0x18001b82e  cmp     edi, 0C0000001h
0x18001b834  jnz     short loc_18001B845
0x18001b836  inc     esi
0x18001b838  cmp     esi, 64h ; 'd'
0x18001b83b  jge     short loc_18001B845
0x18001b83d  test    ebx, ebx
0x18001b83f  jz      loc_18001B6F7
0x18001b845  test    ebx, ebx
0x18001b847  cmovz   ebx, edi
0x18001b84a  mov     eax, ebx
0x18001b84c  mov     rcx, [rbp+0F90h+var_40]
0x18001b853  xor     rcx, rsp; StackCookie
0x18001b856  call    __security_check_cookie
0x18001b85b  add     rsp, 1068h
0x18001b862  pop     r14
0x18001b864  pop     r12
0x18001b866  pop     rdi
0x18001b867  pop     rsi
0x18001b868  pop     rbx
0x18001b869  pop     rbp
0x18001b86a  retn
0x18001b86b  mov     eax, [r8+8]
0x18001b86f  add     [rcx+8], eax
0x18001b872  mov     r9d, [rsp+1090h+var_1050]
0x18001b877  jmp     short loc_18001B7FF
```
