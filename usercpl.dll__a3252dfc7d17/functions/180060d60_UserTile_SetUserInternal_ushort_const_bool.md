# UserTile::_SetUserInternal(ushort const *,bool)

- ea: `0x180060d60`
- end: `0x180060ea1`
- name: `?_SetUserInternal@UserTile@@AEAAJPEBG_N@Z`
- size: `321`
- prototype: `__int64 __fastcall(UserTile *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180015768`
- `0x18002a270`

## callees

- `0x180024a34`
- `0x180038f18`
- `0x180060d60`
- `0x180061108`
- `0x180061158`
- `0x1800708a0`
- `0x180073cec`
- `0x180073e80`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060ddd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060e80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060ddd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060e80`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180060dbe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180060dbe`

## pseudocode

```c
__int64 __fastcall UserTile::_SetUserInternal(UserTile *this, const unsigned __int16 *a2, bool a3)
{
  __int64 result; // rax
  char *v7; // rbx
  unsigned __int64 v8; // rsi
  const WCHAR *v9; // rcx
  const WCHAR *v10; // rcx
  __int64 v11; // rcx
  void *v12; // rcx
  LPVOID pv; // [rsp+70h] [rbp+8h] BYREF

  if ( (*((_BYTE *)this + 256) & 1) != 0 )
    return 2147500037LL;
  if ( !a2 )
    return UserTile::_UpdateTile(this, a3, 1);
  v7 = (char *)this + 264;
  v8 = -1;
  v9 = (const WCHAR *)*((_QWORD *)this + 33);
  if ( v9 )
  {
    if ( *v9 && CompareStringOrdinal(v9, -1, a2, -1, 1) == 2 )
      return UserTile::_UpdateTile(this, a3, 1);
  }
  UserTile::_ShutdownUserTileChangeListener(this);
  if ( *(_QWORD *)v7 )
  {
    CoTaskMemFree(*(LPVOID *)v7);
    *(_QWORD *)v7 = 0;
  }
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 2) = 0;
  do
    ++v8;
  while ( a2[v8] );
  result = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
             (__int64)v7,
             v8);
  if ( (int)result >= 0 )
  {
    StringCchCopyNW(*(unsigned __int16 **)v7, v8 + 1, a2, v8);
    *((_QWORD *)v7 + 1) = v8;
    if ( (int)EnsureUserTileRegKey(*(const unsigned __int16 **)v7) >= 0 )
    {
      v10 = *(const WCHAR **)v7;
      pv = 0;
      if ( (int)GetUserTileRegPath(v10, (LPWSTR *)&pv) >= 0 )
      {
        v11 = *((_QWORD *)this + 39);
        if ( v11 )
        {
          *((_QWORD *)this + 39) = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
        CRegistryChangeListener_CreateInstance(v11, pv);
      }
      v12 = pv;
      pv = 0;
      CoTaskMemFree(v12);
    }
    return UserTile::_UpdateTile(this, a3, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180060d60  push    rbx
0x180060d62  push    rbp
0x180060d63  push    rsi
0x180060d64  push    rdi
0x180060d65  push    r14
0x180060d67  push    r15
0x180060d69  sub     rsp, 38h
0x180060d6d  test    byte ptr [rcx+100h], 1
0x180060d74  mov     r14b, r8b
0x180060d77  mov     rbp, rdx
0x180060d7a  mov     rdi, rcx
0x180060d7d  jz      short loc_180060D89
0x180060d7f  mov     eax, 80004005h
0x180060d84  jmp     loc_180060E94
0x180060d89  xor     r15d, r15d
0x180060d8c  test    rbp, rbp
0x180060d8f  jz      loc_180060E86
0x180060d95  lea     rbx, [rcx+108h]
0x180060d9c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180060da0  mov     rcx, [rbx]; lpString1
0x180060da3  test    rcx, rcx
0x180060da6  jz      short loc_180060DCD
0x180060da8  cmp     [rcx], r15w
0x180060dac  jz      short loc_180060DCD
0x180060dae  mov     r9d, esi; cchCount2
0x180060db1  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180060db9  mov     r8, rbp; lpString2
0x180060dbc  mov     edx, esi; cchCount1
0x180060dbe  call    cs:__imp_CompareStringOrdinal
0x180060dc4  cmp     eax, 2
0x180060dc7  jz      loc_180060E86
0x180060dcd  mov     rcx, rdi; this
0x180060dd0  call    ?_ShutdownUserTileChangeListener@UserTile@@AEAAXXZ; UserTile::_ShutdownUserTileChangeListener(void)
0x180060dd5  mov     rcx, [rbx]; pv
0x180060dd8  test    rcx, rcx
0x180060ddb  jz      short loc_180060DE6
0x180060ddd  call    cs:__imp_CoTaskMemFree
0x180060de3  mov     [rbx], r15
0x180060de6  mov     [rbx+8], r15
0x180060dea  mov     [rbx+10h], r15
0x180060dee  inc     rsi
0x180060df1  cmp     [rbp+rsi*2+0], r15w
0x180060df7  jnz     short loc_180060DEE
0x180060df9  mov     rdx, rsi
0x180060dfc  mov     rcx, rbx
0x180060dff  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180060e04  test    eax, eax
0x180060e06  js      loc_180060E94
0x180060e0c  mov     rcx, [rbx]; unsigned __int16 *
0x180060e0f  lea     rdx, [rsi+1]; unsigned __int64
0x180060e13  mov     r9, rsi; unsigned __int64
0x180060e16  mov     r8, rbp; unsigned __int16 *
0x180060e19  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180060e1e  mov     [rbx+8], rsi
0x180060e22  mov     rcx, [rbx]; unsigned __int16 *
0x180060e25  call    ?EnsureUserTileRegKey@@YAJPEBG@Z; EnsureUserTileRegKey(ushort const *)
0x180060e2a  test    eax, eax
0x180060e2c  js      short loc_180060E86
0x180060e2e  mov     rcx, [rbx]; psz
0x180060e31  lea     rdx, [rsp+68h+pv]; ppwsz
0x180060e36  mov     [rsp+68h+pv], r15
0x180060e3b  call    ?GetUserTileRegPath@@YAJPEBGPEAPEAG@Z; GetUserTileRegPath(ushort const *,ushort * *)
0x180060e40  test    eax, eax
0x180060e42  js      short loc_180060E76
0x180060e44  lea     rbx, [rdi+138h]
0x180060e4b  mov     rcx, [rbx]
0x180060e4e  test    rcx, rcx
0x180060e51  jz      short loc_180060E62
0x180060e53  mov     [rbx], r15
0x180060e56  mov     rax, [rcx]
0x180060e59  mov     rax, [rax+10h]
0x180060e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060e62  mov     rdx, [rsp+68h+pv]
0x180060e67  mov     [rsp+68h+var_40], rbx
0x180060e6c  mov     qword ptr [rsp+68h+bIgnoreCase], rdi
0x180060e71  call    ?CRegistryChangeListener_CreateInstance@@YAJPEAUHKEY__@@PEBGW4REGISTRY_LISTENER_FLAGS@@P6AXPEAX@Z3PEAPEAUIRegistryChangeListener@@@Z; CRegistryChangeListener_CreateInstance(HKEY__ *,ushort const *,REGISTRY_LISTENER_FLAGS,void (*)(void *),void *,IRegistryChangeListener * *)
0x180060e76  mov     rcx, [rsp+68h+pv]; pv
0x180060e7b  mov     [rsp+68h+pv], r15
0x180060e80  call    cs:__imp_CoTaskMemFree
0x180060e86  mov     r8b, 1; bool
0x180060e89  mov     dl, r14b; bool
0x180060e8c  mov     rcx, rdi; this
0x180060e8f  call    ?_UpdateTile@UserTile@@AEAAJ_N0@Z; UserTile::_UpdateTile(bool,bool)
0x180060e94  add     rsp, 38h
0x180060e98  pop     r15
0x180060e9a  pop     r14
0x180060e9c  pop     rdi
0x180060e9d  pop     rsi
0x180060e9e  pop     rbp
0x180060e9f  pop     rbx
0x180060ea0  retn
```
