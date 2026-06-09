# CCriticalSection::Enter(void)

- ea: `0x14000169c`
- end: `0x1400016e8`
- name: `?Enter@CCriticalSection@@QEAAHXZ`
- size: `76`
- prototype: `__int64 __fastcall(CCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400019f0`
- `0x140001b40`
- `0x140001bd0`
- `0x140002310`
- `0x140002bd0`
- `0x140002cd0`
- `0x140007b3c`

## callees

- `0x14000169c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1400016be`
- `KERNEL32!EnterCriticalSection` at `0x1400016be`

## pseudocode

```c
__int64 __fastcall CCriticalSection::Enter(CCriticalSection *this)
{
  _BYTE *v1; // rdi
  unsigned int v2; // ebx

  v1 = (char *)this + 40;
  v2 = 0;
  if ( *((_BYTE *)this + 40) )
    return 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  LOBYTE(v2) = *v1 == 0;
  return v2;
}

```

## disassembly

```asm
0x14000169c  mov     [rsp+arg_10], rbx
0x1400016a1  mov     [rsp+arg_0], rcx
0x1400016a6  push    rdi
0x1400016a7  sub     rsp, 20h
0x1400016ab  lea     rdi, [rcx+28h]
0x1400016af  mov     [rsp+28h+arg_8], rdi
0x1400016b4  xor     ebx, ebx
0x1400016b6  cmp     [rdi], bl
0x1400016b8  jz      short loc_1400016BE
0x1400016ba  xor     eax, eax
0x1400016bc  jmp     short loc_1400016DD
0x1400016be  call    cs:__imp_EnterCriticalSection
0x1400016c4  jmp     short loc_1400016D6
0x1400016c6  mov     rax, [rsp+28h+arg_0]
0x1400016cb  mov     byte ptr [rax+28h], 1
0x1400016cf  xor     ebx, ebx
0x1400016d1  mov     rdi, [rsp+28h+arg_8]
0x1400016d6  cmp     [rdi], bl
0x1400016d8  setz    bl
0x1400016db  mov     eax, ebx
0x1400016dd  mov     rbx, [rsp+28h+arg_10]
0x1400016e2  add     rsp, 20h
0x1400016e6  pop     rdi
0x1400016e7  retn
```
