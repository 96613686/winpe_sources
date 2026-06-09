# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000ba28`
- end: `0x18000bbfd`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180003100`

## callees

- `0x18000ba28`
- `0x18000cd2c`
- `0x18000cda4`
- `0x18001b0f6`
- `0x18001b150`
- `0x18001b210`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int WnfStateData; // ebx
  unsigned int updated; // edi
  int v4; // esi
  int v5; // edx
  int v6; // r8d
  unsigned int v7; // r9d
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
        v9 = v7 / 0xC;
        v10 = *a1 + 12 * ((a1[1] - *a1) / 0xCuLL);
        while ( v8 != v10 )
        {
          v11 = &v17[3 * v9];
          if ( v17 == v11 )
          {
LABEL_12:
            if ( (unsigned __int64)v7 + 12 <= 0x1000 )
            {
              v7 += 12;
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
                    (unsigned int)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                    (unsigned int)v17,
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
0x18000ba28  push    rbp
0x18000ba2a  push    rbx
0x18000ba2b  push    rsi
0x18000ba2c  push    rdi
0x18000ba2d  push    r12
0x18000ba2f  push    r14
0x18000ba31  lea     rbp, [rsp-0F68h]
0x18000ba39  mov     eax, 1068h
0x18000ba3e  call    _alloca_probe
0x18000ba43  sub     rsp, rax
0x18000ba46  mov     rax, cs:__security_cookie
0x18000ba4d  xor     rax, rsp
0x18000ba50  mov     [rbp+0F90h+var_40], rax
0x18000ba57  mov     rax, [rcx+8]
0x18000ba5b  xor     ebx, ebx
0x18000ba5d  sub     rax, [rcx]
0x18000ba60  xor     edi, edi
0x18000ba62  mov     r14, rcx
0x18000ba65  cmp     rax, 0Ch
0x18000ba69  jb      loc_18000BBC9
0x18000ba6f  xor     esi, esi
0x18000ba71  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000ba7b  xor     edx, edx; Val
0x18000ba7d  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000ba82  mov     r8d, 1000h; Size
0x18000ba88  call    memset_0
0x18000ba8d  lea     rax, [rsp+1090h+var_1050]
0x18000ba92  mov     [rsp+1090h+var_1050], 1000h
0x18000ba9a  mov     [rsp+1090h+var_1068], rax
0x18000ba9f  lea     r9, [rsp+1090h+var_104C]
0x18000baa4  lea     rax, [rsp+1090h+var_1040]
0x18000baa9  mov     [rsp+1090h+var_104C], 0
0x18000bab1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000bab8  mov     [rsp+1090h+var_1070], rax
0x18000babd  call    wil_details_NtQueryWnfStateData
0x18000bac2  mov     ebx, eax
0x18000bac4  test    eax, eax
0x18000bac6  jnz     loc_18000BBB2
0x18000bacc  mov     r9d, [rsp+1090h+var_1050]
0x18000bad1  mov     rax, r12
0x18000bad4  mul     r9
0x18000bad7  shr     rdx, 3
0x18000badb  lea     rcx, [rdx+rdx*2]
0x18000badf  shl     rcx, 2
0x18000bae3  cmp     r9, rcx
0x18000bae6  jz      short loc_18000BAF0
0x18000bae8  xor     r9d, r9d
0x18000baeb  mov     [rsp+1090h+var_1050], r9d
0x18000baf0  mov     r8, [r14]
0x18000baf3  mov     rax, r12
0x18000baf6  mov     ecx, r9d
0x18000baf9  mul     rcx
0x18000bafc  mov     rcx, [r14+8]
0x18000bb00  mov     rax, r12
0x18000bb03  mov     r10, rdx
0x18000bb06  sub     rcx, r8
0x18000bb09  mul     rcx
0x18000bb0c  shr     r10, 3
0x18000bb10  shr     rdx, 3
0x18000bb14  lea     rax, [rdx+rdx*2]
0x18000bb18  lea     rdi, [r8+rax*4]
0x18000bb1c  jmp     short loc_18000BB87
0x18000bb1e  mov     eax, r10d
0x18000bb21  lea     rcx, [rax+rax*2]
0x18000bb25  lea     rdx, [rdx+rcx*4]
0x18000bb29  lea     rax, [rsp+1090h+var_1040]
0x18000bb2e  cmp     rax, rdx
0x18000bb31  jz      short loc_18000BB58
0x18000bb33  mov     r11d, [r8]
0x18000bb36  lea     rcx, [rsp+1090h+var_1040]
0x18000bb3b  cmp     [rcx], r11d
0x18000bb3e  jnz     short loc_18000BB4F
0x18000bb40  movzx   eax, word ptr [r8+4]
0x18000bb45  cmp     [rcx+4], ax
0x18000bb49  jz      loc_18000BBEF
0x18000bb4f  add     rcx, 0Ch
0x18000bb53  cmp     rcx, rdx
0x18000bb56  jnz     short loc_18000BB3B
0x18000bb58  mov     eax, r9d
0x18000bb5b  add     rax, 0Ch
0x18000bb5f  cmp     rax, 1000h
0x18000bb65  ja      short loc_18000BB83
0x18000bb67  movsd   xmm0, qword ptr [r8]
0x18000bb6c  add     r9d, 0Ch
0x18000bb70  movsd   qword ptr [rdx], xmm0
0x18000bb74  inc     r10d
0x18000bb77  mov     eax, [r8+8]
0x18000bb7b  mov     [rdx+8], eax
0x18000bb7e  mov     [rsp+1090h+var_1050], r9d
0x18000bb83  add     r8, 0Ch
0x18000bb87  lea     rdx, [rsp+1090h+var_1040]
0x18000bb8c  cmp     r8, rdi
0x18000bb8f  jnz     short loc_18000BB1E
0x18000bb91  mov     eax, [rsp+1090h+var_104C]
0x18000bb95  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000bb9c  mov     [rsp+1090h+var_1060], 1
0x18000bba4  mov     r8d, r9d
0x18000bba7  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000bbab  call    wil_details_NtUpdateWnfStateData
0x18000bbb0  mov     edi, eax
0x18000bbb2  cmp     edi, 0C0000001h
0x18000bbb8  jnz     short loc_18000BBC9
0x18000bbba  inc     esi
0x18000bbbc  cmp     esi, 64h ; 'd'
0x18000bbbf  jge     short loc_18000BBC9
0x18000bbc1  test    ebx, ebx
0x18000bbc3  jz      loc_18000BA7B
0x18000bbc9  test    ebx, ebx
0x18000bbcb  cmovz   ebx, edi
0x18000bbce  mov     eax, ebx
0x18000bbd0  mov     rcx, [rbp+0F90h+var_40]
0x18000bbd7  xor     rcx, rsp; StackCookie
0x18000bbda  call    __security_check_cookie
0x18000bbdf  add     rsp, 1068h
0x18000bbe6  pop     r14
0x18000bbe8  pop     r12
0x18000bbea  pop     rdi
0x18000bbeb  pop     rsi
0x18000bbec  pop     rbx
0x18000bbed  pop     rbp
0x18000bbee  retn
0x18000bbef  mov     eax, [r8+8]
0x18000bbf3  add     [rcx+8], eax
0x18000bbf6  mov     r9d, [rsp+1090h+var_1050]
0x18000bbfb  jmp     short loc_18000BB83
```
