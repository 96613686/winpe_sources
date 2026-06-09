# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x140031080`
- end: `0x14003113b`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140011908`

## callees

- `0x14001bc30`
- `0x140031080`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400310c0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400310c0`

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
0x140031080  mov     r11, rsp
0x140031083  push    rbx
0x140031084  sub     rsp, 40h
0x140031088  mov     rax, cs:__security_cookie
0x14003108f  xor     rax, rsp
0x140031092  mov     [rsp+48h+var_10], rax
0x140031097  mov     eax, edx
0x140031099  mov     qword ptr [r11-28h], 0
0x1400310a1  mov     rbx, rcx
0x1400310a4  lea     r9, [r11-20h]
0x1400310a8  xor     ecx, ecx
0x1400310aa  xor     edx, edx
0x1400310ac  test    r8d, r8d
0x1400310af  mov     [r11-20h], rcx
0x1400310b3  mov     [rsp+48h+var_18], ecx
0x1400310b7  lea     r8, [r11-28h]
0x1400310bb  setz    dl
0x1400310be  mov     ecx, eax
0x1400310c0  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400310c7  nop     dword ptr [rax+rax+00h]
0x1400310cc  test    eax, eax
0x1400310ce  jnz     short loc_14003110B
0x1400310d0  mov     ecx, [rsp+48h+var_1C]
0x1400310d4  mov     edx, 1
0x1400310d9  mov     eax, ecx
0x1400310db  shr     eax, 4
0x1400310de  and     eax, 3
0x1400310e1  mov     [rbx], eax
0x1400310e3  mov     eax, ecx
0x1400310e5  shr     eax, 8
0x1400310e8  and     al, 3Fh
0x1400310ea  mov     [rbx+4], al
0x1400310ed  mov     eax, [rsp+48h+var_18]
0x1400310f1  mov     [rbx+0Ch], eax
0x1400310f4  mov     eax, ecx
0x1400310f6  shr     eax, 0Eh
0x1400310f9  and     eax, 3
0x1400310fc  mov     [rbx+8], eax
0x1400310ff  mov     eax, ecx
0x140031101  shr     eax, 6
0x140031104  and     eax, edx
0x140031106  mov     [rbx+14h], eax
0x140031109  jmp     short loc_14003111D
0x14003110b  xor     edx, edx
0x14003110d  cmp     eax, 117h
0x140031112  jnz     short loc_140031125
0x140031114  mov     ecx, [rsp+48h+var_1C]
0x140031118  mov     edx, 1
0x14003111d  shr     ecx, 7
0x140031120  and     ecx, edx
0x140031122  mov     [rbx+10h], ecx
0x140031125  mov     eax, edx
0x140031127  mov     rcx, [rsp+48h+var_10]
0x14003112c  xor     rcx, rsp; StackCookie
0x14003112f  call    __security_check_cookie
0x140031134  add     rsp, 40h
0x140031138  pop     rbx
0x140031139  retn
```
