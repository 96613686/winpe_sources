# sub_14006EBDC

- ea: `0x14006ebdc`
- end: `0x14006ec8e`
- name: `sub_14006EBDC`
- size: `178`
- prototype: `__int64 __fastcall(PVOID Parameter, WAITORTIMERCALLBACK Callback, DWORD DueTime, DWORD Period, void **, ULONG Flags)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140090b80`
- `0x1400cd9dc`
- `0x1401c751c`

## callees

- `0x14006b6ac`
- `0x14006d1ec`
- `0x14006de60`
- `0x14006ebdc`
- `0x14007cfb4`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x14006ec4e`
- `KERNEL32!CreateTimerQueueTimer` at `0x14006ec4e`
- `KERNEL32!GetLastError` at `0x14006ec58`
- `KERNEL32!GetLastError` at `0x14006ec58`

## pseudocode

```c
__int64 __fastcall sub_14006EBDC(
        PVOID Parameter,
        WAITORTIMERCALLBACK Callback,
        DWORD DueTime,
        DWORD Period,
        void **a5,
        ULONG Flags)
{
  unsigned int v10; // ebx
  int v11; // ecx
  int v12; // eax
  DWORD LastError; // eax
  void *phNewTimer; // [rsp+40h] [rbp-38h] BYREF

  phNewTimer = 0;
  if ( dword_140447200 == 1 )
  {
    v12 = sub_14006B6AC(&unk_140447208);
    v10 = v12;
    if ( v12 >= 0 )
    {
      if ( CreateTimerQueueTimer(&phNewTimer, TimerQueue, Callback, Parameter, DueTime, Period, Flags) )
      {
        *a5 = phNewTimer;
        goto LABEL_9;
      }
      LastError = GetLastError();
      v12 = sub_14006D1EC(LastError);
      v10 = v12;
    }
    v11 = v12;
  }
  else
  {
    v10 = -2147418113;
    v11 = -2147418113;
  }
  sub_14006DE60(v11);
LABEL_9:
  sub_14007CFB4(v10);
  return v10;
}

```

## disassembly

```asm
0x14006ebdc  push    rbx
0x14006ebde  push    rbp
0x14006ebdf  push    rsi
0x14006ebe0  push    rdi
0x14006ebe1  push    r14
0x14006ebe3  sub     rsp, 50h
0x14006ebe7  cmp     cs:dword_140447200, 1
0x14006ebee  mov     edi, r9d
0x14006ebf1  mov     esi, r8d
0x14006ebf4  mov     [rsp+78h+phNewTimer], 0
0x14006ebfd  mov     rbp, rdx
0x14006ec00  mov     r14, rcx
0x14006ec03  jz      short loc_14006EC13
0x14006ec05  mov     ebx, 8000FFFFh
0x14006ec0a  mov     ecx, ebx
0x14006ec0c  call    sub_14006DE60
0x14006ec11  jmp     short loc_14006EC79
0x14006ec13  lea     rcx, unk_140447208
0x14006ec1a  call    sub_14006B6AC
0x14006ec1f  mov     ebx, eax
0x14006ec21  test    eax, eax
0x14006ec23  jns     short loc_14006EC29
0x14006ec25  mov     ecx, eax
0x14006ec27  jmp     short loc_14006EC0C
0x14006ec29  mov     eax, [rsp+78h+arg_28]
0x14006ec30  lea     rcx, [rsp+78h+phNewTimer]; phNewTimer
0x14006ec35  mov     rdx, cs:TimerQueue; TimerQueue
0x14006ec3c  mov     r9, r14; Parameter
0x14006ec3f  mov     [rsp+78h+Flags], eax; Flags
0x14006ec43  mov     r8, rbp; Callback
0x14006ec46  mov     [rsp+78h+Period], edi; Period
0x14006ec4a  mov     [rsp+78h+DueTime], esi; DueTime
0x14006ec4e  call    cs:CreateTimerQueueTimer
0x14006ec54  test    eax, eax
0x14006ec56  jnz     short loc_14006EC69
0x14006ec58  call    cs:GetLastError
0x14006ec5e  mov     ecx, eax
0x14006ec60  call    sub_14006D1EC
0x14006ec65  mov     ebx, eax
0x14006ec67  jmp     short loc_14006EC25
0x14006ec69  mov     rcx, [rsp+78h+arg_20]
0x14006ec71  mov     rax, [rsp+78h+phNewTimer]
0x14006ec76  mov     [rcx], rax
0x14006ec79  mov     ecx, ebx
0x14006ec7b  call    sub_14007CFB4
0x14006ec80  mov     eax, ebx
0x14006ec82  add     rsp, 50h
0x14006ec86  pop     r14
0x14006ec88  pop     rdi
0x14006ec89  pop     rsi
0x14006ec8a  pop     rbp
0x14006ec8b  pop     rbx
0x14006ec8c  retn
```
