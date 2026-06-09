# JobStore::MarkMTRCompletion(void)

- ea: `0x180073ec4`
- end: `0x180073f87`
- name: `?MarkMTRCompletion@JobStore@@AEBAJXZ`
- size: `195`
- prototype: `__int64 __fastcall(JobStore *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180070e78`

## callees

- `0x18002db40`
- `0x180073ec4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073f58`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073f58`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073f15`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073f15`

## string_xrefs

- `0x180073f44`: `MTRCompleted`

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
    dword_1800C1C2C = 1;
  }
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  return v3;
}

```

## disassembly

```asm
0x180073ec4  mov     r11, rsp
0x180073ec7  push    rbx
0x180073ec8  sub     rsp, 50h
0x180073ecc  mov     rcx, [rcx+10h]; hKey
0x180073ed0  lea     rax, [r11+10h]
0x180073ed4  mov     qword ptr [r11-18h], 0
0x180073edc  lea     rdx, ChannelPath; lpSubKey
0x180073ee3  mov     [r11-20h], rax
0x180073ee7  xor     r9d, r9d; lpClass
0x180073eea  mov     qword ptr [r11-28h], 0
0x180073ef2  xor     r8d, r8d; Reserved
0x180073ef5  mov     [rsp+58h+samDesired], 2; samDesired
0x180073efd  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180073f05  mov     qword ptr [r11+10h], 0
0x180073f0d  mov     [rsp+58h+Data], 1
0x180073f15  call    cs:__imp_RegCreateKeyExW
0x180073f1c  nop     dword ptr [rax+rax+00h]
0x180073f21  mov     ebx, eax
0x180073f23  test    eax, eax
0x180073f25  jz      short loc_180073F34
0x180073f27  jle     short loc_180073F74
0x180073f29  movzx   ebx, ax
0x180073f2c  or      ebx, 80070000h
0x180073f32  jmp     short loc_180073F74
0x180073f34  mov     rcx, [rsp+58h+hKey]; hKey
0x180073f39  lea     rax, [rsp+58h+Data]
0x180073f3e  mov     r9d, 4; dwType
0x180073f44  lea     rdx, aMtrcompleted; "MTRCompleted"
0x180073f4b  mov     [rsp+58h+samDesired], r9d; cbData
0x180073f50  xor     r8d, r8d; Reserved
0x180073f53  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180073f58  call    cs:__imp_RegSetValueExW
0x180073f5f  nop     dword ptr [rax+rax+00h]
0x180073f64  mov     ebx, eax
0x180073f66  test    eax, eax
0x180073f68  jnz     short loc_180073F27
0x180073f6a  mov     cs:dword_1800C1C2C, 1
0x180073f74  lea     rcx, [rsp+58h+hKey]; this
0x180073f79  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180073f7e  mov     eax, ebx
0x180073f80  add     rsp, 50h
0x180073f84  pop     rbx
0x180073f85  retn
```
