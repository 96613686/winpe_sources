# IsGetApplicationExecutableRelativePathPresent

- ea: `0x180001d88`
- end: `0x180001dd6`
- name: `IsGetApplicationExecutableRelativePathPresent`
- size: `78`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004fb4`

## callees

- `0x180001d88`
- `0x180001f7d`

## pseudocode

```c
char IsGetApplicationExecutableRelativePathPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_18001D7C4 == 1 )
    return 1;
  if ( dword_18001D7C4 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L":<", &v1) < 0 )
    return 0;
  result = v1;
  dword_18001D7C4 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x180001d88  sub     rsp, 28h
0x180001d8c  mov     ecx, cs:dword_18001D7C4
0x180001d92  sub     ecx, 1
0x180001d95  jz      short loc_180001DCF
0x180001d97  cmp     ecx, 1
0x180001d9a  jz      short loc_180001DCB
0x180001d9c  lea     rdx, [rsp+28h+arg_0]
0x180001da1  mov     [rsp+28h+arg_0], 0
0x180001da6  lea     rcx, asc_180015040; ":<"
0x180001dad  call    ApiSetQueryApiSetPresence_0
0x180001db2  test    eax, eax
0x180001db4  js      short loc_180001DCB
0x180001db6  mov     al, [rsp+28h+arg_0]
0x180001dba  mov     cl, al
0x180001dbc  neg     cl
0x180001dbe  sbb     edx, edx
0x180001dc0  add     edx, 2
0x180001dc3  mov     cs:dword_18001D7C4, edx
0x180001dc9  jmp     short loc_180001DD1
0x180001dcb  xor     al, al
0x180001dcd  jmp     short loc_180001DD1
0x180001dcf  mov     al, 1
0x180001dd1  add     rsp, 28h
0x180001dd5  retn
```
