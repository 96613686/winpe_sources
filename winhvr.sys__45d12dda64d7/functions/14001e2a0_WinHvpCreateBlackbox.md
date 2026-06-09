# WinHvpCreateBlackbox

- ea: `0x14001e2a0`
- end: `0x14001e419`
- name: `WinHvpCreateBlackbox`
- size: `377`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001bd40`
- `0x14001f740`

## callees

- `0x14000b008`
- `0x14000b040`
- `0x14001e2a0`

## import_xrefs

- `ntoskrnl!KeRegisterBugCheckReasonCallback` at `0x14001e308`
- `ntoskrnl!KeRegisterBugCheckReasonCallback` at `0x14001e3c0`
- `ntoskrnl!KeRegisterBugCheckReasonCallback` at `0x14001e308`
- `ntoskrnl!KeRegisterBugCheckReasonCallback` at `0x14001e3c0`
- `ntoskrnl!KeInitializeTriageDumpDataArray` at `0x14001e377`
- `ntoskrnl!KeInitializeTriageDumpDataArray` at `0x14001e377`
- `ntoskrnl!KeAddTriageDumpDataBlock` at `0x14001e3e7`
- `ntoskrnl!KeAddTriageDumpDataBlock` at `0x14001e407`
- `ntoskrnl!KeAddTriageDumpDataBlock` at `0x14001e3e7`
- `ntoskrnl!KeAddTriageDumpDataBlock` at `0x14001e407`

## pseudocode

```c
void WinHvpCreateBlackbox()
{
  signed __int64 Pool; // rax
  SIZE_T v1; // r9
  SIZE_T v2; // r9

  if ( !*(_QWORD *)&WinHvpBlackbox )
  {
    if ( byte_1400161B1 && qword_1400161C0 )
    {
      if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&WinHvpBlackbox, qword_1400161C0, 0) )
      {
        *(_BYTE *)(*(_QWORD *)&WinHvpBlackbox + 1076LL) = 0;
        KeRegisterBugCheckReasonCallback(
          (PKBUGCHECK_REASON_CALLBACK_RECORD)(*(_QWORD *)&WinHvpBlackbox + 1032LL),
          WinHvpTriageDumpBugcheckCallback,
          KbCallbackTriageDumpData,
          (PUCHAR)"WinHv");
      }
    }
    else
    {
      Pool = WinHvpAllocatePool(64, 4096, 1433815127);
      if ( Pool )
      {
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)&WinHvpBlackbox, Pool, 0) )
        {
          WinHvpFreePoolWithTag(Pool, 1433815127);
        }
        else
        {
          *(_BYTE *)(*(_QWORD *)&WinHvpBlackbox + 1076LL) = 0;
          if ( KeInitializeTriageDumpDataArray((PKTRIAGE_DUMP_DATA_ARRAY)(*(_QWORD *)&WinHvpBlackbox + 1080LL), 0xB0u) >= 0 )
          {
            KeRegisterBugCheckReasonCallback(
              (PKBUGCHECK_REASON_CALLBACK_RECORD)(*(_QWORD *)&WinHvpBlackbox + 1032LL),
              WinHvpTriageDumpBugcheckCallback,
              KbCallbackTriageDumpData,
              (PUCHAR)"WinHv");
            KeAddTriageDumpDataBlock(
              (PKTRIAGE_DUMP_DATA_ARRAY)(*(_QWORD *)&WinHvpBlackbox + 1080LL),
              (ULONG)&WinHvpBlackbox,
              (PVOID)8,
              v1);
            KeAddTriageDumpDataBlock(
              (PKTRIAGE_DUMP_DATA_ARRAY)(*(_QWORD *)&WinHvpBlackbox + 1080LL),
              WinHvpBlackbox,
              (PVOID)0x1000,
              v2);
          }
          else
          {
            WinHvpFreePoolWithTag(*(_QWORD *)&WinHvpBlackbox, 1433815127);
            *(_QWORD *)&WinHvpBlackbox = 0;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14001e2a0  sub     rsp, 28h
0x14001e2a4  cmp     cs:WinHvpBlackbox, 0
0x14001e2ac  jnz     loc_14001E413
0x14001e2b2  cmp     cs:byte_1400161B1, 0
0x14001e2b9  jz      short loc_14001E319
0x14001e2bb  mov     rcx, cs:qword_1400161C0
0x14001e2c2  test    rcx, rcx
0x14001e2c5  jz      short loc_14001E319
0x14001e2c7  xor     eax, eax
0x14001e2c9  lock cmpxchg cs:WinHvpBlackbox, rcx
0x14001e2d2  jnz     loc_14001E413
0x14001e2d8  mov     rax, cs:WinHvpBlackbox
0x14001e2df  lea     r9, Component; "WinHv"
0x14001e2e6  mov     r8d, 7; Reason
0x14001e2ec  lea     rdx, WinHvpTriageDumpBugcheckCallback; CallbackRoutine
0x14001e2f3  mov     byte ptr [rax+434h], 0
0x14001e2fa  mov     rcx, cs:WinHvpBlackbox
0x14001e301  add     rcx, 408h; CallbackRecord
0x14001e308  call    cs:__imp_KeRegisterBugCheckReasonCallback
0x14001e30f  nop     dword ptr [rax+rax+00h]
0x14001e314  jmp     loc_14001E413
0x14001e319  mov     edx, 1000h
0x14001e31e  mov     ecx, 40h ; '@'
0x14001e323  mov     r8d, 55764857h
0x14001e329  call    WinHvpAllocatePool
0x14001e32e  mov     rcx, rax
0x14001e331  test    rax, rax
0x14001e334  jz      loc_14001E413
0x14001e33a  xor     eax, eax
0x14001e33c  lock cmpxchg cs:WinHvpBlackbox, rcx
0x14001e345  jz      short loc_14001E356
0x14001e347  mov     edx, 55764857h
0x14001e34c  call    WinHvpFreePoolWithTag
0x14001e351  jmp     loc_14001E413
0x14001e356  mov     rax, cs:WinHvpBlackbox
0x14001e35d  mov     edx, 0B0h; Size
0x14001e362  mov     byte ptr [rax+434h], 0
0x14001e369  mov     rcx, cs:WinHvpBlackbox
0x14001e370  add     rcx, 438h; KtriageDumpDataArray
0x14001e377  call    cs:__imp_KeInitializeTriageDumpDataArray
0x14001e37e  nop     dword ptr [rax+rax+00h]
0x14001e383  mov     rcx, cs:WinHvpBlackbox
0x14001e38a  test    eax, eax
0x14001e38c  jns     short loc_14001E3A5
0x14001e38e  mov     edx, 55764857h
0x14001e393  call    WinHvpFreePoolWithTag
0x14001e398  mov     cs:WinHvpBlackbox, 0
0x14001e3a3  jmp     short loc_14001E413
0x14001e3a5  add     rcx, 408h; CallbackRecord
0x14001e3ac  lea     r9, Component; "WinHv"
0x14001e3b3  mov     r8d, 7; Reason
0x14001e3b9  lea     rdx, WinHvpTriageDumpBugcheckCallback; CallbackRoutine
0x14001e3c0  call    cs:__imp_KeRegisterBugCheckReasonCallback
0x14001e3c7  nop     dword ptr [rax+rax+00h]
0x14001e3cc  mov     rcx, cs:WinHvpBlackbox
0x14001e3d3  lea     rdx, WinHvpBlackbox; MaxDataSize
0x14001e3da  add     rcx, 438h; KtriageDumpDataArray
0x14001e3e1  mov     r8d, 8; Address
0x14001e3e7  call    cs:__imp_KeAddTriageDumpDataBlock
0x14001e3ee  nop     dword ptr [rax+rax+00h]
0x14001e3f3  mov     rdx, cs:WinHvpBlackbox; MaxDataSize
0x14001e3fa  mov     r8d, 1000h; Address
0x14001e400  lea     rcx, [rdx+438h]; KtriageDumpDataArray
0x14001e407  call    cs:__imp_KeAddTriageDumpDataBlock
0x14001e40e  nop     dword ptr [rax+rax+00h]
0x14001e413  add     rsp, 28h
0x14001e417  retn
```
