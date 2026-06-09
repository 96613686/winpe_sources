# CSettings::SaveToRegistry(HKEY__ *)

- ea: `0x140010e30`
- end: `0x140010ec7`
- name: `?SaveToRegistry@CSettings@@QEAAJPEAUHKEY__@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(CSettings *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000919c`

## callees

- `0x140010e30`
- `0x140014eb0`
- `0x140015bc0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140010eb4`
- `ADVAPI32!RegCloseKey` at `0x140010eb4`

## pseudocode

```c
signed int __fastcall CSettings::SaveToRegistry(CSettings *this, HKEY a2)
{
  signed int result; // eax
  int v4; // r8d
  signed int v5; // edi
  HKEY hKey; // [rsp+38h] [rbp+10h] BYREF

  hKey = 0;
  result = CreateRegSettings(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows Script Host\\Settings", 0x20006u, &hKey);
  if ( result >= 0 )
  {
    if ( *((_BYTE *)this + 4) )
      v4 = *(_DWORD *)this;
    else
      v4 = 0;
    v5 = PutRegSettingsInt(hKey, L"Timeout", v4);
    if ( v5 >= 0 )
      v5 = PutRegSettingsInt(hKey, L"DisplayLogo", *((_BYTE *)this + 6) != 0);
    RegCloseKey(hKey);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x140010e30  mov     rax, rsp
0x140010e33  mov     [rax+8], rbx
0x140010e37  mov     [rax+10h], rdx
0x140010e3b  push    rdi
0x140010e3c  sub     rsp, 20h
0x140010e40  mov     rbx, rcx
0x140010e43  mov     qword ptr [rax+10h], 0
0x140010e4b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140010e52  lea     r9, [rax+10h]; phkResult
0x140010e56  mov     r8d, 20006h; samDesired
0x140010e5c  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows Script Hos"...
0x140010e63  call    ?CreateRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; CreateRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x140010e68  test    eax, eax
0x140010e6a  js      short loc_140010EBC
0x140010e6c  cmp     byte ptr [rbx+4], 0
0x140010e70  jz      short loc_140010E77
0x140010e72  mov     r8d, [rbx]
0x140010e75  jmp     short loc_140010E7A
0x140010e77  xor     r8d, r8d; unsigned int
0x140010e7a  mov     rcx, [rsp+28h+hKey]; hKey
0x140010e7f  lea     rdx, aTimeout; "Timeout"
0x140010e86  call    ?PutRegSettingsInt@@YAJPEAUHKEY__@@PEBGK@Z; PutRegSettingsInt(HKEY__ *,ushort const *,ulong)
0x140010e8b  mov     edi, eax
0x140010e8d  test    eax, eax
0x140010e8f  js      short loc_140010EAF
0x140010e91  mov     rcx, [rsp+28h+hKey]; hKey
0x140010e96  lea     rdx, aDisplaylogo; "DisplayLogo"
0x140010e9d  xor     r8d, r8d
0x140010ea0  cmp     [rbx+6], r8b
0x140010ea4  setnz   r8b; unsigned int
0x140010ea8  call    ?PutRegSettingsInt@@YAJPEAUHKEY__@@PEBGK@Z; PutRegSettingsInt(HKEY__ *,ushort const *,ulong)
0x140010ead  mov     edi, eax
0x140010eaf  mov     rcx, [rsp+28h+hKey]; hKey
0x140010eb4  call    cs:__imp_RegCloseKey
0x140010eba  mov     eax, edi
0x140010ebc  mov     rbx, [rsp+28h+arg_0]
0x140010ec1  add     rsp, 20h
0x140010ec5  pop     rdi
0x140010ec6  retn
```
