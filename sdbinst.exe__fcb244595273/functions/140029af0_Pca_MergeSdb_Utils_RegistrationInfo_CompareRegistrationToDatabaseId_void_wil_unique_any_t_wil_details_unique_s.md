# Pca::MergeSdb::Utils::RegistrationInfo::CompareRegistrationToDatabaseId(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,bool &)

- ea: `0x140029af0`
- end: `0x140029b9a`
- name: `?CompareRegistrationToDatabaseId@RegistrationInfo@Utils@MergeSdb@Pca@@SAKPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEA_N@Z`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD *, HKEY *, _BYTE *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14001008c`
- `0x140029af0`
- `0x14002d220`
- `0x14002e420`

## string_xrefs

- `0x140029b3d`: `Failed to read database id from a registration key (%d)`
- `0x140029b4e`: `Pca::MergeSdb::Utils::RegistrationInfo::CompareRegistrationToDatabaseId`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegistrationInfo::CompareRegistrationToDatabaseId(
        _QWORD *a1,
        HKEY *a2,
        _BYTE *a3)
{
  HKEY v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // edi
  struct _GUID v9; // [rsp+30h] [rbp-28h] BYREF

  *a3 = 0;
  v5 = *a2;
  v9 = 0;
  v6 = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(v5, L"DatabaseId", &v9);
  v7 = v6;
  if ( v6 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::CompareRegistrationToDatabaseId",
      924,
      "Failed to read database id from a registration key (%d)",
      v6);
    return v7;
  }
  else
  {
    if ( *a1 == *(_QWORD *)&v9.Data1 && a1[1] == *(_QWORD *)v9.Data4 )
      *a3 = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x140029af0  mov     [rsp+arg_0], rbx
0x140029af5  mov     [rsp+arg_18], rsi
0x140029afa  push    rdi
0x140029afb  sub     rsp, 50h
0x140029aff  mov     rax, cs:__security_cookie
0x140029b06  xor     rax, rsp
0x140029b09  mov     [rsp+58h+var_18], rax
0x140029b0e  mov     rax, rdx
0x140029b11  mov     byte ptr [r8], 0
0x140029b15  mov     rsi, r8
0x140029b18  lea     rdx, ?REG_VALUE_NAME_DATABASE_ID@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "DatabaseId"
0x140029b1f  mov     rbx, rcx
0x140029b22  lea     r8, [rsp+58h+var_28]; struct _GUID *
0x140029b27  xorps   xmm0, xmm0
0x140029b2a  mov     rcx, [rax]; HKEY
0x140029b2d  movups  xmmword ptr [rsp+58h+var_28.Data1], xmm0
0x140029b32  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAU_GUID@@@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,_GUID &)
0x140029b37  mov     edi, eax
0x140029b39  test    eax, eax
0x140029b3b  jz      short loc_140029B63
0x140029b3d  lea     r9, aFailedToReadDa; "Failed to read database id from a regis"...
0x140029b44  mov     [rsp+58h+var_38], eax
0x140029b48  mov     r8d, 39Ch
0x140029b4e  lea     rdx, aPcaMergesdbUti_17; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x140029b55  mov     ecx, 1
0x140029b5a  call    AslLogCallPrintf
0x140029b5f  mov     eax, edi
0x140029b61  jmp     short loc_140029B7D
0x140029b63  mov     rax, [rbx]
0x140029b66  cmp     rax, qword ptr [rsp+58h+var_28.Data1]
0x140029b6b  jnz     short loc_140029B7B
0x140029b6d  mov     rax, [rbx+8]
0x140029b71  cmp     rax, qword ptr [rsp+58h+var_28.Data4]
0x140029b76  jnz     short loc_140029B7B
0x140029b78  mov     byte ptr [rsi], 1
0x140029b7b  xor     eax, eax
0x140029b7d  mov     rcx, [rsp+58h+var_18]
0x140029b82  xor     rcx, rsp; StackCookie
0x140029b85  call    __security_check_cookie
0x140029b8a  mov     rbx, [rsp+58h+arg_0]
0x140029b8f  mov     rsi, [rsp+58h+arg_18]
0x140029b94  add     rsp, 50h
0x140029b98  pop     rdi
0x140029b99  retn
```
