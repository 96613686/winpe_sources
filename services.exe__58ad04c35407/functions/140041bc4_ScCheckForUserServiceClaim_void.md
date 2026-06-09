# ScCheckForUserServiceClaim(void *)

- ea: `0x140041bc4`
- end: `0x140041daa`
- name: `?ScCheckForUserServiceClaim@@YAHPEAX@Z`
- size: `486`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14002fce0`
- `0x140039100`

## callees

- `0x140004c58`
- `0x140041bc4`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x140041bf2`
- `ntdll!RtlInitUnicodeStringEx` at `0x140041bf2`
- `ntdll!RtlFreeHeap` at `0x140041d1a`
- `ntdll!RtlFreeHeap` at `0x140041d62`
- `ntdll!RtlFreeHeap` at `0x140041d1a`
- `ntdll!RtlFreeHeap` at `0x140041d62`
- `ntdll!RtlCompareUnicodeString` at `0x140041d3d`
- `ntdll!RtlCompareUnicodeString` at `0x140041d3d`
- `ntdll!NtQueryInformationToken` at `0x140041c3f`
- `ntdll!NtQueryInformationToken` at `0x140041ccd`
- `ntdll!NtQueryInformationToken` at `0x140041c3f`
- `ntdll!NtQueryInformationToken` at `0x140041ccd`
- `ntdll!RtlAllocateHeap` at `0x140041c78`
- `ntdll!RtlAllocateHeap` at `0x140041c78`

## string_xrefs

- `0x140041be5`: `WIN://SCMUserService`

## pseudocode

```c
__int64 __fastcall ScCheckForUserServiceClaim(HANDLE TokenHandle)
{
  unsigned int v2; // esi
  unsigned int inited; // eax
  __int64 v4; // r9
  PRPC_ASYNC_STATE v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // eax
  PVOID Heap; // rdi
  NTSTATUS v9; // eax
  __int64 i; // rbx
  UNICODE_STRING String1; // [rsp+30h] [rbp-18h] BYREF
  ULONG TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF

  TokenInformationLength = 0;
  v2 = 0;
  String1 = 0;
  inited = RtlInitUnicodeStringEx(&String1, L"WIN://SCMUserService");
  v4 = inited;
  if ( inited )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      v6 = 73;
LABEL_25:
      WPP_SF_d(v5->StubInfo, v6, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, v4);
    }
  }
  else
  {
    v7 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &TokenInformationLength);
    v4 = v7;
    if ( v7 == -1073741789 && TokenInformationLength )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 16LL * TokenInformationLength);
      if ( Heap )
      {
        v9 = NtQueryInformationToken(
               TokenHandle,
               TokenSecurityAttributes,
               Heap,
               TokenInformationLength,
               &TokenInformationLength);
        if ( v9 >= 0 )
        {
          for ( i = 0; (unsigned int)i < *((_DWORD *)Heap + 1); i = (unsigned int)(i + 1) )
          {
            if ( !RtlCompareUnicodeString(&String1, (PCUNICODE_STRING)(*((_QWORD *)Heap + 1) + 40 * i), 1u) )
            {
              v2 = 1;
              break;
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->StubInfo,
              76,
              WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids,
              (unsigned int)v9);
          }
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          v6 = 75;
          v4 = 8;
          goto LABEL_25;
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        v6 = 74;
        goto LABEL_25;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140041bc4  mov     rax, rsp
0x140041bc7  mov     [rax+8], rbx
0x140041bcb  mov     [rax+18h], rsi
0x140041bcf  push    rdi
0x140041bd0  sub     rsp, 40h
0x140041bd4  mov     rbx, rcx
0x140041bd7  mov     dword ptr [rax+10h], 0
0x140041bde  xorps   xmm0, xmm0
0x140041be1  lea     rcx, [rax-18h]; DestinationString
0x140041be5  lea     rdx, aWinScmuserserv; "WIN://SCMUserService"
0x140041bec  xor     esi, esi
0x140041bee  movups  xmmword ptr [rax-18h], xmm0
0x140041bf2  call    cs:__imp_RtlInitUnicodeStringEx
0x140041bf8  mov     r9d, eax
0x140041bfb  test    eax, eax
0x140041bfd  jz      short loc_140041C28
0x140041bff  mov     rcx, cs:WPP_GLOBAL_Control
0x140041c06  lea     rax, WPP_GLOBAL_Control
0x140041c0d  cmp     rcx, rax
0x140041c10  jz      loc_140041D98
0x140041c16  test    byte ptr [rcx+1Ch], 1
0x140041c1a  jz      loc_140041D98
0x140041c20  lea     edx, [rsi+49h]
0x140041c23  jmp     loc_140041D88
0x140041c28  xor     r9d, r9d; TokenInformationLength
0x140041c2b  lea     rax, [rsp+48h+TokenInformationLength]
0x140041c30  xor     r8d, r8d; TokenInformation
0x140041c33  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x140041c38  mov     rcx, rbx; TokenHandle
0x140041c3b  lea     edx, [r9+27h]; TokenInformationClass
0x140041c3f  call    cs:__imp_NtQueryInformationToken
0x140041c45  mov     r9d, eax
0x140041c48  cmp     eax, 0C0000023h
0x140041c4d  jnz     loc_140041D6A
0x140041c53  mov     eax, [rsp+48h+TokenInformationLength]
0x140041c57  test    eax, eax
0x140041c59  jz      loc_140041D6A
0x140041c5f  mov     rcx, gs:60h
0x140041c68  mov     r8d, eax
0x140041c6b  shl     r8, 4; Size
0x140041c6f  mov     edx, 8; Flags
0x140041c74  mov     rcx, [rcx+30h]; HeapHandle
0x140041c78  call    cs:__imp_RtlAllocateHeap
0x140041c7e  mov     rdi, rax
0x140041c81  test    rax, rax
0x140041c84  jnz     short loc_140041CB3
0x140041c86  mov     rcx, cs:WPP_GLOBAL_Control
0x140041c8d  lea     rax, WPP_GLOBAL_Control
0x140041c94  cmp     rcx, rax
0x140041c97  jz      loc_140041D98
0x140041c9d  test    byte ptr [rcx+1Ch], 1
0x140041ca1  jz      loc_140041D98
0x140041ca7  lea     edx, [rdi+4Bh]
0x140041caa  lea     r9d, [rdi+8]
0x140041cae  jmp     loc_140041D88
0x140041cb3  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x140041cb8  lea     rax, [rsp+48h+TokenInformationLength]
0x140041cbd  mov     r8, rdi; TokenInformation
0x140041cc0  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x140041cc5  mov     edx, 27h ; '''; TokenInformationClass
0x140041cca  mov     rcx, rbx; TokenHandle
0x140041ccd  call    cs:__imp_NtQueryInformationToken
0x140041cd3  mov     r9d, eax
0x140041cd6  test    eax, eax
0x140041cd8  jns     short loc_140041D22
0x140041cda  mov     rcx, cs:WPP_GLOBAL_Control
0x140041ce1  lea     rax, WPP_GLOBAL_Control
0x140041ce8  cmp     rcx, rax
0x140041ceb  jz      short loc_140041D08
0x140041ced  test    byte ptr [rcx+1Ch], 1
0x140041cf1  jz      short loc_140041D08
0x140041cf3  mov     rcx, [rcx+10h]
0x140041cf7  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x140041cfe  mov     edx, 4Ch ; 'L'
0x140041d03  call    WPP_SF_d
0x140041d08  mov     rcx, gs:60h
0x140041d11  mov     r8, rdi; P
0x140041d14  xor     edx, edx; Flags
0x140041d16  mov     rcx, [rcx+30h]; HeapHandle
0x140041d1a  call    cs:__imp_RtlFreeHeap
0x140041d20  jmp     short loc_140041D50
0x140041d22  xor     ebx, ebx
0x140041d24  cmp     ebx, [rdi+4]
0x140041d27  jnb     short loc_140041D50
0x140041d29  mov     rax, [rdi+8]
0x140041d2d  lea     rcx, [rbx+rbx*4]
0x140041d31  mov     r8b, 1; CaseInsensitive
0x140041d34  lea     rdx, [rax+rcx*8]; String2
0x140041d38  lea     rcx, [rsp+48h+String1]; String1
0x140041d3d  call    cs:__imp_RtlCompareUnicodeString
0x140041d43  test    eax, eax
0x140041d45  jz      short loc_140041D4B
0x140041d47  inc     ebx
0x140041d49  jmp     short loc_140041D24
0x140041d4b  mov     esi, 1
0x140041d50  mov     rcx, gs:60h
0x140041d59  mov     r8, rdi; P
0x140041d5c  xor     edx, edx; Flags
0x140041d5e  mov     rcx, [rcx+30h]; HeapHandle
0x140041d62  call    cs:__imp_RtlFreeHeap
0x140041d68  jmp     short loc_140041D98
0x140041d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140041d71  lea     rax, WPP_GLOBAL_Control
0x140041d78  cmp     rcx, rax
0x140041d7b  jz      short loc_140041D98
0x140041d7d  test    byte ptr [rcx+1Ch], 1
0x140041d81  jz      short loc_140041D98
0x140041d83  mov     edx, 4Ah ; 'J'
0x140041d88  mov     rcx, [rcx+10h]
0x140041d8c  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x140041d93  call    WPP_SF_d
0x140041d98  mov     rbx, [rsp+48h+arg_0]
0x140041d9d  mov     eax, esi
0x140041d9f  mov     rsi, [rsp+48h+arg_10]
0x140041da4  add     rsp, 40h
0x140041da8  pop     rdi
0x140041da9  retn
```
