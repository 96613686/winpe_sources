# JobStore::MarkHashingCompletion(void)

- ea: `0x1800704fc`
- end: `0x1800705aa`
- name: `?MarkHashingCompletion@JobStore@@AEBAJXZ`
- size: `174`
- prototype: `__int64 __fastcall(JobStore *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006d788`

## callees

- `0x180021300`
- `0x1800704fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007059a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007059a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007054d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007054d`

## string_xrefs

- `0x180070582`: `HashingCompleted`

## pseudocode

```c
__int64 __fastcall JobStore::MarkHashingCompletion(JobStore *this)
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
    v2 = RegSetValueExW(hKey, L"HashingCompleted", 0, 4u, (const BYTE *)&Data, 4u);
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
  wmi::AutoRegKey::Close(&hKey);
  return v3;
}

```

## disassembly

```asm
0x1800704fc  mov     r11, rsp
0x1800704ff  push    rbx
0x180070500  sub     rsp, 50h
0x180070504  mov     rcx, [rcx+10h]; hKey
0x180070508  lea     rax, [r11+10h]
0x18007050c  mov     qword ptr [r11-18h], 0
0x180070514  lea     rdx, ChannelPath; lpSubKey
0x18007051b  mov     [r11-20h], rax
0x18007051f  xor     r9d, r9d; lpClass
0x180070522  mov     qword ptr [r11-28h], 0
0x18007052a  xor     r8d, r8d; Reserved
0x18007052d  mov     [rsp+58h+samDesired], 2; samDesired
0x180070535  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18007053d  mov     qword ptr [r11+10h], 0
0x180070545  mov     [rsp+58h+Data], 1
0x18007054d  call    cs:__imp_RegCreateKeyExW
0x180070553  mov     ebx, eax
0x180070555  test    eax, eax
0x180070557  jz      short loc_180070576
0x180070559  jle     short loc_180070564
0x18007055b  movzx   ebx, ax
0x18007055e  or      ebx, 80070000h
0x180070564  lea     rcx, [rsp+58h+hKey]; this
0x180070569  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18007056e  mov     eax, ebx
0x180070570  add     rsp, 50h
0x180070574  pop     rbx
0x180070575  retn
0x180070576  mov     rcx, [rsp+58h+hKey]; hKey
0x18007057b  lea     rax, [rsp+58h+Data]
0x180070580  xor     ebx, ebx
0x180070582  lea     rdx, aHashingcomplet; "HashingCompleted"
0x180070589  xor     r8d, r8d; Reserved
0x18007058c  lea     r9d, [rbx+4]; dwType
0x180070590  mov     [rsp+58h+samDesired], r9d; cbData
0x180070595  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18007059a  call    cs:__imp_RegSetValueExW
0x1800705a0  test    eax, eax
0x1800705a2  jz      short loc_180070564
0x1800705a4  jg      short loc_18007055B
0x1800705a6  mov     ebx, eax
0x1800705a8  jmp     short loc_180070564
```
