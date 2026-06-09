# CShareMediaSettingsWriterImpl::~CShareMediaSettingsWriterImpl(void)

- ea: `0x180013cbc`
- end: `0x180013d2c`
- name: `??1CShareMediaSettingsWriterImpl@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(CShareMediaSettingsWriterImpl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180014130`

## callees

- `0x18000366c`
- `0x180003860`
- `0x180013cbc`

## pseudocode

```c
void __fastcall CShareMediaSettingsWriterImpl::~CShareMediaSettingsWriterImpl(CShareMediaSettingsWriterImpl *this)
{
  *(_QWORD *)this = &CShareMediaSettingsWriterImpl::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids);
  DllRelease();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids);
}

```

## disassembly

```asm
0x180013cbc  push    rbx
0x180013cbe  sub     rsp, 20h
0x180013cc2  lea     rax, ??_7CShareMediaSettingsWriterImpl@@6B@; const CShareMediaSettingsWriterImpl::`vftable'
0x180013cc9  mov     [rcx], rax
0x180013ccc  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cd3  lea     rbx, WPP_GLOBAL_Control
0x180013cda  cmp     rcx, rbx
0x180013cdd  jz      short loc_180013CFA
0x180013cdf  test    byte ptr [rcx+1Ch], 20h
0x180013ce3  jz      short loc_180013CFA
0x180013ce5  mov     rcx, [rcx+10h]
0x180013ce9  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x180013cf0  mov     edx, 0Ch
0x180013cf5  call    WPP_SF_
0x180013cfa  call    DllRelease
0x180013cff  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d06  cmp     rcx, rbx
0x180013d09  jz      short loc_180013D26
0x180013d0b  test    byte ptr [rcx+1Ch], 20h
0x180013d0f  jz      short loc_180013D26
0x180013d11  mov     rcx, [rcx+10h]
0x180013d15  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x180013d1c  mov     edx, 0Dh
0x180013d21  call    WPP_SF_
0x180013d26  add     rsp, 20h
0x180013d2a  pop     rbx
0x180013d2b  retn
```
