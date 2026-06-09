# Srv2PostAfterReceive

- ea: `0x1400175a0`
- end: `0x14001771f`
- name: `Srv2PostAfterReceive`
- size: `383`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140004020`
- `0x1400051dc`
- `0x1400175a0`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140017615`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140017615`
- `ntoskrnl!KeSetEvent` at `0x14001770e`
- `ntoskrnl!KeSetEvent` at `0x14001770e`
- `ntoskrnl!KeReadStateEvent` at `0x14001764f`
- `ntoskrnl!KeReadStateEvent` at `0x14001764f`
- `ntoskrnl!RtlInitAnsiString` at `0x1400176b9`
- `ntoskrnl!RtlInitAnsiString` at `0x1400176b9`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140017631`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140017631`
- `HAL!KeQueryPerformanceCounter` at `0x140017682`
- `HAL!KeQueryPerformanceCounter` at `0x140017682`

## string_xrefs

- `0x14001769f`: `Srv2PostToThreadPool`

## pseudocode

```c
int __fastcall Srv2PostAfterReceive(int a1, int a2, __int64 a3)
{
  __int64 v3; // rbx
  bool v4; // zf
  __int64 v5; // rdi
  __int64 v6; // rdi
  PSLIST_ENTRY v7; // rax
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v9; // rdx
  __int64 v10; // rax
  int v11; // edx
  int v12; // ecx
  struct _STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF

  v3 = *(_QWORD *)(a3 + 24);
  if ( (int)(a1 + 0x80000000) < 0 || a1 == -2147483643 )
  {
    *(_DWORD *)(v3 + 404) += a2;
    *(_DWORD *)(*(_QWORD *)(v3 + 304) + 36LL) = *(_DWORD *)(v3 + 404);
    if ( *(_DWORD *)(v3 + 404) == *(_DWORD *)(v3 + 400) )
      *(_BYTE *)(v3 + 472) = 1;
  }
  v4 = *(_DWORD *)(v3 + 8) == 5;
  *(_DWORD *)(v3 + 72) = 0;
  if ( v4 )
  {
    v4 = *(_BYTE *)(v3 + 600) == 0;
    DestinationString = 0;
    if ( !v4 )
    {
      PerformanceCounter = KeQueryPerformanceCounter(0);
      LOBYTE(v9) = 1;
      v10 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SRV2_PERF_UPDATE_PERF_COUNTER)(
              v3 + 584,
              v9,
              (LARGE_INTEGER)PerformanceCounter.QuadPart);
      *(_BYTE *)(v3 + 712) = 1;
      *(_QWORD *)(v3 + 720) = v10;
      RtlInitAnsiString(&DestinationString, "Srv2PostToThreadPool");
      if ( (Microsoft_Windows_SMBServerEnableBits & 4) != 0 )
        McTemplateK0qqhsr2_EtwWriteTransfer(
          v12,
          v11,
          v3 + 584,
          1,
          135,
          DestinationString.Length,
          (__int64)DestinationString.Buffer);
    }
  }
  v5 = *(_QWORD *)(*(_QWORD *)(v3 + 64) + 136LL);
  v6 = *(_QWORD *)(v5 + 8LL * KeGetCurrentNodeNumber() + 8);
  v7 = ExpInterlockedPushEntrySList((PSLIST_HEADER)(v6 + 16), (PSLIST_ENTRY)(v3 + 32));
  if ( !v7 )
  {
    if ( *(_WORD *)(v6 + 66) )
    {
      LODWORD(v7) = KeReadStateEvent((PRKEVENT)(v6 + 72));
      if ( !(_DWORD)v7 )
        LODWORD(v7) = KeSetEvent((PRKEVENT)(v6 + 72), 0, 0);
    }
  }
  return (int)v7;
}

```

## disassembly

```asm
0x1400175a0  mov     [rsp+arg_0], rbx
0x1400175a5  push    rdi
0x1400175a6  sub     rsp, 50h
0x1400175aa  mov     rbx, [r8+18h]
0x1400175ae  mov     r8d, 80000000h
0x1400175b4  lea     eax, [rcx+r8]
0x1400175b8  test    r8d, eax
0x1400175bb  jz      loc_14001766F
0x1400175c1  add     [rbx+194h], edx
0x1400175c7  mov     rax, [rbx+130h]
0x1400175ce  mov     ecx, [rbx+194h]
0x1400175d4  mov     [rax+24h], ecx
0x1400175d7  mov     eax, [rbx+190h]
0x1400175dd  cmp     [rbx+194h], eax
0x1400175e3  jnz     short loc_1400175EC
0x1400175e5  mov     byte ptr [rbx+1D8h], 1
0x1400175ec  cmp     dword ptr [rbx+8], 5
0x1400175f0  mov     dword ptr [rbx+48h], 0
0x1400175f7  jnz     short loc_14001760A
0x1400175f9  cmp     byte ptr [rbx+258h], 0
0x140017600  xorps   xmm0, xmm0
0x140017603  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x140017608  jnz     short loc_140017680
0x14001760a  mov     rax, [rbx+40h]
0x14001760e  mov     rdi, [rax+88h]
0x140017615  call    cs:__imp_KeGetCurrentNodeNumber
0x14001761c  nop     dword ptr [rax+rax+00h]
0x140017621  movzx   eax, ax
0x140017624  lea     rdx, [rbx+20h]; ListEntry
0x140017628  mov     rdi, [rdi+rax*8+8]
0x14001762d  lea     rcx, [rdi+10h]; ListHead
0x140017631  call    cs:__imp_ExpInterlockedPushEntrySList
0x140017638  nop     dword ptr [rax+rax+00h]
0x14001763d  test    rax, rax
0x140017640  jnz     short loc_140017663
0x140017642  movzx   ecx, word ptr [rdi+42h]
0x140017646  cmp     ax, cx
0x140017649  jz      short loc_140017663
0x14001764b  lea     rcx, [rdi+48h]; Event
0x14001764f  call    cs:__imp_KeReadStateEvent
0x140017656  nop     dword ptr [rax+rax+00h]
0x14001765b  test    eax, eax
0x14001765d  jz      loc_140017705
0x140017663  mov     rbx, [rsp+58h+arg_0]
0x140017668  add     rsp, 50h
0x14001766c  pop     rdi
0x14001766d  retn
0x14001766f  cmp     ecx, 80000005h
0x140017675  jz      loc_1400175C1
0x14001767b  jmp     loc_1400175EC
0x140017680  xor     ecx, ecx; PerformanceFrequency
0x140017682  call    cs:__imp_KeQueryPerformanceCounter
0x140017689  nop     dword ptr [rax+rax+00h]
0x14001768e  mov     dl, 1
0x140017690  lea     rcx, [rbx+248h]
0x140017697  mov     r8, rax
0x14001769a  call    SRV2_PERF_UPDATE_PERF_COUNTER
0x14001769f  lea     rdx, SourceString; "Srv2PostToThreadPool"
0x1400176a6  mov     byte ptr [rbx+2C8h], 1
0x1400176ad  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x1400176b2  mov     [rbx+2D0h], rax
0x1400176b9  call    cs:__imp_RtlInitAnsiString
0x1400176c0  nop     dword ptr [rax+rax+00h]
0x1400176c5  test    cs:Microsoft_Windows_SMBServerEnableBits, 4
0x1400176cc  jz      loc_14001760A
0x1400176d2  mov     rax, [rsp+58h+DestinationString.Buffer]
0x1400176d7  lea     r8, [rbx+248h]
0x1400176de  mov     [rsp+58h+var_28], rax
0x1400176e3  mov     r9d, 1
0x1400176e9  movzx   eax, [rsp+58h+DestinationString.Length]
0x1400176ee  mov     [rsp+58h+var_30], ax
0x1400176f3  mov     [rsp+58h+var_38], 187h
0x1400176fb  call    McTemplateK0qqhsr2_EtwWriteTransfer
0x140017700  jmp     loc_14001760A
0x140017705  xor     r8d, r8d; Wait
0x140017708  lea     rcx, [rdi+48h]; Event
0x14001770c  xor     edx, edx; Increment
0x14001770e  call    cs:__imp_KeSetEvent
0x140017715  nop     dword ptr [rax+rax+00h]
0x14001771a  jmp     loc_140017663
```
