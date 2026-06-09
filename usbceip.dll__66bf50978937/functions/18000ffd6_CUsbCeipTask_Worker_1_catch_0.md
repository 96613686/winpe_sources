# _CUsbCeipTask::Worker_::_1_::catch$0

- ea: `0x18000ffd6`
- end: `0x18001002f`
- name: `_CUsbCeipTask::Worker_::_1_::catch$0`
- size: `89`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000ffd6`

## pseudocode

```c
__int64 __fastcall CUsbCeipTask::Worker_::_1_::catch_0(__int64 a1, __int64 a2)
{
  int *v3; // rdx
  int v4; // ecx
  int v5; // ecx
  int v6; // eax

  v3 = *(int **)(a2 + 32);
  v4 = v3[1];
  if ( !v4 )
  {
    v6 = *v3;
    if ( *v3 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    goto LABEL_9;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v6 = *v3;
    goto LABEL_9;
  }
  if ( v5 == 1 )
  {
    v6 = *v3 | 0x10000000;
LABEL_9:
    *(_DWORD *)(a2 + 72) = v6;
    return 0;
  }
  *(_DWORD *)(a2 + 72) = -2147467259;
  return 0;
}

```

## disassembly

```asm
0x18000ffd6  mov     [rsp+arg_8], rdx
0x18000ffdb  push    rbp
0x18000ffdc  sub     rsp, 20h
0x18000ffe0  mov     rbp, rdx
0x18000ffe3  mov     rdx, [rbp+20h]
0x18000ffe7  mov     ecx, [rdx+4]
0x18000ffea  test    ecx, ecx
0x18000ffec  jz      short loc_18001000D
0x18000ffee  sub     ecx, 1
0x18000fff1  jz      short loc_180010009
0x18000fff3  cmp     ecx, 1
0x18000fff6  jz      short loc_180010001
0x18000fff8  mov     dword ptr [rbp+48h], 80004005h
0x18000ffff  jmp     short loc_18001001E
0x180010001  mov     eax, [rdx]
0x180010003  bts     eax, 1Ch
0x180010007  jmp     short loc_18001001B
0x180010009  mov     eax, [rdx]
0x18001000b  jmp     short loc_18001001B
0x18001000d  mov     eax, [rdx]
0x18001000f  test    eax, eax
0x180010011  jle     short loc_18001001B
0x180010013  movzx   eax, ax
0x180010016  or      eax, 80070000h
0x18001001b  mov     [rbp+48h], eax
0x18001001e  mov     rax, 0
0x180010028  add     rsp, 20h
0x18001002c  pop     rbp
0x18001002d  retn
```
