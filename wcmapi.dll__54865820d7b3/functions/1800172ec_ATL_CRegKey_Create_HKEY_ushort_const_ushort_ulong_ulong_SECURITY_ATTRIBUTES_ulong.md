# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x1800172ec`
- end: `0x18001738a`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `158`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006b4c`
- `0x180008010`
- `0x18001aa44`

## callees

- `0x1800075e8`
- `0x180008a90`
- `0x1800172ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017350`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017350`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *a4)
{
  unsigned int v5; // ecx
  HKEY v7; // [rsp+50h] [rbp-28h] BYREF
  DWORD v8; // [rsp+58h] [rbp-20h] BYREF

  v8 = 0;
  v7 = 0;
  v5 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &v7, &v8);
  if ( !v5 )
  {
    v5 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = v7;
  }
  return v5;
}

```

## disassembly

```asm
0x1800172ec  mov     r11, rsp
0x1800172ef  push    rbx
0x1800172f0  sub     rsp, 70h
0x1800172f4  mov     rax, cs:__security_cookie
0x1800172fb  xor     rax, rsp
0x1800172fe  mov     [rsp+78h+var_18], rax
0x180017303  mov     rbx, rcx
0x180017306  mov     [rsp+78h+var_20], 0
0x18001730e  lea     rcx, [r11-20h]
0x180017312  mov     qword ptr [r11-28h], 0
0x18001731a  mov     [r11-38h], rcx
0x18001731e  mov     r10, r8
0x180017321  lea     rcx, [r11-28h]
0x180017325  mov     rax, rdx
0x180017328  mov     [r11-40h], rcx
0x18001732c  xor     r9d, r9d; lpClass
0x18001732f  mov     qword ptr [r11-48h], 0
0x180017337  xor     r8d, r8d; Reserved
0x18001733a  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180017342  mov     rdx, r10; lpSubKey
0x180017345  mov     rcx, rax; hKey
0x180017348  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180017350  call    cs:__imp_RegCreateKeyExW
0x180017357  nop     dword ptr [rax+rax+00h]
0x18001735c  mov     ecx, eax
0x18001735e  test    eax, eax
0x180017360  jnz     short loc_180017374
0x180017362  mov     rcx, rbx; this
0x180017365  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001736a  mov     ecx, eax
0x18001736c  mov     rax, [rsp+78h+var_28]
0x180017371  mov     [rbx], rax
0x180017374  mov     eax, ecx
0x180017376  mov     rcx, [rsp+78h+var_18]
0x18001737b  xor     rcx, rsp; StackCookie
0x18001737e  call    __security_check_cookie
0x180017383  add     rsp, 70h
0x180017387  pop     rbx
0x180017388  retn
```
