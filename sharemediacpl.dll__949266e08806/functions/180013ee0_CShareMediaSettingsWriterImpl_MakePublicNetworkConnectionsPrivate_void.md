# CShareMediaSettingsWriterImpl::MakePublicNetworkConnectionsPrivate(void)

- ea: `0x180013ee0`
- end: `0x18001408a`
- name: `?MakePublicNetworkConnectionsPrivate@CShareMediaSettingsWriterImpl@@UEAAJXZ`
- size: `426`
- prototype: `__int64 __fastcall(CShareMediaSettingsWriterImpl *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003860`
- `0x180003888`
- `0x180013ee0`
- `0x18001e010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180013f3e`
- `ole32!CoCreateInstance` at `0x180013f3e`

## pseudocode

```c
__int64 __fastcall CShareMediaSettingsWriterImpl::MakePublicNetworkConnectionsPrivate(
        CShareMediaSettingsWriterImpl *this)
{
  HRESULT v1; // ebx
  __int64 v3; // [rsp+30h] [rbp-20h] BYREF
  __int64 v4; // [rsp+38h] [rbp-18h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-10h] BYREF
  int v6; // [rsp+78h] [rbp+28h] BYREF
  int v7; // [rsp+80h] [rbp+30h] BYREF
  __int64 v8; // [rsp+88h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids);
  ppv = 0;
  v1 = CoCreateInstance(&CLSID_NetworkListManager, 0, 0x15u, &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b, &ppv);
  if ( v1 >= 0 )
  {
    v4 = 0;
    v1 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 72LL))(ppv, &v4);
    if ( v1 >= 0 )
    {
      v3 = 0;
      v7 = 0;
      do
      {
        if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v4 + 64LL))(
               v4,
               1,
               &v3,
               &v7) )
        {
          break;
        }
        v8 = 0;
        v1 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 56LL))(v3, &v8);
        if ( v1 >= 0 )
        {
          v6 = 0;
          v1 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 144LL))(v8, &v6);
          if ( v1 >= 0 && !v6 )
            v1 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 152LL))(v8, 1);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
      }
      while ( v1 >= 0 );
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids, (unsigned int)v1);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180013ee0  push    rbp
0x180013ee2  push    rbx
0x180013ee3  push    rsi
0x180013ee4  mov     rbp, rsp
0x180013ee7  sub     rsp, 50h
0x180013eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ef2  lea     rsi, WPP_GLOBAL_Control
0x180013ef9  cmp     rcx, rsi
0x180013efc  jz      short loc_180013F19
0x180013efe  test    byte ptr [rcx+1Ch], 20h
0x180013f02  jz      short loc_180013F19
0x180013f04  mov     rcx, [rcx+10h]
0x180013f08  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x180013f0f  mov     edx, 1Ah
0x180013f14  call    WPP_SF_
0x180013f19  xor     edx, edx; pUnkOuter
0x180013f1b  mov     [rbp+var_10], 0
0x180013f23  lea     rax, [rbp+var_10]
0x180013f27  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x180013f2e  mov     [rsp+50h+ppv], rax; ppv
0x180013f33  lea     rcx, CLSID_NetworkListManager; rclsid
0x180013f3a  lea     r8d, [rdx+15h]; dwClsContext
0x180013f3e  call    cs:__imp_CoCreateInstance
0x180013f44  mov     ebx, eax
0x180013f46  test    eax, eax
0x180013f48  js      loc_180014056
0x180013f4e  mov     rcx, [rbp+var_10]
0x180013f52  lea     rdx, [rbp+var_18]
0x180013f56  mov     [rbp+var_18], 0
0x180013f5e  mov     rax, [rcx]
0x180013f61  mov     rax, [rax+48h]
0x180013f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f6a  mov     ebx, eax
0x180013f6c  test    eax, eax
0x180013f6e  js      loc_180014046
0x180013f74  mov     [rbp+var_20], 0
0x180013f7c  mov     [rbp+arg_10], 0
0x180013f83  mov     rcx, [rbp+var_18]
0x180013f87  lea     r9, [rbp+arg_10]
0x180013f8b  lea     r8, [rbp+var_20]
0x180013f8f  mov     edx, 1
0x180013f94  mov     rax, [rcx]
0x180013f97  mov     rax, [rax+40h]
0x180013f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fa0  test    eax, eax
0x180013fa2  jnz     loc_180014036
0x180013fa8  mov     rcx, [rbp+var_20]
0x180013fac  lea     rdx, [rbp+arg_18]
0x180013fb0  mov     [rbp+arg_18], 0
0x180013fb8  mov     rax, [rcx]
0x180013fbb  mov     rax, [rax+38h]
0x180013fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fc4  mov     ebx, eax
0x180013fc6  test    eax, eax
0x180013fc8  js      short loc_18001401E
0x180013fca  mov     rcx, [rbp+arg_18]
0x180013fce  lea     rdx, [rbp+arg_8]
0x180013fd2  mov     [rbp+arg_8], 0
0x180013fd9  mov     rax, [rcx]
0x180013fdc  mov     rax, [rax+90h]
0x180013fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fe8  mov     ebx, eax
0x180013fea  test    eax, eax
0x180013fec  js      short loc_18001400E
0x180013fee  cmp     [rbp+arg_8], 0
0x180013ff2  jnz     short loc_18001400E
0x180013ff4  mov     rcx, [rbp+arg_18]
0x180013ff8  mov     edx, 1
0x180013ffd  mov     rax, [rcx]
0x180014000  mov     rax, [rax+98h]
0x180014007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001400c  mov     ebx, eax
0x18001400e  mov     rcx, [rbp+arg_18]
0x180014012  mov     rax, [rcx]
0x180014015  mov     rax, [rax+10h]
0x180014019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001401e  mov     rcx, [rbp+var_20]
0x180014022  mov     rax, [rcx]
0x180014025  mov     rax, [rax+10h]
0x180014029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001402e  test    ebx, ebx
0x180014030  jns     loc_180013F83
0x180014036  mov     rcx, [rbp+var_18]
0x18001403a  mov     rax, [rcx]
0x18001403d  mov     rax, [rax+10h]
0x180014041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014046  mov     rcx, [rbp+var_10]
0x18001404a  mov     rax, [rcx]
0x18001404d  mov     rax, [rax+10h]
0x180014051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014056  mov     rcx, cs:WPP_GLOBAL_Control
0x18001405d  cmp     rcx, rsi
0x180014060  jz      short loc_180014080
0x180014062  test    byte ptr [rcx+1Ch], 20h
0x180014066  jz      short loc_180014080
0x180014068  mov     rcx, [rcx+10h]
0x18001406c  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x180014073  mov     edx, 1Bh
0x180014078  mov     r9d, ebx
0x18001407b  call    WPP_SF_d
0x180014080  mov     eax, ebx
0x180014082  add     rsp, 50h
0x180014086  pop     rsi
0x180014087  pop     rbx
0x180014088  pop     rbp
0x180014089  retn
```
