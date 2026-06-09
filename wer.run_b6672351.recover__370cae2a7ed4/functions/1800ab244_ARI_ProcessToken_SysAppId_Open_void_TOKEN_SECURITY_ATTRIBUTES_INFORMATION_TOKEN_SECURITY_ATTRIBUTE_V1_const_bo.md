# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x1800ab244`
- end: `0x1800ab3b9`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `373`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003f440`

## callees

- `0x180053d3c`
- `0x1800aafe4`
- `0x1800ab05c`
- `0x1800ab244`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800ab281`
- `ntdll!NtQueryInformationToken` at `0x1800ab300`
- `ntdll!NtQueryInformationToken` at `0x1800ab281`
- `ntdll!NtQueryInformationToken` at `0x1800ab300`
- `ntdll!RtlInitUnicodeString` at `0x1800ab33c`
- `ntdll!RtlInitUnicodeString` at `0x1800ab33c`
- `ntdll!RtlCompareUnicodeString` at `0x1800ab36e`
- `ntdll!RtlCompareUnicodeString` at `0x1800ab36e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800ab2a4`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800ab312`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800ab2a4`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800ab312`

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
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
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
0x1800ab244  mov     rax, rsp
0x1800ab247  mov     [rax+8], rbx
0x1800ab24b  mov     [rax+10h], rsi
0x1800ab24f  mov     [rax+20h], r9
0x1800ab253  push    rdi
0x1800ab254  push    r14
0x1800ab256  push    r15
0x1800ab258  sub     rsp, 50h
0x1800ab25c  xor     r9d, r9d; TokenInformationLength
0x1800ab25f  mov     dword ptr [rax+20h], 0
0x1800ab266  mov     r14, r8
0x1800ab269  lea     rax, [rax+20h]
0x1800ab26d  mov     r15, rdx
0x1800ab270  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800ab275  xor     r8d, r8d; TokenInformation
0x1800ab278  mov     rdi, rcx
0x1800ab27b  lea     esi, [r9+27h]
0x1800ab27f  mov     edx, esi; TokenInformationClass
0x1800ab281  call    cs:__imp_NtQueryInformationToken
0x1800ab288  nop     dword ptr [rax+rax+00h]
0x1800ab28d  cmp     eax, 0C0000023h
0x1800ab292  jz      short loc_1800AB2B5
0x1800ab294  test    eax, eax
0x1800ab296  jnz     short loc_1800AB2A2
0x1800ab298  mov     eax, 54Fh
0x1800ab29d  jmp     loc_1800AB3A4
0x1800ab2a2  mov     ecx, eax; Status
0x1800ab2a4  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800ab2ab  nop     dword ptr [rax+rax+00h]
0x1800ab2b0  jmp     loc_1800AB3A4
0x1800ab2b5  mov     ecx, dword ptr [rsp+68h+Size]
0x1800ab2bc  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x1800ab2c1  mov     rbx, rax
0x1800ab2c4  test    rax, rax
0x1800ab2c7  jnz     short loc_1800AB2D1
0x1800ab2c9  lea     ebx, [rax+8]
0x1800ab2cc  jmp     loc_1800AB38A
0x1800ab2d1  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x1800ab2d9  xor     edx, edx; Val
0x1800ab2db  mov     rcx, rbx; void *
0x1800ab2de  call    memset_0
0x1800ab2e3  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x1800ab2eb  lea     rax, [rsp+68h+Size]
0x1800ab2f3  mov     r8, rbx; TokenInformation
0x1800ab2f6  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800ab2fb  mov     edx, esi; TokenInformationClass
0x1800ab2fd  mov     rcx, rdi; TokenHandle
0x1800ab300  call    cs:__imp_NtQueryInformationToken
0x1800ab307  nop     dword ptr [rax+rax+00h]
0x1800ab30c  test    eax, eax
0x1800ab30e  jns     short loc_1800AB322
0x1800ab310  mov     ecx, eax; Status
0x1800ab312  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800ab319  nop     dword ptr [rax+rax+00h]
0x1800ab31e  mov     edi, eax
0x1800ab320  jmp     short loc_1800AB39A
0x1800ab322  cmp     dword ptr [rbx+4], 0
0x1800ab326  jbe     short loc_1800AB395
0x1800ab328  xorps   xmm0, xmm0
0x1800ab32b  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x1800ab332  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800ab337  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800ab33c  call    cs:__imp_RtlInitUnicodeString
0x1800ab343  nop     dword ptr [rax+rax+00h]
0x1800ab348  xorps   xmm0, xmm0
0x1800ab34b  xor     edi, edi
0x1800ab34d  movups  [rsp+68h+var_28], xmm0
0x1800ab352  cmp     edi, [rbx+4]
0x1800ab355  jnb     short loc_1800AB395
0x1800ab357  mov     rax, [rbx+8]
0x1800ab35b  lea     rcx, [rdi+rdi*4]
0x1800ab35f  mov     r8b, 1; CaseInsensitive
0x1800ab362  lea     rsi, [rax+rcx*8]
0x1800ab366  mov     rdx, rsi; String2
0x1800ab369  lea     rcx, [rsp+68h+DestinationString]; String1
0x1800ab36e  call    cs:__imp_RtlCompareUnicodeString
0x1800ab375  nop     dword ptr [rax+rax+00h]
0x1800ab37a  test    eax, eax
0x1800ab37c  jz      short loc_1800AB382
0x1800ab37e  inc     edi
0x1800ab380  jmp     short loc_1800AB352
0x1800ab382  mov     [r14], rsi
0x1800ab385  mov     [r15], rbx
0x1800ab388  xor     ebx, ebx
0x1800ab38a  xor     ecx, ecx; P
0x1800ab38c  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800ab391  mov     eax, ebx
0x1800ab393  jmp     short loc_1800AB3A4
0x1800ab395  mov     edi, 490h
0x1800ab39a  mov     rcx, rbx; P
0x1800ab39d  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800ab3a2  mov     eax, edi
0x1800ab3a4  mov     rbx, [rsp+68h+arg_0]
0x1800ab3a9  mov     rsi, [rsp+68h+arg_8]
0x1800ab3ae  add     rsp, 50h
0x1800ab3b2  pop     r15
0x1800ab3b4  pop     r14
0x1800ab3b6  pop     rdi
0x1800ab3b7  retn
```
