# WamRegMetabaseConfig::MDGetIDs(ushort const *,ushort *,ushort *,ulong)

- ea: `0x180005b90`
- end: `0x180005cf4`
- name: `?MDGetIDs@WamRegMetabaseConfig@@QEAAJPEBGPEAG1K@Z`
- size: `356`
- prototype: `__int64 __fastcall(WamRegMetabaseConfig *this, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003d80`
- `0x180004acc`
- `0x180005584`

## callees

- `0x180005b90`
- `0x180007010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180005cc3`
- `msvcrt!wcscpy_s` at `0x180005cc3`

## pseudocode

```c
__int64 __fastcall WamRegMetabaseConfig::MDGetIDs(
        WamRegMetabaseConfig *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  int v7; // ebx
  const wchar_t *v8; // r8
  __int128 v10; // [rsp+40h] [rbp-30h] BYREF
  __int128 v11; // [rsp+50h] [rbp-20h]
  __int64 v12; // [rsp+60h] [rbp-10h]
  unsigned int v13; // [rsp+90h] [rbp+20h] BYREF
  int v14; // [rsp+94h] [rbp+24h]
  int v15; // [rsp+A0h] [rbp+30h] BYREF

  v14 = HIDWORD(this);
  v13 = 0;
  *a4 = 0;
  *a3 = 0;
  v12 = 0;
  v15 = 0;
  v10 = 0;
  v11 = 0;
  v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const unsigned __int16 *, __int64, int, unsigned int *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 136LL))(
         WamRegMetabaseConfig::m_pMetabase,
         0,
         a2,
         1,
         30000,
         &v13);
  if ( v7 >= 0 )
  {
    *(_QWORD *)&v10 = 2105;
    *((_QWORD *)&v10 + 1) = 0x200000064LL;
    LODWORD(v11) = 78;
    *((_QWORD *)&v11 + 1) = a3;
    v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int128 *, int *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase
                                                                              + 80LL))(
           WamRegMetabaseConfig::m_pMetabase,
           v13,
           0,
           &v10,
           &v15);
    if ( v7 >= 0 )
    {
      if ( a5 == 1 )
      {
        *(_QWORD *)&v10 = 2106;
        *((_QWORD *)&v10 + 1) = 0x200000064LL;
        LODWORD(v11) = 78;
        *((_QWORD *)&v11 + 1) = a4;
        v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int128 *, int *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase
                                                                                  + 80LL))(
               WamRegMetabaseConfig::m_pMetabase,
               v13,
               0,
               &v10,
               &v15);
      }
      else
      {
        v8 = L"{3D14228C-FBE1-11d0-995D-00C04FD919C1}";
        if ( a5 )
          v8 = L"{3D14228D-FBE1-11d0-995D-00C04FD919C1}";
        wcscpy_s(a4, 0x27u, v8);
      }
    }
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 144LL))(
      WamRegMetabaseConfig::m_pMetabase,
      v13);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180005b90  mov     [rsp-18h+arg_8], rbx
0x180005b95  mov     [rsp-18h+arg_0], rcx
0x180005b9a  push    rbp
0x180005b9b  push    rsi
0x180005b9c  push    rdi
0x180005b9d  mov     rbp, rsp
0x180005ba0  sub     rsp, 70h
0x180005ba4  xor     eax, eax
0x180005ba6  mov     dword ptr [rbp+arg_0], 0
0x180005bad  mov     [r9], ax
0x180005bb1  xorps   xmm0, xmm0
0x180005bb4  mov     [r8], ax
0x180005bb8  mov     rsi, r8
0x180005bbb  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180005bc2  lea     r8, [rbp+arg_0]
0x180005bc6  mov     [rbp+var_10], rax
0x180005bca  mov     rdi, r9
0x180005bcd  mov     [rbp+arg_10], eax
0x180005bd0  mov     r9d, 1
0x180005bd6  mov     [rsp+70h+var_48], r8
0x180005bdb  mov     r8, rdx
0x180005bde  movups  [rbp+var_30], xmm0
0x180005be2  xor     edx, edx
0x180005be4  mov     dword ptr [rsp+70h+var_50], 7530h
0x180005bec  movups  [rbp+var_20], xmm0
0x180005bf0  mov     rax, [rcx]
0x180005bf3  mov     rax, [rax+88h]
0x180005bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bff  mov     ebx, eax
0x180005c01  test    eax, eax
0x180005c03  js      loc_180005CE2
0x180005c09  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180005c10  lea     rdx, [rbp+arg_10]
0x180005c14  mov     qword ptr [rbp+var_30], 839h
0x180005c1c  lea     r9, [rbp+var_30]
0x180005c20  mov     dword ptr [rbp+var_30+8], 64h ; 'd'
0x180005c27  xor     r8d, r8d
0x180005c2a  mov     dword ptr [rbp+var_30+0Ch], 2
0x180005c31  mov     dword ptr [rbp+var_20], 4Eh ; 'N'
0x180005c38  mov     qword ptr [rbp+var_20+8], rsi
0x180005c3c  mov     rax, [rcx]
0x180005c3f  mov     [rsp+70h+var_50], rdx
0x180005c44  mov     edx, dword ptr [rbp+arg_0]
0x180005c47  mov     rax, [rax+50h]
0x180005c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c50  mov     ebx, eax
0x180005c52  test    eax, eax
0x180005c54  js      short loc_180005CC9
0x180005c56  mov     eax, [rbp+arg_20]
0x180005c59  cmp     eax, 1
0x180005c5c  jnz     short loc_180005CA9
0x180005c5e  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180005c65  lea     rdx, [rbp+arg_10]
0x180005c69  mov     qword ptr [rbp+var_30], 83Ah
0x180005c71  lea     r9, [rbp+var_30]
0x180005c75  mov     dword ptr [rbp+var_30+8], 64h ; 'd'
0x180005c7c  xor     r8d, r8d
0x180005c7f  mov     dword ptr [rbp+var_30+0Ch], 2
0x180005c86  mov     dword ptr [rbp+var_20], 4Eh ; 'N'
0x180005c8d  mov     qword ptr [rbp+var_20+8], rdi
0x180005c91  mov     rax, [rcx]
0x180005c94  mov     [rsp+70h+var_50], rdx
0x180005c99  mov     edx, dword ptr [rbp+arg_0]
0x180005c9c  mov     rax, [rax+50h]
0x180005ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ca5  mov     ebx, eax
0x180005ca7  jmp     short loc_180005CC9
0x180005ca9  lea     r8, ?g_szIISInProcPackageID@WamRegGlobal@@2QBGB; "{3D14228C-FBE1-11d0-995D-00C04FD919C1}"
0x180005cb0  mov     edx, 27h ; '''; SizeInWords
0x180005cb5  mov     rcx, rdi; Destination
0x180005cb8  test    eax, eax
0x180005cba  jz      short loc_180005CC3
0x180005cbc  lea     r8, ?g_szIISOOPPoolPackageID@WamRegGlobal@@2QBGB; "{3D14228D-FBE1-11d0-995D-00C04FD919C1}"
0x180005cc3  call    cs:__imp_wcscpy_s
0x180005cc9  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180005cd0  mov     edx, dword ptr [rbp+arg_0]
0x180005cd3  mov     rax, [rcx]
0x180005cd6  mov     rax, [rax+90h]
0x180005cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ce2  mov     eax, ebx
0x180005ce4  mov     rbx, [rsp+70h+arg_8]
0x180005cec  add     rsp, 70h
0x180005cf0  pop     rdi
0x180005cf1  pop     rsi
0x180005cf2  pop     rbp
0x180005cf3  retn
```
