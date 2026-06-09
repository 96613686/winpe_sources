# EnterprisePolicyReader::ReadTestHookPolicy(wchar_t const *,wchar_t const *,tagEnterprisePolicyValue_V1 *)

- ea: `0x180012138`
- end: `0x180012225`
- name: `?ReadTestHookPolicy@EnterprisePolicyReader@@CAJPEB_W0PEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, struct tagEnterprisePolicyValue_V1 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180010c1c`

## callees

- `0x180012138`
- `0x18001222c`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800121d4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800121d4`
- `OLEAUT32!__imp_VariantInit` at `0x180012166`
- `OLEAUT32!__imp_VariantInit` at `0x180012180`
- `OLEAUT32!__imp_VariantInit` at `0x180012166`
- `OLEAUT32!__imp_VariantInit` at `0x180012180`
- `OLEAUT32!__imp_VariantClear` at `0x180012203`
- `OLEAUT32!__imp_VariantClear` at `0x180012203`
- `OLEAUT32!__imp_VariantCopy` at `0x1800121c3`
- `OLEAUT32!__imp_VariantCopy` at `0x1800121c3`

## pseudocode

```c
__int64 __fastcall EnterprisePolicyReader::ReadTestHookPolicy(
        const wchar_t *a1,
        const wchar_t *a2,
        struct tagEnterprisePolicyValue_V1 *a3)
{
  int v5; // ebx
  unsigned int v7; // [rsp+20h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-40h] BYREF

  v7 = 0;
  VariantInit(&pvarg);
  if ( a3 && a1 )
  {
    VariantInit(&pvarg);
    v5 = EnterprisePolicyReader::ReadTestHookPolicy(a1, 8u, &pvarg, &v7);
    if ( v5 >= 0 && v7 == 1 )
    {
      *((_DWORD *)a3 + 1) = 1;
      if ( pvarg.vt == 8 )
        v5 = VariantCopy((VARIANTARG *)((char *)a3 + 16), &pvarg);
      else
        *((_QWORD *)a3 + 3) = SysAllocString(&psz);
      if ( *((_QWORD *)a3 + 3) )
      {
        *((_WORD *)a3 + 8) = 8;
        *((_DWORD *)a3 + 2) = 6;
      }
      else
      {
        v5 = -2147024882;
      }
    }
  }
  else
  {
    v5 = -2147467261;
  }
  VariantClear(&pvarg);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180012138  mov     [rsp+arg_8], rbx
0x18001213d  push    rbp
0x18001213e  push    rsi
0x18001213f  push    rdi
0x180012140  sub     rsp, 50h
0x180012144  mov     rax, cs:__security_cookie
0x18001214b  xor     rax, rsp
0x18001214e  mov     [rsp+68h+var_28], rax
0x180012153  mov     rdi, r8
0x180012156  mov     rbx, rcx
0x180012159  mov     [rsp+68h+var_48], 0
0x180012161  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180012166  call    cs:__imp_VariantInit
0x18001216c  nop
0x18001216d  test    rdi, rdi
0x180012170  jz      loc_1800121F9
0x180012176  test    rbx, rbx
0x180012179  jz      short loc_1800121F9
0x18001217b  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180012180  call    cs:__imp_VariantInit
0x180012186  mov     ebp, 8
0x18001218b  mov     edx, ebp; unsigned __int16
0x18001218d  lea     r9, [rsp+68h+var_48]; unsigned int *
0x180012192  lea     r8, [rsp+68h+pvarg]; struct tagVARIANT *
0x180012197  mov     rcx, rbx; wchar_t *
0x18001219a  call    ?ReadTestHookPolicy@EnterprisePolicyReader@@CAJPEB_WGPEAUtagVARIANT@@PEAK@Z; EnterprisePolicyReader::ReadTestHookPolicy(wchar_t const *,ushort,tagVARIANT *,ulong *)
0x18001219f  mov     ebx, eax
0x1800121a1  test    eax, eax
0x1800121a3  js      short loc_1800121FE
0x1800121a5  cmp     [rsp+68h+var_48], 1
0x1800121aa  jnz     short loc_1800121FE
0x1800121ac  mov     dword ptr [rdi+4], 1
0x1800121b3  cmp     word ptr [rsp+68h+pvarg], bp
0x1800121b8  jnz     short loc_1800121CD
0x1800121ba  lea     rdx, [rsp+68h+pvarg]; pvargSrc
0x1800121bf  lea     rcx, [rdi+10h]; pvargDest
0x1800121c3  call    cs:__imp_VariantCopy
0x1800121c9  mov     ebx, eax
0x1800121cb  jmp     short loc_1800121DE
0x1800121cd  lea     rcx, psz; psz
0x1800121d4  call    cs:__imp_SysAllocString
0x1800121da  mov     [rdi+18h], rax
0x1800121de  cmp     qword ptr [rdi+18h], 0
0x1800121e3  jnz     short loc_1800121EC
0x1800121e5  mov     ebx, 8007000Eh
0x1800121ea  jmp     short loc_1800121FE
0x1800121ec  mov     [rdi+10h], bp
0x1800121f0  mov     dword ptr [rdi+8], 6
0x1800121f7  jmp     short loc_1800121FE
0x1800121f9  mov     ebx, 80004003h
0x1800121fe  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180012203  call    cs:__imp_VariantClear
0x180012209  mov     eax, ebx
0x18001220b  mov     rcx, [rsp+68h+var_28]
0x180012210  xor     rcx, rsp; StackCookie
0x180012213  call    __security_check_cookie
0x180012218  mov     rbx, [rsp+68h+arg_8]
0x18001221d  add     rsp, 50h
0x180012221  pop     rdi
0x180012222  pop     rsi
0x180012223  pop     rbp
0x180012224  retn
```
