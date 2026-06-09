# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x140003124`
- end: `0x1400031a9`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `133`
- prototype: `int(ATL::CRegKey *__hidden this, HKEY, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004190`

## callees

- `0x140003124`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140003191`
- `ADVAPI32!RegCloseKey` at `0x140003191`
- `ADVAPI32!RegCreateKeyExW` at `0x14000317d`
- `ADVAPI32!RegCreateKeyExW` at `0x14000317d`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(
        HKEY *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  unsigned int v6; // ecx
  HKEY v8; // [rsp+78h] [rbp+20h] BYREF

  a5 = 0;
  v8 = 0;
  v6 = RegCreateKeyExW(a2, a3, 0, 0, 0, 0x2001Fu, 0, &v8, &a5);
  if ( !v6 )
  {
    if ( *this )
      v6 = RegCloseKey(*this);
    *this = v8;
  }
  return v6;
}

```

## disassembly

```asm
0x140003124  mov     r11, rsp
0x140003127  mov     [r11+20h], r9
0x14000312b  push    rbx
0x14000312c  sub     rsp, 50h
0x140003130  mov     rbx, rcx
0x140003133  mov     dword ptr [r11+28h], 0
0x14000313b  lea     rcx, [r11+28h]
0x14000313f  mov     qword ptr [r11+20h], 0
0x140003147  mov     [r11-18h], rcx
0x14000314b  mov     rax, r8
0x14000314e  lea     rcx, [r11+20h]
0x140003152  mov     r10, rdx
0x140003155  mov     [r11-20h], rcx
0x140003159  xor     r9d, r9d; lpClass
0x14000315c  mov     qword ptr [r11-28h], 0
0x140003164  xor     r8d, r8d; Reserved
0x140003167  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x14000316f  mov     rdx, rax; lpSubKey
0x140003172  mov     rcx, r10; hKey
0x140003175  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14000317d  call    cs:__imp_RegCreateKeyExW
0x140003183  mov     ecx, eax
0x140003185  test    eax, eax
0x140003187  jnz     short loc_1400031A1
0x140003189  cmp     [rbx], rcx
0x14000318c  jz      short loc_140003199
0x14000318e  mov     rcx, [rbx]; hKey
0x140003191  call    cs:__imp_RegCloseKey
0x140003197  mov     ecx, eax
0x140003199  mov     rax, [rsp+58h+arg_18]
0x14000319e  mov     [rbx], rax
0x1400031a1  mov     eax, ecx
0x1400031a3  add     rsp, 50h
0x1400031a7  pop     rbx
0x1400031a8  retn
```
