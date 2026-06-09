# CTokenInformation::GetLogonSID(void)

- ea: `0x1800045b8`
- end: `0x180004615`
- name: `?GetLogonSID@CTokenInformation@@QEAAPEAXXZ`
- size: `93`
- prototype: `__int64 __fastcall(unsigned int **this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800020fc`
- `0x180003190`

## callees

- `0x1800045b8`
- `0x1800063fc`

## pseudocode

```c
__int64 __fastcall CTokenInformation::GetLogonSID(unsigned int **this)
{
  __int64 v1; // rdi
  unsigned int *v3; // rcx
  unsigned int v5; // edx

  v1 = 0;
  if ( *this && !this[1] )
    CTokenInformation::GetTokenGroups((CTokenInformation *)this);
  v3 = this[1];
  if ( v3 )
  {
    v5 = 0;
    do
    {
      if ( v5 >= *v3 )
        break;
      if ( (v3[4 * v5 + 4] & 0xC0000000) != 0 )
        v1 = *(_QWORD *)&v3[4 * v5 + 2];
      ++v5;
    }
    while ( !v1 );
  }
  return v1;
}

```

## disassembly

```asm
0x1800045b8  mov     [rsp+arg_0], rbx
0x1800045bd  push    rdi
0x1800045be  sub     rsp, 20h
0x1800045c2  xor     edi, edi
0x1800045c4  mov     rbx, rcx
0x1800045c7  cmp     [rcx], rdi
0x1800045ca  jnz     short loc_180004608
0x1800045cc  mov     rcx, [rbx+8]; this
0x1800045d0  test    rcx, rcx
0x1800045d3  jnz     short loc_1800045E3
0x1800045d5  mov     rbx, [rsp+28h+arg_0]
0x1800045da  mov     rax, rdi
0x1800045dd  add     rsp, 20h
0x1800045e1  pop     rdi
0x1800045e2  retn
0x1800045e3  xor     edx, edx
0x1800045e5  cmp     edx, [rcx]
0x1800045e7  jnb     short loc_1800045D5
0x1800045e9  mov     eax, edx
0x1800045eb  add     rax, rax
0x1800045ee  test    dword ptr [rcx+rax*8+10h], 0C0000000h
0x1800045f6  jnz     short loc_180004601
0x1800045f8  inc     edx
0x1800045fa  test    rdi, rdi
0x1800045fd  jz      short loc_1800045E5
0x1800045ff  jmp     short loc_1800045D5
0x180004601  mov     rdi, [rcx+rax*8+8]
0x180004606  jmp     short loc_1800045F8
0x180004608  cmp     [rcx+8], rdi
0x18000460c  jnz     short loc_1800045CC
0x18000460e  call    ?GetTokenGroups@CTokenInformation@@AEAAXXZ; CTokenInformation::GetTokenGroups(void)
0x180004613  jmp     short loc_1800045CC
```
