# W3WP_HOST::LoadProtocolManagerAndGetCustomInterface(ushort const *,ushort const *,ulong,void * *)

- ea: `0x180006180`
- end: `0x180006206`
- name: `?LoadProtocolManagerAndGetCustomInterface@W3WP_HOST@@UEAAJPEBG0KPEAPEAX@Z`
- size: `134`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006180`
- `0x18000a0f4`
- `0x18000e010`

## string_xrefs

- `0x1800061a4`: `GetProtocolManager`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::LoadProtocolManagerAndGetCustomInterface(
        PROTOCOL_MANAGER_LIST ***this,
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
  result = PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(this + 36, a2, a3, &v7, 1);
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
0x180006180  mov     [rsp+arg_8], rbx
0x180006185  push    rdi
0x180006186  sub     rsp, 30h
0x18000618a  xor     edi, edi
0x18000618c  mov     ebx, r9d
0x18000618f  mov     [rsp+38h+arg_0], rdi
0x180006194  mov     [rsp+38h+arg_10], rdi
0x180006199  test    r8, r8
0x18000619c  jz      short loc_1800061A4
0x18000619e  cmp     [r8], di
0x1800061a2  jnz     short loc_1800061AB
0x1800061a4  lea     r8, aGetprotocolman; "GetProtocolManager"
0x1800061ab  add     rcx, 120h; this
0x1800061b2  mov     [rsp+38h+var_18], 1; int
0x1800061ba  lea     r9, [rsp+38h+arg_0]; struct PROTOCOL_MANAGER_ENTRY **
0x1800061bf  call    ?GetProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@H@Z; PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *,int)
0x1800061c4  test    eax, eax
0x1800061c6  js      short loc_1800061FA
0x1800061c8  mov     rax, [rsp+38h+arg_0]
0x1800061cd  lea     r8, [rsp+38h+arg_10]
0x1800061d2  mov     edx, ebx
0x1800061d4  mov     rcx, [rax+100h]
0x1800061db  mov     rax, [rcx]
0x1800061de  mov     rax, [rax+18h]
0x1800061e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061e7  test    eax, eax
0x1800061e9  js      short loc_1800061FA
0x1800061eb  mov     rax, [rsp+38h+arg_10]
0x1800061f0  mov     rcx, [rsp+38h+arg_20]
0x1800061f5  mov     [rcx], rax
0x1800061f8  xor     eax, eax
0x1800061fa  mov     rbx, [rsp+38h+arg_8]
0x1800061ff  add     rsp, 30h
0x180006203  pop     rdi
0x180006204  retn
```
