# TetheringService::IsBluetoothAutoConnectionEnabled(void)

- ea: `0x18001a21c`
- end: `0x18001a2d2`
- name: `?IsBluetoothAutoConnectionEnabled@TetheringService@@AEAAHXZ`
- size: `182`
- prototype: `__int64 __fastcall(TetheringService *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180014c8c`
- `0x18001e4a4`

## callees

- `0x18000304c`
- `0x18000bf4c`
- `0x18000bfb4`
- `0x18001a21c`
- `0x18002b1f0`

## pseudocode

```c
__int64 __fastcall TetheringService::IsBluetoothAutoConnectionEnabled(TetheringService *this)
{
  unsigned int *SettingValueGlobalInternal; // rax
  __int64 v2; // r9
  unsigned int v3; // ebx
  TetheringServiceTelemetry *v4; // rcx

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 253, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  SettingValueGlobalInternal = (unsigned int *)TetheringSettingsGetSettingValueGlobalInternal(10);
  if ( SettingValueGlobalInternal )
  {
    v3 = *SettingValueGlobalInternal;
    free(SettingValueGlobalInternal);
LABEL_9:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_10;
  }
  v4 = WPP_GLOBAL_Control;
  v3 = 0;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 254, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    goto LABEL_9;
  }
LABEL_10:
  if ( v4 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
  {
    LOBYTE(v2) = v3 != 0;
    WPP_SF_c(*((_QWORD *)v4 + 2), 255, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v2);
  }
  return v3;
}

```

## disassembly

```asm
0x18001a21c  mov     [rsp+arg_0], rbx
0x18001a221  push    rdi
0x18001a222  sub     rsp, 20h
0x18001a226  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a22d  lea     rdi, WPP_GLOBAL_Control
0x18001a234  cmp     rcx, rdi
0x18001a237  jz      short loc_18001A254
0x18001a239  test    byte ptr [rcx+1Ch], 8
0x18001a23d  jz      short loc_18001A254
0x18001a23f  mov     rcx, [rcx+10h]
0x18001a243  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001a24a  mov     edx, 0FDh
0x18001a24f  call    WPP_SF_
0x18001a254  mov     ecx, 0Ah
0x18001a259  call    ?TetheringSettingsGetSettingValueGlobalInternal@@YAPEAXW4TetheringSettingGlobal@@@Z; TetheringSettingsGetSettingValueGlobalInternal(TetheringSettingGlobal)
0x18001a25e  test    rax, rax
0x18001a261  jz      short loc_18001A26F
0x18001a263  mov     ebx, [rax]
0x18001a265  mov     rcx, rax; Block
0x18001a268  call    free
0x18001a26d  jmp     short loc_18001A298
0x18001a26f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a276  xor     ebx, ebx
0x18001a278  cmp     rcx, rdi
0x18001a27b  jz      short loc_18001A2C5
0x18001a27d  test    byte ptr [rcx+1Ch], 1
0x18001a281  jz      short loc_18001A29F
0x18001a283  mov     rcx, [rcx+10h]
0x18001a287  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001a28e  mov     edx, 0FEh
0x18001a293  call    WPP_SF_
0x18001a298  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a29f  cmp     rcx, rdi
0x18001a2a2  jz      short loc_18001A2C5
0x18001a2a4  test    byte ptr [rcx+1Ch], 8
0x18001a2a8  jz      short loc_18001A2C5
0x18001a2aa  mov     rcx, [rcx+10h]
0x18001a2ae  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001a2b5  test    ebx, ebx
0x18001a2b7  mov     edx, 0FFh
0x18001a2bc  setnz   r9b
0x18001a2c0  call    WPP_SF_c
0x18001a2c5  mov     eax, ebx
0x18001a2c7  mov     rbx, [rsp+28h+arg_0]
0x18001a2cc  add     rsp, 20h
0x18001a2d0  pop     rdi
0x18001a2d1  retn
```
