# WamRegMetabaseConfig::MDSetKeyType(IMSAdminBaseW *,ushort const *,ushort const *)

- ea: `0x1800061d0`
- end: `0x1800062af`
- name: `?MDSetKeyType@WamRegMetabaseConfig@@QEAAJPEAUIMSAdminBaseW@@PEBG1@Z`
- size: `223`
- prototype: `__int64 __fastcall(WamRegMetabaseConfig *__hidden this, struct IMSAdminBaseW *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002850`

## callees

- `0x1800061d0`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall WamRegMetabaseConfig::MDSetKeyType(
        WamRegMetabaseConfig *this,
        struct IMSAdminBaseW *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  LPVOID v4; // rdi
  int v5; // ebx
  __int128 v7; // [rsp+40h] [rbp-30h] BYREF
  __int128 v8; // [rsp+50h] [rbp-20h]
  __int64 v9; // [rsp+60h] [rbp-10h]
  unsigned int v10; // [rsp+98h] [rbp+28h] BYREF
  int v11; // [rsp+9Ch] [rbp+2Ch]

  v11 = HIDWORD(a4);
  v4 = WamRegMetabaseConfig::m_pMetabase;
  v9 = 0;
  v10 = 0;
  v7 = 0;
  v8 = 0;
  v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const unsigned __int16 *, __int64, int, unsigned int *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 136LL))(
         WamRegMetabaseConfig::m_pMetabase,
         0,
         a3,
         2,
         30000,
         &v10);
  if ( v5 >= 0 )
  {
    *((_QWORD *)&v8 + 1) = L"IIsApplicationPool";
    *(_QWORD *)&v7 = 1002;
    *((_QWORD *)&v7 + 1) = 0x200000001LL;
    LODWORD(v8) = 38;
    v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const wchar_t *, __int128 *))(*(_QWORD *)v4 + 72LL))(
           v4,
           v10,
           L"/",
           &v7);
    if ( v5 >= 0 )
      v5 = 0;
  }
  if ( v10 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 144LL))(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800061d0  mov     r11, rsp
0x1800061d3  mov     [r11+8], rbx
0x1800061d7  mov     [r11+10h], rdi
0x1800061db  mov     [r11+20h], r9
0x1800061df  push    rbp
0x1800061e0  mov     rbp, rsp
0x1800061e3  sub     rsp, 70h
0x1800061e7  mov     rdi, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x1800061ee  lea     rcx, [rbp+arg_18]
0x1800061f2  xor     eax, eax
0x1800061f4  mov     [r11-50h], rcx
0x1800061f8  xorps   xmm0, xmm0
0x1800061fb  mov     [rbp+var_10], rax
0x1800061ff  mov     [rbp+arg_18], 0
0x180006206  xor     edx, edx
0x180006208  movups  [rbp+var_30], xmm0
0x18000620c  mov     rcx, rdi
0x18000620f  mov     [rsp+70h+var_50], 7530h
0x180006217  movups  [rbp+var_20], xmm0
0x18000621b  mov     rax, [rdi]
0x18000621e  lea     r9d, [rdx+2]
0x180006222  mov     rax, [rax+88h]
0x180006229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000622e  mov     ebx, eax
0x180006230  test    eax, eax
0x180006232  js      short loc_180006282
0x180006234  mov     edx, [rbp+arg_18]
0x180006237  lea     rax, aIisapplication; "IIsApplicationPool"
0x18000623e  mov     qword ptr [rbp+var_20+8], rax
0x180006242  lea     r9, [rbp+var_30]
0x180006246  mov     qword ptr [rbp+var_30], 3EAh
0x18000624e  lea     r8, asc_180008770; "/"
0x180006255  mov     dword ptr [rbp+var_30+8], 1
0x18000625c  mov     rcx, rdi
0x18000625f  mov     dword ptr [rbp+var_30+0Ch], 2
0x180006266  mov     dword ptr [rbp+var_20], 26h ; '&'
0x18000626d  mov     rax, [rdi]
0x180006270  mov     rax, [rax+48h]
0x180006274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006279  mov     ebx, eax
0x18000627b  xor     eax, eax
0x18000627d  test    ebx, ebx
0x18000627f  cmovns  ebx, eax
0x180006282  mov     edx, [rbp+arg_18]
0x180006285  test    edx, edx
0x180006287  jz      short loc_18000629B
0x180006289  mov     rax, [rdi]
0x18000628c  mov     rcx, rdi
0x18000628f  mov     rax, [rax+90h]
0x180006296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000629b  lea     r11, [rsp+70h+var_s0]
0x1800062a0  mov     eax, ebx
0x1800062a2  mov     rbx, [r11+10h]
0x1800062a6  mov     rdi, [r11+18h]
0x1800062aa  mov     rsp, r11
0x1800062ad  pop     rbp
0x1800062ae  retn
```
