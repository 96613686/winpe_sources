# Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,Pca::MergeSdb::Utils::RegValue &)

- ea: `0x14002d418`
- end: `0x14002d614`
- name: `?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAVRegValue@234@@Z`
- size: `508`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, struct Pca::MergeSdb::Utils::RegValue *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x140024958`

## callees

- `0x1400025f8`
- `0x14001008c`
- `0x14002d418`
- `0x14002e0a4`
- `0x14002e3e2`
- `0x14002e420`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x14002d48c`
- `ADVAPI32!RegQueryValueExW` at `0x14002d53b`
- `ADVAPI32!RegQueryValueExW` at `0x14002d48c`
- `ADVAPI32!RegQueryValueExW` at `0x14002d53b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002d5a0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002d5ad`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002d5a0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002d5ad`

## string_xrefs

- `0x14002d4ab`: `Failed to read registry value (%d)`
- `0x14002d547`: `Failed to read registry value (%d)`
- `0x14002d4bc`: `Pca::MergeSdb::Utils::RegUtil::ReadRegValue`
- `0x14002d58b`: `Pca::MergeSdb::Utils::RegUtil::ReadRegValue`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegUtil::ReadRegValue(
        HKEY hKey,
        const unsigned __int16 *a2,
        struct Pca::MergeSdb::Utils::RegValue *a3)
{
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 v8; // r8
  DWORD v10; // edi
  BYTE *v11; // rax
  BYTE *v12; // rbx
  LSTATUS v13; // eax
  unsigned int v14; // edi
  const char *v15; // r9
  __int64 v16; // r8
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  LPBYTE lpDataa; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  BYTE *v21; // [rsp+38h] [rbp-C8h]
  BYTE Data[256]; // [rsp+40h] [rbp-C0h] BYREF

  memset_0(Data, 0, sizeof(Data));
  cbData = 256;
  Type = 0;
  v5 = RegQueryValueExW(hKey, L"DisableMergeSdbs", 0, &Type, Data, &cbData);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 != 234 )
    {
      if ( (unsigned int)(v5 - 2) <= 1 )
        return v6;
      v7 = "Failed to read registry value (%d)";
      v8 = 157;
LABEL_5:
      LODWORD(lpData) = v6;
      AslLogCallPrintf(1, "Pca::MergeSdb::Utils::RegUtil::ReadRegValue", v8, v7, lpData);
      return v6;
    }
    cbData += 2;
    v10 = cbData;
    v11 = (BYTE *)operator new[](cbData, (const struct std::nothrow_t *)&std::nothrow);
    v12 = v11;
    if ( v11 )
      memset_0(v11, 0, v10);
    else
      v12 = 0;
    v21 = v12;
    if ( !v12 )
      return 14;
    v13 = RegQueryValueExW(hKey, L"DisableMergeSdbs", 0, &Type, v12, &cbData);
    v14 = v13;
    if ( v13 )
    {
      v15 = "Failed to read registry value (%d)";
      v16 = 175;
LABEL_16:
      LODWORD(lpDataa) = v13;
      AslLogCallPrintf(1, "Pca::MergeSdb::Utils::RegUtil::ReadRegValue", v16, v15, lpDataa);
      operator delete[](v12);
      return v14;
    }
    v13 = Pca::MergeSdb::Utils::RegValue::SetValue(a3, L"DisableMergeSdbs", Type, cbData, v12);
    v14 = v13;
    if ( v13 )
    {
      v15 = "Failed to set reg value out param (%d)";
      v16 = 183;
      goto LABEL_16;
    }
    operator delete[](v12);
  }
  else
  {
    v6 = Pca::MergeSdb::Utils::RegValue::SetValue(a3, L"DisableMergeSdbs", Type, cbData, Data);
    if ( v6 )
    {
      v7 = "Failed to set reg value out param (%d)";
      v8 = 191;
      goto LABEL_5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14002d418  mov     [rsp-8+arg_8], rbx
0x14002d41d  mov     [rsp-8+arg_18], rsi
0x14002d422  push    rbp
0x14002d423  push    rdi
0x14002d424  push    r14
0x14002d426  lea     rbp, [rsp-50h]
0x14002d42b  sub     rsp, 150h
0x14002d432  mov     rax, cs:__security_cookie
0x14002d439  xor     rax, rsp
0x14002d43c  mov     [rbp+60h+var_20], rax
0x14002d440  mov     rsi, r8
0x14002d443  mov     r14, rcx
0x14002d446  mov     ebx, 100h
0x14002d44b  mov     r8d, ebx; Size
0x14002d44e  xor     edx, edx; Val
0x14002d450  lea     rcx, [rsp+160h+Data]; void *
0x14002d455  call    memset_0
0x14002d45a  mov     [rsp+160h+cbData], ebx
0x14002d45e  mov     [rsp+160h+Type], 0
0x14002d466  lea     rax, [rsp+160h+cbData]
0x14002d46b  mov     [rsp+160h+lpcbData], rax; lpcbData
0x14002d470  lea     rax, [rsp+160h+Data]
0x14002d475  mov     [rsp+160h+lpData], rax; lpData
0x14002d47a  lea     r9, [rsp+160h+Type]; lpType
0x14002d47f  xor     r8d, r8d; lpReserved
0x14002d482  lea     rdx, aDisablemergesd; "DisableMergeSdbs"
0x14002d489  mov     rcx, r14; hKey
0x14002d48c  call    cs:__imp_RegQueryValueExW
0x14002d492  mov     ebx, eax
0x14002d494  test    eax, eax
0x14002d496  jz      loc_14002D5D9
0x14002d49c  cmp     eax, 0EAh
0x14002d4a1  jz      short loc_14002D4D4
0x14002d4a3  lea     ecx, [rax-2]
0x14002d4a6  cmp     ecx, 1
0x14002d4a9  jbe     short loc_14002D4CD
0x14002d4ab  lea     r9, aFailedToReadRe; "Failed to read registry value (%d)"
0x14002d4b2  mov     r8d, 9Dh
0x14002d4b8  mov     dword ptr [rsp+160h+lpData], ebx
0x14002d4bc  lea     rdx, aPcaMergesdbUti_14; "Pca::MergeSdb::Utils::RegUtil::ReadRegV"...
0x14002d4c3  mov     ecx, 1
0x14002d4c8  call    AslLogCallPrintf
0x14002d4cd  mov     eax, ebx
0x14002d4cf  jmp     loc_14002D5B5
0x14002d4d4  mov     eax, [rsp+160h+cbData]
0x14002d4d8  add     eax, 2
0x14002d4db  mov     [rsp+160h+cbData], eax
0x14002d4df  mov     edi, eax
0x14002d4e1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002d4e8  mov     ecx, eax; unsigned __int64
0x14002d4ea  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002d4ef  mov     rbx, rax
0x14002d4f2  test    rax, rax
0x14002d4f5  jz      short loc_14002D506
0x14002d4f7  mov     r8d, edi; Size
0x14002d4fa  xor     edx, edx; Val
0x14002d4fc  mov     rcx, rax; void *
0x14002d4ff  call    memset_0
0x14002d504  jmp     short loc_14002D508
0x14002d506  xor     ebx, ebx
0x14002d508  mov     [rsp+160h+var_128], rbx
0x14002d50d  test    rbx, rbx
0x14002d510  jnz     short loc_14002D51A
0x14002d512  lea     eax, [rbx+0Eh]
0x14002d515  jmp     loc_14002D5B5
0x14002d51a  lea     rax, [rsp+160h+cbData]
0x14002d51f  mov     [rsp+160h+lpcbData], rax; lpcbData
0x14002d524  mov     [rsp+160h+lpData], rbx; lpData
0x14002d529  lea     r9, [rsp+160h+Type]; lpType
0x14002d52e  xor     r8d, r8d; lpReserved
0x14002d531  lea     rdx, aDisablemergesd; "DisableMergeSdbs"
0x14002d538  mov     rcx, r14; hKey
0x14002d53b  call    cs:__imp_RegQueryValueExW
0x14002d541  mov     edi, eax
0x14002d543  test    eax, eax
0x14002d545  jz      short loc_14002D556
0x14002d547  lea     r9, aFailedToReadRe; "Failed to read registry value (%d)"
0x14002d54e  mov     r8d, 0AFh
0x14002d554  jmp     short loc_14002D587
0x14002d556  mov     [rsp+160h+lpData], rbx; unsigned __int8 *
0x14002d55b  mov     r9d, [rsp+160h+cbData]; unsigned int
0x14002d560  mov     r8d, [rsp+160h+Type]; unsigned int
0x14002d565  lea     rdx, aDisablemergesd; "DisableMergeSdbs"
0x14002d56c  mov     rcx, rsi; this
0x14002d56f  call    ?SetValue@RegValue@Utils@MergeSdb@Pca@@QEAAKPEBGKKPEBE@Z; Pca::MergeSdb::Utils::RegValue::SetValue(ushort const *,ulong,ulong,uchar const *)
0x14002d574  mov     edi, eax
0x14002d576  test    eax, eax
0x14002d578  jz      short loc_14002D5AA
0x14002d57a  lea     r9, aFailedToSetReg; "Failed to set reg value out param (%d)"
0x14002d581  mov     r8d, 0B7h
0x14002d587  mov     dword ptr [rsp+160h+lpData], eax
0x14002d58b  lea     rdx, aPcaMergesdbUti_14; "Pca::MergeSdb::Utils::RegUtil::ReadRegV"...
0x14002d592  mov     ecx, 1
0x14002d597  call    AslLogCallPrintf
0x14002d59c  nop
0x14002d59d  mov     rcx, rbx
0x14002d5a0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14002d5a6  mov     eax, edi
0x14002d5a8  jmp     short loc_14002D5B5
0x14002d5aa  mov     rcx, rbx
0x14002d5ad  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14002d5b3  xor     eax, eax
0x14002d5b5  mov     rcx, [rbp+60h+var_20]
0x14002d5b9  xor     rcx, rsp; StackCookie
0x14002d5bc  call    __security_check_cookie
0x14002d5c1  lea     r11, [rsp+160h+var_10]
0x14002d5c9  mov     rbx, [r11+28h]
0x14002d5cd  mov     rsi, [r11+38h]
0x14002d5d1  mov     rsp, r11
0x14002d5d4  pop     r14
0x14002d5d6  pop     rdi
0x14002d5d7  pop     rbp
0x14002d5d8  retn
0x14002d5d9  lea     rax, [rsp+160h+Data]
0x14002d5de  mov     [rsp+160h+lpData], rax; unsigned __int8 *
0x14002d5e3  mov     r9d, [rsp+160h+cbData]; unsigned int
0x14002d5e8  mov     r8d, [rsp+160h+Type]; unsigned int
0x14002d5ed  lea     rdx, aDisablemergesd; "DisableMergeSdbs"
0x14002d5f4  mov     rcx, rsi; this
0x14002d5f7  call    ?SetValue@RegValue@Utils@MergeSdb@Pca@@QEAAKPEBGKKPEBE@Z; Pca::MergeSdb::Utils::RegValue::SetValue(ushort const *,ulong,ulong,uchar const *)
0x14002d5fc  mov     ebx, eax
0x14002d5fe  test    eax, eax
0x14002d600  jz      short loc_14002D5B3
0x14002d602  lea     r9, aFailedToSetReg; "Failed to set reg value out param (%d)"
0x14002d609  mov     r8d, 0BFh
0x14002d60f  jmp     loc_14002D4B8
```
