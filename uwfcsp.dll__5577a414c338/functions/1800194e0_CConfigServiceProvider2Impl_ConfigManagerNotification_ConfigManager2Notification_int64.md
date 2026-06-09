# CConfigServiceProvider2Impl::ConfigManagerNotification(ConfigManager2Notification,__int64)

- ea: `0x1800194e0`
- end: `0x18001963f`
- name: `?ConfigManagerNotification@CConfigServiceProvider2Impl@@UEAAJW4ConfigManager2Notification@@_J@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007300`

## callees

- `0x1800194e0`
- `0x18001a0e8`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::ConfigManagerNotification(__int64 a1, int a2, __int64 a3)
{
  unsigned int v3; // ebx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  unsigned int v7; // edx
  int v8; // eax
  unsigned int v9; // edx
  int v10; // eax
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx

  v3 = 0;
  if ( a2 > 5 )
  {
    v11 = a2 - 6;
    if ( !v11 )
    {
      if ( *(_DWORD *)(a1 + 24) == 5 )
      {
        *(_DWORD *)(a1 + 24) = 6;
        return v3;
      }
      return (unsigned int)-2147418113;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      if ( (*(_DWORD *)(a1 + 24) & 0xFFFFFFF9) == 0 && *(_DWORD *)(a1 + 24) != 6 )
      {
        *(_DWORD *)(a1 + 24) = 7;
        return v3;
      }
      return (unsigned int)-2147418113;
    }
    v13 = v12 - 1;
    if ( !v13 )
    {
      if ( *(_DWORD *)(a1 + 24) == 7 )
      {
        *(_DWORD *)(a1 + 24) = 8;
        return v3;
      }
      return (unsigned int)-2147418113;
    }
    v14 = v13 - 1;
    if ( !v14 )
    {
      if ( *(_DWORD *)(a1 + 24) == 1 || *(_DWORD *)(a1 + 24) == 10 )
      {
        *(_DWORD *)(a1 + 24) = 9;
        return v3;
      }
      return (unsigned int)-2147418113;
    }
    if ( v14 == 1 )
    {
      if ( *(_DWORD *)(a1 + 24) == 9 )
      {
        *(_DWORD *)(a1 + 24) = 10;
        return v3;
      }
      return (unsigned int)-2147418113;
    }
    goto LABEL_30;
  }
  if ( a2 == 5 )
  {
    if ( *(_DWORD *)(a1 + 24) == 2 )
    {
      *(_DWORD *)(a1 + 24) = 5;
      return v3;
    }
    return (unsigned int)-2147418113;
  }
  if ( !a2 )
  {
    if ( !*(_DWORD *)(a1 + 24) )
    {
      *(_DWORD *)(a1 + 24) = 0;
      return v3;
    }
    return (unsigned int)-2147418113;
  }
  v4 = a2 - 1;
  if ( !v4 )
  {
    v9 = *(_DWORD *)(a1 + 24);
    if ( v9 <= 8 )
    {
      v10 = 337;
      if ( _bittest(&v10, v9) )
      {
        *(_DWORD *)(a1 + 24) = 1;
        return v3;
      }
    }
    return (unsigned int)-2147418113;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    if ( *(_DWORD *)(a1 + 24) == 1 || *(_DWORD *)(a1 + 24) == 10 )
    {
      *(_DWORD *)(a1 + 24) = 2;
      return v3;
    }
    return (unsigned int)-2147418113;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v7 = *(_DWORD *)(a1 + 24);
    if ( v7 <= 8 )
    {
      v8 = 337;
      if ( _bittest(&v8, v7) )
      {
        *(_DWORD *)(a1 + 24) = 3;
        return v3;
      }
    }
    return (unsigned int)-2147418113;
  }
  if ( v6 != 1 )
  {
LABEL_30:
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return (unsigned int)-2147418113;
  }
  if ( *(_DWORD *)(a1 + 24) )
    return (unsigned int)-2147418113;
  *(_DWORD *)(a1 + 24) = 4;
  if ( a3 )
  {
    *(_QWORD *)(a1 + 16) = a3;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x1800194e0  push    rbx
0x1800194e2  sub     rsp, 20h
0x1800194e6  xor     r9d, r9d
0x1800194e9  mov     ebx, r9d
0x1800194ec  lea     r10d, [r9+5]
0x1800194f0  cmp     edx, r10d
0x1800194f3  jg      loc_1800195BA
0x1800194f9  jz      loc_1800195AE
0x1800194ff  test    edx, edx
0x180019501  jz      loc_1800195A2
0x180019507  sub     edx, 1
0x18001950a  jz      short loc_180019587
0x18001950c  sub     edx, 1
0x18001950f  jz      short loc_180019572
0x180019511  sub     edx, 1
0x180019514  jz      short loc_180019557
0x180019516  cmp     edx, 1
0x180019519  jnz     loc_1800195D3
0x18001951f  cmp     [rcx+18h], r9d
0x180019523  jnz     loc_1800195D8
0x180019529  mov     dword ptr [rcx+18h], 4
0x180019530  test    r8, r8
0x180019533  jz      short loc_18001954D
0x180019535  mov     [rcx+10h], r8
0x180019539  mov     rcx, r8
0x18001953c  mov     rax, [r8]
0x18001953f  mov     rax, [rax+8]
0x180019543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019548  jmp     loc_1800195DD
0x18001954d  mov     ebx, 80070057h
0x180019552  jmp     loc_1800195DD
0x180019557  mov     edx, [rcx+18h]
0x18001955a  cmp     edx, 8
0x18001955d  ja      short loc_1800195D8
0x18001955f  mov     eax, 151h
0x180019564  bt      eax, edx
0x180019567  jnb     short loc_1800195D8
0x180019569  mov     dword ptr [rcx+18h], 3
0x180019570  jmp     short loc_1800195DD
0x180019572  cmp     dword ptr [rcx+18h], 1
0x180019576  jz      short loc_18001957E
0x180019578  cmp     dword ptr [rcx+18h], 0Ah
0x18001957c  jnz     short loc_1800195D8
0x18001957e  mov     dword ptr [rcx+18h], 2
0x180019585  jmp     short loc_1800195DD
0x180019587  mov     edx, [rcx+18h]
0x18001958a  cmp     edx, 8
0x18001958d  ja      short loc_1800195D8
0x18001958f  mov     eax, 151h
0x180019594  bt      eax, edx
0x180019597  jnb     short loc_1800195D8
0x180019599  mov     dword ptr [rcx+18h], 1
0x1800195a0  jmp     short loc_1800195DD
0x1800195a2  cmp     [rcx+18h], r9d
0x1800195a6  jnz     short loc_1800195D8
0x1800195a8  mov     [rcx+18h], r9d
0x1800195ac  jmp     short loc_1800195DD
0x1800195ae  cmp     dword ptr [rcx+18h], 2
0x1800195b2  jnz     short loc_1800195D8
0x1800195b4  mov     [rcx+18h], r10d
0x1800195b8  jmp     short loc_1800195DD
0x1800195ba  sub     edx, 6
0x1800195bd  jz      short loc_180019630
0x1800195bf  sub     edx, 1
0x1800195c2  jz      short loc_180019618
0x1800195c4  sub     edx, 1
0x1800195c7  jz      short loc_180019609
0x1800195c9  sub     edx, 1
0x1800195cc  jz      short loc_1800195F4
0x1800195ce  cmp     edx, 1
0x1800195d1  jz      short loc_1800195E5
0x1800195d3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800195d8  mov     ebx, 8000FFFFh
0x1800195dd  mov     eax, ebx
0x1800195df  add     rsp, 20h
0x1800195e3  pop     rbx
0x1800195e4  retn
0x1800195e5  cmp     dword ptr [rcx+18h], 9
0x1800195e9  jnz     short loc_1800195D8
0x1800195eb  mov     dword ptr [rcx+18h], 0Ah
0x1800195f2  jmp     short loc_1800195DD
0x1800195f4  cmp     dword ptr [rcx+18h], 1
0x1800195f8  jz      short loc_180019600
0x1800195fa  cmp     dword ptr [rcx+18h], 0Ah
0x1800195fe  jnz     short loc_1800195D8
0x180019600  mov     dword ptr [rcx+18h], 9
0x180019607  jmp     short loc_1800195DD
0x180019609  cmp     dword ptr [rcx+18h], 7
0x18001960d  jnz     short loc_1800195D8
0x18001960f  mov     dword ptr [rcx+18h], 8
0x180019616  jmp     short loc_1800195DD
0x180019618  test    dword ptr [rcx+18h], 0FFFFFFF9h
0x18001961f  jnz     short loc_1800195D8
0x180019621  cmp     dword ptr [rcx+18h], 6
0x180019625  jz      short loc_1800195D8
0x180019627  mov     dword ptr [rcx+18h], 7
0x18001962e  jmp     short loc_1800195DD
0x180019630  cmp     [rcx+18h], r10d
0x180019634  jnz     short loc_1800195D8
0x180019636  mov     dword ptr [rcx+18h], 6
0x18001963d  jmp     short loc_1800195DD
```
