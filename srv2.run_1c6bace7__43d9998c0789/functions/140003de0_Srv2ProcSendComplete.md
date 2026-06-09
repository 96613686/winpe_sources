# Srv2ProcSendComplete

- ea: `0x140003de0`
- end: `0x140004017`
- name: `Srv2ProcSendComplete`
- size: `567`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140003de0`
- `0x140004020`
- `0x1400051dc`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140003e9f`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140003e9f`
- `ntoskrnl!KeSetEvent` at `0x140004006`
- `ntoskrnl!KeSetEvent` at `0x140004006`
- `ntoskrnl!KeReadStateEvent` at `0x140003ed9`
- `ntoskrnl!KeReadStateEvent` at `0x140003ed9`
- `ntoskrnl!RtlInitAnsiString` at `0x140003fb5`
- `ntoskrnl!RtlInitAnsiString` at `0x140003fb5`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140003ebb`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140003ebb`
- `HAL!KeQueryPerformanceCounter` at `0x140003f33`
- `HAL!KeQueryPerformanceCounter` at `0x140003f82`
- `HAL!KeQueryPerformanceCounter` at `0x140003f33`
- `HAL!KeQueryPerformanceCounter` at `0x140003f82`

## string_xrefs

- `0x140003f9b`: `Srv2PostToThreadPool`

## pseudocode

```c
int __fastcall Srv2ProcSendComplete(int a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 v6; // rax
  bool v7; // zf
  __int64 v8; // rdi
  __int64 v9; // rdi
  PSLIST_ENTRY v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  LARGE_INTEGER PerformanceCounter; // rax
  unsigned int v15; // ecx
  __int64 v16; // r8
  LARGE_INTEGER v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rax
  int v20; // edx
  int v21; // ecx
  _STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF

  v3 = *(_QWORD *)(a3 + 24);
  *(_DWORD *)(v3 + 496) = a1;
  *(_QWORD *)(v3 + 504) = a2;
  v4 = *(_QWORD *)(a3 + 32);
  if ( v4 )
    *(_QWORD *)(v3 + 48) = v4;
  _InterlockedAdd64(
    (volatile signed __int64 *)Srv2HotGlobals + 16 * (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) + 5,
    (int)a2);
  v5 = v3 + 584;
  v6 = MEMORY[0xFFFFF78000000014];
  if ( (unsigned __int8)(*(_BYTE *)(v3 + 713) - 2) <= 1u )
  {
    v13 = *(_QWORD *)(v3 + 696);
    if ( v13 <= MEMORY[0xFFFFF78000000014] - *(_QWORD *)(v3 + 736) )
      v13 = MEMORY[0xFFFFF78000000014] - *(_QWORD *)(v3 + 736);
    *(_QWORD *)(v3 + 696) = v13;
  }
  if ( (unsigned __int8)(*(_BYTE *)(v3 + 714) - 4) <= 1u )
  {
    v11 = *(_QWORD *)(v3 + 744);
    v12 = v6 - v11;
    if ( v11 <= v12 )
      v11 = v12;
    *(_QWORD *)(v3 + 704) = v11;
  }
  v7 = *(_BYTE *)(v3 + 600) == 0;
  *(_WORD *)(v3 + 713) = -1;
  if ( !v7 )
  {
    PerformanceCounter = KeQueryPerformanceCounter(0);
    v15 = *(unsigned __int8 *)(v3 + 712);
    if ( (_BYTE)v15 != 0xFF )
    {
      v16 = *(_QWORD *)(v3 + 720);
      if ( PerformanceCounter.QuadPart > v16 )
        *(_QWORD *)(v5 + 8LL * *(unsigned __int8 *)(v3 + 712) + 40) += PerformanceCounter.QuadPart - v16;
      ++*(_WORD *)(v5 + 2LL * v15 + 18);
    }
    *(_QWORD *)(v3 + 688) = PerformanceCounter.QuadPart - *(_QWORD *)(v3 + 728);
    *(_BYTE *)(v3 + 712) = -1;
  }
  v7 = *(_DWORD *)(v3 + 8) == 5;
  *(_DWORD *)(v3 + 72) = 0;
  if ( v7 )
  {
    v7 = *(_BYTE *)(v3 + 600) == 0;
    DestinationString = 0;
    if ( !v7 )
    {
      v17 = KeQueryPerformanceCounter(0);
      LOBYTE(v18) = 1;
      v19 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SRV2_PERF_UPDATE_PERF_COUNTER)(
              v3 + 584,
              v18,
              (LARGE_INTEGER)v17.QuadPart);
      *(_BYTE *)(v3 + 712) = 1;
      *(_QWORD *)(v3 + 720) = v19;
      RtlInitAnsiString(&DestinationString, "Srv2PostToThreadPool");
      if ( (Microsoft_Windows_SMBServerEnableBits & 4) != 0 )
        McTemplateK0qqhsr2_EtwWriteTransfer(
          v21,
          v20,
          v3 + 584,
          1,
          135,
          DestinationString.Length,
          (__int64)DestinationString.Buffer);
    }
  }
  v8 = *(_QWORD *)(*(_QWORD *)(v3 + 64) + 136LL);
  v9 = *(_QWORD *)(v8 + 8LL * KeGetCurrentNodeNumber() + 8);
  v10 = ExpInterlockedPushEntrySList((PSLIST_HEADER)(v9 + 16), (PSLIST_ENTRY)(v3 + 32));
  if ( !v10 )
  {
    if ( *(_WORD *)(v9 + 66) )
    {
      LODWORD(v10) = KeReadStateEvent((PRKEVENT)(v9 + 72));
      if ( !(_DWORD)v10 )
        LODWORD(v10) = KeSetEvent((PRKEVENT)(v9 + 72), 0, 0);
    }
  }
  return (int)v10;
}

```

## disassembly

```asm
0x140003de0  mov     [rsp+arg_0], rbx
0x140003de5  push    rdi
0x140003de6  sub     rsp, 50h
0x140003dea  mov     rbx, [r8+18h]
0x140003dee  mov     eax, edx
0x140003df0  mov     [rbx+1F0h], ecx
0x140003df6  mov     [rbx+1F8h], rax
0x140003dfd  mov     rax, [r8+20h]
0x140003e01  test    rax, rax
0x140003e04  jz      short loc_140003E0A
0x140003e06  mov     [rbx+30h], rax
0x140003e0a  mov     eax, gs:1A4h
0x140003e12  mov     ecx, eax
0x140003e14  mov     rax, cs:Srv2HotGlobals
0x140003e1b  shl     rcx, 7
0x140003e1f  movsxd  rdx, edx
0x140003e22  lock add [rcx+rax+28h], rdx
0x140003e28  mov     rax, 0FFFFF78000000014h
0x140003e32  lea     rdi, [rbx+248h]
0x140003e39  mov     rax, [rax]
0x140003e3c  movzx   ecx, byte ptr [rdi+81h]
0x140003e43  sub     cl, 2
0x140003e46  cmp     cl, 1
0x140003e49  jbe     loc_140003F13
0x140003e4f  movzx   ecx, byte ptr [rdi+82h]
0x140003e56  sub     cl, 4
0x140003e59  cmp     cl, 1
0x140003e5c  jbe     loc_140003EF9
0x140003e62  cmp     byte ptr [rdi+10h], 0
0x140003e66  mov     word ptr [rdi+81h], 0FFFFh
0x140003e6f  jnz     loc_140003F31
0x140003e75  cmp     dword ptr [rbx+8], 5
0x140003e79  mov     dword ptr [rbx+48h], 0
0x140003e80  jnz     short loc_140003E94
0x140003e82  cmp     byte ptr [rdi+10h], 0
0x140003e86  xorps   xmm0, xmm0
0x140003e89  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x140003e8e  jnz     loc_140003F80
0x140003e94  mov     rax, [rbx+40h]
0x140003e98  mov     rdi, [rax+88h]
0x140003e9f  call    cs:__imp_KeGetCurrentNodeNumber
0x140003ea6  nop     dword ptr [rax+rax+00h]
0x140003eab  movzx   eax, ax
0x140003eae  lea     rdx, [rbx+20h]; ListEntry
0x140003eb2  mov     rdi, [rdi+rax*8+8]
0x140003eb7  lea     rcx, [rdi+10h]; ListHead
0x140003ebb  call    cs:__imp_ExpInterlockedPushEntrySList
0x140003ec2  nop     dword ptr [rax+rax+00h]
0x140003ec7  test    rax, rax
0x140003eca  jnz     short loc_140003EED
0x140003ecc  movzx   ecx, word ptr [rdi+42h]
0x140003ed0  cmp     ax, cx
0x140003ed3  jz      short loc_140003EED
0x140003ed5  lea     rcx, [rdi+48h]; Event
0x140003ed9  call    cs:__imp_KeReadStateEvent
0x140003ee0  nop     dword ptr [rax+rax+00h]
0x140003ee5  test    eax, eax
0x140003ee7  jz      loc_140003FFD
0x140003eed  mov     rbx, [rsp+58h+arg_0]
0x140003ef2  add     rsp, 50h
0x140003ef6  pop     rdi
0x140003ef7  retn
0x140003ef9  mov     rcx, [rdi+0A0h]
0x140003f00  sub     rax, rcx
0x140003f03  cmp     rcx, rax
0x140003f06  cmovle  rcx, rax
0x140003f0a  mov     [rdi+78h], rcx
0x140003f0e  jmp     loc_140003E62
0x140003f13  mov     rcx, [rdi+70h]
0x140003f17  mov     rdx, rax
0x140003f1a  sub     rdx, [rdi+98h]
0x140003f21  cmp     rcx, rdx
0x140003f24  cmovle  rcx, rdx
0x140003f28  mov     [rdi+70h], rcx
0x140003f2c  jmp     loc_140003E4F
0x140003f31  xor     ecx, ecx; PerformanceFrequency
0x140003f33  call    cs:__imp_KeQueryPerformanceCounter
0x140003f3a  nop     dword ptr [rax+rax+00h]
0x140003f3f  movzx   ecx, byte ptr [rdi+80h]
0x140003f46  cmp     cl, 0FFh
0x140003f49  jz      short loc_140003F69
0x140003f4b  mov     r8, [rdi+88h]
0x140003f52  mov     edx, ecx
0x140003f54  cmp     rax, r8
0x140003f57  jle     short loc_140003F64
0x140003f59  mov     rcx, rax
0x140003f5c  sub     rcx, r8
0x140003f5f  add     [rdi+rdx*8+28h], rcx
0x140003f64  inc     word ptr [rdi+rdx*2+12h]
0x140003f69  sub     rax, [rdi+90h]
0x140003f70  mov     [rdi+68h], rax
0x140003f74  mov     byte ptr [rdi+80h], 0FFh
0x140003f7b  jmp     loc_140003E75
0x140003f80  xor     ecx, ecx; PerformanceFrequency
0x140003f82  call    cs:__imp_KeQueryPerformanceCounter
0x140003f89  nop     dword ptr [rax+rax+00h]
0x140003f8e  mov     dl, 1
0x140003f90  mov     rcx, rdi
0x140003f93  mov     r8, rax
0x140003f96  call    SRV2_PERF_UPDATE_PERF_COUNTER
0x140003f9b  lea     rdx, SourceString; "Srv2PostToThreadPool"
0x140003fa2  mov     byte ptr [rdi+80h], 1
0x140003fa9  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x140003fae  mov     [rdi+88h], rax
0x140003fb5  call    cs:__imp_RtlInitAnsiString
0x140003fbc  nop     dword ptr [rax+rax+00h]
0x140003fc1  test    cs:Microsoft_Windows_SMBServerEnableBits, 4
0x140003fc8  jz      loc_140003E94
0x140003fce  mov     rax, [rsp+58h+DestinationString.Buffer]
0x140003fd3  mov     r9d, 1
0x140003fd9  mov     [rsp+58h+var_28], rax
0x140003fde  mov     r8, rdi
0x140003fe1  movzx   eax, [rsp+58h+DestinationString.Length]
0x140003fe6  mov     [rsp+58h+var_30], ax
0x140003feb  mov     [rsp+58h+var_38], 187h
0x140003ff3  call    McTemplateK0qqhsr2_EtwWriteTransfer
0x140003ff8  jmp     loc_140003E94
0x140003ffd  xor     r8d, r8d; Wait
0x140004000  lea     rcx, [rdi+48h]; Event
0x140004004  xor     edx, edx; Increment
0x140004006  call    cs:__imp_KeSetEvent
0x14000400d  nop     dword ptr [rax+rax+00h]
0x140004012  jmp     loc_140003EED
```
