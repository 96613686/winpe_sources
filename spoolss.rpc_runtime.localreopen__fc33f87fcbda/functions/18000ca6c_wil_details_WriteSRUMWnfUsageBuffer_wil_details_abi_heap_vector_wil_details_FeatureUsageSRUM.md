# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000ca6c`
- end: `0x18000cc37`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180006890`

## callees

- `0x180005680`
- `0x18000601c`
- `0x18000ca6c`
- `0x18001097c`
- `0x1800109f4`
- `0x1800169d0`

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
0x18000ca6c  push    rbp
0x18000ca6e  push    rbx
0x18000ca6f  push    rsi
0x18000ca70  push    rdi
0x18000ca71  push    r12
0x18000ca73  push    r14
0x18000ca75  lea     rbp, [rsp-0F68h]
0x18000ca7d  mov     eax, 1068h
0x18000ca82  call    _alloca_probe
0x18000ca87  sub     rsp, rax
0x18000ca8a  mov     rax, cs:__security_cookie
0x18000ca91  xor     rax, rsp
0x18000ca94  mov     [rbp+0F90h+var_40], rax
0x18000ca9b  mov     rax, [rcx+8]
0x18000ca9f  xor     ebx, ebx
0x18000caa1  sub     rax, [rcx]
0x18000caa4  xor     edi, edi
0x18000caa6  mov     r14, rcx
0x18000caa9  cmp     rax, 0Ch
0x18000caad  jb      loc_18000CC10
0x18000cab3  xor     esi, esi
0x18000cab5  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000cabf  xor     edx, edx; Val
0x18000cac1  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000cac6  mov     r8d, 1000h; Size
0x18000cacc  call    memset_0
0x18000cad1  lea     rax, [rsp+1090h+var_1050]
0x18000cad6  mov     [rsp+1090h+var_1050], 1000h
0x18000cade  mov     [rsp+1090h+var_1068], rax
0x18000cae3  lea     r9, [rsp+1090h+var_104C]
0x18000cae8  lea     rax, [rsp+1090h+var_1040]
0x18000caed  mov     [rsp+1090h+var_104C], 0
0x18000caf5  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000cafc  mov     [rsp+1090h+var_1070], rax
0x18000cb01  call    wil_details_NtQueryWnfStateData
0x18000cb06  mov     ebx, eax
0x18000cb08  test    eax, eax
0x18000cb0a  jnz     loc_18000CBF9
0x18000cb10  mov     r9d, [rsp+1090h+var_1050]
0x18000cb15  mov     rax, r12
0x18000cb18  mul     r9
0x18000cb1b  shr     rdx, 3
0x18000cb1f  lea     rcx, [rdx+rdx*2]
0x18000cb23  shl     rcx, 2
0x18000cb27  cmp     r9, rcx
0x18000cb2a  jz      short loc_18000CB34
0x18000cb2c  xor     r9d, r9d
0x18000cb2f  mov     [rsp+1090h+var_1050], r9d
0x18000cb34  mov     r8, [r14]
0x18000cb37  mov     rax, r12
0x18000cb3a  mov     ecx, r9d
0x18000cb3d  mul     rcx
0x18000cb40  mov     rcx, [r14+8]
0x18000cb44  mov     rax, r12
0x18000cb47  mov     r11, rdx
0x18000cb4a  sub     rcx, r8
0x18000cb4d  mul     rcx
0x18000cb50  shr     r11, 3
0x18000cb54  shr     rdx, 3
0x18000cb58  lea     rax, [rdx+rdx*2]
0x18000cb5c  lea     rdi, [r8+rax*4]
0x18000cb60  jmp     short loc_18000CBCE
0x18000cb62  mov     eax, r11d
0x18000cb65  lea     r10, [rsp+1090h+var_1040]
0x18000cb6a  lea     rcx, [rax+rax*2]
0x18000cb6e  lea     r10, [r10+rcx*4]
0x18000cb72  cmp     rdx, r10
0x18000cb75  jz      short loc_18000CB9D
0x18000cb77  mov     eax, [r8]
0x18000cb7a  cmp     [rdx], eax
0x18000cb7c  jnz     short loc_18000CB89
0x18000cb7e  movzx   eax, word ptr [r8+4]
0x18000cb83  cmp     [rdx+4], ax
0x18000cb87  jz      short loc_18000CB8F
0x18000cb89  add     rdx, 0Ch
0x18000cb8d  jmp     short loc_18000CB72
0x18000cb8f  mov     eax, [r8+8]
0x18000cb93  add     [rdx+8], eax
0x18000cb96  mov     r9d, [rsp+1090h+var_1050]
0x18000cb9b  jmp     short loc_18000CBCA
0x18000cb9d  mov     eax, r9d
0x18000cba0  add     rax, 0Ch
0x18000cba4  cmp     rax, 1000h
0x18000cbaa  ja      short loc_18000CBCA
0x18000cbac  movsd   xmm0, qword ptr [r8]
0x18000cbb1  add     r9d, 0Ch
0x18000cbb5  movsd   qword ptr [r10], xmm0
0x18000cbba  inc     r11d
0x18000cbbd  mov     eax, [r8+8]
0x18000cbc1  mov     [r10+8], eax
0x18000cbc5  mov     [rsp+1090h+var_1050], r9d
0x18000cbca  add     r8, 0Ch
0x18000cbce  lea     rdx, [rsp+1090h+var_1040]
0x18000cbd3  cmp     r8, rdi
0x18000cbd6  jnz     short loc_18000CB62
0x18000cbd8  mov     eax, [rsp+1090h+var_104C]
0x18000cbdc  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000cbe3  mov     [rsp+1090h+var_1060], 1
0x18000cbeb  mov     r8d, r9d
0x18000cbee  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000cbf2  call    wil_details_NtUpdateWnfStateData
0x18000cbf7  mov     edi, eax
0x18000cbf9  cmp     edi, 0C0000001h
0x18000cbff  jnz     short loc_18000CC10
0x18000cc01  inc     esi
0x18000cc03  cmp     esi, 64h ; 'd'
0x18000cc06  jge     short loc_18000CC10
0x18000cc08  test    ebx, ebx
0x18000cc0a  jz      loc_18000CABF
0x18000cc10  test    ebx, ebx
0x18000cc12  cmovz   ebx, edi
0x18000cc15  mov     eax, ebx
0x18000cc17  mov     rcx, [rbp+0F90h+var_40]
0x18000cc1e  xor     rcx, rsp; StackCookie
0x18000cc21  call    __security_check_cookie
0x18000cc26  add     rsp, 1068h
0x18000cc2d  pop     r14
0x18000cc2f  pop     r12
0x18000cc31  pop     rdi
0x18000cc32  pop     rsi
0x18000cc33  pop     rbx
0x18000cc34  pop     rbp
0x18000cc35  retn
```
