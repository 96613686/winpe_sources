# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000c930`
- end: `0x18000cafa`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000a540`

## callees

- `0x18000c930`
- `0x18000cb60`
- `0x18000cbd8`
- `0x18000f9da`
- `0x18000fa00`
- `0x18000fa90`

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
        v9 = v7 / 0xC;
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
          if ( (unsigned __int64)v7 + 12 <= 0x1000 )
          {
            v7 += 12;
            *(_QWORD *)v11 = *(_QWORD *)v8;
            ++v9;
            v11[2] = *(_DWORD *)(v8 + 8);
            v15 = v7;
          }
LABEL_15:
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
0x18000c930  push    rbp
0x18000c932  push    rbx
0x18000c933  push    rsi
0x18000c934  push    rdi
0x18000c935  push    r12
0x18000c937  push    r14
0x18000c939  lea     rbp, [rsp-0F68h]
0x18000c941  mov     eax, 1068h
0x18000c946  call    _alloca_probe
0x18000c94b  sub     rsp, rax
0x18000c94e  mov     rax, cs:__security_cookie
0x18000c955  xor     rax, rsp
0x18000c958  mov     [rbp+0F90h+var_40], rax
0x18000c95f  mov     rax, [rcx+8]
0x18000c963  xor     ebx, ebx
0x18000c965  sub     rax, [rcx]
0x18000c968  xor     edi, edi
0x18000c96a  mov     r14, rcx
0x18000c96d  cmp     rax, 0Ch
0x18000c971  jb      loc_18000CAD4
0x18000c977  xor     esi, esi
0x18000c979  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000c983  xor     edx, edx; Val
0x18000c985  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000c98a  mov     r8d, 1000h; Size
0x18000c990  call    memset_0
0x18000c995  lea     rax, [rsp+1090h+var_1050]
0x18000c99a  mov     [rsp+1090h+var_1050], 1000h
0x18000c9a2  mov     [rsp+1090h+var_1068], rax
0x18000c9a7  lea     r9, [rsp+1090h+var_104C]
0x18000c9ac  lea     rax, [rsp+1090h+var_1040]
0x18000c9b1  mov     [rsp+1090h+var_104C], 0
0x18000c9b9  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000c9c0  mov     [rsp+1090h+var_1070], rax
0x18000c9c5  call    wil_details_NtQueryWnfStateData
0x18000c9ca  mov     ebx, eax
0x18000c9cc  test    eax, eax
0x18000c9ce  jnz     loc_18000CABD
0x18000c9d4  mov     r9d, [rsp+1090h+var_1050]
0x18000c9d9  mov     rax, r12
0x18000c9dc  mul     r9
0x18000c9df  shr     rdx, 3
0x18000c9e3  lea     rcx, [rdx+rdx*2]
0x18000c9e7  shl     rcx, 2
0x18000c9eb  cmp     r9, rcx
0x18000c9ee  jz      short loc_18000C9F8
0x18000c9f0  xor     r9d, r9d
0x18000c9f3  mov     [rsp+1090h+var_1050], r9d
0x18000c9f8  mov     r8, [r14]
0x18000c9fb  mov     rax, r12
0x18000c9fe  mov     ecx, r9d
0x18000ca01  mul     rcx
0x18000ca04  mov     rcx, [r14+8]
0x18000ca08  mov     rax, r12
0x18000ca0b  mov     r11, rdx
0x18000ca0e  sub     rcx, r8
0x18000ca11  mul     rcx
0x18000ca14  shr     r11, 3
0x18000ca18  shr     rdx, 3
0x18000ca1c  lea     rax, [rdx+rdx*2]
0x18000ca20  lea     rdi, [r8+rax*4]
0x18000ca24  jmp     short loc_18000CA92
0x18000ca26  mov     eax, r11d
0x18000ca29  lea     r10, [rsp+1090h+var_1040]
0x18000ca2e  lea     rcx, [rax+rax*2]
0x18000ca32  lea     r10, [r10+rcx*4]
0x18000ca36  cmp     rdx, r10
0x18000ca39  jz      short loc_18000CA61
0x18000ca3b  mov     eax, [r8]
0x18000ca3e  cmp     [rdx], eax
0x18000ca40  jnz     short loc_18000CA4D
0x18000ca42  movzx   eax, word ptr [r8+4]
0x18000ca47  cmp     [rdx+4], ax
0x18000ca4b  jz      short loc_18000CA53
0x18000ca4d  add     rdx, 0Ch
0x18000ca51  jmp     short loc_18000CA36
0x18000ca53  mov     eax, [r8+8]
0x18000ca57  add     [rdx+8], eax
0x18000ca5a  mov     r9d, [rsp+1090h+var_1050]
0x18000ca5f  jmp     short loc_18000CA8E
0x18000ca61  mov     eax, r9d
0x18000ca64  add     rax, 0Ch
0x18000ca68  cmp     rax, 1000h
0x18000ca6e  ja      short loc_18000CA8E
0x18000ca70  movsd   xmm0, qword ptr [r8]
0x18000ca75  add     r9d, 0Ch
0x18000ca79  movsd   qword ptr [r10], xmm0
0x18000ca7e  inc     r11d
0x18000ca81  mov     eax, [r8+8]
0x18000ca85  mov     [r10+8], eax
0x18000ca89  mov     [rsp+1090h+var_1050], r9d
0x18000ca8e  add     r8, 0Ch
0x18000ca92  lea     rdx, [rsp+1090h+var_1040]
0x18000ca97  cmp     r8, rdi
0x18000ca9a  jnz     short loc_18000CA26
0x18000ca9c  mov     eax, [rsp+1090h+var_104C]
0x18000caa0  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000caa7  mov     [rsp+1090h+var_1060], 1
0x18000caaf  mov     r8d, r9d
0x18000cab2  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000cab6  call    wil_details_NtUpdateWnfStateData
0x18000cabb  mov     edi, eax
0x18000cabd  cmp     edi, 0C0000001h
0x18000cac3  jnz     short loc_18000CAD4
0x18000cac5  inc     esi
0x18000cac7  cmp     esi, 64h ; 'd'
0x18000caca  jge     short loc_18000CAD4
0x18000cacc  test    ebx, ebx
0x18000cace  jz      loc_18000C983
0x18000cad4  test    ebx, ebx
0x18000cad6  cmovz   ebx, edi
0x18000cad9  mov     eax, ebx
0x18000cadb  mov     rcx, [rbp+0F90h+var_40]
0x18000cae2  xor     rcx, rsp; StackCookie
0x18000cae5  call    __security_check_cookie
0x18000caea  add     rsp, 1068h
0x18000caf1  pop     r14
0x18000caf3  pop     r12
0x18000caf5  pop     rdi
0x18000caf6  pop     rsi
0x18000caf7  pop     rbx
0x18000caf8  pop     rbp
0x18000caf9  retn
```
