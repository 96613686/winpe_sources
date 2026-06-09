# WdsIdnCompareHostNames

- ea: `0x180012e6c`
- end: `0x180012f2c`
- name: `WdsIdnCompareHostNames`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180001790`

## callees

- `0x180012cd4`
- `0x180012e6c`
- `0x180014d58`
- `0x1800150b8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180012eec`
- `msvcrt!_wcsicmp` at `0x180012eec`

## string_xrefs

- `0x180012ea4`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`
- `0x180012ecb`: `onecore\base\eco\wds\wdslib\common\src\wdsidn.cpp`

## pseudocode

```c
__int64 __fastcall WdsIdnCompareHostNames(const WCHAR *a1, const WCHAR *a2, int *a3)
{
  wchar_t *v5; // rbx
  unsigned int v6; // esi
  const char *v7; // rdx
  __int64 v8; // rcx
  const char *v9; // rdx
  unsigned int v10; // eax
  wchar_t *String2; // [rsp+20h] [rbp-18h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp+20h] BYREF

  String1 = 0;
  v5 = 0;
  String2 = 0;
  v6 = WdsIdnToAscii((__int64)a1, a1, &String1);
  if ( !ElValidateWin32(v6, v7, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsidn.cpp", 0x92u) )
  {
    v6 = WdsIdnToAscii(v8, a2, &String2);
    v10 = ElValidateWin32(v6, v9, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsidn.cpp", 0x97u);
    v5 = String2;
    if ( !v10 )
      *a3 = _wcsicmp(String1, String2);
  }
  if ( String1 )
    operator delete(String1);
  if ( v5 )
    operator delete(v5);
  return v6;
}

```

## disassembly

```asm
0x180012e6c  mov     rax, rsp
0x180012e6f  mov     [rax+8], rbx
0x180012e73  mov     [rax+10h], rbp
0x180012e77  mov     [rax+18h], rsi
0x180012e7b  push    r14
0x180012e7d  sub     rsp, 30h
0x180012e81  and     qword ptr [rax+20h], 0
0x180012e86  mov     r14, r8
0x180012e89  mov     rbp, rdx
0x180012e8c  lea     r8, [rax+20h]
0x180012e90  xor     ebx, ebx
0x180012e92  mov     rdx, rcx
0x180012e95  mov     [rax-18h], rbx
0x180012e99  call    WdsIdnToAscii
0x180012e9e  mov     r9d, 92h; unsigned int
0x180012ea4  lea     r8, aOnecoreBaseEco_0; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180012eab  mov     ecx, eax; unsigned int
0x180012ead  mov     esi, eax
0x180012eaf  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180012eb4  test    eax, eax
0x180012eb6  jnz     short loc_180012EF5
0x180012eb8  lea     r8, [rsp+38h+String2]
0x180012ebd  mov     rdx, rbp
0x180012ec0  call    WdsIdnToAscii
0x180012ec5  mov     r9d, 97h; unsigned int
0x180012ecb  lea     r8, aOnecoreBaseEco_0; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180012ed2  mov     ecx, eax; unsigned int
0x180012ed4  mov     esi, eax
0x180012ed6  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180012edb  mov     rbx, [rsp+38h+String2]
0x180012ee0  test    eax, eax
0x180012ee2  jnz     short loc_180012EF5
0x180012ee4  mov     rcx, [rsp+38h+String1]; String1
0x180012ee9  mov     rdx, rbx; String2
0x180012eec  call    cs:__imp__wcsicmp
0x180012ef2  mov     [r14], eax
0x180012ef5  cmp     [rsp+38h+String1], 0
0x180012efb  jz      short loc_180012F07
0x180012efd  mov     rcx, [rsp+38h+String1]; Block
0x180012f02  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012f07  test    rbx, rbx
0x180012f0a  jz      short loc_180012F14
0x180012f0c  mov     rcx, rbx; Block
0x180012f0f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012f14  mov     rbx, [rsp+38h+arg_0]
0x180012f19  mov     eax, esi
0x180012f1b  mov     rsi, [rsp+38h+arg_10]
0x180012f20  mov     rbp, [rsp+38h+arg_8]
0x180012f25  add     rsp, 30h
0x180012f29  pop     r14
0x180012f2b  retn
```
