# FusionpCompareStrings(ushort const *,unsigned __int64,ushort const *,unsigned __int64,bool)

- ea: `0x180013150`
- end: `0x1800131cc`
- name: `?FusionpCompareStrings@@YAHPEBG_K01_N@Z`
- size: `124`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64, bool)`
- caller_count: `19`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800011f0`
- `0x180011de0`
- `0x1800135f0`
- `0x18001f2c0`
- `0x18002aa40`
- `0x18002bdb4`
- `0x18003b420`
- `0x18003c7d0`
- `0x18003e310`
- `0x180044080`
- `0x180045cb0`
- `0x18004c700`
- `0x180053760`
- `0x180054034`
- `0x180057580`
- `0x1800576c0`
- `0x180057cd0`
- `0x18005a6bc`
- `0x180069c10`

## callees

- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1800131ad`
- `ntdll!RtlCompareUnicodeString` at `0x1800131ad`

## pseudocode

```c
LONG __fastcall FusionpCompareStrings(WCHAR *a1, __int16 a2, WCHAR *a3, __int16 a4, BOOLEAN a5)
{
  UNICODE_STRING String2; // [rsp+20h] [rbp-38h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-28h] BYREF

  *(&String1.MaximumLength + 2) = 0;
  String1.Buffer = a1;
  *(&String2.MaximumLength + 2) = 0;
  String1.Length = 2 * a2;
  *(_DWORD *)&String1.MaximumLength = (unsigned __int16)(2 * a2);
  String2.Buffer = a3;
  String2.Length = 2 * a4;
  *(_DWORD *)&String2.MaximumLength = (unsigned __int16)(2 * a4);
  return RtlCompareUnicodeString(&String1, &String2, a5);
}

```

## disassembly

```asm
0x180013150  sub     rsp, 58h
0x180013154  mov     rax, cs:__security_cookie
0x18001315b  xor     rax, rsp
0x18001315e  mov     [rsp+58h+var_18], rax
0x180013163  add     dx, dx
0x180013166  add     r9w, r9w
0x18001316a  xorps   xmm0, xmm0
0x18001316d  xorps   xmm1, xmm1
0x180013170  movups  xmmword ptr [rsp+58h+String1.Length], xmm0
0x180013175  mov     [rsp+58h+String1.Buffer], rcx
0x18001317a  lea     rcx, [rsp+58h+String1]; String1
0x18001317f  movups  xmmword ptr [rsp+58h+String2.Length], xmm1
0x180013184  mov     [rsp+58h+String1.Length], dx
0x180013189  mov     [rsp+58h+String1.MaximumLength], dx
0x18001318e  lea     rdx, [rsp+58h+String2]; String2
0x180013193  mov     [rsp+58h+String2.Buffer], r8
0x180013198  movzx   r8d, [rsp+58h+arg_20]; CaseInsensitive
0x1800131a1  mov     [rsp+58h+String2.Length], r9w
0x1800131a7  mov     [rsp+58h+String2.MaximumLength], r9w
0x1800131ad  call    cs:__imp_RtlCompareUnicodeString
0x1800131b4  nop     dword ptr [rax+rax+00h]
0x1800131b9  mov     rcx, [rsp+58h+var_18]
0x1800131be  xor     rcx, rsp; StackCookie
0x1800131c1  call    __security_check_cookie
0x1800131c6  add     rsp, 58h
0x1800131ca  retn
```
