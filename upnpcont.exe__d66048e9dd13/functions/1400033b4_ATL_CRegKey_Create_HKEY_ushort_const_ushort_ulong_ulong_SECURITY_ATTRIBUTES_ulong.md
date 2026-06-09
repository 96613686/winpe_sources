# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x1400033b4`
- end: `0x140003439`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `133`
- prototype: `__int64 __fastcall(HKEY *this, HKEY, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003a88`
- `0x140004954`

## callees

- `0x1400033b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000340d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000340d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003421`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003421`

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
0x1400033b4  mov     r11, rsp
0x1400033b7  mov     [r11+20h], r9
0x1400033bb  push    rbx
0x1400033bc  sub     rsp, 50h
0x1400033c0  mov     rbx, rcx
0x1400033c3  mov     dword ptr [r11+28h], 0
0x1400033cb  lea     rcx, [r11+28h]
0x1400033cf  mov     qword ptr [r11+20h], 0
0x1400033d7  mov     [r11-18h], rcx
0x1400033db  mov     rax, r8
0x1400033de  lea     rcx, [r11+20h]
0x1400033e2  mov     r10, rdx
0x1400033e5  mov     [r11-20h], rcx
0x1400033e9  xor     r9d, r9d; lpClass
0x1400033ec  mov     qword ptr [r11-28h], 0
0x1400033f4  xor     r8d, r8d; Reserved
0x1400033f7  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x1400033ff  mov     rdx, rax; lpSubKey
0x140003402  mov     rcx, r10; hKey
0x140003405  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14000340d  call    cs:__imp_RegCreateKeyExW
0x140003413  mov     ecx, eax
0x140003415  test    eax, eax
0x140003417  jnz     short loc_140003431
0x140003419  cmp     [rbx], rcx
0x14000341c  jz      short loc_140003429
0x14000341e  mov     rcx, [rbx]; hKey
0x140003421  call    cs:__imp_RegCloseKey
0x140003427  mov     ecx, eax
0x140003429  mov     rax, [rsp+58h+arg_18]
0x14000342e  mov     [rbx], rax
0x140003431  mov     eax, ecx
0x140003433  add     rsp, 50h
0x140003437  pop     rbx
0x140003438  retn
```
