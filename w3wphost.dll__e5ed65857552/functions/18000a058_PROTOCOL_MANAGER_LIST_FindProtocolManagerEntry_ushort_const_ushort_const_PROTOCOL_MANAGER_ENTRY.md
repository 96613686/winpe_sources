# PROTOCOL_MANAGER_LIST::FindProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *)

- ea: `0x18000a058`
- end: `0x18000a0ec`
- name: `?FindProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@AEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@@Z`
- size: `148`
- prototype: `int(PROTOCOL_MANAGER_LIST *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct PROTOCOL_MANAGER_ENTRY **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a0f4`

## callees

- `0x18000a058`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000a08e`
- `msvcrt!_wcsicmp` at `0x18000a08e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a07c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a0a5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a07c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a0a5`

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
0x18000a058  push    rbx
0x18000a05a  push    rbp
0x18000a05b  push    rsi
0x18000a05c  push    rdi
0x18000a05d  push    r14
0x18000a05f  sub     rsp, 20h
0x18000a063  lea     rdi, [rcx+8]
0x18000a067  mov     rsi, r9
0x18000a06a  mov     rbx, [rdi]
0x18000a06d  mov     rbp, r8
0x18000a070  mov     r14, rdx
0x18000a073  cmp     rbx, rdi
0x18000a076  jz      short loc_18000A0DB
0x18000a078  lea     rcx, [rbx+10h]
0x18000a07c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000a083  nop     dword ptr [rax+rax+00h]
0x18000a088  mov     rcx, rax; String1
0x18000a08b  mov     rdx, r14; String2
0x18000a08e  call    cs:__imp__wcsicmp
0x18000a095  nop     dword ptr [rax+rax+00h]
0x18000a09a  test    eax, eax
0x18000a09c  jnz     short loc_18000A0CF
0x18000a09e  lea     rcx, [rbx+88h]
0x18000a0a5  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000a0ac  nop     dword ptr [rax+rax+00h]
0x18000a0b1  mov     r8, rbp
0x18000a0b4  sub     r8, rax
0x18000a0b7  movzx   ecx, word ptr [rax]
0x18000a0ba  movzx   edx, word ptr [rax+r8]
0x18000a0bf  sub     ecx, edx
0x18000a0c1  jnz     short loc_18000A0CB
0x18000a0c3  add     rax, 2
0x18000a0c7  test    edx, edx
0x18000a0c9  jnz     short loc_18000A0B7
0x18000a0cb  test    ecx, ecx
0x18000a0cd  jz      short loc_18000A0D4
0x18000a0cf  mov     rbx, [rbx]
0x18000a0d2  jmp     short loc_18000A073
0x18000a0d4  mov     [rsi], rbx
0x18000a0d7  xor     eax, eax
0x18000a0d9  jmp     short loc_18000A0E0
0x18000a0db  mov     eax, 80070490h
0x18000a0e0  add     rsp, 20h
0x18000a0e4  pop     r14
0x18000a0e6  pop     rdi
0x18000a0e7  pop     rsi
0x18000a0e8  pop     rbp
0x18000a0e9  pop     rbx
0x18000a0ea  retn
```
