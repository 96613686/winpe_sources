# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x140054a30`
- end: `0x140054aeb`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001eb00`

## callees

- `0x140040a30`
- `0x140054a30`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140054a70`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140054a70`

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
0x140054a30  mov     r11, rsp
0x140054a33  push    rbx
0x140054a34  sub     rsp, 40h
0x140054a38  mov     rax, cs:__security_cookie
0x140054a3f  xor     rax, rsp
0x140054a42  mov     [rsp+48h+var_10], rax
0x140054a47  mov     eax, edx
0x140054a49  mov     qword ptr [r11-28h], 0
0x140054a51  mov     rbx, rcx
0x140054a54  lea     r9, [r11-20h]
0x140054a58  xor     ecx, ecx
0x140054a5a  xor     edx, edx
0x140054a5c  test    r8d, r8d
0x140054a5f  mov     [r11-20h], rcx
0x140054a63  mov     [rsp+48h+var_18], ecx
0x140054a67  lea     r8, [r11-28h]
0x140054a6b  setz    dl
0x140054a6e  mov     ecx, eax
0x140054a70  call    cs:__imp_RtlQueryFeatureConfiguration
0x140054a77  nop     dword ptr [rax+rax+00h]
0x140054a7c  test    eax, eax
0x140054a7e  jnz     short loc_140054ABB
0x140054a80  mov     ecx, [rsp+48h+var_1C]
0x140054a84  mov     edx, 1
0x140054a89  mov     eax, ecx
0x140054a8b  shr     eax, 4
0x140054a8e  and     eax, 3
0x140054a91  mov     [rbx], eax
0x140054a93  mov     eax, ecx
0x140054a95  shr     eax, 8
0x140054a98  and     al, 3Fh
0x140054a9a  mov     [rbx+4], al
0x140054a9d  mov     eax, [rsp+48h+var_18]
0x140054aa1  mov     [rbx+0Ch], eax
0x140054aa4  mov     eax, ecx
0x140054aa6  shr     eax, 0Eh
0x140054aa9  and     eax, 3
0x140054aac  mov     [rbx+8], eax
0x140054aaf  mov     eax, ecx
0x140054ab1  shr     eax, 6
0x140054ab4  and     eax, edx
0x140054ab6  mov     [rbx+14h], eax
0x140054ab9  jmp     short loc_140054ACD
0x140054abb  xor     edx, edx
0x140054abd  cmp     eax, 117h
0x140054ac2  jnz     short loc_140054AD5
0x140054ac4  mov     ecx, [rsp+48h+var_1C]
0x140054ac8  mov     edx, 1
0x140054acd  shr     ecx, 7
0x140054ad0  and     ecx, edx
0x140054ad2  mov     [rbx+10h], ecx
0x140054ad5  mov     eax, edx
0x140054ad7  mov     rcx, [rsp+48h+var_10]
0x140054adc  xor     rcx, rsp; StackCookie
0x140054adf  call    __security_check_cookie
0x140054ae4  add     rsp, 40h
0x140054ae8  pop     rbx
0x140054ae9  retn
```
