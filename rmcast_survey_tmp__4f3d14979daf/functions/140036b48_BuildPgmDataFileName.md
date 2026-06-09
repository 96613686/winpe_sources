# BuildPgmDataFileName

- ea: `0x140036b48`
- end: `0x140036d55`
- name: `BuildPgmDataFileName`
- size: `525`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140036d5c`

## callees

- `0x140005068`
- `0x14001c878`
- `0x14001cdf0`
- `0x140036b48`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036c38`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036c53`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036ca0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036d28`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036c38`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036c53`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036ca0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140036d28`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140036cb9`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140036cf5`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140036cb9`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140036cf5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140036cd1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140036d0d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140036cd1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140036d0d`
- `ntoskrnl!ExAllocatePool2` at `0x140036bab`
- `ntoskrnl!ExAllocatePool2` at `0x140036bab`

## string_xrefs

- `0x140036c31`: `\SystemRoot\System32`

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
    GetRandomData((__int64)&v10, 2u);
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
0x140036b48  mov     [rsp-8+arg_8], rbx
0x140036b4d  mov     [rsp-8+arg_10], rdi
0x140036b52  push    rbp
0x140036b53  mov     rbp, rsp
0x140036b56  sub     rsp, 60h
0x140036b5a  mov     rax, cs:__security_cookie
0x140036b61  xor     rax, rsp
0x140036b64  mov     [rbp+var_10], rax
0x140036b68  xor     eax, eax
0x140036b6a  mov     rbx, rcx
0x140036b6d  mov     rcx, cs:pPgmRegistryConfig
0x140036b74  xorps   xmm0, xmm0
0x140036b77  mov     [rbp+var_40], ax
0x140036b7b  movups  xmmword ptr [rbp+String.Length], xmm0
0x140036b7f  mov     eax, [rcx+4]
0x140036b82  test    al, 1
0x140036b84  jz      short loc_140036B8F
0x140036b86  movzx   eax, word ptr [rcx+8]
0x140036b8a  shr     ax, 1
0x140036b8d  jmp     short loc_140036B94
0x140036b8f  mov     eax, 15h
0x140036b94  add     ax, 0Eh
0x140036b98  mov     ecx, 40h ; '@'
0x140036b9d  movzx   edi, ax
0x140036ba0  mov     r8d, 326D6750h
0x140036ba6  mov     edx, edi
0x140036ba8  add     rdx, rdx
0x140036bab  call    cs:__imp_ExAllocatePool2
0x140036bb2  nop     dword ptr [rax+rax+00h]
0x140036bb7  mov     rcx, [rbx+28h]
0x140036bbb  mov     [rcx+18h], rax
0x140036bbf  test    rax, rax
0x140036bc2  jnz     short loc_140036C00
0x140036bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140036bcb  lea     rax, WPP_GLOBAL_Control
0x140036bd2  cmp     rcx, rax
0x140036bd5  jz      short loc_140036BF6
0x140036bd7  mov     eax, [rcx+2Ch]
0x140036bda  test    al, 2
0x140036bdc  jz      short loc_140036BF6
0x140036bde  mov     rcx, [rcx+18h]
0x140036be2  lea     r8, WPP_0e4477596d4f3af6adc990aa583f3876_Traceguids
0x140036be9  mov     r9d, edi
0x140036bec  mov     edx, 0Ah
0x140036bf1  call    WPP_SF_d
0x140036bf6  mov     eax, 0C000009Ah
0x140036bfb  jmp     loc_140036D36
0x140036c00  mov     rax, [rbx+28h]
0x140036c04  add     di, di
0x140036c07  mov     rdx, cs:pPgmRegistryConfig
0x140036c0e  mov     [rax+12h], di
0x140036c12  xor     eax, eax
0x140036c14  mov     rcx, [rbx+28h]
0x140036c18  mov     [rcx+10h], ax
0x140036c1c  mov     rcx, [rbx+28h]
0x140036c20  mov     eax, [rdx+4]
0x140036c23  add     rcx, 10h; Destination
0x140036c27  test    al, 1
0x140036c29  jz      short loc_140036C31
0x140036c2b  mov     rdx, [rdx+10h]
0x140036c2f  jmp     short loc_140036C38
0x140036c31  lea     rdx, Source; "\\SystemRoot\\System32"
0x140036c38  call    cs:__imp_RtlAppendUnicodeToString
0x140036c3f  nop     dword ptr [rax+rax+00h]
0x140036c44  mov     rcx, [rbx+28h]
0x140036c48  lea     rdx, aT; "\\T"
0x140036c4f  add     rcx, 10h; Destination
0x140036c53  call    cs:__imp_RtlAppendUnicodeToString
0x140036c5a  nop     dword ptr [rax+rax+00h]
0x140036c5f  movzx   ecx, word ptr [rbx+46h]
0x140036c63  mov     eax, 14h
0x140036c68  mov     [rbp+String.MaximumLength], ax
0x140036c6c  mov     edi, 0Ah
0x140036c71  lea     rax, [rbp+var_28]
0x140036c75  mov     [rbp+String.Buffer], rax
0x140036c79  mov     eax, 51EB851Fh
0x140036c7e  mul     ecx
0x140036c80  shr     edx, 5
0x140036c83  imul    eax, edx, 64h ; 'd'
0x140036c86  sub     ecx, eax
0x140036c88  mov     [rbp+var_40], cx
0x140036c8c  cmp     cx, di
0x140036c8f  jnb     short loc_140036CB0
0x140036c91  mov     rcx, [rbx+28h]
0x140036c95  lea     rdx, a0; "0"
0x140036c9c  add     rcx, 10h; Destination
0x140036ca0  call    cs:__imp_RtlAppendUnicodeToString
0x140036ca7  nop     dword ptr [rax+rax+00h]
0x140036cac  movzx   ecx, [rbp+var_40]
0x140036cb0  movzx   ecx, cx; Value
0x140036cb3  lea     r8, [rbp+String]; String
0x140036cb7  mov     edx, edi; Base
0x140036cb9  call    cs:__imp_RtlIntegerToUnicodeString
0x140036cc0  nop     dword ptr [rax+rax+00h]
0x140036cc5  mov     rcx, [rbx+28h]
0x140036cc9  lea     rdx, [rbp+String]; Source
0x140036ccd  add     rcx, 10h; Destination
0x140036cd1  call    cs:__imp_RtlAppendUnicodeStringToString
0x140036cd8  nop     dword ptr [rax+rax+00h]
0x140036cdd  mov     edx, 2
0x140036ce2  lea     rcx, [rbp+var_40]
0x140036ce6  call    GetRandomData
0x140036ceb  movzx   ecx, [rbp+var_40]; Value
0x140036cef  lea     r8, [rbp+String]; String
0x140036cf3  mov     edx, edi; Base
0x140036cf5  call    cs:__imp_RtlIntegerToUnicodeString
0x140036cfc  nop     dword ptr [rax+rax+00h]
0x140036d01  mov     rcx, [rbx+28h]
0x140036d05  lea     rdx, [rbp+String]; Source
0x140036d09  add     rcx, 10h; Destination
0x140036d0d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140036d14  nop     dword ptr [rax+rax+00h]
0x140036d19  mov     rcx, [rbx+28h]
0x140036d1d  lea     rdx, aPgm_0; ".PGM"
0x140036d24  add     rcx, 10h; Destination
0x140036d28  call    cs:__imp_RtlAppendUnicodeToString
0x140036d2f  nop     dword ptr [rax+rax+00h]
0x140036d34  xor     eax, eax
0x140036d36  mov     rcx, [rbp+var_10]
0x140036d3a  xor     rcx, rsp; StackCookie
0x140036d3d  call    __security_check_cookie
0x140036d42  lea     r11, [rsp+60h+var_s0]
0x140036d47  mov     rbx, [r11+18h]
0x140036d4b  mov     rdi, [r11+20h]
0x140036d4f  mov     rsp, r11
0x140036d52  pop     rbp
0x140036d53  retn
```
