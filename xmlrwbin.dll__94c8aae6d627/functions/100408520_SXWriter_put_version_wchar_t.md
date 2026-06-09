# SXWriter::put_version(wchar_t *)

- ea: `0x100408520`
- end: `0x1004085fd`
- name: `?put_version@SXWriter@@UEAAJPEA_W@Z`
- size: `221`
- prototype: `__int64 __fastcall(SXWriter *__hidden this, wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x100401350`
- `0x100408520`

## pseudocode

```c
__int64 __fastcall SXWriter::put_version(SXWriter *this, wchar_t *a2)
{
  _WORD *v2; // rax
  __int64 v3; // r8
  __int64 v4; // rcx
  int v5; // ebx
  __int64 v6; // r9

  if ( a2 && *a2 )
  {
    v2 = (_WORD *)((char *)this + 188);
    v3 = 2147483646;
    v4 = 16;
    v5 = 0;
    v6 = 0;
    while ( v4 )
    {
      if ( !v3 || !*a2 )
        goto LABEL_10;
      *v2++ = *a2++;
      --v4;
      --v3;
      ++v6;
    }
    --v2;
    v5 = -2147024774;
LABEL_10:
    *v2 = 0;
    if ( v5 )
    {
      MXRRaiseException(-2147024809);
      __debugbreak();
      JUMPOUT(0x1004085FDLL);
    }
  }
  else
  {
    *((_WORD *)this + 94) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x100408520  push    rbx
0x100408522  sub     rsp, 70h
0x100408526  xor     r11d, r11d
0x100408529  test    rdx, rdx
0x10040852c  jz      loc_1004085D9
0x100408532  cmp     [rdx], r11w
0x100408536  jz      loc_1004085D9
0x10040853c  lea     rax, [rcx+0BCh]
0x100408543  mov     r8d, 7FFFFFFEh
0x100408549  mov     [rsp+78h+var_28], r8
0x10040854e  mov     [rsp+78h+var_38], rdx
0x100408553  mov     ecx, 10h
0x100408558  mov     [rsp+78h+var_30], rcx
0x10040855d  mov     [rsp+78h+var_48], rax
0x100408562  mov     ebx, r11d
0x100408565  mov     r9d, r11d
0x100408568  mov     [rsp+78h+var_40], r11
0x10040856d  nop     dword ptr [rax]
0x100408570  test    rcx, rcx
0x100408573  jz      short loc_1004085B9
0x100408575  test    r8, r8
0x100408578  jz      short loc_1004085B4
0x10040857a  movzx   r10d, word ptr [rdx]
0x10040857e  test    r10w, r10w
0x100408582  jz      short loc_1004085B4
0x100408584  mov     [rax], r10w
0x100408588  add     rax, 2
0x10040858c  mov     [rsp+78h+var_48], rax
0x100408591  add     rdx, 2
0x100408595  mov     [rsp+78h+var_38], rdx
0x10040859a  dec     rcx
0x10040859d  mov     [rsp+78h+var_30], rcx
0x1004085a2  dec     r8
0x1004085a5  mov     [rsp+78h+var_28], r8
0x1004085aa  inc     r9
0x1004085ad  mov     [rsp+78h+var_40], r9
0x1004085b2  jmp     short loc_100408570
0x1004085b4  test    rcx, rcx
0x1004085b7  jnz     short loc_1004085CF
0x1004085b9  sub     rax, 2
0x1004085bd  mov     [rsp+78h+var_48], rax
0x1004085c2  dec     r9
0x1004085c5  mov     [rsp+78h+var_40], r9
0x1004085ca  mov     ebx, 8007007Ah
0x1004085cf  mov     [rax], r11w
0x1004085d3  test    ebx, ebx
0x1004085d5  jnz     short loc_1004085F1
0x1004085d7  jmp     short loc_1004085E1
0x1004085d9  mov     [rcx+0BCh], r11w
0x1004085e1  jmp     short loc_1004085E8
0x1004085e3  mov     r11d, [rsp+78h+var_58]
0x1004085e8  mov     eax, r11d
0x1004085eb  add     rsp, 70h
0x1004085ef  pop     rbx
0x1004085f0  retn
0x1004085f1  mov     ecx, 80070057h; int
0x1004085f6  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004085fb  nop
0x1004085fc  int     3; Trap to Debugger
0x100424700  push    rbp
0x100424702  sub     rsp, 20h
0x100424706  mov     rbp, rdx
0x100424709  mov     [rbp+60h], rcx
0x10042470d  mov     [rbp+58h], rcx
0x100424711  mov     rax, [rbp+58h]
0x100424715  mov     rcx, [rax]
0x100424718  mov     [rbp+28h], rcx
0x10042471c  mov     rax, [rbp+28h]
0x100424720  mov     eax, [rax]
0x100424722  cmp     eax, 0C0000005h
0x100424727  jz      short loc_100424759
0x100424729  add     eax, 1FFFFFFFh
0x10042472e  cmp     eax, 1
0x100424731  ja      short loc_100424749
0x100424733  mov     rax, [rbp+28h]
0x100424737  cmp     dword ptr [rax+18h], 1
0x10042473b  jnz     short loc_100424749
0x10042473d  mov     rax, [rbp+28h]
0x100424741  mov     ecx, [rax+20h]
0x100424744  mov     [rbp+20h], ecx
0x100424747  jmp     short loc_100424750
0x100424749  mov     dword ptr [rbp+20h], 8000FFFFh
0x100424750  mov     dword ptr [rbp+24h], 1
0x100424757  jmp     short loc_100424760
0x100424759  mov     dword ptr [rbp+24h], 0
0x100424760  mov     eax, [rbp+24h]
0x100424763  add     rsp, 20h
0x100424767  pop     rbp
0x100424768  retn
```
