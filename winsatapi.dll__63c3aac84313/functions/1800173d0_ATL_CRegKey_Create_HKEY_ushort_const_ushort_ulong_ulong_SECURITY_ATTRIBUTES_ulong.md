# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x1800173d0`
- end: `0x18001744f`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `127`
- prototype: `__int64 __fastcall(HKEY *this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a0e0`
- `0x18001ed98`
- `0x180020784`

## callees

- `0x1800173a4`
- `0x1800173d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017429`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017429`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(HKEY *this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *a4, unsigned int a5)
{
  unsigned int v6; // ecx
  HKEY v8; // [rsp+78h] [rbp+20h] BYREF

  a5 = 0;
  v8 = 0;
  v6 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &v8, &a5);
  if ( !v6 )
  {
    v6 = ATL::CRegKey::Close(this);
    *this = v8;
  }
  return v6;
}

```

## disassembly

```asm
0x1800173d0  mov     r11, rsp
0x1800173d3  mov     [r11+20h], r9
0x1800173d7  push    rbx
0x1800173d8  sub     rsp, 50h
0x1800173dc  mov     rbx, rcx
0x1800173df  mov     dword ptr [r11+28h], 0
0x1800173e7  lea     rcx, [r11+28h]
0x1800173eb  mov     qword ptr [r11+20h], 0
0x1800173f3  mov     [r11-18h], rcx
0x1800173f7  mov     rax, r8
0x1800173fa  lea     rcx, [r11+20h]
0x1800173fe  mov     r10, rdx
0x180017401  mov     [r11-20h], rcx
0x180017405  xor     r9d, r9d; lpClass
0x180017408  mov     qword ptr [r11-28h], 0
0x180017410  xor     r8d, r8d; Reserved
0x180017413  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18001741b  mov     rdx, rax; lpSubKey
0x18001741e  mov     rcx, r10; hKey
0x180017421  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180017429  call    cs:__imp_RegCreateKeyExW
0x18001742f  mov     ecx, eax
0x180017431  test    eax, eax
0x180017433  jnz     short loc_180017447
0x180017435  mov     rcx, rbx; this
0x180017438  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001743d  mov     ecx, eax
0x18001743f  mov     rax, [rsp+58h+arg_18]
0x180017444  mov     [rbx], rax
0x180017447  mov     eax, ecx
0x180017449  add     rsp, 50h
0x18001744d  pop     rbx
0x18001744e  retn
```
