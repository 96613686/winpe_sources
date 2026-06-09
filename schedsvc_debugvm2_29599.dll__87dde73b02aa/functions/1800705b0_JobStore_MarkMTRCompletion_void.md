# JobStore::MarkMTRCompletion(void)

- ea: `0x1800705b0`
- end: `0x180070666`
- name: `?MarkMTRCompletion@JobStore@@AEBAJXZ`
- size: `182`
- prototype: `__int64 __fastcall(JobStore *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006d788`

## callees

- `0x180021300`
- `0x1800705b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007063e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007063e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180070601`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180070601`

## string_xrefs

- `0x18007062a`: `MTRCompleted`

## pseudocode

```c
__int64 __fastcall JobStore::MarkMTRCompletion(JobStore *this)
{
  HKEY v1; // rcx
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  bool v4; // cc
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  v1 = (HKEY)*((_QWORD *)this + 2);
  hKey = 0;
  Data = 1;
  v2 = RegCreateKeyExW(v1, &ChannelPath, 0, 0, 0, 2u, 0, &hKey, 0);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 || (v2 = RegSetValueExW(hKey, L"MTRCompleted", 0, 4u, (const BYTE *)&Data, 4u), v3 = v2, v4 = v2 <= 0, v2) )
  {
    if ( !v4 )
      v3 = (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    dword_1800BDB40 = 1;
  }
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  return v3;
}

```

## disassembly

```asm
0x1800705b0  mov     r11, rsp
0x1800705b3  push    rbx
0x1800705b4  sub     rsp, 50h
0x1800705b8  mov     rcx, [rcx+10h]; hKey
0x1800705bc  lea     rax, [r11+10h]
0x1800705c0  mov     qword ptr [r11-18h], 0
0x1800705c8  lea     rdx, ChannelPath; lpSubKey
0x1800705cf  mov     [r11-20h], rax
0x1800705d3  xor     r9d, r9d; lpClass
0x1800705d6  mov     qword ptr [r11-28h], 0
0x1800705de  xor     r8d, r8d; Reserved
0x1800705e1  mov     [rsp+58h+samDesired], 2; samDesired
0x1800705e9  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800705f1  mov     qword ptr [r11+10h], 0
0x1800705f9  mov     [rsp+58h+Data], 1
0x180070601  call    cs:__imp_RegCreateKeyExW
0x180070607  mov     ebx, eax
0x180070609  test    eax, eax
0x18007060b  jz      short loc_18007061A
0x18007060d  jle     short loc_180070654
0x18007060f  movzx   ebx, ax
0x180070612  or      ebx, 80070000h
0x180070618  jmp     short loc_180070654
0x18007061a  mov     rcx, [rsp+58h+hKey]; hKey
0x18007061f  lea     rax, [rsp+58h+Data]
0x180070624  mov     r9d, 4; dwType
0x18007062a  lea     rdx, aMtrcompleted; "MTRCompleted"
0x180070631  mov     [rsp+58h+samDesired], r9d; cbData
0x180070636  xor     r8d, r8d; Reserved
0x180070639  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18007063e  call    cs:__imp_RegSetValueExW
0x180070644  mov     ebx, eax
0x180070646  test    eax, eax
0x180070648  jnz     short loc_18007060D
0x18007064a  mov     cs:dword_1800BDB40, 1
0x180070654  lea     rcx, [rsp+58h+hKey]; this
0x180070659  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18007065e  mov     eax, ebx
0x180070660  add     rsp, 50h
0x180070664  pop     rbx
0x180070665  retn
```
