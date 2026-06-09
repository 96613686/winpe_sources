# TdxTlIoRequestEndpointComplete

- ea: `0x14000a040`
- end: `0x14000a19b`
- name: `TdxTlIoRequestEndpointComplete`
- size: `347`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005b00`

## callees

- `0x1400047d0`
- `0x140008c50`
- `0x14000a040`
- `0x140012b8c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000a07c`
- `ntoskrnl!IofCompleteRequest` at `0x14000a07c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a098`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a098`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000a0ec`
- `ntoskrnl!RtlGetCallersAddress` at `0x14000a0ec`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a114`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a114`

## string_xrefs

- `0x14000a167`: `TdxTlIoRequestEndpointComplete`

## pseudocode

```c
__int64 __fastcall TdxTlIoRequestEndpointComplete(IRP *a1, NTSTATUS a2, ULONG_PTR a3)
{
  _DWORD *v3; // rbx
  _DWORD *FsContext; // rsi
  int v5; // edi
  KIRQL v6; // al
  int v7; // ecx
  KIRQL v8; // di
  _DWORD *v9; // rdx
  __int64 result; // rax
  PVOID CallersAddress; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0;
  FsContext = a1->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  v5 = FsContext[1];
  a1->IoStatus.Status = a2;
  if ( v5 != 2 )
    v3 = FsContext;
  a1->IoStatus.Information = a3;
  if ( v5 != 2 )
    FsContext = 0;
  IofCompleteRequest(a1, 2);
  if ( v5 == 2 )
    return DbgTdxDereferenceConnection(FsContext, "TdxTlIoRequestEndpointComplete", 1242);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v3 + 69);
  v7 = v3[4];
  v8 = v6;
  v9 = &v3[8 * v3[204]];
  CallersAddress = 0;
  v9[146] = v7 - 1;
  *((_QWORD *)v9 + 70) = "minio\\netio\\session\\tdi\\request.c";
  v9[142] = 1244;
  RtlGetCallersAddress(&CallersAddress, (PVOID *)v9 + 72);
  v3[204] = ((unsigned __int8)v3[204] + 1) & 7;
  KeReleaseSpinLock((PKSPIN_LOCK)v3 + 69, v8);
  result = (unsigned int)_InterlockedExchangeAdd(v3 + 4, 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids, v3);
    }
    return TdxCleanupObjectHeader(v3);
  }
  return result;
}

```

## disassembly

```asm
0x14000a040  mov     [rsp+arg_8], rbx
0x14000a045  mov     [rsp+arg_10], rsi
0x14000a04a  push    rdi
0x14000a04b  sub     rsp, 20h
0x14000a04f  mov     rax, [rcx+0B8h]
0x14000a056  xor     ebx, ebx
0x14000a058  mov     r9, [rax+30h]
0x14000a05c  mov     rsi, [r9+18h]
0x14000a060  mov     edi, [rsi+4]
0x14000a063  cmp     edi, 2
0x14000a066  mov     [rcx+30h], edx
0x14000a069  mov     dl, 2; PriorityBoost
0x14000a06b  cmovnz  rbx, rsi
0x14000a06f  mov     [rcx+38h], r8
0x14000a073  xor     eax, eax
0x14000a075  cmp     edi, 2
0x14000a078  cmovnz  rsi, rax
0x14000a07c  call    cs:__imp_IofCompleteRequest
0x14000a083  nop     dword ptr [rax+rax+00h]
0x14000a088  cmp     edi, 2
0x14000a08b  jz      loc_14000A161
0x14000a091  lea     rcx, [rbx+228h]; SpinLock
0x14000a098  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a09f  nop     dword ptr [rax+rax+00h]
0x14000a0a4  mov     ecx, [rbx+10h]
0x14000a0a7  movzx   edi, al
0x14000a0aa  mov     edx, [rbx+330h]
0x14000a0b0  lea     rax, aMinioNetioSess_0; "minio\\netio\\session\\tdi\\request.c"
0x14000a0b7  shl     rdx, 5
0x14000a0bb  add     rdx, rbx
0x14000a0be  mov     [rsp+28h+CallersAddress], 0
0x14000a0c7  dec     ecx
0x14000a0c9  mov     [rdx+248h], ecx
0x14000a0cf  lea     rcx, [rsp+28h+CallersAddress]; CallersAddress
0x14000a0d4  mov     [rdx+230h], rax
0x14000a0db  mov     dword ptr [rdx+238h], 4DCh
0x14000a0e5  add     rdx, 240h; CallersCaller
0x14000a0ec  call    cs:__imp_RtlGetCallersAddress
0x14000a0f3  nop     dword ptr [rax+rax+00h]
0x14000a0f8  mov     eax, [rbx+330h]
0x14000a0fe  lea     rcx, [rbx+228h]; SpinLock
0x14000a105  inc     eax
0x14000a107  movzx   edx, dil; NewIrql
0x14000a10b  and     eax, 7
0x14000a10e  mov     [rbx+330h], eax
0x14000a114  call    cs:__imp_KeReleaseSpinLock
0x14000a11b  nop     dword ptr [rax+rax+00h]
0x14000a120  mov     eax, 0FFFFFFFFh
0x14000a125  lock xadd [rbx+10h], eax
0x14000a12a  cmp     eax, 1
0x14000a12d  jnz     short loc_14000A150
0x14000a12f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a136  lea     rax, WPP_GLOBAL_Control
0x14000a13d  cmp     rcx, rax
0x14000a140  jz      short loc_14000A148
0x14000a142  cmp     byte ptr [rcx+29h], 5
0x14000a146  jnb     short loc_14000A178
0x14000a148  mov     rcx, rbx
0x14000a14b  call    TdxCleanupObjectHeader
0x14000a150  mov     rbx, [rsp+28h+arg_8]
0x14000a155  mov     rsi, [rsp+28h+arg_10]
0x14000a15a  add     rsp, 20h
0x14000a15e  pop     rdi
0x14000a15f  retn
0x14000a161  mov     r8d, 4DAh
0x14000a167  lea     rdx, aTdxtliorequest; "TdxTlIoRequestEndpointComplete"
0x14000a16e  mov     rcx, rsi
0x14000a171  call    DbgTdxDereferenceConnection
0x14000a176  jmp     short loc_14000A150
0x14000a178  test    dword ptr [rcx+2Ch], 200h
0x14000a17f  jz      short loc_14000A148
0x14000a181  mov     rcx, [rcx+18h]
0x14000a185  lea     r8, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids
0x14000a18c  mov     edx, 11h
0x14000a191  mov     r9, rbx
0x14000a194  call    WPP_SF_q
0x14000a199  jmp     short loc_14000A148
```
