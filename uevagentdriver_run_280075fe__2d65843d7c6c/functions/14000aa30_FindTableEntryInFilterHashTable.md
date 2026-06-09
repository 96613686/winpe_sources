# FindTableEntryInFilterHashTable

- ea: `0x14000aa30`
- end: `0x14000aac9`
- name: `FindTableEntryInFilterHashTable`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a994`
- `0x14000ab5c`

## callees

- `0x140001118`
- `0x140001a70`
- `0x14000aa30`

## pseudocode

```c
char __fastcall FindTableEntryInFilterHashTable(
        unsigned int (__fastcall **a1)(__int64),
        __int64 a2,
        unsigned int (__fastcall **a3)(__int64),
        unsigned int (__fastcall **a4)(__int64))
{
  unsigned int (__fastcall *v6)(__int64); // rbp
  char v9; // si
  unsigned int (__fastcall *i)(__int64); // rcx
  __int64 v11; // r8

  v6 = 0;
  v9 = 0;
  DbgTrace(2, "UevFilter.FindTableEntryInFilterHashTable: Entry\n", (__int64)a3);
  if ( a4 )
    *a4 = 0;
  if ( a3 )
    *a3 = 0;
  for ( i = a1[(*a1)(a2) + 3]; i; i = *(unsigned int (__fastcall **)(__int64))i )
  {
    if ( a2 == *((_QWORD *)i + 1) )
    {
      if ( a3 )
        *a3 = i;
      if ( a4 )
        *a4 = v6;
      v9 = 1;
      break;
    }
    v6 = i;
  }
  DbgTrace(2, "UevFilter.FindTableEntryInFilterHashTable: Exit\n", v11);
  return v9;
}

```

## disassembly

```asm
0x14000aa30  push    rbx
0x14000aa32  push    rbp
0x14000aa33  push    rsi
0x14000aa34  push    rdi
0x14000aa35  push    r14
0x14000aa37  push    r15
0x14000aa39  sub     rsp, 28h
0x14000aa3d  mov     r14, rdx
0x14000aa40  mov     r15, rcx
0x14000aa43  xor     ebp, ebp
0x14000aa45  lea     rdx, aUevfilterFindt; "UevFilter.FindTableEntryInFilterHashTab"...
0x14000aa4c  mov     rdi, r9
0x14000aa4f  mov     rbx, r8
0x14000aa52  xor     sil, sil
0x14000aa55  lea     ecx, [rbp+2]
0x14000aa58  call    DbgTrace
0x14000aa5d  test    rdi, rdi
0x14000aa60  jz      short loc_14000AA65
0x14000aa62  mov     [rdi], rbp
0x14000aa65  test    rbx, rbx
0x14000aa68  jz      short loc_14000AA6D
0x14000aa6a  mov     [rbx], rbp
0x14000aa6d  mov     rax, [r15]
0x14000aa70  mov     rcx, r14
0x14000aa73  call    _guard_dispatch_icall
0x14000aa78  mov     eax, eax
0x14000aa7a  mov     rcx, [r15+rax*8+18h]
0x14000aa7f  jmp     short loc_14000AA8D
0x14000aa81  cmp     r14, [rcx+8]
0x14000aa85  jz      short loc_14000AA94
0x14000aa87  mov     rbp, rcx
0x14000aa8a  mov     rcx, [rcx]
0x14000aa8d  test    rcx, rcx
0x14000aa90  jnz     short loc_14000AA81
0x14000aa92  jmp     short loc_14000AAA7
0x14000aa94  test    rbx, rbx
0x14000aa97  jz      short loc_14000AA9C
0x14000aa99  mov     [rbx], rcx
0x14000aa9c  test    rdi, rdi
0x14000aa9f  jz      short loc_14000AAA4
0x14000aaa1  mov     [rdi], rbp
0x14000aaa4  mov     sil, 1
0x14000aaa7  lea     rdx, aUevfilterFindt_0; "UevFilter.FindTableEntryInFilterHashTab"...
0x14000aaae  mov     ecx, 2
0x14000aab3  call    DbgTrace
0x14000aab8  mov     al, sil
0x14000aabb  add     rsp, 28h
0x14000aabf  pop     r15
0x14000aac1  pop     r14
0x14000aac3  pop     rdi
0x14000aac4  pop     rsi
0x14000aac5  pop     rbp
0x14000aac6  pop     rbx
0x14000aac7  retn
```
