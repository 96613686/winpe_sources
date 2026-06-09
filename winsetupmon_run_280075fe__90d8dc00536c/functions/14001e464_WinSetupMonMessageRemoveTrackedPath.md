# WinSetupMonMessageRemoveTrackedPath

- ea: `0x14001e464`
- end: `0x14001e505`
- name: `WinSetupMonMessageRemoveTrackedPath`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140007668`

## callees

- `0x140001220`
- `0x140006bd4`
- `0x14000f930`
- `0x14001e044`
- `0x14001e10c`
- `0x14001e464`

## pseudocode

```c
__int64 __fastcall WinSetupMonMessageRemoveTrackedPath(char a1, void *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  int v5; // ebx
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
  if ( WORD4(v8) )
  {
    LOBYTE(v4) = a1;
    v5 = WinSetupMonDuplicateCapturedUnicodeStringFromMode(&v7, (char *)&v8 + 8, v4);
    if ( v5 >= 0 )
      v5 = RemoveTrackedPath(&v7);
  }
  else
  {
    v5 = -1073741811;
  }
  LOBYTE(v3) = a1;
  WinSetupMonFreeCapturedUnicodeStringFromMode(&v7, v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001e464  mov     r11, rsp
0x14001e467  mov     [r11+10h], rbx
0x14001e46b  mov     [r11+18h], rsi
0x14001e46f  mov     [rsp+arg_0], cl
0x14001e473  push    rdi
0x14001e474  sub     rsp, 50h
0x14001e478  mov     dil, cl
0x14001e47b  xorps   xmm0, xmm0
0x14001e47e  xor     eax, eax
0x14001e480  movups  [rsp+58h+var_20], xmm0
0x14001e485  mov     [r11-10h], rax
0x14001e489  movups  xmmword ptr [rsp+58h+var_30.Length], xmm0
0x14001e48e  xor     esi, esi
0x14001e490  lea     r8d, [rax+18h]; Size
0x14001e494  lea     rcx, [r11-20h]; void *
0x14001e498  test    dil, dil
0x14001e49b  jz      short loc_14001E4A4
0x14001e49d  call    RtlCopyFromUser
0x14001e4a2  jmp     short loc_14001E4AA
0x14001e4a4  call    RtlCopyVolatileMemory
0x14001e4a9  nop
0x14001e4aa  cmp     word ptr [rsp+58h+var_20+8], si
0x14001e4af  jnz     short loc_14001E4B8
0x14001e4b1  mov     ebx, 0C000000Dh
0x14001e4b6  jmp     short loc_14001E4E5
0x14001e4b8  mov     r8b, dil
0x14001e4bb  lea     rdx, [rsp+58h+var_20+8]
0x14001e4c0  lea     rcx, [rsp+58h+var_30]
0x14001e4c5  call    WinSetupMonDuplicateCapturedUnicodeStringFromMode
0x14001e4ca  mov     ebx, eax
0x14001e4cc  test    eax, eax
0x14001e4ce  js      short loc_14001E4E5
0x14001e4d0  lea     rcx, [rsp+58h+var_30]; struct _UNICODE_STRING *
0x14001e4d5  call    ?RemoveTrackedPath@@YAJPEBU_UNICODE_STRING@@@Z; RemoveTrackedPath(_UNICODE_STRING const *)
0x14001e4da  mov     ebx, eax
0x14001e4dc  jmp     short loc_14001E4E5
0x14001e4de  mov     ebx, eax
0x14001e4e0  mov     dil, [rsp+58h+arg_0]
0x14001e4e5  mov     dl, dil
0x14001e4e8  lea     rcx, [rsp+58h+var_30]
0x14001e4ed  call    WinSetupMonFreeCapturedUnicodeStringFromMode
0x14001e4f2  mov     eax, ebx
0x14001e4f4  mov     rbx, [rsp+58h+arg_8]
0x14001e4f9  mov     rsi, [rsp+58h+arg_10]
0x14001e4fe  add     rsp, 50h
0x14001e502  pop     rdi
0x14001e503  retn
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
