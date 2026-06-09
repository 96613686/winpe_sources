# IsDeviceSpecial

- ea: `0x180009bc4`
- end: `0x180009d5e`
- name: `IsDeviceSpecial`
- size: `410`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008d20`
- `0x18000aba0`

## callees

- `0x180008bf0`
- `0x180009bc4`
- `0x1800120b0`
- `0x180013504`
- `0x180018970`
- `0x180018a00`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009cb2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009cb2`

## pseudocode

```c
__int64 __fastcall IsDeviceSpecial(__int64 a1)
{
  WCHAR *v1; // r14
  bool v2; // zf
  int v4; // eax
  int v5; // eax
  unsigned int i; // esi
  BYTE *PropertyBuffer; // rdi
  int ObjectProp; // eax
  int v9; // r8d
  __int64 v10; // rax
  unsigned int v11; // edi
  ULONG v13; // [rsp+40h] [rbp-1058h] BYREF
  DEVPROPTYPE PropertyType[1027]; // [rsp+44h] [rbp-1054h] BYREF

  v1 = *(WCHAR **)(a1 + 32);
  v2 = (*(_BYTE *)(a1 + 104) & 1) == 0;
  PropertyType[0] = 0;
  v13 = 0;
  if ( v2 )
  {
    if ( (*(_BYTE *)(a1 + 104) & 2) != 0 )
    {
      v5 = *(_DWORD *)(a1 + 104);
    }
    else
    {
      for ( i = 0; i < 2; ++i )
      {
        PropertyBuffer = (BYTE *)&PropertyType[512 * (unsigned __int64)i + 3];
        v13 = 2048;
        ObjectProp = PnpGetObjectProp(v1, PropertyType, PropertyBuffer, &v13);
        if ( ObjectProp || PropertyType[0] != 8210 || v13 > 0x800 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
          {
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (unsigned int)&WPP_GLOBAL_Control,
              v9,
              ObjectProp,
              (__int64)v1);
          }
        }
        else
        {
          PropertyType[512 * (unsigned __int64)i + 514] = 0;
          while ( *(_WORD *)PropertyBuffer )
          {
            if ( CompareStringOrdinal(L"STORAGE\\VolumeSnapshot", -1, (LPCWCH)PropertyBuffer, -1, 1) == 2 )
            {
              v4 = *(_DWORD *)(a1 + 104);
              goto LABEL_21;
            }
            v10 = -1;
            do
              ++v10;
            while ( *(_WORD *)&PropertyBuffer[2 * v10] );
            PropertyBuffer += 2 * v10 + 2;
          }
        }
      }
      v5 = *(_DWORD *)(a1 + 104);
    }
    v11 = 0;
    *(_DWORD *)(a1 + 104) = v5 | 2;
  }
  else
  {
    v4 = *(_DWORD *)(a1 + 104);
LABEL_21:
    v11 = 1;
    *(_DWORD *)(a1 + 104) = v4 | 1;
    if ( (Microsoft_Windows_UserPnpEnableBits & 1) != 0 )
      McTemplateU0z_EtwEventWriteTransfer(a1, SCHEDULER_VOLUME_SNAPSHOT_DEVICE_FOUND, v1);
  }
  return v11;
}

```

## disassembly

```asm
0x180009bc4  push    rbx
0x180009bc6  push    rbp
0x180009bc7  push    rsi
0x180009bc8  push    rdi
0x180009bc9  push    r14
0x180009bcb  push    r15
0x180009bcd  mov     eax, 1068h
0x180009bd2  call    _alloca_probe
0x180009bd7  sub     rsp, rax
0x180009bda  mov     rax, cs:__security_cookie
0x180009be1  xor     rax, rsp
0x180009be4  mov     [rsp+1098h+var_48], rax
0x180009bec  mov     r14, [rcx+20h]
0x180009bf0  xor     r15d, r15d
0x180009bf3  test    byte ptr [rcx+68h], 1
0x180009bf7  mov     rbx, rcx
0x180009bfa  mov     [rsp+1098h+PropertyType], r15d
0x180009bff  mov     [rsp+1098h+var_1058], r15d
0x180009c04  jz      short loc_180009C0E
0x180009c06  mov     eax, [rcx+68h]
0x180009c09  jmp     loc_180009D0C
0x180009c0e  test    byte ptr [rcx+68h], 2
0x180009c12  jz      short loc_180009C1C
0x180009c14  mov     eax, [rcx+68h]
0x180009c17  jmp     loc_180009D33
0x180009c1c  mov     esi, r15d
0x180009c1f  cmp     esi, 2
0x180009c22  jnb     loc_180009D30
0x180009c28  lea     rax, DEVPKEY_Device_CompatibleIds
0x180009c2f  mov     ebp, esi
0x180009c31  shl     rbp, 0Bh
0x180009c35  lea     rdi, [rsp+1098h+var_1048]
0x180009c3a  add     rdi, rbp
0x180009c3d  mov     [rsp+1098h+var_1058], 800h
0x180009c45  test    esi, esi
0x180009c47  lea     r9, DEVPKEY_Device_HardwareIds
0x180009c4e  mov     rcx, r14; pDeviceID
0x180009c51  cmovnz  r9, rax
0x180009c55  lea     rax, [rsp+1098h+var_1058]
0x180009c5a  mov     [rsp+1098h+var_1068], rax; PULONG
0x180009c5f  lea     rax, [rsp+1098h+PropertyType]
0x180009c64  mov     [rsp+1098h+PropertyBuffer], rdi; PropertyBuffer
0x180009c69  mov     qword ptr [rsp+1098h+bIgnoreCase], rax; PropertyType
0x180009c6e  call    PnpGetObjectProp
0x180009c73  test    eax, eax
0x180009c75  jnz     short loc_180009CD5
0x180009c77  cmp     [rsp+1098h+PropertyType], 2012h
0x180009c7f  jnz     short loc_180009CD5
0x180009c81  cmp     [rsp+1098h+var_1058], 800h
0x180009c89  ja      short loc_180009CD5
0x180009c8b  mov     [rsp+rbp+1098h+var_84C], r15d
0x180009c93  cmp     [rdi], r15w
0x180009c97  jz      short loc_180009D02
0x180009c99  or      r9d, 0FFFFFFFFh; cchCount2
0x180009c9d  mov     [rsp+1098h+bIgnoreCase], 1; bIgnoreCase
0x180009ca5  or      edx, r9d; cchCount1
0x180009ca8  lea     rcx, String1; "STORAGE\\VolumeSnapshot"
0x180009caf  mov     r8, rdi; lpString2
0x180009cb2  call    cs:__imp_CompareStringOrdinal
0x180009cb8  cmp     eax, 2
0x180009cbb  jz      short loc_180009D09
0x180009cbd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009cc1  inc     rax
0x180009cc4  cmp     [rdi+rax*2], r15w
0x180009cc9  jnz     short loc_180009CC1
0x180009ccb  lea     rdi, [rdi+rax*2]
0x180009ccf  add     rdi, 2
0x180009cd3  jmp     short loc_180009C93
0x180009cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cdc  lea     rdx, WPP_GLOBAL_Control
0x180009ce3  cmp     rcx, rdx
0x180009ce6  jz      short loc_180009D02
0x180009ce8  test    dword ptr [rcx+1Ch], 100000h
0x180009cef  jz      short loc_180009D02
0x180009cf1  mov     rcx, [rcx+10h]
0x180009cf5  mov     r9d, eax
0x180009cf8  mov     qword ptr [rsp+1098h+bIgnoreCase], r14
0x180009cfd  call    WPP_SF_DS
0x180009d02  inc     esi
0x180009d04  jmp     loc_180009C1F
0x180009d09  mov     eax, [rbx+68h]
0x180009d0c  mov     edi, 1
0x180009d11  or      eax, edi
0x180009d13  mov     [rbx+68h], eax
0x180009d16  test    cs:Microsoft_Windows_UserPnpEnableBits, dil
0x180009d1d  jz      short loc_180009D3C
0x180009d1f  mov     r8, r14
0x180009d22  lea     rdx, SCHEDULER_VOLUME_SNAPSHOT_DEVICE_FOUND
0x180009d29  call    McTemplateU0z_EtwEventWriteTransfer
0x180009d2e  jmp     short loc_180009D3C
0x180009d30  mov     eax, [rbx+68h]
0x180009d33  or      eax, 2
0x180009d36  mov     edi, r15d
0x180009d39  mov     [rbx+68h], eax
0x180009d3c  mov     eax, edi
0x180009d3e  mov     rcx, [rsp+1098h+var_48]
0x180009d46  xor     rcx, rsp; StackCookie
0x180009d49  call    __security_check_cookie
0x180009d4e  add     rsp, 1068h
0x180009d55  pop     r15
0x180009d57  pop     r14
0x180009d59  pop     rdi
0x180009d5a  pop     rsi
0x180009d5b  pop     rbp
0x180009d5c  pop     rbx
0x180009d5d  retn
```
