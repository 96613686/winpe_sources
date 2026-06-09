# CDeviceSettings::~CDeviceSettings(void)

- ea: `0x180003ed0`
- end: `0x180003f8b`
- name: `??1CDeviceSettings@@IEAA@XZ`
- size: `187`
- prototype: `void __fastcall(CDeviceSettings *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800061a0`

## callees

- `0x180003860`
- `0x180003ed0`
- `0x1800166a0`
- `0x18001e010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180003f36`
- `ole32!CoTaskMemFree` at `0x180003f40`
- `ole32!CoTaskMemFree` at `0x180003f4a`
- `ole32!CoTaskMemFree` at `0x180003f36`
- `ole32!CoTaskMemFree` at `0x180003f40`
- `ole32!CoTaskMemFree` at `0x180003f4a`

## pseudocode

```c
void __fastcall CDeviceSettings::~CDeviceSettings(CDeviceSettings *this)
{
  __int64 v2; // rcx
  struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *v3; // rdx

  *(_QWORD *)this = &CDeviceSettings::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    *((_QWORD *)this + 2) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  CoTaskMemFree(*((LPVOID *)this + 13));
  CoTaskMemFree(*((LPVOID *)this + 9));
  CoTaskMemFree(*((LPVOID *)this + 8));
  HMEHelpers::CleanupWMPDeviceSettings((CDeviceSettings *)((char *)this + 24), v3);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
}

```

## disassembly

```asm
0x180003ed0  mov     [rsp+arg_0], rbx
0x180003ed5  push    rdi
0x180003ed6  sub     rsp, 20h
0x180003eda  lea     rax, ??_7CDeviceSettings@@6B@; const CDeviceSettings::`vftable'
0x180003ee1  mov     rbx, rcx
0x180003ee4  mov     [rcx], rax
0x180003ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x180003eee  lea     rdi, WPP_GLOBAL_Control
0x180003ef5  cmp     rcx, rdi
0x180003ef8  jz      short loc_180003F15
0x180003efa  test    byte ptr [rcx+1Ch], 20h
0x180003efe  jz      short loc_180003F15
0x180003f00  mov     rcx, [rcx+10h]
0x180003f04  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180003f0b  mov     edx, 0Ch
0x180003f10  call    WPP_SF_
0x180003f15  mov     rcx, [rbx+10h]
0x180003f19  test    rcx, rcx
0x180003f1c  jz      short loc_180003F32
0x180003f1e  mov     qword ptr [rbx+10h], 0
0x180003f26  mov     rax, [rcx]
0x180003f29  mov     rax, [rax+10h]
0x180003f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f32  mov     rcx, [rbx+68h]; pv
0x180003f36  call    cs:__imp_CoTaskMemFree
0x180003f3c  mov     rcx, [rbx+48h]; pv
0x180003f40  call    cs:__imp_CoTaskMemFree
0x180003f46  mov     rcx, [rbx+40h]; pv
0x180003f4a  call    cs:__imp_CoTaskMemFree
0x180003f50  lea     rcx, [rbx+18h]; this
0x180003f54  call    ?CleanupWMPDeviceSettings@HMEHelpers@@YAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; HMEHelpers::CleanupWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180003f59  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f60  cmp     rcx, rdi
0x180003f63  jz      short loc_180003F80
0x180003f65  test    byte ptr [rcx+1Ch], 20h
0x180003f69  jz      short loc_180003F80
0x180003f6b  mov     rcx, [rcx+10h]
0x180003f6f  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180003f76  mov     edx, 0Dh
0x180003f7b  call    WPP_SF_
0x180003f80  mov     rbx, [rsp+28h+arg_0]
0x180003f85  add     rsp, 20h
0x180003f89  pop     rdi
0x180003f8a  retn
```
