# GetTypeAndSubType(char const *,STRA *,STRA *,int *)

- ea: `0x1800174f8`
- end: `0x18001755a`
- name: `?GetTypeAndSubType@@YAJPEBDPEAVSTRA@@1PEAH@Z`
- size: `98`
- prototype: `__int64 __fastcall(const char *, struct STRA *, struct STRA *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180017718`

## callees

- `0x1800174f8`

## import_xrefs

- `msvcrt!strchr` at `0x180017514`
- `msvcrt!strchr` at `0x180017514`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180017532`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180017532`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180017543`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180017543`

## pseudocode

```c
int __fastcall GetTypeAndSubType(const char *a1, struct STRA *a2, struct STRA *a3, int *a4)
{
  char *v8; // rax
  char *v9; // rdi

  v8 = strchr(a1, 47);
  v9 = v8;
  if ( v8 )
  {
    LODWORD(v8) = STRA::Copy(a2, a1, (_DWORD)v8 - (_DWORD)a1);
    if ( (int)v8 >= 0 )
      LODWORD(v8) = STRA::Copy(a3, v9 + 1);
    *a4 = 1;
  }
  else
  {
    *a4 = 0;
  }
  return (int)v8;
}

```

## disassembly

```asm
0x1800174f8  push    rbx
0x1800174fa  push    rbp
0x1800174fb  push    rsi
0x1800174fc  push    rdi
0x1800174fd  push    r14
0x1800174ff  sub     rsp, 20h
0x180017503  mov     r14, rdx
0x180017506  mov     rbx, r9
0x180017509  mov     edx, 2Fh ; '/'; Val
0x18001750e  mov     rbp, r8
0x180017511  mov     rsi, rcx
0x180017514  call    cs:__imp_strchr
0x18001751a  mov     rdi, rax
0x18001751d  test    rax, rax
0x180017520  jnz     short loc_180017526
0x180017522  mov     [rbx], eax
0x180017524  jmp     short loc_18001754F
0x180017526  mov     r8d, edi
0x180017529  mov     rdx, rsi
0x18001752c  sub     r8d, esi
0x18001752f  mov     rcx, r14
0x180017532  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180017538  test    eax, eax
0x18001753a  js      short loc_180017549
0x18001753c  lea     rdx, [rdi+1]
0x180017540  mov     rcx, rbp
0x180017543  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180017549  mov     dword ptr [rbx], 1
0x18001754f  add     rsp, 20h
0x180017553  pop     r14
0x180017555  pop     rdi
0x180017556  pop     rsi
0x180017557  pop     rbp
0x180017558  pop     rbx
0x180017559  retn
```
