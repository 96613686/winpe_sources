# BuildPgmDataFileName

- ea: `0x140036b98`
- end: `0x140036da5`
- name: `BuildPgmDataFileName`
- size: `525`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140036dac`

## callees

- `0x140005068`
- `0x14001c878`
- `0x14001cdf0`
- `0x140036b98`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036c88`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036ca3`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036cf0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036d78`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036c88`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036ca3`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036cf0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036d78`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140036d09`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140036d45`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140036d09`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140036d45`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140036d21`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140036d5d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140036d21`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140036d5d`
- `ntoskrnl!ExAllocatePool2` at `0x140036bfb`
- `ntoskrnl!ExAllocatePool2` at `0x140036bfb`

## string_xrefs

- `0x140036c81`: `\SystemRoot\System32`

## pseudocode

```c
__int64 __fastcall BuildPgmDataFileName(__int64 a1)
{
  __int16 v2; // ax
  __int64 v3; // rdi
  __int64 Pool2; // rax
  PVOID v6; // rdx
  const WCHAR *v7; // rdx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned __int16 v10; // [rsp+20h] [rbp-40h] BYREF
  struct _UNICODE_STRING String; // [rsp+28h] [rbp-38h] BYREF
  char v12; // [rsp+38h] [rbp-28h] BYREF

  v10 = 0;
  String = 0;
  if ( (*((_DWORD *)pPgmRegistryConfig + 1) & 1) != 0 )
    v2 = *((_WORD *)pPgmRegistryConfig + 4) >> 1;
  else
    v2 = 21;
  v3 = (unsigned __int16)(v2 + 14);
  Pool2 = ExAllocatePool2(64, 2 * v3, 846030672);
  *(_QWORD *)(*(_QWORD *)(a1 + 40) + 24LL) = Pool2;
  if ( Pool2 )
  {
    v6 = pPgmRegistryConfig;
    *(_WORD *)(*(_QWORD *)(a1 + 40) + 18LL) = 2 * v3;
    *(_WORD *)(*(_QWORD *)(a1 + 40) + 16LL) = 0;
    if ( (*((_DWORD *)v6 + 1) & 1) != 0 )
      v7 = (const WCHAR *)*((_QWORD *)v6 + 2);
    else
      v7 = L"\\SystemRoot\\System32";
    RtlAppendUnicodeToString((PUNICODE_STRING)(*(_QWORD *)(a1 + 40) + 16LL), v7);
    RtlAppendUnicodeToString((PUNICODE_STRING)(*(_QWORD *)(a1 + 40) + 16LL), L"\\T");
    v8 = *(unsigned __int16 *)(a1 + 70);
    String.MaximumLength = 20;
    String.Buffer = (PWSTR)&v12;
    v9 = v8 % 0x64;
    v10 = v9;
    if ( (unsigned __int16)v9 < 0xAu )
    {
      RtlAppendUnicodeToString((PUNICODE_STRING)(*(_QWORD *)(a1 + 40) + 16LL), L"0");
      LOWORD(v9) = v10;
    }
    RtlIntegerToUnicodeString((unsigned __int16)v9, 0xAu, &String);
    RtlAppendUnicodeStringToString((PUNICODE_STRING)(*(_QWORD *)(a1 + 40) + 16LL), &String);
    GetRandomData(&v10, 2);
    RtlIntegerToUnicodeString(v10, 0xAu, &String);
    RtlAppendUnicodeStringToString((PUNICODE_STRING)(*(_QWORD *)(a1 + 40) + 16LL), &String);
    RtlAppendUnicodeToString((PUNICODE_STRING)(*(_QWORD *)(a1 + 40) + 16LL), L".PGM");
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids,
        (unsigned int)v3);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140036b98  mov     [rsp-8+arg_8], rbx
0x140036b9d  mov     [rsp-8+arg_10], rdi
0x140036ba2  push    rbp
0x140036ba3  mov     rbp, rsp
0x140036ba6  sub     rsp, 60h
0x140036baa  mov     rax, cs:__security_cookie
0x140036bb1  xor     rax, rsp
0x140036bb4  mov     [rbp+var_10], rax
0x140036bb8  xor     eax, eax
0x140036bba  mov     rbx, rcx
0x140036bbd  mov     rcx, cs:pPgmRegistryConfig
0x140036bc4  xorps   xmm0, xmm0
0x140036bc7  mov     [rbp+var_40], ax
0x140036bcb  movups  xmmword ptr [rbp+String.Length], xmm0
0x140036bcf  mov     eax, [rcx+4]
0x140036bd2  test    al, 1
0x140036bd4  jz      short loc_140036BDF
0x140036bd6  movzx   eax, word ptr [rcx+8]
0x140036bda  shr     ax, 1
0x140036bdd  jmp     short loc_140036BE4
0x140036bdf  mov     eax, 15h
0x140036be4  add     ax, 0Eh
0x140036be8  mov     ecx, 40h ; '@'
0x140036bed  movzx   edi, ax
0x140036bf0  mov     r8d, 326D6750h
0x140036bf6  mov     edx, edi
0x140036bf8  add     rdx, rdx
0x140036bfb  call    cs:__imp_ExAllocatePool2
0x140036c02  nop     dword ptr [rax+rax+00h]
0x140036c07  mov     rcx, [rbx+28h]
0x140036c0b  mov     [rcx+18h], rax
0x140036c0f  test    rax, rax
0x140036c12  jnz     short loc_140036C50
0x140036c14  mov     rcx, cs:WPP_GLOBAL_Control
0x140036c1b  lea     rax, WPP_GLOBAL_Control
0x140036c22  cmp     rcx, rax
0x140036c25  jz      short loc_140036C46
0x140036c27  mov     eax, [rcx+2Ch]
0x140036c2a  test    al, 2
0x140036c2c  jz      short loc_140036C46
0x140036c2e  mov     rcx, [rcx+18h]
0x140036c32  lea     r8, WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids
0x140036c39  mov     r9d, edi
0x140036c3c  mov     edx, 0Ah
0x140036c41  call    WPP_SF_d
0x140036c46  mov     eax, 0C000009Ah
0x140036c4b  jmp     loc_140036D86
0x140036c50  mov     rax, [rbx+28h]
0x140036c54  add     di, di
0x140036c57  mov     rdx, cs:pPgmRegistryConfig
0x140036c5e  mov     [rax+12h], di
0x140036c62  xor     eax, eax
0x140036c64  mov     rcx, [rbx+28h]
0x140036c68  mov     [rcx+10h], ax
0x140036c6c  mov     rcx, [rbx+28h]
0x140036c70  mov     eax, [rdx+4]
0x140036c73  add     rcx, 10h; Destination
0x140036c77  test    al, 1
0x140036c79  jz      short loc_140036C81
0x140036c7b  mov     rdx, [rdx+10h]
0x140036c7f  jmp     short loc_140036C88
0x140036c81  lea     rdx, Source; "\\SystemRoot\\System32"
0x140036c88  call    cs:__imp_RtlAppendUnicodeToString
0x140036c8f  nop     dword ptr [rax+rax+00h]
0x140036c94  mov     rcx, [rbx+28h]
0x140036c98  lea     rdx, aT; "\\T"
0x140036c9f  add     rcx, 10h; Destination
0x140036ca3  call    cs:__imp_RtlAppendUnicodeToString
0x140036caa  nop     dword ptr [rax+rax+00h]
0x140036caf  movzx   ecx, word ptr [rbx+46h]
0x140036cb3  mov     eax, 14h
0x140036cb8  mov     [rbp+String.MaximumLength], ax
0x140036cbc  mov     edi, 0Ah
0x140036cc1  lea     rax, [rbp+var_28]
0x140036cc5  mov     [rbp+String.Buffer], rax
0x140036cc9  mov     eax, 51EB851Fh
0x140036cce  mul     ecx
0x140036cd0  shr     edx, 5
0x140036cd3  imul    eax, edx, 64h ; 'd'
0x140036cd6  sub     ecx, eax
0x140036cd8  mov     [rbp+var_40], cx
0x140036cdc  cmp     cx, di
0x140036cdf  jnb     short loc_140036D00
0x140036ce1  mov     rcx, [rbx+28h]
0x140036ce5  lea     rdx, a0; "0"
0x140036cec  add     rcx, 10h; Destination
0x140036cf0  call    cs:__imp_RtlAppendUnicodeToString
0x140036cf7  nop     dword ptr [rax+rax+00h]
0x140036cfc  movzx   ecx, [rbp+var_40]
0x140036d00  movzx   ecx, cx; Value
0x140036d03  lea     r8, [rbp+String]; String
0x140036d07  mov     edx, edi; Base
0x140036d09  call    cs:__imp_RtlIntegerToUnicodeString
0x140036d10  nop     dword ptr [rax+rax+00h]
0x140036d15  mov     rcx, [rbx+28h]
0x140036d19  lea     rdx, [rbp+String]; Source
0x140036d1d  add     rcx, 10h; Destination
0x140036d21  call    cs:__imp_RtlAppendUnicodeStringToString
0x140036d28  nop     dword ptr [rax+rax+00h]
0x140036d2d  mov     edx, 2
0x140036d32  lea     rcx, [rbp+var_40]
0x140036d36  call    GetRandomData
0x140036d3b  movzx   ecx, [rbp+var_40]; Value
0x140036d3f  lea     r8, [rbp+String]; String
0x140036d43  mov     edx, edi; Base
0x140036d45  call    cs:__imp_RtlIntegerToUnicodeString
0x140036d4c  nop     dword ptr [rax+rax+00h]
0x140036d51  mov     rcx, [rbx+28h]
0x140036d55  lea     rdx, [rbp+String]; Source
0x140036d59  add     rcx, 10h; Destination
0x140036d5d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140036d64  nop     dword ptr [rax+rax+00h]
0x140036d69  mov     rcx, [rbx+28h]
0x140036d6d  lea     rdx, aPgm_0; ".PGM"
0x140036d74  add     rcx, 10h; Destination
0x140036d78  call    cs:__imp_RtlAppendUnicodeToString
0x140036d7f  nop     dword ptr [rax+rax+00h]
0x140036d84  xor     eax, eax
0x140036d86  mov     rcx, [rbp+var_10]
0x140036d8a  xor     rcx, rsp; StackCookie
0x140036d8d  call    __security_check_cookie
0x140036d92  lea     r11, [rsp+60h+var_s0]
0x140036d97  mov     rbx, [r11+18h]
0x140036d9b  mov     rdi, [r11+20h]
0x140036d9f  mov     rsp, r11
0x140036da2  pop     rbp
0x140036da3  retn
```
