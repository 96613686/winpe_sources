# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x180026d30`
- end: `0x180026e80`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026ba4`

## callees

- `0x1800268d4`
- `0x180026d30`
- `0x180026e88`
- `0x18002bc68`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180026d8a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180026dec`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180026d8a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180026dec`
- `ntdll!RtlInitUnicodeString` at `0x180026e10`
- `ntdll!RtlInitUnicodeString` at `0x180026e10`
- `ntdll!NtQueryInformationToken` at `0x180026d6d`
- `ntdll!NtQueryInformationToken` at `0x180026de0`
- `ntdll!NtQueryInformationToken` at `0x180026d6d`
- `ntdll!NtQueryInformationToken` at `0x180026de0`
- `ntdll!RtlCompareUnicodeString` at `0x180026e3c`
- `ntdll!RtlCompareUnicodeString` at `0x180026e3c`

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
0x180026d30  mov     rax, rsp
0x180026d33  mov     [rax+8], rbx
0x180026d37  mov     [rax+10h], rsi
0x180026d3b  mov     [rax+20h], r9
0x180026d3f  push    rdi
0x180026d40  push    r14
0x180026d42  push    r15
0x180026d44  sub     rsp, 50h
0x180026d48  xor     r9d, r9d; TokenInformationLength
0x180026d4b  mov     dword ptr [rax+20h], 0
0x180026d52  mov     r14, r8
0x180026d55  lea     rax, [rax+20h]
0x180026d59  mov     r15, rdx
0x180026d5c  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180026d61  xor     r8d, r8d; TokenInformation
0x180026d64  mov     rdi, rcx
0x180026d67  lea     esi, [r9+27h]
0x180026d6b  mov     edx, esi; TokenInformationClass
0x180026d6d  call    cs:__imp_NtQueryInformationToken
0x180026d73  cmp     eax, 0C0000023h
0x180026d78  jz      short loc_180026D95
0x180026d7a  test    eax, eax
0x180026d7c  jnz     short loc_180026D88
0x180026d7e  mov     eax, 54Fh
0x180026d83  jmp     loc_180026E6C
0x180026d88  mov     ecx, eax; Status
0x180026d8a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180026d90  jmp     loc_180026E6C
0x180026d95  mov     ecx, dword ptr [rsp+68h+Size]
0x180026d9c  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x180026da1  mov     rbx, rax
0x180026da4  test    rax, rax
0x180026da7  jnz     short loc_180026DB1
0x180026da9  lea     ebx, [rax+8]
0x180026dac  jmp     loc_180026E52
0x180026db1  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x180026db9  xor     edx, edx; Val
0x180026dbb  mov     rcx, rbx; void *
0x180026dbe  call    memset_0
0x180026dc3  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x180026dcb  lea     rax, [rsp+68h+Size]
0x180026dd3  mov     r8, rbx; TokenInformation
0x180026dd6  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180026ddb  mov     edx, esi; TokenInformationClass
0x180026ddd  mov     rcx, rdi; TokenHandle
0x180026de0  call    cs:__imp_NtQueryInformationToken
0x180026de6  test    eax, eax
0x180026de8  jns     short loc_180026DF6
0x180026dea  mov     ecx, eax; Status
0x180026dec  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180026df2  mov     edi, eax
0x180026df4  jmp     short loc_180026E62
0x180026df6  cmp     dword ptr [rbx+4], 0
0x180026dfa  jbe     short loc_180026E5D
0x180026dfc  xorps   xmm0, xmm0
0x180026dff  lea     rdx, SourceString; "WIN://SYSAPPID"
0x180026e06  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180026e0b  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180026e10  call    cs:__imp_RtlInitUnicodeString
0x180026e16  xorps   xmm0, xmm0
0x180026e19  xor     edi, edi
0x180026e1b  movups  [rsp+68h+var_28], xmm0
0x180026e20  cmp     edi, [rbx+4]
0x180026e23  jnb     short loc_180026E5D
0x180026e25  mov     rax, [rbx+8]
0x180026e29  lea     rcx, [rdi+rdi*4]
0x180026e2d  mov     r8b, 1; CaseInsensitive
0x180026e30  lea     rsi, [rax+rcx*8]
0x180026e34  mov     rdx, rsi; String2
0x180026e37  lea     rcx, [rsp+68h+DestinationString]; String1
0x180026e3c  call    cs:__imp_RtlCompareUnicodeString
0x180026e42  test    eax, eax
0x180026e44  jz      short loc_180026E4A
0x180026e46  inc     edi
0x180026e48  jmp     short loc_180026E20
0x180026e4a  mov     [r14], rsi
0x180026e4d  mov     [r15], rbx
0x180026e50  xor     ebx, ebx
0x180026e52  xor     ecx, ecx; P
0x180026e54  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180026e59  mov     eax, ebx
0x180026e5b  jmp     short loc_180026E6C
0x180026e5d  mov     edi, 490h
0x180026e62  mov     rcx, rbx; P
0x180026e65  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180026e6a  mov     eax, edi
0x180026e6c  mov     rbx, [rsp+68h+arg_0]
0x180026e71  mov     rsi, [rsp+68h+arg_8]
0x180026e76  add     rsp, 50h
0x180026e7a  pop     r15
0x180026e7c  pop     r14
0x180026e7e  pop     rdi
0x180026e7f  retn
```
