# HashpInitHash

- ea: `0x18004c1ac`
- end: `0x18004c24d`
- name: `HashpInitHash`
- size: `161`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x18001cec8`
- `0x180046350`
- `0x18004bab4`
- `0x18004bd44`
- `0x18004be0c`
- `0x18004f3e8`

## callees

- `0x1800071c0`
- `0x180007310`
- `0x180021c98`
- `0x180021e00`
- `0x1800229c0`
- `0x18004c1ac`

## pseudocode

```c
__int64 __fastcall HashpInitHash(_DWORD *a1, int *a2)
{
  int v5; // eax

  switch ( *a1 )
  {
    case 0x8003:
      SymCryptMd5Init(a1 + 4, a2, (unsigned int)(*a1 - 32771));
      v5 = 16;
      break;
    case 0x8004:
      SymCryptSha1Init(a1 + 4);
      v5 = 20;
      break;
    case 0x800C:
      SymCryptSha256Init(a1 + 4);
      v5 = 32;
      break;
    case 0x800D:
      SymCryptSha384Init(a1 + 4);
      v5 = 48;
      break;
    case 0x800E:
      SymCryptSha512Init(a1 + 4);
      v5 = 64;
      break;
    default:
      return 3221226536LL;
  }
  a1[1] = v5;
  if ( a2 )
    *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x18004c1ac  mov     [rsp+arg_0], rbx
0x18004c1b1  push    rdi
0x18004c1b2  sub     rsp, 20h
0x18004c1b6  mov     r8d, [rcx]
0x18004c1b9  mov     rdi, rdx
0x18004c1bc  mov     rbx, rcx
0x18004c1bf  sub     r8d, 8003h
0x18004c1c6  jz      short loc_18004C227
0x18004c1c8  sub     r8d, 1
0x18004c1cc  jz      short loc_18004C217
0x18004c1ce  sub     r8d, 8
0x18004c1d2  jz      short loc_18004C207
0x18004c1d4  sub     r8d, 1
0x18004c1d8  jz      short loc_18004C1F7
0x18004c1da  cmp     r8d, 1
0x18004c1de  jz      short loc_18004C1E7
0x18004c1e0  mov     eax, 0C0000428h
0x18004c1e5  jmp     short loc_18004C241
0x18004c1e7  add     rcx, 10h
0x18004c1eb  call    SymCryptSha512Init
0x18004c1f0  mov     eax, 40h ; '@'
0x18004c1f5  jmp     short loc_18004C235
0x18004c1f7  add     rcx, 10h
0x18004c1fb  call    SymCryptSha384Init
0x18004c200  mov     eax, 30h ; '0'
0x18004c205  jmp     short loc_18004C235
0x18004c207  add     rcx, 10h
0x18004c20b  call    SymCryptSha256Init
0x18004c210  mov     eax, 20h ; ' '
0x18004c215  jmp     short loc_18004C235
0x18004c217  add     rcx, 10h
0x18004c21b  call    SymCryptSha1Init
0x18004c220  mov     eax, 14h
0x18004c225  jmp     short loc_18004C235
0x18004c227  add     rcx, 10h
0x18004c22b  call    SymCryptMd5Init
0x18004c230  mov     eax, 10h
0x18004c235  mov     [rbx+4], eax
0x18004c238  test    rdi, rdi
0x18004c23b  jz      short loc_18004C23F
0x18004c23d  mov     [rdi], eax
0x18004c23f  xor     eax, eax
0x18004c241  mov     rbx, [rsp+28h+arg_0]
0x18004c246  add     rsp, 20h
0x18004c24a  pop     rdi
0x18004c24b  retn
```
