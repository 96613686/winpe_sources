# JobStore::MarkPermissionsRestoreCompletion(void)

- ea: `0x180074054`
- end: `0x18007410f`
- name: `?MarkPermissionsRestoreCompletion@JobStore@@AEBAJXZ`
- size: `187`
- prototype: `__int64 __fastcall(JobStore *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180070e78`

## callees

- `0x18002db40`
- `0x180074054`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800740f9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800740f9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800740a5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800740a5`

## string_xrefs

- `0x1800740e1`: `OwnUpdateCompleted`

## pseudocode

```c
__int64 __fastcall JobStore::MarkPermissionsRestoreCompletion(JobStore *this)
{
  HKEY v1; // rcx
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  v1 = (HKEY)*((_QWORD *)this + 2);
  hKey = 0;
  Data = 1;
  v2 = RegCreateKeyExW(v1, &ChannelPath, 0, 0, 0, 2u, 0, &hKey, 0);
  v3 = v2;
  if ( !v2 )
  {
    v3 = 0;
    v2 = RegSetValueExW(hKey, L"OwnUpdateCompleted", 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v2 )
      goto LABEL_4;
    if ( v2 <= 0 )
    {
      v3 = v2;
      goto LABEL_4;
    }
    goto LABEL_3;
  }
  if ( v2 > 0 )
LABEL_3:
    v3 = (unsigned __int16)v2 | 0x80070000;
LABEL_4:
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  return v3;
}

```

## disassembly

```asm
0x180074054  mov     r11, rsp
0x180074057  push    rbx
0x180074058  sub     rsp, 50h
0x18007405c  mov     rcx, [rcx+10h]; hKey
0x180074060  lea     rax, [r11+10h]
0x180074064  mov     qword ptr [r11-18h], 0
0x18007406c  lea     rdx, ChannelPath; lpSubKey
0x180074073  mov     [r11-20h], rax
0x180074077  xor     r9d, r9d; lpClass
0x18007407a  mov     qword ptr [r11-28h], 0
0x180074082  xor     r8d, r8d; Reserved
0x180074085  mov     [rsp+58h+samDesired], 2; samDesired
0x18007408d  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180074095  mov     qword ptr [r11+10h], 0
0x18007409d  mov     [rsp+58h+Data], 1
0x1800740a5  call    cs:__imp_RegCreateKeyExW
0x1800740ac  nop     dword ptr [rax+rax+00h]
0x1800740b1  mov     ebx, eax
0x1800740b3  test    eax, eax
0x1800740b5  jz      short loc_1800740D5
0x1800740b7  jle     short loc_1800740C2
0x1800740b9  movzx   ebx, ax
0x1800740bc  or      ebx, 80070000h
0x1800740c2  lea     rcx, [rsp+58h+hKey]; this
0x1800740c7  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800740cc  mov     eax, ebx
0x1800740ce  add     rsp, 50h
0x1800740d2  pop     rbx
0x1800740d3  retn
0x1800740d5  mov     rcx, [rsp+58h+hKey]; hKey
0x1800740da  lea     rax, [rsp+58h+Data]
0x1800740df  xor     ebx, ebx
0x1800740e1  lea     rdx, aOwnupdatecompl; "OwnUpdateCompleted"
0x1800740e8  xor     r8d, r8d; Reserved
0x1800740eb  lea     r9d, [rbx+4]; dwType
0x1800740ef  mov     [rsp+58h+samDesired], r9d; cbData
0x1800740f4  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800740f9  call    cs:__imp_RegSetValueExW
0x180074100  nop     dword ptr [rax+rax+00h]
0x180074105  test    eax, eax
0x180074107  jz      short loc_1800740C2
0x180074109  jg      short loc_1800740B9
0x18007410b  mov     ebx, eax
0x18007410d  jmp     short loc_1800740C2
```
