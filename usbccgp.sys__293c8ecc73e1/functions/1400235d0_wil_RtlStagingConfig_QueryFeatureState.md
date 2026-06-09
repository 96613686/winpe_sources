# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1400235d0`
- end: `0x14002368b`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140011cc4`

## callees

- `0x140014d10`
- `0x1400235d0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140023610`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140023610`

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
0x1400235d0  mov     r11, rsp
0x1400235d3  push    rbx
0x1400235d4  sub     rsp, 40h
0x1400235d8  mov     rax, cs:__security_cookie
0x1400235df  xor     rax, rsp
0x1400235e2  mov     [rsp+48h+var_10], rax
0x1400235e7  mov     eax, edx
0x1400235e9  mov     qword ptr [r11-28h], 0
0x1400235f1  mov     rbx, rcx
0x1400235f4  lea     r9, [r11-20h]
0x1400235f8  xor     ecx, ecx
0x1400235fa  xor     edx, edx
0x1400235fc  test    r8d, r8d
0x1400235ff  mov     [r11-20h], rcx
0x140023603  mov     [rsp+48h+var_18], ecx
0x140023607  lea     r8, [r11-28h]
0x14002360b  setz    dl
0x14002360e  mov     ecx, eax
0x140023610  call    cs:__imp_RtlQueryFeatureConfiguration
0x140023617  nop     dword ptr [rax+rax+00h]
0x14002361c  test    eax, eax
0x14002361e  jnz     short loc_14002365B
0x140023620  mov     ecx, [rsp+48h+var_1C]
0x140023624  mov     edx, 1
0x140023629  mov     eax, ecx
0x14002362b  shr     eax, 4
0x14002362e  and     eax, 3
0x140023631  mov     [rbx], eax
0x140023633  mov     eax, ecx
0x140023635  shr     eax, 8
0x140023638  and     al, 3Fh
0x14002363a  mov     [rbx+4], al
0x14002363d  mov     eax, [rsp+48h+var_18]
0x140023641  mov     [rbx+0Ch], eax
0x140023644  mov     eax, ecx
0x140023646  shr     eax, 0Eh
0x140023649  and     eax, 3
0x14002364c  mov     [rbx+8], eax
0x14002364f  mov     eax, ecx
0x140023651  shr     eax, 6
0x140023654  and     eax, edx
0x140023656  mov     [rbx+14h], eax
0x140023659  jmp     short loc_14002366D
0x14002365b  xor     edx, edx
0x14002365d  cmp     eax, 117h
0x140023662  jnz     short loc_140023675
0x140023664  mov     ecx, [rsp+48h+var_1C]
0x140023668  mov     edx, 1
0x14002366d  shr     ecx, 7
0x140023670  and     ecx, edx
0x140023672  mov     [rbx+10h], ecx
0x140023675  mov     eax, edx
0x140023677  mov     rcx, [rsp+48h+var_10]
0x14002367c  xor     rcx, rsp; StackCookie
0x14002367f  call    __security_check_cookie
0x140023684  add     rsp, 40h
0x140023688  pop     rbx
0x140023689  retn
```
