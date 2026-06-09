# W3WP_HOST::ProcessHttpPreloadApplications(int)

- ea: `0x180006754`
- end: `0x1800067eb`
- name: `?ProcessHttpPreloadApplications@W3WP_HOST@@QEAAJH@Z`
- size: `151`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800067f4`

## callees

- `0x180006754`
- `0x18000a0f4`
- `0x18000e010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006773`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006773`

## string_xrefs

- `0x180006796`: `GetProtocolManager`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::ProcessHttpPreloadApplications(PROTOCOL_MANAGER_LIST ***this, unsigned int a2)
{
  const unsigned __int16 *Str; // rax
  int ProtocolManagerEntry; // ecx
  __int64 v6; // rcx
  struct PROTOCOL_MANAGER_ENTRY *v8; // [rsp+40h] [rbp+8h] BYREF

  v8 = 0;
  Str = STRU::QueryStr((STRU *)(this + 50));
  ProtocolManagerEntry = PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(this + 40, Str, L"GetProtocolManager", &v8, 1);
  if ( ProtocolManagerEntry >= 0 )
  {
    v6 = *((_QWORD *)v8 + 36);
    if ( v6 )
    {
      ProtocolManagerEntry = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v6 + 16LL))(
                               v6,
                               0,
                               0,
                               a2);
      if ( ProtocolManagerEntry < 0 )
        return 0;
    }
    else
    {
      return (unsigned int)-2147467263;
    }
  }
  return (unsigned int)ProtocolManagerEntry;
}

```

## disassembly

```asm
0x180006754  mov     [rsp+arg_8], rbx
0x180006759  push    rdi
0x18000675a  sub     rsp, 30h
0x18000675e  mov     rbx, rcx
0x180006761  mov     [rsp+38h+arg_0], 0
0x18000676a  add     rcx, 190h
0x180006771  mov     edi, edx
0x180006773  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000677a  nop     dword ptr [rax+rax+00h]
0x18000677f  lea     rcx, [rbx+140h]; this
0x180006786  mov     [rsp+38h+var_18], 1; int
0x18000678e  mov     rdx, rax; unsigned __int16 *
0x180006791  lea     r9, [rsp+38h+arg_0]; struct PROTOCOL_MANAGER_ENTRY **
0x180006796  lea     r8, aGetprotocolman; "GetProtocolManager"
0x18000679d  call    ?GetProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@H@Z; PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *,int)
0x1800067a2  mov     ecx, eax
0x1800067a4  test    eax, eax
0x1800067a6  js      short loc_1800067DD
0x1800067a8  mov     rax, [rsp+38h+arg_0]
0x1800067ad  mov     rcx, [rax+120h]
0x1800067b4  test    rcx, rcx
0x1800067b7  jnz     short loc_1800067C0
0x1800067b9  mov     ecx, 80004001h
0x1800067be  jmp     short loc_1800067DD
0x1800067c0  mov     rax, [rcx]
0x1800067c3  mov     r9d, edi
0x1800067c6  xor     r8d, r8d
0x1800067c9  xor     edx, edx
0x1800067cb  mov     rax, [rax+10h]
0x1800067cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067d4  mov     ecx, eax
0x1800067d6  xor     eax, eax
0x1800067d8  test    ecx, ecx
0x1800067da  cmovs   ecx, eax
0x1800067dd  mov     rbx, [rsp+38h+arg_8]
0x1800067e2  mov     eax, ecx
0x1800067e4  add     rsp, 30h
0x1800067e8  pop     rdi
0x1800067e9  retn
```
