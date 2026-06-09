# SmpLogFailureString

- ea: `0x1400010ec`
- end: `0x14000119b`
- name: `SmpLogFailureString`
- size: `175`
- prototype: ``
- caller_count: `30`
- callee_count: `4`
- tags: ``

## callers

- `0x140001f60`
- `0x140003450`
- `0x1400036d0`
- `0x140004610`
- `0x1400050a0`
- `0x1400053e0`
- `0x140005f64`
- `0x140006f30`
- `0x140007420`
- `0x140008470`
- `0x14000c638`
- `0x14000f3ec`
- `0x14000f9c8`
- `0x14000fa74`
- `0x14000fed0`
- `0x140010bb8`
- `0x1400112c8`
- `0x140012f60`
- `0x140013370`
- `0x140013680`
- `0x140013a40`
- `0x140013fd8`
- `0x1400146ac`
- `0x140014c70`
- `0x1400150f0`
- `0x1400151e0`
- `0x140015660`
- `0x140015ae8`
- `0x140016190`
- `0x140017ad0`

## callees

- `0x1400010ec`
- `0x140005998`
- `0x14001cc29`
- `0x14001cc40`

## pseudocode

```c
__int64 __fastcall SmpLogFailureString(__int64 a1, unsigned int a2, _WORD *a3, unsigned int a4)
{
  __int64 v8; // rcx
  __int64 v9; // r8
  char *v10; // rax
  char *v11; // rdx
  _BYTE v13[64]; // [rsp+20h] [rbp-118h] BYREF
  char v14; // [rsp+60h] [rbp-D8h] BYREF

  memset_0(v13, 0, 0xE0u);
  if ( a3 )
  {
    v8 = 2147483646;
    v9 = 64;
    v10 = &v14;
    do
    {
      if ( !v8 )
        break;
      if ( !*a3 )
        break;
      *(_WORD *)v10 = *a3++;
      v10 += 2;
      --v8;
      --v9;
    }
    while ( v9 );
    v11 = v10 - 2;
    if ( v9 )
      v11 = v10;
    *(_WORD *)v11 = 0;
  }
  return SmpInternalLogFailure(a1, a2, a4, v13);
}

```

## disassembly

```asm
0x1400010ec  push    rbx
0x1400010ee  push    rbp
0x1400010ef  push    rsi
0x1400010f0  push    rdi
0x1400010f1  sub     rsp, 118h
0x1400010f8  mov     rax, cs:__security_cookie
0x1400010ff  xor     rax, rsp
0x140001102  mov     [rsp+138h+var_38], rax
0x14000110a  mov     rbx, r8
0x14000110d  mov     esi, edx
0x14000110f  mov     rbp, rcx
0x140001112  xor     edx, edx; Val
0x140001114  mov     r8d, 0E0h; Size
0x14000111a  lea     rcx, [rsp+138h+var_118]; void *
0x14000111f  mov     edi, r9d
0x140001122  call    memset_0
0x140001127  xor     r9d, r9d
0x14000112a  test    rbx, rbx
0x14000112d  jz      short loc_14000116D
0x14000112f  mov     ecx, 7FFFFFFEh
0x140001134  lea     r8d, [r9+40h]
0x140001138  lea     rax, [rsp+138h+var_D8]
0x14000113d  test    rcx, rcx
0x140001140  jz      short loc_14000115E
0x140001142  movzx   edx, word ptr [rbx]
0x140001145  test    dx, dx
0x140001148  jz      short loc_14000115E
0x14000114a  mov     [rax], dx
0x14000114d  add     rbx, 2
0x140001151  add     rax, 2
0x140001155  dec     rcx
0x140001158  sub     r8, 1
0x14000115c  jnz     short loc_14000113D
0x14000115e  test    r8, r8
0x140001161  lea     rdx, [rax-2]
0x140001165  cmovnz  rdx, rax
0x140001169  mov     [rdx], r9w
0x14000116d  lea     r9, [rsp+138h+var_118]
0x140001172  mov     r8d, edi
0x140001175  mov     edx, esi
0x140001177  mov     rcx, rbp
0x14000117a  call    SmpInternalLogFailure
0x14000117f  mov     rcx, [rsp+138h+var_38]
0x140001187  xor     rcx, rsp; StackCookie
0x14000118a  call    __security_check_cookie
0x14000118f  add     rsp, 118h
0x140001196  pop     rdi
0x140001197  pop     rsi
0x140001198  pop     rbp
0x140001199  pop     rbx
0x14000119a  retn
```
