# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x180006b00`
- end: `0x180006b7f`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `127`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800078ec`

## callees

- `0x180006ad4`
- `0x180006b00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006b59`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006b59`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(
        ATL::CRegKey *this,
        HKEY hKey,
        LPCWSTR lpSubKey,
        unsigned __int16 *a4,
        unsigned int a5)
{
  unsigned int v6; // ecx
  HKEY v8; // [rsp+78h] [rbp+20h] BYREF

  a5 = 0;
  v8 = 0;
  v6 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &v8, &a5);
  if ( !v6 )
  {
    v6 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = v8;
  }
  return v6;
}

```

## disassembly

```asm
0x180006b00  mov     r11, rsp
0x180006b03  mov     [r11+20h], r9
0x180006b07  push    rbx
0x180006b08  sub     rsp, 50h
0x180006b0c  mov     rbx, rcx
0x180006b0f  mov     dword ptr [r11+28h], 0
0x180006b17  lea     rcx, [r11+28h]
0x180006b1b  mov     qword ptr [r11+20h], 0
0x180006b23  mov     [r11-18h], rcx
0x180006b27  mov     rax, r8
0x180006b2a  lea     rcx, [r11+20h]
0x180006b2e  mov     r10, rdx
0x180006b31  mov     [r11-20h], rcx
0x180006b35  xor     r9d, r9d; lpClass
0x180006b38  mov     qword ptr [r11-28h], 0
0x180006b40  xor     r8d, r8d; Reserved
0x180006b43  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180006b4b  mov     rdx, rax; lpSubKey
0x180006b4e  mov     rcx, r10; hKey
0x180006b51  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180006b59  call    cs:__imp_RegCreateKeyExW
0x180006b5f  mov     ecx, eax
0x180006b61  test    eax, eax
0x180006b63  jnz     short loc_180006B77
0x180006b65  mov     rcx, rbx; this
0x180006b68  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180006b6d  mov     ecx, eax
0x180006b6f  mov     rax, [rsp+58h+arg_18]
0x180006b74  mov     [rbx], rax
0x180006b77  mov     eax, ecx
0x180006b79  add     rsp, 50h
0x180006b7d  pop     rbx
0x180006b7e  retn
```
