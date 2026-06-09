# ldap_MoveMemory

- ea: `0x18001ef10`
- end: `0x18001ef64`
- name: `ldap_MoveMemory`
- size: `84`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800191d0`
- `0x18001d470`
- `0x18001ef6c`
- `0x18002376c`
- `0x18002e6d4`
- `0x18003d78c`
- `0x1800416d0`
- `0x180041e40`

## callees

- `0x18001ef10`

## pseudocode

```c
__int64 __fastcall ldap_MoveMemory(unsigned __int8 *a1, unsigned __int8 *a2, unsigned int a3)
{
  __int64 result; // rax
  unsigned __int8 *v4; // rcx
  unsigned __int8 *i; // rdx

  if ( a1 > a2 )
  {
    result = a3;
    v4 = &a1[a3];
    for ( i = &a2[a3]; a3; --a3 )
    {
      result = *--i;
      *--v4 = result;
    }
  }
  else if ( a1 != a2 && a3 )
  {
    do
    {
      result = *a2++;
      *a1++ = result;
      --a3;
    }
    while ( a3 );
  }
  return result;
}

```

## disassembly

```asm
0x18001ef10  cmp     rcx, rdx
0x18001ef13  ja      short loc_18001EF19
0x18001ef15  jnz     short loc_18001EF47
0x18001ef17  retn
0x18001ef19  mov     eax, r8d
0x18001ef1c  add     rcx, rax
0x18001ef1f  add     rdx, rax
0x18001ef22  test    r8d, r8d
0x18001ef25  jz      short locret_18001EF17
0x18001ef27  nop     word ptr [rax+rax+00000000h]
0x18001ef30  movzx   eax, byte ptr [rdx-1]
0x18001ef34  lea     rdx, [rdx-1]
0x18001ef38  mov     [rcx-1], al
0x18001ef3b  lea     rcx, [rcx-1]
0x18001ef3f  add     r8d, 0FFFFFFFFh
0x18001ef43  jnz     short loc_18001EF30
0x18001ef45  retn
0x18001ef47  test    r8d, r8d
0x18001ef4a  jz      short locret_18001EF17
0x18001ef4c  nop     dword ptr [rax+00h]
0x18001ef50  movzx   eax, byte ptr [rdx]
0x18001ef53  lea     rdx, [rdx+1]
0x18001ef57  mov     [rcx], al
0x18001ef59  lea     rcx, [rcx+1]
0x18001ef5d  add     r8d, 0FFFFFFFFh
0x18001ef61  jnz     short loc_18001EF50
0x18001ef63  retn
```
