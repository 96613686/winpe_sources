# FusionpEqualStrings(ushort const *,unsigned __int64,ushort const *,unsigned __int64,bool)

- ea: `0x18004d2d0`
- end: `0x18004d35b`
- name: `?FusionpEqualStrings@@YA_NPEBG_K01_N@Z`
- size: `139`
- prototype: `bool __fastcall(const unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64, bool)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001fe0`
- `0x18000bc20`
- `0x18002ee20`
- `0x180031260`
- `0x1800434a0`
- `0x180058dc4`

## callees

- `0x18004d2d0`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18004d332`
- `ntdll!RtlCompareUnicodeString` at `0x18004d332`

## pseudocode

```c
bool __fastcall FusionpEqualStrings(WCHAR *a1, __int64 a2, WCHAR *a3, __int64 a4, BOOLEAN a5)
{
  UNICODE_STRING String2; // [rsp+20h] [rbp-38h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-28h] BYREF

  if ( a2 != a4 )
    return 0;
  *(&String1.MaximumLength + 2) = 0;
  String1.Buffer = a1;
  *(&String2.MaximumLength + 2) = 0;
  String1.Length = 2 * a2;
  *(_DWORD *)&String1.MaximumLength = (unsigned __int16)(2 * a2);
  String2.Buffer = a3;
  String2.Length = 2 * a4;
  *(_DWORD *)&String2.MaximumLength = (unsigned __int16)(2 * a4);
  return !RtlCompareUnicodeString(&String1, &String2, a5);
}

```

## disassembly

```asm
0x18004d2d0  sub     rsp, 58h
0x18004d2d4  mov     rax, cs:__security_cookie
0x18004d2db  xor     rax, rsp
0x18004d2de  mov     [rsp+58h+var_18], rax
0x18004d2e3  cmp     rdx, r9
0x18004d2e6  jnz     short loc_18004D357
0x18004d2e8  add     dx, dx
0x18004d2eb  add     r9w, r9w
0x18004d2ef  xorps   xmm0, xmm0
0x18004d2f2  xorps   xmm1, xmm1
0x18004d2f5  movups  xmmword ptr [rsp+58h+String1.Length], xmm0
0x18004d2fa  mov     [rsp+58h+String1.Buffer], rcx
0x18004d2ff  lea     rcx, [rsp+58h+String1]; String1
0x18004d304  movups  xmmword ptr [rsp+58h+String2.Length], xmm1
0x18004d309  mov     [rsp+58h+String1.Length], dx
0x18004d30e  mov     [rsp+58h+String1.MaximumLength], dx
0x18004d313  lea     rdx, [rsp+58h+String2]; String2
0x18004d318  mov     [rsp+58h+String2.Buffer], r8
0x18004d31d  movzx   r8d, [rsp+58h+arg_20]; CaseInsensitive
0x18004d326  mov     [rsp+58h+String2.Length], r9w
0x18004d32c  mov     [rsp+58h+String2.MaximumLength], r9w
0x18004d332  call    cs:__imp_RtlCompareUnicodeString
0x18004d339  nop     dword ptr [rax+rax+00h]
0x18004d33e  test    eax, eax
0x18004d340  jnz     short loc_18004D357
0x18004d342  mov     al, 1
0x18004d344  mov     rcx, [rsp+58h+var_18]
0x18004d349  xor     rcx, rsp; StackCookie
0x18004d34c  call    __security_check_cookie
0x18004d351  add     rsp, 58h
0x18004d355  retn
0x18004d357  xor     al, al
0x18004d359  jmp     short loc_18004D344
```
