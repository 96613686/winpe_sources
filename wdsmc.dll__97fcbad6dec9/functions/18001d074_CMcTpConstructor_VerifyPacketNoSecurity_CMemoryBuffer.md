# CMcTpConstructor::VerifyPacketNoSecurity(CMemoryBuffer *)

- ea: `0x18001d074`
- end: `0x18001d0d2`
- name: `?VerifyPacketNoSecurity@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z`
- size: `94`
- prototype: `__int64 __fastcall(CMcTpConstructor *this, struct CMemoryBuffer *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015c34`

## callees

- `0x18001d074`
- `0x180026d3a`

## pseudocode

```c
__int64 __fastcall CMcTpConstructor::VerifyPacketNoSecurity(CMcTpConstructor *this, struct CMemoryBuffer *a2)
{
  unsigned int v3; // ebx
  unsigned int v4; // edx
  _WORD *v5; // rcx

  v3 = 0;
  v4 = *((_DWORD *)a2 + 12);
  if ( v4 < 5 )
    return 13;
  v5 = (_WORD *)*((_QWORD *)a2 + 5);
  if ( *v5 != *(_WORD *)"WD" || *(_WORD *)((char *)v5 + 3) )
  {
    return 13;
  }
  else if ( *((_BYTE *)v5 + 2) )
  {
    return (unsigned int)-1054801650;
  }
  else
  {
    memmove_0(v5, (char *)v5 + 5, v4 - 5);
    *((_DWORD *)a2 + 12) -= 5;
  }
  return v3;
}

```

## disassembly

```asm
0x18001d074  mov     [rsp+arg_0], rbx
0x18001d079  push    rdi
0x18001d07a  sub     rsp, 20h
0x18001d07e  mov     rdi, rdx
0x18001d081  xor     ebx, ebx
0x18001d083  mov     edx, [rdx+30h]
0x18001d086  cmp     edx, 5
0x18001d089  jb      short loc_18001D0C0
0x18001d08b  mov     rcx, [rdi+28h]; void *
0x18001d08f  movzx   eax, word ptr [rcx]
0x18001d092  cmp     ax, word ptr cs:aWd; "WD"
0x18001d099  jnz     short loc_18001D0C0
0x18001d09b  cmp     [rcx+3], bx
0x18001d09f  jnz     short loc_18001D0C0
0x18001d0a1  cmp     [rcx+2], bl
0x18001d0a4  jz      short loc_18001D0AD
0x18001d0a6  mov     ebx, 0C121010Eh
0x18001d0ab  jmp     short loc_18001D0C5
0x18001d0ad  lea     r8d, [rdx-5]; Size
0x18001d0b1  lea     rdx, [rcx+5]; Src
0x18001d0b5  call    memmove_0
0x18001d0ba  add     dword ptr [rdi+30h], 0FFFFFFFBh
0x18001d0be  jmp     short loc_18001D0C5
0x18001d0c0  mov     ebx, 0Dh
0x18001d0c5  mov     eax, ebx
0x18001d0c7  mov     rbx, [rsp+28h+arg_0]
0x18001d0cc  add     rsp, 20h
0x18001d0d0  pop     rdi
0x18001d0d1  retn
```
