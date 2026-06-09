# IsFullscreenCXHRunning(void)

- ea: `0x140020c64`
- end: `0x140020cfc`
- name: `?IsFullscreenCXHRunning@@YA_NXZ`
- size: `152`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002116c`

## callees

- `0x140016dc8`
- `0x140020c64`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140020c9a`
- `ADVAPI32!RegOpenKeyExW` at `0x140020c9a`
- `ADVAPI32!RegCloseKey` at `0x140020cdd`
- `ADVAPI32!RegCloseKey` at `0x140020cdd`

## pseudocode

```c
bool IsFullscreenCXHRunning(void)
{
  LSTATUS v0; // eax
  unsigned int v1; // r9d
  bool v2; // sf
  bool result; // al
  int v4; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  hKey = 0;
  v0 = RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost",
         0,
         0x20019u,
         &hKey);
  v2 = v0 < 0;
  if ( v0 > 0 )
    v2 = 1;
  result = 0;
  if ( !v2 )
  {
    SHRegGetBOOLWithREGSAM(hKey, L"Fullscreen", L"FullscreenCXHRunning", v1, &v4);
    RegCloseKey(hKey);
    if ( v4 )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x140020c64  sub     rsp, 38h
0x140020c68  lea     rax, [rsp+38h+hKey]
0x140020c6d  mov     [rsp+38h+arg_0], 0
0x140020c75  mov     r9d, 20019h; samDesired
0x140020c7b  mov     [rsp+38h+phkResult], rax; phkResult
0x140020c80  xor     r8d, r8d; ulOptions
0x140020c83  mov     [rsp+38h+hKey], 0
0x140020c8c  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140020c93  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140020c9a  call    cs:__imp_RegOpenKeyExW
0x140020ca1  nop     dword ptr [rax+rax+00h]
0x140020ca6  test    eax, eax
0x140020ca8  jle     short loc_140020CB4
0x140020caa  movzx   eax, ax
0x140020cad  or      eax, 80070000h
0x140020cb2  test    eax, eax
0x140020cb4  js      short loc_140020CF4
0x140020cb6  mov     rcx, [rsp+38h+hKey]; HKEY
0x140020cbb  lea     rax, [rsp+38h+arg_0]
0x140020cc0  lea     r8, aFullscreencxhr; "FullscreenCXHRunning"
0x140020cc7  mov     [rsp+38h+phkResult], rax; int *
0x140020ccc  lea     rdx, aFullscreen; "Fullscreen"
0x140020cd3  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x140020cd8  mov     rcx, [rsp+38h+hKey]; hKey
0x140020cdd  call    cs:__imp_RegCloseKey
0x140020ce4  nop     dword ptr [rax+rax+00h]
0x140020ce9  cmp     [rsp+38h+arg_0], 0
0x140020cee  jz      short loc_140020CF4
0x140020cf0  mov     al, 1
0x140020cf2  jmp     short loc_140020CF6
0x140020cf4  xor     al, al
0x140020cf6  add     rsp, 38h
0x140020cfa  retn
```
