# CRegUtilT<ushort *,CRegType,0,1>::RegOpenKeyAccess64BitView<1>(HKEY__ *,ushort const *,ulong,HKEY__ * *)

- ea: `0x18003aea0`
- end: `0x18003af2d`
- name: `??$RegOpenKeyAccess64BitView@$00@?$CRegUtilT@PEAGUCRegType@@$0A@$00@@CAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b354`

## callees

- `0x180003520`
- `0x180004288`
- `0x18003aea0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003af18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003af18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003aecf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003aecf`

## pseudocode

```c
__int64 __fastcall CRegUtilT<unsigned short *,CRegType,0,1>::RegOpenKeyAccess64BitView<1>(
        HKEY a1,
        __int64 a2,
        __int64 a3,
        HKEY *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v5 = RegOpenKeyExW(a1, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SoftwareProtectionPlatform", 0, 1u, &hKey);
  if ( v5 )
  {
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    v6 = v5;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v5);
  }
  else
  {
    *a4 = hKey;
    v6 = 0;
    hKey = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x18003aea0  mov     r11, rsp
0x18003aea3  mov     [r11+10h], rdx
0x18003aea7  push    rbx
0x18003aea8  sub     rsp, 30h
0x18003aeac  mov     rbx, r9
0x18003aeaf  mov     qword ptr [r11+10h], 0
0x18003aeb7  lea     rax, [r11+10h]
0x18003aebb  mov     r9d, 1; samDesired
0x18003aec1  xor     r8d, r8d; ulOptions
0x18003aec4  mov     [r11-18h], rax
0x18003aec8  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003aecf  call    cs:__imp_RegOpenKeyExW
0x18003aed6  nop     dword ptr [rax+rax+00h]
0x18003aedb  test    eax, eax
0x18003aedd  jz      short loc_18003AEF4
0x18003aedf  jle     short loc_18003AEE9
0x18003aee1  movzx   eax, ax
0x18003aee4  or      eax, 80070000h
0x18003aee9  mov     ecx, eax
0x18003aeeb  mov     ebx, eax
0x18003aeed  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003aef2  jmp     short loc_18003AF07
0x18003aef4  mov     rax, [rsp+38h+hKey]
0x18003aef9  mov     [rbx], rax
0x18003aefc  xor     ebx, ebx
0x18003aefe  mov     [rsp+38h+hKey], 0
0x18003af07  mov     ecx, ebx
0x18003af09  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003af0e  mov     rcx, [rsp+38h+hKey]; hKey
0x18003af13  test    rcx, rcx
0x18003af16  jz      short loc_18003AF24
0x18003af18  call    cs:__imp_RegCloseKey
0x18003af1f  nop     dword ptr [rax+rax+00h]
0x18003af24  mov     eax, ebx
0x18003af26  add     rsp, 30h
0x18003af2a  pop     rbx
0x18003af2b  retn
```
