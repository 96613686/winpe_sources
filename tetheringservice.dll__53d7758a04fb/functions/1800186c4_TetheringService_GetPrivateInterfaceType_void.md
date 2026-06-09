# TetheringService::GetPrivateInterfaceType(void)

- ea: `0x1800186c4`
- end: `0x180018775`
- name: `?GetPrivateInterfaceType@TetheringService@@AEAA?AW4_TETHERING_CONNECTION_TYPE@@XZ`
- size: `177`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180019170`

## callees

- `0x18000304c`
- `0x18000bf4c`
- `0x18000bf74`
- `0x1800186c4`
- `0x18002b1f0`

## pseudocode

```c
__int64 TetheringService::GetPrivateInterfaceType()
{
  unsigned int *SettingValueGlobalInternal; // rax
  unsigned int v1; // ebx
  TetheringServiceTelemetry *v2; // rcx

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  SettingValueGlobalInternal = (unsigned int *)TetheringSettingsGetSettingValueGlobalInternal(7);
  if ( SettingValueGlobalInternal )
  {
    v1 = *SettingValueGlobalInternal;
    free(SettingValueGlobalInternal);
LABEL_9:
    v2 = WPP_GLOBAL_Control;
    goto LABEL_10;
  }
  v2 = WPP_GLOBAL_Control;
  v1 = 0;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    return v1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    goto LABEL_9;
  }
LABEL_10:
  if ( v2 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v2 + 2), 46, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x1800186c4  mov     [rsp+arg_0], rbx
0x1800186c9  push    rdi
0x1800186ca  sub     rsp, 20h
0x1800186ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186d5  lea     rdi, WPP_GLOBAL_Control
0x1800186dc  cmp     rcx, rdi
0x1800186df  jz      short loc_1800186FC
0x1800186e1  test    byte ptr [rcx+1Ch], 8
0x1800186e5  jz      short loc_1800186FC
0x1800186e7  mov     rcx, [rcx+10h]
0x1800186eb  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800186f2  mov     edx, 2Ch ; ','
0x1800186f7  call    WPP_SF_
0x1800186fc  mov     ecx, 7
0x180018701  call    ?TetheringSettingsGetSettingValueGlobalInternal@@YAPEAXW4TetheringSettingGlobal@@@Z; TetheringSettingsGetSettingValueGlobalInternal(TetheringSettingGlobal)
0x180018706  test    rax, rax
0x180018709  jz      short loc_180018717
0x18001870b  mov     ebx, [rax]
0x18001870d  mov     rcx, rax; Block
0x180018710  call    free
0x180018715  jmp     short loc_18001873E
0x180018717  mov     rcx, cs:WPP_GLOBAL_Control
0x18001871e  xor     ebx, ebx
0x180018720  cmp     rcx, rdi
0x180018723  jz      short loc_180018768
0x180018725  test    byte ptr [rcx+1Ch], 1
0x180018729  jz      short loc_180018745
0x18001872b  mov     rcx, [rcx+10h]
0x18001872f  lea     edx, [rbx+2Dh]
0x180018732  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180018739  call    WPP_SF_
0x18001873e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018745  cmp     rcx, rdi
0x180018748  jz      short loc_180018768
0x18001874a  test    byte ptr [rcx+1Ch], 8
0x18001874e  jz      short loc_180018768
0x180018750  mov     rcx, [rcx+10h]
0x180018754  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001875b  mov     edx, 2Eh ; '.'
0x180018760  mov     r9d, ebx
0x180018763  call    WPP_SF_d
0x180018768  mov     eax, ebx
0x18001876a  mov     rbx, [rsp+28h+arg_0]
0x18001876f  add     rsp, 20h
0x180018773  pop     rdi
0x180018774  retn
```
