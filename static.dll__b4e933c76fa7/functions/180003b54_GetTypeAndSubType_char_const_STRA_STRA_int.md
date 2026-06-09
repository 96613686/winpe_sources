# GetTypeAndSubType(char const *,STRA *,STRA *,int *)

- ea: `0x180003b54`
- end: `0x180003bb6`
- name: `?GetTypeAndSubType@@YAJPEBDPEAVSTRA@@1PEAH@Z`
- size: `98`
- prototype: `int __fastcall(const char *, struct STRA *, struct STRA *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003d74`

## callees

- `0x180003b54`

## import_xrefs

- `msvcrt!strchr` at `0x180003b70`
- `msvcrt!strchr` at `0x180003b70`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180003b8e`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180003b8e`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003b9f`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003b9f`

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
0x180003b54  push    rbx
0x180003b56  push    rbp
0x180003b57  push    rsi
0x180003b58  push    rdi
0x180003b59  push    r14
0x180003b5b  sub     rsp, 20h
0x180003b5f  mov     r14, rdx
0x180003b62  mov     rbx, r9
0x180003b65  mov     edx, 2Fh ; '/'; Val
0x180003b6a  mov     rbp, r8
0x180003b6d  mov     rsi, rcx
0x180003b70  call    cs:__imp_strchr
0x180003b76  mov     rdi, rax
0x180003b79  test    rax, rax
0x180003b7c  jnz     short loc_180003B82
0x180003b7e  mov     [rbx], eax
0x180003b80  jmp     short loc_180003BAB
0x180003b82  mov     r8d, edi
0x180003b85  mov     rdx, rsi
0x180003b88  sub     r8d, esi
0x180003b8b  mov     rcx, r14
0x180003b8e  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180003b94  test    eax, eax
0x180003b96  js      short loc_180003BA5
0x180003b98  lea     rdx, [rdi+1]
0x180003b9c  mov     rcx, rbp
0x180003b9f  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180003ba5  mov     dword ptr [rbx], 1
0x180003bab  add     rsp, 20h
0x180003baf  pop     r14
0x180003bb1  pop     rdi
0x180003bb2  pop     rsi
0x180003bb3  pop     rbp
0x180003bb4  pop     rbx
0x180003bb5  retn
```
