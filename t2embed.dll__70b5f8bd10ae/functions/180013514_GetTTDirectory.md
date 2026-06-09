# GetTTDirectory

- ea: `0x180013514`
- end: `0x180013573`
- name: `GetTTDirectory`
- size: `95`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fd44`
- `0x1800134b4`
- `0x180016438`
- `0x18001cfc0`
- `0x180027504`
- `0x1800275d4`

## callees

- `0x180013514`
- `0x180015190`
- `0x1800153d0`

## pseudocode

```c
__int64 __fastcall GetTTDirectory(__int64 *a1, _DWORD *a2, __int64 a3)
{
  unsigned int v5; // ebx
  __int16 v7; // [rsp+78h] [rbp+20h] BYREF

  v7 = 0;
  v5 = TTDirectoryEntryOffset((__int64)a1, a2);
  if ( v5 - 1 > 0xFFFFFFFD
    || (unsigned __int16)ReadGeneric(a1, a3, 0x10u, (unsigned __int8 *)&DIRECTORY_CONTROL, v5, &v7) )
  {
    return 0;
  }
  else
  {
    return v5;
  }
}

```

## disassembly

```asm
0x180013514  push    rbx
0x180013516  push    rbp
0x180013517  push    rsi
0x180013518  push    rdi
0x180013519  sub     rsp, 38h
0x18001351d  xor     ebp, ebp
0x18001351f  mov     rsi, r8
0x180013522  mov     [rsp+58h+arg_18], bp
0x180013527  mov     rdi, rcx
0x18001352a  call    TTDirectoryEntryOffset
0x18001352f  mov     ebx, eax
0x180013531  lea     edx, [rax-1]
0x180013534  cmp     edx, 0FFFFFFFDh
0x180013537  jbe     short loc_180013544
0x180013539  xor     eax, eax
0x18001353b  add     rsp, 38h
0x18001353f  pop     rdi
0x180013540  pop     rsi
0x180013541  pop     rbp
0x180013542  pop     rbx
0x180013543  retn
0x180013544  lea     rax, [rsp+58h+arg_18]
0x180013549  mov     r8d, 10h
0x18001354f  mov     [rsp+58h+var_30], rax
0x180013554  lea     r9, DIRECTORY_CONTROL
0x18001355b  mov     rdx, rsi
0x18001355e  mov     [rsp+58h+var_38], ebx
0x180013562  mov     rcx, rdi
0x180013565  call    ReadGeneric
0x18001356a  test    ax, ax
0x18001356d  jnz     short loc_180013539
0x18001356f  mov     eax, ebx
0x180013571  jmp     short loc_18001353B
```
