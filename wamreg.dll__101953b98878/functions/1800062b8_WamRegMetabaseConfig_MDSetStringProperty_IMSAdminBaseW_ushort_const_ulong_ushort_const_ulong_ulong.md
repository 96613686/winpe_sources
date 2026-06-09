# WamRegMetabaseConfig::MDSetStringProperty(IMSAdminBaseW *,ushort const *,ulong,ushort const *,ulong,ulong)

- ea: `0x1800062b8`
- end: `0x180006392`
- name: `?MDSetStringProperty@WamRegMetabaseConfig@@QEAAJPEAUIMSAdminBaseW@@PEBGK1KK@Z`
- size: `218`
- prototype: `__int64 __fastcall(WamRegMetabaseConfig *this, struct IMSAdminBaseW *, const unsigned __int16 *, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180002730`

## callees

- `0x1800062b8`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall WamRegMetabaseConfig::MDSetStringProperty(
        WamRegMetabaseConfig *this,
        struct IMSAdminBaseW *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        const unsigned __int16 *a5)
{
  LPVOID v5; // rbx
  int v6; // edi
  __int64 v7; // rax
  __int128 v9; // [rsp+40h] [rbp-38h] BYREF
  __int128 v10; // [rsp+50h] [rbp-28h]
  __int64 v11; // [rsp+60h] [rbp-18h]
  unsigned int v12; // [rsp+B8h] [rbp+40h] BYREF

  v5 = WamRegMetabaseConfig::m_pMetabase;
  v11 = 0;
  v12 = 0;
  v9 = 0;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const unsigned __int16 *, __int64, int, unsigned int *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 136LL))(
         WamRegMetabaseConfig::m_pMetabase,
         0,
         a3,
         2,
         30000,
         &v12);
  if ( v6 >= 0 )
  {
    *((_QWORD *)&v9 + 1) = 0x200000001LL;
    v7 = -1;
    *(_QWORD *)&v9 = 0x10000238DLL;
    do
      ++v7;
    while ( a5[v7] );
    LODWORD(v10) = 2 * v7 + 2;
    *((_QWORD *)&v10 + 1) = a5;
    v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const wchar_t *, __int128 *))(*(_QWORD *)v5 + 72LL))(
           v5,
           v12,
           L"/",
           &v9);
    if ( v6 >= 0 )
      v6 = 0;
  }
  if ( v12 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 144LL))(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800062b8  mov     [rsp-20h+arg_18], r9d
0x1800062bd  push    rbp
0x1800062be  push    rbx
0x1800062bf  push    rsi
0x1800062c0  push    rdi
0x1800062c1  mov     rbp, rsp
0x1800062c4  sub     rsp, 78h
0x1800062c8  mov     rbx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x1800062cf  lea     rcx, [rbp+arg_18]
0x1800062d3  xor     eax, eax
0x1800062d5  mov     [rsp+78h+var_50], rcx
0x1800062da  xorps   xmm0, xmm0
0x1800062dd  mov     [rbp+var_18], rax
0x1800062e1  xor     esi, esi
0x1800062e3  mov     [rsp+78h+var_58], 7530h
0x1800062eb  mov     [rbp+arg_18], esi
0x1800062ee  xor     edx, edx
0x1800062f0  movups  [rbp+var_38], xmm0
0x1800062f4  mov     rcx, rbx
0x1800062f7  movups  [rbp+var_28], xmm0
0x1800062fb  mov     rax, [rbx]
0x1800062fe  lea     r9d, [rsi+2]
0x180006302  mov     rax, [rax+88h]
0x180006309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000630e  mov     edi, eax
0x180006310  test    eax, eax
0x180006312  js      short loc_18000636E
0x180006314  mov     rcx, [rbp+arg_20]
0x180006318  lea     eax, [rsi+1]
0x18000631b  mov     dword ptr [rbp+var_38+4], eax
0x18000631e  mov     dword ptr [rbp+var_38+8], eax
0x180006321  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006325  mov     dword ptr [rbp+var_38], 238Dh
0x18000632c  mov     dword ptr [rbp+var_38+0Ch], 2
0x180006333  inc     rax
0x180006336  cmp     [rcx+rax*2], si
0x18000633a  jnz     short loc_180006333
0x18000633c  mov     edx, [rbp+arg_18]
0x18000633f  lea     eax, ds:2[rax*2]
0x180006346  mov     dword ptr [rbp+var_28], eax
0x180006349  lea     r9, [rbp+var_38]
0x18000634d  mov     qword ptr [rbp+var_28+8], rcx
0x180006351  lea     r8, asc_180008770; "/"
0x180006358  mov     rax, [rbx]
0x18000635b  mov     rcx, rbx
0x18000635e  mov     rax, [rax+48h]
0x180006362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006367  test    eax, eax
0x180006369  mov     edi, eax
0x18000636b  cmovns  edi, esi
0x18000636e  mov     edx, [rbp+arg_18]
0x180006371  test    edx, edx
0x180006373  jz      short loc_180006387
0x180006375  mov     rax, [rbx]
0x180006378  mov     rcx, rbx
0x18000637b  mov     rax, [rax+90h]
0x180006382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006387  mov     eax, edi
0x180006389  add     rsp, 78h
0x18000638d  pop     rdi
0x18000638e  pop     rsi
0x18000638f  pop     rbx
0x180006390  pop     rbp
0x180006391  retn
```
