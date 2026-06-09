# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x180041198`
- end: `0x1800412e8`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180052c38`

## callees

- `0x180041198`
- `0x180072b4c`
- `0x1800735f0`
- `0x18008a9d8`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800411d5`
- `ntdll!NtQueryInformationToken` at `0x180041248`
- `ntdll!NtQueryInformationToken` at `0x1800411d5`
- `ntdll!NtQueryInformationToken` at `0x180041248`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800411f2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180041254`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800411f2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180041254`
- `ntdll!RtlCompareUnicodeString` at `0x1800412a4`
- `ntdll!RtlCompareUnicodeString` at `0x1800412a4`
- `ntdll!RtlInitUnicodeString` at `0x180041278`
- `ntdll!RtlInitUnicodeString` at `0x180041278`

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
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
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
0x180041198  mov     rax, rsp
0x18004119b  mov     [rax+8], rbx
0x18004119f  mov     [rax+10h], rsi
0x1800411a3  mov     [rax+20h], r9
0x1800411a7  push    rdi
0x1800411a8  push    r14
0x1800411aa  push    r15
0x1800411ac  sub     rsp, 50h
0x1800411b0  xor     r9d, r9d; TokenInformationLength
0x1800411b3  mov     dword ptr [rax+20h], 0
0x1800411ba  mov     r14, r8
0x1800411bd  lea     rax, [rax+20h]
0x1800411c1  mov     r15, rdx
0x1800411c4  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800411c9  xor     r8d, r8d; TokenInformation
0x1800411cc  mov     rdi, rcx
0x1800411cf  lea     esi, [r9+27h]
0x1800411d3  mov     edx, esi; TokenInformationClass
0x1800411d5  call    cs:__imp_NtQueryInformationToken
0x1800411db  cmp     eax, 0C0000023h
0x1800411e0  jz      short loc_1800411FD
0x1800411e2  test    eax, eax
0x1800411e4  jnz     short loc_1800411F0
0x1800411e6  mov     eax, 54Fh
0x1800411eb  jmp     loc_1800412D4
0x1800411f0  mov     ecx, eax; Status
0x1800411f2  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800411f8  jmp     loc_1800412D4
0x1800411fd  mov     ecx, dword ptr [rsp+68h+Size]
0x180041204  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x180041209  mov     rbx, rax
0x18004120c  test    rax, rax
0x18004120f  jnz     short loc_180041219
0x180041211  lea     ebx, [rax+8]
0x180041214  jmp     loc_1800412BA
0x180041219  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x180041221  xor     edx, edx; Val
0x180041223  mov     rcx, rbx; void *
0x180041226  call    memset_0
0x18004122b  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x180041233  lea     rax, [rsp+68h+Size]
0x18004123b  mov     r8, rbx; TokenInformation
0x18004123e  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180041243  mov     edx, esi; TokenInformationClass
0x180041245  mov     rcx, rdi; TokenHandle
0x180041248  call    cs:__imp_NtQueryInformationToken
0x18004124e  test    eax, eax
0x180041250  jns     short loc_18004125E
0x180041252  mov     ecx, eax; Status
0x180041254  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18004125a  mov     edi, eax
0x18004125c  jmp     short loc_1800412CA
0x18004125e  cmp     dword ptr [rbx+4], 0
0x180041262  jbe     short loc_1800412C5
0x180041264  xorps   xmm0, xmm0
0x180041267  lea     rdx, SourceString; "WIN://SYSAPPID"
0x18004126e  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180041273  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180041278  call    cs:__imp_RtlInitUnicodeString
0x18004127e  xorps   xmm0, xmm0
0x180041281  xor     edi, edi
0x180041283  movups  [rsp+68h+var_28], xmm0
0x180041288  cmp     edi, [rbx+4]
0x18004128b  jnb     short loc_1800412C5
0x18004128d  mov     rax, [rbx+8]
0x180041291  lea     rcx, [rdi+rdi*4]
0x180041295  mov     r8b, 1; CaseInsensitive
0x180041298  lea     rsi, [rax+rcx*8]
0x18004129c  mov     rdx, rsi; String2
0x18004129f  lea     rcx, [rsp+68h+DestinationString]; String1
0x1800412a4  call    cs:__imp_RtlCompareUnicodeString
0x1800412aa  test    eax, eax
0x1800412ac  jz      short loc_1800412B2
0x1800412ae  inc     edi
0x1800412b0  jmp     short loc_180041288
0x1800412b2  mov     [r14], rsi
0x1800412b5  mov     [r15], rbx
0x1800412b8  xor     ebx, ebx
0x1800412ba  xor     ecx, ecx; P
0x1800412bc  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800412c1  mov     eax, ebx
0x1800412c3  jmp     short loc_1800412D4
0x1800412c5  mov     edi, 490h
0x1800412ca  mov     rcx, rbx; P
0x1800412cd  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800412d2  mov     eax, edi
0x1800412d4  mov     rbx, [rsp+68h+arg_0]
0x1800412d9  mov     rsi, [rsp+68h+arg_8]
0x1800412de  add     rsp, 50h
0x1800412e2  pop     r15
0x1800412e4  pop     r14
0x1800412e6  pop     rdi
0x1800412e7  retn
```
