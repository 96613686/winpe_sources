# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180010c7c`
- end: `0x180010e46`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000c950`

## callees

- `0x18000b550`
- `0x18000c1a4`
- `0x180010c7c`
- `0x180010f98`
- `0x180011010`
- `0x18001c5d0`

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
0x180010c7c  push    rbp
0x180010c7e  push    rbx
0x180010c7f  push    rsi
0x180010c80  push    rdi
0x180010c81  push    r12
0x180010c83  push    r14
0x180010c85  lea     rbp, [rsp-0F68h]
0x180010c8d  mov     eax, 1068h
0x180010c92  call    _alloca_probe
0x180010c97  sub     rsp, rax
0x180010c9a  mov     rax, cs:__security_cookie
0x180010ca1  xor     rax, rsp
0x180010ca4  mov     [rbp+0F90h+var_40], rax
0x180010cab  mov     rax, [rcx+8]
0x180010caf  xor     ebx, ebx
0x180010cb1  sub     rax, [rcx]
0x180010cb4  xor     edi, edi
0x180010cb6  mov     r14, rcx
0x180010cb9  cmp     rax, 0Ch
0x180010cbd  jb      loc_180010E20
0x180010cc3  xor     esi, esi
0x180010cc5  mov     r12, 0AAAAAAAAAAAAAAABh
0x180010ccf  xor     edx, edx; Val
0x180010cd1  lea     rcx, [rsp+1090h+var_1040]; void *
0x180010cd6  mov     r8d, 1000h; Size
0x180010cdc  call    memset_0
0x180010ce1  lea     rax, [rsp+1090h+var_1050]
0x180010ce6  mov     [rsp+1090h+var_1050], 1000h
0x180010cee  mov     [rsp+1090h+var_1068], rax
0x180010cf3  lea     r9, [rsp+1090h+var_104C]
0x180010cf8  lea     rax, [rsp+1090h+var_1040]
0x180010cfd  mov     [rsp+1090h+var_104C], 0
0x180010d05  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180010d0c  mov     [rsp+1090h+var_1070], rax
0x180010d11  call    wil_details_NtQueryWnfStateData
0x180010d16  mov     ebx, eax
0x180010d18  test    eax, eax
0x180010d1a  jnz     loc_180010E09
0x180010d20  mov     r9d, [rsp+1090h+var_1050]
0x180010d25  mov     rax, r12
0x180010d28  mul     r9
0x180010d2b  shr     rdx, 3
0x180010d2f  lea     rcx, [rdx+rdx*2]
0x180010d33  shl     rcx, 2
0x180010d37  cmp     r9, rcx
0x180010d3a  jz      short loc_180010D44
0x180010d3c  xor     r9d, r9d
0x180010d3f  mov     [rsp+1090h+var_1050], r9d
0x180010d44  mov     r8, [r14]
0x180010d47  mov     rax, r12
0x180010d4a  mov     ecx, r9d
0x180010d4d  mul     rcx
0x180010d50  mov     rcx, [r14+8]
0x180010d54  mov     rax, r12
0x180010d57  mov     r11, rdx
0x180010d5a  sub     rcx, r8
0x180010d5d  mul     rcx
0x180010d60  shr     r11, 3
0x180010d64  shr     rdx, 3
0x180010d68  lea     rax, [rdx+rdx*2]
0x180010d6c  lea     rdi, [r8+rax*4]
0x180010d70  jmp     short loc_180010DDE
0x180010d72  mov     eax, r11d
0x180010d75  lea     r10, [rsp+1090h+var_1040]
0x180010d7a  lea     rcx, [rax+rax*2]
0x180010d7e  lea     r10, [r10+rcx*4]
0x180010d82  cmp     rdx, r10
0x180010d85  jz      short loc_180010DAD
0x180010d87  mov     eax, [r8]
0x180010d8a  cmp     [rdx], eax
0x180010d8c  jnz     short loc_180010D99
0x180010d8e  movzx   eax, word ptr [r8+4]
0x180010d93  cmp     [rdx+4], ax
0x180010d97  jz      short loc_180010D9F
0x180010d99  add     rdx, 0Ch
0x180010d9d  jmp     short loc_180010D82
0x180010d9f  mov     eax, [r8+8]
0x180010da3  add     [rdx+8], eax
0x180010da6  mov     r9d, [rsp+1090h+var_1050]
0x180010dab  jmp     short loc_180010DDA
0x180010dad  mov     eax, r9d
0x180010db0  add     rax, 0Ch
0x180010db4  cmp     rax, 1000h
0x180010dba  ja      short loc_180010DDA
0x180010dbc  movsd   xmm0, qword ptr [r8]
0x180010dc1  add     r9d, 0Ch
0x180010dc5  movsd   qword ptr [r10], xmm0
0x180010dca  inc     r11d
0x180010dcd  mov     eax, [r8+8]
0x180010dd1  mov     [r10+8], eax
0x180010dd5  mov     [rsp+1090h+var_1050], r9d
0x180010dda  add     r8, 0Ch
0x180010dde  lea     rdx, [rsp+1090h+var_1040]
0x180010de3  cmp     r8, rdi
0x180010de6  jnz     short loc_180010D72
0x180010de8  mov     eax, [rsp+1090h+var_104C]
0x180010dec  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180010df3  mov     [rsp+1090h+var_1060], 1
0x180010dfb  mov     r8d, r9d
0x180010dfe  mov     dword ptr [rsp+1090h+var_1068], eax
0x180010e02  call    wil_details_NtUpdateWnfStateData
0x180010e07  mov     edi, eax
0x180010e09  cmp     edi, 0C0000001h
0x180010e0f  jnz     short loc_180010E20
0x180010e11  inc     esi
0x180010e13  cmp     esi, 64h ; 'd'
0x180010e16  jge     short loc_180010E20
0x180010e18  test    ebx, ebx
0x180010e1a  jz      loc_180010CCF
0x180010e20  test    ebx, ebx
0x180010e22  cmovz   ebx, edi
0x180010e25  mov     eax, ebx
0x180010e27  mov     rcx, [rbp+0F90h+var_40]
0x180010e2e  xor     rcx, rsp; StackCookie
0x180010e31  call    __security_check_cookie
0x180010e36  add     rsp, 1068h
0x180010e3d  pop     r14
0x180010e3f  pop     r12
0x180010e41  pop     rdi
0x180010e42  pop     rsi
0x180010e43  pop     rbx
0x180010e44  pop     rbp
0x180010e45  retn
```
