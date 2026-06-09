# CommsESE_JetMove(unsigned __int64,unsigned __int64,long,ulong)

- ea: `0x180002880`
- end: `0x1800029d6`
- name: `?CommsESE_JetMove@@YAJ_K0JK@Z`
- size: `342`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, int, unsigned int)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180002344`
- `0x180002698`
- `0x1800115a0`
- `0x180012628`

## callees

- `0x180002880`
- `0x1800068f0`
- `0x180045990`
- `0x180067c1c`
- `0x18006f180`
- `0x18007d4e4`
- `0x18007d540`
- `0x18007d59c`
- `0x1800c50aa`
- `0x1800c50f0`

## import_xrefs

- `ESENT!JetMove` at `0x1800028a3`
- `ESENT!JetMove` at `0x1800028a3`
- `ESENT!JetGetErrorInfoW` at `0x180002900`
- `ESENT!JetGetErrorInfoW` at `0x180002900`

## string_xrefs

- `0x18000298d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800029c3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall CommsESE_JetMove(JET_SESID a1, JET_TABLEID a2, int a3)
{
  JET_ERR v3; // eax
  unsigned int v4; // ebx
  int v6; // eax
  __int64 v7; // rcx
  unsigned int v8; // [rsp+30h] [rbp-69h] BYREF
  JET_ERR v9; // [rsp+38h] [rbp-61h] BYREF
  int v10; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v11[4]; // [rsp+44h] [rbp-55h] BYREF
  int v12; // [rsp+48h] [rbp-51h]

  v3 = JetMove(a1, a2, a3, 0);
  v4 = v3;
  if ( !g_fInProc || dword_18010D924 )
    return v4;
  if ( v3 != -1414 )
  {
    v9 = v3;
    if ( v3 >= 0 )
      return v4;
    memset_0(v11, 0, 0x94u);
    v10 = 152;
    if ( (int)JetGetErrorInfoW(&v9, &v10, 152, 1, 0) < 0 )
      return v4;
    if ( v12 != 10 )
    {
      if ( v12 == 11 )
      {
        v8 = v9;
        UnistoreTelemetry::JetInconsistentError<unsigned long>(&v8);
      }
      else if ( v12 == 12 )
      {
        v8 = v9;
        UnistoreTelemetry::JetFragmentationError<unsigned long>(&v8);
      }
      return v4;
    }
    if ( v9 == -1414 )
      return v4;
  }
  v6 = RegistrySetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store", L"CorruptReason", v4);
  if ( v6 >= 0 )
  {
    v8 = v4;
    UnistoreTelemetry::MarkStoreCorruption<unsigned long>(&v8);
    if ( (unsigned int)IsJetCorruptionError(v4) )
    {
      Log_AssertionEvent(
        v7,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        109);
      __int2c();
    }
  }
  else
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v6,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      102);
  }
  return v4;
}

```

## disassembly

```asm
0x180002880  mov     [rsp-8+arg_18], rbx
0x180002885  push    rbp
0x180002886  lea     rbp, [rsp-57h]
0x18000288b  sub     rsp, 0F0h
0x180002892  mov     rax, cs:__security_cookie
0x180002899  xor     rax, rsp
0x18000289c  mov     [rbp+57h+var_10], rax
0x1800028a0  xor     r9d, r9d; grbit
0x1800028a3  call    cs:__imp_JetMove
0x1800028a9  cmp     cs:?g_fInProc@@3HA, 0; int g_fInProc
0x1800028b0  mov     ebx, eax
0x1800028b2  jz      short loc_18000290A
0x1800028b4  cmp     cs:dword_18010D924, 0
0x1800028bb  jnz     short loc_18000290A
0x1800028bd  cmp     eax, 0FFFFFA7Ah
0x1800028c2  jz      loc_180002966
0x1800028c8  mov     [rbp+57h+var_B8], eax
0x1800028cb  test    eax, eax
0x1800028cd  jns     short loc_18000290A
0x1800028cf  xor     edx, edx; Val
0x1800028d1  lea     rcx, [rbp+57h+var_AC]; void *
0x1800028d5  mov     r8d, 94h; Size
0x1800028db  call    memset_0
0x1800028e0  mov     r8d, 98h
0x1800028e6  mov     [rsp+0F0h+var_D0], 0
0x1800028ee  mov     r9d, 1
0x1800028f4  mov     [rbp+57h+var_B0], r8d
0x1800028f8  lea     rdx, [rbp+57h+var_B0]
0x1800028fc  lea     rcx, [rbp+57h+var_B8]
0x180002900  call    cs:__imp_JetGetErrorInfoW
0x180002906  test    eax, eax
0x180002908  jns     short loc_180002929
0x18000290a  mov     eax, ebx
0x18000290c  mov     rcx, [rbp+57h+var_10]
0x180002910  xor     rcx, rsp; StackCookie
0x180002913  call    __security_check_cookie
0x180002918  mov     rbx, [rsp+0F0h+arg_18]
0x180002920  add     rsp, 0F0h
0x180002927  pop     rbp
0x180002928  retn
0x180002929  mov     ecx, [rbp+57h+var_A8]
0x18000292c  sub     ecx, 0Ah
0x18000292f  jz      short loc_18000295D
0x180002931  sub     ecx, 1
0x180002934  jz      short loc_18000294C
0x180002936  cmp     ecx, 1
0x180002939  jnz     short loc_18000290A
0x18000293b  mov     eax, [rbp+57h+var_B8]
0x18000293e  lea     rcx, [rbp+57h+var_C0]
0x180002942  mov     [rbp+57h+var_C0], eax
0x180002945  call    ??$JetFragmentationError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetFragmentationError<ulong>(ulong &&)
0x18000294a  jmp     short loc_18000290A
0x18000294c  mov     eax, [rbp+57h+var_B8]
0x18000294f  lea     rcx, [rbp+57h+var_C0]
0x180002953  mov     [rbp+57h+var_C0], eax
0x180002956  call    ??$JetInconsistentError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetInconsistentError<ulong>(ulong &&)
0x18000295b  jmp     short loc_18000290A
0x18000295d  cmp     [rbp+57h+var_B8], 0FFFFFA7Ah
0x180002964  jz      short loc_18000290A
0x180002966  mov     r9d, ebx; unsigned int
0x180002969  lea     r8, ?c_wszUnistoreRegistryCorruptAfterMount@@3QBGB; "CorruptReason"
0x180002970  lea     rdx, ?c_wszUnistoreRegistryRoot@@3QBGB; "Software\\Microsoft\\Unified Store"
0x180002977  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000297e  call    ?RegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; RegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180002983  test    eax, eax
0x180002985  jns     short loc_1800029A2
0x180002987  mov     r9d, 66h ; 'f'
0x18000298d  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180002994  xor     edx, edx
0x180002996  mov     ecx, eax
0x180002998  call    Log_UnistoreHREvent_0
0x18000299d  jmp     loc_18000290A
0x1800029a2  lea     rcx, [rbp+57h+var_C0]
0x1800029a6  mov     [rbp+57h+var_C0], ebx
0x1800029a9  call    ??$MarkStoreCorruption@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::MarkStoreCorruption<ulong>(ulong &&)
0x1800029ae  mov     ecx, ebx; int
0x1800029b0  call    ?IsJetCorruptionError@@YAHJ@Z; IsJetCorruptionError(long)
0x1800029b5  test    eax, eax
0x1800029b7  jz      loc_18000290A
0x1800029bd  mov     r8d, 6Dh ; 'm'
0x1800029c3  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800029ca  call    Log_AssertionEvent
0x1800029cf  int     2Ch; Windows NT - assertion failure
0x1800029d1  jmp     loc_18000290A
```
