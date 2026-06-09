# WinHvpWithdrawMemory

- ea: `0x1400231a4`
- end: `0x140023345`
- name: `WinHvpWithdrawMemory`
- size: `417`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140021c40`
- `0x140022af0`
- `0x140022b50`
- `0x140022b80`

## callees

- `0x140003b70`
- `0x140004408`
- `0x140009c90`
- `0x14000a040`
- `0x1400231a4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002324a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002324a`

## pseudocode

```c
NTSTATUS __fastcall WinHvpWithdrawMemory(
        __int64 a1,
        unsigned __int64 a2,
        unsigned int a3,
        char a4,
        _QWORD *a5,
        __int64 a6)
{
  _QWORD *v10; // rsi
  __int64 v11; // rbx
  bool v12; // cf
  char *v13; // rbp
  NTSTATUS result; // eax
  int v15; // edi
  unsigned __int64 v16; // rdx
  __int64 v17; // [rsp+80h] [rbp-78h] BYREF
  __int64 v18; // [rsp+88h] [rbp-70h] BYREF
  _QWORD v19[8]; // [rsp+90h] [rbp-68h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+100h] [rbp+8h] BYREF

  memset(v19, 0, sizeof(v19));
  v10 = a5;
  v17 = a1;
  v11 = a6;
  v18 = 0;
  v12 = a6 != 0;
  Timeout.QuadPart = 0;
  *a5 = 0;
  LOBYTE(v19[3]) = a4;
  v13 = (char *)((v11 + 48) & -(__int64)v12);
  if ( !a4 && !byte_14001606B )
  {
    result = KeWaitForSingleObject(WinHvpWithdrawAllowedEvent, Executive, 0, 0, &Timeout);
    if ( result < 0 )
      return result;
    byte_14001606B = 1;
  }
  WinHvpSetProximityDomain(&v18, a3);
  v15 = WinHvpSpecialListRepHypercall(
          73,
          a2,
          &v17,
          0x10u,
          0,
          0,
          0,
          0,
          0,
          0,
          v13,
          8u,
          (void (__fastcall *)(const void *, char *, _QWORD))WinHvpWithdrawMemoryConsumer,
          v19,
          v10);
  if ( v11 )
  {
    v16 = *v10 << 12;
    *(_QWORD *)v11 = 0;
    *(_WORD *)(v11 + 10) = 0;
    *(_WORD *)(v11 + 8) = 8 * ((v16 >> 12) + 6);
    *(_QWORD *)(v11 + 32) = 0;
    *(_QWORD *)(v11 + 40) = (unsigned int)v16;
  }
  if ( v19[0] )
    ((void (*)(void))v19[7])();
  return v15;
}

```

## disassembly

```asm
0x1400231a4  mov     rax, rsp
0x1400231a7  mov     [rax+10h], rbx
0x1400231ab  mov     [rax+18h], rbp
0x1400231af  push    rsi
0x1400231b0  push    rdi
0x1400231b1  push    r12
0x1400231b3  push    r14
0x1400231b5  push    r15
0x1400231b7  sub     rsp, 0D0h
0x1400231be  mov     r15, rdx
0x1400231c1  mov     r14d, r8d
0x1400231c4  xor     edx, edx; Val
0x1400231c6  mov     rbx, rcx
0x1400231c9  lea     rcx, [rax-68h]; void *
0x1400231cd  mov     dil, r9b
0x1400231d0  lea     r8d, [rdx+40h]; Size
0x1400231d4  call    memset
0x1400231d9  mov     rsi, [rsp+0F8h+arg_20]
0x1400231e1  xor     r12d, r12d
0x1400231e4  mov     [rsp+0F8h+var_78], rbx
0x1400231ec  mov     rbx, [rsp+0F8h+arg_28]
0x1400231f4  mov     rax, rbx
0x1400231f7  mov     [rsp+0F8h+var_70], r12
0x1400231ff  neg     rax
0x140023202  mov     qword ptr [rsp+0F8h+arg_0], r12
0x14002320a  mov     [rsi], r12
0x14002320d  sbb     rbp, rbp
0x140023210  mov     [rsp+0F8h+var_50], dil
0x140023218  lea     rcx, [rbx+30h]
0x14002321c  and     rbp, rcx
0x14002321f  test    dil, dil
0x140023222  jnz     short loc_140023265
0x140023224  mov     al, cs:byte_14001606B
0x14002322a  test    al, al
0x14002322c  jnz     short loc_140023265
0x14002322e  mov     rcx, cs:WinHvpWithdrawAllowedEvent; Object
0x140023235  lea     rax, [rsp+0F8h+arg_0]
0x14002323d  xor     r9d, r9d; Alertable
0x140023240  mov     [rsp+0F8h+Timeout], rax; Timeout
0x140023245  xor     r8d, r8d; WaitMode
0x140023248  xor     edx, edx; WaitReason
0x14002324a  call    cs:__imp_KeWaitForSingleObject
0x140023251  nop     dword ptr [rax+rax+00h]
0x140023256  test    eax, eax
0x140023258  js      loc_140023328
0x14002325e  mov     cs:byte_14001606B, 1
0x140023265  mov     edx, r14d
0x140023268  lea     rcx, [rsp+0F8h+var_70]
0x140023270  call    WinHvpSetProximityDomain
0x140023275  mov     [rsp+0F8h+var_88], rsi
0x14002327a  lea     rax, [rsp+0F8h+var_68]
0x140023282  mov     [rsp+0F8h+var_90], rax
0x140023287  lea     r8, [rsp+0F8h+var_78]
0x14002328f  lea     rax, WinHvpWithdrawMemoryConsumer
0x140023296  mov     r9d, 10h
0x14002329c  mov     [rsp+0F8h+var_98], rax
0x1400232a1  mov     rdx, r15
0x1400232a4  mov     [rsp+0F8h+var_A0], 8
0x1400232ac  mov     [rsp+0F8h+var_A8], rbp
0x1400232b1  mov     [rsp+0F8h+var_B0], r12
0x1400232b6  lea     ecx, [r9+39h]
0x1400232ba  mov     [rsp+0F8h+var_B8], r12
0x1400232bf  mov     [rsp+0F8h+var_C0], r12d
0x1400232c4  mov     [rsp+0F8h+var_C8], r12
0x1400232c9  mov     [rsp+0F8h+var_D0], r12
0x1400232ce  mov     [rsp+0F8h+Timeout], r12
0x1400232d3  call    WinHvpSpecialListRepHypercall
0x1400232d8  mov     edi, eax
0x1400232da  test    rbx, rbx
0x1400232dd  jz      short loc_14002330C
0x1400232df  mov     rdx, [rsi]
0x1400232e2  shl     rdx, 0Ch
0x1400232e6  mov     rcx, rdx
0x1400232e9  mov     [rbx], r12
0x1400232ec  shr     rcx, 0Ch
0x1400232f0  add     cx, 6
0x1400232f4  mov     [rbx+0Ah], r12w
0x1400232f9  shl     cx, 3
0x1400232fd  mov     [rbx+8], cx
0x140023301  mov     [rbx+20h], r12
0x140023305  mov     [rbx+2Ch], r12d
0x140023309  mov     [rbx+28h], edx
0x14002330c  mov     rcx, [rsp+0F8h+var_68]
0x140023314  test    rcx, rcx
0x140023317  jz      short loc_140023326
0x140023319  mov     rax, [rsp+0F8h+var_30]
0x140023321  call    _guard_dispatch_icall
0x140023326  mov     eax, edi
0x140023328  lea     r11, [rsp+0F8h+var_28]
0x140023330  mov     rbx, [r11+38h]
0x140023334  mov     rbp, [r11+40h]
0x140023338  mov     rsp, r11
0x14002333b  pop     r15
0x14002333d  pop     r14
0x14002333f  pop     r12
0x140023341  pop     rdi
0x140023342  pop     rsi
0x140023343  retn
```
