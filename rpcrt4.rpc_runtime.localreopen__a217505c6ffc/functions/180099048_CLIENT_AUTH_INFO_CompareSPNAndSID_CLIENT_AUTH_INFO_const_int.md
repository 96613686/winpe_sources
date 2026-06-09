# CLIENT_AUTH_INFO::CompareSPNAndSID(CLIENT_AUTH_INFO const *,int *)

- ea: `0x180099048`
- end: `0x18009917b`
- name: `?CompareSPNAndSID@CLIENT_AUTH_INFO@@QEBAJPEBU1@PEAH@Z`
- size: `307`
- prototype: `__int64 __fastcall(CLIENT_AUTH_INFO *__hidden this, const struct CLIENT_AUTH_INFO *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001403c`

## callees

- `0x180023a40`
- `0x180031a64`
- `0x180099048`

## import_xrefs

- `ntdll!_wcsicmp` at `0x180099092`
- `ntdll!_wcsicmp` at `0x180099092`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800990c5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800990c5`

## pseudocode

```c
__int64 __fastcall CLIENT_AUTH_INFO::CompareSPNAndSID(
        CLIENT_AUTH_INFO *this,
        const struct CLIENT_AUTH_INFO *a2,
        int *a3)
{
  void *v4; // r8
  volatile signed __int64 *v5; // rbx
  const wchar_t *v7; // r9
  const wchar_t *v8; // rcx
  __int64 result; // rax
  void *v10; // rdx
  void *v11; // rcx
  BOOL v12; // eax
  bool v13; // zf
  void *v14; // rcx
  const WCHAR *v15; // rcx
  void *v16; // rcx
  int v17; // [rsp+38h] [rbp+10h] BYREF
  void *lpMem; // [rsp+48h] [rbp+20h] BYREF

  lpMem = 0;
  v4 = (void *)*((_QWORD *)a2 + 3);
  v5 = (volatile signed __int64 *)((char *)this + 24);
  v17 = 0;
  if ( v4 )
  {
    v10 = (void *)*v5;
    if ( *v5 )
    {
      v11 = v4;
LABEL_9:
      v12 = EqualSid(v11, v10);
LABEL_10:
      *a3 = v12;
      return 0;
    }
  }
  v7 = (const wchar_t *)*((_QWORD *)a2 + 2);
  v8 = (const wchar_t *)*((_QWORD *)this + 2);
  if ( v7 )
  {
    if ( v8 )
    {
      *a3 = _wcsicmp(*((const wchar_t **)a2 + 2), v8) == 0;
      return 0;
    }
  }
  else if ( !v8 )
  {
    v12 = 0;
    v13 = v4 == *(void **)v5;
LABEL_14:
    LOBYTE(v12) = v13;
    goto LABEL_10;
  }
  if ( !v4 && !*v5 )
  {
    v12 = 0;
    v13 = v7 == v8;
    goto LABEL_14;
  }
  if ( v7 && v4 )
    goto LABEL_29;
  if ( !v8 )
    goto LABEL_24;
  if ( *v5 )
  {
LABEL_29:
    *a3 = 0;
    return 0;
  }
  result = RpcpLookupAccountName(v8, &v17, &lpMem);
  if ( (_DWORD)result )
    return result;
  v14 = lpMem;
  if ( _InterlockedCompareExchange64(v5, (signed __int64)lpMem, 0) )
    FreeWrapper(v14);
LABEL_24:
  v15 = (const WCHAR *)*((_QWORD *)a2 + 2);
  if ( !v15 )
  {
LABEL_28:
    v10 = (void *)*v5;
    v11 = (void *)*((_QWORD *)a2 + 3);
    goto LABEL_9;
  }
  result = RpcpLookupAccountName(v15, &v17, &lpMem);
  if ( !(_DWORD)result )
  {
    v16 = lpMem;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)a2 + 3, (signed __int64)lpMem, 0) )
      FreeWrapper(v16);
    goto LABEL_28;
  }
  return result;
}

```

## disassembly

```asm
0x180099048  mov     rax, rsp
0x18009904b  mov     [rax+8], rbx
0x18009904f  mov     [rax+18h], rsi
0x180099053  push    rdi
0x180099054  sub     rsp, 20h
0x180099058  mov     rdi, r8
0x18009905b  mov     qword ptr [rax+20h], 0
0x180099063  mov     r8, [rdx+18h]
0x180099067  lea     rbx, [rcx+18h]
0x18009906b  mov     dword ptr [rax+10h], 0
0x180099072  mov     rsi, rdx
0x180099075  test    r8, r8
0x180099078  jnz     short loc_1800990BA
0x18009907a  mov     r9, [rsi+10h]
0x18009907e  mov     rcx, [rcx+10h]; lpAccountName
0x180099082  test    r9, r9
0x180099085  jz      short loc_1800990D5
0x180099087  test    rcx, rcx
0x18009908a  jz      short loc_1800990EB
0x18009908c  mov     rdx, rcx; String2
0x18009908f  mov     rcx, r9; String1
0x180099092  call    cs:__imp__wcsicmp
0x180099099  nop     dword ptr [rax+rax+00h]
0x18009909e  xor     ecx, ecx
0x1800990a0  test    eax, eax
0x1800990a2  setz    cl
0x1800990a5  mov     [rdi], ecx
0x1800990a7  xor     eax, eax
0x1800990a9  mov     rbx, [rsp+28h+arg_0]
0x1800990ae  mov     rsi, [rsp+28h+arg_10]
0x1800990b3  add     rsp, 20h
0x1800990b7  pop     rdi
0x1800990b8  retn
0x1800990ba  mov     rdx, [rbx]; pSid2
0x1800990bd  test    rdx, rdx
0x1800990c0  jz      short loc_18009907A
0x1800990c2  mov     rcx, r8; pSid1
0x1800990c5  call    cs:__imp_EqualSid
0x1800990cc  nop     dword ptr [rax+rax+00h]
0x1800990d1  mov     [rdi], eax
0x1800990d3  jmp     short loc_1800990A7
0x1800990d5  test    rcx, rcx
0x1800990d8  jnz     short loc_1800990EB
0x1800990da  xor     eax, eax
0x1800990dc  cmp     r8, [rbx]
0x1800990df  jmp     short loc_1800990E6
0x1800990e1  xor     eax, eax
0x1800990e3  cmp     r9, rcx
0x1800990e6  setz    al
0x1800990e9  jmp     short loc_1800990D1
0x1800990eb  test    r8, r8
0x1800990ee  jnz     short loc_1800990F5
0x1800990f0  cmp     [rbx], r8
0x1800990f3  jz      short loc_1800990E1
0x1800990f5  test    r9, r9
0x1800990f8  jz      short loc_1800990FF
0x1800990fa  test    r8, r8
0x1800990fd  jnz     short loc_180099170
0x1800990ff  test    rcx, rcx
0x180099102  jz      short loc_180099130
0x180099104  cmp     qword ptr [rbx], 0
0x180099108  jnz     short loc_180099170
0x18009910a  lea     r8, [rsp+28h+lpMem]; void **
0x18009910f  lea     rdx, [rsp+28h+arg_8]; int *
0x180099114  call    ?RpcpLookupAccountName@@YAJPEBGPEAHPEAPEAX@Z; RpcpLookupAccountName(ushort const *,int *,void * *)
0x180099119  test    eax, eax
0x18009911b  jnz     short loc_1800990A9
0x18009911d  mov     rcx, [rsp+28h+lpMem]; lpMem
0x180099122  xor     eax, eax
0x180099124  lock cmpxchg [rbx], rcx
0x180099129  jz      short loc_180099130
0x18009912b  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180099130  mov     rcx, [rsi+10h]; lpAccountName
0x180099134  test    rcx, rcx
0x180099137  jz      short loc_180099164
0x180099139  lea     r8, [rsp+28h+lpMem]; void **
0x18009913e  lea     rdx, [rsp+28h+arg_8]; int *
0x180099143  call    ?RpcpLookupAccountName@@YAJPEBGPEAHPEAPEAX@Z; RpcpLookupAccountName(ushort const *,int *,void * *)
0x180099148  test    eax, eax
0x18009914a  jnz     loc_1800990A9
0x180099150  mov     rcx, [rsp+28h+lpMem]; lpMem
0x180099155  xor     eax, eax
0x180099157  lock cmpxchg [rsi+18h], rcx
0x18009915d  jz      short loc_180099164
0x18009915f  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180099164  mov     rdx, [rbx]
0x180099167  mov     rcx, [rsi+18h]
0x18009916b  jmp     loc_1800990C5
0x180099170  mov     dword ptr [rdi], 0
0x180099176  jmp     loc_1800990A7
```
