# CUpdatePolicyReader::ReadUpdatePolicy(tagUpdatePolicy,tagUpdatePolicyValue_V1 *)

- ea: `0x18000c940`
- end: `0x18000c9cd`
- name: `?ReadUpdatePolicy@CUpdatePolicyReader@@UEAAJW4tagUpdatePolicy@@PEAUtagUpdatePolicyValue_V1@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x18000c940`
- `0x18001a320`
- `0x18001ece0`
- `0x18001f2e0`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18000c990`
- `OLEAUT32!__imp_VariantCopy` at `0x18000c990`

## pseudocode

```c
__int64 __fastcall CUpdatePolicyReader::ReadUpdatePolicy(__int64 a1, unsigned int a2, __int64 a3)
{
  HRESULT v5; // ebx
  int v6; // eax
  struct tagUpdatePolicyValue_V1 *v7; // rsi
  struct tagUpdatePolicyValue_V1 *v9; // [rsp+40h] [rbp+18h] BYREF

  v9 = 0;
  if ( a3 )
  {
    PolicyHelpers::InitPolicyState((struct tagUpdatePolicyValue_V1 *)a3);
    v6 = UpdatePolicyReader::ReadPolicy(a2, &v9);
    v7 = v9;
    v5 = v6;
    if ( v6 >= 0 )
    {
      v5 = VariantCopy((VARIANTARG *)(a3 + 16), (const VARIANTARG *)((char *)v9 + 16));
      if ( v5 >= 0 )
      {
        *(_DWORD *)a3 = *(_DWORD *)v7;
        *(_DWORD *)(a3 + 4) = *((_DWORD *)v7 + 1);
        *(_DWORD *)(a3 + 8) = *((_DWORD *)v7 + 2);
      }
    }
    if ( v7 )
      UpdatePolicyReader::ReleaseUpdatePolicyValue(&v9);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000c940  mov     [rsp+arg_0], rbx
0x18000c945  mov     [rsp+arg_8], rsi
0x18000c94a  push    rdi
0x18000c94b  sub     rsp, 20h
0x18000c94f  mov     [rsp+28h+arg_10], 0
0x18000c958  mov     rdi, r8
0x18000c95b  mov     ebx, edx
0x18000c95d  test    r8, r8
0x18000c960  jnz     short loc_18000C969
0x18000c962  mov     ebx, 80004003h
0x18000c967  jmp     short loc_18000C9BB
0x18000c969  mov     rcx, rdi; struct tagUpdatePolicyValue_V1 *
0x18000c96c  call    ?InitPolicyState@PolicyHelpers@@SAXPEAUtagUpdatePolicyValue_V1@@@Z; PolicyHelpers::InitPolicyState(tagUpdatePolicyValue_V1 *)
0x18000c971  lea     rdx, [rsp+28h+arg_10]
0x18000c976  mov     ecx, ebx
0x18000c978  call    ?ReadPolicy@UpdatePolicyReader@@SAJW4tagUpdatePolicy@@PEAPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadPolicy(tagUpdatePolicy,tagUpdatePolicyValue_V1 * *)
0x18000c97d  mov     rsi, [rsp+28h+arg_10]
0x18000c982  mov     ebx, eax
0x18000c984  test    eax, eax
0x18000c986  js      short loc_18000C9AC
0x18000c988  lea     rdx, [rsi+10h]; pvargSrc
0x18000c98c  lea     rcx, [rdi+10h]; pvargDest
0x18000c990  call    cs:__imp_VariantCopy
0x18000c996  mov     ebx, eax
0x18000c998  test    eax, eax
0x18000c99a  js      short loc_18000C9AC
0x18000c99c  mov     eax, [rsi]
0x18000c99e  mov     [rdi], eax
0x18000c9a0  mov     eax, [rsi+4]
0x18000c9a3  mov     [rdi+4], eax
0x18000c9a6  mov     eax, [rsi+8]
0x18000c9a9  mov     [rdi+8], eax
0x18000c9ac  test    rsi, rsi
0x18000c9af  jz      short loc_18000C9BB
0x18000c9b1  lea     rcx, [rsp+28h+arg_10]; struct tagUpdatePolicyValue_V1 **
0x18000c9b6  call    ?ReleaseUpdatePolicyValue@UpdatePolicyReader@@SAJPEAPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReleaseUpdatePolicyValue(tagUpdatePolicyValue_V1 * *)
0x18000c9bb  mov     rsi, [rsp+28h+arg_8]
0x18000c9c0  mov     eax, ebx
0x18000c9c2  mov     rbx, [rsp+28h+arg_0]
0x18000c9c7  add     rsp, 20h
0x18000c9cb  pop     rdi
0x18000c9cc  retn
```
