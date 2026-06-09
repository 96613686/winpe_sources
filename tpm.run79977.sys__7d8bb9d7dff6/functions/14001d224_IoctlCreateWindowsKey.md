# IoctlCreateWindowsKey

- ea: `0x14001d224`
- end: `0x14001d2c9`
- name: `IoctlCreateWindowsKey`
- size: `165`
- prototype: `__int64 __fastcall(TpmStack *this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140017ea0`

## callees

- `0x140008a5c`
- `0x14000e3ac`
- `0x14001d224`
- `0x14002d050`
- `0x14002d8b4`

## pseudocode

```c
__int64 __fastcall IoctlCreateWindowsKey(TpmStack *this, int *a2, int a3)
{
  char *v3; // rdi
  int v5; // edi
  int TpmContext; // ebx
  bool v7; // zf
  int WindowsSrk; // eax
  struct Tpm20Context *v10; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0;
  v10 = 0;
  if ( this && a2 && a3 == 4 )
  {
    v5 = *a2;
    TpmContext = TpmStack::CreateTpmContext(this, (void **)&v10);
    if ( TpmContext < 0 )
    {
      v3 = (char *)v10;
      goto LABEL_12;
    }
    if ( v5 == -2130706431 )
    {
      v3 = (char *)v10;
      WindowsSrk = CreateWindowsSrk(v10, this, 0);
      goto LABEL_9;
    }
    v7 = v5 == -2130640895;
    v3 = (char *)v10;
    if ( v7 )
    {
      WindowsSrk = CreateWindowsEk(v10, this, 0);
LABEL_9:
      TpmContext = WindowsSrk;
      goto LABEL_12;
    }
  }
  TpmContext = -1073741811;
LABEL_12:
  if ( v3 )
    TpmStack::DeleteTpmContext((TpmDevice **)this, v3);
  return (unsigned int)TpmContext;
}

```

## disassembly

```asm
0x14001d224  mov     rax, rsp
0x14001d227  mov     [rax+10h], rbx
0x14001d22b  mov     [rax+18h], rsi
0x14001d22f  push    rdi
0x14001d230  sub     rsp, 20h
0x14001d234  xor     edi, edi
0x14001d236  mov     rsi, rcx
0x14001d239  mov     [rax+8], rdi
0x14001d23d  test    rcx, rcx
0x14001d240  jz      short loc_14001D2A1
0x14001d242  test    rdx, rdx
0x14001d245  jz      short loc_14001D2A1
0x14001d247  cmp     r8d, 4
0x14001d24b  jnz     short loc_14001D2A1
0x14001d24d  mov     edi, [rdx]
0x14001d24f  lea     rdx, [rax+8]; void **
0x14001d253  call    ?CreateTpmContext@TpmStack@@QEAAJPEAPEAX@Z; TpmStack::CreateTpmContext(void * *)
0x14001d258  mov     ebx, eax
0x14001d25a  test    eax, eax
0x14001d25c  js      short loc_14001D29A
0x14001d25e  cmp     edi, 81000001h
0x14001d264  jz      short loc_14001D283
0x14001d266  cmp     edi, 81010001h
0x14001d26c  mov     rdi, [rsp+28h+arg_0]
0x14001d271  jnz     short loc_14001D2A1
0x14001d273  xor     r8d, r8d; struct Event *
0x14001d276  mov     rdx, rsi; struct TpmStack *
0x14001d279  mov     rcx, rdi; struct Tpm20Context *
0x14001d27c  call    ?CreateWindowsEk@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAVEvent@@@Z; CreateWindowsEk(Tpm20Context *,TpmStack *,Event *)
0x14001d281  jmp     short loc_14001D296
0x14001d283  mov     rdi, [rsp+28h+arg_0]
0x14001d288  xor     r8d, r8d; struct Event *
0x14001d28b  mov     rcx, rdi; struct Tpm20Context *
0x14001d28e  mov     rdx, rsi; struct TpmStack *
0x14001d291  call    ?CreateWindowsSrk@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAVEvent@@@Z; CreateWindowsSrk(Tpm20Context *,TpmStack *,Event *)
0x14001d296  mov     ebx, eax
0x14001d298  jmp     short loc_14001D2A6
0x14001d29a  mov     rdi, [rsp+28h+arg_0]
0x14001d29f  jmp     short loc_14001D2A6
0x14001d2a1  mov     ebx, 0C000000Dh
0x14001d2a6  test    rdi, rdi
0x14001d2a9  jz      short loc_14001D2B6
0x14001d2ab  mov     rdx, rdi; void *
0x14001d2ae  mov     rcx, rsi; this
0x14001d2b1  call    ?DeleteTpmContext@TpmStack@@QEAAXPEAX@Z; TpmStack::DeleteTpmContext(void *)
0x14001d2b6  mov     rsi, [rsp+28h+arg_10]
0x14001d2bb  mov     eax, ebx
0x14001d2bd  mov     rbx, [rsp+28h+arg_8]
0x14001d2c2  add     rsp, 20h
0x14001d2c6  pop     rdi
0x14001d2c7  retn
```
