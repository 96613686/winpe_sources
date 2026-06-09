# IsScriptFile

- ea: `0x180026320`
- end: `0x1800263e6`
- name: `IsScriptFile`
- size: `198`
- prototype: `char __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180040d58`

## callees

- `0x180026320`

## import_xrefs

- `ntdll!RtlImageNtHeaderEx` at `0x180026341`
- `ntdll!RtlImageNtHeaderEx` at `0x180026341`

## pseudocode

```c
char __fastcall IsScriptFile(_QWORD *a1, __int64 a2)
{
  ULONGLONG v2; // r8
  void *v3; // rdx
  NTSTATUS v5; // edx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  char result; // al
  PIMAGE_NT_HEADERS NtHeader; // [rsp+38h] [rbp+10h] BYREF

  v2 = *(_QWORD *)(a2 + 16);
  v3 = *(void **)(a2 + 8);
  NtHeader = 0;
  v5 = RtlImageNtHeaderEx(0, v3, v2, &NtHeader);
  v6 = *a1 - 0x11D08E59DE351A43LL;
  if ( *a1 == 0x11D08E59DE351A43LL )
    v6 = a1[1] + 0x116A3DB03FFFB874LL;
  if ( !v6 )
    return 0;
  v7 = *a1 - 0x11D08E78C689AABALL;
  if ( *a1 == 0x11D08E78C689AABALL )
    v7 = a1[1] + 0x116A3DB03FFFB874LL;
  if ( !v7 )
    return 0;
  v8 = *a1 - 0x11D0E73A9BA61D3FLL;
  if ( *a1 == 0x11D0E73A9BA61D3FLL )
    v8 = a1[1] + 0x116A3DB03FFF2D74LL;
  if ( !v8 )
    return 0;
  v9 = *a1 - 0x11D08E78C689AAB8LL;
  if ( *a1 == 0x11D08E78C689AAB8LL )
    v9 = a1[1] + 0x116A3DB03FFFB874LL;
  if ( !v9 )
    return 0;
  v10 = *a1 - 790769LL;
  if ( *a1 == 790769 )
    v10 = a1[1] - 0x46000000000000C0LL;
  if ( !v10 )
    return 0;
  result = 1;
  if ( v5 >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180026320  push    rbx
0x180026322  sub     rsp, 20h
0x180026326  mov     r8, [rdx+10h]; Size
0x18002632a  lea     r9, [rsp+28h+NtHeader]; NtHeader
0x18002632f  mov     rdx, [rdx+8]; BaseAddress
0x180026333  mov     rbx, rcx
0x180026336  xor     ecx, ecx; Flags
0x180026338  mov     [rsp+28h+NtHeader], 0
0x180026341  call    cs:__imp_RtlImageNtHeaderEx
0x180026347  mov     rcx, [rbx]
0x18002634a  mov     edx, eax
0x18002634c  sub     rcx, cs:qword_180056FE8
0x180026353  jnz     short loc_180026360
0x180026355  mov     rcx, [rbx+8]
0x180026359  sub     rcx, cs:qword_180056FF0
0x180026360  test    rcx, rcx
0x180026363  jz      short loc_1800263DE
0x180026365  mov     rax, [rbx]
0x180026368  sub     rax, cs:qword_180057018
0x18002636f  jnz     short loc_18002637C
0x180026371  mov     rax, [rbx+8]
0x180026375  sub     rax, cs:qword_180057020
0x18002637c  test    rax, rax
0x18002637f  jz      short loc_1800263DE
0x180026381  mov     rax, [rbx]
0x180026384  sub     rax, cs:qword_180057028
0x18002638b  jnz     short loc_180026398
0x18002638d  mov     rax, [rbx+8]
0x180026391  sub     rax, cs:qword_180057030
0x180026398  test    rax, rax
0x18002639b  jz      short loc_1800263DE
0x18002639d  mov     rax, [rbx]
0x1800263a0  sub     rax, cs:qword_180056FF8
0x1800263a7  jnz     short loc_1800263B4
0x1800263a9  mov     rax, [rbx+8]
0x1800263ad  sub     rax, cs:qword_180057000
0x1800263b4  test    rax, rax
0x1800263b7  jz      short loc_1800263DE
0x1800263b9  mov     rax, [rbx]
0x1800263bc  sub     rax, cs:qword_180057008
0x1800263c3  jnz     short loc_1800263D0
0x1800263c5  mov     rax, [rbx+8]
0x1800263c9  sub     rax, cs:qword_180057010
0x1800263d0  test    rax, rax
0x1800263d3  jz      short loc_1800263DE
0x1800263d5  shr     edx, 1Fh
0x1800263d8  mov     al, 1
0x1800263da  xor     dl, al
0x1800263dc  jz      short loc_1800263E0
0x1800263de  xor     al, al
0x1800263e0  add     rsp, 20h
0x1800263e4  pop     rbx
0x1800263e5  retn
```
