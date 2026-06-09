# WamRegMetabaseConfig::MDSetAppState(ushort const *,ulong)

- ea: `0x1800060f4`
- end: `0x1800061c9`
- name: `?MDSetAppState@WamRegMetabaseConfig@@QEAAJPEBGK@Z`
- size: `213`
- prototype: `__int64 __fastcall(WamRegMetabaseConfig *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180004acc`

## callees

- `0x1800060f4`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall WamRegMetabaseConfig::MDSetAppState(WamRegMetabaseConfig *this, const unsigned __int16 *a2)
{
  int v2; // ebx
  int v4; // [rsp+40h] [rbp-30h] BYREF
  __int128 v5; // [rsp+48h] [rbp-28h] BYREF
  __int128 v6; // [rsp+58h] [rbp-18h]
  __int64 v7; // [rsp+68h] [rbp-8h]
  unsigned int v8; // [rsp+90h] [rbp+20h] BYREF

  v7 = 0;
  v8 = 0;
  v4 = 6;
  v5 = 0;
  v6 = 0;
  v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const unsigned __int16 *, __int64, int, unsigned int *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 136LL))(
         WamRegMetabaseConfig::m_pMetabase,
         0,
         a2,
         2,
         30000,
         &v8);
  if ( v2 >= 0 )
  {
    *((_QWORD *)&v6 + 1) = &v4;
    *(_QWORD *)&v5 = 0x10000083DLL;
    *((_QWORD *)&v5 + 1) = 0x100000064LL;
    LODWORD(v6) = 4;
    v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int128 *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase
                                                                       + 72LL))(
           WamRegMetabaseConfig::m_pMetabase,
           v8,
           0,
           &v5);
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 144LL))(
      WamRegMetabaseConfig::m_pMetabase,
      v8);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800060f4  mov     [rsp-8+arg_0], rbx
0x1800060f9  mov     [rsp-8+arg_10], r8d
0x1800060fe  push    rbp
0x1800060ff  mov     rbp, rsp
0x180006102  sub     rsp, 70h
0x180006106  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x18000610d  lea     r8, [rbp+arg_10]
0x180006111  xor     eax, eax
0x180006113  mov     [rsp+70h+var_48], r8
0x180006118  xorps   xmm0, xmm0
0x18000611b  mov     [rbp+var_8], rax
0x18000611f  mov     [rbp+arg_10], eax
0x180006122  mov     r8, rdx
0x180006125  mov     [rbp+var_30], 6
0x18000612c  mov     r9d, 2
0x180006132  movups  [rbp+var_28], xmm0
0x180006136  xor     edx, edx
0x180006138  mov     [rsp+70h+var_50], 7530h
0x180006140  movups  [rbp+var_18], xmm0
0x180006144  mov     rax, [rcx]
0x180006147  mov     rax, [rax+88h]
0x18000614e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006153  mov     ebx, eax
0x180006155  test    eax, eax
0x180006157  js      short loc_1800061B9
0x180006159  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180006160  lea     r9, [rbp+var_28]
0x180006164  mov     edx, [rbp+arg_10]
0x180006167  mov     eax, 1
0x18000616c  mov     dword ptr [rbp+var_28+4], eax
0x18000616f  xor     r8d, r8d
0x180006172  mov     dword ptr [rbp+var_28+0Ch], eax
0x180006175  lea     rax, [rbp+var_30]
0x180006179  mov     qword ptr [rbp+var_18+8], rax
0x18000617d  mov     dword ptr [rbp+var_28], 83Dh
0x180006184  mov     dword ptr [rbp+var_28+8], 64h ; 'd'
0x18000618b  mov     dword ptr [rbp+var_18], 4
0x180006192  mov     rax, [rcx]
0x180006195  mov     rax, [rax+48h]
0x180006199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000619e  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x1800061a5  mov     ebx, eax
0x1800061a7  mov     edx, [rbp+arg_10]
0x1800061aa  mov     rax, [rcx]
0x1800061ad  mov     rax, [rax+90h]
0x1800061b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061b9  mov     eax, ebx
0x1800061bb  mov     rbx, [rsp+70h+arg_0]
0x1800061c3  add     rsp, 70h
0x1800061c7  pop     rbp
0x1800061c8  retn
```
