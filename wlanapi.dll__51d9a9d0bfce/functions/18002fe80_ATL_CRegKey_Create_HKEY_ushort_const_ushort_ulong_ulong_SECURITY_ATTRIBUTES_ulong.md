# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x18002fe80`
- end: `0x18002feff`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `127`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030acc`

## callees

- `0x18002fe54`
- `0x18002fe80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002fed9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002fed9`

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
0x18002fe80  mov     r11, rsp
0x18002fe83  mov     [r11+20h], r9
0x18002fe87  push    rbx
0x18002fe88  sub     rsp, 50h
0x18002fe8c  mov     rbx, rcx
0x18002fe8f  mov     dword ptr [r11+28h], 0
0x18002fe97  lea     rcx, [r11+28h]
0x18002fe9b  mov     qword ptr [r11+20h], 0
0x18002fea3  mov     [r11-18h], rcx
0x18002fea7  mov     rax, r8
0x18002feaa  lea     rcx, [r11+20h]
0x18002feae  mov     r10, rdx
0x18002feb1  mov     [r11-20h], rcx
0x18002feb5  xor     r9d, r9d; lpClass
0x18002feb8  mov     qword ptr [r11-28h], 0
0x18002fec0  xor     r8d, r8d; Reserved
0x18002fec3  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18002fecb  mov     rdx, rax; lpSubKey
0x18002fece  mov     rcx, r10; hKey
0x18002fed1  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18002fed9  call    cs:__imp_RegCreateKeyExW
0x18002fedf  mov     ecx, eax
0x18002fee1  test    eax, eax
0x18002fee3  jnz     short loc_18002FEF7
0x18002fee5  mov     rcx, rbx; this
0x18002fee8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002feed  mov     ecx, eax
0x18002feef  mov     rax, [rsp+58h+arg_18]
0x18002fef4  mov     [rbx], rax
0x18002fef7  mov     eax, ecx
0x18002fef9  add     rsp, 50h
0x18002fefd  pop     rbx
0x18002fefe  retn
```
