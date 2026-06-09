# CShareMediaSettingsWriterImpl::EnableHMEOnMachine(int)

- ea: `0x180013dd0`
- end: `0x180013ed4`
- name: `?EnableHMEOnMachine@CShareMediaSettingsWriterImpl@@UEAAJH@Z`
- size: `260`
- prototype: `__int64 __fastcall(CShareMediaSettingsWriterImpl *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180003860`
- `0x180003888`
- `0x180013dd0`
- `0x18001e010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180013e3b`
- `ole32!CoCreateInstance` at `0x180013e3b`

## pseudocode

```c
__int64 __fastcall CShareMediaSettingsWriterImpl::EnableHMEOnMachine(CShareMediaSettingsWriterImpl *this, int a2)
{
  unsigned __int16 v3; // di
  HRESULT v4; // ebx
  __int16 v6; // [rsp+48h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids);
  ppv = 0;
  v3 = -(a2 != 0);
  v4 = CoCreateInstance(
         &GUID_ad581b00_7b64_4e59_a38d_d2c5bf51ddb3,
         0,
         1u,
         &GUID_01f5f85e_0a81_40da_a7c8_21ef3af8440c,
         &ppv);
  if ( v4 >= 0 )
  {
    v6 = 0;
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)ppv + 96LL))(ppv, &v6);
    if ( v4 >= 0 && v6 != v3 )
      v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 104LL))(ppv, v3);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids, (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180013dd0  mov     [rsp+arg_0], rbx
0x180013dd5  mov     [rsp+arg_18], rsi
0x180013dda  push    rdi
0x180013ddb  sub     rsp, 30h
0x180013ddf  mov     ebx, edx
0x180013de1  mov     rcx, cs:WPP_GLOBAL_Control
0x180013de8  lea     rsi, WPP_GLOBAL_Control
0x180013def  cmp     rcx, rsi
0x180013df2  jz      short loc_180013E0F
0x180013df4  test    byte ptr [rcx+1Ch], 20h
0x180013df8  jz      short loc_180013E0F
0x180013dfa  mov     rcx, [rcx+10h]
0x180013dfe  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x180013e05  mov     edx, 16h
0x180013e0a  call    WPP_SF_
0x180013e0f  lea     rax, [rsp+38h+arg_10]
0x180013e14  mov     [rsp+38h+arg_10], 0
0x180013e1d  neg     ebx
0x180013e1f  mov     [rsp+38h+ppv], rax; ppv
0x180013e24  lea     r9, _GUID_01f5f85e_0a81_40da_a7c8_21ef3af8440c; riid
0x180013e2b  sbb     di, di
0x180013e2e  lea     rcx, _GUID_ad581b00_7b64_4e59_a38d_d2c5bf51ddb3; rclsid
0x180013e35  xor     edx, edx; pUnkOuter
0x180013e37  lea     r8d, [rdx+1]; dwClsContext
0x180013e3b  call    cs:__imp_CoCreateInstance
0x180013e41  mov     ebx, eax
0x180013e43  test    eax, eax
0x180013e45  js      short loc_180013E98
0x180013e47  mov     rcx, [rsp+38h+arg_10]
0x180013e4c  lea     rdx, [rsp+38h+arg_8]
0x180013e51  xor     eax, eax
0x180013e53  mov     [rsp+38h+arg_8], ax
0x180013e58  mov     rax, [rcx]
0x180013e5b  mov     rax, [rax+60h]
0x180013e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e64  mov     ebx, eax
0x180013e66  test    eax, eax
0x180013e68  js      short loc_180013E87
0x180013e6a  cmp     [rsp+38h+arg_8], di
0x180013e6f  jz      short loc_180013E87
0x180013e71  mov     rcx, [rsp+38h+arg_10]
0x180013e76  movzx   edx, di
0x180013e79  mov     rax, [rcx]
0x180013e7c  mov     rax, [rax+68h]
0x180013e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e85  mov     ebx, eax
0x180013e87  mov     rcx, [rsp+38h+arg_10]
0x180013e8c  mov     rax, [rcx]
0x180013e8f  mov     rax, [rax+10h]
0x180013e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e98  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e9f  cmp     rcx, rsi
0x180013ea2  jz      short loc_180013EC2
0x180013ea4  test    byte ptr [rcx+1Ch], 20h
0x180013ea8  jz      short loc_180013EC2
0x180013eaa  mov     rcx, [rcx+10h]
0x180013eae  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x180013eb5  mov     edx, 17h
0x180013eba  mov     r9d, ebx
0x180013ebd  call    WPP_SF_d
0x180013ec2  mov     rsi, [rsp+38h+arg_18]
0x180013ec7  mov     eax, ebx
0x180013ec9  mov     rbx, [rsp+38h+arg_0]
0x180013ece  add     rsp, 30h
0x180013ed2  pop     rdi
0x180013ed3  retn
```
