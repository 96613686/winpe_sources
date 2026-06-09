# CShareMediaSettingsWriterImpl::RemoveDevice(ushort *)

- ea: `0x1800141e0`
- end: `0x1800142ca`
- name: `?RemoveDevice@CShareMediaSettingsWriterImpl@@UEAAJPEAG@Z`
- size: `234`
- prototype: `int(CShareMediaSettingsWriterImpl *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180003860`
- `0x180003888`
- `0x1800141e0`
- `0x18001e010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18001425b`
- `ole32!CoCreateInstance` at `0x18001425b`
- `OLEAUT32!__imp_SysStringLen` at `0x180014223`
- `OLEAUT32!__imp_SysStringLen` at `0x180014223`

## pseudocode

```c
__int64 __fastcall CShareMediaSettingsWriterImpl::RemoveDevice(
        CShareMediaSettingsWriterImpl *this,
        unsigned __int16 *a2)
{
  HRESULT v3; // ebx
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids);
  if ( SysStringLen(a2) )
  {
    ppv = 0;
    v3 = CoCreateInstance(
           &GUID_92498132_4d1a_4297_9b78_9e2e4ba99c07,
           0,
           1u,
           &GUID_301936dc_7aa2_4c82_bf04_239ded72c828,
           &ppv);
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)ppv + 104LL))(ppv, a2);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  else
  {
    v3 = -2147024809;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800141e0  mov     [rsp+arg_0], rbx
0x1800141e5  mov     [rsp+arg_8], rsi
0x1800141ea  push    rdi
0x1800141eb  sub     rsp, 30h
0x1800141ef  mov     rdi, rdx
0x1800141f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141f9  lea     rsi, WPP_GLOBAL_Control
0x180014200  cmp     rcx, rsi
0x180014203  jz      short loc_180014220
0x180014205  test    byte ptr [rcx+1Ch], 20h
0x180014209  jz      short loc_180014220
0x18001420b  mov     rcx, [rcx+10h]
0x18001420f  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x180014216  mov     edx, 18h
0x18001421b  call    WPP_SF_
0x180014220  mov     rcx, rdi; pbstr
0x180014223  call    cs:__imp_SysStringLen
0x180014229  test    eax, eax
0x18001422b  jnz     short loc_180014234
0x18001422d  mov     ebx, 80070057h
0x180014232  jmp     short loc_18001428E
0x180014234  xor     edx, edx; pUnkOuter
0x180014236  mov     [rsp+38h+arg_10], 0
0x18001423f  lea     rax, [rsp+38h+arg_10]
0x180014244  lea     r9, _GUID_301936dc_7aa2_4c82_bf04_239ded72c828; riid
0x18001424b  mov     [rsp+38h+ppv], rax; ppv
0x180014250  lea     rcx, _GUID_92498132_4d1a_4297_9b78_9e2e4ba99c07; rclsid
0x180014257  lea     r8d, [rdx+1]; dwClsContext
0x18001425b  call    cs:__imp_CoCreateInstance
0x180014261  mov     ebx, eax
0x180014263  test    eax, eax
0x180014265  js      short loc_18001428E
0x180014267  mov     rcx, [rsp+38h+arg_10]
0x18001426c  mov     rdx, rdi
0x18001426f  mov     rax, [rcx]
0x180014272  mov     rax, [rax+68h]
0x180014276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001427b  mov     rcx, [rsp+38h+arg_10]
0x180014280  mov     ebx, eax
0x180014282  mov     rax, [rcx]
0x180014285  mov     rax, [rax+10h]
0x180014289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001428e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014295  cmp     rcx, rsi
0x180014298  jz      short loc_1800142B8
0x18001429a  test    byte ptr [rcx+1Ch], 20h
0x18001429e  jz      short loc_1800142B8
0x1800142a0  mov     rcx, [rcx+10h]
0x1800142a4  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x1800142ab  mov     edx, 19h
0x1800142b0  mov     r9d, ebx
0x1800142b3  call    WPP_SF_d
0x1800142b8  mov     rsi, [rsp+38h+arg_8]
0x1800142bd  mov     eax, ebx
0x1800142bf  mov     rbx, [rsp+38h+arg_0]
0x1800142c4  add     rsp, 30h
0x1800142c8  pop     rdi
0x1800142c9  retn
```
