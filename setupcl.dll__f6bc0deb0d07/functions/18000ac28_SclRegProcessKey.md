# SclRegProcessKey

- ea: `0x18000ac28`
- end: `0x18000ace3`
- name: `SclRegProcessKey`
- size: `187`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000b738`
- `0x180010f44`

## callees

- `0x1800014e8`
- `0x18000a524`
- `0x18000ac28`
- `0x18000acec`

## import_xrefs

- `ntdll!NtClose` at `0x18000ac88`
- `ntdll!NtClose` at `0x18000ac88`

## string_xrefs

- `0x18000acb6`: `(%lx): Failed to open key: [%ws]`

## pseudocode

```c
__int64 __fastcall SclRegProcessKey(__int64 a1, const WCHAR *a2, __int64 a3)
{
  int Key; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  HANDLE Handle; // [rsp+88h] [rbp+20h] BYREF

  Handle = 0;
  Key = SclCreateKey(0, a2, 0x10F003Fu, (__int64)&Handle);
  if ( Key < 0 )
  {
    v9 = a1 + 1152;
    if ( !a1 )
      v9 = 0;
    SclLogGenericMessage(
      v9,
      3,
      (int)SclEvent_Generic_Error,
      231,
      (__int64)"SclRegProcessKey",
      "(%lx): Failed to open key: [%ws]",
      Key,
      a2);
  }
  else
  {
    if ( a3 )
    {
      v8 = a3;
      v7 = 0;
    }
    else
    {
      v8 = 0;
      LOBYTE(v7) = 1;
    }
    Key = SclRegProcessKeyByHandle(a1, Handle, v7, v8);
    NtClose(Handle);
  }
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x18000ac28  mov     rax, rsp
0x18000ac2b  push    rbx
0x18000ac2c  push    rbp
0x18000ac2d  push    rsi
0x18000ac2e  push    rdi
0x18000ac2f  sub     rsp, 48h
0x18000ac33  mov     rsi, r8
0x18000ac36  mov     qword ptr [rax+20h], 0
0x18000ac3e  mov     rdi, rcx
0x18000ac41  lea     r9, [rax+20h]
0x18000ac45  xor     ecx, ecx
0x18000ac47  mov     r8d, 10F003Fh
0x18000ac4d  mov     rbp, rdx
0x18000ac50  call    SclCreateKey
0x18000ac55  mov     ebx, eax
0x18000ac57  test    eax, eax
0x18000ac59  js      short loc_18000AC90
0x18000ac5b  mov     rdx, [rsp+68h+Handle]
0x18000ac63  mov     rcx, rdi
0x18000ac66  test    rsi, rsi
0x18000ac69  jnz     short loc_18000AC73
0x18000ac6b  xor     r9d, r9d
0x18000ac6e  mov     r8b, 1
0x18000ac71  jmp     short loc_18000AC79
0x18000ac73  mov     r9, rsi
0x18000ac76  xor     r8d, r8d
0x18000ac79  call    SclRegProcessKeyByHandle
0x18000ac7e  mov     rcx, [rsp+68h+Handle]; Handle
0x18000ac86  mov     ebx, eax
0x18000ac88  call    cs:__imp_NtClose
0x18000ac8e  jmp     short loc_18000ACD8
0x18000ac90  xor     eax, eax
0x18000ac92  mov     [rsp+68h+var_30], rbp
0x18000ac97  test    rdi, rdi
0x18000ac9a  mov     [rsp+68h+var_38], ebx
0x18000ac9e  lea     rcx, [rdi+480h]
0x18000aca5  mov     r9d, 0E7h
0x18000acab  cmovz   rcx, rax
0x18000acaf  lea     r8, SclEvent_Generic_Error
0x18000acb6  lea     rax, aLxFailedToOpen; "(%lx): Failed to open key: [%ws]"
0x18000acbd  mov     edx, 3
0x18000acc2  mov     [rsp+68h+var_40], rax
0x18000acc7  lea     rax, aSclregprocessk; "SclRegProcessKey"
0x18000acce  mov     [rsp+68h+var_48], rax
0x18000acd3  call    SclLogGenericMessage
0x18000acd8  mov     eax, ebx
0x18000acda  add     rsp, 48h
0x18000acde  pop     rdi
0x18000acdf  pop     rsi
0x18000ace0  pop     rbp
0x18000ace1  pop     rbx
0x18000ace2  retn
```
