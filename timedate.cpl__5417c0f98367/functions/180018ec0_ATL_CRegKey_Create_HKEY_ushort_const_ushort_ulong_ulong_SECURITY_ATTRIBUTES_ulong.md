# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x180018ec0`
- end: `0x180018f3f`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `127`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019fa0`

## callees

- `0x180018e94`
- `0x180018ec0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018f19`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018f19`

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
0x180018ec0  mov     r11, rsp
0x180018ec3  mov     [r11+20h], r9
0x180018ec7  push    rbx
0x180018ec8  sub     rsp, 50h
0x180018ecc  mov     rbx, rcx
0x180018ecf  mov     dword ptr [r11+28h], 0
0x180018ed7  lea     rcx, [r11+28h]
0x180018edb  mov     qword ptr [r11+20h], 0
0x180018ee3  mov     [r11-18h], rcx
0x180018ee7  mov     rax, r8
0x180018eea  lea     rcx, [r11+20h]
0x180018eee  mov     r10, rdx
0x180018ef1  mov     [r11-20h], rcx
0x180018ef5  xor     r9d, r9d; lpClass
0x180018ef8  mov     qword ptr [r11-28h], 0
0x180018f00  xor     r8d, r8d; Reserved
0x180018f03  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180018f0b  mov     rdx, rax; lpSubKey
0x180018f0e  mov     rcx, r10; hKey
0x180018f11  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180018f19  call    cs:__imp_RegCreateKeyExW
0x180018f1f  mov     ecx, eax
0x180018f21  test    eax, eax
0x180018f23  jnz     short loc_180018F37
0x180018f25  mov     rcx, rbx; this
0x180018f28  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180018f2d  mov     ecx, eax
0x180018f2f  mov     rax, [rsp+58h+arg_18]
0x180018f34  mov     [rbx], rax
0x180018f37  mov     eax, ecx
0x180018f39  add     rsp, 50h
0x180018f3d  pop     rbx
0x180018f3e  retn
```
