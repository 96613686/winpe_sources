# TpmStack::Entropy20ProvidedCallback(_TPM20RM_COMPLETION *)

- ea: `0x140014d20`
- end: `0x140014e88`
- name: `?Entropy20ProvidedCallback@TpmStack@@CAXPEAU_TPM20RM_COMPLETION@@@Z`
- size: `360`
- prototype: `void __fastcall(struct _TPM20RM_COMPLETION *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400078b8`
- `0x140014d20`
- `0x14001a770`
- `0x1400454a0`

## import_xrefs

- `cng!EntropyProvideData` at `0x140014e05`
- `cng!EntropyProvideData` at `0x140014e05`

## pseudocode

```c
void __fastcall TpmStack::Entropy20ProvidedCallback(struct _TPM20RM_COMPLETION *a1)
{
  char *v1; // rbx
  __int64 v2; // r9
  SIZE_T v3; // rdi
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx

  v1 = (char *)a1 - 8;
  if ( *((_DWORD *)a1 + 8)
    || (v2 = *((unsigned int *)a1 + 9), (unsigned int)(v2 - 12) > 0x80)
    || *(_DWORD *)(v1 + 50) != _byteswap_ulong(v2)
    || *((_WORD *)v1 + 24) != 384
    || *(_DWORD *)(v1 + 54) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
      goto LABEL_23;
    v7 = 16;
LABEL_22:
    WPP_SF_(v6->AttachedDevice, v7, WPP_b13eeff4b5e83ce555d199d430c2416d_Traceguids);
    goto LABEL_23;
  }
  v3 = (unsigned __int16)__ROR2__(*((_WORD *)v1 + 29), 8);
  if ( (_DWORD)v3 + 12 != (_DWORD)v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v5 = 17;
LABEL_10:
      WPP_SF_Dd(v4->AttachedDevice, v5, WPP_b13eeff4b5e83ce555d199d430c2416d_Traceguids, v2);
      goto LABEL_23;
    }
    goto LABEL_23;
  }
  if ( !(_DWORD)v3 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
      goto LABEL_23;
    v7 = 18;
    goto LABEL_22;
  }
  if ( EntropyProvideData(*(ENTROPY_SOURCE_HANDLE *)(*(_QWORD *)v1 + 24LL), (PCBYTE)v1 + 60, v3, 8000 * v3) < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v5 = 19;
      v2 = (unsigned int)v3;
      goto LABEL_10;
    }
  }
LABEL_23:
  TpmFree(v1);
}

```

## disassembly

```asm
0x140014d20  mov     [rsp+arg_0], rbx
0x140014d25  push    rdi
0x140014d26  sub     rsp, 30h
0x140014d2a  cmp     dword ptr [rcx+20h], 0
0x140014d2e  lea     rbx, [rcx-8]
0x140014d32  jnz     loc_140014E45
0x140014d38  mov     r9d, [rcx+24h]
0x140014d3c  lea     eax, [r9-0Ch]
0x140014d40  cmp     eax, 80h
0x140014d45  ja      loc_140014E45
0x140014d4b  mov     eax, r9d
0x140014d4e  bswap   eax
0x140014d50  cmp     [rbx+32h], eax
0x140014d53  jnz     loc_140014E45
0x140014d59  mov     eax, 180h
0x140014d5e  cmp     [rbx+30h], ax
0x140014d62  jnz     loc_140014E45
0x140014d68  cmp     dword ptr [rbx+36h], 0
0x140014d6c  jnz     loc_140014E45
0x140014d72  movzx   eax, word ptr [rbx+3Ah]
0x140014d76  ror     ax, 8
0x140014d7a  movzx   edi, ax
0x140014d7d  lea     eax, [rdi+0Ch]
0x140014d80  cmp     eax, r9d
0x140014d83  jz      short loc_140014DC5
0x140014d85  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140014d8c  lea     rax, WPP_GLOBAL_Control
0x140014d93  cmp     rcx, rax
0x140014d96  jz      loc_140014E74
0x140014d9c  mov     eax, [rcx+2Ch]
0x140014d9f  test    al, 1
0x140014da1  jz      loc_140014E74
0x140014da7  mov     edx, 11h
0x140014dac  mov     [rsp+38h+var_18], edi
0x140014db0  mov     rcx, [rcx+18h]
0x140014db4  lea     r8, WPP_b13eeff4b5e83ce555d199d430c2416d_Traceguids
0x140014dbb  call    WPP_SF_Dd
0x140014dc0  jmp     loc_140014E74
0x140014dc5  test    edi, edi
0x140014dc7  jnz     short loc_140014DF0
0x140014dc9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140014dd0  lea     rax, WPP_GLOBAL_Control
0x140014dd7  cmp     rcx, rax
0x140014dda  jz      loc_140014E74
0x140014de0  mov     eax, [rcx+2Ch]
0x140014de3  test    al, 2
0x140014de5  jz      loc_140014E74
0x140014deb  lea     edx, [rdi+12h]
0x140014dee  jmp     short loc_140014E64
0x140014df0  mov     rcx, [rbx]
0x140014df3  lea     rdx, [rbx+3Ch]; pbData
0x140014df7  imul    r9d, edi, 1F40h; entropyEstimateInMilliBits
0x140014dfe  mov     r8, rdi; cbData
0x140014e01  mov     rcx, [rcx+18h]; hEntropySource
0x140014e05  call    cs:__imp_EntropyProvideData
0x140014e0c  nop     dword ptr [rax+rax+00h]
0x140014e11  mov     r8d, eax
0x140014e14  test    eax, eax
0x140014e16  jns     short loc_140014E74
0x140014e18  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140014e1f  lea     rax, WPP_GLOBAL_Control
0x140014e26  cmp     rcx, rax
0x140014e29  jz      short loc_140014E74
0x140014e2b  mov     edx, [rcx+2Ch]
0x140014e2e  test    dl, 1
0x140014e31  jz      short loc_140014E74
0x140014e33  mov     edx, 13h
0x140014e38  mov     [rsp+38h+var_18], r8d
0x140014e3d  mov     r9d, edi
0x140014e40  jmp     loc_140014DB0
0x140014e45  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140014e4c  lea     rax, WPP_GLOBAL_Control
0x140014e53  cmp     rcx, rax
0x140014e56  jz      short loc_140014E74
0x140014e58  mov     eax, [rcx+2Ch]
0x140014e5b  test    al, 2
0x140014e5d  jz      short loc_140014E74
0x140014e5f  mov     edx, 10h
0x140014e64  mov     rcx, [rcx+18h]
0x140014e68  lea     r8, WPP_b13eeff4b5e83ce555d199d430c2416d_Traceguids
0x140014e6f  call    WPP_SF_
0x140014e74  mov     rcx, rbx; void *
0x140014e77  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x140014e7c  mov     rbx, [rsp+38h+arg_0]
0x140014e81  add     rsp, 30h
0x140014e85  pop     rdi
0x140014e86  retn
```
