# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x180006080`
- end: `0x1800060ff`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `127`
- prototype: `__int64 __fastcall(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d678`

## callees

- `0x180005de4`
- `0x180006080`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800060d9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800060d9`

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
0x180006080  mov     r11, rsp
0x180006083  mov     [r11+20h], r9
0x180006087  push    rbx
0x180006088  sub     rsp, 50h
0x18000608c  mov     rbx, rcx
0x18000608f  mov     dword ptr [r11+28h], 0
0x180006097  lea     rcx, [r11+28h]
0x18000609b  mov     qword ptr [r11+20h], 0
0x1800060a3  mov     [r11-18h], rcx
0x1800060a7  mov     rax, r8
0x1800060aa  lea     rcx, [r11+20h]
0x1800060ae  mov     r10, rdx
0x1800060b1  mov     [r11-20h], rcx
0x1800060b5  xor     r9d, r9d; lpClass
0x1800060b8  mov     qword ptr [r11-28h], 0
0x1800060c0  xor     r8d, r8d; Reserved
0x1800060c3  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x1800060cb  mov     rdx, rax; lpSubKey
0x1800060ce  mov     rcx, r10; hKey
0x1800060d1  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800060d9  call    cs:__imp_RegCreateKeyExW
0x1800060df  mov     ecx, eax
0x1800060e1  test    eax, eax
0x1800060e3  jnz     short loc_1800060F7
0x1800060e5  mov     rcx, rbx; this
0x1800060e8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800060ed  mov     ecx, eax
0x1800060ef  mov     rax, [rsp+58h+arg_18]
0x1800060f4  mov     [rbx], rax
0x1800060f7  mov     eax, ecx
0x1800060f9  add     rsp, 50h
0x1800060fd  pop     rbx
0x1800060fe  retn
```
