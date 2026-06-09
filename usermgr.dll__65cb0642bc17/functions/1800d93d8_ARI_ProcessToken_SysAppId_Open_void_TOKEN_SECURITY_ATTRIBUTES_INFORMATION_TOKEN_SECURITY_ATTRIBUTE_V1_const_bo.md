# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x1800d93d8`
- end: `0x1800d9528`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800d9248`

## callees

- `0x18006f1c9`
- `0x1800d8e04`
- `0x1800d8e84`
- `0x1800d93d8`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800d9432`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800d9494`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800d9432`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800d9494`
- `ntdll!RtlCompareUnicodeString` at `0x1800d94e4`
- `ntdll!RtlCompareUnicodeString` at `0x1800d94e4`
- `ntdll!NtQueryInformationToken` at `0x1800d9415`
- `ntdll!NtQueryInformationToken` at `0x1800d9488`
- `ntdll!NtQueryInformationToken` at `0x1800d9415`
- `ntdll!NtQueryInformationToken` at `0x1800d9488`
- `ntdll!RtlInitUnicodeString` at `0x1800d94b8`
- `ntdll!RtlInitUnicodeString` at `0x1800d94b8`

## pseudocode

```c
ULONG __fastcall ARI::ProcessToken::SysAppId::Open(
        HANDLE TokenHandle,
        _QWORD *a2,
        struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v7; // eax
  PVOID v9; // rax
  void *v10; // rdx
  PVOID v11; // rbx
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
    v9 = ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(Size);
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
0x1800d93d8  mov     rax, rsp
0x1800d93db  mov     [rax+8], rbx
0x1800d93df  mov     [rax+10h], rsi
0x1800d93e3  mov     [rax+20h], r9
0x1800d93e7  push    rdi
0x1800d93e8  push    r14
0x1800d93ea  push    r15
0x1800d93ec  sub     rsp, 50h
0x1800d93f0  xor     r9d, r9d; TokenInformationLength
0x1800d93f3  mov     dword ptr [rax+20h], 0
0x1800d93fa  mov     r14, r8
0x1800d93fd  lea     rax, [rax+20h]
0x1800d9401  mov     r15, rdx
0x1800d9404  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800d9409  xor     r8d, r8d; TokenInformation
0x1800d940c  mov     rdi, rcx
0x1800d940f  lea     esi, [r9+27h]
0x1800d9413  mov     edx, esi; TokenInformationClass
0x1800d9415  call    cs:__imp_NtQueryInformationToken
0x1800d941b  cmp     eax, 0C0000023h
0x1800d9420  jz      short loc_1800D943D
0x1800d9422  test    eax, eax
0x1800d9424  jnz     short loc_1800D9430
0x1800d9426  mov     eax, 54Fh
0x1800d942b  jmp     loc_1800D9514
0x1800d9430  mov     ecx, eax; Status
0x1800d9432  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800d9438  jmp     loc_1800D9514
0x1800d943d  mov     ecx, dword ptr [rsp+68h+Size]
0x1800d9444  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x1800d9449  mov     rbx, rax
0x1800d944c  test    rax, rax
0x1800d944f  jnz     short loc_1800D9459
0x1800d9451  lea     ebx, [rax+8]
0x1800d9454  jmp     loc_1800D94FA
0x1800d9459  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x1800d9461  xor     edx, edx; Val
0x1800d9463  mov     rcx, rbx; void *
0x1800d9466  call    memset_0
0x1800d946b  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x1800d9473  lea     rax, [rsp+68h+Size]
0x1800d947b  mov     r8, rbx; TokenInformation
0x1800d947e  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800d9483  mov     edx, esi; TokenInformationClass
0x1800d9485  mov     rcx, rdi; TokenHandle
0x1800d9488  call    cs:__imp_NtQueryInformationToken
0x1800d948e  test    eax, eax
0x1800d9490  jns     short loc_1800D949E
0x1800d9492  mov     ecx, eax; Status
0x1800d9494  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800d949a  mov     edi, eax
0x1800d949c  jmp     short loc_1800D950A
0x1800d949e  cmp     dword ptr [rbx+4], 0
0x1800d94a2  jbe     short loc_1800D9505
0x1800d94a4  xorps   xmm0, xmm0
0x1800d94a7  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x1800d94ae  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800d94b3  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800d94b8  call    cs:__imp_RtlInitUnicodeString
0x1800d94be  xorps   xmm0, xmm0
0x1800d94c1  xor     edi, edi
0x1800d94c3  movups  [rsp+68h+var_28], xmm0
0x1800d94c8  cmp     edi, [rbx+4]
0x1800d94cb  jnb     short loc_1800D9505
0x1800d94cd  mov     rax, [rbx+8]
0x1800d94d1  lea     rcx, [rdi+rdi*4]
0x1800d94d5  mov     r8b, 1; CaseInsensitive
0x1800d94d8  lea     rsi, [rax+rcx*8]
0x1800d94dc  mov     rdx, rsi; String2
0x1800d94df  lea     rcx, [rsp+68h+DestinationString]; String1
0x1800d94e4  call    cs:__imp_RtlCompareUnicodeString
0x1800d94ea  test    eax, eax
0x1800d94ec  jz      short loc_1800D94F2
0x1800d94ee  inc     edi
0x1800d94f0  jmp     short loc_1800D94C8
0x1800d94f2  mov     [r14], rsi
0x1800d94f5  mov     [r15], rbx
0x1800d94f8  xor     ebx, ebx
0x1800d94fa  xor     ecx, ecx; P
0x1800d94fc  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800d9501  mov     eax, ebx
0x1800d9503  jmp     short loc_1800D9514
0x1800d9505  mov     edi, 490h
0x1800d950a  mov     rcx, rbx; P
0x1800d950d  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800d9512  mov     eax, edi
0x1800d9514  mov     rbx, [rsp+68h+arg_0]
0x1800d9519  mov     rsi, [rsp+68h+arg_8]
0x1800d951e  add     rsp, 50h
0x1800d9522  pop     r15
0x1800d9524  pop     r14
0x1800d9526  pop     rdi
0x1800d9527  retn
```
