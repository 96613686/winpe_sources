# CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18000de30`
- end: `0x18000de8a`
- name: `?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `90`
- prototype: `__int64 __fastcall(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired)`
- caller_count: `23`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007420`
- `0x180008170`
- `0x180008300`
- `0x18000866c`
- `0x180008730`
- `0x180008900`
- `0x180008924`
- `0x180008b3c`
- `0x180008c30`
- `0x18000d690`
- `0x18000e780`
- `0x18000ea14`
- `0x18000ef58`
- `0x18000efbc`
- `0x18000f17c`
- `0x18000f610`
- `0x18000ffd0`
- `0x180010040`
- `0x180010228`
- `0x180010a5c`
- `0x180010d10`
- `0x180015bb4`
- `0x180015e74`

## callees

- `0x18000d5f0`
- `0x18000de30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000de64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000de64`

## pseudocode

```c
__int64 __fastcall CUwfRegKey::Open(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired)
{
  unsigned int v4; // ebx
  LSTATUS v9; // eax

  v4 = 0;
  if ( *phkResult )
    CUwfRegKey::Close(phkResult);
  v9 = RegOpenKeyExW(hKey, lpSubKey, 0, samDesired, phkResult);
  if ( v9 )
  {
    if ( v9 > 0 )
      return (unsigned __int16)v9 | 0x80070000;
    else
      return (unsigned int)v9;
  }
  return v4;
}

```

## disassembly

```asm
0x18000de30  push    rbx
0x18000de32  push    rbp
0x18000de33  push    rsi
0x18000de34  push    rdi
0x18000de35  push    r14
0x18000de37  sub     rsp, 30h
0x18000de3b  xor     ebx, ebx
0x18000de3d  mov     esi, r9d
0x18000de40  mov     rbp, r8
0x18000de43  mov     r14, rdx
0x18000de46  mov     rdi, rcx
0x18000de49  cmp     [rcx], rbx
0x18000de4c  jz      short loc_18000DE53
0x18000de4e  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18000de53  mov     r9d, esi; samDesired
0x18000de56  mov     [rsp+58h+phkResult], rdi; phkResult
0x18000de5b  xor     r8d, r8d; ulOptions
0x18000de5e  mov     rdx, rbp; lpSubKey
0x18000de61  mov     rcx, r14; hKey
0x18000de64  call    cs:__imp_RegOpenKeyExW
0x18000de6a  test    eax, eax
0x18000de6c  jz      short loc_18000DE7D
0x18000de6e  jg      short loc_18000DE74
0x18000de70  mov     ebx, eax
0x18000de72  jmp     short loc_18000DE7D
0x18000de74  movzx   ebx, ax
0x18000de77  or      ebx, 80070000h
0x18000de7d  mov     eax, ebx
0x18000de7f  add     rsp, 30h
0x18000de83  pop     r14
0x18000de85  pop     rdi
0x18000de86  pop     rsi
0x18000de87  pop     rbp
0x18000de88  pop     rbx
0x18000de89  retn
```
