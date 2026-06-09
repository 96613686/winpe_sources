# TpmTransportSpbI2CNTCDevice::CancelCurrentCommand(void)

- ea: `0x140025630`
- end: `0x1400256e0`
- name: `?CancelCurrentCommand@TpmTransportSpbI2CNTCDevice@@UEAAXXZ`
- size: `176`
- prototype: `void __fastcall(TpmTransportSpbI2CNTCDevice *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140025630`
- `0x140025d5c`
- `0x140026924`
- `0x140026a68`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x140025656`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140025656`

## pseudocode

```c
void __fastcall TpmTransportSpbI2CNTCDevice::CancelCurrentCommand(TpmTransportSpbI2CNTCDevice *this)
{
  __int64 v2; // rbx
  __int64 v3; // rbx
  unsigned __int8 v4; // [rsp+48h] [rbp+10h] BYREF
  __int16 v5; // [rsp+50h] [rbp+18h] BYREF

  v4 = 0;
  v5 = 0x4000;
  v2 = MEMORY[0xFFFFF78000000320];
  v3 = 0x1312D00uLL / KeQueryTimeIncrement() + v2;
  while ( (int)TpmTransportSpbDevice::SPBWrite(this, &v5, 2) >= 0
       && (int)TpmTransportSpbDevice::SPBSequence(this, 0, &v4, 1u, 0) >= 0
       && (v4 & 0x40) == 0
       && TpmTransportSpbDevice::Idle(this, 100, 0) >= 0
       && MEMORY[0xFFFFF78000000320] < v3 )
    ;
}

```

## disassembly

```asm
0x140025630  mov     [rsp+arg_0], rbx
0x140025635  push    rdi
0x140025636  sub     rsp, 30h
0x14002563a  mov     [rsp+38h+arg_8], 0
0x14002563f  mov     rbx, 0FFFFF78000000320h
0x140025649  mov     [rsp+38h+arg_10], 4000h
0x140025650  mov     rdi, rcx
0x140025653  mov     rbx, [rbx]
0x140025656  call    cs:__imp_KeQueryTimeIncrement
0x14002565d  nop     dword ptr [rax+rax+00h]
0x140025662  mov     r8d, eax
0x140025665  xor     edx, edx
0x140025667  mov     eax, 1312D00h
0x14002566c  div     r8
0x14002566f  add     rbx, rax
0x140025672  mov     r8d, 2; unsigned int
0x140025678  lea     rdx, [rsp+38h+arg_10]; void *
0x14002567d  mov     rcx, rdi; this
0x140025680  call    ?SPBWrite@TpmTransportSpbDevice@@IEAAJPEAXI@Z; TpmTransportSpbDevice::SPBWrite(void *,uint)
0x140025685  test    eax, eax
0x140025687  js      short loc_1400256D4
0x140025689  mov     r9d, 1; unsigned int
0x14002568f  mov     [rsp+38h+var_18], 0; unsigned int *
0x140025698  lea     r8, [rsp+38h+arg_8]; unsigned __int8 *
0x14002569d  xor     edx, edx; unsigned __int8
0x14002569f  mov     rcx, rdi; this
0x1400256a2  call    ?SPBSequence@TpmTransportSpbDevice@@IEAAJEPEAEIPEAI@Z; TpmTransportSpbDevice::SPBSequence(uchar,uchar *,uint,uint *)
0x1400256a7  test    eax, eax
0x1400256a9  js      short loc_1400256D4
0x1400256ab  test    [rsp+38h+arg_8], 40h
0x1400256b0  jnz     short loc_1400256D4
0x1400256b2  xor     r8d, r8d; bool
0x1400256b5  mov     rcx, rdi; this
0x1400256b8  lea     edx, [r8+64h]; __int64
0x1400256bc  call    ?Idle@TpmTransportSpbDevice@@IEAAJ_J_N@Z; TpmTransportSpbDevice::Idle(__int64,bool)
0x1400256c1  test    eax, eax
0x1400256c3  js      short loc_1400256D4
0x1400256c5  mov     rax, ds:0FFFFF78000000320h
0x1400256cf  cmp     rax, rbx
0x1400256d2  jl      short loc_140025672
0x1400256d4  mov     rbx, [rsp+38h+arg_0]
0x1400256d9  add     rsp, 30h
0x1400256dd  pop     rdi
0x1400256de  retn
```
