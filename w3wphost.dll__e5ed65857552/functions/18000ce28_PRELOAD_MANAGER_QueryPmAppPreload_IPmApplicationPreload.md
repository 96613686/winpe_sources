# PRELOAD_MANAGER::QueryPmAppPreload(IPmApplicationPreload * *)

- ea: `0x18000ce28`
- end: `0x18000cec1`
- name: `?QueryPmAppPreload@PRELOAD_MANAGER@@AEAAJPEAPEAVIPmApplicationPreload@@@Z`
- size: `153`
- prototype: `__int64 __fastcall(PRELOAD_MANAGER *__hidden this, struct IPmApplicationPreload **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c320`

## callees

- `0x18000a0f4`
- `0x18000ce28`

## string_xrefs

- `0x18000ce7b`: `GetProtocolManager`

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
  v6 = &dword_18000FB84;
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
0x18000ce28  mov     [rsp+arg_8], rbx
0x18000ce2d  push    rdi
0x18000ce2e  sub     rsp, 30h
0x18000ce32  mov     rax, [rcx+28h]
0x18000ce36  mov     rdi, rdx
0x18000ce39  mov     [rsp+38h+arg_0], 0
0x18000ce42  mov     rbx, rcx
0x18000ce45  test    rax, rax
0x18000ce48  jnz     short loc_18000CEAE
0x18000ce4a  cmp     dword ptr [rcx+40h], 1
0x18000ce4e  jnz     short loc_18000CE57
0x18000ce50  mov     edx, 80004004h
0x18000ce55  jmp     short loc_18000CEB3
0x18000ce57  mov     rcx, [rcx+20h]
0x18000ce5b  lea     rdx, dword_18000FB84
0x18000ce62  add     rcx, 140h; this
0x18000ce69  mov     [rsp+38h+var_18], 1; int
0x18000ce71  cmp     qword ptr [rbx+18h], 0
0x18000ce76  lea     r9, [rsp+38h+arg_0]; struct PROTOCOL_MANAGER_ENTRY **
0x18000ce7b  lea     r8, aGetprotocolman; "GetProtocolManager"
0x18000ce82  cmovnz  rdx, [rbx+18h]; unsigned __int16 *
0x18000ce87  call    ?GetProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@H@Z; PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *,int)
0x18000ce8c  mov     edx, eax
0x18000ce8e  test    eax, eax
0x18000ce90  js      short loc_18000CEB3
0x18000ce92  mov     rcx, [rsp+38h+arg_0]
0x18000ce97  mov     rax, [rcx+120h]
0x18000ce9e  mov     [rbx+28h], rax
0x18000cea2  test    rax, rax
0x18000cea5  jnz     short loc_18000CEB0
0x18000cea7  mov     edx, 80004001h
0x18000ceac  jmp     short loc_18000CEB3
0x18000ceae  xor     edx, edx
0x18000ceb0  mov     [rdi], rax
0x18000ceb3  mov     rbx, [rsp+38h+arg_8]
0x18000ceb8  mov     eax, edx
0x18000ceba  add     rsp, 30h
0x18000cebe  pop     rdi
0x18000cebf  retn
```
