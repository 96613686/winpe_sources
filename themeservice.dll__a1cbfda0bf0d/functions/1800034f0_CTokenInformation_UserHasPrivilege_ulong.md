# CTokenInformation::UserHasPrivilege(ulong)

- ea: `0x1800034f0`
- end: `0x18000354f`
- name: `?UserHasPrivilege@CTokenInformation@@QEAA_NK@Z`
- size: `95`
- prototype: `char __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180003434`

## callees

- `0x1800034f0`
- `0x180004b20`

## pseudocode

```c
char __fastcall CTokenInformation::UserHasPrivilege(HANDLE *this)
{
  char v1; // di
  _DWORD *v3; // rcx
  __int64 i; // rdx

  v1 = 0;
  if ( *this && !this[2] )
    CTokenInformation::GetTokenPrivileges(this);
  v3 = this[2];
  if ( v3 )
  {
    for ( i = 0; (unsigned int)i < *v3; i = (unsigned int)(i + 1) )
    {
      if ( v3[3 * i + 1] == 7 && !v3[3 * i + 2] )
        return 1;
      v1 = 0;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800034f0  mov     [rsp+arg_0], rbx
0x1800034f5  push    rdi
0x1800034f6  sub     rsp, 20h
0x1800034fa  xor     dil, dil
0x1800034fd  mov     rbx, rcx
0x180003500  cmp     qword ptr [rcx], 0
0x180003504  jnz     short loc_180003541
0x180003506  mov     rcx, [rbx+10h]; this
0x18000350a  test    rcx, rcx
0x18000350d  jz      short loc_180003533
0x18000350f  xor     edx, edx
0x180003511  cmp     edx, [rcx]
0x180003513  jnb     short loc_180003533
0x180003515  lea     r8, [rdx+rdx*2]
0x180003519  cmp     dword ptr [rcx+r8*4+4], 7
0x18000351f  jz      short loc_180003528
0x180003521  xor     dil, dil
0x180003524  inc     edx
0x180003526  jmp     short loc_180003511
0x180003528  cmp     dword ptr [rcx+r8*4+8], 0
0x18000352e  jnz     short loc_180003521
0x180003530  mov     dil, 1
0x180003533  mov     rbx, [rsp+28h+arg_0]
0x180003538  mov     al, dil
0x18000353b  add     rsp, 20h
0x18000353f  pop     rdi
0x180003540  retn
0x180003541  cmp     qword ptr [rcx+10h], 0
0x180003546  jnz     short loc_180003506
0x180003548  call    ?GetTokenPrivileges@CTokenInformation@@AEAAXXZ; CTokenInformation::GetTokenPrivileges(void)
0x18000354d  jmp     short loc_180003506
```
