# CreateTelemetrySessionId

- ea: `0x14001b644`
- end: `0x14001b6ff`
- name: `CreateTelemetrySessionId`
- size: `187`
- prototype: `__int64 __fastcall(UUID *Uuid)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400156a0`

## callees

- `0x14001b644`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14001b692`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001b692`
- `ntoskrnl!ExUuidCreate` at `0x14001b66d`
- `ntoskrnl!ExUuidCreate` at `0x14001b66d`

## pseudocode

```c
void __fastcall CreateTelemetrySessionId(UUID *Uuid)
{
  int i; // edi
  int v3; // eax
  unsigned __int64 v4; // rdx
  union _LARGE_INTEGER Interval; // [rsp+30h] [rbp+8h] BYREF

  if ( Uuid )
  {
    for ( i = 0; i <= 10; ++i )
    {
      Interval.QuadPart = 0;
      if ( ExUuidCreate(Uuid) != -1073741267 )
        return;
      Interval.QuadPart = -10000;
      KeDelayExecutionThread(0, 0, &Interval);
    }
    v3 = MEMORY[0xFFFFF78000000014];
    v4 = MEMORY[0xFFFFF78000000014];
    *(_QWORD *)&Uuid->Data1 = 0;
    v4 >>= 32;
    Uuid->Data4[3] = v4;
    Uuid->Data4[0] = BYTE3(v4);
    Uuid->Data4[1] = BYTE2(v4);
    Uuid->Data4[2] = BYTE1(v4);
    Uuid->Data4[4] = HIBYTE(v3);
    Uuid->Data4[5] = BYTE2(v3);
    Uuid->Data4[6] = BYTE1(v3);
    Uuid->Data4[7] = v3;
  }
}

```

## disassembly

```asm
0x14001b644  test    rcx, rcx
0x14001b647  jz      locret_14001B6FD
0x14001b64d  mov     [rsp+arg_8], rbx
0x14001b652  push    rdi
0x14001b653  sub     rsp, 20h
0x14001b657  mov     rbx, rcx
0x14001b65a  xor     edi, edi
0x14001b65c  cmp     edi, 0Ah
0x14001b65f  jg      short loc_14001B6A2
0x14001b661  mov     rcx, rbx; Uuid
0x14001b664  mov     qword ptr [rsp+28h+Interval], 0
0x14001b66d  call    cs:__imp_ExUuidCreate
0x14001b674  nop     dword ptr [rax+rax+00h]
0x14001b679  cmp     eax, 0C000022Dh
0x14001b67e  jnz     short loc_14001B6F3
0x14001b680  lea     r8, [rsp+28h+Interval]; Interval
0x14001b685  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFFFD8F0h
0x14001b68e  xor     edx, edx; Alertable
0x14001b690  xor     ecx, ecx; WaitMode
0x14001b692  call    cs:__imp_KeDelayExecutionThread
0x14001b699  nop     dword ptr [rax+rax+00h]
0x14001b69e  inc     edi
0x14001b6a0  jmp     short loc_14001B65C
0x14001b6a2  mov     rax, 0FFFFF78000000014h
0x14001b6ac  mov     rax, [rax]
0x14001b6af  mov     rdx, rax
0x14001b6b2  mov     qword ptr [rbx], 0
0x14001b6b9  shr     rdx, 20h
0x14001b6bd  mov     ecx, edx
0x14001b6bf  mov     [rbx+0Bh], dl
0x14001b6c2  sar     ecx, 18h
0x14001b6c5  mov     [rbx+8], cl
0x14001b6c8  mov     ecx, edx
0x14001b6ca  sar     ecx, 10h
0x14001b6cd  mov     [rbx+9], cl
0x14001b6d0  mov     ecx, edx
0x14001b6d2  sar     ecx, 8
0x14001b6d5  mov     [rbx+0Ah], cl
0x14001b6d8  mov     ecx, eax
0x14001b6da  shr     ecx, 18h
0x14001b6dd  mov     [rbx+0Ch], cl
0x14001b6e0  mov     ecx, eax
0x14001b6e2  shr     ecx, 10h
0x14001b6e5  mov     [rbx+0Dh], cl
0x14001b6e8  mov     ecx, eax
0x14001b6ea  shr     ecx, 8
0x14001b6ed  mov     [rbx+0Eh], cl
0x14001b6f0  mov     [rbx+0Fh], al
0x14001b6f3  mov     rbx, [rsp+28h+arg_8]
0x14001b6f8  add     rsp, 20h
0x14001b6fc  pop     rdi
0x14001b6fd  retn
```
