# CSettings::SaveToRegistry(HKEY__ *)

- ea: `0x18000af74`
- end: `0x18000affd`
- name: `?SaveToRegistry@CSettings@@QEAAJPEAUHKEY__@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(CSettings *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800076a0`

## callees

- `0x18000af74`
- `0x18000b574`
- `0x18000c33c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000afea`
- `ADVAPI32!RegCloseKey` at `0x18000afea`

## pseudocode

```c
int __fastcall CSettings::SaveToRegistry(CSettings *this, const unsigned __int16 *a2)
{
  int result; // eax
  int v4; // r8d
  signed int v5; // edi
  HKEY hKey; // [rsp+38h] [rbp+10h] BYREF

  hKey = 0;
  result = CreateRegSettings((HKEY)this, a2, 0x20006u, &hKey);
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
0x18000af74  mov     rax, rsp
0x18000af77  mov     [rax+8], rbx
0x18000af7b  mov     [rax+10h], rdx
0x18000af7f  push    rdi
0x18000af80  sub     rsp, 20h
0x18000af84  lea     r9, [rax+10h]; HKEY *
0x18000af88  mov     qword ptr [rax+10h], 0
0x18000af90  mov     r8d, 20006h; unsigned int
0x18000af96  mov     rbx, rcx
0x18000af99  call    ?CreateRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; CreateRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18000af9e  test    eax, eax
0x18000afa0  js      short loc_18000AFF2
0x18000afa2  cmp     byte ptr [rbx+4], 0
0x18000afa6  jz      short loc_18000AFAD
0x18000afa8  mov     r8d, [rbx]
0x18000afab  jmp     short loc_18000AFB0
0x18000afad  xor     r8d, r8d; unsigned int
0x18000afb0  mov     rcx, [rsp+28h+hKey]; hKey
0x18000afb5  lea     rdx, aTimeout; "Timeout"
0x18000afbc  call    ?PutRegSettingsInt@@YAJPEAUHKEY__@@PEBGK@Z; PutRegSettingsInt(HKEY__ *,ushort const *,ulong)
0x18000afc1  mov     edi, eax
0x18000afc3  test    eax, eax
0x18000afc5  js      short loc_18000AFE5
0x18000afc7  mov     rcx, [rsp+28h+hKey]; hKey
0x18000afcc  lea     rdx, aDisplaylogo; "DisplayLogo"
0x18000afd3  xor     r8d, r8d
0x18000afd6  cmp     [rbx+6], r8b
0x18000afda  setnz   r8b; unsigned int
0x18000afde  call    ?PutRegSettingsInt@@YAJPEAUHKEY__@@PEBGK@Z; PutRegSettingsInt(HKEY__ *,ushort const *,ulong)
0x18000afe3  mov     edi, eax
0x18000afe5  mov     rcx, [rsp+28h+hKey]; hKey
0x18000afea  call    cs:__imp_RegCloseKey
0x18000aff0  mov     eax, edi
0x18000aff2  mov     rbx, [rsp+28h+arg_0]
0x18000aff7  add     rsp, 20h
0x18000affb  pop     rdi
0x18000affc  retn
```
