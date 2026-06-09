# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x1800e0988`
- end: `0x1800e0afd`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `373`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800e07ec`

## callees

- `0x180054ad4`
- `0x1800e0250`
- `0x1800e02c8`
- `0x1800e0988`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800e0a80`
- `ntdll!RtlInitUnicodeString` at `0x1800e0a80`
- `ntdll!RtlCompareUnicodeString` at `0x1800e0ab2`
- `ntdll!RtlCompareUnicodeString` at `0x1800e0ab2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800e09e8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800e0a56`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800e09e8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800e0a56`
- `ntdll!NtQueryInformationToken` at `0x1800e09c5`
- `ntdll!NtQueryInformationToken` at `0x1800e0a44`
- `ntdll!NtQueryInformationToken` at `0x1800e09c5`
- `ntdll!NtQueryInformationToken` at `0x1800e0a44`

## pseudocode

```c
ULONG __fastcall ARI::ProcessToken::SysAppId::Open(
        HANDLE TokenHandle,
        _QWORD *a2,
        struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v7; // eax
  void *v9; // rax
  void *v10; // rdx
  void *v11; // rbx
  int v12; // ebx
  int v13; // eax
  ULONG v14; // edi
  __int64 v15; // rdi
  struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v16; // rsi
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  __int128 v18; // [rsp+40h] [rbp-28h]
  ULONG Size; // [rsp+88h] [rbp+20h] BYREF
  int Size_4; // [rsp+8Ch] [rbp+24h]

  Size_4 = HIDWORD(a4);
  Size = 0;
  v7 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &Size);
  if ( v7 == -1073741789 )
  {
    v9 = (void *)ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(Size);
    v11 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, Size);
      v13 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, v11, Size, &Size);
      if ( v13 >= 0 )
      {
        if ( *((_DWORD *)v11 + 1) )
        {
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
          v15 = 0;
          v18 = 0;
          while ( (unsigned int)v15 < *((_DWORD *)v11 + 1) )
          {
            v16 = (struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)(*((_QWORD *)v11 + 1) + 40 * v15);
            if ( !RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)v16, 1u) )
            {
              *a3 = v16;
              *a2 = v11;
              v12 = 0;
              goto LABEL_15;
            }
            v15 = (unsigned int)(v15 + 1);
          }
        }
        v14 = 1168;
      }
      else
      {
        v14 = RtlNtStatusToDosErrorNoTeb(v13);
      }
      ARI::Free(v11, v10);
      return v14;
    }
    else
    {
      v12 = 8;
LABEL_15:
      ARI::Free(0, v10);
      return v12;
    }
  }
  else if ( v7 )
  {
    return RtlNtStatusToDosErrorNoTeb(v7);
  }
  else
  {
    return 1359;
  }
}

```

## disassembly

```asm
0x1800e0988  mov     rax, rsp
0x1800e098b  mov     [rax+8], rbx
0x1800e098f  mov     [rax+10h], rsi
0x1800e0993  mov     [rax+20h], r9
0x1800e0997  push    rdi
0x1800e0998  push    r14
0x1800e099a  push    r15
0x1800e099c  sub     rsp, 50h
0x1800e09a0  xor     r9d, r9d; TokenInformationLength
0x1800e09a3  mov     dword ptr [rax+20h], 0
0x1800e09aa  mov     r14, r8
0x1800e09ad  lea     rax, [rax+20h]
0x1800e09b1  mov     r15, rdx
0x1800e09b4  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800e09b9  xor     r8d, r8d; TokenInformation
0x1800e09bc  mov     rdi, rcx
0x1800e09bf  lea     esi, [r9+27h]
0x1800e09c3  mov     edx, esi; TokenInformationClass
0x1800e09c5  call    cs:__imp_NtQueryInformationToken
0x1800e09cc  nop     dword ptr [rax+rax+00h]
0x1800e09d1  cmp     eax, 0C0000023h
0x1800e09d6  jz      short loc_1800E09F9
0x1800e09d8  test    eax, eax
0x1800e09da  jnz     short loc_1800E09E6
0x1800e09dc  mov     eax, 54Fh
0x1800e09e1  jmp     loc_1800E0AE8
0x1800e09e6  mov     ecx, eax; Status
0x1800e09e8  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800e09ef  nop     dword ptr [rax+rax+00h]
0x1800e09f4  jmp     loc_1800E0AE8
0x1800e09f9  mov     ecx, dword ptr [rsp+68h+Size]
0x1800e0a00  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x1800e0a05  mov     rbx, rax
0x1800e0a08  test    rax, rax
0x1800e0a0b  jnz     short loc_1800E0A15
0x1800e0a0d  lea     ebx, [rax+8]
0x1800e0a10  jmp     loc_1800E0ACE
0x1800e0a15  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x1800e0a1d  xor     edx, edx; Val
0x1800e0a1f  mov     rcx, rbx; void *
0x1800e0a22  call    memset_0
0x1800e0a27  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x1800e0a2f  lea     rax, [rsp+68h+Size]
0x1800e0a37  mov     r8, rbx; TokenInformation
0x1800e0a3a  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800e0a3f  mov     edx, esi; TokenInformationClass
0x1800e0a41  mov     rcx, rdi; TokenHandle
0x1800e0a44  call    cs:__imp_NtQueryInformationToken
0x1800e0a4b  nop     dword ptr [rax+rax+00h]
0x1800e0a50  test    eax, eax
0x1800e0a52  jns     short loc_1800E0A66
0x1800e0a54  mov     ecx, eax; Status
0x1800e0a56  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800e0a5d  nop     dword ptr [rax+rax+00h]
0x1800e0a62  mov     edi, eax
0x1800e0a64  jmp     short loc_1800E0ADE
0x1800e0a66  cmp     dword ptr [rbx+4], 0
0x1800e0a6a  jbe     short loc_1800E0AD9
0x1800e0a6c  xorps   xmm0, xmm0
0x1800e0a6f  lea     rdx, SourceString; "WIN://SYSAPPID"
0x1800e0a76  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800e0a7b  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800e0a80  call    cs:__imp_RtlInitUnicodeString
0x1800e0a87  nop     dword ptr [rax+rax+00h]
0x1800e0a8c  xorps   xmm0, xmm0
0x1800e0a8f  xor     edi, edi
0x1800e0a91  movups  [rsp+68h+var_28], xmm0
0x1800e0a96  cmp     edi, [rbx+4]
0x1800e0a99  jnb     short loc_1800E0AD9
0x1800e0a9b  mov     rax, [rbx+8]
0x1800e0a9f  lea     rcx, [rdi+rdi*4]
0x1800e0aa3  mov     r8b, 1; CaseInsensitive
0x1800e0aa6  lea     rsi, [rax+rcx*8]
0x1800e0aaa  mov     rdx, rsi; String2
0x1800e0aad  lea     rcx, [rsp+68h+DestinationString]; String1
0x1800e0ab2  call    cs:__imp_RtlCompareUnicodeString
0x1800e0ab9  nop     dword ptr [rax+rax+00h]
0x1800e0abe  test    eax, eax
0x1800e0ac0  jz      short loc_1800E0AC6
0x1800e0ac2  inc     edi
0x1800e0ac4  jmp     short loc_1800E0A96
0x1800e0ac6  mov     [r14], rsi
0x1800e0ac9  mov     [r15], rbx
0x1800e0acc  xor     ebx, ebx
0x1800e0ace  xor     ecx, ecx; P
0x1800e0ad0  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800e0ad5  mov     eax, ebx
0x1800e0ad7  jmp     short loc_1800E0AE8
0x1800e0ad9  mov     edi, 490h
0x1800e0ade  mov     rcx, rbx; P
0x1800e0ae1  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800e0ae6  mov     eax, edi
0x1800e0ae8  mov     rbx, [rsp+68h+arg_0]
0x1800e0aed  mov     rsi, [rsp+68h+arg_8]
0x1800e0af2  add     rsp, 50h
0x1800e0af6  pop     r15
0x1800e0af8  pop     r14
0x1800e0afa  pop     rdi
0x1800e0afb  retn
```
