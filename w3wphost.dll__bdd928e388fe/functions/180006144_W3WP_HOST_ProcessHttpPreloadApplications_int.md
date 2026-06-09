# W3WP_HOST::ProcessHttpPreloadApplications(int)

- ea: `0x180006144`
- end: `0x1800061d4`
- name: `?ProcessHttpPreloadApplications@W3WP_HOST@@QEAAJH@Z`
- size: `144`
- prototype: `__int64 __fastcall(PROTOCOL_MANAGER_LIST ***this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800061dc`

## callees

- `0x180006144`
- `0x180009630`
- `0x18000d010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006163`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006163`

## string_xrefs

- `0x180006180`: `GetProtocolManager`

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
0x180006144  mov     [rsp+arg_8], rbx
0x180006149  push    rdi
0x18000614a  sub     rsp, 30h
0x18000614e  mov     rbx, rcx
0x180006151  mov     [rsp+38h+arg_0], 0
0x18000615a  add     rcx, 190h
0x180006161  mov     edi, edx
0x180006163  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180006169  lea     rcx, [rbx+140h]; this
0x180006170  mov     [rsp+38h+var_18], 1; int
0x180006178  mov     rdx, rax; unsigned __int16 *
0x18000617b  lea     r9, [rsp+38h+arg_0]; struct PROTOCOL_MANAGER_ENTRY **
0x180006180  lea     r8, aGetprotocolman; "GetProtocolManager"
0x180006187  call    ?GetProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@H@Z; PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *,int)
0x18000618c  mov     ecx, eax
0x18000618e  test    eax, eax
0x180006190  js      short loc_1800061C7
0x180006192  mov     rax, [rsp+38h+arg_0]
0x180006197  mov     rcx, [rax+120h]
0x18000619e  test    rcx, rcx
0x1800061a1  jnz     short loc_1800061AA
0x1800061a3  mov     ecx, 80004001h
0x1800061a8  jmp     short loc_1800061C7
0x1800061aa  mov     rax, [rcx]
0x1800061ad  mov     r9d, edi
0x1800061b0  xor     r8d, r8d
0x1800061b3  xor     edx, edx
0x1800061b5  mov     rax, [rax+10h]
0x1800061b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061be  mov     ecx, eax
0x1800061c0  xor     eax, eax
0x1800061c2  test    ecx, ecx
0x1800061c4  cmovs   ecx, eax
0x1800061c7  mov     rbx, [rsp+38h+arg_8]
0x1800061cc  mov     eax, ecx
0x1800061ce  add     rsp, 30h
0x1800061d2  pop     rdi
0x1800061d3  retn
```
