# PRELOAD_MANAGER::QueryPmAppPreload(IPmApplicationPreload * *)

- ea: `0x18000bf58`
- end: `0x18000bff0`
- name: `?QueryPmAppPreload@PRELOAD_MANAGER@@AEAAJPEAPEAVIPmApplicationPreload@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(PRELOAD_MANAGER *__hidden this, struct IPmApplicationPreload **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b50c`

## callees

- `0x180009630`
- `0x18000bf58`

## string_xrefs

- `0x18000bfab`: `GetProtocolManager`

## pseudocode

```c
__int64 __fastcall PRELOAD_MANAGER::QueryPmAppPreload(PRELOAD_MANAGER *this, struct IPmApplicationPreload **a2)
{
  struct IPmApplicationPreload *v2; // rax
  int ProtocolManagerEntry; // edx
  const unsigned __int16 *v6; // rdx
  PROTOCOL_MANAGER_LIST ***v7; // rcx
  struct PROTOCOL_MANAGER_ENTRY *v9; // [rsp+40h] [rbp+8h] BYREF

  v2 = (struct IPmApplicationPreload *)*((_QWORD *)this + 5);
  v9 = 0;
  if ( v2 )
  {
    ProtocolManagerEntry = 0;
    goto LABEL_10;
  }
  if ( *((_DWORD *)this + 16) == 1 )
    return (unsigned int)-2147467260;
  v6 = &dword_18000EB74;
  v7 = (PROTOCOL_MANAGER_LIST ***)(*((_QWORD *)this + 4) + 320LL);
  if ( *((_QWORD *)this + 3) )
    v6 = (const unsigned __int16 *)*((_QWORD *)this + 3);
  ProtocolManagerEntry = PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(v7, v6, L"GetProtocolManager", &v9, 1);
  if ( ProtocolManagerEntry >= 0 )
  {
    v2 = (struct IPmApplicationPreload *)*((_QWORD *)v9 + 36);
    *((_QWORD *)this + 5) = v2;
    if ( !v2 )
      return (unsigned int)-2147467263;
LABEL_10:
    *a2 = v2;
  }
  return (unsigned int)ProtocolManagerEntry;
}

```

## disassembly

```asm
0x18000bf58  mov     [rsp+arg_8], rbx
0x18000bf5d  push    rdi
0x18000bf5e  sub     rsp, 30h
0x18000bf62  mov     rax, [rcx+28h]
0x18000bf66  mov     rdi, rdx
0x18000bf69  mov     [rsp+38h+arg_0], 0
0x18000bf72  mov     rbx, rcx
0x18000bf75  test    rax, rax
0x18000bf78  jnz     short loc_18000BFDE
0x18000bf7a  cmp     dword ptr [rcx+40h], 1
0x18000bf7e  jnz     short loc_18000BF87
0x18000bf80  mov     edx, 80004004h
0x18000bf85  jmp     short loc_18000BFE3
0x18000bf87  mov     rcx, [rcx+20h]
0x18000bf8b  lea     rdx, dword_18000EB74
0x18000bf92  add     rcx, 140h; this
0x18000bf99  mov     [rsp+38h+var_18], 1; int
0x18000bfa1  cmp     qword ptr [rbx+18h], 0
0x18000bfa6  lea     r9, [rsp+38h+arg_0]; struct PROTOCOL_MANAGER_ENTRY **
0x18000bfab  lea     r8, aGetprotocolman; "GetProtocolManager"
0x18000bfb2  cmovnz  rdx, [rbx+18h]; unsigned __int16 *
0x18000bfb7  call    ?GetProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@H@Z; PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *,int)
0x18000bfbc  mov     edx, eax
0x18000bfbe  test    eax, eax
0x18000bfc0  js      short loc_18000BFE3
0x18000bfc2  mov     rcx, [rsp+38h+arg_0]
0x18000bfc7  mov     rax, [rcx+120h]
0x18000bfce  mov     [rbx+28h], rax
0x18000bfd2  test    rax, rax
0x18000bfd5  jnz     short loc_18000BFE0
0x18000bfd7  mov     edx, 80004001h
0x18000bfdc  jmp     short loc_18000BFE3
0x18000bfde  xor     edx, edx
0x18000bfe0  mov     [rdi], rax
0x18000bfe3  mov     rbx, [rsp+38h+arg_8]
0x18000bfe8  mov     eax, edx
0x18000bfea  add     rsp, 30h
0x18000bfee  pop     rdi
0x18000bfef  retn
```
