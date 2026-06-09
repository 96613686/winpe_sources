# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x180072cc0`
- end: `0x180072e18`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `344`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180072b10`

## callees

- `0x180072cc0`
- `0x180072e20`
- `0x180072e4c`
- `0x1800ba574`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180072cfd`
- `ntdll!NtQueryInformationToken` at `0x180072d55`
- `ntdll!NtQueryInformationToken` at `0x180072cfd`
- `ntdll!NtQueryInformationToken` at `0x180072d55`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180072dfd`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180072e07`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180072dfd`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180072e07`
- `ntdll!RtlCompareUnicodeString` at `0x180072da9`
- `ntdll!RtlCompareUnicodeString` at `0x180072da9`
- `ntdll!RtlInitUnicodeString` at `0x180072d7d`
- `ntdll!RtlInitUnicodeString` at `0x180072d7d`

## pseudocode

```c
ULONG __fastcall ARI::ProcessToken::SysAppId::Open(
        HANDLE TokenHandle,
        _QWORD *a2,
        struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v7; // eax
  void *v8; // rax
  void *v9; // rdx
  void *v10; // rbx
  int v11; // eax
  __int64 v12; // rdi
  struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v13; // rsi
  int v14; // ebx
  ULONG v16; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  __int128 v18; // [rsp+40h] [rbp-28h]
  ULONG Size; // [rsp+88h] [rbp+20h] BYREF
  int Size_4; // [rsp+8Ch] [rbp+24h]

  Size_4 = HIDWORD(a4);
  Size = 0;
  v7 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &Size);
  if ( v7 == -1073741789 )
  {
    v8 = (void *)ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(Size);
    v10 = v8;
    if ( v8 )
    {
      memset_0(v8, 0, Size);
      v11 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, v10, Size, &Size);
      if ( v11 < 0 )
      {
        v16 = RtlNtStatusToDosErrorNoTeb(v11);
      }
      else
      {
        if ( *((_DWORD *)v10 + 1) )
        {
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
          v12 = 0;
          v18 = 0;
          while ( (unsigned int)v12 < *((_DWORD *)v10 + 1) )
          {
            v13 = (struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)(*((_QWORD *)v10 + 1) + 40 * v12);
            if ( !RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)v13, 1u) )
            {
              *a3 = v13;
              *a2 = v10;
              v14 = 0;
              goto LABEL_9;
            }
            v12 = (unsigned int)(v12 + 1);
          }
        }
        v16 = 1168;
      }
      ARI::Free(v10, v9);
      return v16;
    }
    else
    {
      v14 = 8;
LABEL_9:
      ARI::Free(0, v9);
      return v14;
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
0x180072cc0  mov     rax, rsp
0x180072cc3  mov     [rax+8], rbx
0x180072cc7  mov     [rax+10h], rsi
0x180072ccb  mov     [rax+20h], r9
0x180072ccf  push    rdi
0x180072cd0  push    r14
0x180072cd2  push    r15
0x180072cd4  sub     rsp, 50h
0x180072cd8  xor     r9d, r9d; TokenInformationLength
0x180072cdb  mov     dword ptr [rax+20h], 0
0x180072ce2  mov     r14, r8
0x180072ce5  lea     rax, [rax+20h]
0x180072ce9  mov     r15, rdx
0x180072cec  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180072cf1  xor     r8d, r8d; TokenInformation
0x180072cf4  mov     rdi, rcx
0x180072cf7  lea     esi, [r9+27h]
0x180072cfb  mov     edx, esi; TokenInformationClass
0x180072cfd  call    cs:__imp_NtQueryInformationToken
0x180072d03  cmp     eax, 0C0000023h
0x180072d08  jnz     loc_180072DF0
0x180072d0e  mov     ecx, dword ptr [rsp+68h+Size]
0x180072d15  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x180072d1a  mov     rbx, rax
0x180072d1d  test    rax, rax
0x180072d20  jz      loc_180072DE9
0x180072d26  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x180072d2e  xor     edx, edx; Val
0x180072d30  mov     rcx, rax; void *
0x180072d33  call    memset_0
0x180072d38  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x180072d40  lea     rax, [rsp+68h+Size]
0x180072d48  mov     r8, rbx; TokenInformation
0x180072d4b  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180072d50  mov     edx, esi; TokenInformationClass
0x180072d52  mov     rcx, rdi; TokenHandle
0x180072d55  call    cs:__imp_NtQueryInformationToken
0x180072d5b  test    eax, eax
0x180072d5d  js      loc_180072E05
0x180072d63  cmp     dword ptr [rbx+4], 0
0x180072d67  jbe     short loc_180072DD8
0x180072d69  xorps   xmm0, xmm0
0x180072d6c  lea     rdx, SourceString; "WIN://SYSAPPID"
0x180072d73  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180072d78  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180072d7d  call    cs:__imp_RtlInitUnicodeString
0x180072d83  xorps   xmm0, xmm0
0x180072d86  xor     edi, edi
0x180072d88  movups  [rsp+68h+var_28], xmm0
0x180072d8d  cmp     edi, [rbx+4]
0x180072d90  jnb     short loc_180072DD8
0x180072d92  mov     rax, [rbx+8]
0x180072d96  lea     rcx, [rdi+rdi*4]
0x180072d9a  mov     r8b, 1; CaseInsensitive
0x180072d9d  lea     rsi, [rax+rcx*8]
0x180072da1  mov     rdx, rsi; String2
0x180072da4  lea     rcx, [rsp+68h+DestinationString]; String1
0x180072da9  call    cs:__imp_RtlCompareUnicodeString
0x180072daf  test    eax, eax
0x180072db1  jnz     short loc_180072E11
0x180072db3  mov     [r14], rsi
0x180072db6  mov     [r15], rbx
0x180072db9  xor     ebx, ebx
0x180072dbb  xor     ecx, ecx; P
0x180072dbd  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180072dc2  mov     eax, ebx
0x180072dc4  mov     rbx, [rsp+68h+arg_0]
0x180072dc9  mov     rsi, [rsp+68h+arg_8]
0x180072dce  add     rsp, 50h
0x180072dd2  pop     r15
0x180072dd4  pop     r14
0x180072dd6  pop     rdi
0x180072dd7  retn
0x180072dd8  mov     edi, 490h
0x180072ddd  mov     rcx, rbx; P
0x180072de0  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180072de5  mov     eax, edi
0x180072de7  jmp     short loc_180072DC4
0x180072de9  mov     ebx, 8
0x180072dee  jmp     short loc_180072DBB
0x180072df0  test    eax, eax
0x180072df2  jnz     short loc_180072DFB
0x180072df4  mov     eax, 54Fh
0x180072df9  jmp     short loc_180072DC4
0x180072dfb  mov     ecx, eax; Status
0x180072dfd  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180072e03  jmp     short loc_180072DC4
0x180072e05  mov     ecx, eax; Status
0x180072e07  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180072e0d  mov     edi, eax
0x180072e0f  jmp     short loc_180072DDD
0x180072e11  inc     edi
0x180072e13  jmp     loc_180072D8D
```
