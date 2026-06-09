# KmclpRundownCountZeroThread

- ea: `0x14000ddc0`
- end: `0x14000dec1`
- name: `KmclpRundownCountZeroThread`
- size: `257`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000d9b0`
- `0x14000ddc0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000dea9`
- `ntoskrnl!KeSetEvent` at `0x14000dea9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ddf2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ddf2`

## pseudocode

```c
void __fastcall KmclpRundownCountZeroThread(char *StartContext)
{
  __int64 v2; // rdx
  __int64 v3; // rcx

  while ( !StartContext[2281] )
  {
    KeWaitForSingleObject(StartContext + 2232, Executive, 0, 0, 0);
    if ( StartContext[2281] )
      break;
    v2 = _InterlockedIncrement((volatile signed __int32 *)StartContext + 824) % 24;
    v3 = v2 + 207;
    v2 *= 2;
    *(_QWORD *)&StartContext[8 * v2 + 3304] = MEMORY[0xFFFFF78000000008];
    StartContext[16 * v3] = StartContext[2200];
    StartContext[8 * v2 + 3313] = StartContext[2204];
    *(_WORD *)&StartContext[8 * v2 + 3314] = *((_DWORD *)StartContext + 554);
    *(_WORD *)&StartContext[8 * v2 + 3316] = 4180;
    KmclpRundownCountZero(0, StartContext);
  }
  KeSetEvent((PRKEVENT)StartContext + 94, 0, 0);
}

```

## disassembly

```asm
0x14000ddc0  mov     [rsp+arg_0], rbx
0x14000ddc5  push    rdi
0x14000ddc6  sub     rsp, 30h
0x14000ddca  cmp     byte ptr [rcx+8E9h], 0
0x14000ddd1  mov     rbx, rcx
0x14000ddd4  jnz     loc_14000DE9D
0x14000ddda  xor     r9d, r9d; Alertable
0x14000dddd  mov     [rsp+38h+Timeout], 0; Timeout
0x14000dde6  xor     r8d, r8d; WaitMode
0x14000dde9  lea     rcx, [rbx+8B8h]; Object
0x14000ddf0  xor     edx, edx; WaitReason
0x14000ddf2  call    cs:__imp_KeWaitForSingleObject
0x14000ddf9  nop     dword ptr [rax+rax+00h]
0x14000ddfe  cmp     byte ptr [rbx+8E9h], 0
0x14000de05  jnz     loc_14000DE9D
0x14000de0b  mov     ecx, 1
0x14000de10  lock xadd [rbx+0CE0h], ecx
0x14000de18  inc     ecx
0x14000de1a  mov     eax, 2AAAAAABh
0x14000de1f  imul    ecx
0x14000de21  sar     edx, 2
0x14000de24  mov     eax, edx
0x14000de26  shr     eax, 1Fh
0x14000de29  add     edx, eax
0x14000de2b  lea     eax, [rdx+rdx*2]
0x14000de2e  shl     eax, 3
0x14000de31  sub     ecx, eax
0x14000de33  mov     rax, ds:0FFFFF78000000008h
0x14000de3d  movsxd  rcx, ecx
0x14000de40  mov     rdx, rcx
0x14000de43  add     rcx, 0CFh
0x14000de4a  add     rdx, rdx
0x14000de4d  add     rcx, rcx
0x14000de50  mov     [rbx+rdx*8+0CE8h], rax
0x14000de58  mov     al, [rbx+898h]
0x14000de5e  mov     [rbx+rcx*8], al
0x14000de61  xor     ecx, ecx; DeviceObject
0x14000de63  mov     al, [rbx+89Ch]
0x14000de69  mov     [rbx+rdx*8+0CF1h], al
0x14000de70  mov     eax, [rbx+8A8h]
0x14000de76  mov     [rbx+rdx*8+0CF2h], ax
0x14000de7e  mov     word ptr [rbx+rdx*8+0CF4h], 1054h
0x14000de88  mov     rdx, rbx; Context
0x14000de8b  call    KmclpRundownCountZero
0x14000de90  cmp     byte ptr [rbx+8E9h], 0
0x14000de97  jz      loc_14000DDDA
0x14000de9d  lea     rcx, [rbx+8D0h]; Event
0x14000dea4  xor     r8d, r8d; Wait
0x14000dea7  xor     edx, edx; Increment
0x14000dea9  call    cs:__imp_KeSetEvent
0x14000deb0  nop     dword ptr [rax+rax+00h]
0x14000deb5  mov     rbx, [rsp+38h+arg_0]
0x14000deba  add     rsp, 30h
0x14000debe  pop     rdi
0x14000debf  retn
```
