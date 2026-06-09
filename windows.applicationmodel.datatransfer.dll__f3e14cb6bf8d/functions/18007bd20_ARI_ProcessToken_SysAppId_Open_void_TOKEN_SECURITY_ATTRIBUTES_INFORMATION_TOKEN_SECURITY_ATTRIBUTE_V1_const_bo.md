# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x18007bd20`
- end: `0x18007bebb`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `411`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006556c`

## callees

- `0x18000346c`
- `0x18007bb08`
- `0x18007bd20`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18007bd60`
- `ntdll!NtQueryInformationToken` at `0x18007bdfa`
- `ntdll!NtQueryInformationToken` at `0x18007bd60`
- `ntdll!NtQueryInformationToken` at `0x18007bdfa`
- `ntdll!RtlCompareUnicodeString` at `0x18007be65`
- `ntdll!RtlCompareUnicodeString` at `0x18007be65`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18007bd7d`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18007be06`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18007bd7d`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18007be06`
- `ntdll!RtlAllocateHeap` at `0x18007bdb9`
- `ntdll!RtlAllocateHeap` at `0x18007bdb9`
- `ntdll!RtlInitUnicodeString` at `0x18007be3a`
- `ntdll!RtlInitUnicodeString` at `0x18007be3a`

## pseudocode

```c
ULONG __fastcall ARI::ProcessToken::SysAppId::Open(
        HANDLE TokenHandle,
        _QWORD *a2,
        const UNICODE_STRING **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v7; // eax
  PVOID Heap; // rax
  _DWORD *v10; // rdi
  int v11; // eax
  ULONG v12; // ebx
  _DWORD *v13; // rsi
  __int64 v14; // rbx
  const UNICODE_STRING *v15; // rbp
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  __int128 v17; // [rsp+40h] [rbp-38h]
  ULONG Size; // [rsp+98h] [rbp+20h] BYREF
  int Size_4; // [rsp+9Ch] [rbp+24h]

  Size_4 = HIDWORD(a4);
  Size = 0;
  v7 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &Size);
  if ( v7 == -1073741789 )
  {
    *(_QWORD *)&DestinationString.Length = 0;
    if ( is_mul_ok(Size, 0x10u)
      && (Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, (Size * (unsigned __int128)0x10uLL) >> 64, 16LL * Size),
          (v10 = Heap) != 0) )
    {
      memset_0(Heap, 0, Size);
      v11 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, v10, Size, &Size);
      if ( v11 >= 0 )
      {
        v13 = v10 + 1;
        if ( v10[1]
          && (DestinationString = 0, RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID"), v14 = 0, v17 = 0, *v13) )
        {
          while ( 1 )
          {
            v15 = (const UNICODE_STRING *)(*((_QWORD *)v10 + 1) + 40 * v14);
            if ( !RtlCompareUnicodeString(&DestinationString, v15, 1u) )
              break;
            v14 = (unsigned int)(v14 + 1);
            if ( (unsigned int)v14 >= *v13 )
              goto LABEL_13;
          }
          *a3 = v15;
          *a2 = v10;
          ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(0);
          return 0;
        }
        else
        {
LABEL_13:
          ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(v10);
          return 1168;
        }
      }
      else
      {
        v12 = RtlNtStatusToDosErrorNoTeb(v11);
        ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(v10);
        return v12;
      }
    }
    else
    {
      ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(0);
      return 8;
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
0x18007bd20  mov     rax, rsp
0x18007bd23  mov     [rax+8], rbx
0x18007bd27  mov     [rax+10h], rbp
0x18007bd2b  mov     [rax+20h], r9
0x18007bd2f  push    rsi
0x18007bd30  push    rdi
0x18007bd31  push    r12
0x18007bd33  push    r14
0x18007bd35  push    r15
0x18007bd37  sub     rsp, 50h
0x18007bd3b  xor     r9d, r9d; TokenInformationLength
0x18007bd3e  mov     dword ptr [rax+20h], 0
0x18007bd45  mov     r15, r8
0x18007bd48  lea     rax, [rax+20h]
0x18007bd4c  mov     r12, rdx
0x18007bd4f  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18007bd54  xor     r8d, r8d; TokenInformation
0x18007bd57  mov     rbx, rcx
0x18007bd5a  lea     esi, [r9+27h]
0x18007bd5e  mov     edx, esi; TokenInformationClass
0x18007bd60  call    cs:__imp_NtQueryInformationToken
0x18007bd66  cmp     eax, 0C0000023h
0x18007bd6b  jz      short loc_18007BD88
0x18007bd6d  test    eax, eax
0x18007bd6f  jnz     short loc_18007BD7B
0x18007bd71  mov     eax, 54Fh
0x18007bd76  jmp     loc_18007BEA2
0x18007bd7b  mov     ecx, eax; Status
0x18007bd7d  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18007bd83  jmp     loc_18007BEA2
0x18007bd88  mov     ecx, dword ptr [rsp+78h+Size]
0x18007bd8f  mov     eax, 10h
0x18007bd94  mul     rcx
0x18007bd97  mov     qword ptr [rsp+78h+DestinationString.Length], 0
0x18007bda0  test    rdx, rdx
0x18007bda3  jnz     loc_18007BE96
0x18007bda9  mov     rcx, gs:60h
0x18007bdb2  mov     r8, rax; Size
0x18007bdb5  mov     rcx, [rcx+30h]; HeapHandle
0x18007bdb9  call    cs:__imp_RtlAllocateHeap
0x18007bdbf  mov     rdi, rax
0x18007bdc2  test    rax, rax
0x18007bdc5  jz      loc_18007BE96
0x18007bdcb  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x18007bdd3  xor     edx, edx; Val
0x18007bdd5  mov     rcx, rax; void *
0x18007bdd8  call    memset_0
0x18007bddd  mov     r9d, dword ptr [rsp+78h+Size]; TokenInformationLength
0x18007bde5  lea     rax, [rsp+78h+Size]
0x18007bded  mov     r8, rdi; TokenInformation
0x18007bdf0  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18007bdf5  mov     edx, esi; TokenInformationClass
0x18007bdf7  mov     rcx, rbx; TokenHandle
0x18007bdfa  call    cs:__imp_NtQueryInformationToken
0x18007be00  test    eax, eax
0x18007be02  jns     short loc_18007BE1D
0x18007be04  mov     ecx, eax; Status
0x18007be06  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18007be0c  mov     rcx, rdi; P
0x18007be0f  mov     ebx, eax
0x18007be11  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x18007be16  mov     eax, ebx
0x18007be18  jmp     loc_18007BEA2
0x18007be1d  lea     rsi, [rdi+4]
0x18007be21  cmp     dword ptr [rsi], 0
0x18007be24  jbe     short loc_18007BE75
0x18007be26  xorps   xmm0, xmm0
0x18007be29  lea     rdx, SourceString; "WIN://SYSAPPID"
0x18007be30  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x18007be35  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x18007be3a  call    cs:__imp_RtlInitUnicodeString
0x18007be40  xor     ebx, ebx
0x18007be42  xorps   xmm0, xmm0
0x18007be45  movups  [rsp+78h+var_38], xmm0
0x18007be4a  cmp     [rsi], ebx
0x18007be4c  jbe     short loc_18007BE75
0x18007be4e  mov     rax, [rdi+8]
0x18007be52  lea     rcx, [rbx+rbx*4]
0x18007be56  mov     r8b, 1; CaseInsensitive
0x18007be59  lea     rbp, [rax+rcx*8]
0x18007be5d  mov     rdx, rbp; String2
0x18007be60  lea     rcx, [rsp+78h+DestinationString]; String1
0x18007be65  call    cs:__imp_RtlCompareUnicodeString
0x18007be6b  test    eax, eax
0x18007be6d  jz      short loc_18007BE84
0x18007be6f  inc     ebx
0x18007be71  cmp     ebx, [rsi]
0x18007be73  jb      short loc_18007BE4E
0x18007be75  mov     rcx, rdi; P
0x18007be78  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x18007be7d  mov     eax, 490h
0x18007be82  jmp     short loc_18007BEA2
0x18007be84  mov     [r15], rbp
0x18007be87  xor     ecx, ecx; P
0x18007be89  mov     [r12], rdi
0x18007be8d  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x18007be92  xor     eax, eax
0x18007be94  jmp     short loc_18007BEA2
0x18007be96  xor     ecx, ecx; P
0x18007be98  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x18007be9d  mov     eax, 8
0x18007bea2  lea     r11, [rsp+78h+var_28]
0x18007bea7  mov     rbx, [r11+30h]
0x18007beab  mov     rbp, [r11+38h]
0x18007beaf  mov     rsp, r11
0x18007beb2  pop     r15
0x18007beb4  pop     r14
0x18007beb6  pop     r12
0x18007beb8  pop     rdi
0x18007beb9  pop     rsi
0x18007beba  retn
```
