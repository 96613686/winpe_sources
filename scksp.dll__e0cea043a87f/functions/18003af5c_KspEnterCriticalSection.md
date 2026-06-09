# KspEnterCriticalSection

- ea: `0x18003af5c`
- end: `0x18003afb7`
- name: `KspEnterCriticalSection`
- size: `91`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `32`
- callee_count: `3`
- tags: ``

## callers

- `0x180012b24`
- `0x180012d08`
- `0x1800134fc`
- `0x1800135dc`
- `0x1800146c4`
- `0x180015728`
- `0x180015a5c`
- `0x180017b24`
- `0x18001c818`
- `0x18001d4e0`
- `0x18001dbc8`
- `0x18001e590`
- `0x18001e92c`
- `0x18001ee70`
- `0x18001f2f0`
- `0x18001f61c`
- `0x1800203a0`
- `0x1800206e8`
- `0x180020ed4`
- `0x180021220`
- `0x1800229fc`
- `0x1800232ec`
- `0x180023dd0`
- `0x180024250`
- `0x180024e98`
- `0x1800253c0`
- `0x180025ff0`
- `0x180027054`
- `0x1800283dc`
- `0x180028a30`
- `0x180029abc`
- `0x18002a4c0`

## callees

- `0x18000a590`
- `0x18003af5c`
- `0x18003b018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003af65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003af65`

## pseudocode

```c
__int64 __fastcall KspEnterCriticalSection(struct _RTL_CRITICAL_SECTION *a1)
{
  char v1; // bl
  __int64 v2; // rcx
  int v3; // r8d
  int v4; // r9d

  v1 = (char)a1;
  EnterCriticalSection(a1);
  WppTraceIndent(v2, 2u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v3, v4, v1);
  }
  return 0;
}

```

## disassembly

```asm
0x18003af5c  push    rbx
0x18003af5e  sub     rsp, 30h
0x18003af62  mov     rbx, rcx
0x18003af65  call    cs:__imp_EnterCriticalSection
0x18003af6b  mov     edx, 2
0x18003af70  call    WppTraceIndent
0x18003af75  lea     rax, WPP_GLOBAL_Control
0x18003af7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003af83  cmp     rcx, rax
0x18003af86  jz      short loc_18003AFA8
0x18003af88  test    byte ptr [rcx+1Ch], 1
0x18003af8c  jz      short loc_18003AFA8
0x18003af8e  cmp     byte ptr [rcx+19h], 5
0x18003af92  jb      short loc_18003AFA8
0x18003af94  mov     edx, 0Ch
0x18003af99  mov     [rsp+38h+var_18], rbx
0x18003af9e  mov     rcx, [rcx+10h]
0x18003afa2  call    WPP_SF_sq
0x18003afa7  nop
0x18003afa8  xor     eax, eax
0x18003afaa  jmp     short loc_18003AFB1
0x18003afac  mov     eax, 8
0x18003afb1  add     rsp, 30h
0x18003afb5  pop     rbx
0x18003afb6  retn
```
