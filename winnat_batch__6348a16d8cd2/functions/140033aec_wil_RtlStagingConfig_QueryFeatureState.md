# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x140033aec`
- end: `0x140033ba7`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140017e6c`

## callees

- `0x14001ede0`
- `0x140033aec`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140033b2c`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140033b2c`

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
0x140033aec  mov     r11, rsp
0x140033aef  push    rbx
0x140033af0  sub     rsp, 40h
0x140033af4  mov     rax, cs:__security_cookie
0x140033afb  xor     rax, rsp
0x140033afe  mov     [rsp+48h+var_10], rax
0x140033b03  mov     eax, edx
0x140033b05  mov     qword ptr [r11-28h], 0
0x140033b0d  mov     rbx, rcx
0x140033b10  lea     r9, [r11-20h]
0x140033b14  xor     ecx, ecx
0x140033b16  xor     edx, edx
0x140033b18  test    r8d, r8d
0x140033b1b  mov     [r11-20h], rcx
0x140033b1f  mov     [rsp+48h+var_18], ecx
0x140033b23  lea     r8, [r11-28h]
0x140033b27  setz    dl
0x140033b2a  mov     ecx, eax
0x140033b2c  call    cs:__imp_RtlQueryFeatureConfiguration
0x140033b33  nop     dword ptr [rax+rax+00h]
0x140033b38  test    eax, eax
0x140033b3a  jnz     short loc_140033B77
0x140033b3c  mov     ecx, [rsp+48h+var_1C]
0x140033b40  mov     edx, 1
0x140033b45  mov     eax, ecx
0x140033b47  shr     eax, 4
0x140033b4a  and     eax, 3
0x140033b4d  mov     [rbx], eax
0x140033b4f  mov     eax, ecx
0x140033b51  shr     eax, 8
0x140033b54  and     al, 3Fh
0x140033b56  mov     [rbx+4], al
0x140033b59  mov     eax, [rsp+48h+var_18]
0x140033b5d  mov     [rbx+0Ch], eax
0x140033b60  mov     eax, ecx
0x140033b62  shr     eax, 0Eh
0x140033b65  and     eax, 3
0x140033b68  mov     [rbx+8], eax
0x140033b6b  mov     eax, ecx
0x140033b6d  shr     eax, 6
0x140033b70  and     eax, edx
0x140033b72  mov     [rbx+14h], eax
0x140033b75  jmp     short loc_140033B89
0x140033b77  xor     edx, edx
0x140033b79  cmp     eax, 117h
0x140033b7e  jnz     short loc_140033B91
0x140033b80  mov     ecx, [rsp+48h+var_1C]
0x140033b84  mov     edx, 1
0x140033b89  shr     ecx, 7
0x140033b8c  and     ecx, edx
0x140033b8e  mov     [rbx+10h], ecx
0x140033b91  mov     eax, edx
0x140033b93  mov     rcx, [rsp+48h+var_10]
0x140033b98  xor     rcx, rsp; StackCookie
0x140033b9b  call    __security_check_cookie
0x140033ba0  add     rsp, 40h
0x140033ba4  pop     rbx
0x140033ba5  retn
```
