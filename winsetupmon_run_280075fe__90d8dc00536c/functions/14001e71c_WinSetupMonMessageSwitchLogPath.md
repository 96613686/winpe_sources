# WinSetupMonMessageSwitchLogPath

- ea: `0x14001e71c`
- end: `0x14001e7a0`
- name: `WinSetupMonMessageSwitchLogPath`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140007668`

## callees

- `0x140001220`
- `0x14000362c`
- `0x14000f930`
- `0x14001e044`
- `0x14001e10c`
- `0x14001e71c`

## pseudocode

```c
__int64 __fastcall WinSetupMonMessageSwitchLogPath(char a1, void *a2)
{
  __int64 v3; // r8
  __int64 v4; // rdx
  int v5; // edi
  struct _UNICODE_STRING v7; // [rsp+28h] [rbp-30h] BYREF
  __int128 v8; // [rsp+38h] [rbp-20h] BYREF
  __int64 v9; // [rsp+48h] [rbp-10h]

  v8 = 0;
  v9 = 0;
  v7 = 0;
  if ( a1 )
    RtlCopyFromUser(&v8, a2, 0x18u);
  else
    RtlCopyVolatileMemory(&v8, a2, 0x18u);
  LOBYTE(v3) = a1;
  v5 = WinSetupMonDuplicateCapturedUnicodeStringFromMode(&v7, (char *)&v8 + 8, v3);
  if ( v5 >= 0 )
    v5 = SwitchLogPath(&v7);
  LOBYTE(v4) = a1;
  WinSetupMonFreeCapturedUnicodeStringFromMode(&v7, v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001e71c  mov     [rsp+arg_8], rbx
0x14001e721  mov     [rsp+arg_0], cl
0x14001e725  push    rdi
0x14001e726  sub     rsp, 50h
0x14001e72a  mov     bl, cl
0x14001e72c  xorps   xmm0, xmm0
0x14001e72f  xor     eax, eax
0x14001e731  movups  [rsp+58h+var_20], xmm0
0x14001e736  mov     [rsp+58h+var_10], rax
0x14001e73b  movups  xmmword ptr [rsp+58h+var_30.Length], xmm0
0x14001e740  lea     r8d, [rax+18h]; Size
0x14001e744  lea     rcx, [rsp+58h+var_20]; void *
0x14001e749  test    bl, bl
0x14001e74b  jz      short loc_14001E754
0x14001e74d  call    RtlCopyFromUser
0x14001e752  jmp     short loc_14001E75A
0x14001e754  call    RtlCopyVolatileMemory
0x14001e759  nop
0x14001e75a  mov     r8b, bl
0x14001e75d  lea     rdx, [rsp+58h+var_20+8]
0x14001e762  lea     rcx, [rsp+58h+var_30]
0x14001e767  call    WinSetupMonDuplicateCapturedUnicodeStringFromMode
0x14001e76c  mov     edi, eax
0x14001e76e  test    eax, eax
0x14001e770  js      short loc_14001E786
0x14001e772  lea     rcx, [rsp+58h+var_30]; struct _UNICODE_STRING *
0x14001e777  call    ?SwitchLogPath@@YAJPEBU_UNICODE_STRING@@@Z; SwitchLogPath(_UNICODE_STRING const *)
0x14001e77c  mov     edi, eax
0x14001e77e  jmp     short loc_14001E786
0x14001e780  mov     edi, eax
0x14001e782  mov     bl, [rsp+58h+arg_0]
0x14001e786  mov     dl, bl
0x14001e788  lea     rcx, [rsp+58h+var_30]
0x14001e78d  call    WinSetupMonFreeCapturedUnicodeStringFromMode
0x14001e792  mov     eax, edi
0x14001e794  mov     rbx, [rsp+58h+arg_8]
0x14001e799  add     rsp, 50h
0x14001e79d  pop     rdi
0x14001e79e  retn
0x140021c5f  push    rbp
0x140021c61  sub     rsp, 20h
0x140021c65  mov     rbp, rdx
0x140021c68  xor     eax, eax
0x140021c6a  cmp     [rbp+60h], al
0x140021c6d  setnz   al
0x140021c70  mov     [rbp+20h], eax
0x140021c73  mov     eax, [rbp+20h]
0x140021c76  add     rsp, 20h
0x140021c7a  pop     rbp
0x140021c7b  retn
```
