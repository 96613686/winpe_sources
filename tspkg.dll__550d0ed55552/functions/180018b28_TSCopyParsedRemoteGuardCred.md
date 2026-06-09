# TSCopyParsedRemoteGuardCred

- ea: `0x180018b28`
- end: `0x180018b85`
- name: `TSCopyParsedRemoteGuardCred`
- size: `93`
- prototype: `__int64 __fastcall(struct tagASN1octetstring_t *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180018e3c`

## callees

- `0x1800032c0`
- `0x180009b2c`
- `0x180018b28`
- `0x18001c63c`

## pseudocode

```c
__int64 __fastcall TSCopyParsedRemoteGuardCred(struct tagASN1octetstring_t *a1, struct _UNICODE_STRING *a2)
{
  __int64 result; // rax
  WCHAR *v5; // rax

  result = TSOctetStringToUnicodeGeneral(a2, a1, 0);
  if ( (int)result >= 0 )
  {
    v5 = (WCHAR *)TSAllocate(*((unsigned int *)a1 + 4));
    a2[1].Buffer = v5;
    if ( v5 )
    {
      *(_DWORD *)&a2[1].Length = *((_DWORD *)a1 + 4);
      memcpy_0(v5, *((const void **)a1 + 3), *((unsigned int *)a1 + 4));
      return 0;
    }
    else
    {
      return 3221225495LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180018b28  mov     [rsp+arg_0], rbx
0x180018b2d  push    rdi
0x180018b2e  sub     rsp, 20h
0x180018b32  mov     rdi, rdx
0x180018b35  mov     rbx, rcx
0x180018b38  mov     rdx, rcx; struct tagASN1octetstring_t *
0x180018b3b  xor     r8d, r8d; unsigned __int8
0x180018b3e  mov     rcx, rdi; struct _UNICODE_STRING *
0x180018b41  call    ?TSOctetStringToUnicodeGeneral@@YAJPEAU_UNICODE_STRING@@PEBUtagASN1octetstring_t@@E@Z; TSOctetStringToUnicodeGeneral(_UNICODE_STRING *,tagASN1octetstring_t const *,uchar)
0x180018b46  test    eax, eax
0x180018b48  js      short loc_180018B7A
0x180018b4a  mov     ecx, [rbx+10h]; Size
0x180018b4d  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x180018b52  mov     [rdi+18h], rax
0x180018b56  mov     rcx, rax; void *
0x180018b59  test    rax, rax
0x180018b5c  jnz     short loc_180018B65
0x180018b5e  mov     eax, 0C0000017h
0x180018b63  jmp     short loc_180018B7A
0x180018b65  mov     eax, [rbx+10h]
0x180018b68  mov     [rdi+10h], eax
0x180018b6b  mov     r8d, [rbx+10h]; Size
0x180018b6f  mov     rdx, [rbx+18h]; Src
0x180018b73  call    memcpy_0
0x180018b78  xor     eax, eax
0x180018b7a  mov     rbx, [rsp+28h+arg_0]
0x180018b7f  add     rsp, 20h
0x180018b83  pop     rdi
0x180018b84  retn
```
