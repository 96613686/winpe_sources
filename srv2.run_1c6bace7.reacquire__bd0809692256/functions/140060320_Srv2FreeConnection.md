# Srv2FreeConnection

- ea: `0x140060320`
- end: `0x1400604df`
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
- `0x140060320`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400603fe`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006042d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400603fe`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006042d`
- `ntoskrnl!ExDeleteResourceLite` at `0x14006043d`
- `ntoskrnl!ExDeleteResourceLite` at `0x14006043d`
- `ntoskrnl!RtlInitString` at `0x1400603cf`
- `ntoskrnl!RtlInitString` at `0x1400603cf`
- `ntoskrnl!ExFlushLookasideListEx` at `0x1400604a2`
- `ntoskrnl!ExFlushLookasideListEx` at `0x1400604ba`
- `ntoskrnl!ExFlushLookasideListEx` at `0x1400604a2`
- `ntoskrnl!ExFlushLookasideListEx` at `0x1400604ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400603ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400603e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060418`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060463`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400603ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400603e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060418`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060463`
- `srvnet!SrvNetCloseConnection` at `0x140060381`
- `srvnet!SrvNetCloseConnection` at `0x140060381`

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
0x140060320  mov     [rsp+arg_8], rbx
0x140060325  mov     [rsp+arg_10], rsi
0x14006032a  push    rdi
0x14006032b  sub     rsp, 30h
0x14006032f  mov     rbx, rcx
0x140060332  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140060339  lea     rax, WPP_GLOBAL_Control
0x140060340  cmp     rcx, rax
0x140060343  jz      short loc_140060372
0x140060345  mov     eax, [rcx+2Ch]
0x140060348  test    al, 1
0x14006034a  jz      short loc_140060372
0x14006034c  cmp     byte ptr [rcx+29h], 2
0x140060350  jb      short loc_140060372
0x140060352  mov     rax, [rbx]
0x140060355  mov     edx, 16h
0x14006035a  mov     rcx, cs:WPP_GLOBAL_Control
0x140060361  mov     r9, rbx
0x140060364  mov     [rsp+38h+var_18], rax
0x140060369  mov     rcx, [rcx+18h]
0x14006036d  call    WPP_SF_qP
0x140060372  mov     rcx, rbx
0x140060375  call    Srv2GlobalConnectionListRemove
0x14006037a  mov     rcx, [rbx+1E0h]
0x140060381  call    cs:__imp_SrvNetCloseConnection
0x140060388  nop     dword ptr [rax+rax+00h]
0x14006038d  mov     rcx, [rbx+1F0h]; void *
0x140060394  mov     qword ptr [rbx+1E0h], 0
0x14006039f  call    Smb2CleanupConnection
0x1400603a4  mov     rcx, rbx
0x1400603a7  call    Srv2RemoveConnectionFromEndpointList
0x1400603ac  mov     rcx, [rbx+160h]; P
0x1400603b3  test    rcx, rcx
0x1400603b6  jz      short loc_1400603DB
0x1400603b8  xor     edx, edx; Tag
0x1400603ba  call    cs:__imp_ExFreePoolWithTag
0x1400603c1  nop     dword ptr [rax+rax+00h]
0x1400603c6  lea     rcx, [rbx+158h]; DestinationString
0x1400603cd  xor     edx, edx; SourceString
0x1400603cf  call    cs:__imp_RtlInitString
0x1400603d6  nop     dword ptr [rax+rax+00h]
0x1400603db  mov     rcx, [rbx+170h]; P
0x1400603e2  test    rcx, rcx
0x1400603e5  jz      short loc_14006040A
0x1400603e7  xor     edx, edx; Tag
0x1400603e9  call    cs:__imp_ExFreePoolWithTag
0x1400603f0  nop     dword ptr [rax+rax+00h]
0x1400603f5  lea     rcx, [rbx+168h]; DestinationString
0x1400603fc  xor     edx, edx; SourceString
0x1400603fe  call    cs:__imp_RtlInitUnicodeString
0x140060405  nop     dword ptr [rax+rax+00h]
0x14006040a  mov     rcx, [rbx+180h]; P
0x140060411  test    rcx, rcx
0x140060414  jz      short loc_140060439
0x140060416  xor     edx, edx; Tag
0x140060418  call    cs:__imp_ExFreePoolWithTag
0x14006041f  nop     dword ptr [rax+rax+00h]
0x140060424  lea     rcx, [rbx+178h]; DestinationString
0x14006042b  xor     edx, edx; SourceString
0x14006042d  call    cs:__imp_RtlInitUnicodeString
0x140060434  nop     dword ptr [rax+rax+00h]
0x140060439  lea     rcx, [rbx+50h]; Resource
0x14006043d  call    cs:__imp_ExDeleteResourceLite
0x140060444  nop     dword ptr [rax+rax+00h]
0x140060449  mov     rsi, [rbx+1E8h]
0x140060450  mov     edx, 6332534Ch; Tag
0x140060455  mov     rcx, rbx; P
0x140060458  mov     qword ptr [rbx+1E8h], 0
0x140060463  call    cs:__imp_ExFreePoolWithTag
0x14006046a  nop     dword ptr [rax+rax+00h]
0x14006046f  or      eax, 0FFFFFFFFh
0x140060472  lock xadd cs:Srv2ConnectionCount, eax
0x14006047a  cmp     eax, 1
0x14006047d  jnz     short loc_1400604C6
0x14006047f  mov     rdi, cs:qword_140058148
0x140060486  mov     ebx, [rdi]
0x140060488  jmp     short loc_1400604AE
0x14006048a  mov     edx, ebx
0x14006048c  shl     rdx, 7
0x140060490  mov     al, [rdx+rdi+0B0h]
0x140060497  test    al, al
0x140060499  jz      short loc_1400604AE
0x14006049b  lea     rcx, [rdi+40h]
0x14006049f  add     rcx, rdx; Lookaside
0x1400604a2  call    cs:__imp_ExFlushLookasideListEx
0x1400604a9  nop     dword ptr [rax+rax+00h]
0x1400604ae  sub     ebx, 1
0x1400604b1  jns     short loc_14006048A
0x1400604b3  lea     rcx, Srv2PagedBlockTypeBuffer8K; Lookaside
0x1400604ba  call    cs:__imp_ExFlushLookasideListEx
0x1400604c1  nop     dword ptr [rax+rax+00h]
0x1400604c6  mov     rcx, rsi
0x1400604c9  call    Srv2DereferenceEndpoint
0x1400604ce  mov     rbx, [rsp+38h+arg_8]
0x1400604d3  mov     rsi, [rsp+38h+arg_10]
0x1400604d8  add     rsp, 30h
0x1400604dc  pop     rdi
0x1400604dd  retn
```
