# WerpCheckPolicy

- ea: `0x14000d438`
- end: `0x14000d551`
- name: `WerpCheckPolicy`
- size: `281`
- prototype: `__int64 __fastcall(PCWSTR SourceString, int, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000c6f0`

## callees

- `0x14000d438`
- `0x14000f1f8`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000d473`
- `ntoskrnl!DbgPrintEx` at `0x14000d49f`
- `ntoskrnl!DbgPrintEx` at `0x14000d4e8`
- `ntoskrnl!DbgPrintEx` at `0x14000d505`
- `ntoskrnl!DbgPrintEx` at `0x14000d527`
- `ntoskrnl!DbgPrintEx` at `0x14000d473`
- `ntoskrnl!DbgPrintEx` at `0x14000d49f`
- `ntoskrnl!DbgPrintEx` at `0x14000d4e8`
- `ntoskrnl!DbgPrintEx` at `0x14000d505`
- `ntoskrnl!DbgPrintEx` at `0x14000d527`

## pseudocode

```c
__int64 __fastcall WerpCheckPolicy(PCWSTR SourceString, int a2, int *a3)
{
  int v6; // ebx

  if ( a3 && SourceString )
  {
    DbgPrintEx(5u, 3u, "WERKERNELHOST: WerpCheckPolicy: Requested Policy is %i \n", a2);
    if ( a2 <= WerHighestAllowedPolicy )
    {
      v6 = a2;
    }
    else
    {
      DbgPrintEx(
        5u,
        1u,
        "WERKERNELHOST: WerpCheckPolicy: Requested Policy %i is higher than highest allowed %i\n",
        a2,
        WerHighestAllowedPolicy);
      v6 = WerHighestAllowedPolicy;
    }
    if ( v6 == 2 && (unsigned __int8)WerpFullDumpIsThrottled(SourceString) )
      v6 = 0;
    if ( a2 <= v6 )
      DbgPrintEx(5u, 3u, "WERKERNELHOST: WerpCheckPolicy: Granting requested policy %i\n", v6);
    else
      DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpCheckPolicy: Requested Policy %i is higher than granted %i\n", a2, v6);
    *a3 = v6;
    return 0;
  }
  else
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpCheckPolicy: invalid parameter\n");
    if ( a3 )
      *a3 = 0;
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14000d438  push    rbx
0x14000d43a  push    rbp
0x14000d43b  push    rsi
0x14000d43c  push    r14
0x14000d43e  push    r15
0x14000d440  sub     rsp, 30h
0x14000d444  mov     r15, r9
0x14000d447  mov     r14, r8
0x14000d44a  mov     esi, edx
0x14000d44c  mov     rbp, rcx
0x14000d44f  test    r8, r8
0x14000d452  jz      loc_14000D518
0x14000d458  test    rcx, rcx
0x14000d45b  jz      loc_14000D518
0x14000d461  mov     r9d, edx
0x14000d464  lea     r8, aWerkernelhostW_2; "WERKERNELHOST: WerpCheckPolicy: Request"...
0x14000d46b  mov     edx, 3; Level
0x14000d470  lea     ecx, [rdx+2]; ComponentId
0x14000d473  call    cs:__imp_DbgPrintEx
0x14000d47a  nop     dword ptr [rax+rax+00h]
0x14000d47f  mov     eax, cs:WerHighestAllowedPolicy
0x14000d485  cmp     esi, eax
0x14000d487  jle     short loc_14000D4B3
0x14000d489  mov     edx, 1; Level
0x14000d48e  mov     [rsp+58h+var_38], eax
0x14000d492  mov     r9d, esi
0x14000d495  lea     r8, aWerkernelhostW_1; "WERKERNELHOST: WerpCheckPolicy: Request"...
0x14000d49c  lea     ecx, [rdx+4]; ComponentId
0x14000d49f  call    cs:__imp_DbgPrintEx
0x14000d4a6  nop     dword ptr [rax+rax+00h]
0x14000d4ab  mov     ebx, cs:WerHighestAllowedPolicy
0x14000d4b1  jmp     short loc_14000D4B5
0x14000d4b3  mov     ebx, esi
0x14000d4b5  cmp     ebx, 2
0x14000d4b8  jnz     short loc_14000D4CE
0x14000d4ba  mov     rdx, r15
0x14000d4bd  mov     rcx, rbp; SourceString
0x14000d4c0  call    WerpFullDumpIsThrottled
0x14000d4c5  xor     r8d, r8d
0x14000d4c8  test    al, al
0x14000d4ca  cmovnz  ebx, r8d
0x14000d4ce  mov     ecx, 5; ComponentId
0x14000d4d3  cmp     esi, ebx
0x14000d4d5  jle     short loc_14000D4F6
0x14000d4d7  mov     r9d, esi
0x14000d4da  mov     [rsp+58h+var_38], ebx
0x14000d4de  lea     r8, aWerkernelhostW_59; "WERKERNELHOST: WerpCheckPolicy: Request"...
0x14000d4e5  lea     edx, [rcx-4]; Level
0x14000d4e8  call    cs:__imp_DbgPrintEx
0x14000d4ef  nop     dword ptr [rax+rax+00h]
0x14000d4f4  jmp     short loc_14000D511
0x14000d4f6  mov     r9d, ebx
0x14000d4f9  lea     r8, aWerkernelhostW_16; "WERKERNELHOST: WerpCheckPolicy: Grantin"...
0x14000d500  mov     edx, 3; Level
0x14000d505  call    cs:__imp_DbgPrintEx
0x14000d50c  nop     dword ptr [rax+rax+00h]
0x14000d511  mov     [r14], ebx
0x14000d514  xor     eax, eax
0x14000d516  jmp     short loc_14000D544
0x14000d518  mov     edx, 1; Level
0x14000d51d  lea     r8, aWerkernelhostW_13; "WERKERNELHOST: WerpCheckPolicy: invalid"...
0x14000d524  lea     ecx, [rdx+4]; ComponentId
0x14000d527  call    cs:__imp_DbgPrintEx
0x14000d52e  nop     dword ptr [rax+rax+00h]
0x14000d533  test    r14, r14
0x14000d536  jz      short loc_14000D53F
0x14000d538  mov     dword ptr [r14], 0
0x14000d53f  mov     eax, 0C000000Dh
0x14000d544  add     rsp, 30h
0x14000d548  pop     r15
0x14000d54a  pop     r14
0x14000d54c  pop     rsi
0x14000d54d  pop     rbp
0x14000d54e  pop     rbx
0x14000d54f  retn
```
