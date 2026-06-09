# _InstallManifestCommand::Execute_::_1_::catch$46

- ea: `0x140031bd0`
- end: `0x140031c7d`
- name: `_InstallManifestCommand::Execute_::_1_::catch$46`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140010450`
- `0x140022cec`
- `0x14002f7fc`
- `0x140031810`
- `0x140031bd0`

## pseudocode

```c
void __fastcall __noreturn InstallManifestCommand::Execute_::_1_::catch_46(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  const wchar_t *Src; // rax
  const char *v5; // [rsp+20h] [rbp-78h]

  v3 = *(_QWORD *)(a2 + 456);
  if ( *(_DWORD *)(v3 + 20) != 4 )
    throw;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids, 15000);
  }
  Src = GetChannelPropertyName(*(_DWORD *)(v3 + 20));
  EvtException::EvtException((EvtException *)(a2 + 880), 0x3A98u, 0, 0, v5, 286, 0x5Au, Src);
  throw (EvtException *)(a2 + 880);
}

```

## disassembly

```asm
0x140031bd0  mov     [rsp+arg_8], rdx
0x140031bd5  push    rbx
0x140031bd6  push    rbp
0x140031bd7  sub     rsp, 88h
0x140031bde  mov     rbp, rdx
0x140031be1  mov     rbx, [rbp+1C8h]
0x140031be8  cmp     dword ptr [rbx+14h], 4
0x140031bec  jz      short loc_140031BF8
0x140031bee  xor     edx, edx; pThrowInfo
0x140031bf0  xor     ecx, ecx; pExceptionObject
0x140031bf2  call    _CxxThrowException_0
0x140031bf8  lea     rax, WPP_GLOBAL_Control
0x140031bff  mov     rcx, cs:WPP_GLOBAL_Control
0x140031c06  cmp     rcx, rax
0x140031c09  jz      short loc_140031C35
0x140031c0b  test    dword ptr [rcx+1Ch], 400000h
0x140031c12  jz      short loc_140031C35
0x140031c14  cmp     byte ptr [rcx+19h], 2
0x140031c18  jb      short loc_140031C35
0x140031c1a  mov     edx, 1Eh
0x140031c1f  mov     r9d, 3A98h
0x140031c25  lea     r8, WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids
0x140031c2c  mov     rcx, [rcx+10h]
0x140031c30  call    WPP_SF_d
0x140031c35  mov     ecx, [rbx+14h]; unsigned int
0x140031c38  call    ?GetChannelPropertyName@@YAPEB_WK@Z; GetChannelPropertyName(ulong)
0x140031c3d  mov     [rsp+98h+Src], rax; Src
0x140031c42  mov     [rsp+98h+var_68], 5Ah ; 'Z'; unsigned int
0x140031c4a  mov     [rsp+98h+var_70], 11Eh; int
0x140031c52  xor     r9d, r9d; unsigned int
0x140031c55  xor     r8d, r8d; unsigned int
0x140031c58  mov     edx, 3A98h; unsigned int
0x140031c5d  lea     rcx, [rbp+370h]; this
0x140031c64  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140031c69  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140031c70  lea     rcx, [rbp+370h]; pExceptionObject
0x140031c77  call    _CxxThrowException_0
```
