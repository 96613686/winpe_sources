# CSettings::LoadFromRegistry(HKEY__ *)

- ea: `0x18000adfc`
- end: `0x18000aeaa`
- name: `?LoadFromRegistry@CSettings@@QEAAJPEAUHKEY__@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(CSettings *__hidden this, HKEY)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006160`
- `0x180006440`
- `0x1800072c4`

## callees

- `0x18000adfc`
- `0x18000b574`
- `0x18000bbdc`
- `0x18000be68`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000ae97`
- `ADVAPI32!RegCloseKey` at `0x18000ae97`

## pseudocode

```c
int __fastcall CSettings::LoadFromRegistry(CSettings *this, const unsigned __int16 *a2)
{
  int result; // eax
  const unsigned __int16 *v4; // rdx
  int RegSettingsInt; // eax
  const unsigned __int16 *v6; // rdx
  int v7; // edi
  unsigned int v8; // ecx
  bool v9; // zf
  signed int RegSettingsBool; // eax
  unsigned int v11; // [rsp+38h] [rbp+10h] BYREF
  int v12; // [rsp+3Ch] [rbp+14h]
  HKEY hKey; // [rsp+40h] [rbp+18h] BYREF

  v12 = HIDWORD(a2);
  hKey = 0;
  v11 = 0;
  result = CreateRegSettings((HKEY)this, a2, 0x20019u, &hKey);
  if ( result >= 0 )
  {
    RegSettingsInt = GetRegSettingsInt(hKey, v4, &v11);
    v7 = RegSettingsInt;
    if ( RegSettingsInt >= 0 )
    {
      v8 = v11;
      v9 = v11 == 0;
      *(_DWORD *)this = v11;
      *((_BYTE *)this + 4) = !v9;
      if ( v8 )
        goto LABEL_7;
    }
    else
    {
      if ( RegSettingsInt != -2147024894 )
      {
LABEL_11:
        RegCloseKey(hKey);
        return v7;
      }
      *((_BYTE *)this + 4) = 0;
    }
    *(_DWORD *)this = 0;
LABEL_7:
    RegSettingsBool = GetRegSettingsBool(hKey, v6, (bool *)this + 6);
    v7 = RegSettingsBool;
    if ( RegSettingsBool >= 0 )
    {
      *((_BYTE *)this + 7) = 1;
    }
    else if ( RegSettingsBool == -2147024894 )
    {
      *((_BYTE *)this + 7) = 0;
      v7 = 0;
    }
    goto LABEL_11;
  }
  return result;
}

```

## disassembly

```asm
0x18000adfc  mov     rax, rsp
0x18000adff  mov     [rax+8], rbx
0x18000ae03  mov     [rax+10h], rdx
0x18000ae07  push    rdi
0x18000ae08  sub     rsp, 20h
0x18000ae0c  lea     r9, [rax+18h]; HKEY *
0x18000ae10  mov     qword ptr [rax+18h], 0
0x18000ae18  mov     r8d, 20019h; unsigned int
0x18000ae1e  mov     dword ptr [rax+10h], 0
0x18000ae25  mov     rbx, rcx
0x18000ae28  call    ?CreateRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; CreateRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18000ae2d  test    eax, eax
0x18000ae2f  js      short loc_18000AE9F
0x18000ae31  mov     rcx, [rsp+28h+hKey]; hKey
0x18000ae36  lea     r8, [rsp+28h+arg_8]; unsigned int *
0x18000ae3b  call    ?GetRegSettingsInt@@YAJPEAUHKEY__@@PEBGPEAK@Z; GetRegSettingsInt(HKEY__ *,ushort const *,ulong *)
0x18000ae40  mov     edi, eax
0x18000ae42  test    eax, eax
0x18000ae44  jns     short loc_18000AE53
0x18000ae46  cmp     eax, 80070002h
0x18000ae4b  jnz     short loc_18000AE92
0x18000ae4d  mov     byte ptr [rbx+4], 0
0x18000ae51  jmp     short loc_18000AE65
0x18000ae53  mov     ecx, [rsp+28h+arg_8]
0x18000ae57  test    ecx, ecx
0x18000ae59  mov     [rbx], ecx
0x18000ae5b  setnz   al
0x18000ae5e  mov     [rbx+4], al
0x18000ae61  test    ecx, ecx
0x18000ae63  jnz     short loc_18000AE6B
0x18000ae65  mov     dword ptr [rbx], 0
0x18000ae6b  mov     rcx, [rsp+28h+hKey]; hKey
0x18000ae70  lea     r8, [rbx+6]; bool *
0x18000ae74  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x18000ae79  mov     edi, eax
0x18000ae7b  test    eax, eax
0x18000ae7d  jns     short loc_18000AE8E
0x18000ae7f  cmp     eax, 80070002h
0x18000ae84  jnz     short loc_18000AE92
0x18000ae86  mov     byte ptr [rbx+7], 0
0x18000ae8a  xor     edi, edi
0x18000ae8c  jmp     short loc_18000AE92
0x18000ae8e  mov     byte ptr [rbx+7], 1
0x18000ae92  mov     rcx, [rsp+28h+hKey]; hKey
0x18000ae97  call    cs:__imp_RegCloseKey
0x18000ae9d  mov     eax, edi
0x18000ae9f  mov     rbx, [rsp+28h+arg_0]
0x18000aea4  add     rsp, 20h
0x18000aea8  pop     rdi
0x18000aea9  retn
```
