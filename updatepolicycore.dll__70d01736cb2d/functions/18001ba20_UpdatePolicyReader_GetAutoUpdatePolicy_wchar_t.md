# UpdatePolicyReader::GetAutoUpdatePolicy(wchar_t * *)

- ea: `0x18001ba20`
- end: `0x18001bb40`
- name: `?GetAutoUpdatePolicy@UpdatePolicyReader@@SAJPEAPEA_W@Z`
- size: `288`
- prototype: `__int64 __fastcall(wchar_t **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callees

- `0x1800090a8`
- `0x18001a320`
- `0x18001ba20`
- `0x18001ece0`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001badc`
- `OLEAUT32!__imp_SysAllocString` at `0x18001badc`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::GetAutoUpdatePolicy(wchar_t **a1)
{
  int Policy; // ebx
  struct tagUpdatePolicyValue_V1 *v3; // r9
  int v4; // ecx
  int v5; // ecx
  int v6; // eax
  wchar_t *v7; // rax
  struct tagUpdatePolicyValue_V1 *v9[2]; // [rsp+20h] [rbp-60h] BYREF
  OLECHAR psz[32]; // [rsp+30h] [rbp-50h] BYREF

  v9[0] = 0;
  if ( !a1 )
  {
    Policy = -2147467261;
    goto LABEL_15;
  }
  Policy = UpdatePolicyReader::ReadPolicy(3u, v9);
  if ( Policy < 0 )
    goto LABEL_15;
  v3 = v9[0];
  if ( !*((_DWORD *)v9[0] + 1) )
  {
    UpdatePolicyReader::ReleaseUpdatePolicyValue(v9);
    Policy = UpdatePolicyReader::ReadPolicy(7u, v9);
    if ( Policy < 0 )
      goto LABEL_15;
    v3 = v9[0];
  }
  if ( *((_DWORD *)v3 + 1) == 1 )
  {
    v4 = *((_DWORD *)v3 + 2);
    if ( v4 )
    {
      v5 = v4 - 1;
      if ( !v5 )
      {
        v6 = StringCchPrintfW(psz, 0x20u, L"GP|%ld", *((unsigned int *)v3 + 6), v9[0]);
        goto LABEL_12;
      }
      if ( v5 == 1 )
      {
        v6 = StringCchPrintfW(psz, 0x20u, L"MDM|%ld", *((unsigned int *)v3 + 6), v9[0]);
        goto LABEL_12;
      }
    }
  }
  v6 = StringCchPrintfW(psz, 0x20u, L"Default|4");
LABEL_12:
  Policy = v6;
  if ( v6 >= 0 )
  {
    v7 = SysAllocString(psz);
    *a1 = v7;
    if ( !v7 )
      Policy = -2147024882;
  }
LABEL_15:
  UpdatePolicyReader::ReleaseUpdatePolicyValue(v9);
  return (unsigned int)Policy;
}

```

## disassembly

```asm
0x18001ba20  mov     [rsp-8+arg_8], rbx
0x18001ba25  mov     [rsp-8+arg_10], rdi
0x18001ba2a  push    rbp
0x18001ba2b  mov     rbp, rsp
0x18001ba2e  sub     rsp, 80h
0x18001ba35  mov     rax, cs:__security_cookie
0x18001ba3c  xor     rax, rsp
0x18001ba3f  mov     [rbp+var_10], rax
0x18001ba43  mov     [rbp+var_60], 0
0x18001ba4b  mov     rdi, rcx
0x18001ba4e  test    rcx, rcx
0x18001ba51  jnz     short loc_18001BA5D
0x18001ba53  mov     ebx, 80004003h
0x18001ba58  jmp     loc_18001BAF0
0x18001ba5d  lea     rdx, [rbp+var_60]
0x18001ba61  mov     ecx, 3
0x18001ba66  call    ?ReadPolicy@UpdatePolicyReader@@SAJW4tagUpdatePolicy@@PEAPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadPolicy(tagUpdatePolicy,tagUpdatePolicyValue_V1 * *)
0x18001ba6b  mov     ebx, eax
0x18001ba6d  test    eax, eax
0x18001ba6f  js      short loc_18001BAF0
0x18001ba71  mov     r9, [rbp+var_60]
0x18001ba75  cmp     dword ptr [r9+4], 0
0x18001ba7a  jnz     short loc_18001BA9D
0x18001ba7c  lea     rcx, [rbp+var_60]; struct tagUpdatePolicyValue_V1 **
0x18001ba80  call    ?ReleaseUpdatePolicyValue@UpdatePolicyReader@@SAJPEAPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReleaseUpdatePolicyValue(tagUpdatePolicyValue_V1 * *)
0x18001ba85  lea     rdx, [rbp+var_60]
0x18001ba89  mov     ecx, 7
0x18001ba8e  call    ?ReadPolicy@UpdatePolicyReader@@SAJW4tagUpdatePolicy@@PEAPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadPolicy(tagUpdatePolicy,tagUpdatePolicyValue_V1 * *)
0x18001ba93  mov     ebx, eax
0x18001ba95  test    eax, eax
0x18001ba97  js      short loc_18001BAF0
0x18001ba99  mov     r9, [rbp+var_60]
0x18001ba9d  cmp     dword ptr [r9+4], 1
0x18001baa2  jnz     short loc_18001BABD
0x18001baa4  mov     ecx, [r9+8]
0x18001baa8  test    ecx, ecx
0x18001baaa  jz      short loc_18001BABD
0x18001baac  sub     ecx, 1
0x18001baaf  jz      loc_18001BB37
0x18001bab5  sub     ecx, 1
0x18001bab8  jz      short loc_18001BB1C
0x18001baba  sub     ecx, 1
0x18001babd  lea     r8, aDefault4; "Default|4"
0x18001bac4  mov     edx, 20h ; ' '; unsigned __int64
0x18001bac9  lea     rcx, [rbp+psz]; Buffer
0x18001bacd  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001bad2  mov     ebx, eax
0x18001bad4  test    eax, eax
0x18001bad6  js      short loc_18001BAF0
0x18001bad8  lea     rcx, [rbp+psz]; psz
0x18001badc  call    cs:__imp_SysAllocString
0x18001bae2  test    rax, rax
0x18001bae5  mov     [rdi], rax
0x18001bae8  mov     ecx, 8007000Eh
0x18001baed  cmovz   ebx, ecx
0x18001baf0  lea     rcx, [rbp+var_60]; struct tagUpdatePolicyValue_V1 **
0x18001baf4  call    ?ReleaseUpdatePolicyValue@UpdatePolicyReader@@SAJPEAPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReleaseUpdatePolicyValue(tagUpdatePolicyValue_V1 * *)
0x18001baf9  mov     eax, ebx
0x18001bafb  mov     rcx, [rbp+var_10]
0x18001baff  xor     rcx, rsp; StackCookie
0x18001bb02  call    __security_check_cookie
0x18001bb07  lea     r11, [rsp+80h+var_s0]
0x18001bb0f  mov     rbx, [r11+18h]
0x18001bb13  mov     rdi, [r11+20h]
0x18001bb17  mov     rsp, r11
0x18001bb1a  pop     rbp
0x18001bb1b  retn
0x18001bb1c  lea     r8, aMdmLd; "MDM|%ld"
0x18001bb23  mov     r9d, [r9+18h]
0x18001bb27  lea     rcx, [rbp+psz]; Buffer
0x18001bb2b  mov     edx, 20h ; ' '; unsigned __int64
0x18001bb30  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001bb35  jmp     short loc_18001BAD2
0x18001bb37  lea     r8, aGpLd; "GP|%ld"
0x18001bb3e  jmp     short loc_18001BB23
```
