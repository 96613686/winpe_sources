# CSxGlobalTracer::_ReadRegistry(HINSTANCE__ *)

- ea: `0x1800267b4`
- end: `0x18002686d`
- name: `?_ReadRegistry@CSxGlobalTracer@@AEAAJPEAUHINSTANCE__@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(CSxGlobalTracer *__hidden this, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180026004`

## callees

- `0x180026284`
- `0x1800267b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026860`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026860`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800267ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800267ea`

## string_xrefs

- `0x1800267dc`: `SYSTEM\CurrentControlSet\Services\SPP\Debug\Tracing`

## pseudocode

```c
__int64 __fastcall CSxGlobalTracer::_ReadRegistry(CSxGlobalTracer *this, HINSTANCE a2)
{
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  HINSTANCE v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = a2;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\SPP\\Debug\\Tracing",
          0,
          0x20019u,
          &hKey) )
  {
    LODWORD(v4) = 0;
    if ( (int)QueryDWORDValue(hKey, &v4, L"TrackFailure") >= 0 && ((int)v4 < 0 || (_DWORD)v4 == 1) )
      dword_1800421E4 = (int)v4;
    LODWORD(v4) = 0;
    if ( (int)QueryDWORDValue(hKey, &v4, L"BreakOnTrackedError") >= 0 )
      dword_1800421E8 = (_DWORD)v4 != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800267b4  mov     r11, rsp
0x1800267b7  mov     [r11+10h], rdx
0x1800267bb  mov     [r11+8], rcx
0x1800267bf  sub     rsp, 38h
0x1800267c3  lea     rax, [r11+8]
0x1800267c7  mov     qword ptr [r11+8], 0
0x1800267cf  mov     r9d, 20019h; samDesired
0x1800267d5  mov     [r11-18h], rax
0x1800267d9  xor     r8d, r8d; ulOptions
0x1800267dc  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\SP"...
0x1800267e3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800267ea  call    cs:__imp_RegOpenKeyExW
0x1800267f0  test    eax, eax
0x1800267f2  jnz     short loc_180026856
0x1800267f4  mov     rcx, [rsp+38h+hKey]
0x1800267f9  lea     r8, aTrackfailure; "TrackFailure"
0x180026800  lea     rdx, [rsp+38h+arg_8]
0x180026805  mov     dword ptr [rsp+38h+arg_8], eax
0x180026809  call    QueryDWORDValue
0x18002680e  test    eax, eax
0x180026810  js      short loc_180026825
0x180026812  mov     eax, dword ptr [rsp+38h+arg_8]
0x180026816  test    eax, eax
0x180026818  js      short loc_18002681F
0x18002681a  cmp     eax, 1
0x18002681d  jnz     short loc_180026825
0x18002681f  mov     cs:dword_1800421E4, eax
0x180026825  mov     rcx, [rsp+38h+hKey]
0x18002682a  lea     r8, aBreakontracked; "BreakOnTrackedError"
0x180026831  lea     rdx, [rsp+38h+arg_8]
0x180026836  mov     dword ptr [rsp+38h+arg_8], 0
0x18002683e  call    QueryDWORDValue
0x180026843  test    eax, eax
0x180026845  js      short loc_180026856
0x180026847  xor     eax, eax
0x180026849  cmp     dword ptr [rsp+38h+arg_8], eax
0x18002684d  setnz   al
0x180026850  mov     cs:dword_1800421E8, eax
0x180026856  mov     rcx, [rsp+38h+hKey]; hKey
0x18002685b  test    rcx, rcx
0x18002685e  jz      short loc_180026866
0x180026860  call    cs:__imp_RegCloseKey
0x180026866  xor     eax, eax
0x180026868  add     rsp, 38h
0x18002686c  retn
```
