# CLIENT_AUTH_INFO::CompareSPNAndSID(CLIENT_AUTH_INFO const *,int *)

- ea: `0x180054150`
- end: `0x180054276`
- name: `?CompareSPNAndSID@CLIENT_AUTH_INFO@@QEBAJPEBU1@PEAH@Z`
- size: `294`
- prototype: `__int64 __fastcall(CLIENT_AUTH_INFO *__hidden this, const struct CLIENT_AUTH_INFO *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800535d0`

## callees

- `0x180022870`
- `0x1800306c8`
- `0x180054150`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18005419a`
- `ntdll!_wcsicmp` at `0x18005419a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800541c6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800541c6`

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
0x180054150  mov     rax, rsp
0x180054153  mov     [rax+8], rbx
0x180054157  mov     [rax+18h], rsi
0x18005415b  push    rdi
0x18005415c  sub     rsp, 20h
0x180054160  mov     rdi, r8
0x180054163  mov     qword ptr [rax+20h], 0
0x18005416b  mov     r8, [rdx+18h]
0x18005416f  lea     rbx, [rcx+18h]
0x180054173  mov     dword ptr [rax+10h], 0
0x18005417a  mov     rsi, rdx
0x18005417d  test    r8, r8
0x180054180  jnz     short loc_1800541BB
0x180054182  mov     r9, [rsi+10h]
0x180054186  mov     rcx, [rcx+10h]; lpAccountName
0x18005418a  test    r9, r9
0x18005418d  jz      short loc_1800541D0
0x18005418f  test    rcx, rcx
0x180054192  jz      short loc_1800541E6
0x180054194  mov     rdx, rcx; String2
0x180054197  mov     rcx, r9; String1
0x18005419a  call    cs:__imp__wcsicmp
0x1800541a0  xor     ecx, ecx
0x1800541a2  test    eax, eax
0x1800541a4  setz    cl
0x1800541a7  mov     [rdi], ecx
0x1800541a9  xor     eax, eax
0x1800541ab  mov     rbx, [rsp+28h+arg_0]
0x1800541b0  mov     rsi, [rsp+28h+arg_10]
0x1800541b5  add     rsp, 20h
0x1800541b9  pop     rdi
0x1800541ba  retn
0x1800541bb  mov     rdx, [rbx]; pSid2
0x1800541be  test    rdx, rdx
0x1800541c1  jz      short loc_180054182
0x1800541c3  mov     rcx, r8; pSid1
0x1800541c6  call    cs:__imp_EqualSid
0x1800541cc  mov     [rdi], eax
0x1800541ce  jmp     short loc_1800541A9
0x1800541d0  test    rcx, rcx
0x1800541d3  jnz     short loc_1800541E6
0x1800541d5  xor     eax, eax
0x1800541d7  cmp     r8, [rbx]
0x1800541da  jmp     short loc_1800541E1
0x1800541dc  xor     eax, eax
0x1800541de  cmp     r9, rcx
0x1800541e1  setz    al
0x1800541e4  jmp     short loc_1800541CC
0x1800541e6  test    r8, r8
0x1800541e9  jnz     short loc_1800541F0
0x1800541eb  cmp     [rbx], r8
0x1800541ee  jz      short loc_1800541DC
0x1800541f0  test    r9, r9
0x1800541f3  jz      short loc_1800541FA
0x1800541f5  test    r8, r8
0x1800541f8  jnz     short loc_18005426B
0x1800541fa  test    rcx, rcx
0x1800541fd  jz      short loc_18005422B
0x1800541ff  cmp     qword ptr [rbx], 0
0x180054203  jnz     short loc_18005426B
0x180054205  lea     r8, [rsp+28h+lpMem]; void **
0x18005420a  lea     rdx, [rsp+28h+arg_8]; int *
0x18005420f  call    ?RpcpLookupAccountName@@YAJPEBGPEAHPEAPEAX@Z; RpcpLookupAccountName(ushort const *,int *,void * *)
0x180054214  test    eax, eax
0x180054216  jnz     short loc_1800541AB
0x180054218  mov     rcx, [rsp+28h+lpMem]; lpMem
0x18005421d  xor     eax, eax
0x18005421f  lock cmpxchg [rbx], rcx
0x180054224  jz      short loc_18005422B
0x180054226  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18005422b  mov     rcx, [rsi+10h]; lpAccountName
0x18005422f  test    rcx, rcx
0x180054232  jz      short loc_18005425F
0x180054234  lea     r8, [rsp+28h+lpMem]; void **
0x180054239  lea     rdx, [rsp+28h+arg_8]; int *
0x18005423e  call    ?RpcpLookupAccountName@@YAJPEBGPEAHPEAPEAX@Z; RpcpLookupAccountName(ushort const *,int *,void * *)
0x180054243  test    eax, eax
0x180054245  jnz     loc_1800541AB
0x18005424b  mov     rcx, [rsp+28h+lpMem]; lpMem
0x180054250  xor     eax, eax
0x180054252  lock cmpxchg [rsi+18h], rcx
0x180054258  jz      short loc_18005425F
0x18005425a  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18005425f  mov     rdx, [rbx]
0x180054262  mov     rcx, [rsi+18h]
0x180054266  jmp     loc_1800541C6
0x18005426b  mov     dword ptr [rdi], 0
0x180054271  jmp     loc_1800541A9
```
