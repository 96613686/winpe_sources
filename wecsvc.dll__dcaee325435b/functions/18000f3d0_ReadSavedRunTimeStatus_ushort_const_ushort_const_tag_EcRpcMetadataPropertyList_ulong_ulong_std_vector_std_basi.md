# ReadSavedRunTimeStatus(ushort const *,ushort const *,tag_EcRpcMetadataPropertyList &,ulong,ulong,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *,ulong)

- ea: `0x18000f3d0`
- end: `0x18000f5e2`
- name: `?ReadSavedRunTimeStatus@@YAXPEBG0AEAUtag_EcRpcMetadataPropertyList@@KKPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@K@Z`
- size: `530`
- prototype: `void __fastcall(__int64, __int64, struct tag_EcRpcMetadataPropertyList *, __int64, unsigned int, _QWORD *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18000d830`
- `0x18000d940`

## callees

- `0x180003e6c`
- `0x1800062d4`
- `0x18000ef44`
- `0x18000f3d0`
- `0x18000ff3c`
- `0x180012424`
- `0x18001274c`
- `0x1800128c0`
- `0x18001fe50`

## import_xrefs

- `msvcrt!wcstol` at `0x18000f4f8`
- `msvcrt!wcstol` at `0x18000f4f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000f536`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000f536`

## pseudocode

```c
void __fastcall ReadSavedRunTimeStatus(
        __int64 a1,
        __int64 a2,
        struct tag_EcRpcMetadataPropertyList *a3,
        __int64 a4,
        unsigned int a5,
        _QWORD *a6,
        unsigned int a7)
{
  HKEY v8; // rbx
  enum _EC_SUBSCRIPTION_RUNTIME_STATUS_ACTIVE_STATUS v9; // edx
  unsigned __int64 i; // rbx
  __int64 v11; // rcx
  int v12; // eax
  const unsigned __int16 *v13; // r9
  unsigned int v14; // [rsp+40h] [rbp-31h] BYREF
  unsigned int v15; // [rsp+44h] [rbp-2Dh] BYREF
  unsigned int v16; // [rsp+48h] [rbp-29h] BYREF
  unsigned __int64 v17; // [rsp+50h] [rbp-21h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-19h] BYREF
  unsigned __int64 v19; // [rsp+60h] [rbp-11h] BYREF
  HKEY v20; // [rsp+68h] [rbp-9h] BYREF
  unsigned __int16 *v21[2]; // [rsp+70h] [rbp-1h] BYREF
  __int64 v22; // [rsp+80h] [rbp+Fh]
  unsigned __int64 v23; // [rsp+88h] [rbp+17h]

  v8 = OpenSubscriptionEventSourceKey(a1, a2, 0x20019u, 0);
  v20 = v8;
  v14 = 0;
  v23 = 7;
  v22 = 0;
  LOWORD(v21[0]) = 0;
  v19 = 0;
  v17 = 0;
  v15 = 1;
  v16 = 0;
  RegReadDWORDValue(v8, L"enabled", &v15);
  RegReadDWORDValue(v8, L"LastErrorCount", &v16);
  RegReadDWORDValue(v8, L"LastError", &v14);
  RegReadStringValue(v8, L"LastFaultMessage", v21);
  RegReadQWORDValue(v8, L"LastErrorTime", &v19);
  RegReadQWORDValue(v8, L"LastHeartbeatTime", &v17);
  if ( v15 )
  {
    if ( v14 )
    {
      if ( a6 )
      {
        for ( i = 0; i < (__int64)(a6[1] - *a6) >> 5; ++i )
        {
          v11 = 32 * i + *a6;
          if ( *(_QWORD *)(v11 + 24) >= 8u )
            v11 = *(_QWORD *)v11;
          v12 = wcstol((const wchar_t *)v11, 0, 0);
          if ( v14 == v12 )
            goto LABEL_12;
        }
      }
      v9 = EcRuntimeStatusActiveStatusActive;
      if ( v16 >= a7 )
LABEL_12:
        v9 = EcRuntimeStatusActiveStatusInactive;
    }
    else if ( !a5
           || !v17
           || (SystemTimeAsFileTime = 0,
               GetSystemTimeAsFileTime(&SystemTimeAsFileTime),
               v17 > *(_QWORD *)&SystemTimeAsFileTime)
           || (v9 = EcRuntimeStatusActiveStatusInactive,
               *(_QWORD *)&SystemTimeAsFileTime - v17 < 10000 * (unsigned __int64)a5) )
    {
      v9 = EcRuntimeStatusActiveStatusActive;
    }
  }
  else
  {
    v9 = EcRuntimeStatusActiveStatusDisabled;
  }
  if ( v22 )
  {
    v13 = (const unsigned __int16 *)v21;
    if ( v23 >= 8 )
      v13 = v21[0];
  }
  else
  {
    v13 = 0;
  }
  SetRunTimeStatus(a3, v9, v14, v13, v19, 0, v17);
  std::wstring::_Tidy(v21, 1, 0);
  wmi::AutoRegKey::Close(&v20);
}

```

## disassembly

```asm
0x18000f3d0  mov     [rsp-8+arg_18], rbx
0x18000f3d5  push    rbp
0x18000f3d6  push    rsi
0x18000f3d7  push    rdi
0x18000f3d8  lea     rbp, [rsp-2Fh]
0x18000f3dd  sub     rsp, 0A0h
0x18000f3e4  mov     rax, cs:__security_cookie
0x18000f3eb  xor     rax, rsp
0x18000f3ee  mov     [rbp+3Fh+var_20], rax
0x18000f3f2  mov     rsi, r8
0x18000f3f5  mov     rdi, [rbp+3Fh+arg_28]
0x18000f3f9  xor     r9d, r9d
0x18000f3fc  mov     r8d, 20019h
0x18000f402  call    OpenSubscriptionEventSourceKey
0x18000f407  mov     rbx, rax
0x18000f40a  mov     [rbp+3Fh+var_48], rax
0x18000f40e  mov     [rbp+3Fh+var_70], 0
0x18000f415  mov     [rbp+3Fh+var_28], 7
0x18000f41d  mov     [rbp+3Fh+var_30], 0
0x18000f425  xor     eax, eax
0x18000f427  mov     word ptr [rbp+3Fh+var_40], ax
0x18000f42b  mov     [rbp+3Fh+var_50], rax
0x18000f42f  mov     [rbp+3Fh+var_60], rax
0x18000f433  mov     [rbp+3Fh+var_6C], 1
0x18000f43a  mov     [rbp+3Fh+var_68], eax
0x18000f43d  lea     r8, [rbp+3Fh+var_6C]; unsigned int *
0x18000f441  lea     rdx, aEnabled_0; "enabled"
0x18000f448  mov     rcx, rbx; HKEY
0x18000f44b  call    ?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z; RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)
0x18000f450  lea     r8, [rbp+3Fh+var_68]; unsigned int *
0x18000f454  lea     rdx, aLasterrorcount; "LastErrorCount"
0x18000f45b  mov     rcx, rbx; HKEY
0x18000f45e  call    ?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z; RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)
0x18000f463  lea     r8, [rbp+3Fh+var_70]; unsigned int *
0x18000f467  lea     rdx, aLasterror; "LastError"
0x18000f46e  mov     rcx, rbx; HKEY
0x18000f471  call    ?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z; RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)
0x18000f476  lea     r8, [rbp+3Fh+var_40]
0x18000f47a  lea     rdx, aLastfaultmessa; "LastFaultMessage"
0x18000f481  mov     rcx, rbx
0x18000f484  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x18000f489  lea     r8, [rbp+3Fh+var_50]; unsigned __int64 *
0x18000f48d  lea     rdx, aLasterrortime; "LastErrorTime"
0x18000f494  mov     rcx, rbx; HKEY
0x18000f497  call    ?RegReadQWORDValue@@YA_NPEAUHKEY__@@PEBGAEA_K@Z; RegReadQWORDValue(HKEY__ *,ushort const *,unsigned __int64 &)
0x18000f49c  lea     r8, [rbp+3Fh+var_60]; unsigned __int64 *
0x18000f4a0  lea     rdx, aLastheartbeatt; "LastHeartbeatTime"
0x18000f4a7  mov     rcx, rbx; HKEY
0x18000f4aa  call    ?RegReadQWORDValue@@YA_NPEAUHKEY__@@PEBGAEA_K@Z; RegReadQWORDValue(HKEY__ *,ushort const *,unsigned __int64 &)
0x18000f4af  cmp     [rbp+3Fh+var_6C], 0
0x18000f4b3  jnz     short loc_18000F4BF
0x18000f4b5  mov     edx, 1
0x18000f4ba  jmp     loc_18000F569
0x18000f4bf  cmp     [rbp+3Fh+var_70], 0
0x18000f4c3  jz      short loc_18000F51C
0x18000f4c5  test    rdi, rdi
0x18000f4c8  jz      short loc_18000F508
0x18000f4ca  xor     ebx, ebx
0x18000f4cc  mov     rcx, [rdi]
0x18000f4cf  mov     rax, [rdi+8]
0x18000f4d3  sub     rax, rcx
0x18000f4d6  sar     rax, 5
0x18000f4da  cmp     rbx, rax
0x18000f4dd  jnb     short loc_18000F508
0x18000f4df  mov     rax, rbx
0x18000f4e2  shl     rax, 5
0x18000f4e6  add     rcx, rax
0x18000f4e9  cmp     qword ptr [rcx+18h], 8
0x18000f4ee  jb      short loc_18000F4F3
0x18000f4f0  mov     rcx, [rcx]; String
0x18000f4f3  xor     r8d, r8d; Radix
0x18000f4f6  xor     edx, edx; EndPtr
0x18000f4f8  call    cs:__imp_wcstol
0x18000f4fe  cmp     [rbp+3Fh+var_70], eax
0x18000f501  jz      short loc_18000F515
0x18000f503  inc     rbx
0x18000f506  jmp     short loc_18000F4CC
0x18000f508  mov     edx, 2
0x18000f50d  mov     eax, [rbp+3Fh+arg_30]
0x18000f510  cmp     [rbp+3Fh+var_68], eax
0x18000f513  jb      short loc_18000F569
0x18000f515  mov     edx, 3
0x18000f51a  jmp     short loc_18000F569
0x18000f51c  mov     ebx, [rbp+3Fh+arg_20]
0x18000f51f  test    ebx, ebx
0x18000f521  jz      short loc_18000F564
0x18000f523  cmp     [rbp+3Fh+var_60], 0
0x18000f528  jz      short loc_18000F564
0x18000f52a  mov     qword ptr [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000f532  lea     rcx, [rbp+3Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000f536  call    cs:__imp_GetSystemTimeAsFileTime
0x18000f53c  mov     edx, [rbp+3Fh+SystemTimeAsFileTime.dwHighDateTime]
0x18000f53f  shl     rdx, 20h
0x18000f543  mov     eax, [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime]
0x18000f546  or      rdx, rax
0x18000f549  cmp     [rbp+3Fh+var_60], rdx
0x18000f54d  ja      short loc_18000F564
0x18000f54f  sub     rdx, [rbp+3Fh+var_60]
0x18000f553  imul    rcx, rbx, 2710h
0x18000f55a  cmp     rdx, rcx
0x18000f55d  mov     edx, 3
0x18000f562  jnb     short loc_18000F569
0x18000f564  mov     edx, 2; enum _EC_SUBSCRIPTION_RUNTIME_STATUS_ACTIVE_STATUS
0x18000f569  mov     rax, [rbp+3Fh+var_60]
0x18000f56d  mov     rcx, [rbp+3Fh+var_50]
0x18000f571  cmp     [rbp+3Fh+var_30], 0
0x18000f576  jnz     short loc_18000F57D
0x18000f578  xor     r9d, r9d
0x18000f57b  jmp     short loc_18000F58B
0x18000f57d  lea     r9, [rbp+3Fh+var_40]
0x18000f581  cmp     [rbp+3Fh+var_28], 8
0x18000f586  cmovnb  r9, [rbp+3Fh+var_40]; unsigned __int16 *
0x18000f58b  mov     [rsp+0B0h+var_80], rax; unsigned __int64
0x18000f590  mov     [rsp+0B0h+var_88], 0; unsigned __int64
0x18000f599  mov     [rsp+0B0h+var_90], rcx; unsigned __int64
0x18000f59e  mov     r8d, [rbp+3Fh+var_70]; unsigned int
0x18000f5a2  mov     rcx, rsi; struct tag_EcRpcMetadataPropertyList *
0x18000f5a5  call    ?SetRunTimeStatus@@YAXAEAUtag_EcRpcMetadataPropertyList@@W4_EC_SUBSCRIPTION_RUNTIME_STATUS_ACTIVE_STATUS@@KPEBG_K33@Z; SetRunTimeStatus(tag_EcRpcMetadataPropertyList &,_EC_SUBSCRIPTION_RUNTIME_STATUS_ACTIVE_STATUS,ulong,ushort const *,unsigned __int64,unsigned __int64,unsigned __int64)
0x18000f5aa  nop
0x18000f5ab  xor     r8d, r8d
0x18000f5ae  mov     dl, 1
0x18000f5b0  lea     rcx, [rbp+3Fh+var_40]
0x18000f5b4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f5b9  nop
0x18000f5ba  lea     rcx, [rbp+3Fh+var_48]; this
0x18000f5be  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18000f5c3  mov     rcx, [rbp+3Fh+var_20]
0x18000f5c7  xor     rcx, rsp; StackCookie
0x18000f5ca  call    __security_check_cookie
0x18000f5cf  mov     rbx, [rsp+0B0h+arg_18]
0x18000f5d7  add     rsp, 0A0h
0x18000f5de  pop     rdi
0x18000f5df  pop     rsi
0x18000f5e0  pop     rbp
0x18000f5e1  retn
```
