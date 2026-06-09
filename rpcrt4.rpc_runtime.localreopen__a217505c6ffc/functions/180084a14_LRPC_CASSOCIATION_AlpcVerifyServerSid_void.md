# LRPC_CASSOCIATION::AlpcVerifyServerSid(void *)

- ea: `0x180084a14`
- end: `0x180084aed`
- name: `?AlpcVerifyServerSid@LRPC_CASSOCIATION@@QEAAJPEAX@Z`
- size: `217`
- prototype: `int(LRPC_CASSOCIATION *__hidden this, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180029fc0`
- `0x180084af4`

## callees

- `0x180022e80`
- `0x1800295d8`
- `0x180084a14`

## import_xrefs

- `ntdll!NtAlpcQueryInformation` at `0x180084a53`
- `ntdll!NtAlpcQueryInformation` at `0x180084a53`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180084a2c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180084a2c`

## pseudocode

```c
__int64 __fastcall LRPC_CASSOCIATION::AlpcVerifyServerSid(LRPC_CASSOCIATION *this, unsigned int *a2)
{
  DWORD LengthSid; // eax
  int Information; // esi
  unsigned int v6; // ebx
  int v8; // [rsp+28h] [rbp-40h]
  int v9; // [rsp+30h] [rbp-38h]
  _DWORD v10[10]; // [rsp+40h] [rbp-28h] BYREF

  LengthSid = GetLengthSid(a2);
  Information = NtAlpcQueryInformation(*((_QWORD *)this + 17), 3, a2, LengthSid, 0);
  LogEvent(0x4Cu, 0x71u, *((void **)this + 17), (void *)3, *a2, v8, v9);
  if ( Information )
  {
    if ( Information == -1073741152 )
    {
      v6 = -1073606633;
      RpcpErrorAddRecord(2u, -1073606633, 0x19Au, 0, 0);
    }
    else
    {
      v10[0] = 3;
      v6 = 1727;
      v10[2] = Information;
      RpcpErrorAddRecord(2u, 1727, 0x19Bu, 1, (struct tagParam *)v10);
    }
  }
  else
  {
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180084a14  mov     [rsp+arg_0], rbx
0x180084a19  mov     [rsp+arg_8], rsi
0x180084a1e  push    rdi
0x180084a1f  sub     rsp, 60h
0x180084a23  mov     rdi, rcx
0x180084a26  mov     rbx, rdx
0x180084a29  mov     rcx, rdx; pSid
0x180084a2c  call    cs:__imp_GetLengthSid
0x180084a33  nop     dword ptr [rax+rax+00h]
0x180084a38  mov     rcx, [rdi+88h]
0x180084a3f  mov     r8, rbx
0x180084a42  mov     r9d, eax
0x180084a45  mov     [rsp+68h+var_48], 0
0x180084a4e  mov     edx, 3
0x180084a53  call    cs:__imp_NtAlpcQueryInformation
0x180084a5a  nop     dword ptr [rax+rax+00h]
0x180084a5f  mov     ecx, [rbx]
0x180084a61  mov     r9d, 3; void *
0x180084a67  mov     r8, [rdi+88h]; void *
0x180084a6e  mov     dl, 71h ; 'q'; unsigned __int8
0x180084a70  mov     [rsp+68h+var_48], rcx; unsigned __int64
0x180084a75  mov     esi, eax
0x180084a77  mov     cl, 4Ch ; 'L'; unsigned __int8
0x180084a79  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x180084a7e  test    esi, esi
0x180084a80  jnz     short loc_180084A97
0x180084a82  xor     ebx, ebx
0x180084a84  mov     rsi, [rsp+68h+arg_8]
0x180084a89  mov     eax, ebx
0x180084a8b  mov     rbx, [rsp+68h+arg_0]
0x180084a90  add     rsp, 60h
0x180084a94  pop     rdi
0x180084a95  retn
0x180084a97  mov     ecx, 2; unsigned int
0x180084a9c  cmp     esi, 0C00002A0h
0x180084aa2  jnz     short loc_180084ABD
0x180084aa4  mov     ebx, 0C0021017h
0x180084aa9  mov     [rsp+68h+var_48], 0
0x180084ab2  mov     r8d, 19Ah
0x180084ab8  xor     r9d, r9d
0x180084abb  jmp     short loc_180084AE4
0x180084abd  lea     rax, [rsp+68h+var_28]
0x180084ac2  mov     [rsp+68h+var_28], 3
0x180084aca  mov     [rsp+68h+var_48], rax; struct tagParam *
0x180084acf  mov     ebx, 6BFh
0x180084ad4  mov     [rsp+68h+var_20], esi
0x180084ad8  mov     r8d, 19Bh; unsigned __int16
0x180084ade  mov     r9d, 1; int
0x180084ae4  mov     edx, ebx; int
0x180084ae6  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180084aeb  jmp     short loc_180084A84
```
