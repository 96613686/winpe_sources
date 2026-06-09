# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18001cb7c`
- end: `0x18001cd52`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180017890`

## callees

- `0x18001cb7c`
- `0x18001ce40`
- `0x18001ceb8`
- `0x18001d1da`
- `0x18001d210`
- `0x18001d2a0`

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
0x18001cb7c  push    rbp
0x18001cb7e  push    rbx
0x18001cb7f  push    rsi
0x18001cb80  push    rdi
0x18001cb81  push    r12
0x18001cb83  push    r14
0x18001cb85  lea     rbp, [rsp-0F68h]
0x18001cb8d  mov     eax, 1068h
0x18001cb92  call    _alloca_probe
0x18001cb97  sub     rsp, rax
0x18001cb9a  mov     rax, cs:__security_cookie
0x18001cba1  xor     rax, rsp
0x18001cba4  mov     [rbp+0F90h+var_40], rax
0x18001cbab  mov     rax, [rcx+8]
0x18001cbaf  xor     ebx, ebx
0x18001cbb1  sub     rax, [rcx]
0x18001cbb4  xor     edi, edi
0x18001cbb6  mov     r14, rcx
0x18001cbb9  cmp     rax, 0Ch
0x18001cbbd  jb      loc_18001CD1D
0x18001cbc3  xor     esi, esi
0x18001cbc5  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001cbcf  xor     edx, edx; Val
0x18001cbd1  lea     rcx, [rsp+1090h+var_1040]; void *
0x18001cbd6  mov     r8d, 1000h; Size
0x18001cbdc  call    memset_0
0x18001cbe1  lea     rax, [rsp+1090h+var_1050]
0x18001cbe6  mov     [rsp+1090h+var_1050], 1000h
0x18001cbee  mov     [rsp+1090h+var_1068], rax
0x18001cbf3  lea     r9, [rsp+1090h+var_104C]
0x18001cbf8  lea     rax, [rsp+1090h+var_1040]
0x18001cbfd  mov     [rsp+1090h+var_104C], 0
0x18001cc05  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001cc0c  mov     [rsp+1090h+var_1070], rax
0x18001cc11  call    wil_details_NtQueryWnfStateData
0x18001cc16  mov     ebx, eax
0x18001cc18  test    eax, eax
0x18001cc1a  jnz     loc_18001CD06
0x18001cc20  mov     r9d, [rsp+1090h+var_1050]
0x18001cc25  mov     rax, r12
0x18001cc28  mul     r9
0x18001cc2b  shr     rdx, 3
0x18001cc2f  lea     rcx, [rdx+rdx*2]
0x18001cc33  shl     rcx, 2
0x18001cc37  cmp     r9, rcx
0x18001cc3a  jz      short loc_18001CC44
0x18001cc3c  xor     r9d, r9d
0x18001cc3f  mov     [rsp+1090h+var_1050], r9d
0x18001cc44  mov     r8, [r14]
0x18001cc47  mov     rax, r12
0x18001cc4a  mov     ecx, r9d
0x18001cc4d  mul     rcx
0x18001cc50  mov     rcx, [r14+8]
0x18001cc54  mov     rax, r12
0x18001cc57  mov     r10, rdx
0x18001cc5a  sub     rcx, r8
0x18001cc5d  mul     rcx
0x18001cc60  shr     r10, 3
0x18001cc64  shr     rdx, 3
0x18001cc68  lea     rax, [rdx+rdx*2]
0x18001cc6c  lea     rdi, [r8+rax*4]
0x18001cc70  jmp     short loc_18001CCDB
0x18001cc72  mov     eax, r10d
0x18001cc75  lea     rcx, [rax+rax*2]
0x18001cc79  lea     rdx, [rdx+rcx*4]
0x18001cc7d  lea     rax, [rsp+1090h+var_1040]
0x18001cc82  cmp     rax, rdx
0x18001cc85  jz      short loc_18001CCAC
0x18001cc87  mov     r11d, [r8]
0x18001cc8a  lea     rcx, [rsp+1090h+var_1040]
0x18001cc8f  cmp     [rcx], r11d
0x18001cc92  jnz     short loc_18001CCA3
0x18001cc94  movzx   eax, word ptr [r8+4]
0x18001cc99  cmp     [rcx+4], ax
0x18001cc9d  jz      loc_18001CD44
0x18001cca3  add     rcx, 0Ch
0x18001cca7  cmp     rcx, rdx
0x18001ccaa  jnz     short loc_18001CC8F
0x18001ccac  mov     eax, r9d
0x18001ccaf  add     rax, 0Ch
0x18001ccb3  cmp     rax, 1000h
0x18001ccb9  ja      short loc_18001CCD7
0x18001ccbb  movsd   xmm0, qword ptr [r8]
0x18001ccc0  add     r9d, 0Ch
0x18001ccc4  movsd   qword ptr [rdx], xmm0
0x18001ccc8  inc     r10d
0x18001cccb  mov     eax, [r8+8]
0x18001cccf  mov     [rdx+8], eax
0x18001ccd2  mov     [rsp+1090h+var_1050], r9d
0x18001ccd7  add     r8, 0Ch
0x18001ccdb  lea     rdx, [rsp+1090h+var_1040]
0x18001cce0  cmp     r8, rdi
0x18001cce3  jnz     short loc_18001CC72
0x18001cce5  mov     eax, [rsp+1090h+var_104C]
0x18001cce9  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001ccf0  mov     [rsp+1090h+var_1060], 1
0x18001ccf8  mov     r8d, r9d
0x18001ccfb  mov     dword ptr [rsp+1090h+var_1068], eax
0x18001ccff  call    wil_details_NtUpdateWnfStateData
0x18001cd04  mov     edi, eax
0x18001cd06  cmp     edi, 0C0000001h
0x18001cd0c  jnz     short loc_18001CD1D
0x18001cd0e  inc     esi
0x18001cd10  cmp     esi, 64h ; 'd'
0x18001cd13  jge     short loc_18001CD1D
0x18001cd15  test    ebx, ebx
0x18001cd17  jz      loc_18001CBCF
0x18001cd1d  test    ebx, ebx
0x18001cd1f  cmovz   ebx, edi
0x18001cd22  mov     eax, ebx
0x18001cd24  mov     rcx, [rbp+0F90h+var_40]
0x18001cd2b  xor     rcx, rsp; StackCookie
0x18001cd2e  call    __security_check_cookie
0x18001cd33  add     rsp, 1068h
0x18001cd3a  pop     r14
0x18001cd3c  pop     r12
0x18001cd3e  pop     rdi
0x18001cd3f  pop     rsi
0x18001cd40  pop     rbx
0x18001cd41  pop     rbp
0x18001cd42  retn
0x18001cd44  mov     eax, [r8+8]
0x18001cd48  add     [rcx+8], eax
0x18001cd4b  mov     r9d, [rsp+1090h+var_1050]
0x18001cd50  jmp     short loc_18001CCD7
```
