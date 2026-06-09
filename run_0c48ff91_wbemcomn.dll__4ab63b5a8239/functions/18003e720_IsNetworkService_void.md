# IsNetworkService(void *)

- ea: `0x18003e720`
- end: `0x18003e7bd`
- name: `?IsNetworkService@@YAHPEAX@Z`
- size: `157`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x18001b3c4`
- `0x18001c658`
- `0x18003e720`
- `0x180044310`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18003e797`
- `ntdll!RtlFreeSid` at `0x18003e797`

## pseudocode

```c
__int64 __fastcall IsNetworkService(void *a1)
{
  unsigned int v3; // [rsp+20h] [rbp-60h]
  unsigned int v4; // [rsp+28h] [rbp-58h]
  unsigned int v5; // [rsp+30h] [rbp-50h]
  unsigned int v6; // [rsp+38h] [rbp-48h]
  unsigned int v7; // [rsp+40h] [rbp-40h]
  unsigned int v8; // [rsp+48h] [rbp-38h]
  int v9; // [rsp+60h] [rbp-20h] BYREF
  PSID Sid; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v11; // [rsp+70h] [rbp-10h] BYREF

  *(_DWORD *)v11.Value = 0;
  *(_WORD *)&v11.Value[4] = 1280;
  Sid = 0;
  v9 = 0;
  if ( (unsigned int)DLAllocateAndInitializeSid(&v11, 1u, 0x14u, 0, v3, v4, v5, v6, v7, v8, &Sid) )
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
0x18003e720  mov     [rsp-8+arg_8], rbx
0x18003e725  push    rbp
0x18003e726  mov     rbp, rsp
0x18003e729  sub     rsp, 80h
0x18003e730  mov     rax, cs:__security_cookie
0x18003e737  xor     rax, rsp
0x18003e73a  mov     [rbp+var_8], rax
0x18003e73e  xor     r9d, r9d; unsigned int
0x18003e741  mov     dword ptr [rbp+var_10.Value], 0
0x18003e748  mov     rbx, rcx
0x18003e74b  mov     word ptr [rbp+var_10.Value+4], 500h
0x18003e751  lea     rax, [rbp+Sid]
0x18003e755  mov     [rbp+Sid], 0
0x18003e75d  mov     dl, 1; unsigned __int8
0x18003e75f  mov     [rbp+var_20], 0
0x18003e766  lea     r8d, [r9+14h]; unsigned int
0x18003e76a  mov     [rsp+80h+var_30], rax; void **
0x18003e76f  lea     rcx, [rbp+var_10]; struct _SID_IDENTIFIER_AUTHORITY *
0x18003e773  call    ?DLAllocateAndInitializeSid@@YAHPEAU_SID_IDENTIFIER_AUTHORITY@@EKKKKKKKKPEAPEAX@Z; DLAllocateAndInitializeSid(_SID_IDENTIFIER_AUTHORITY *,uchar,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,void * *)
0x18003e778  test    eax, eax
0x18003e77a  jz      short loc_18003E79D
0x18003e77c  mov     rdx, [rbp+Sid]; void *
0x18003e780  lea     r8, [rbp+var_20]; int *
0x18003e784  mov     rcx, rbx; void *
0x18003e787  call    ?DLCheckTokenMembership@@YAHPEAX0PEAH@Z; DLCheckTokenMembership(void *,void *,int *)
0x18003e78c  test    eax, eax
0x18003e78e  jnz     short loc_18003E793
0x18003e790  mov     [rbp+var_20], eax
0x18003e793  mov     rcx, [rbp+Sid]; Sid
0x18003e797  call    cs:__imp_RtlFreeSid
0x18003e79d  mov     eax, [rbp+var_20]
0x18003e7a0  mov     rcx, [rbp+var_8]
0x18003e7a4  xor     rcx, rsp; StackCookie
0x18003e7a7  call    __security_check_cookie
0x18003e7ac  mov     rbx, [rsp+80h+arg_8]
0x18003e7b4  add     rsp, 80h
0x18003e7bb  pop     rbp
0x18003e7bc  retn
```
