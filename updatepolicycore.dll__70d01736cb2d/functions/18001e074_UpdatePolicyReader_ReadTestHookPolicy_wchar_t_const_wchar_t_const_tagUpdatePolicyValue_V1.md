# UpdatePolicyReader::ReadTestHookPolicy(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)

- ea: `0x18001e074`
- end: `0x18001e15f`
- name: `?ReadTestHookPolicy@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, struct tagUpdatePolicyValue_V1 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18001da6c`

## callees

- `0x18001e074`
- `0x18001e168`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001e111`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e111`
- `OLEAUT32!__imp_VariantInit` at `0x18001e0a0`
- `OLEAUT32!__imp_VariantInit` at `0x18001e0bb`
- `OLEAUT32!__imp_VariantInit` at `0x18001e0a0`
- `OLEAUT32!__imp_VariantInit` at `0x18001e0bb`
- `OLEAUT32!__imp_VariantClear` at `0x18001e13d`
- `OLEAUT32!__imp_VariantClear` at `0x18001e13d`
- `OLEAUT32!__imp_VariantCopy` at `0x18001e100`
- `OLEAUT32!__imp_VariantCopy` at `0x18001e100`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadTestHookPolicy(
        const wchar_t *a1,
        const wchar_t *a2,
        struct tagUpdatePolicyValue_V1 *a3)
{
  HRESULT v5; // ebx
  unsigned int v7; // [rsp+20h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-40h] BYREF

  v5 = 0;
  v7 = 0;
  VariantInit(&pvarg);
  if ( !a3 || !a1 )
    v5 = -2147467261;
  VariantInit(&pvarg);
  if ( v5 >= 0 )
  {
    v5 = UpdatePolicyReader::ReadTestHookPolicy(a1, &pvarg, &v7);
    if ( v5 >= 0 && v7 == 1 )
    {
      *((_DWORD *)a3 + 1) = 1;
      if ( pvarg.vt == 8 )
        v5 = VariantCopy((VARIANTARG *)((char *)a3 + 16), &pvarg);
      else
        *((_QWORD *)a3 + 3) = SysAllocString(&psz);
      if ( *((_QWORD *)a3 + 3) )
      {
        if ( v5 >= 0 )
        {
          *((_WORD *)a3 + 8) = 8;
          *((_DWORD *)a3 + 2) = 6;
        }
      }
      else
      {
        v5 = -2147024882;
      }
    }
  }
  VariantClear(&pvarg);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001e074  mov     [rsp+arg_8], rbx
0x18001e079  push    rbp
0x18001e07a  push    rsi
0x18001e07b  push    rdi
0x18001e07c  sub     rsp, 50h
0x18001e080  mov     rax, cs:__security_cookie
0x18001e087  xor     rax, rsp
0x18001e08a  mov     [rsp+68h+var_28], rax
0x18001e08f  mov     rdi, r8
0x18001e092  mov     rsi, rcx
0x18001e095  xor     ebx, ebx
0x18001e097  mov     [rsp+68h+var_48], ebx
0x18001e09b  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001e0a0  call    cs:__imp_VariantInit
0x18001e0a6  nop
0x18001e0a7  test    rdi, rdi
0x18001e0aa  jz      short loc_18001E0B1
0x18001e0ac  test    rsi, rsi
0x18001e0af  jnz     short loc_18001E0B6
0x18001e0b1  mov     ebx, 80004003h
0x18001e0b6  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001e0bb  call    cs:__imp_VariantInit
0x18001e0c1  test    ebx, ebx
0x18001e0c3  js      short loc_18001E138
0x18001e0c5  lea     r8, [rsp+68h+var_48]; unsigned int *
0x18001e0ca  lea     rdx, [rsp+68h+pvarg]; pvargDest
0x18001e0cf  mov     rcx, rsi; wchar_t *
0x18001e0d2  call    ?ReadTestHookPolicy@UpdatePolicyReader@@CAJPEB_WPEAUtagVARIANT@@PEAK@Z; UpdatePolicyReader::ReadTestHookPolicy(wchar_t const *,tagVARIANT *,ulong *)
0x18001e0d7  mov     ebx, eax
0x18001e0d9  test    eax, eax
0x18001e0db  js      short loc_18001E138
0x18001e0dd  cmp     [rsp+68h+var_48], 1
0x18001e0e2  jnz     short loc_18001E138
0x18001e0e4  mov     dword ptr [rdi+4], 1
0x18001e0eb  mov     ebp, 8
0x18001e0f0  cmp     word ptr [rsp+68h+pvarg], bp
0x18001e0f5  jnz     short loc_18001E10A
0x18001e0f7  lea     rdx, [rsp+68h+pvarg]; pvargSrc
0x18001e0fc  lea     rcx, [rdi+10h]; pvargDest
0x18001e100  call    cs:__imp_VariantCopy
0x18001e106  mov     ebx, eax
0x18001e108  jmp     short loc_18001E11B
0x18001e10a  lea     rcx, psz; psz
0x18001e111  call    cs:__imp_SysAllocString
0x18001e117  mov     [rdi+18h], rax
0x18001e11b  cmp     qword ptr [rdi+18h], 0
0x18001e120  jnz     short loc_18001E129
0x18001e122  mov     ebx, 8007000Eh
0x18001e127  jmp     short loc_18001E138
0x18001e129  test    ebx, ebx
0x18001e12b  js      short loc_18001E138
0x18001e12d  mov     [rdi+10h], bp
0x18001e131  mov     dword ptr [rdi+8], 6
0x18001e138  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001e13d  call    cs:__imp_VariantClear
0x18001e143  mov     eax, ebx
0x18001e145  mov     rcx, [rsp+68h+var_28]
0x18001e14a  xor     rcx, rsp; StackCookie
0x18001e14d  call    __security_check_cookie
0x18001e152  mov     rbx, [rsp+68h+arg_8]
0x18001e157  add     rsp, 50h
0x18001e15b  pop     rdi
0x18001e15c  pop     rsi
0x18001e15d  pop     rbp
0x18001e15e  retn
```
