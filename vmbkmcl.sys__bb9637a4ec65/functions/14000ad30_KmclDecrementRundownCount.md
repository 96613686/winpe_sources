# KmclDecrementRundownCount

- ea: `0x14000ad30`
- end: `0x14000aeae`
- name: `KmclDecrementRundownCount`
- size: `382`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400049a0`
- `0x14000bb70`
- `0x14000c87c`
- `0x14000cdb0`
- `0x14000cfe4`
- `0x14000e9e0`

## callees

- `0x14000ad30`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000ae76`
- `ntoskrnl!KeSetEvent` at `0x14000ae76`
- `ntoskrnl!IoQueueWorkItem` at `0x14000ae9b`
- `ntoskrnl!IoQueueWorkItem` at `0x14000ae9b`

## pseudocode

```c
void __fastcall KmclDecrementRundownCount(PVOID Context, char a2, __int16 a3)
{
  signed __int32 v5; // r10d
  signed __int32 v6; // r9d
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rcx

  v5 = _InterlockedExchangeAdd((volatile signed __int32 *)Context + 554, 0xFFFFFFFF);
  v6 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
  v7 = 2LL * v6;
  *((_QWORD *)Context + v7 + 413) = MEMORY[0xFFFFF78000000008];
  *((_BYTE *)Context + 16 * v6 + 3312) = *((_BYTE *)Context + 2200);
  *((_BYTE *)Context + 8 * v7 + 3313) = *((_BYTE *)Context + 2204);
  *((_WORD *)Context + 4 * v7 + 1657) = *((_DWORD *)Context + 554);
  *((_WORD *)Context + 4 * v7 + 1658) = a3;
  if ( v5 == 1 && a2 )
  {
    v8 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
    v9 = v8 + 207;
    v8 *= 2;
    *((_QWORD *)Context + v8 + 413) = MEMORY[0xFFFFF78000000008];
    *((_BYTE *)Context + 16 * v9) = *((_BYTE *)Context + 2200);
    *((_BYTE *)Context + 8 * v8 + 3313) = *((_BYTE *)Context + 2204);
    *((_WORD *)Context + 4 * v8 + 1657) = *((_DWORD *)Context + 554);
    *((_WORD *)Context + 4 * v8 + 1658) = 4309;
    if ( *((_BYTE *)Context + 2280) )
      KeSetEvent((PRKEVENT)Context + 93, 0, 0);
    else
      IoQueueWorkItem(*((PIO_WORKITEM *)Context + 278), KmclpRundownCountZero, DelayedWorkQueue, Context);
  }
}

```

## disassembly

```asm
0x14000ad30  push    rbx
0x14000ad32  sub     rsp, 20h
0x14000ad36  mov     bl, dl
0x14000ad38  mov     r11, rcx
0x14000ad3b  or      r10d, 0FFFFFFFFh
0x14000ad3f  lock xadd [rcx+8A8h], r10d
0x14000ad48  mov     r9d, 1
0x14000ad4e  lock xadd [rcx+0CE0h], r9d
0x14000ad57  inc     r9d
0x14000ad5a  mov     eax, 2AAAAAABh
0x14000ad5f  imul    r9d
0x14000ad62  sar     edx, 2
0x14000ad65  mov     eax, edx
0x14000ad67  shr     eax, 1Fh
0x14000ad6a  add     edx, eax
0x14000ad6c  lea     eax, [rdx+rdx*2]
0x14000ad6f  shl     eax, 3
0x14000ad72  sub     r9d, eax
0x14000ad75  mov     rax, ds:0FFFFF78000000008h
0x14000ad7f  movsxd  rcx, r9d
0x14000ad82  mov     rdx, rcx
0x14000ad85  add     rcx, 0CFh
0x14000ad8c  add     rdx, rdx
0x14000ad8f  add     rcx, rcx
0x14000ad92  mov     [r11+rdx*8+0CE8h], rax
0x14000ad9a  mov     al, [r11+898h]
0x14000ada1  mov     [r11+rcx*8], al
0x14000ada5  mov     al, [r11+89Ch]
0x14000adac  mov     [r11+rdx*8+0CF1h], al
0x14000adb4  mov     eax, [r11+8A8h]
0x14000adbb  mov     [r11+rdx*8+0CF2h], ax
0x14000adc4  mov     [r11+rdx*8+0CF4h], r8w
0x14000adcd  cmp     r10d, 1
0x14000add1  jnz     loc_14000AEA7
0x14000add7  test    bl, bl
0x14000add9  jz      loc_14000AEA7
0x14000addf  mov     ecx, r10d
0x14000ade2  lock xadd [r11+0CE0h], ecx
0x14000adeb  inc     ecx
0x14000aded  mov     eax, 2AAAAAABh
0x14000adf2  imul    ecx
0x14000adf4  sar     edx, 2
0x14000adf7  mov     eax, edx
0x14000adf9  shr     eax, 1Fh
0x14000adfc  add     edx, eax
0x14000adfe  lea     eax, [rdx+rdx*2]
0x14000ae01  shl     eax, 3
0x14000ae04  sub     ecx, eax
0x14000ae06  mov     rax, ds:0FFFFF78000000008h
0x14000ae10  movsxd  rcx, ecx
0x14000ae13  mov     rdx, rcx
0x14000ae16  add     rcx, 0CFh
0x14000ae1d  add     rdx, rdx
0x14000ae20  add     rcx, rcx
0x14000ae23  mov     [r11+rdx*8+0CE8h], rax
0x14000ae2b  mov     al, [r11+898h]
0x14000ae32  mov     [r11+rcx*8], al
0x14000ae36  mov     al, [r11+89Ch]
0x14000ae3d  mov     [r11+rdx*8+0CF1h], al
0x14000ae45  mov     eax, [r11+8A8h]
0x14000ae4c  mov     [r11+rdx*8+0CF2h], ax
0x14000ae55  mov     word ptr [r11+rdx*8+0CF4h], 10D5h
0x14000ae60  cmp     byte ptr [r11+8E8h], 0
0x14000ae68  jz      short loc_14000AE84
0x14000ae6a  lea     rcx, [r11+8B8h]; Event
0x14000ae71  xor     r8d, r8d; Wait
0x14000ae74  xor     edx, edx; Increment
0x14000ae76  call    cs:__imp_KeSetEvent
0x14000ae7d  nop     dword ptr [rax+rax+00h]
0x14000ae82  jmp     short loc_14000AEA7
0x14000ae84  mov     rcx, [r11+8B0h]; IoWorkItem
0x14000ae8b  lea     rdx, KmclpRundownCountZero; WorkerRoutine
0x14000ae92  mov     r9, r11; Context
0x14000ae95  mov     r8d, 1; QueueType
0x14000ae9b  call    cs:__imp_IoQueueWorkItem
0x14000aea2  nop     dword ptr [rax+rax+00h]
0x14000aea7  add     rsp, 20h
0x14000aeab  pop     rbx
0x14000aeac  retn
```
