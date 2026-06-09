# LRPC_CASSOCIATION::AlpcVerifyServerSid(void *)

- ea: `0x18008314c`
- end: `0x180083218`
- name: `?AlpcVerifyServerSid@LRPC_CASSOCIATION@@QEAAJPEAX@Z`
- size: `204`
- prototype: `int(LRPC_CASSOCIATION *__hidden this, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180028d70`
- `0x180083220`

## callees

- `0x180021ce0`
- `0x1800283bc`
- `0x18008314c`

## import_xrefs

- `ntdll!NtAlpcQueryInformation` at `0x180083185`
- `ntdll!NtAlpcQueryInformation` at `0x180083185`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180083164`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180083164`

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
0x18008314c  mov     [rsp+arg_0], rbx
0x180083151  mov     [rsp+arg_8], rsi
0x180083156  push    rdi
0x180083157  sub     rsp, 60h
0x18008315b  mov     rdi, rcx
0x18008315e  mov     rbx, rdx
0x180083161  mov     rcx, rdx; pSid
0x180083164  call    cs:__imp_GetLengthSid
0x18008316a  mov     rcx, [rdi+88h]
0x180083171  mov     r8, rbx
0x180083174  mov     r9d, eax
0x180083177  mov     [rsp+68h+var_48], 0
0x180083180  mov     edx, 3
0x180083185  call    cs:__imp_NtAlpcQueryInformation
0x18008318b  mov     ecx, [rbx]
0x18008318d  mov     r9d, 3; void *
0x180083193  mov     r8, [rdi+88h]; void *
0x18008319a  mov     dl, 71h ; 'q'; unsigned __int8
0x18008319c  mov     [rsp+68h+var_48], rcx; unsigned __int64
0x1800831a1  mov     esi, eax
0x1800831a3  mov     cl, 4Ch ; 'L'; unsigned __int8
0x1800831a5  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x1800831aa  test    esi, esi
0x1800831ac  jnz     short loc_1800831C2
0x1800831ae  xor     ebx, ebx
0x1800831b0  mov     rsi, [rsp+68h+arg_8]
0x1800831b5  mov     eax, ebx
0x1800831b7  mov     rbx, [rsp+68h+arg_0]
0x1800831bc  add     rsp, 60h
0x1800831c0  pop     rdi
0x1800831c1  retn
0x1800831c2  mov     ecx, 2; unsigned int
0x1800831c7  cmp     esi, 0C00002A0h
0x1800831cd  jnz     short loc_1800831E8
0x1800831cf  mov     ebx, 0C0021017h
0x1800831d4  mov     [rsp+68h+var_48], 0
0x1800831dd  mov     r8d, 19Ah
0x1800831e3  xor     r9d, r9d
0x1800831e6  jmp     short loc_18008320F
0x1800831e8  lea     rax, [rsp+68h+var_28]
0x1800831ed  mov     [rsp+68h+var_28], 3
0x1800831f5  mov     [rsp+68h+var_48], rax; struct tagParam *
0x1800831fa  mov     ebx, 6BFh
0x1800831ff  mov     [rsp+68h+var_20], esi
0x180083203  mov     r8d, 19Bh; unsigned __int16
0x180083209  mov     r9d, 1; int
0x18008320f  mov     edx, ebx; int
0x180083211  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180083216  jmp     short loc_1800831B0
```
