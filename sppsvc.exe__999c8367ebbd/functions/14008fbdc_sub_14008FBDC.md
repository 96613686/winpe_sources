# sub_14008FBDC

- ea: `0x14008fbdc`
- end: `0x14008fcab`
- name: `sub_14008FBDC`
- size: `207`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, const BYTE *, DWORD cbData)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140091b60`

## callees

- `0x14006a02c`
- `0x14006ad88`
- `0x14006de60`
- `0x14007cfb4`
- `0x14007ff54`
- `0x14008fbdc`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14008fc59`
- `ADVAPI32!RegSetValueExW` at `0x14008fc59`

## pseudocode

```c
__int64 __fastcall sub_14008FBDC(__int64 a1, const WCHAR *a2, __int64 a3, const BYTE *a4, DWORD cbData)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  LSTATUS v9; // eax
  _QWORD v11[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  hKey = 0;
  v11[0] = 0;
  v12 = 0;
  v6 = sub_14006A02C(HKEY_USERS, a2, 2u, &hKey);
  v7 = v6;
  if ( v6 >= 0 )
  {
    sub_14007CFB4(0);
    v9 = RegSetValueExW(hKey, L"Value", 0, 3u, a4, cbData);
    v7 = v9;
    if ( !v9 )
    {
      v7 = 0;
      goto LABEL_9;
    }
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
    v8 = v7;
  }
  else
  {
    v8 = (unsigned int)v6;
  }
  sub_14006DE60(v8);
LABEL_9:
  sub_14007CFB4(v7);
  sub_14006AD88(&v12);
  sub_14007FF54(v11);
  sub_14007FF54(&hKey);
  return v7;
}

```

## disassembly

```asm
0x14008fbdc  mov     rax, rsp
0x14008fbdf  mov     [rax+10h], rbx
0x14008fbe3  mov     [rax+18h], r8
0x14008fbe7  mov     [rax+8], rcx
0x14008fbeb  push    rdi
0x14008fbec  sub     rsp, 40h
0x14008fbf0  mov     rdi, r9
0x14008fbf3  mov     qword ptr [rax+18h], 0
0x14008fbfb  lea     r9, [rax+18h]
0x14008fbff  mov     qword ptr [rax-18h], 0
0x14008fc07  mov     rcx, 0FFFFFFFF80000003h
0x14008fc0e  mov     qword ptr [rax+8], 0
0x14008fc16  mov     r8d, 2
0x14008fc1c  call    sub_14006A02C
0x14008fc21  mov     ebx, eax
0x14008fc23  test    eax, eax
0x14008fc25  jns     short loc_14008FC30
0x14008fc27  mov     ecx, eax
0x14008fc29  call    sub_14006DE60
0x14008fc2e  jmp     short loc_14008FC78
0x14008fc30  xor     ecx, ecx
0x14008fc32  call    sub_14007CFB4
0x14008fc37  mov     eax, [rsp+48h+arg_20]
0x14008fc3b  lea     rdx, aValue; "Value"
0x14008fc42  mov     rcx, [rsp+48h+hKey]; hKey
0x14008fc47  mov     r9d, 3; dwType
0x14008fc4d  mov     [rsp+48h+cbData], eax; cbData
0x14008fc51  xor     r8d, r8d; Reserved
0x14008fc54  mov     [rsp+48h+lpData], rdi; lpData
0x14008fc59  call    cs:RegSetValueExW
0x14008fc5f  mov     ebx, eax
0x14008fc61  test    eax, eax
0x14008fc63  jz      short loc_14008FC76
0x14008fc65  test    eax, eax
0x14008fc67  jle     short loc_14008FC72
0x14008fc69  movzx   ebx, bx
0x14008fc6c  or      ebx, 80070000h
0x14008fc72  mov     ecx, ebx
0x14008fc74  jmp     short loc_14008FC29
0x14008fc76  xor     ebx, ebx
0x14008fc78  mov     ecx, ebx
0x14008fc7a  call    sub_14007CFB4
0x14008fc7f  lea     rcx, [rsp+48h+arg_0]
0x14008fc84  call    sub_14006AD88
0x14008fc89  lea     rcx, [rsp+48h+var_18]
0x14008fc8e  call    sub_14007FF54
0x14008fc93  lea     rcx, [rsp+48h+hKey]
0x14008fc98  call    sub_14007FF54
0x14008fc9d  mov     eax, ebx
0x14008fc9f  mov     rbx, [rsp+48h+arg_8]
0x14008fca4  add     rsp, 40h
0x14008fca8  pop     rdi
0x14008fca9  retn
```
