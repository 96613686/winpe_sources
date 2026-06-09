# WldpUninstallEndpointSecurityPolicy

- ea: `0x180036ba0`
- end: `0x180036d50`
- name: `WldpUninstallEndpointSecurityPolicy`
- size: `432`
- prototype: `__int64 __fastcall(__int64, _WORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001f038`
- `0x1800206f4`
- `0x18003611c`
- `0x1800362dc`
- `0x180036ba0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036c89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036cf9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036d1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036c89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036cf9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036d1e`
- `ntdll!NtQuerySystemInformationEx` at `0x180036cba`
- `ntdll!NtQuerySystemInformationEx` at `0x180036cba`
- `ntdll!RtlFreeUnicodeString` at `0x180036c00`
- `ntdll!RtlFreeUnicodeString` at `0x180036c71`
- `ntdll!RtlFreeUnicodeString` at `0x180036ce2`
- `ntdll!RtlFreeUnicodeString` at `0x180036d07`
- `ntdll!RtlFreeUnicodeString` at `0x180036d2c`
- `ntdll!RtlFreeUnicodeString` at `0x180036c00`
- `ntdll!RtlFreeUnicodeString` at `0x180036c71`
- `ntdll!RtlFreeUnicodeString` at `0x180036ce2`
- `ntdll!RtlFreeUnicodeString` at `0x180036d07`
- `ntdll!RtlFreeUnicodeString` at `0x180036d2c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180036bd8`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180036bd8`

## string_xrefs

- `0x180036be9`: `onecore\base\ngscb\wldp\dll\endpointsecuritypolicy.cpp`
- `0x180036c5b`: `onecore\base\ngscb\wldp\dll\endpointsecuritypolicy.cpp`
- `0x180036ccb`: `onecore\base\ngscb\wldp\dll\endpointsecuritypolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WldpUninstallEndpointSecurityPolicy(__int64 a1, _WORD *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // eax
  unsigned int v8; // ebx
  HLOCAL v9; // rcx
  HLOCAL v10; // rbx
  int SystemInformation; // eax
  unsigned int v12; // edi
  int v13; // [rsp+20h] [rbp-30h]
  int v14; // [rsp+20h] [rbp-30h]
  HLOCAL hMem; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  unsigned int v18; // [rsp+70h] [rbp+20h] BYREF

  hMem = 0;
  v18 = 0;
  UnicodeString = 0;
  v4 = RtlDosPathNameToNtPathName_U_WithStatus(a1, &UnicodeString, 0, 0);
  if ( v4 >= 0 )
  {
    if ( a1 && a2 && IsValidIdentityEku((__int64)a2) )
    {
      v7 = SetupBuffer(1, (const void **)&UnicodeString, a2, &v18, &hMem);
      v8 = v7;
      if ( v7 >= 0 )
      {
        v10 = hMem;
        SystemInformation = NtQuerySystemInformationEx(256, hMem, v18, 0);
        if ( SystemInformation >= 0 )
        {
          RtlFreeUnicodeString(&UnicodeString);
          hMem = 0;
          if ( v10 )
            LocalFree(v10);
          return 0;
        }
        else
        {
          v12 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x122,
                  (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\endpointsecuritypolicy.cpp",
                  (const char *)(unsigned int)SystemInformation,
                  0);
          RtlFreeUnicodeString(&UnicodeString);
          hMem = 0;
          if ( v10 )
            LocalFree(v10);
          return v12;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11A,
          (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\endpointsecuritypolicy.cpp",
          (const char *)(unsigned int)v7,
          v14);
        RtlFreeUnicodeString(&UnicodeString);
        v9 = hMem;
        hMem = 0;
        if ( v9 )
          LocalFree(v9);
        return v8;
      }
    }
    else
    {
      RtlFreeUnicodeString(&UnicodeString);
      return 2147942487LL;
    }
  }
  else
  {
    v5 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x109,
           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\endpointsecuritypolicy.cpp",
           (const char *)(unsigned int)v4,
           v13);
    RtlFreeUnicodeString(&UnicodeString);
    return v5;
  }
}

```

## disassembly

```asm
0x180036ba0  mov     [rsp-8+arg_0], rbx
0x180036ba5  mov     [rsp-8+arg_8], rdi
0x180036baa  push    rbp
0x180036bab  mov     rbp, rsp
0x180036bae  sub     rsp, 50h
0x180036bb2  mov     rbx, rdx
0x180036bb5  mov     rdi, rcx
0x180036bb8  mov     [rbp+hMem], 0
0x180036bc0  mov     [rbp+arg_10], 0
0x180036bc7  xorps   xmm0, xmm0
0x180036bca  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180036bce  xor     r9d, r9d
0x180036bd1  xor     r8d, r8d
0x180036bd4  lea     rdx, [rbp+UnicodeString]
0x180036bd8  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180036bde  test    eax, eax
0x180036be0  jns     short loc_180036C0E
0x180036be2  mov     rcx, [rbp+8]; this
0x180036be6  mov     r9d, eax; char *
0x180036be9  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\wldp\\dll\\endpoi"...
0x180036bf0  mov     edx, 109h; void *
0x180036bf5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180036bfa  mov     ebx, eax
0x180036bfc  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180036c00  call    cs:__imp_RtlFreeUnicodeString
0x180036c06  nop
0x180036c07  mov     eax, ebx
0x180036c09  jmp     loc_180036D38
0x180036c0e  test    rdi, rdi
0x180036c11  jz      loc_180036D28
0x180036c17  test    rbx, rbx
0x180036c1a  jz      loc_180036D28
0x180036c20  mov     rcx, rbx
0x180036c23  call    IsValidIdentityEku
0x180036c28  test    al, al
0x180036c2a  jz      loc_180036D28
0x180036c30  lea     rax, [rbp+hMem]
0x180036c34  mov     qword ptr [rsp+50h+var_30], rax; int
0x180036c39  lea     r9, [rbp+arg_10]
0x180036c3d  mov     r8, rbx
0x180036c40  lea     rdx, [rbp+UnicodeString]
0x180036c44  mov     ecx, 1
0x180036c49  call    SetupBuffer
0x180036c4e  mov     ebx, eax
0x180036c50  test    eax, eax
0x180036c52  jns     short loc_180036C96
0x180036c54  mov     rcx, [rbp+8]; this
0x180036c58  mov     r9d, eax; char *
0x180036c5b  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\wldp\\dll\\endpoi"...
0x180036c62  mov     edx, 11Ah; void *
0x180036c67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036c6c  nop
0x180036c6d  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180036c71  call    cs:__imp_RtlFreeUnicodeString
0x180036c77  nop
0x180036c78  mov     rcx, [rbp+hMem]; hMem
0x180036c7c  mov     [rbp+hMem], 0
0x180036c84  test    rcx, rcx
0x180036c87  jz      short loc_180036C8F
0x180036c89  call    cs:__imp_LocalFree
0x180036c8f  mov     eax, ebx
0x180036c91  jmp     loc_180036D40
0x180036c96  mov     [rsp+50h+var_28], 0
0x180036c9f  mov     [rsp+50h+var_30], 0; int
0x180036ca7  xor     r9d, r9d
0x180036caa  mov     r8d, [rbp+arg_10]
0x180036cae  mov     rbx, [rbp+hMem]
0x180036cb2  mov     rdx, rbx
0x180036cb5  mov     ecx, 100h
0x180036cba  call    cs:__imp_NtQuerySystemInformationEx
0x180036cc0  test    eax, eax
0x180036cc2  jns     short loc_180036D03
0x180036cc4  mov     rcx, [rbp+8]; this
0x180036cc8  mov     r9d, eax; char *
0x180036ccb  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\wldp\\dll\\endpoi"...
0x180036cd2  mov     edx, 122h; void *
0x180036cd7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180036cdc  mov     edi, eax
0x180036cde  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180036ce2  call    cs:__imp_RtlFreeUnicodeString
0x180036ce8  nop
0x180036ce9  mov     [rbp+hMem], 0
0x180036cf1  test    rbx, rbx
0x180036cf4  jz      short loc_180036CFF
0x180036cf6  mov     rcx, rbx; hMem
0x180036cf9  call    cs:__imp_LocalFree
0x180036cff  mov     eax, edi
0x180036d01  jmp     short loc_180036D40
0x180036d03  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180036d07  call    cs:__imp_RtlFreeUnicodeString
0x180036d0d  nop
0x180036d0e  mov     [rbp+hMem], 0
0x180036d16  test    rbx, rbx
0x180036d19  jz      short loc_180036D24
0x180036d1b  mov     rcx, rbx; hMem
0x180036d1e  call    cs:__imp_LocalFree
0x180036d24  xor     eax, eax
0x180036d26  jmp     short loc_180036D40
0x180036d28  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180036d2c  call    cs:__imp_RtlFreeUnicodeString
0x180036d32  nop
0x180036d33  mov     eax, 80070057h
0x180036d38  mov     [rbp+hMem], 0
0x180036d40  mov     rbx, [rsp+50h+arg_0]
0x180036d45  mov     rdi, [rsp+50h+arg_8]
0x180036d4a  add     rsp, 50h
0x180036d4e  pop     rbp
0x180036d4f  retn
```
