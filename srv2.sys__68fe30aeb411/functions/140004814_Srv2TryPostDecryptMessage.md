# Srv2TryPostDecryptMessage

- ea: `0x140004814`
- end: `0x140004957`
- name: `Srv2TryPostDecryptMessage`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400055b0`

## callees

- `0x140004020`
- `0x140004814`
- `0x140004960`
- `0x1400051dc`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140004886`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140004886`
- `ntoskrnl!RtlInitAnsiString` at `0x14000490f`
- `ntoskrnl!RtlInitAnsiString` at `0x14000490f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400048a2`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400048a2`
- `HAL!KeQueryPerformanceCounter` at `0x1400048dc`
- `HAL!KeQueryPerformanceCounter` at `0x1400048dc`

## string_xrefs

- `0x1400048f5`: `Srv2PostToThreadPool`

## pseudocode

```c
char __fastcall Srv2TryPostDecryptMessage(__int64 a1)
{
  unsigned __int32 v2; // eax
  unsigned __int32 v3; // edx
  bool v4; // zf
  __int64 v5; // rbx
  __int64 v6; // rbx
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v9; // rdx
  __int64 v10; // rax
  int v11; // edx
  int v12; // ecx
  struct _STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF

  v2 = _InterlockedCompareExchange(&Srv2AsyncDecryptionCount, 0, 0);
  do
  {
    if ( v2 >= Smb2MaxAsyncDecryptionThreads )
      return 0;
    v3 = v2;
    v2 = _InterlockedCompareExchange(&Srv2AsyncDecryptionCount, v2 + 1, v2);
  }
  while ( v2 != v3 );
  v4 = *(_DWORD *)(a1 + 8) == 5;
  *(_QWORD *)(a1 + 48) = Srv2DecryptMessageWorker;
  *(_DWORD *)(a1 + 72) = 0;
  if ( v4 )
  {
    v4 = *(_BYTE *)(a1 + 600) == 0;
    DestinationString = 0;
    if ( !v4 )
    {
      PerformanceCounter = KeQueryPerformanceCounter(0);
      LOBYTE(v9) = 1;
      v10 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SRV2_PERF_UPDATE_PERF_COUNTER)(
              a1 + 584,
              v9,
              (LARGE_INTEGER)PerformanceCounter.QuadPart);
      *(_BYTE *)(a1 + 712) = 1;
      *(_QWORD *)(a1 + 720) = v10;
      RtlInitAnsiString(&DestinationString, "Srv2PostToThreadPool");
      if ( (Microsoft_Windows_SMBServerEnableBits & 4) != 0 )
        McTemplateK0qqhsr2_EtwWriteTransfer(
          v12,
          v11,
          a1 + 584,
          1,
          135,
          DestinationString.Length,
          (__int64)DestinationString.Buffer);
    }
  }
  v5 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 136LL);
  v6 = *(_QWORD *)(v5 + 8LL * KeGetCurrentNodeNumber() + 8);
  if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v6 + 16), (PSLIST_ENTRY)(a1 + 32)) )
  {
    if ( *(_WORD *)(v6 + 66) )
      RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v6);
  }
  return 1;
}

```

## disassembly

```asm
0x140004814  mov     [rsp+arg_0], rbx
0x140004819  push    rdi
0x14000481a  sub     rsp, 50h
0x14000481e  mov     r8d, cs:Smb2MaxAsyncDecryptionThreads
0x140004825  xor     edx, edx
0x140004827  xor     eax, eax
0x140004829  mov     rdi, rcx
0x14000482c  lock cmpxchg cs:Srv2AsyncDecryptionCount, edx
0x140004834  cmp     eax, r8d
0x140004837  jnb     loc_1400048D6
0x14000483d  mov     edx, eax
0x14000483f  lea     ecx, [rax+1]
0x140004842  lock cmpxchg cs:Srv2AsyncDecryptionCount, ecx
0x14000484a  cmp     eax, edx
0x14000484c  jnz     short loc_140004834
0x14000484e  cmp     dword ptr [rdi+8], 5
0x140004852  lea     rax, Srv2DecryptMessageWorker
0x140004859  mov     [rdi+30h], rax
0x14000485d  mov     dword ptr [rdi+48h], 0
0x140004864  jnz     short loc_14000487B
0x140004866  lea     rbx, [rdi+248h]
0x14000486d  xorps   xmm0, xmm0
0x140004870  cmp     byte ptr [rbx+10h], 0
0x140004874  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x140004879  jnz     short loc_1400048DA
0x14000487b  mov     rax, [rdi+40h]
0x14000487f  mov     rbx, [rax+88h]
0x140004886  call    cs:__imp_KeGetCurrentNodeNumber
0x14000488d  nop     dword ptr [rax+rax+00h]
0x140004892  movzx   eax, ax
0x140004895  lea     rdx, [rdi+20h]; ListEntry
0x140004899  mov     rbx, [rbx+rax*8+8]
0x14000489e  lea     rcx, [rbx+10h]; ListHead
0x1400048a2  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400048a9  nop     dword ptr [rax+rax+00h]
0x1400048ae  test    rax, rax
0x1400048b1  jnz     short loc_1400048C8
0x1400048b3  movzx   r8d, word ptr [rbx+42h]
0x1400048b8  xor     edx, edx
0x1400048ba  cmp     dx, r8w
0x1400048be  jz      short loc_1400048C8
0x1400048c0  mov     rcx, rbx
0x1400048c3  call    RfspThreadPoolNodeWakeIdleWorker
0x1400048c8  mov     al, 1
0x1400048ca  mov     rbx, [rsp+58h+arg_0]
0x1400048cf  add     rsp, 50h
0x1400048d3  pop     rdi
0x1400048d4  retn
0x1400048d6  xor     al, al
0x1400048d8  jmp     short loc_1400048CA
0x1400048da  xor     ecx, ecx; PerformanceFrequency
0x1400048dc  call    cs:__imp_KeQueryPerformanceCounter
0x1400048e3  nop     dword ptr [rax+rax+00h]
0x1400048e8  mov     dl, 1
0x1400048ea  mov     rcx, rbx
0x1400048ed  mov     r8, rax
0x1400048f0  call    SRV2_PERF_UPDATE_PERF_COUNTER
0x1400048f5  lea     rdx, SourceString; "Srv2PostToThreadPool"
0x1400048fc  mov     byte ptr [rbx+80h], 1
0x140004903  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x140004908  mov     [rbx+88h], rax
0x14000490f  call    cs:__imp_RtlInitAnsiString
0x140004916  nop     dword ptr [rax+rax+00h]
0x14000491b  test    cs:Microsoft_Windows_SMBServerEnableBits, 4
0x140004922  jz      loc_14000487B
0x140004928  mov     rax, [rsp+58h+DestinationString.Buffer]
0x14000492d  mov     r9d, 1
0x140004933  mov     [rsp+58h+var_28], rax
0x140004938  mov     r8, rbx
0x14000493b  movzx   eax, [rsp+58h+DestinationString.Length]
0x140004940  mov     [rsp+58h+var_30], ax
0x140004945  mov     [rsp+58h+var_38], 187h
0x14000494d  call    McTemplateK0qqhsr2_EtwWriteTransfer
0x140004952  jmp     loc_14000487B
```
