# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x1800a630c`
- end: `0x1800a645c`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `ULONG __fastcall(HANDLE TokenHandle, _QWORD *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d38c`

## callees

- `0x1800517cc`
- `0x1800a6130`
- `0x1800a617c`
- `0x1800a630c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800a6349`
- `ntdll!NtQueryInformationToken` at `0x1800a63bc`
- `ntdll!NtQueryInformationToken` at `0x1800a6349`
- `ntdll!NtQueryInformationToken` at `0x1800a63bc`
- `ntdll!RtlInitUnicodeString` at `0x1800a63ec`
- `ntdll!RtlInitUnicodeString` at `0x1800a63ec`
- `ntdll!RtlCompareUnicodeString` at `0x1800a6418`
- `ntdll!RtlCompareUnicodeString` at `0x1800a6418`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800a6366`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800a63c8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800a6366`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800a63c8`

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
0x1800a630c  mov     rax, rsp
0x1800a630f  mov     [rax+8], rbx
0x1800a6313  mov     [rax+10h], rsi
0x1800a6317  mov     [rax+20h], r9
0x1800a631b  push    rdi
0x1800a631c  push    r14
0x1800a631e  push    r15
0x1800a6320  sub     rsp, 50h
0x1800a6324  xor     r9d, r9d; TokenInformationLength
0x1800a6327  mov     dword ptr [rax+20h], 0
0x1800a632e  mov     r14, r8
0x1800a6331  lea     rax, [rax+20h]
0x1800a6335  mov     r15, rdx
0x1800a6338  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800a633d  xor     r8d, r8d; TokenInformation
0x1800a6340  mov     rdi, rcx
0x1800a6343  lea     esi, [r9+27h]
0x1800a6347  mov     edx, esi; TokenInformationClass
0x1800a6349  call    cs:__imp_NtQueryInformationToken
0x1800a634f  cmp     eax, 0C0000023h
0x1800a6354  jz      short loc_1800A6371
0x1800a6356  test    eax, eax
0x1800a6358  jnz     short loc_1800A6364
0x1800a635a  mov     eax, 54Fh
0x1800a635f  jmp     loc_1800A6448
0x1800a6364  mov     ecx, eax; Status
0x1800a6366  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800a636c  jmp     loc_1800A6448
0x1800a6371  mov     ecx, dword ptr [rsp+68h+Size]
0x1800a6378  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x1800a637d  mov     rbx, rax
0x1800a6380  test    rax, rax
0x1800a6383  jnz     short loc_1800A638D
0x1800a6385  lea     ebx, [rax+8]
0x1800a6388  jmp     loc_1800A642E
0x1800a638d  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x1800a6395  xor     edx, edx; Val
0x1800a6397  mov     rcx, rbx; void *
0x1800a639a  call    memset_0
0x1800a639f  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x1800a63a7  lea     rax, [rsp+68h+Size]
0x1800a63af  mov     r8, rbx; TokenInformation
0x1800a63b2  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800a63b7  mov     edx, esi; TokenInformationClass
0x1800a63b9  mov     rcx, rdi; TokenHandle
0x1800a63bc  call    cs:__imp_NtQueryInformationToken
0x1800a63c2  test    eax, eax
0x1800a63c4  jns     short loc_1800A63D2
0x1800a63c6  mov     ecx, eax; Status
0x1800a63c8  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800a63ce  mov     edi, eax
0x1800a63d0  jmp     short loc_1800A643E
0x1800a63d2  cmp     dword ptr [rbx+4], 0
0x1800a63d6  jbe     short loc_1800A6439
0x1800a63d8  xorps   xmm0, xmm0
0x1800a63db  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x1800a63e2  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800a63e7  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800a63ec  call    cs:__imp_RtlInitUnicodeString
0x1800a63f2  xorps   xmm0, xmm0
0x1800a63f5  xor     edi, edi
0x1800a63f7  movups  [rsp+68h+var_28], xmm0
0x1800a63fc  cmp     edi, [rbx+4]
0x1800a63ff  jnb     short loc_1800A6439
0x1800a6401  mov     rax, [rbx+8]
0x1800a6405  lea     rcx, [rdi+rdi*4]
0x1800a6409  mov     r8b, 1; CaseInsensitive
0x1800a640c  lea     rsi, [rax+rcx*8]
0x1800a6410  mov     rdx, rsi; String2
0x1800a6413  lea     rcx, [rsp+68h+DestinationString]; String1
0x1800a6418  call    cs:__imp_RtlCompareUnicodeString
0x1800a641e  test    eax, eax
0x1800a6420  jz      short loc_1800A6426
0x1800a6422  inc     edi
0x1800a6424  jmp     short loc_1800A63FC
0x1800a6426  mov     [r14], rsi
0x1800a6429  mov     [r15], rbx
0x1800a642c  xor     ebx, ebx
0x1800a642e  xor     ecx, ecx; P
0x1800a6430  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800a6435  mov     eax, ebx
0x1800a6437  jmp     short loc_1800A6448
0x1800a6439  mov     edi, 490h
0x1800a643e  mov     rcx, rbx; P
0x1800a6441  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800a6446  mov     eax, edi
0x1800a6448  mov     rbx, [rsp+68h+arg_0]
0x1800a644d  mov     rsi, [rsp+68h+arg_8]
0x1800a6452  add     rsp, 50h
0x1800a6456  pop     r15
0x1800a6458  pop     r14
0x1800a645a  pop     rdi
0x1800a645b  retn
```
