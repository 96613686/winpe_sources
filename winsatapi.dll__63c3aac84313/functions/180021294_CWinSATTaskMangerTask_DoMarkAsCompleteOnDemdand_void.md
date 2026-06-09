# CWinSATTaskMangerTask::DoMarkAsCompleteOnDemdand(void)

- ea: `0x180021294`
- end: `0x1800213c7`
- name: `?DoMarkAsCompleteOnDemdand@CWinSATTaskMangerTask@@AEAAXXZ`
- size: `307`
- prototype: `void __fastcall(CWinSATTaskMangerTask *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020dcc`

## callees

- `0x18001c414`
- `0x180021294`
- `0x1800214fc`
- `0x1800218c0`
- `0x18002bb04`
- `0x18002bd2c`
- `0x18002bed4`

## import_xrefs

- `msvcrt!_time64` at `0x1800212f6`
- `msvcrt!_time64` at `0x1800212f6`

## string_xrefs

- `0x180021324`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x1800213ab`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021315`: `Cannot save %s to the registry`
- `0x180021397`: `Cannot save %s to the registry`
- `0x18002135b`: `Cannot read %s from the registry`
- `0x1800212de`: `Cannot determine if %s exists in the registry`
- `0x1800212d2`: `FirstIdleCompletionTimeDate`
- `0x1800212fc`: `FirstIdleCompletionTimeDate`
- `0x180021384`: `FirstIdleAssessmentCompletionDuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CWinSATTaskMangerTask::DoMarkAsCompleteOnDemdand(CWinSATTaskMangerTask *this)
{
  __int64 v1; // rdx
  DWORD v2; // ecx
  const wchar_t *v3; // rbx
  __time64_t v4; // rdi
  __int64 v5; // rcx
  CWinSATTaskMangerTask *v6; // rcx
  __int64 v7; // rcx
  unsigned int v8; // [rsp+48h] [rbp+18h] BYREF
  unsigned __int64 v9; // [rsp+50h] [rbp+20h] BYREF

  LOBYTE(v8) = 0;
  if ( !CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(this, (bool *)&v8) || !(_BYTE)v8 )
  {
    LOBYTE(v8) = 0;
    if ( (unsigned int)RegHelper::DoesValueExist(v2, v1, &v8) )
    {
      v3 = L"FirstIdleCompletionTimeDate";
LABEL_10:
      Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", (char)v3);
      return;
    }
    if ( !(_BYTE)v8 )
    {
      v4 = _time64(0);
      if ( (unsigned int)RegHelper::WriteQWORDValue(v5, L"FirstIdleCompletionTimeDate", v4) )
        Record_Win32Error_w(
          "base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp",
          (char)L"FirstIdleCompletionTimeDate");
      v9 = 0;
      v3 = (const wchar_t *)L"FirstIdleRunTimeDate";
      if ( (unsigned int)RegHelper::ReadQWORDValue(1, L"FirstIdleRunTimeDate", &v9) )
        goto LABEL_10;
      v8 = 0;
      CWinSATTaskMangerTask::SQMFirstCompletionDuration(v6, v9, v4, &v8);
      v3 = L"FirstIdleAssessmentCompletionDuration";
      if ( (unsigned int)RegHelper::WriteQWORDValue(v7, L"FirstIdleAssessmentCompletionDuration", v8) )
        goto LABEL_10;
    }
  }
}

```

## disassembly

```asm
0x180021294  mov     [rsp-8+arg_0], rbx
0x180021299  mov     [rsp-8+arg_18], rdi
0x18002129e  push    rbp
0x18002129f  mov     rbp, rsp
0x1800212a2  sub     rsp, 30h
0x1800212a6  lea     rdx, [rbp+arg_8]; bool *
0x1800212aa  mov     byte ptr [rbp+arg_8], 0
0x1800212ae  call    ?HasIdleWinSATCompletedOnce@CWinSATTaskMangerTask@@AEAA_NAEA_N@Z; CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(bool &)
0x1800212b3  test    al, al
0x1800212b5  jz      short loc_1800212C1
0x1800212b7  cmp     byte ptr [rbp+arg_8], 0
0x1800212bb  jnz     loc_1800213B7
0x1800212c1  lea     r8, [rbp+arg_8]
0x1800212c5  mov     byte ptr [rbp+arg_8], 0
0x1800212c9  call    ?DoesValueExist@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEA_N@Z; RegHelper::DoesValueExist(WinSATRegistryKeys::Enum,ushort const *,bool &)
0x1800212ce  test    eax, eax
0x1800212d0  jz      short loc_1800212EA
0x1800212d2  lea     rbx, ValueName; "FirstIdleCompletionTimeDate"
0x1800212d9  mov     edx, 1A0h
0x1800212de  lea     r9, aCannotDetermin; "Cannot determine if %s exists in the re"...
0x1800212e5  jmp     loc_1800213A3
0x1800212ea  cmp     byte ptr [rbp+arg_8], 0
0x1800212ee  jnz     loc_1800213B7
0x1800212f4  xor     ecx, ecx; Time
0x1800212f6  call    cs:__imp__time64
0x1800212fc  lea     rbx, ValueName; "FirstIdleCompletionTimeDate"
0x180021303  mov     r8, rax
0x180021306  mov     rdx, rbx
0x180021309  mov     rdi, rax
0x18002130c  call    ?WriteQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBG_K@Z; RegHelper::WriteQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64)
0x180021311  test    eax, eax
0x180021313  jz      short loc_180021335
0x180021315  lea     r9, aCannotSaveSToT; "Cannot save %s to the registry"
0x18002131c  mov     qword ptr [rsp+30h+var_10], rbx; char
0x180021321  mov     r8d, eax
0x180021324  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x18002132b  mov     edx, 1B4h
0x180021330  call    Record_Win32Error_w
0x180021335  xor     r9d, r9d
0x180021338  mov     [rbp+arg_10], 0
0x180021340  lea     rbx, aFirstidlerunti; "FirstIdleRunTimeDate"
0x180021347  lea     r8, [rbp+arg_10]
0x18002134b  mov     rdx, rbx
0x18002134e  lea     ecx, [r9+1]
0x180021352  call    ?ReadQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEA_KPEA_N@Z; RegHelper::ReadQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64 &,bool *)
0x180021357  test    eax, eax
0x180021359  jz      short loc_180021369
0x18002135b  lea     r9, aCannotReadSFro; "Cannot read %s from the registry"
0x180021362  mov     edx, 1C1h
0x180021367  jmp     short loc_1800213A3
0x180021369  mov     rdx, [rbp+arg_10]; unsigned __int64
0x18002136d  lea     r9, [rbp+arg_8]; unsigned int *
0x180021371  mov     r8, rdi; unsigned __int64
0x180021374  mov     [rbp+arg_8], 0
0x18002137b  call    ?SQMFirstCompletionDuration@CWinSATTaskMangerTask@@AEAAX_K0AEAK@Z; CWinSATTaskMangerTask::SQMFirstCompletionDuration(unsigned __int64,unsigned __int64,ulong &)
0x180021380  mov     r8d, [rbp+arg_8]
0x180021384  lea     rbx, aFirstidleasses; "FirstIdleAssessmentCompletionDuration"
0x18002138b  mov     rdx, rbx
0x18002138e  call    ?WriteQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBG_K@Z; RegHelper::WriteQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64)
0x180021393  test    eax, eax
0x180021395  jz      short loc_1800213B7
0x180021397  lea     r9, aCannotSaveSToT; "Cannot save %s to the registry"
0x18002139e  mov     edx, 1CFh
0x1800213a3  mov     r8d, eax
0x1800213a6  mov     qword ptr [rsp+30h+var_10], rbx; char
0x1800213ab  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x1800213b2  call    Record_Win32Error_w
0x1800213b7  mov     rbx, [rsp+30h+arg_0]
0x1800213bc  mov     rdi, [rsp+30h+arg_18]
0x1800213c1  add     rsp, 30h
0x1800213c5  pop     rbp
0x1800213c6  retn
```
