# Function

- ea: `0x14000ef80`
- end: `0x14000f04f`
- name: `Function`
- size: `207`
- prototype: `EX_CALLBACK_FUNCTION`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000b3f0`
- `0x14000b638`
- `0x14000b808`
- `0x14000b988`
- `0x14000c878`
- `0x14000ef80`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000efbf`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000efbf`
- `ntoskrnl!PsInitialSystemProcess` at `0x14000ef99`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000efae`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000efae`

## pseudocode

```c
__int64 __fastcall Function(PVOID CallbackContext, PVOID Argument1, PVOID Argument2)
{
  int v4; // edi
  unsigned int v6; // esi
  int v7; // edi
  int v8; // edi
  int v9; // edi

  v4 = (int)Argument1;
  v6 = 0;
  if ( IoGetCurrentProcess() != PsInitialSystemProcess && KeGetCurrentIrql() <= 1u && Argument2 )
  {
    if ( v4 )
    {
      v7 = v4 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          v9 = v8 - 2;
          if ( v9 )
          {
            if ( v9 != 34 )
              return v6;
            return (unsigned int)sub_14000B808(CallbackContext, Argument2);
          }
          else
          {
            return (unsigned int)sub_14000C878(CallbackContext, Argument2);
          }
        }
        else
        {
          return (unsigned int)sub_14000B638(CallbackContext, Argument2);
        }
      }
      else
      {
        return (unsigned int)sub_14000B988(CallbackContext, Argument2);
      }
    }
    else
    {
      return (unsigned int)sub_14000B3F0(CallbackContext, Argument2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000ef80  mov     rax, rsp
0x14000ef83  mov     [rax+8], rbx
0x14000ef87  mov     [rax+10h], rbp
0x14000ef8b  mov     [rax+18h], rsi
0x14000ef8f  mov     [rax+20h], rdi
0x14000ef93  push    r14
0x14000ef95  sub     rsp, 20h
0x14000ef99  mov     rax, cs:PsInitialSystemProcess
0x14000efa0  mov     rbp, r8
0x14000efa3  mov     rdi, rdx
0x14000efa6  mov     r14, rcx
0x14000efa9  xor     esi, esi
0x14000efab  mov     rbx, [rax]
0x14000efae  call    cs:IoGetCurrentProcess
0x14000efb5  nop     dword ptr [rax+rax+00h]
0x14000efba  cmp     rax, rbx
0x14000efbd  jz      short loc_14000F031
0x14000efbf  call    cs:KeGetCurrentIrql
0x14000efc6  nop     dword ptr [rax+rax+00h]
0x14000efcb  cmp     al, 1
0x14000efcd  ja      short loc_14000F031
0x14000efcf  test    rbp, rbp
0x14000efd2  jz      short loc_14000F031
0x14000efd4  test    edi, edi
0x14000efd6  jz      short loc_14000F020
0x14000efd8  sub     edi, 1
0x14000efdb  jz      short loc_14000F013
0x14000efdd  sub     edi, 1
0x14000efe0  jz      short loc_14000F006
0x14000efe2  sub     edi, 2
0x14000efe5  jz      short loc_14000EFF9
0x14000efe7  cmp     edi, 22h ; '"'
0x14000efea  jnz     short loc_14000F02D
0x14000efec  mov     rdx, rbp
0x14000efef  mov     rcx, r14
0x14000eff2  call    sub_14000B808
0x14000eff7  jmp     short loc_14000F02B
0x14000eff9  mov     rdx, rbp
0x14000effc  mov     rcx, r14
0x14000efff  call    sub_14000C878
0x14000f004  jmp     short loc_14000F02B
0x14000f006  mov     rdx, rbp
0x14000f009  mov     rcx, r14
0x14000f00c  call    sub_14000B638
0x14000f011  jmp     short loc_14000F02B
0x14000f013  mov     rdx, rbp
0x14000f016  mov     rcx, r14
0x14000f019  call    sub_14000B988
0x14000f01e  jmp     short loc_14000F02B
0x14000f020  mov     rdx, rbp
0x14000f023  mov     rcx, r14
0x14000f026  call    sub_14000B3F0
0x14000f02b  mov     esi, eax
0x14000f02d  mov     eax, esi
0x14000f02f  jmp     short loc_14000F033
0x14000f031  xor     eax, eax
0x14000f033  mov     rbx, [rsp+28h+arg_0]
0x14000f038  mov     rbp, [rsp+28h+arg_8]
0x14000f03d  mov     rsi, [rsp+28h+arg_10]
0x14000f042  mov     rdi, [rsp+28h+arg_18]
0x14000f047  add     rsp, 20h
0x14000f04b  pop     r14
0x14000f04d  retn
```
