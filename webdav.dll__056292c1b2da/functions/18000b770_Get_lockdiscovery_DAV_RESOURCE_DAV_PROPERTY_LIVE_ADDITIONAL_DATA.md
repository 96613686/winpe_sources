# Get_lockdiscovery(DAV_RESOURCE *,DAV_PROPERTY *,LIVE_ADDITIONAL_DATA *)

- ea: `0x18000b770`
- end: `0x18000b9f5`
- name: `?Get_lockdiscovery@@YAJPEAVDAV_RESOURCE@@PEAVDAV_PROPERTY@@PEAULIVE_ADDITIONAL_DATA@@@Z`
- size: `645`
- prototype: `__int64 __fastcall(struct DAV_RESOURCE *, struct DAV_PROPERTY *, struct LIVE_ADDITIONAL_DATA *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callees

- `0x18000b770`
- `0x180013f2c`
- `0x180020614`
- `0x1800206ec`
- `0x180022520`
- `0x1800225b0`
- `0x180023010`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000b813`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000b9ba`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000b813`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000b9ba`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b96f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b96f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000b7f1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000b7f1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b808`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b9af`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b808`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b9af`
- `iisutil!?AppendA@STRU@@QEAAJPEBD@Z` at `0x18000b984`
- `iisutil!?AppendA@STRU@@QEAAJPEBD@Z` at `0x18000b984`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000b7bd`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000b7bd`

## pseudocode

```c
__int64 __fastcall Get_lockdiscovery(
        __int64 (__fastcall ***a1)(struct DAV_RESOURCE *),
        struct DAV_PROPERTY *a2,
        struct LIVE_ADDITIONAL_DATA *a3)
{
  int v7; // esi
  const char *v8; // rax
  __int64 (__fastcall **v9)(struct DAV_RESOURCE *); // rax
  __int64 v10; // rax
  int appended; // ebx
  __int64 v12; // rbx
  __int64 v13; // rax
  _WORD *v14; // rcx
  _WORD *v15; // rcx
  __int64 (__fastcall **v16)(struct DAV_RESOURCE *); // rax
  const unsigned __int16 *v17; // rax
  int v18; // r9d
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  __int16 *v20; // [rsp+38h] [rbp-C8h]
  const char *v21; // [rsp+40h] [rbp-C0h]
  _BYTE v22[32]; // [rsp+48h] [rbp-B8h] BYREF
  const char *v23; // [rsp+68h] [rbp-98h]
  int v24; // [rsp+78h] [rbp-88h]
  int v25; // [rsp+80h] [rbp-80h]
  _BYTE v26[32]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v27; // [rsp+B0h] [rbp-50h]
  char v28[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v29[624]; // [rsp+D8h] [rbp-28h] BYREF
  int v30; // [rsp+1458h] [rbp+1358h]
  int v31; // [rsp+145Ch] [rbp+135Ch]

  LOCK_SET::LOCK_SET((LOCK_SET *)v28);
  STRA::STRA((STRA *)v22);
  v25 = 65537;
  v21 = ">";
  v19 = 1;
  v20 = &word_1800263B2;
  STRU::STRU((STRU *)v26);
  if ( *(_DWORD *)(*((_QWORD *)a3 + 7) + 28LL) )
  {
    if ( (*((_BYTE *)a3 + 64) & 4) != 0 )
    {
      v7 = 1;
      v19 = 1;
      v20 = &word_1800263B2;
      v8 = ">";
    }
    else
    {
      v19 = 0;
      v20 = (__int16 *)"\r\n";
      v7 = 0;
      v8 = ">\r\n";
    }
    v21 = v8;
    v9 = *a1;
    v25 = 65537;
    v10 = (*v9)((struct DAV_RESOURCE *)a1);
    appended = (*(__int64 (__fastcall **)(__int64 *, __int64))(v29[0] + 8))(v29, v10);
    if ( appended >= 0 )
    {
      v12 = *((_QWORD *)a3 + 7);
      v13 = (**a1)((struct DAV_RESOURCE *)a1);
      appended = (*(__int64 (__fastcall **)(_QWORD, __int64, char *, __int64))(**(_QWORD **)(v12 + 16) + 88LL))(
                   *(_QWORD *)(v12 + 16),
                   v13,
                   v28,
                   1);
      if ( appended >= 0 )
      {
        if ( v30 || v31 )
        {
          *v23 = 0;
          v16 = *a1;
          v24 = 0;
          v17 = (const unsigned __int16 *)v16[1]((struct DAV_RESOURCE *)a1);
          appended = XML_RENDERER::AppendActiveLockSet((XML_RENDERER *)&v19, (struct IPubLockSet *)v28, v17, v18);
          if ( appended >= 0 )
          {
            if ( v7 || (appended = STRU::Copy((STRU *)v26, L"\r\n"), appended >= 0) )
            {
              appended = STRU::AppendA((STRU *)v26, v23);
              if ( appended >= 0 )
                appended = (*(__int64 (__fastcall **)(struct DAV_PROPERTY *, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
                             a2,
                             v27,
                             0,
                             0);
            }
          }
        }
        else
        {
          appended = 0;
          **((_WORD **)a2 + 15) = 0;
          v14 = (_WORD *)*((_QWORD *)a2 + 22);
          *((_DWORD *)a2 + 34) = 0;
          *v14 = 0;
          v15 = (_WORD *)*((_QWORD *)a2 + 29);
          *((_DWORD *)a2 + 48) = 0;
          *v15 = 0;
          *((_DWORD *)a2 + 62) = 0;
          *((_QWORD *)a2 + 32) = 0;
          *((_QWORD *)a2 + 33) = 0;
        }
      }
    }
    STRU::~STRU((STRU *)v26);
    STRA::~STRA((STRA *)v22);
    LOCK_SET::~LOCK_SET((LOCK_SET *)v28);
    return (unsigned int)appended;
  }
  else
  {
    STRU::~STRU((STRU *)v26);
    STRA::~STRA((STRA *)v22);
    LOCK_SET::~LOCK_SET((LOCK_SET *)v28);
    return 0;
  }
}

```

## disassembly

```asm
0x18000b770  mov     [rsp-8+arg_18], rbx
0x18000b775  push    rbp
0x18000b776  push    rsi
0x18000b777  push    rdi
0x18000b778  push    r12
0x18000b77a  push    r13
0x18000b77c  push    r14
0x18000b77e  push    r15
0x18000b780  lea     rbp, [rsp-1370h]
0x18000b788  mov     eax, 1470h
0x18000b78d  call    _alloca_probe
0x18000b792  sub     rsp, rax
0x18000b795  mov     rax, cs:__security_cookie
0x18000b79c  xor     rax, rsp
0x18000b79f  mov     [rbp+13A0h+var_40], rax
0x18000b7a6  mov     r14, rcx
0x18000b7a9  mov     r15, r8
0x18000b7ac  lea     rcx, [rbp+13A0h+var_13D0]; this
0x18000b7b0  mov     rdi, rdx
0x18000b7b3  call    ??0LOCK_SET@@QEAA@XZ; LOCK_SET::LOCK_SET(void)
0x18000b7b8  lea     rcx, [rsp+14A0h+var_1458]
0x18000b7bd  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18000b7c3  lea     rax, asc_1800263B8; ">"
0x18000b7ca  mov     [rbp+13A0h+var_1420], 10001h
0x18000b7d1  mov     r13d, 1
0x18000b7d7  mov     [rsp+14A0h+var_1460], rax
0x18000b7dc  lea     rbx, word_1800263B2
0x18000b7e3  mov     [rsp+14A0h+var_1470], r13d
0x18000b7e8  lea     rcx, [rbp+13A0h+var_1410]
0x18000b7ec  mov     [rsp+14A0h+var_1468], rbx
0x18000b7f1  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000b7f7  mov     rax, [r15+38h]
0x18000b7fb  xor     r12d, r12d
0x18000b7fe  cmp     [rax+1Ch], r12d
0x18000b802  jnz     short loc_18000B829
0x18000b804  lea     rcx, [rbp+13A0h+var_1410]
0x18000b808  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000b80e  lea     rcx, [rsp+14A0h+var_1458]
0x18000b813  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000b819  lea     rcx, [rbp+13A0h+var_13D0]; this
0x18000b81d  call    ??1LOCK_SET@@UEAA@XZ; LOCK_SET::~LOCK_SET(void)
0x18000b822  xor     eax, eax
0x18000b824  jmp     loc_18000B9CB
0x18000b829  test    byte ptr [r15+40h], 4
0x18000b82e  jz      short loc_18000B846
0x18000b830  mov     esi, r13d
0x18000b833  mov     [rsp+14A0h+var_1470], r13d
0x18000b838  mov     [rsp+14A0h+var_1468], rbx
0x18000b83d  lea     rax, asc_1800263B8; ">"
0x18000b844  jmp     short loc_18000B861
0x18000b846  lea     rax, asc_1800263B4; "\r\n"
0x18000b84d  mov     [rsp+14A0h+var_1470], r12d
0x18000b852  mov     [rsp+14A0h+var_1468], rax
0x18000b857  mov     esi, r12d
0x18000b85a  lea     rax, asc_1800263BC; ">\r\n"
0x18000b861  mov     [rsp+14A0h+var_1460], rax
0x18000b866  mov     rcx, r14
0x18000b869  mov     rax, [r14]
0x18000b86c  mov     [rbp+13A0h+var_1420], 10001h
0x18000b873  mov     rax, [rax]
0x18000b876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b87b  mov     rcx, [rbp+13A0h+var_13C8]
0x18000b87f  mov     rdx, rax
0x18000b882  mov     r8, [rcx+8]
0x18000b886  lea     rcx, [rbp+13A0h+var_13C8]
0x18000b88a  mov     rax, r8
0x18000b88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b892  mov     ebx, eax
0x18000b894  test    eax, eax
0x18000b896  js      loc_18000B9AB
0x18000b89c  mov     rax, [r14]
0x18000b89f  mov     rcx, r14
0x18000b8a2  mov     rbx, [r15+38h]
0x18000b8a6  mov     rax, [rax]
0x18000b8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8ae  mov     r10, [rbx+10h]
0x18000b8b2  lea     r8, [rbp+13A0h+var_13D0]
0x18000b8b6  mov     rdx, rax
0x18000b8b9  mov     r9d, r13d
0x18000b8bc  mov     rcx, [r10]
0x18000b8bf  mov     rax, [rcx+58h]
0x18000b8c3  mov     rcx, r10
0x18000b8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8cb  mov     ebx, eax
0x18000b8cd  test    eax, eax
0x18000b8cf  js      loc_18000B9AB
0x18000b8d5  cmp     [rbp+13A0h+var_48], r12d
0x18000b8dc  jnz     short loc_18000B92D
0x18000b8de  cmp     [rbp+13A0h+var_44], r12d
0x18000b8e5  jnz     short loc_18000B92D
0x18000b8e7  mov     rcx, [rdi+78h]
0x18000b8eb  mov     ebx, r12d
0x18000b8ee  mov     [rcx], r12w
0x18000b8f2  mov     rcx, [rdi+0B0h]
0x18000b8f9  mov     [rdi+88h], r12d
0x18000b900  mov     [rcx], r12w
0x18000b904  mov     rcx, [rdi+0E8h]
0x18000b90b  mov     [rdi+0C0h], r12d
0x18000b912  mov     [rcx], r12w
0x18000b916  mov     [rdi+0F8h], r12d
0x18000b91d  mov     [rdi+100h], r12
0x18000b924  mov     [rdi+108h], r12
0x18000b92b  jmp     short loc_18000B9AB
0x18000b92d  mov     rax, [rsp+14A0h+var_1438]
0x18000b932  mov     rcx, r14
0x18000b935  mov     [rax], r12b
0x18000b938  mov     rax, [r14]
0x18000b93b  mov     [rsp+14A0h+var_1428], r12d
0x18000b940  mov     rax, [rax+8]
0x18000b944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b949  mov     r8, rax; unsigned __int16 *
0x18000b94c  lea     rdx, [rbp+13A0h+var_13D0]; struct IPubLockSet *
0x18000b950  lea     rcx, [rsp+14A0h+var_1470]; this
0x18000b955  call    ?AppendActiveLockSet@XML_RENDERER@@AEAAJPEAVIPubLockSet@@PEBGH@Z; XML_RENDERER::AppendActiveLockSet(IPubLockSet *,ushort const *,int)
0x18000b95a  mov     ebx, eax
0x18000b95c  test    eax, eax
0x18000b95e  js      short loc_18000B9AB
0x18000b960  test    esi, esi
0x18000b962  jnz     short loc_18000B97B
0x18000b964  lea     rdx, asc_18002716C; "\r\n"
0x18000b96b  lea     rcx, [rbp+13A0h+var_1410]
0x18000b96f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000b975  mov     ebx, eax
0x18000b977  test    eax, eax
0x18000b979  js      short loc_18000B9AB
0x18000b97b  mov     rdx, [rsp+14A0h+var_1438]
0x18000b980  lea     rcx, [rbp+13A0h+var_1410]
0x18000b984  call    cs:__imp_?AppendA@STRU@@QEAAJPEBD@Z; STRU::AppendA(char const *)
0x18000b98a  mov     ebx, eax
0x18000b98c  test    eax, eax
0x18000b98e  js      short loc_18000B9AB
0x18000b990  mov     rax, [rdi]
0x18000b993  xor     r9d, r9d
0x18000b996  mov     rdx, [rbp+13A0h+var_13F0]
0x18000b99a  xor     r8d, r8d
0x18000b99d  mov     rcx, rdi
0x18000b9a0  mov     rax, [rax+40h]
0x18000b9a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9a9  mov     ebx, eax
0x18000b9ab  lea     rcx, [rbp+13A0h+var_1410]
0x18000b9af  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000b9b5  lea     rcx, [rsp+14A0h+var_1458]
0x18000b9ba  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000b9c0  lea     rcx, [rbp+13A0h+var_13D0]; this
0x18000b9c4  call    ??1LOCK_SET@@UEAA@XZ; LOCK_SET::~LOCK_SET(void)
0x18000b9c9  mov     eax, ebx
0x18000b9cb  mov     rcx, [rbp+13A0h+var_40]
0x18000b9d2  xor     rcx, rsp; StackCookie
0x18000b9d5  call    __security_check_cookie
0x18000b9da  mov     rbx, [rsp+14A0h+arg_18]
0x18000b9e2  add     rsp, 1470h
0x18000b9e9  pop     r15
0x18000b9eb  pop     r14
0x18000b9ed  pop     r13
0x18000b9ef  pop     r12
0x18000b9f1  pop     rdi
0x18000b9f2  pop     rsi
0x18000b9f3  pop     rbp
0x18000b9f4  retn
```
