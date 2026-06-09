# TetheringService::MigrateSettingsNeeded(int *)

- ea: `0x18001a714`
- end: `0x18001a7f1`
- name: `?MigrateSettingsNeeded@TetheringService@@AEAAJPEAH@Z`
- size: `221`
- prototype: `__int64 __fastcall(TetheringService *__hidden this, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18001935c`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x18001a714`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a789`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a789`

## string_xrefs

- `0x18001a779`: `System\CurrentControlSet\Services\IcsSvc\Settings`

## pseudocode

```c
__int64 __fastcall TetheringService::MigrateSettingsNeeded(TetheringService *this, int *a2)
{
  int v3; // edi
  LSTATUS ValueW; // eax
  int v5; // ebx
  __int64 v6; // r9
  TetheringService *pcbData; // [rsp+70h] [rbp+8h] BYREF

  pcbData = this;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 389, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  v3 = 0;
  LODWORD(pcbData) = 208;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\IcsSvc\\Settings",
             L"PrivateConnectionSettings",
             8u,
             0,
             0,
             (LPDWORD)&pcbData);
  v5 = ValueW;
  if ( !ValueW )
    goto LABEL_7;
  if ( ValueW == 2 )
  {
    v5 = 0;
    v3 = 1;
LABEL_7:
    *a2 = v3;
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    else
      v6 = (unsigned int)v5;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 390, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v6);
  }
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001a714  mov     [rsp+arg_0], rcx
0x18001a719  push    rbx
0x18001a71a  push    rbp
0x18001a71b  push    rsi
0x18001a71c  push    rdi
0x18001a71d  sub     rsp, 48h
0x18001a721  mov     rsi, rdx
0x18001a724  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a72b  lea     rbp, WPP_GLOBAL_Control
0x18001a732  cmp     rcx, rbp
0x18001a735  jz      short loc_18001A752
0x18001a737  test    byte ptr [rcx+1Ch], 8
0x18001a73b  jz      short loc_18001A752
0x18001a73d  mov     rcx, [rcx+10h]
0x18001a741  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001a748  mov     edx, 185h
0x18001a74d  call    WPP_SF_
0x18001a752  xor     edi, edi
0x18001a754  mov     dword ptr [rsp+68h+arg_0], 0D0h
0x18001a75c  lea     rax, [rsp+68h+arg_0]
0x18001a761  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001a768  mov     [rsp+68h+pcbData], rax; pcbData
0x18001a76d  lea     r8, aPrivateconnect; "PrivateConnectionSettings"
0x18001a774  mov     [rsp+68h+pvData], rdi; pvData
0x18001a779  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Ic"...
0x18001a780  lea     r9d, [rdi+8]; dwFlags
0x18001a784  mov     [rsp+68h+pdwType], rdi; pdwType
0x18001a789  call    cs:__imp_RegGetValueW
0x18001a78f  mov     ebx, eax
0x18001a791  test    eax, eax
0x18001a793  jz      short loc_18001A79F
0x18001a795  cmp     eax, 2
0x18001a798  jnz     short loc_18001A7A1
0x18001a79a  xor     ebx, ebx
0x18001a79c  lea     edi, [rax-1]
0x18001a79f  mov     [rsi], edi
0x18001a7a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a7a8  mov     edi, 80070000h
0x18001a7ad  cmp     rcx, rbp
0x18001a7b0  jz      short loc_18001A7DD
0x18001a7b2  test    byte ptr [rcx+1Ch], 8
0x18001a7b6  jz      short loc_18001A7DD
0x18001a7b8  test    ebx, ebx
0x18001a7ba  jg      short loc_18001A7C1
0x18001a7bc  mov     r9d, ebx
0x18001a7bf  jmp     short loc_18001A7C8
0x18001a7c1  movzx   r9d, bx
0x18001a7c5  or      r9d, edi
0x18001a7c8  mov     rcx, [rcx+10h]
0x18001a7cc  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001a7d3  mov     edx, 186h
0x18001a7d8  call    WPP_SF_d
0x18001a7dd  test    ebx, ebx
0x18001a7df  jle     short loc_18001A7E6
0x18001a7e1  movzx   ebx, bx
0x18001a7e4  or      ebx, edi
0x18001a7e6  mov     eax, ebx
0x18001a7e8  add     rsp, 48h
0x18001a7ec  pop     rdi
0x18001a7ed  pop     rsi
0x18001a7ee  pop     rbp
0x18001a7ef  pop     rbx
0x18001a7f0  retn
```
