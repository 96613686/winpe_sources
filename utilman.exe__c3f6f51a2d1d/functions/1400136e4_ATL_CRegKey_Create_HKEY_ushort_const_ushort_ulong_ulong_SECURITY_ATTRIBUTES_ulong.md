# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x1400136e4`
- end: `0x14001378c`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `168`
- prototype: `__int64 __usercall@<rax>(ATL::CRegKey *__hidden this@<rcx>, HKEY hKey@<rdx>, LPCWSTR lpSubKey@<r8>, unsigned __int16 *@<r9>, DWORD, REGSAM, HKEY, unsigned int *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140015720`
- `0x140015c74`
- `0x140016e8c`
- `0x1400172b0`
- `0x14001c778`
- `0x14001c8d0`

## callees

- `0x14000d75c`
- `0x1400136e4`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x140013749`
- `ADVAPI32!RegCreateKeyExW` at `0x140013749`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(
        ATL::CRegKey *this,
        HKEY hKey,
        LPCWSTR lpSubKey,
        unsigned __int16 *a4,
        DWORD dwOptions,
        REGSAM samDesired,
        HKEY phkResult,
        unsigned int *a8)
{
  unsigned int v9; // edx
  DWORD lpdwDisposition; // [rsp+78h] [rbp+20h] BYREF
  int v12; // [rsp+7Ch] [rbp+24h]

  v12 = HIDWORD(a4);
  lpdwDisposition = 0;
  phkResult = 0;
  v9 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, dwOptions, samDesired, 0, &phkResult, &lpdwDisposition);
  if ( a8 )
    *a8 = lpdwDisposition;
  if ( !v9 )
  {
    v9 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v9;
}

```

## disassembly

```asm
0x1400136e4  mov     rax, rsp
0x1400136e7  mov     [rax+20h], r9
0x1400136eb  push    rbx
0x1400136ec  sub     rsp, 50h
0x1400136f0  mov     dword ptr [rax+20h], 0
0x1400136f7  mov     r10, r8
0x1400136fa  mov     qword ptr [rax+38h], 0
0x140013702  lea     rax, [rax+20h]
0x140013706  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x14001370b  mov     r11, rdx
0x14001370e  lea     rax, [rsp+58h+arg_30]
0x140013716  mov     rbx, rcx
0x140013719  mov     [rsp+58h+phkResult], rax; phkResult
0x14001371e  xor     r9d, r9d; lpClass
0x140013721  mov     eax, [rsp+58h+arg_28]
0x140013728  xor     r8d, r8d; Reserved
0x14001372b  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140013734  mov     rdx, r10; lpSubKey
0x140013737  mov     [rsp+58h+samDesired], eax; samDesired
0x14001373b  mov     rcx, r11; hKey
0x14001373e  mov     eax, [rsp+58h+arg_20]
0x140013745  mov     [rsp+58h+dwOptions], eax; dwOptions
0x140013749  call    cs:__imp_RegCreateKeyExW
0x140013750  nop     dword ptr [rax+rax+00h]
0x140013755  mov     edx, eax
0x140013757  mov     rax, [rsp+58h+arg_38]
0x14001375f  test    rax, rax
0x140013762  jz      short loc_14001376A
0x140013764  mov     ecx, [rsp+58h+arg_18]
0x140013768  mov     [rax], ecx
0x14001376a  test    edx, edx
0x14001376c  jnz     short loc_140013783
0x14001376e  mov     rcx, rbx; this
0x140013771  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140013776  mov     edx, eax
0x140013778  mov     rax, [rsp+58h+arg_30]
0x140013780  mov     [rbx], rax
0x140013783  mov     eax, edx
0x140013785  add     rsp, 50h
0x140013789  pop     rbx
0x14001378a  retn
```
