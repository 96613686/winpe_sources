# PolicyTransforms::ConvertAndSetPauseUpdates(wchar_t const *,PauseUpdateType,ulong,tagEnterprisePolicyValue_V1 *)

- ea: `0x180017014`
- end: `0x1800171b5`
- name: `?ConvertAndSetPauseUpdates@PolicyTransforms@@SAJPEB_WW4PauseUpdateType@@KPEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `417`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, __int64, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800171c0`
- `0x1800171e0`
- `0x180017200`

## callees

- `0x180017014`
- `0x18001f09c`
- `0x18001f560`
- `0x18001f6c8`
- `0x18001f818`
- `0x18002cdfc`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180017136`
- `OLEAUT32!__imp_SysAllocString` at `0x180017136`
- `OLEAUT32!__imp_VariantClear` at `0x1800170f7`
- `OLEAUT32!__imp_VariantClear` at `0x1800170f7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800170d1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800170d1`

## pseudocode

```c
__int64 __fastcall PolicyTransforms::ConvertAndSetPauseUpdates(
        const wchar_t *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v4; // esi
  BOOL v7; // edi
  int v9; // r14d
  HRESULT PersistedPauseDate; // ecx
  bool v11; // zf
  BSTR v12; // rax
  struct _FILETIME v13; // rdx
  int v15; // [rsp+20h] [rbp-60h] BYREF
  struct _FILETIME v16; // [rsp+28h] [rbp-58h] BYREF
  FILETIME FileTime1; // [rsp+30h] [rbp-50h] BYREF
  FILETIME FileTime2; // [rsp+38h] [rbp-48h] BYREF
  OLECHAR psz[8]; // [rsp+40h] [rbp-40h] BYREF
  __int128 v20; // [rsp+50h] [rbp-30h]
  __int64 v21; // [rsp+60h] [rbp-20h]
  __int16 v22; // [rsp+68h] [rbp-18h]

  v4 = 0;
  v15 = 0;
  v16 = 0;
  FileTime1 = 0;
  FileTime2 = 0;
  v7 = 1;
  v21 = 0;
  v22 = 0;
  v9 = 0;
  *(_OWORD *)psz = 0;
  v20 = 0;
  if ( a4 )
  {
    if ( (unsigned int)PolicyHelpers::IsPolicyConfiguredAndEnabled((struct tagUpdatePolicyValue_V1 *)a4) )
    {
      FileTime1 = *(FILETIME *)(a4 + 40);
      PersistedPauseDate = PolicyHelpers::GetPersistedPauseDate(a1, &v15, &v16);
      if ( PersistedPauseDate < 0 )
        return (unsigned int)PersistedPauseDate;
      v9 = v15;
      if ( v15 )
      {
        FileTime2 = (FILETIME)(*(_QWORD *)&v16 + 30240000000000LL);
        LOBYTE(v4) = CompareFileTime(&FileTime1, &FileTime2) != -1;
        ++v4;
      }
      else
      {
        v4 = 1;
      }
    }
    else
    {
      v11 = *(_DWORD *)(a4 + 4) == 1;
      *(_DWORD *)(a4 + 4) = 0;
      v7 = !v11;
    }
    PersistedPauseDate = VariantClear((VARIANTARG *)(a4 + 16));
    if ( PersistedPauseDate >= 0 )
    {
      if ( (v11 = v16.dwLowDateTime == 0, *(_WORD *)(a4 + 16) = 8, v11) && !v16.dwHighDateTime
        || (PersistedPauseDate = FileTimeToString(psz), PersistedPauseDate >= 0) )
      {
        v12 = SysAllocString(psz);
        *(_QWORD *)(a4 + 24) = v12;
        if ( v12 )
        {
          PersistedPauseDate = PolicyHelpers::PersistPauseStatus(a2, v4);
          if ( PersistedPauseDate >= 0 )
          {
            v13 = FileTime1;
            if ( v9 )
              v13 = v16;
            v16 = v13;
            if ( !v7 || *(_QWORD *)&v13 )
              return (unsigned int)PolicyHelpers::PersistPauseDate(a1, v13, v7);
          }
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)PersistedPauseDate;
}

```

## disassembly

```asm
0x180017014  mov     [rsp-38h+arg_8], rbx
0x180017019  push    rbp
0x18001701a  push    rsi
0x18001701b  push    rdi
0x18001701c  push    r12
0x18001701e  push    r13
0x180017020  push    r14
0x180017022  push    r15
0x180017024  mov     rbp, rsp
0x180017027  sub     rsp, 80h
0x18001702e  mov     rax, cs:__security_cookie
0x180017035  xor     rax, rsp
0x180017038  mov     [rbp+var_10], rax
0x18001703c  xor     esi, esi
0x18001703e  xor     eax, eax
0x180017040  mov     [rbp+var_60], esi
0x180017043  xorps   xmm0, xmm0
0x180017046  mov     qword ptr [rbp+var_58.dwLowDateTime], rsi
0x18001704a  mov     rbx, r9
0x18001704d  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rsi
0x180017051  mov     r13d, edx
0x180017054  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rsi
0x180017058  lea     edi, [rsi+1]
0x18001705b  mov     [rbp+var_20], rax
0x18001705f  mov     r12, rcx
0x180017062  mov     [rbp+var_18], ax
0x180017066  mov     r14d, esi
0x180017069  movups  xmmword ptr [rbp+psz], xmm0
0x18001706d  movups  [rbp+var_30], xmm0
0x180017071  test    r9, r9
0x180017074  jnz     short loc_180017080
0x180017076  mov     ecx, 80004003h
0x18001707b  jmp     loc_18001718C
0x180017080  mov     rcx, rbx; struct tagUpdatePolicyValue_V1 *
0x180017083  call    ?IsPolicyConfiguredAndEnabled@PolicyHelpers@@SAHPEAUtagUpdatePolicyValue_V1@@@Z; PolicyHelpers::IsPolicyConfiguredAndEnabled(tagUpdatePolicyValue_V1 *)
0x180017088  test    eax, eax
0x18001708a  jz      short loc_1800170E6
0x18001708c  mov     rax, [rbx+28h]
0x180017090  lea     r8, [rbp+var_58]; struct _FILETIME *
0x180017094  lea     rdx, [rbp+var_60]; int *
0x180017098  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x18001709c  mov     rcx, r12; wchar_t *
0x18001709f  call    ?GetPersistedPauseDate@PolicyHelpers@@SAJPEB_WPEAHPEAU_FILETIME@@@Z; PolicyHelpers::GetPersistedPauseDate(wchar_t const *,int *,_FILETIME *)
0x1800170a4  mov     ecx, eax
0x1800170a6  test    eax, eax
0x1800170a8  js      loc_18001718C
0x1800170ae  mov     r14d, [rbp+var_60]
0x1800170b2  test    r14d, r14d
0x1800170b5  jz      short loc_1800170E2
0x1800170b7  mov     rcx, 1B80CC754000h
0x1800170c1  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x1800170c5  add     rcx, qword ptr [rbp+var_58.dwLowDateTime]
0x1800170c9  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rcx
0x1800170cd  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800170d1  call    cs:__imp_CompareFileTime
0x1800170d7  cmp     eax, 0FFFFFFFFh
0x1800170da  setnz   sil
0x1800170de  add     esi, edi
0x1800170e0  jmp     short loc_1800170F3
0x1800170e2  mov     esi, edi
0x1800170e4  jmp     short loc_1800170F3
0x1800170e6  cmp     [rbx+4], edi
0x1800170e9  mov     eax, esi
0x1800170eb  mov     [rbx+4], esi
0x1800170ee  setnz   al
0x1800170f1  mov     edi, eax
0x1800170f3  lea     rcx, [rbx+10h]; pvarg
0x1800170f7  call    cs:__imp_VariantClear
0x1800170fd  mov     ecx, eax
0x1800170ff  test    eax, eax
0x180017101  js      loc_18001718C
0x180017107  cmp     [rbp+var_58.dwLowDateTime], 0
0x18001710b  mov     word ptr [rbx+10h], 8
0x180017111  jnz     short loc_180017119
0x180017113  cmp     [rbp+var_58.dwHighDateTime], 0
0x180017117  jz      short loc_180017132
0x180017119  mov     r9d, 6
0x18001711f  lea     r8, [rbp+var_58]
0x180017123  lea     rcx, [rbp+psz]; Buffer
0x180017127  call    FileTimeToString
0x18001712c  mov     ecx, eax
0x18001712e  test    eax, eax
0x180017130  js      short loc_18001718C
0x180017132  lea     rcx, [rbp+psz]; psz
0x180017136  call    cs:__imp_SysAllocString
0x18001713c  mov     [rbx+18h], rax
0x180017140  test    rax, rax
0x180017143  jnz     short loc_18001714C
0x180017145  mov     ecx, 8007000Eh
0x18001714a  jmp     short loc_18001718C
0x18001714c  mov     edx, esi
0x18001714e  mov     ecx, r13d
0x180017151  call    ?PersistPauseStatus@PolicyHelpers@@SAJW4PauseUpdateType@@K@Z; PolicyHelpers::PersistPauseStatus(PauseUpdateType,ulong)
0x180017156  mov     ecx, eax
0x180017158  test    eax, eax
0x18001715a  js      short loc_18001718C
0x18001715c  mov     rdx, qword ptr [rbp+FileTime1.dwLowDateTime]
0x180017160  test    r14d, r14d
0x180017163  cmovnz  rdx, qword ptr [rbp+var_58.dwLowDateTime]; struct _FILETIME
0x180017168  mov     qword ptr [rbp+var_58.dwLowDateTime], rdx
0x18001716c  test    edi, edi
0x18001716e  jz      short loc_18001717F
0x180017170  test    edx, edx
0x180017172  jnz     short loc_18001717F
0x180017174  mov     rax, rdx
0x180017177  shr     rax, 20h
0x18001717b  test    eax, eax
0x18001717d  jz      short loc_18001718C
0x18001717f  mov     r8d, edi; int
0x180017182  mov     rcx, r12; wchar_t *
0x180017185  call    ?PersistPauseDate@PolicyHelpers@@SAJPEB_WU_FILETIME@@H@Z; PolicyHelpers::PersistPauseDate(wchar_t const *,_FILETIME,int)
0x18001718a  mov     ecx, eax
0x18001718c  mov     eax, ecx
0x18001718e  mov     rcx, [rbp+var_10]
0x180017192  xor     rcx, rsp; StackCookie
0x180017195  call    __security_check_cookie
0x18001719a  mov     rbx, [rsp+80h+arg_8]
0x1800171a2  add     rsp, 80h
0x1800171a9  pop     r15
0x1800171ab  pop     r14
0x1800171ad  pop     r13
0x1800171af  pop     r12
0x1800171b1  pop     rdi
0x1800171b2  pop     rsi
0x1800171b3  pop     rbp
0x1800171b4  retn
```
