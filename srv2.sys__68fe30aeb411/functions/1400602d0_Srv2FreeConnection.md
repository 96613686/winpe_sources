# Srv2FreeConnection

- ea: `0x1400602d0`
- end: `0x14006048f`
- name: `Srv2FreeConnection`
- size: `447`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140006580`
- `0x140006ad0`
- `0x14000ae60`

## callees

- `0x14000b0fc`
- `0x14001aa78`
- `0x14001f5e0`
- `0x1400238f8`
- `0x140023e24`
- `0x1400602d0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400603ae`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400603dd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400603ae`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400603dd`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400603ed`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400603ed`
- `ntoskrnl!RtlInitString` at `0x14006037f`
- `ntoskrnl!RtlInitString` at `0x14006037f`
- `ntoskrnl!ExFlushLookasideListEx` at `0x140060452`
- `ntoskrnl!ExFlushLookasideListEx` at `0x14006046a`
- `ntoskrnl!ExFlushLookasideListEx` at `0x140060452`
- `ntoskrnl!ExFlushLookasideListEx` at `0x14006046a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006036a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060399`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400603c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060413`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006036a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060399`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400603c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060413`
- `srvnet!SrvNetCloseConnection` at `0x140060331`
- `srvnet!SrvNetCloseConnection` at `0x140060331`

## pseudocode

```c
__int64 __fastcall Srv2FreeConnection(char *P, __int64 a2, __int64 a3)
{
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  __int64 v8; // rsi
  _BYTE *v9; // rdi
  unsigned int v10; // ebx
  unsigned __int64 v11; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qP(WPP_GLOBAL_Control->AttachedDevice, 22, a3, P, *(_QWORD *)P);
  }
  Srv2GlobalConnectionListRemove(P);
  SrvNetCloseConnection(*((_QWORD *)P + 60));
  v4 = (void *)*((_QWORD *)P + 62);
  *((_QWORD *)P + 60) = 0;
  Smb2CleanupConnection(v4);
  Srv2RemoveConnectionFromEndpointList(P);
  v5 = (void *)*((_QWORD *)P + 44);
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0);
    RtlInitString((PSTRING)(P + 344), 0);
  }
  v6 = (void *)*((_QWORD *)P + 46);
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0);
    RtlInitUnicodeString((PUNICODE_STRING)(P + 360), 0);
  }
  v7 = (void *)*((_QWORD *)P + 48);
  if ( v7 )
  {
    ExFreePoolWithTag(v7, 0);
    RtlInitUnicodeString((PUNICODE_STRING)(P + 376), 0);
  }
  ExDeleteResourceLite((PERESOURCE)(P + 80));
  v8 = *((_QWORD *)P + 61);
  *((_QWORD *)P + 61) = 0;
  ExFreePoolWithTag(P, 0x6332534Cu);
  if ( _InterlockedExchangeAdd(&Srv2ConnectionCount, 0xFFFFFFFF) == 1 )
  {
    v9 = qword_140058148;
    v10 = *(_DWORD *)qword_140058148;
    while ( (--v10 & 0x80000000) == 0 )
    {
      v11 = (unsigned __int64)v10 << 7;
      if ( v9[v11 + 176] )
        ExFlushLookasideListEx((PLOOKASIDE_LIST_EX)&v9[v11 + 64]);
    }
    ExFlushLookasideListEx(&Srv2PagedBlockTypeBuffer8K);
  }
  return Srv2DereferenceEndpoint(v8);
}

```

## disassembly

```asm
0x1400602d0  mov     [rsp+arg_8], rbx
0x1400602d5  mov     [rsp+arg_10], rsi
0x1400602da  push    rdi
0x1400602db  sub     rsp, 30h
0x1400602df  mov     rbx, rcx
0x1400602e2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400602e9  lea     rax, WPP_GLOBAL_Control
0x1400602f0  cmp     rcx, rax
0x1400602f3  jz      short loc_140060322
0x1400602f5  mov     eax, [rcx+2Ch]
0x1400602f8  test    al, 1
0x1400602fa  jz      short loc_140060322
0x1400602fc  cmp     byte ptr [rcx+29h], 2
0x140060300  jb      short loc_140060322
0x140060302  mov     rax, [rbx]
0x140060305  mov     edx, 16h
0x14006030a  mov     rcx, cs:WPP_GLOBAL_Control
0x140060311  mov     r9, rbx
0x140060314  mov     [rsp+38h+var_18], rax
0x140060319  mov     rcx, [rcx+18h]
0x14006031d  call    WPP_SF_qP
0x140060322  mov     rcx, rbx
0x140060325  call    Srv2GlobalConnectionListRemove
0x14006032a  mov     rcx, [rbx+1E0h]
0x140060331  call    cs:__imp_SrvNetCloseConnection
0x140060338  nop     dword ptr [rax+rax+00h]
0x14006033d  mov     rcx, [rbx+1F0h]; void *
0x140060344  mov     qword ptr [rbx+1E0h], 0
0x14006034f  call    Smb2CleanupConnection
0x140060354  mov     rcx, rbx
0x140060357  call    Srv2RemoveConnectionFromEndpointList
0x14006035c  mov     rcx, [rbx+160h]; P
0x140060363  test    rcx, rcx
0x140060366  jz      short loc_14006038B
0x140060368  xor     edx, edx; Tag
0x14006036a  call    cs:__imp_ExFreePoolWithTag
0x140060371  nop     dword ptr [rax+rax+00h]
0x140060376  lea     rcx, [rbx+158h]; DestinationString
0x14006037d  xor     edx, edx; SourceString
0x14006037f  call    cs:__imp_RtlInitString
0x140060386  nop     dword ptr [rax+rax+00h]
0x14006038b  mov     rcx, [rbx+170h]; P
0x140060392  test    rcx, rcx
0x140060395  jz      short loc_1400603BA
0x140060397  xor     edx, edx; Tag
0x140060399  call    cs:__imp_ExFreePoolWithTag
0x1400603a0  nop     dword ptr [rax+rax+00h]
0x1400603a5  lea     rcx, [rbx+168h]; DestinationString
0x1400603ac  xor     edx, edx; SourceString
0x1400603ae  call    cs:__imp_RtlInitUnicodeString
0x1400603b5  nop     dword ptr [rax+rax+00h]
0x1400603ba  mov     rcx, [rbx+180h]; P
0x1400603c1  test    rcx, rcx
0x1400603c4  jz      short loc_1400603E9
0x1400603c6  xor     edx, edx; Tag
0x1400603c8  call    cs:__imp_ExFreePoolWithTag
0x1400603cf  nop     dword ptr [rax+rax+00h]
0x1400603d4  lea     rcx, [rbx+178h]; DestinationString
0x1400603db  xor     edx, edx; SourceString
0x1400603dd  call    cs:__imp_RtlInitUnicodeString
0x1400603e4  nop     dword ptr [rax+rax+00h]
0x1400603e9  lea     rcx, [rbx+50h]; Resource
0x1400603ed  call    cs:__imp_ExDeleteResourceLite
0x1400603f4  nop     dword ptr [rax+rax+00h]
0x1400603f9  mov     rsi, [rbx+1E8h]
0x140060400  mov     edx, 6332534Ch; Tag
0x140060405  mov     rcx, rbx; P
0x140060408  mov     qword ptr [rbx+1E8h], 0
0x140060413  call    cs:__imp_ExFreePoolWithTag
0x14006041a  nop     dword ptr [rax+rax+00h]
0x14006041f  or      eax, 0FFFFFFFFh
0x140060422  lock xadd cs:Srv2ConnectionCount, eax
0x14006042a  cmp     eax, 1
0x14006042d  jnz     short loc_140060476
0x14006042f  mov     rdi, cs:qword_140058148
0x140060436  mov     ebx, [rdi]
0x140060438  jmp     short loc_14006045E
0x14006043a  mov     edx, ebx
0x14006043c  shl     rdx, 7
0x140060440  mov     al, [rdx+rdi+0B0h]
0x140060447  test    al, al
0x140060449  jz      short loc_14006045E
0x14006044b  lea     rcx, [rdi+40h]
0x14006044f  add     rcx, rdx; Lookaside
0x140060452  call    cs:__imp_ExFlushLookasideListEx
0x140060459  nop     dword ptr [rax+rax+00h]
0x14006045e  sub     ebx, 1
0x140060461  jns     short loc_14006043A
0x140060463  lea     rcx, Srv2PagedBlockTypeBuffer8K; Lookaside
0x14006046a  call    cs:__imp_ExFlushLookasideListEx
0x140060471  nop     dword ptr [rax+rax+00h]
0x140060476  mov     rcx, rsi
0x140060479  call    Srv2DereferenceEndpoint
0x14006047e  mov     rbx, [rsp+38h+arg_8]
0x140060483  mov     rsi, [rsp+38h+arg_10]
0x140060488  add     rsp, 30h
0x14006048c  pop     rdi
0x14006048d  retn
```
