# SmpSessionIdIsInitialSessions

- ea: `0x1400010b0`
- end: `0x1400010e5`
- name: `SmpSessionIdIsInitialSessions`
- size: `53`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140001630`
- `0x1400031b0`
- `0x140005ac4`

## callees

- `0x1400010b0`

## pseudocode

```c
bool __fastcall SmpSessionIdIsInitialSessions(int a1)
{
  __int64 i; // rdx

  if ( a1 != -1 )
  {
    for ( i = 0; (unsigned int)i < SmpNumberInitialSessions; i = (unsigned int)(i + 1) )
    {
      if ( a1 == *(_DWORD *)(SmpCoreProcessIds + 40 * i) )
        return (_DWORD)i != -1;
    }
  }
  LODWORD(i) = -1;
  return (_DWORD)i != -1;
}

```

## disassembly

```asm
0x1400010b0  or      r10d, 0FFFFFFFFh
0x1400010b4  mov     r8d, ecx
0x1400010b7  cmp     ecx, r10d
0x1400010ba  jz      short loc_1400010DB
0x1400010bc  mov     r9, cs:SmpCoreProcessIds
0x1400010c3  xor     edx, edx
0x1400010c5  cmp     edx, cs:SmpNumberInitialSessions
0x1400010cb  jnb     short loc_1400010DB
0x1400010cd  lea     rcx, [rdx+rdx*4]
0x1400010d1  cmp     r8d, [r9+rcx*8]
0x1400010d5  jz      short loc_1400010DE
0x1400010d7  inc     edx
0x1400010d9  jmp     short loc_1400010C5
0x1400010db  mov     edx, r10d
0x1400010de  cmp     edx, r10d
0x1400010e1  setnz   al
0x1400010e4  retn
```
