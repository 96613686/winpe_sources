# CSettings::LoadFromRegistry(HKEY__ *)

- ea: `0x140010d64`
- end: `0x140010e2a`
- name: `?LoadFromRegistry@CSettings@@QEAAJPEAUHKEY__@@@Z`
- size: `198`
- prototype: `int(CSettings *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000919c`

## callees

- `0x140010d64`
- `0x140014eb0`
- `0x14001550c`
- `0x140015794`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140010e17`
- `ADVAPI32!RegCloseKey` at `0x140010e17`

## pseudocode

```c
int __fastcall CSettings::LoadFromRegistry(CSettings *this, HKEY a2)
{
  int result; // eax
  signed int RegSettingsInt; // eax
  signed int v5; // edi
  int v6; // ecx
  bool v7; // zf
  signed int RegSettingsBool; // eax
  int Data; // [rsp+40h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+20h] BYREF

  hKey = 0;
  Data = 0;
  result = CreateRegSettings(a2, L"Software\\Microsoft\\Windows Script Host\\Settings", 0x20019u, &hKey);
  if ( result >= 0 )
  {
    RegSettingsInt = GetRegSettingsInt(hKey, L"Timeout", (LPBYTE)&Data);
    v5 = RegSettingsInt;
    if ( RegSettingsInt >= 0 )
    {
      v6 = Data;
      v7 = Data == 0;
      *(_DWORD *)this = Data;
      *((_BYTE *)this + 4) = !v7;
      if ( v6 )
        goto LABEL_7;
    }
    else
    {
      if ( RegSettingsInt != -2147024894 )
      {
LABEL_11:
        RegCloseKey(hKey);
        return v5;
      }
      *((_BYTE *)this + 4) = 0;
    }
    *(_DWORD *)this = 0;
LABEL_7:
    RegSettingsBool = GetRegSettingsBool(hKey, L"DisplayLogo", (bool *)this + 6);
    v5 = RegSettingsBool;
    if ( RegSettingsBool >= 0 )
    {
      *((_BYTE *)this + 7) = 1;
    }
    else if ( RegSettingsBool == -2147024894 )
    {
      *((_BYTE *)this + 7) = 0;
      v5 = 0;
    }
    goto LABEL_11;
  }
  return result;
}

```

## disassembly

```asm
0x140010d64  mov     [rsp+arg_0], rbx
0x140010d69  push    rdi
0x140010d6a  sub     rsp, 20h
0x140010d6e  mov     rax, rdx
0x140010d71  mov     [rsp+28h+hKey], 0
0x140010d7a  mov     rbx, rcx
0x140010d7d  mov     [rsp+28h+Data], 0
0x140010d85  mov     rcx, rax; hKey
0x140010d88  lea     r9, [rsp+28h+hKey]; phkResult
0x140010d8d  mov     r8d, 20019h; samDesired
0x140010d93  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows Script Hos"...
0x140010d9a  call    ?CreateRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; CreateRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x140010d9f  test    eax, eax
0x140010da1  js      short loc_140010E1F
0x140010da3  mov     rcx, [rsp+28h+hKey]; hKey
0x140010da8  lea     r8, [rsp+28h+Data]; lpData
0x140010dad  lea     rdx, aTimeout; "Timeout"
0x140010db4  call    ?GetRegSettingsInt@@YAJPEAUHKEY__@@PEBGPEAK@Z; GetRegSettingsInt(HKEY__ *,ushort const *,ulong *)
0x140010db9  mov     edi, eax
0x140010dbb  test    eax, eax
0x140010dbd  jns     short loc_140010DCC
0x140010dbf  cmp     eax, 80070002h
0x140010dc4  jnz     short loc_140010E12
0x140010dc6  mov     byte ptr [rbx+4], 0
0x140010dca  jmp     short loc_140010DDE
0x140010dcc  mov     ecx, [rsp+28h+Data]
0x140010dd0  test    ecx, ecx
0x140010dd2  mov     [rbx], ecx
0x140010dd4  setnz   al
0x140010dd7  mov     [rbx+4], al
0x140010dda  test    ecx, ecx
0x140010ddc  jnz     short loc_140010DE4
0x140010dde  mov     dword ptr [rbx], 0
0x140010de4  mov     rcx, [rsp+28h+hKey]; hKey
0x140010de9  lea     r8, [rbx+6]; bool *
0x140010ded  lea     rdx, aDisplaylogo; "DisplayLogo"
0x140010df4  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x140010df9  mov     edi, eax
0x140010dfb  test    eax, eax
0x140010dfd  jns     short loc_140010E0E
0x140010dff  cmp     eax, 80070002h
0x140010e04  jnz     short loc_140010E12
0x140010e06  mov     byte ptr [rbx+7], 0
0x140010e0a  xor     edi, edi
0x140010e0c  jmp     short loc_140010E12
0x140010e0e  mov     byte ptr [rbx+7], 1
0x140010e12  mov     rcx, [rsp+28h+hKey]; hKey
0x140010e17  call    cs:__imp_RegCloseKey
0x140010e1d  mov     eax, edi
0x140010e1f  mov     rbx, [rsp+28h+arg_0]
0x140010e24  add     rsp, 20h
0x140010e28  pop     rdi
0x140010e29  retn
```
