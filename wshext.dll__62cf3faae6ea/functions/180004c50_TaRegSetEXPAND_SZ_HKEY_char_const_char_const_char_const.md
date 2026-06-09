# TaRegSetEXPAND_SZ(HKEY__ *,char const *,char const *,char const *)

- ea: `0x180004c50`
- end: `0x180004d20`
- name: `?TaRegSetEXPAND_SZ@@YAJPEAUHKEY__@@PEBD11@Z`
- size: `208`
- prototype: `int(HKEY, const char *, const char *, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000494c`
- `0x180004d28`

## callees

- `0x180004c50`

## import_xrefs

- `ADVAPI32!RegSetValueExA` at `0x180004cf3`
- `ADVAPI32!RegSetValueExA` at `0x180004cf3`
- `ADVAPI32!RegCreateKeyExA` at `0x180004ca0`
- `ADVAPI32!RegCreateKeyExA` at `0x180004ca0`
- `ADVAPI32!RegCloseKey` at `0x180004d00`
- `ADVAPI32!RegCloseKey` at `0x180004d00`

## pseudocode

```c
LSTATUS __fastcall TaRegSetEXPAND_SZ(HKEY a1, const char *a2, const char *a3, const BYTE *a4)
{
  LSTATUS result; // eax
  __int64 v7; // rax
  LSTATUS v8; // ebx
  DWORD v9; // [rsp+50h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-10h] BYREF

  hKey = 0;
  v9 = 0;
  result = RegCreateKeyExA(a1, a2, 0, 0, 0, 0x20006u, 0, &hKey, &v9);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    if ( a4 )
    {
      v7 = -1;
      do
        ++v7;
      while ( a4[v7] );
    }
    else
    {
      LODWORD(v7) = 0;
    }
    v8 = RegSetValueExA(hKey, a3, 0, Global::g_fWindowsNT + 1, a4, v7 + 1);
    RegCloseKey(hKey);
    if ( v8 > 0 )
      return (unsigned __int16)v8 | 0x80070000;
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180004c50  mov     r11, rsp
0x180004c53  mov     [r11+8], rbx
0x180004c57  push    rdi
0x180004c58  sub     rsp, 60h
0x180004c5c  lea     rax, [r11-18h]
0x180004c60  mov     qword ptr [r11-10h], 0
0x180004c68  mov     [r11-28h], rax
0x180004c6c  mov     rbx, r9
0x180004c6f  lea     rax, [r11-10h]
0x180004c73  mov     [rsp+68h+var_18], 0
0x180004c7b  mov     [r11-30h], rax
0x180004c7f  mov     rdi, r8
0x180004c82  mov     qword ptr [r11-38h], 0
0x180004c8a  xor     r9d, r9d; lpClass
0x180004c8d  mov     [rsp+68h+samDesired], 20006h; samDesired
0x180004c95  xor     r8d, r8d; Reserved
0x180004c98  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180004ca0  call    cs:__imp_RegCreateKeyExA
0x180004ca6  test    eax, eax
0x180004ca8  jz      short loc_180004CB6
0x180004caa  jle     short loc_180004D15
0x180004cac  movzx   eax, ax
0x180004caf  or      eax, 80070000h
0x180004cb4  jmp     short loc_180004D15
0x180004cb6  mov     al, cs:?g_fWindowsNT@Global@@2_NA; bool Global::g_fWindowsNT
0x180004cbc  neg     al
0x180004cbe  sbb     r9d, r9d
0x180004cc1  neg     r9d
0x180004cc4  inc     r9d; dwType
0x180004cc7  test    rbx, rbx
0x180004cca  jz      short loc_180004CDB
0x180004ccc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004cd0  inc     rax
0x180004cd3  cmp     byte ptr [rbx+rax], 0
0x180004cd7  jnz     short loc_180004CD0
0x180004cd9  jmp     short loc_180004CDD
0x180004cdb  xor     eax, eax
0x180004cdd  mov     rcx, [rsp+68h+hKey]; hKey
0x180004ce2  inc     eax
0x180004ce4  mov     [rsp+68h+samDesired], eax; cbData
0x180004ce8  xor     r8d, r8d; Reserved
0x180004ceb  mov     rdx, rdi; lpValueName
0x180004cee  mov     qword ptr [rsp+68h+dwOptions], rbx; lpData
0x180004cf3  call    cs:__imp_RegSetValueExA
0x180004cf9  mov     rcx, [rsp+68h+hKey]; hKey
0x180004cfe  mov     ebx, eax
0x180004d00  call    cs:__imp_RegCloseKey
0x180004d06  test    ebx, ebx
0x180004d08  jle     short loc_180004D13
0x180004d0a  movzx   ebx, bx
0x180004d0d  or      ebx, 80070000h
0x180004d13  mov     eax, ebx
0x180004d15  mov     rbx, [rsp+68h+arg_0]
0x180004d1a  add     rsp, 60h
0x180004d1e  pop     rdi
0x180004d1f  retn
```
