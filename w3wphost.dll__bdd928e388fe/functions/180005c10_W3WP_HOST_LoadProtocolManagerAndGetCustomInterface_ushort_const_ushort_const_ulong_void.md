# W3WP_HOST::LoadProtocolManagerAndGetCustomInterface(ushort const *,ushort const *,ulong,void * *)

- ea: `0x180005c10`
- end: `0x180005c95`
- name: `?LoadProtocolManagerAndGetCustomInterface@W3WP_HOST@@UEAAJPEBG0KPEAPEAX@Z`
- size: `133`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005c10`
- `0x180009630`
- `0x18000d010`

## string_xrefs

- `0x180005c34`: `GetProtocolManager`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::LoadProtocolManagerAndGetCustomInterface(
        W3WP_HOST *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        void **a5)
{
  __int64 result; // rax
  struct PROTOCOL_MANAGER_ENTRY *v7; // [rsp+40h] [rbp+8h] BYREF
  void *v8; // [rsp+50h] [rbp+18h] BYREF

  v7 = 0;
  v8 = 0;
  if ( !a3 || !*a3 )
    a3 = L"GetProtocolManager";
  result = PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry((W3WP_HOST *)((char *)this + 288), a2, a3, &v7, 1);
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void **))(**((_QWORD **)v7 + 32) + 24LL))(
               *((_QWORD *)v7 + 32),
               a4,
               &v8);
    if ( (int)result >= 0 )
    {
      *a5 = v8;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005c10  mov     [rsp+arg_8], rbx
0x180005c15  push    rdi
0x180005c16  sub     rsp, 30h
0x180005c1a  xor     edi, edi
0x180005c1c  mov     ebx, r9d
0x180005c1f  mov     [rsp+38h+arg_0], rdi
0x180005c24  mov     [rsp+38h+arg_10], rdi
0x180005c29  test    r8, r8
0x180005c2c  jz      short loc_180005C34
0x180005c2e  cmp     [r8], di
0x180005c32  jnz     short loc_180005C3B
0x180005c34  lea     r8, aGetprotocolman; "GetProtocolManager"
0x180005c3b  add     rcx, 120h; this
0x180005c42  mov     [rsp+38h+var_18], 1; int
0x180005c4a  lea     r9, [rsp+38h+arg_0]; struct PROTOCOL_MANAGER_ENTRY **
0x180005c4f  call    ?GetProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@H@Z; PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *,int)
0x180005c54  test    eax, eax
0x180005c56  js      short loc_180005C8A
0x180005c58  mov     rax, [rsp+38h+arg_0]
0x180005c5d  lea     r8, [rsp+38h+arg_10]
0x180005c62  mov     edx, ebx
0x180005c64  mov     rcx, [rax+100h]
0x180005c6b  mov     rax, [rcx]
0x180005c6e  mov     rax, [rax+18h]
0x180005c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c77  test    eax, eax
0x180005c79  js      short loc_180005C8A
0x180005c7b  mov     rax, [rsp+38h+arg_10]
0x180005c80  mov     rcx, [rsp+38h+arg_20]
0x180005c85  mov     [rcx], rax
0x180005c88  xor     eax, eax
0x180005c8a  mov     rbx, [rsp+38h+arg_8]
0x180005c8f  add     rsp, 30h
0x180005c93  pop     rdi
0x180005c94  retn
```
