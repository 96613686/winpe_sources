# PROTOCOL_MANAGER_LIST::FindProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *)

- ea: `0x1800095a8`
- end: `0x180009629`
- name: `?FindProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@AEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@@Z`
- size: `129`
- prototype: `__int64 __fastcall(PROTOCOL_MANAGER_LIST *this, const unsigned __int16 *, char *, struct PROTOCOL_MANAGER_ENTRY **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009630`

## callees

- `0x1800095a8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800095d8`
- `msvcrt!_wcsicmp` at `0x1800095d8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800095cc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800095e9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800095cc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800095e9`

## pseudocode

```c
__int64 __fastcall PROTOCOL_MANAGER_LIST::FindProtocolManagerEntry(
        PROTOCOL_MANAGER_LIST *this,
        const unsigned __int16 *a2,
        char *a3,
        struct PROTOCOL_MANAGER_ENTRY **a4)
{
  char *v4; // rdi
  char *i; // rbx
  const wchar_t *Str; // rax
  unsigned __int16 *v10; // rax
  char *v11; // r8
  int v12; // edx
  int v13; // ecx

  v4 = (char *)this + 8;
  for ( i = (char *)*((_QWORD *)this + 1); i != v4; i = *(char **)i )
  {
    Str = STRU::QueryStr((STRU *)(i + 16));
    if ( !_wcsicmp(Str, a2) )
    {
      v10 = STRU::QueryStr((STRU *)(i + 136));
      v11 = (char *)(a3 - (char *)v10);
      do
      {
        v12 = *(unsigned __int16 *)&v11[(_QWORD)v10];
        v13 = *v10 - v12;
        if ( v13 )
          break;
        ++v10;
      }
      while ( v12 );
      if ( !v13 )
      {
        *a4 = (struct PROTOCOL_MANAGER_ENTRY *)i;
        return 0;
      }
    }
  }
  return 2147943568LL;
}

```

## disassembly

```asm
0x1800095a8  push    rbx
0x1800095aa  push    rbp
0x1800095ab  push    rsi
0x1800095ac  push    rdi
0x1800095ad  push    r14
0x1800095af  sub     rsp, 20h
0x1800095b3  lea     rdi, [rcx+8]
0x1800095b7  mov     rsi, r9
0x1800095ba  mov     rbx, [rdi]
0x1800095bd  mov     rbp, r8
0x1800095c0  mov     r14, rdx
0x1800095c3  cmp     rbx, rdi
0x1800095c6  jz      short loc_180009619
0x1800095c8  lea     rcx, [rbx+10h]
0x1800095cc  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800095d2  mov     rcx, rax; String1
0x1800095d5  mov     rdx, r14; String2
0x1800095d8  call    cs:__imp__wcsicmp
0x1800095de  test    eax, eax
0x1800095e0  jnz     short loc_18000960D
0x1800095e2  lea     rcx, [rbx+88h]
0x1800095e9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800095ef  mov     r8, rbp
0x1800095f2  sub     r8, rax
0x1800095f5  movzx   ecx, word ptr [rax]
0x1800095f8  movzx   edx, word ptr [rax+r8]
0x1800095fd  sub     ecx, edx
0x1800095ff  jnz     short loc_180009609
0x180009601  add     rax, 2
0x180009605  test    edx, edx
0x180009607  jnz     short loc_1800095F5
0x180009609  test    ecx, ecx
0x18000960b  jz      short loc_180009612
0x18000960d  mov     rbx, [rbx]
0x180009610  jmp     short loc_1800095C3
0x180009612  mov     [rsi], rbx
0x180009615  xor     eax, eax
0x180009617  jmp     short loc_18000961E
0x180009619  mov     eax, 80070490h
0x18000961e  add     rsp, 20h
0x180009622  pop     r14
0x180009624  pop     rdi
0x180009625  pop     rsi
0x180009626  pop     rbp
0x180009627  pop     rbx
0x180009628  retn
```
