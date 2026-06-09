# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x14004e5ec`
- end: `0x14004e6a7`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001ec8c`

## callees

- `0x140039740`
- `0x14004e5ec`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14004e62c`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14004e62c`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3)
{
  int v4; // eax
  unsigned int v5; // ecx
  unsigned int v6; // edx
  __int64 v8; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+28h] [rbp-20h] BYREF
  int v10; // [rsp+30h] [rbp-18h]

  v8 = 0;
  v9 = 0;
  v10 = 0;
  v4 = RtlQueryFeatureConfiguration(a2, a3 == 0, &v8, &v9);
  if ( !v4 )
  {
    v5 = HIDWORD(v9);
    v6 = 1;
    *(_DWORD *)a1 = (HIDWORD(v9) >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v5) & 0x3F;
    *(_DWORD *)(a1 + 12) = v10;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v5 >> 14;
    *(_DWORD *)(a1 + 20) = (v5 >> 6) & 1;
LABEL_5:
    *(_DWORD *)(a1 + 16) = (v5 >> 7) & 1;
    return v6;
  }
  v6 = 0;
  if ( v4 == 279 )
  {
    v5 = HIDWORD(v9);
    v6 = 1;
    goto LABEL_5;
  }
  return v6;
}

```

## disassembly

```asm
0x14004e5ec  mov     r11, rsp
0x14004e5ef  push    rbx
0x14004e5f0  sub     rsp, 40h
0x14004e5f4  mov     rax, cs:__security_cookie
0x14004e5fb  xor     rax, rsp
0x14004e5fe  mov     [rsp+48h+var_10], rax
0x14004e603  mov     eax, edx
0x14004e605  mov     qword ptr [r11-28h], 0
0x14004e60d  mov     rbx, rcx
0x14004e610  lea     r9, [r11-20h]
0x14004e614  xor     ecx, ecx
0x14004e616  xor     edx, edx
0x14004e618  test    r8d, r8d
0x14004e61b  mov     [r11-20h], rcx
0x14004e61f  mov     [rsp+48h+var_18], ecx
0x14004e623  lea     r8, [r11-28h]
0x14004e627  setz    dl
0x14004e62a  mov     ecx, eax
0x14004e62c  call    cs:__imp_RtlQueryFeatureConfiguration
0x14004e633  nop     dword ptr [rax+rax+00h]
0x14004e638  test    eax, eax
0x14004e63a  jnz     short loc_14004E677
0x14004e63c  mov     ecx, [rsp+48h+var_1C]
0x14004e640  mov     edx, 1
0x14004e645  mov     eax, ecx
0x14004e647  shr     eax, 4
0x14004e64a  and     eax, 3
0x14004e64d  mov     [rbx], eax
0x14004e64f  mov     eax, ecx
0x14004e651  shr     eax, 8
0x14004e654  and     al, 3Fh
0x14004e656  mov     [rbx+4], al
0x14004e659  mov     eax, [rsp+48h+var_18]
0x14004e65d  mov     [rbx+0Ch], eax
0x14004e660  mov     eax, ecx
0x14004e662  shr     eax, 0Eh
0x14004e665  and     eax, 3
0x14004e668  mov     [rbx+8], eax
0x14004e66b  mov     eax, ecx
0x14004e66d  shr     eax, 6
0x14004e670  and     eax, edx
0x14004e672  mov     [rbx+14h], eax
0x14004e675  jmp     short loc_14004E689
0x14004e677  xor     edx, edx
0x14004e679  cmp     eax, 117h
0x14004e67e  jnz     short loc_14004E691
0x14004e680  mov     ecx, [rsp+48h+var_1C]
0x14004e684  mov     edx, 1
0x14004e689  shr     ecx, 7
0x14004e68c  and     ecx, edx
0x14004e68e  mov     [rbx+10h], ecx
0x14004e691  mov     eax, edx
0x14004e693  mov     rcx, [rsp+48h+var_10]
0x14004e698  xor     rcx, rsp; StackCookie
0x14004e69b  call    __security_check_cookie
0x14004e6a0  add     rsp, 40h
0x14004e6a4  pop     rbx
0x14004e6a5  retn
```
