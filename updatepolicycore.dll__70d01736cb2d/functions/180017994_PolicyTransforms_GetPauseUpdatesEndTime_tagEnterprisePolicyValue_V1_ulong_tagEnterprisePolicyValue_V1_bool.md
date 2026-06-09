# PolicyTransforms::GetPauseUpdatesEndTime(tagEnterprisePolicyValue_V1 *,ulong,tagEnterprisePolicyValue_V1 *,bool)

- ea: `0x180017994`
- end: `0x180017b1b`
- name: `?GetPauseUpdatesEndTime@PolicyTransforms@@SAJPEAUtagEnterprisePolicyValue_V1@@K0_N@Z`
- size: `391`
- prototype: `__int64 __fastcall(struct tagEnterprisePolicyValue_V1 *, __int64, struct tagEnterprisePolicyValue_V1 *, unsigned __int8)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180017b30`
- `0x180017bd0`

## callees

- `0x180017994`
- `0x18001f09c`
- `0x18002c854`
- `0x18002c898`
- `0x18002cdfc`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180017adf`
- `OLEAUT32!__imp_SysAllocString` at `0x180017adf`
- `OLEAUT32!__imp_VariantClear` at `0x180017ab2`
- `OLEAUT32!__imp_VariantClear` at `0x180017afa`
- `OLEAUT32!__imp_VariantClear` at `0x180017ab2`
- `OLEAUT32!__imp_VariantClear` at `0x180017afa`

## pseudocode

```c
__int64 __fastcall PolicyTransforms::GetPauseUpdatesEndTime(
        struct tagEnterprisePolicyValue_V1 *a1,
        __int64 a2,
        struct tagEnterprisePolicyValue_V1 *a3,
        unsigned __int8 a4)
{
  unsigned int v4; // esi
  int v7; // r8d
  DWORD dwLowDateTime; // r9d
  struct _FILETIME v9; // rax
  __int64 v10; // r9
  int v11; // edi
  BSTR v12; // rax
  struct _FILETIME v14; // [rsp+20h] [rbp-50h] BYREF
  struct _FILETIME v15; // [rsp+28h] [rbp-48h] BYREF
  OLECHAR psz[8]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v17; // [rsp+40h] [rbp-30h]
  __int64 v18; // [rsp+50h] [rbp-20h]
  __int16 v19; // [rsp+58h] [rbp-18h]

  v4 = a4;
  v15 = 0;
  v14 = 0;
  v18 = 0;
  v19 = 0;
  *(_OWORD *)psz = 0;
  v17 = 0;
  if ( !a3 || !a1 )
    goto LABEL_19;
  if ( !(unsigned int)PolicyHelpers::IsPolicyConfiguredAndEnabled(a3) || *((_DWORD *)a3 + 2) != *((_DWORD *)a1 + 2) )
  {
    *((_DWORD *)a3 + 1) = *((_DWORD *)a1 + 1);
    *((_WORD *)a3 + 8) = *((_WORD *)a1 + 8);
    *((_DWORD *)a3 + 2) = *((_DWORD *)a1 + 2);
    if ( !(unsigned int)PolicyHelpers::IsPolicyConfiguredAndEnabled(a1)
      || (int)StringToFileTime(*((_QWORD *)a1 + 3), &v15, v4) >= 0 )
    {
      dwLowDateTime = v15.dwLowDateTime;
      v9 = (struct _FILETIME)(*(_QWORD *)&v15 + 30240000000000LL);
      v14 = (struct _FILETIME)(*(_QWORD *)&v15 + 30240000000000LL);
      goto LABEL_10;
    }
LABEL_19:
    *(_QWORD *)((char *)a3 + 4) = 0;
    return (unsigned int)VariantClear((VARIANTARG *)((char *)a3 + 16));
  }
  if ( (int)StringToFileTime(*((_QWORD *)a3 + 3), &v14, v4) < 0 )
    goto LABEL_19;
  dwLowDateTime = v15.dwLowDateTime;
  v9 = v14;
LABEL_10:
  if ( !*((_DWORD *)a3 + 1) )
    goto LABEL_19;
  if ( (dwLowDateTime || v15.dwHighDateTime) && *(_QWORD *)&v9 && (int)TimeDiff(&v15, &v14, v7) > 3024000 )
    v14 = (struct _FILETIME)(v10 + 30240000000000LL);
  if ( VariantClear((VARIANTARG *)((char *)a3 + 16)) < 0 )
    goto LABEL_19;
  v11 = FileTimeToString(psz);
  if ( v11 < 0 )
    goto LABEL_19;
  *((_WORD *)a3 + 8) = 8;
  v12 = SysAllocString(psz);
  *((_QWORD *)a3 + 3) = v12;
  if ( !v12 )
    goto LABEL_19;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180017994  push    rbp
0x180017996  push    rbx
0x180017997  push    rsi
0x180017998  push    rdi
0x180017999  push    r15
0x18001799b  mov     rbp, rsp
0x18001799e  sub     rsp, 70h
0x1800179a2  mov     rax, cs:__security_cookie
0x1800179a9  xor     rax, rsp
0x1800179ac  mov     [rbp+var_10], rax
0x1800179b0  xor     eax, eax
0x1800179b2  movzx   esi, r9b
0x1800179b6  mov     qword ptr [rbp+var_48.dwLowDateTime], 0
0x1800179be  xorps   xmm0, xmm0
0x1800179c1  mov     qword ptr [rbp+var_50.dwLowDateTime], 0
0x1800179c9  mov     rbx, r8
0x1800179cc  mov     [rbp+var_20], rax
0x1800179d0  mov     rdi, rcx
0x1800179d3  mov     [rbp+var_18], ax
0x1800179d7  movups  xmmword ptr [rbp+psz], xmm0
0x1800179db  movups  [rbp+var_30], xmm0
0x1800179df  test    r8, r8
0x1800179e2  jz      loc_180017AEE
0x1800179e8  test    rcx, rcx
0x1800179eb  jz      loc_180017AEE
0x1800179f1  mov     rcx, rbx; struct tagUpdatePolicyValue_V1 *
0x1800179f4  call    ?IsPolicyConfiguredAndEnabled@PolicyHelpers@@SAHPEAUtagUpdatePolicyValue_V1@@@Z; PolicyHelpers::IsPolicyConfiguredAndEnabled(tagUpdatePolicyValue_V1 *)
0x1800179f9  mov     r15, 1B80CC754000h
0x180017a03  test    eax, eax
0x180017a05  jz      short loc_180017A31
0x180017a07  mov     eax, [rdi+8]
0x180017a0a  cmp     [rbx+8], eax
0x180017a0d  jnz     short loc_180017A31
0x180017a0f  mov     rcx, [rbx+18h]
0x180017a13  lea     rdx, [rbp+var_50]
0x180017a17  mov     r8d, esi
0x180017a1a  call    StringToFileTime
0x180017a1f  test    eax, eax
0x180017a21  js      loc_180017AEE
0x180017a27  mov     r9, qword ptr [rbp+var_48.dwLowDateTime]
0x180017a2b  mov     rax, qword ptr [rbp+var_50.dwLowDateTime]
0x180017a2f  jmp     short loc_180017A75
0x180017a31  mov     eax, [rdi+4]
0x180017a34  mov     rcx, rdi; struct tagUpdatePolicyValue_V1 *
0x180017a37  mov     [rbx+4], eax
0x180017a3a  movzx   eax, word ptr [rdi+10h]
0x180017a3e  mov     [rbx+10h], ax
0x180017a42  mov     eax, [rdi+8]
0x180017a45  mov     [rbx+8], eax
0x180017a48  call    ?IsPolicyConfiguredAndEnabled@PolicyHelpers@@SAHPEAUtagUpdatePolicyValue_V1@@@Z; PolicyHelpers::IsPolicyConfiguredAndEnabled(tagUpdatePolicyValue_V1 *)
0x180017a4d  test    eax, eax
0x180017a4f  jz      short loc_180017A69
0x180017a51  mov     rcx, [rdi+18h]
0x180017a55  lea     rdx, [rbp+var_48]
0x180017a59  mov     r8d, esi
0x180017a5c  call    StringToFileTime
0x180017a61  test    eax, eax
0x180017a63  js      loc_180017AEE
0x180017a69  mov     r9, qword ptr [rbp+var_48.dwLowDateTime]
0x180017a6d  lea     rax, [r9+r15]
0x180017a71  mov     qword ptr [rbp+var_50.dwLowDateTime], rax
0x180017a75  cmp     dword ptr [rbx+4], 0
0x180017a79  jz      short loc_180017AEE
0x180017a7b  test    r9d, r9d
0x180017a7e  jnz     short loc_180017A86
0x180017a80  cmp     [rbp+var_48.dwHighDateTime], r9d
0x180017a84  jz      short loc_180017AAE
0x180017a86  test    eax, eax
0x180017a88  jnz     short loc_180017A92
0x180017a8a  shr     rax, 20h
0x180017a8e  test    eax, eax
0x180017a90  jz      short loc_180017AAE
0x180017a92  lea     rdx, [rbp+var_50]; struct _FILETIME *
0x180017a96  lea     rcx, [rbp+var_48]; struct _FILETIME *
0x180017a9a  call    ?TimeDiff@@YAHAEBU_FILETIME@@0H@Z; TimeDiff(_FILETIME const &,_FILETIME const &,int)
0x180017a9f  cmp     eax, 2E2480h
0x180017aa4  jle     short loc_180017AAE
0x180017aa6  lea     rax, [r9+r15]
0x180017aaa  mov     qword ptr [rbp+var_50.dwLowDateTime], rax
0x180017aae  lea     rcx, [rbx+10h]; pvarg
0x180017ab2  call    cs:__imp_VariantClear
0x180017ab8  test    eax, eax
0x180017aba  js      short loc_180017AEE
0x180017abc  mov     r9d, 6
0x180017ac2  lea     r8, [rbp+var_50]
0x180017ac6  lea     rcx, [rbp+psz]; Buffer
0x180017aca  call    FileTimeToString
0x180017acf  mov     edi, eax
0x180017ad1  test    eax, eax
0x180017ad3  js      short loc_180017AEE
0x180017ad5  lea     rcx, [rbp+psz]; psz
0x180017ad9  mov     word ptr [rbx+10h], 8
0x180017adf  call    cs:__imp_SysAllocString
0x180017ae5  mov     [rbx+18h], rax
0x180017ae9  test    rax, rax
0x180017aec  jnz     short loc_180017B02
0x180017aee  mov     qword ptr [rbx+4], 0
0x180017af6  lea     rcx, [rbx+10h]; pvarg
0x180017afa  call    cs:__imp_VariantClear
0x180017b00  mov     edi, eax
0x180017b02  mov     eax, edi
0x180017b04  mov     rcx, [rbp+var_10]
0x180017b08  xor     rcx, rsp; StackCookie
0x180017b0b  call    __security_check_cookie
0x180017b10  add     rsp, 70h
0x180017b14  pop     r15
0x180017b16  pop     rdi
0x180017b17  pop     rsi
0x180017b18  pop     rbx
0x180017b19  pop     rbp
0x180017b1a  retn
```
