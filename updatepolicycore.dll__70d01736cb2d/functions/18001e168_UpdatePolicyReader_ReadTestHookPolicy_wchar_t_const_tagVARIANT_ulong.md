# UpdatePolicyReader::ReadTestHookPolicy(wchar_t const *,tagVARIANT *,ulong *)

- ea: `0x18001e168`
- end: `0x18001e256`
- name: `?ReadTestHookPolicy@UpdatePolicyReader@@CAJPEB_WPEAUtagVARIANT@@PEAK@Z`
- size: `238`
- prototype: `__int64 __fastcall(const wchar_t *, VARIANTARG *pvargDest, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18001df94`
- `0x18001e074`

## callees

- `0x18000aac0`
- `0x1800188fc`
- `0x18001e168`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001e192`
- `OLEAUT32!__imp_VariantInit` at `0x18001e192`
- `OLEAUT32!__imp_VariantClear` at `0x18001e232`
- `OLEAUT32!__imp_VariantClear` at `0x18001e232`
- `OLEAUT32!__imp_VariantCopy` at `0x18001e201`
- `OLEAUT32!__imp_VariantCopy` at `0x18001e201`

## string_xrefs

- `0x18001e219`: `C:\__w\1\s\src\Client\policy\src\Update\PolicyReader.cpp`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadTestHookPolicy(const wchar_t *a1, VARIANTARG *pvargDest, unsigned int *a3)
{
  __int64 v6; // rdx
  int PolicyValue; // ebx
  __int64 v9; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG pvargSrc; // [rsp+28h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  VariantInit(&pvarg);
  v9 = 0;
  pvargSrc = pvarg;
  if ( !a1 )
  {
    v6 = 2939;
LABEL_7:
    PolicyValue = -2147467261;
    goto LABEL_12;
  }
  if ( !pvargDest )
  {
    v6 = 2940;
    goto LABEL_7;
  }
  if ( !a3 )
  {
    v6 = 2941;
    goto LABEL_7;
  }
  PolicyValue = TestHookPolicyReader::GetPolicyValue(a1, 0x13u, (struct tagTestHookPolicyValue_V1 *)&v9);
  if ( PolicyValue >= 0 )
  {
    PolicyValue = VariantCopy(pvargDest, &pvargSrc);
    if ( PolicyValue >= 0 )
    {
      *a3 = v9;
      PolicyValue = 0;
      goto LABEL_14;
    }
    v6 = 2945;
  }
  else
  {
    v6 = 2943;
  }
LABEL_12:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Update\\PolicyReader.cpp",
    (const char *)(unsigned int)PolicyValue,
    v9);
LABEL_14:
  VariantClear(&pvarg);
  return (unsigned int)PolicyValue;
}

```

## disassembly

```asm
0x18001e168  mov     [rsp-18h+arg_18], rbx
0x18001e16d  push    rbp
0x18001e16e  push    rsi
0x18001e16f  push    rdi
0x18001e170  mov     rbp, rsp
0x18001e173  sub     rsp, 60h
0x18001e177  mov     rax, cs:__security_cookie
0x18001e17e  xor     rax, rsp
0x18001e181  mov     [rbp+var_8], rax
0x18001e185  mov     rdi, r8
0x18001e188  mov     rsi, rdx
0x18001e18b  mov     rbx, rcx
0x18001e18e  lea     rcx, [rbp+pvarg]; pvarg
0x18001e192  call    cs:__imp_VariantInit
0x18001e198  nop
0x18001e199  mov     [rbp+var_40], 0
0x18001e1a1  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18001e1a5  movups  xmmword ptr [rbp+pvargSrc], xmm0
0x18001e1a9  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18001e1ae  movsd   qword ptr [rbp+pvargSrc+10h], xmm1
0x18001e1b3  test    rbx, rbx
0x18001e1b6  jnz     short loc_18001E1BF
0x18001e1b8  mov     edx, 0B7Bh
0x18001e1bd  jmp     short loc_18001E1D5
0x18001e1bf  test    rsi, rsi
0x18001e1c2  jnz     short loc_18001E1CB
0x18001e1c4  mov     edx, 0B7Ch
0x18001e1c9  jmp     short loc_18001E1D5
0x18001e1cb  test    rdi, rdi
0x18001e1ce  jnz     short loc_18001E1DC
0x18001e1d0  mov     edx, 0B7Dh
0x18001e1d5  mov     ebx, 80004003h
0x18001e1da  jmp     short loc_18001E212
0x18001e1dc  mov     edx, 13h; unsigned __int16
0x18001e1e1  lea     r8, [rbp+var_40]; struct tagTestHookPolicyValue_V1 *
0x18001e1e5  mov     rcx, rbx; wchar_t *
0x18001e1e8  call    ?GetPolicyValue@TestHookPolicyReader@@SAJPEB_WGPEAUtagTestHookPolicyValue_V1@@@Z; TestHookPolicyReader::GetPolicyValue(wchar_t const *,ushort,tagTestHookPolicyValue_V1 *)
0x18001e1ed  mov     ebx, eax
0x18001e1ef  test    eax, eax
0x18001e1f1  jns     short loc_18001E1FA
0x18001e1f3  mov     edx, 0B7Fh
0x18001e1f8  jmp     short loc_18001E212
0x18001e1fa  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x18001e1fe  mov     rcx, rsi; pvargDest
0x18001e201  call    cs:__imp_VariantCopy
0x18001e207  mov     ebx, eax
0x18001e209  test    eax, eax
0x18001e20b  jns     short loc_18001E227
0x18001e20d  mov     edx, 0B81h; void *
0x18001e212  mov     rcx, [rbp+18h]; this
0x18001e216  mov     r9d, ebx; char *
0x18001e219  lea     r8, aCW1SSrcClientP_9; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18001e220  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e225  jmp     short loc_18001E22E
0x18001e227  mov     eax, dword ptr [rbp+var_40]
0x18001e22a  mov     [rdi], eax
0x18001e22c  xor     ebx, ebx
0x18001e22e  lea     rcx, [rbp+pvarg]; pvarg
0x18001e232  call    cs:__imp_VariantClear
0x18001e238  mov     eax, ebx
0x18001e23a  mov     rcx, [rbp+var_8]
0x18001e23e  xor     rcx, rsp; StackCookie
0x18001e241  call    __security_check_cookie
0x18001e246  mov     rbx, [rsp+60h+arg_18]
0x18001e24e  add     rsp, 60h
0x18001e252  pop     rdi
0x18001e253  pop     rsi
0x18001e254  pop     rbp
0x18001e255  retn
```
