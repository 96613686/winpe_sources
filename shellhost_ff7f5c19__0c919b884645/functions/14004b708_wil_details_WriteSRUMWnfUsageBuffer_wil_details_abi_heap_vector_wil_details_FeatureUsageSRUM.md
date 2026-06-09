# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14004b708`
- end: `0x14004b8d2`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140044b40`

## callees

- `0x14000f7e0`
- `0x14001062c`
- `0x14004b708`
- `0x14004bbec`
- `0x14004bc64`
- `0x140060520`

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
0x14004b708  push    rbp
0x14004b70a  push    rbx
0x14004b70b  push    rsi
0x14004b70c  push    rdi
0x14004b70d  push    r12
0x14004b70f  push    r14
0x14004b711  lea     rbp, [rsp-0F68h]
0x14004b719  mov     eax, 1068h
0x14004b71e  call    _alloca_probe
0x14004b723  sub     rsp, rax
0x14004b726  mov     rax, cs:__security_cookie
0x14004b72d  xor     rax, rsp
0x14004b730  mov     [rbp+0F90h+var_40], rax
0x14004b737  mov     rax, [rcx+8]
0x14004b73b  xor     ebx, ebx
0x14004b73d  sub     rax, [rcx]
0x14004b740  xor     edi, edi
0x14004b742  mov     r14, rcx
0x14004b745  cmp     rax, 0Ch
0x14004b749  jb      loc_14004B8AC
0x14004b74f  xor     esi, esi
0x14004b751  mov     r12, 0AAAAAAAAAAAAAAABh
0x14004b75b  xor     edx, edx; Val
0x14004b75d  lea     rcx, [rsp+1090h+var_1040]; void *
0x14004b762  mov     r8d, 1000h; Size
0x14004b768  call    memset_0
0x14004b76d  lea     rax, [rsp+1090h+var_1050]
0x14004b772  mov     [rsp+1090h+var_1050], 1000h
0x14004b77a  mov     [rsp+1090h+var_1068], rax
0x14004b77f  lea     r9, [rsp+1090h+var_104C]
0x14004b784  lea     rax, [rsp+1090h+var_1040]
0x14004b789  mov     [rsp+1090h+var_104C], 0
0x14004b791  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14004b798  mov     [rsp+1090h+var_1070], rax
0x14004b79d  call    wil_details_NtQueryWnfStateData
0x14004b7a2  mov     ebx, eax
0x14004b7a4  test    eax, eax
0x14004b7a6  jnz     loc_14004B895
0x14004b7ac  mov     r9d, [rsp+1090h+var_1050]
0x14004b7b1  mov     rax, r12
0x14004b7b4  mul     r9
0x14004b7b7  shr     rdx, 3
0x14004b7bb  lea     rcx, [rdx+rdx*2]
0x14004b7bf  shl     rcx, 2
0x14004b7c3  cmp     r9, rcx
0x14004b7c6  jz      short loc_14004B7D0
0x14004b7c8  xor     r9d, r9d
0x14004b7cb  mov     [rsp+1090h+var_1050], r9d
0x14004b7d0  mov     r8, [r14]
0x14004b7d3  mov     rax, r12
0x14004b7d6  mov     ecx, r9d
0x14004b7d9  mul     rcx
0x14004b7dc  mov     rcx, [r14+8]
0x14004b7e0  mov     rax, r12
0x14004b7e3  mov     r11, rdx
0x14004b7e6  sub     rcx, r8
0x14004b7e9  mul     rcx
0x14004b7ec  shr     r11, 3
0x14004b7f0  shr     rdx, 3
0x14004b7f4  lea     rax, [rdx+rdx*2]
0x14004b7f8  lea     rdi, [r8+rax*4]
0x14004b7fc  jmp     short loc_14004B86A
0x14004b7fe  mov     eax, r11d
0x14004b801  lea     r10, [rsp+1090h+var_1040]
0x14004b806  lea     rcx, [rax+rax*2]
0x14004b80a  lea     r10, [r10+rcx*4]
0x14004b80e  cmp     rdx, r10
0x14004b811  jz      short loc_14004B839
0x14004b813  mov     eax, [r8]
0x14004b816  cmp     [rdx], eax
0x14004b818  jnz     short loc_14004B825
0x14004b81a  movzx   eax, word ptr [r8+4]
0x14004b81f  cmp     [rdx+4], ax
0x14004b823  jz      short loc_14004B82B
0x14004b825  add     rdx, 0Ch
0x14004b829  jmp     short loc_14004B80E
0x14004b82b  mov     eax, [r8+8]
0x14004b82f  add     [rdx+8], eax
0x14004b832  mov     r9d, [rsp+1090h+var_1050]
0x14004b837  jmp     short loc_14004B866
0x14004b839  mov     eax, r9d
0x14004b83c  add     rax, 0Ch
0x14004b840  cmp     rax, 1000h
0x14004b846  ja      short loc_14004B866
0x14004b848  movsd   xmm0, qword ptr [r8]
0x14004b84d  add     r9d, 0Ch
0x14004b851  movsd   qword ptr [r10], xmm0
0x14004b856  inc     r11d
0x14004b859  mov     eax, [r8+8]
0x14004b85d  mov     [r10+8], eax
0x14004b861  mov     [rsp+1090h+var_1050], r9d
0x14004b866  add     r8, 0Ch
0x14004b86a  lea     rdx, [rsp+1090h+var_1040]
0x14004b86f  cmp     r8, rdi
0x14004b872  jnz     short loc_14004B7FE
0x14004b874  mov     eax, [rsp+1090h+var_104C]
0x14004b878  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14004b87f  mov     [rsp+1090h+var_1060], 1
0x14004b887  mov     r8d, r9d
0x14004b88a  mov     dword ptr [rsp+1090h+var_1068], eax
0x14004b88e  call    wil_details_NtUpdateWnfStateData
0x14004b893  mov     edi, eax
0x14004b895  cmp     edi, 0C0000001h
0x14004b89b  jnz     short loc_14004B8AC
0x14004b89d  inc     esi
0x14004b89f  cmp     esi, 64h ; 'd'
0x14004b8a2  jge     short loc_14004B8AC
0x14004b8a4  test    ebx, ebx
0x14004b8a6  jz      loc_14004B75B
0x14004b8ac  test    ebx, ebx
0x14004b8ae  cmovz   ebx, edi
0x14004b8b1  mov     eax, ebx
0x14004b8b3  mov     rcx, [rbp+0F90h+var_40]
0x14004b8ba  xor     rcx, rsp; StackCookie
0x14004b8bd  call    __security_check_cookie
0x14004b8c2  add     rsp, 1068h
0x14004b8c9  pop     r14
0x14004b8cb  pop     r12
0x14004b8cd  pop     rdi
0x14004b8ce  pop     rsi
0x14004b8cf  pop     rbx
0x14004b8d0  pop     rbp
0x14004b8d1  retn
```
