# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000bb68`
- end: `0x18000bd55`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180002770`

## callees

- `0x18000bb68`
- `0x18000be68`
- `0x18000bf10`
- `0x18000d6d2`
- `0x18000d700`
- `0x18000d7c0`

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
0x18000bb68  mov     rax, rsp
0x18000bb6b  mov     [rax+8], rbx
0x18000bb6f  mov     [rax+10h], rsi
0x18000bb73  mov     [rax+18h], rdi
0x18000bb77  push    rbp
0x18000bb78  push    r12
0x18000bb7a  push    r14
0x18000bb7c  lea     rbp, [rax-0F78h]
0x18000bb83  mov     eax, 1060h
0x18000bb88  call    _alloca_probe
0x18000bb8d  sub     rsp, rax
0x18000bb90  mov     rax, cs:__security_cookie
0x18000bb97  xor     rax, rsp
0x18000bb9a  mov     [rbp+0F70h+var_20], rax
0x18000bba1  mov     rax, [rcx+8]
0x18000bba5  xor     ebx, ebx
0x18000bba7  sub     rax, [rcx]
0x18000bbaa  xor     edi, edi
0x18000bbac  mov     r14, rcx
0x18000bbaf  cmp     rax, 0Ch
0x18000bbb3  jb      loc_18000BD10
0x18000bbb9  xor     esi, esi
0x18000bbbb  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000bbc5  xor     edx, edx; Val
0x18000bbc7  lea     rcx, [rsp+1070h+var_1020]; void *
0x18000bbcc  mov     r8d, 1000h; Size
0x18000bbd2  call    memset_0
0x18000bbd7  and     [rsp+1070h+var_102C], 0
0x18000bbdc  lea     rax, [rsp+1070h+var_1030]
0x18000bbe1  mov     qword ptr [rsp+1070h+var_1048], rax
0x18000bbe6  lea     r9, [rsp+1070h+var_102C]
0x18000bbeb  lea     rax, [rsp+1070h+var_1020]
0x18000bbf0  mov     [rsp+1070h+var_1030], 1000h
0x18000bbf8  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000bbff  mov     [rsp+1070h+var_1050], rax
0x18000bc04  call    wil_details_NtQueryWnfStateData
0x18000bc09  mov     ebx, eax
0x18000bc0b  test    eax, eax
0x18000bc0d  jnz     loc_18000BCF9
0x18000bc13  mov     r9d, [rsp+1070h+var_1030]
0x18000bc18  mov     rax, r12
0x18000bc1b  mul     r9
0x18000bc1e  shr     rdx, 3
0x18000bc22  lea     rcx, [rdx+rdx*2]
0x18000bc26  shl     rcx, 2
0x18000bc2a  cmp     r9, rcx
0x18000bc2d  jz      short loc_18000BC37
0x18000bc2f  xor     r9d, r9d
0x18000bc32  mov     [rsp+1070h+var_1030], r9d
0x18000bc37  mov     r8, [r14]
0x18000bc3a  mov     rax, r12
0x18000bc3d  mov     ecx, r9d
0x18000bc40  mul     rcx
0x18000bc43  mov     rcx, [r14+8]
0x18000bc47  mov     rax, r12
0x18000bc4a  mov     r10, rdx
0x18000bc4d  sub     rcx, r8
0x18000bc50  mul     rcx
0x18000bc53  shr     r10, 3
0x18000bc57  shr     rdx, 3
0x18000bc5b  lea     rax, [rdx+rdx*2]
0x18000bc5f  lea     rdi, [r8+rax*4]
0x18000bc63  jmp     short loc_18000BCCE
0x18000bc65  mov     eax, r10d
0x18000bc68  lea     rcx, [rax+rax*2]
0x18000bc6c  lea     rdx, [rdx+rcx*4]
0x18000bc70  lea     rax, [rsp+1070h+var_1020]
0x18000bc75  lea     rcx, [rsp+1070h+var_1020]
0x18000bc7a  cmp     rax, rdx
0x18000bc7d  jz      short loc_18000BC9F
0x18000bc7f  mov     r11d, [r8]
0x18000bc82  cmp     [rcx], r11d
0x18000bc85  jnz     short loc_18000BC96
0x18000bc87  movzx   eax, word ptr [r8+4]
0x18000bc8c  cmp     [rcx+4], ax
0x18000bc90  jz      loc_18000BD44
0x18000bc96  add     rcx, 0Ch
0x18000bc9a  cmp     rcx, rdx
0x18000bc9d  jnz     short loc_18000BC82
0x18000bc9f  mov     eax, r9d
0x18000bca2  add     rax, 0Ch
0x18000bca6  cmp     rax, 1000h
0x18000bcac  ja      short loc_18000BCCA
0x18000bcae  movsd   xmm0, qword ptr [r8]
0x18000bcb3  add     r9d, 0Ch
0x18000bcb7  movsd   qword ptr [rdx], xmm0
0x18000bcbb  inc     r10d
0x18000bcbe  mov     eax, [r8+8]
0x18000bcc2  mov     [rdx+8], eax
0x18000bcc5  mov     [rsp+1070h+var_1030], r9d
0x18000bcca  add     r8, 0Ch
0x18000bcce  lea     rdx, [rsp+1070h+var_1020]
0x18000bcd3  cmp     r8, rdi
0x18000bcd6  jnz     short loc_18000BC65
0x18000bcd8  mov     eax, [rsp+1070h+var_102C]
0x18000bcdc  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000bce3  mov     [rsp+1070h+var_1040], 1
0x18000bceb  mov     r8d, r9d
0x18000bcee  mov     [rsp+1070h+var_1048], eax
0x18000bcf2  call    wil_details_NtUpdateWnfStateData
0x18000bcf7  mov     edi, eax
0x18000bcf9  inc     esi
0x18000bcfb  cmp     edi, 0C0000001h
0x18000bd01  jnz     short loc_18000BD10
0x18000bd03  cmp     esi, 64h ; 'd'
0x18000bd06  jge     short loc_18000BD10
0x18000bd08  test    ebx, ebx
0x18000bd0a  jz      loc_18000BBC5
0x18000bd10  test    ebx, ebx
0x18000bd12  cmovz   ebx, edi
0x18000bd15  mov     eax, ebx
0x18000bd17  mov     rcx, [rbp+0F70h+var_20]
0x18000bd1e  xor     rcx, rsp; StackCookie
0x18000bd21  call    __security_check_cookie
0x18000bd26  lea     r11, [rsp+1070h+var_10]
0x18000bd2e  mov     rbx, [r11+20h]
0x18000bd32  mov     rsi, [r11+28h]
0x18000bd36  mov     rdi, [r11+30h]
0x18000bd3a  mov     rsp, r11
0x18000bd3d  pop     r14
0x18000bd3f  pop     r12
0x18000bd41  pop     rbp
0x18000bd42  retn
0x18000bd44  mov     eax, [r8+8]
0x18000bd48  add     [rcx+8], eax
0x18000bd4b  mov     r9d, [rsp+1070h+var_1030]
0x18000bd50  jmp     loc_18000BCCA
```
