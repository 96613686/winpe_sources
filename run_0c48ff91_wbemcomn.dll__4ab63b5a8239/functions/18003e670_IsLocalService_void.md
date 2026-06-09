# IsLocalService(void *)

- ea: `0x18003e670`
- end: `0x18003e70d`
- name: `?IsLocalService@@YAHPEAX@Z`
- size: `157`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x18001b3c4`
- `0x18001c658`
- `0x18003e670`
- `0x180044310`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18003e6e7`
- `ntdll!RtlFreeSid` at `0x18003e6e7`

## pseudocode

```c
__int64 __fastcall IsLocalService(void *a1)
{
  unsigned int v3; // [rsp+20h] [rbp-60h]
  unsigned int v4; // [rsp+28h] [rbp-58h]
  unsigned int v5; // [rsp+30h] [rbp-50h]
  unsigned int v6; // [rsp+38h] [rbp-48h]
  unsigned int v7; // [rsp+40h] [rbp-40h]
  unsigned int v8; // [rsp+48h] [rbp-38h]
  int v9; // [rsp+60h] [rbp-20h] BYREF
  PSID Sid; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY v11; // [rsp+70h] [rbp-10h] BYREF

  *(_DWORD *)v11.Value = 0;
  *(_WORD *)&v11.Value[4] = 1280;
  Sid = 0;
  v9 = 0;
  if ( (unsigned int)DLAllocateAndInitializeSid(&v11, 1u, 0x13u, 0, v3, v4, v5, v6, v7, v8, &Sid) )
  {
    if ( !(unsigned int)DLCheckTokenMembership(a1, Sid, &v9) )
      v9 = 0;
    RtlFreeSid(Sid);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003e670  mov     [rsp-8+arg_8], rbx
0x18003e675  push    rbp
0x18003e676  mov     rbp, rsp
0x18003e679  sub     rsp, 80h
0x18003e680  mov     rax, cs:__security_cookie
0x18003e687  xor     rax, rsp
0x18003e68a  mov     [rbp+var_8], rax
0x18003e68e  xor     r9d, r9d; unsigned int
0x18003e691  mov     dword ptr [rbp+var_10.Value], 0
0x18003e698  mov     rbx, rcx
0x18003e69b  mov     word ptr [rbp+var_10.Value+4], 500h
0x18003e6a1  lea     rax, [rbp+Sid]
0x18003e6a5  mov     [rbp+Sid], 0
0x18003e6ad  mov     dl, 1; unsigned __int8
0x18003e6af  mov     [rbp+var_20], 0
0x18003e6b6  lea     r8d, [r9+13h]; unsigned int
0x18003e6ba  mov     [rsp+80h+var_30], rax; void **
0x18003e6bf  lea     rcx, [rbp+var_10]; struct _SID_IDENTIFIER_AUTHORITY *
0x18003e6c3  call    ?DLAllocateAndInitializeSid@@YAHPEAU_SID_IDENTIFIER_AUTHORITY@@EKKKKKKKKPEAPEAX@Z; DLAllocateAndInitializeSid(_SID_IDENTIFIER_AUTHORITY *,uchar,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,void * *)
0x18003e6c8  test    eax, eax
0x18003e6ca  jz      short loc_18003E6ED
0x18003e6cc  mov     rdx, [rbp+Sid]; void *
0x18003e6d0  lea     r8, [rbp+var_20]; int *
0x18003e6d4  mov     rcx, rbx; void *
0x18003e6d7  call    ?DLCheckTokenMembership@@YAHPEAX0PEAH@Z; DLCheckTokenMembership(void *,void *,int *)
0x18003e6dc  test    eax, eax
0x18003e6de  jnz     short loc_18003E6E3
0x18003e6e0  mov     [rbp+var_20], eax
0x18003e6e3  mov     rcx, [rbp+Sid]; Sid
0x18003e6e7  call    cs:__imp_RtlFreeSid
0x18003e6ed  mov     eax, [rbp+var_20]
0x18003e6f0  mov     rcx, [rbp+var_8]
0x18003e6f4  xor     rcx, rsp; StackCookie
0x18003e6f7  call    __security_check_cookie
0x18003e6fc  mov     rbx, [rsp+80h+arg_8]
0x18003e704  add     rsp, 80h
0x18003e70b  pop     rbp
0x18003e70c  retn
```
