# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180012948`
- end: `0x180012b1d`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000bcc0`

## callees

- `0x180009e82`
- `0x180012948`
- `0x1800137ec`
- `0x180013864`
- `0x18003c240`
- `0x18003c300`

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
0x180012948  push    rbp
0x18001294a  push    rbx
0x18001294b  push    rsi
0x18001294c  push    rdi
0x18001294d  push    r12
0x18001294f  push    r14
0x180012951  lea     rbp, [rsp-0F68h]
0x180012959  mov     eax, 1068h
0x18001295e  call    _alloca_probe
0x180012963  sub     rsp, rax
0x180012966  mov     rax, cs:__security_cookie
0x18001296d  xor     rax, rsp
0x180012970  mov     [rbp+0F90h+var_40], rax
0x180012977  mov     rax, [rcx+8]
0x18001297b  xor     ebx, ebx
0x18001297d  sub     rax, [rcx]
0x180012980  xor     edi, edi
0x180012982  mov     r14, rcx
0x180012985  cmp     rax, 0Ch
0x180012989  jb      loc_180012AE9
0x18001298f  xor     esi, esi
0x180012991  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001299b  xor     edx, edx; Val
0x18001299d  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800129a2  mov     r8d, 1000h; Size
0x1800129a8  call    memset_0
0x1800129ad  lea     rax, [rsp+1090h+var_1050]
0x1800129b2  mov     [rsp+1090h+var_1050], 1000h
0x1800129ba  mov     [rsp+1090h+var_1068], rax
0x1800129bf  lea     r9, [rsp+1090h+var_104C]
0x1800129c4  lea     rax, [rsp+1090h+var_1040]
0x1800129c9  mov     [rsp+1090h+var_104C], 0
0x1800129d1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800129d8  mov     [rsp+1090h+var_1070], rax
0x1800129dd  call    wil_details_NtQueryWnfStateData
0x1800129e2  mov     ebx, eax
0x1800129e4  test    eax, eax
0x1800129e6  jnz     loc_180012AD2
0x1800129ec  mov     r9d, [rsp+1090h+var_1050]
0x1800129f1  mov     rax, r12
0x1800129f4  mul     r9
0x1800129f7  shr     rdx, 3
0x1800129fb  lea     rcx, [rdx+rdx*2]
0x1800129ff  shl     rcx, 2
0x180012a03  cmp     r9, rcx
0x180012a06  jz      short loc_180012A10
0x180012a08  xor     r9d, r9d
0x180012a0b  mov     [rsp+1090h+var_1050], r9d
0x180012a10  mov     r8, [r14]
0x180012a13  mov     rax, r12
0x180012a16  mov     ecx, r9d
0x180012a19  mul     rcx
0x180012a1c  mov     rcx, [r14+8]
0x180012a20  mov     rax, r12
0x180012a23  mov     r10, rdx
0x180012a26  sub     rcx, r8
0x180012a29  mul     rcx
0x180012a2c  shr     r10, 3
0x180012a30  shr     rdx, 3
0x180012a34  lea     rax, [rdx+rdx*2]
0x180012a38  lea     rdi, [r8+rax*4]
0x180012a3c  jmp     short loc_180012AA7
0x180012a3e  mov     eax, r10d
0x180012a41  lea     rcx, [rax+rax*2]
0x180012a45  lea     rdx, [rdx+rcx*4]
0x180012a49  lea     rax, [rsp+1090h+var_1040]
0x180012a4e  cmp     rax, rdx
0x180012a51  jz      short loc_180012A78
0x180012a53  mov     r11d, [r8]
0x180012a56  lea     rcx, [rsp+1090h+var_1040]
0x180012a5b  cmp     [rcx], r11d
0x180012a5e  jnz     short loc_180012A6F
0x180012a60  movzx   eax, word ptr [r8+4]
0x180012a65  cmp     [rcx+4], ax
0x180012a69  jz      loc_180012B0F
0x180012a6f  add     rcx, 0Ch
0x180012a73  cmp     rcx, rdx
0x180012a76  jnz     short loc_180012A5B
0x180012a78  mov     eax, r9d
0x180012a7b  add     rax, 0Ch
0x180012a7f  cmp     rax, 1000h
0x180012a85  ja      short loc_180012AA3
0x180012a87  movsd   xmm0, qword ptr [r8]
0x180012a8c  add     r9d, 0Ch
0x180012a90  movsd   qword ptr [rdx], xmm0
0x180012a94  inc     r10d
0x180012a97  mov     eax, [r8+8]
0x180012a9b  mov     [rdx+8], eax
0x180012a9e  mov     [rsp+1090h+var_1050], r9d
0x180012aa3  add     r8, 0Ch
0x180012aa7  lea     rdx, [rsp+1090h+var_1040]
0x180012aac  cmp     r8, rdi
0x180012aaf  jnz     short loc_180012A3E
0x180012ab1  mov     eax, [rsp+1090h+var_104C]
0x180012ab5  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180012abc  mov     [rsp+1090h+var_1060], 1
0x180012ac4  mov     r8d, r9d
0x180012ac7  mov     dword ptr [rsp+1090h+var_1068], eax
0x180012acb  call    wil_details_NtUpdateWnfStateData
0x180012ad0  mov     edi, eax
0x180012ad2  cmp     edi, 0C0000001h
0x180012ad8  jnz     short loc_180012AE9
0x180012ada  inc     esi
0x180012adc  cmp     esi, 64h ; 'd'
0x180012adf  jge     short loc_180012AE9
0x180012ae1  test    ebx, ebx
0x180012ae3  jz      loc_18001299B
0x180012ae9  test    ebx, ebx
0x180012aeb  cmovz   ebx, edi
0x180012aee  mov     eax, ebx
0x180012af0  mov     rcx, [rbp+0F90h+var_40]
0x180012af7  xor     rcx, rsp; StackCookie
0x180012afa  call    __security_check_cookie
0x180012aff  add     rsp, 1068h
0x180012b06  pop     r14
0x180012b08  pop     r12
0x180012b0a  pop     rdi
0x180012b0b  pop     rsi
0x180012b0c  pop     rbx
0x180012b0d  pop     rbp
0x180012b0e  retn
0x180012b0f  mov     eax, [r8+8]
0x180012b13  add     [rcx+8], eax
0x180012b16  mov     r9d, [rsp+1090h+var_1050]
0x180012b1b  jmp     short loc_180012AA3
```
