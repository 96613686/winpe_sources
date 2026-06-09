# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x1803191d4`
- end: `0x180319349`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `373`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180319050`

## callees

- `0x18012eb08`
- `0x180318d20`
- `0x180318e68`
- `0x1803191d4`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1803192cc`
- `ntdll!RtlInitUnicodeString` at `0x1803192cc`
- `ntdll!RtlCompareUnicodeString` at `0x1803192fe`
- `ntdll!RtlCompareUnicodeString` at `0x1803192fe`
- `ntdll!NtQueryInformationToken` at `0x180319211`
- `ntdll!NtQueryInformationToken` at `0x180319290`
- `ntdll!NtQueryInformationToken` at `0x180319211`
- `ntdll!NtQueryInformationToken` at `0x180319290`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180319234`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1803192a2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180319234`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1803192a2`

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
0x1803191d4  mov     rax, rsp
0x1803191d7  mov     [rax+8], rbx
0x1803191db  mov     [rax+10h], rsi
0x1803191df  mov     [rax+20h], r9
0x1803191e3  push    rdi
0x1803191e4  push    r14
0x1803191e6  push    r15
0x1803191e8  sub     rsp, 50h
0x1803191ec  xor     r9d, r9d; TokenInformationLength
0x1803191ef  mov     dword ptr [rax+20h], 0
0x1803191f6  mov     r14, r8
0x1803191f9  lea     rax, [rax+20h]
0x1803191fd  mov     r15, rdx
0x180319200  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180319205  xor     r8d, r8d; TokenInformation
0x180319208  mov     rdi, rcx
0x18031920b  lea     esi, [r9+27h]
0x18031920f  mov     edx, esi; TokenInformationClass
0x180319211  call    cs:__imp_NtQueryInformationToken
0x180319218  nop     dword ptr [rax+rax+00h]
0x18031921d  cmp     eax, 0C0000023h
0x180319222  jz      short loc_180319245
0x180319224  test    eax, eax
0x180319226  jnz     short loc_180319232
0x180319228  mov     eax, 54Fh
0x18031922d  jmp     loc_180319334
0x180319232  mov     ecx, eax; Status
0x180319234  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18031923b  nop     dword ptr [rax+rax+00h]
0x180319240  jmp     loc_180319334
0x180319245  mov     ecx, dword ptr [rsp+68h+Size]
0x18031924c  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x180319251  mov     rbx, rax
0x180319254  test    rax, rax
0x180319257  jnz     short loc_180319261
0x180319259  lea     ebx, [rax+8]
0x18031925c  jmp     loc_18031931A
0x180319261  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x180319269  xor     edx, edx; Val
0x18031926b  mov     rcx, rbx; void *
0x18031926e  call    memset_0
0x180319273  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x18031927b  lea     rax, [rsp+68h+Size]
0x180319283  mov     r8, rbx; TokenInformation
0x180319286  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18031928b  mov     edx, esi; TokenInformationClass
0x18031928d  mov     rcx, rdi; TokenHandle
0x180319290  call    cs:__imp_NtQueryInformationToken
0x180319297  nop     dword ptr [rax+rax+00h]
0x18031929c  test    eax, eax
0x18031929e  jns     short loc_1803192B2
0x1803192a0  mov     ecx, eax; Status
0x1803192a2  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1803192a9  nop     dword ptr [rax+rax+00h]
0x1803192ae  mov     edi, eax
0x1803192b0  jmp     short loc_18031932A
0x1803192b2  cmp     dword ptr [rbx+4], 0
0x1803192b6  jbe     short loc_180319325
0x1803192b8  xorps   xmm0, xmm0
0x1803192bb  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x1803192c2  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1803192c7  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1803192cc  call    cs:__imp_RtlInitUnicodeString
0x1803192d3  nop     dword ptr [rax+rax+00h]
0x1803192d8  xorps   xmm0, xmm0
0x1803192db  xor     edi, edi
0x1803192dd  movups  [rsp+68h+var_28], xmm0
0x1803192e2  cmp     edi, [rbx+4]
0x1803192e5  jnb     short loc_180319325
0x1803192e7  mov     rax, [rbx+8]
0x1803192eb  lea     rcx, [rdi+rdi*4]
0x1803192ef  mov     r8b, 1; CaseInsensitive
0x1803192f2  lea     rsi, [rax+rcx*8]
0x1803192f6  mov     rdx, rsi; String2
0x1803192f9  lea     rcx, [rsp+68h+DestinationString]; String1
0x1803192fe  call    cs:__imp_RtlCompareUnicodeString
0x180319305  nop     dword ptr [rax+rax+00h]
0x18031930a  test    eax, eax
0x18031930c  jz      short loc_180319312
0x18031930e  inc     edi
0x180319310  jmp     short loc_1803192E2
0x180319312  mov     [r14], rsi
0x180319315  mov     [r15], rbx
0x180319318  xor     ebx, ebx
0x18031931a  xor     ecx, ecx; P
0x18031931c  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180319321  mov     eax, ebx
0x180319323  jmp     short loc_180319334
0x180319325  mov     edi, 490h
0x18031932a  mov     rcx, rbx; P
0x18031932d  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180319332  mov     eax, edi
0x180319334  mov     rbx, [rsp+68h+arg_0]
0x180319339  mov     rsi, [rsp+68h+arg_8]
0x18031933e  add     rsp, 50h
0x180319342  pop     r15
0x180319344  pop     r14
0x180319346  pop     rdi
0x180319347  retn
```
