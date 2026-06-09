# GetRandomData

- ea: `0x14001c878`
- end: `0x14001c8eb`
- name: `GetRandomData`
- size: `115`
- prototype: `char __fastcall(__int64, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1400013b8`
- `0x14001c8f4`
- `0x140036b48`
- `0x140037574`

## callees

- `0x14001c878`
- `0x14001ce30`
- `0x140037f5c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14001c887`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001c887`

## pseudocode

```c
char __fastcall GetRandomData(__int64 a1, unsigned int a2)
{
  int v4; // eax
  __int64 v5; // rdx
  __int64 v7; // [rsp+40h] [rbp+18h]

  if ( KeGetCurrentIrql()
    || !(unsigned __int8)PgmFipsInitialize()
    || (v4 = ((__int64 (__fastcall *)(__int64, _QWORD))qword_140021D28)(a1, a2)) == 0 )
  {
LABEL_4:
    v7 = (__int64)MEMORY[0xFFFFF78000000014] >> 4;
    v5 = 0;
    while ( 1 )
    {
      LOBYTE(v4) = *((_BYTE *)&v7 + v5);
      *(_BYTE *)(--a2 + a1) = v4;
      if ( !a2 )
        break;
      v5 = (unsigned int)(v5 + 1);
      if ( (unsigned int)v5 >= 4 )
        goto LABEL_4;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14001c878  mov     [rsp+arg_0], rbx
0x14001c87d  push    rdi
0x14001c87e  sub     rsp, 20h
0x14001c882  mov     ebx, edx
0x14001c884  mov     rdi, rcx
0x14001c887  call    cs:__imp_KeGetCurrentIrql
0x14001c88e  nop     dword ptr [rax+rax+00h]
0x14001c893  test    al, al
0x14001c895  jnz     short loc_14001C8B5
0x14001c897  call    PgmFipsInitialize
0x14001c89c  test    al, al
0x14001c89e  jz      short loc_14001C8B5
0x14001c8a0  mov     rax, cs:qword_140021D28
0x14001c8a7  mov     edx, ebx
0x14001c8a9  mov     rcx, rdi
0x14001c8ac  call    _guard_dispatch_icall
0x14001c8b1  test    eax, eax
0x14001c8b3  jnz     short loc_14001C8DF
0x14001c8b5  mov     rax, ds:0FFFFF78000000014h
0x14001c8bf  sar     rax, 4
0x14001c8c3  mov     [rsp+28h+arg_10], rax
0x14001c8c8  xor     edx, edx
0x14001c8ca  mov     al, byte ptr [rsp+rdx+28h+arg_10]
0x14001c8ce  sub     ebx, 1
0x14001c8d1  mov     [rbx+rdi], al
0x14001c8d4  jz      short loc_14001C8DF
0x14001c8d6  inc     edx
0x14001c8d8  cmp     edx, 4
0x14001c8db  jb      short loc_14001C8CA
0x14001c8dd  jmp     short loc_14001C8B5
0x14001c8df  mov     rbx, [rsp+28h+arg_0]
0x14001c8e4  add     rsp, 20h
0x14001c8e8  pop     rdi
0x14001c8e9  retn
```
