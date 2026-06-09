# WamRegGlobal::RecoverApp(ushort const *,int)

- ea: `0x180004fd4`
- end: `0x18000512f`
- name: `?RecoverApp@WamRegGlobal@@QEAAJPEBGH@Z`
- size: `347`
- prototype: `int(WamRegGlobal *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x1800021d0`

## callees

- `0x180004948`
- `0x180004fd4`
- `0x180005a50`
- `0x180007010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180005117`
- `iisutil!PuDbgPrint` at `0x180005117`

## string_xrefs

- `0x1800050ee`: `Failed to remove MD_APP_STATE from path %S, hr = %08x\n`

## pseudocode

```c
__int64 __fastcall WamRegGlobal::RecoverApp(WamRegGlobal *this, const unsigned __int16 *a2, __int64 a3)
{
  int v4; // eax
  WamRegGlobal *v5; // rcx
  int PooledApp; // ebx
  int v7; // r9d
  int v8; // r8d
  int v9; // esi
  unsigned int v11; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+54h] [rbp+Ch]
  unsigned int v13; // [rsp+60h] [rbp+18h] BYREF

  v13 = a3;
  v12 = HIDWORD(this);
  v11 = 0;
  v4 = WamRegMetabaseConfig::MDGetDWORD(this, a2, a3, &v11);
  PooledApp = v4;
  if ( v4 == -2146646015 )
    return 0;
  if ( v4 < 0 )
    return (unsigned int)PooledApp;
  if ( v11 == 2 )
  {
    v7 = 0;
LABEL_9:
    v8 = 0;
    goto LABEL_10;
  }
  if ( v11 )
  {
    v7 = 1;
    goto LABEL_9;
  }
  v7 = 0;
  v8 = 1;
LABEL_10:
  PooledApp = WamRegGlobal::CreatePooledApp(v5, a2, v8, v7);
  if ( PooledApp >= 0 )
  {
    v13 = 0;
    v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const unsigned __int16 *, __int64, int, unsigned int *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 136LL))(
           WamRegMetabaseConfig::m_pMetabase,
           0,
           a2,
           2,
           30000,
           &v13);
    if ( v9 < 0
      || (v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int64, int))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase
                                                                               + 88LL))(
                 WamRegMetabaseConfig::m_pMetabase,
                 v13,
                 0,
                 2109,
                 1),
          (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 144LL))(
            WamRegMetabaseConfig::m_pMetabase,
            v13),
          v9 < 0) )
    {
      if ( v9 != -2146646015 && (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfunc.cpp",
          1343,
          "WamRegGlobal::RecoverApp",
          "Failed to remove MD_APP_STATE from path %S, hr = %08x\n",
          a2,
          v9);
    }
  }
  return (unsigned int)PooledApp;
}

```

## disassembly

```asm
0x180004fd4  mov     rax, rsp
0x180004fd7  mov     [rax+10h], rbx
0x180004fdb  mov     [rax+20h], rsi
0x180004fdf  mov     [rax+18h], r8d
0x180004fe3  mov     [rax+8], rcx
0x180004fe7  push    rdi
0x180004fe8  sub     rsp, 40h
0x180004fec  lea     r9, [rax+8]; unsigned int *
0x180004ff0  mov     dword ptr [rax+8], 0
0x180004ff7  mov     rdi, rdx
0x180004ffa  call    ?MDGetDWORD@WamRegMetabaseConfig@@QEAAJPEBGKPEAK@Z; WamRegMetabaseConfig::MDGetDWORD(ushort const *,ulong,ulong *)
0x180004fff  mov     ebx, eax
0x180005001  cmp     eax, 800CC801h
0x180005006  jnz     short loc_18000500F
0x180005008  xor     ebx, ebx
0x18000500a  jmp     loc_18000511D
0x18000500f  test    eax, eax
0x180005011  js      loc_18000511D
0x180005017  mov     eax, [rsp+48h+arg_0]
0x18000501b  cmp     eax, 2
0x18000501e  jnz     short loc_180005025
0x180005020  xor     r9d, r9d
0x180005023  jmp     short loc_180005038
0x180005025  test    eax, eax
0x180005027  jnz     short loc_180005032
0x180005029  xor     r9d, r9d
0x18000502c  lea     r8d, [rax+1]
0x180005030  jmp     short loc_18000503B
0x180005032  mov     r9d, 1; int
0x180005038  xor     r8d, r8d; int
0x18000503b  mov     rdx, rdi; unsigned __int16 *
0x18000503e  call    ?CreatePooledApp@WamRegGlobal@@QEAAJPEBGHH@Z; WamRegGlobal::CreatePooledApp(ushort const *,int,int)
0x180005043  mov     ebx, eax
0x180005045  test    eax, eax
0x180005047  js      loc_18000511D
0x18000504d  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180005054  lea     rdx, [rsp+48h+arg_10]
0x180005059  mov     [rsp+48h+var_20], rdx
0x18000505e  mov     r9d, 2
0x180005064  mov     [rsp+48h+arg_10], 0
0x18000506c  mov     r8, rdi
0x18000506f  xor     edx, edx
0x180005071  mov     dword ptr [rsp+48h+var_28], 7530h
0x180005079  mov     rax, [rcx]
0x18000507c  mov     rax, [rax+88h]
0x180005083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005088  mov     esi, eax
0x18000508a  test    eax, eax
0x18000508c  js      short loc_1800050D6
0x18000508e  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180005095  mov     r9d, 83Dh
0x18000509b  mov     edx, [rsp+48h+arg_10]
0x18000509f  xor     r8d, r8d
0x1800050a2  mov     dword ptr [rsp+48h+var_28], 1
0x1800050aa  mov     rax, [rcx]
0x1800050ad  mov     rax, [rax+58h]
0x1800050b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050b6  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x1800050bd  mov     esi, eax
0x1800050bf  mov     edx, [rsp+48h+arg_10]
0x1800050c3  mov     rax, [rcx]
0x1800050c6  mov     rax, [rax+90h]
0x1800050cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050d2  test    esi, esi
0x1800050d4  jns     short loc_18000511D
0x1800050d6  cmp     esi, 800CC801h
0x1800050dc  jz      short loc_18000511D
0x1800050de  test    byte ptr cs:g_dwDebugFlags, 3
0x1800050e5  jz      short loc_18000511D
0x1800050e7  mov     rcx, cs:g_pDebug
0x1800050ee  lea     rax, aFailedToRemove; "Failed to remove MD_APP_STATE from path"...
0x1800050f5  mov     [rsp+48h+var_18], esi
0x1800050f9  lea     r9, aWamregglobalRe; "WamRegGlobal::RecoverApp"
0x180005100  mov     [rsp+48h+var_20], rdi
0x180005105  lea     rdx, aInetsrvIisSvcs; "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfun"...
0x18000510c  mov     r8d, 53Fh
0x180005112  mov     [rsp+48h+var_28], rax
0x180005117  call    cs:__imp_PuDbgPrint
0x18000511d  mov     rsi, [rsp+48h+arg_18]
0x180005122  mov     eax, ebx
0x180005124  mov     rbx, [rsp+48h+arg_8]
0x180005129  add     rsp, 40h
0x18000512d  pop     rdi
0x18000512e  retn
```
