# RtlWideCharArrayCopyStringWorker

- ea: `0x180011b78`
- end: `0x180011bdf`
- name: `RtlWideCharArrayCopyStringWorker`
- size: `103`
- prototype: `__int64 __fastcall(_WORD *, __int64, _QWORD *, _WORD *, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800119d8`
- `0x180011a5c`

## callees

- `0x180011b78`

## pseudocode

```c
__int64 __fastcall RtlWideCharArrayCopyStringWorker(_WORD *a1, __int64 a2, _QWORD *a3, _WORD *a4, __int64 a5)
{
  __int64 result; // rax
  __int64 v8; // r11

  result = 0;
  v8 = 0;
  if ( a2 )
  {
    while ( a5 )
    {
      if ( *a4 )
      {
        *a1++ = *a4++;
        --a5;
        ++v8;
        if ( --a2 )
          continue;
      }
      if ( a2 )
        break;
      goto LABEL_6;
    }
  }
  else
  {
LABEL_6:
    if ( a5 && *a4 )
      result = 2147483653LL;
  }
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180011b78  mov     [rsp+arg_0], rbx
0x180011b7d  mov     [rsp+arg_8], rdi
0x180011b82  mov     r10, [rsp+arg_20]
0x180011b87  xor     edi, edi
0x180011b89  mov     rbx, rcx
0x180011b8c  mov     eax, edi
0x180011b8e  mov     r11d, edi
0x180011b91  test    rdx, rdx
0x180011b94  jz      short loc_180011BC0
0x180011b96  test    r10, r10
0x180011b99  jz      short loc_180011BD1
0x180011b9b  movzx   ecx, word ptr [r9]
0x180011b9f  test    cx, cx
0x180011ba2  jz      short loc_180011BBB
0x180011ba4  mov     [rbx], cx
0x180011ba7  add     r9, 2
0x180011bab  add     rbx, 2
0x180011baf  dec     r10
0x180011bb2  inc     r11
0x180011bb5  sub     rdx, 1
0x180011bb9  jnz     short loc_180011B96
0x180011bbb  test    rdx, rdx
0x180011bbe  jnz     short loc_180011BD1
0x180011bc0  test    r10, r10
0x180011bc3  jz      short loc_180011BD1
0x180011bc5  cmp     [r9], di
0x180011bc9  mov     ecx, 80000005h
0x180011bce  cmovnz  eax, ecx
0x180011bd1  mov     rbx, [rsp+arg_0]
0x180011bd6  mov     rdi, [rsp+arg_8]
0x180011bdb  mov     [r8], r11
0x180011bde  retn
```
