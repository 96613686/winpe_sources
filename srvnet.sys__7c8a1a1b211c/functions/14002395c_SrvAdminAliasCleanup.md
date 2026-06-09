# SrvAdminAliasCleanup

- ea: `0x14002395c`
- end: `0x1400239df`
- name: `SrvAdminAliasCleanup`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140021d88`

## callees

- `0x140007360`
- `0x14002395c`

## import_xrefs

- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x1400239c3`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x1400239c3`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140023971`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140023971`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14002398b`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14002398b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400239b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400239b0`

## pseudocode

```c
BOOLEAN SrvAdminAliasCleanup()
{
  unsigned int *v0; // rdi
  BOOLEAN result; // al

  while ( 1 )
  {
    result = RtlIsGenericTableEmptyAvl(&AliasTableAvl);
    if ( result )
      break;
    v0 = (unsigned int *)*((_QWORD *)RtlEnumerateGenericTableAvl(&AliasTableAvl, 1u) + 2);
    RtlDeleteElementGenericTableAvl(&AliasTableAvl, v0);
    if ( v0 )
    {
      SrvNetUpdateMemStatistics(*(v0 - 3), *(v0 - 4), 0);
      ExFreePoolWithTag(v0 - 4, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002395c  mov     [rsp+arg_0], rbx
0x140023961  push    rdi
0x140023962  sub     rsp, 20h
0x140023966  jmp     short loc_1400239BC
0x140023968  mov     dl, 1; Restart
0x14002396a  lea     rcx, AliasTableAvl; Table
0x140023971  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140023978  nop     dword ptr [rax+rax+00h]
0x14002397d  lea     rcx, AliasTableAvl; Table
0x140023984  mov     rdi, [rax+10h]
0x140023988  mov     rdx, rdi; Buffer
0x14002398b  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140023992  nop     dword ptr [rax+rax+00h]
0x140023997  test    rdi, rdi
0x14002399a  jz      short loc_1400239BC
0x14002399c  mov     ecx, [rdi-0Ch]
0x14002399f  xor     r8d, r8d
0x1400239a2  mov     edx, [rdi-10h]
0x1400239a5  call    SrvNetUpdateMemStatistics
0x1400239aa  xor     edx, edx; Tag
0x1400239ac  lea     rcx, [rdi-10h]; P
0x1400239b0  call    cs:__imp_ExFreePoolWithTag
0x1400239b7  nop     dword ptr [rax+rax+00h]
0x1400239bc  lea     rcx, AliasTableAvl; Table
0x1400239c3  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x1400239ca  nop     dword ptr [rax+rax+00h]
0x1400239cf  test    al, al
0x1400239d1  jz      short loc_140023968
0x1400239d3  mov     rbx, [rsp+28h+arg_0]
0x1400239d8  add     rsp, 20h
0x1400239dc  pop     rdi
0x1400239dd  retn
```
