# ProbeForWrite

- ea: `0x1400442ec`
- end: `0x140044370`
- name: `ProbeForWrite`
- size: `132`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `14`
- callee_count: `5`
- tags: ``

## callers

- `0x140021428`
- `0x14003fcfc`
- `0x140043038`
- `0x140043654`
- `0x14005cad8`
- `0x140067ecc`
- `0x1400961bc`
- `0x1400ad5c4`
- `0x1400b0bc0`
- `0x1400b6b80`
- `0x1400b6c24`
- `0x1400bc1b4`
- `0x1400c2b18`
- `0x1400dc13c`

## callees

- `0x140040c64`
- `0x140040c7c`
- `0x1400442ec`
- `0x1400fc62c`
- `0x1400fc778`

## pseudocode

```c
void __stdcall ProbeForWrite(volatile void *Address, SIZE_T Length, ULONG Alignment)
{
  unsigned __int64 v3; // rbx
  char *v4; // rax
  unsigned __int64 v5; // rdi
  __int64 v6; // rdx

  v3 = (unsigned __int64)Address;
  if ( Length )
  {
    if ( ((Alignment - 1) & (unsigned int)Address) != 0 )
      ExRaiseDatatypeMisalignment();
    v4 = (char *)Address + Length;
    if ( (char *)Address + Length <= Address || (unsigned __int64)v4 > 0x7FFFFFFF0000LL )
      ExRaiseAccessViolation();
    v5 = ((unsigned __int64)(v4 - 1) & 0xFFFFFFFFFFFFF000uLL) + 4096;
    do
    {
      LOBYTE(v6) = RtlReadUCharFromUser(v3);
      RtlWriteUCharToUser(v3, v6);
      v3 = (v3 & 0xFFFFFFFFFFFFF000uLL) + 4096;
    }
    while ( v3 != v5 );
  }
}

```

## disassembly

```asm
0x1400442ec  mov     [rsp+arg_0], rbx
0x1400442f1  push    rdi
0x1400442f2  sub     rsp, 20h
0x1400442f6  mov     rbx, rcx
0x1400442f9  test    rdx, rdx
0x1400442fc  jz      short loc_140044363
0x1400442fe  dec     r8d
0x140044301  test    rcx, r8
0x140044304  jnz     short loc_14004435D
0x140044306  lea     rax, [rcx+rdx]
0x14004430a  cmp     rax, rcx
0x14004430d  jbe     short loc_140044357
0x14004430f  mov     rcx, 7FFFFFFF0000h
0x140044319  cmp     rax, rcx
0x14004431c  ja      short loc_140044357
0x14004431e  lea     rdi, [rax-1]
0x140044322  and     rdi, 0FFFFFFFFFFFFF000h
0x140044329  add     rdi, 1000h
0x140044330  mov     rcx, rbx
0x140044333  call    RtlReadUCharFromUser
0x140044338  mov     dl, al
0x14004433a  mov     rcx, rbx
0x14004433d  call    RtlWriteUCharToUser
0x140044342  and     rbx, 0FFFFFFFFFFFFF000h
0x140044349  add     rbx, 1000h
0x140044350  cmp     rbx, rdi
0x140044353  jnz     short loc_140044330
0x140044355  jmp     short loc_140044364
0x140044357  call    ExRaiseAccessViolation
0x14004435d  call    ExRaiseDatatypeMisalignment
0x140044363  nop
0x140044364  mov     rbx, [rsp+28h+arg_0]
0x140044369  add     rsp, 20h
0x14004436d  pop     rdi
0x14004436e  retn
```
