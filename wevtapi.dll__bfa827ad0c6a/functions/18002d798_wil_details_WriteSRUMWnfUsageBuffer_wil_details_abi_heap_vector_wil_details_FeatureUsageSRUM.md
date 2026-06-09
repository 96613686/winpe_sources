# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18002d798`
- end: `0x18002d962`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800293d0`

## callees

- `0x180024a50`
- `0x180025514`
- `0x18002d798`
- `0x18002db5c`
- `0x18002dbd4`
- `0x180038f50`

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
0x18002d798  push    rbp
0x18002d79a  push    rbx
0x18002d79b  push    rsi
0x18002d79c  push    rdi
0x18002d79d  push    r12
0x18002d79f  push    r14
0x18002d7a1  lea     rbp, [rsp-0F68h]
0x18002d7a9  mov     eax, 1068h
0x18002d7ae  call    _alloca_probe
0x18002d7b3  sub     rsp, rax
0x18002d7b6  mov     rax, cs:__security_cookie
0x18002d7bd  xor     rax, rsp
0x18002d7c0  mov     [rbp+0F90h+var_40], rax
0x18002d7c7  mov     rax, [rcx+8]
0x18002d7cb  xor     ebx, ebx
0x18002d7cd  sub     rax, [rcx]
0x18002d7d0  xor     edi, edi
0x18002d7d2  mov     r14, rcx
0x18002d7d5  cmp     rax, 0Ch
0x18002d7d9  jb      loc_18002D93C
0x18002d7df  xor     esi, esi
0x18002d7e1  mov     r12, 0AAAAAAAAAAAAAAABh
0x18002d7eb  xor     edx, edx; Val
0x18002d7ed  lea     rcx, [rsp+1090h+var_1040]; void *
0x18002d7f2  mov     r8d, 1000h; Size
0x18002d7f8  call    memset_0
0x18002d7fd  lea     rax, [rsp+1090h+var_1050]
0x18002d802  mov     [rsp+1090h+var_1050], 1000h
0x18002d80a  mov     [rsp+1090h+var_1068], rax
0x18002d80f  lea     r9, [rsp+1090h+var_104C]
0x18002d814  lea     rax, [rsp+1090h+var_1040]
0x18002d819  mov     [rsp+1090h+var_104C], 0
0x18002d821  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002d828  mov     [rsp+1090h+var_1070], rax
0x18002d82d  call    wil_details_NtQueryWnfStateData
0x18002d832  mov     ebx, eax
0x18002d834  test    eax, eax
0x18002d836  jnz     loc_18002D925
0x18002d83c  mov     r9d, [rsp+1090h+var_1050]
0x18002d841  mov     rax, r12
0x18002d844  mul     r9
0x18002d847  shr     rdx, 3
0x18002d84b  lea     rcx, [rdx+rdx*2]
0x18002d84f  shl     rcx, 2
0x18002d853  cmp     r9, rcx
0x18002d856  jz      short loc_18002D860
0x18002d858  xor     r9d, r9d
0x18002d85b  mov     [rsp+1090h+var_1050], r9d
0x18002d860  mov     r8, [r14]
0x18002d863  mov     rax, r12
0x18002d866  mov     ecx, r9d
0x18002d869  mul     rcx
0x18002d86c  mov     rcx, [r14+8]
0x18002d870  mov     rax, r12
0x18002d873  mov     r11, rdx
0x18002d876  sub     rcx, r8
0x18002d879  mul     rcx
0x18002d87c  shr     r11, 3
0x18002d880  shr     rdx, 3
0x18002d884  lea     rax, [rdx+rdx*2]
0x18002d888  lea     rdi, [r8+rax*4]
0x18002d88c  jmp     short loc_18002D8FA
0x18002d88e  mov     eax, r11d
0x18002d891  lea     r10, [rsp+1090h+var_1040]
0x18002d896  lea     rcx, [rax+rax*2]
0x18002d89a  lea     r10, [r10+rcx*4]
0x18002d89e  cmp     rdx, r10
0x18002d8a1  jz      short loc_18002D8C9
0x18002d8a3  mov     eax, [r8]
0x18002d8a6  cmp     [rdx], eax
0x18002d8a8  jnz     short loc_18002D8B5
0x18002d8aa  movzx   eax, word ptr [r8+4]
0x18002d8af  cmp     [rdx+4], ax
0x18002d8b3  jz      short loc_18002D8BB
0x18002d8b5  add     rdx, 0Ch
0x18002d8b9  jmp     short loc_18002D89E
0x18002d8bb  mov     eax, [r8+8]
0x18002d8bf  add     [rdx+8], eax
0x18002d8c2  mov     r9d, [rsp+1090h+var_1050]
0x18002d8c7  jmp     short loc_18002D8F6
0x18002d8c9  mov     eax, r9d
0x18002d8cc  add     rax, 0Ch
0x18002d8d0  cmp     rax, 1000h
0x18002d8d6  ja      short loc_18002D8F6
0x18002d8d8  movsd   xmm0, qword ptr [r8]
0x18002d8dd  add     r9d, 0Ch
0x18002d8e1  movsd   qword ptr [r10], xmm0
0x18002d8e6  inc     r11d
0x18002d8e9  mov     eax, [r8+8]
0x18002d8ed  mov     [r10+8], eax
0x18002d8f1  mov     [rsp+1090h+var_1050], r9d
0x18002d8f6  add     r8, 0Ch
0x18002d8fa  lea     rdx, [rsp+1090h+var_1040]
0x18002d8ff  cmp     r8, rdi
0x18002d902  jnz     short loc_18002D88E
0x18002d904  mov     eax, [rsp+1090h+var_104C]
0x18002d908  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002d90f  mov     [rsp+1090h+var_1060], 1
0x18002d917  mov     r8d, r9d
0x18002d91a  mov     dword ptr [rsp+1090h+var_1068], eax
0x18002d91e  call    wil_details_NtUpdateWnfStateData
0x18002d923  mov     edi, eax
0x18002d925  cmp     edi, 0C0000001h
0x18002d92b  jnz     short loc_18002D93C
0x18002d92d  inc     esi
0x18002d92f  cmp     esi, 64h ; 'd'
0x18002d932  jge     short loc_18002D93C
0x18002d934  test    ebx, ebx
0x18002d936  jz      loc_18002D7EB
0x18002d93c  test    ebx, ebx
0x18002d93e  cmovz   ebx, edi
0x18002d941  mov     eax, ebx
0x18002d943  mov     rcx, [rbp+0F90h+var_40]
0x18002d94a  xor     rcx, rsp; StackCookie
0x18002d94d  call    __security_check_cookie
0x18002d952  add     rsp, 1068h
0x18002d959  pop     r14
0x18002d95b  pop     r12
0x18002d95d  pop     rdi
0x18002d95e  pop     rsi
0x18002d95f  pop     rbx
0x18002d960  pop     rbp
0x18002d961  retn
```
