# ReadRegistryT<256>::ReadRegistryT<256>(ushort const *)

- ea: `0x14006d01c`
- end: `0x14006d0bc`
- name: `??0?$ReadRegistryT@$0BAA@@@QEAA@PEBG@Z`
- size: `160`
- prototype: `ReadRegistryT<256> *__fastcall(ReadRegistryT<256> *this, const WCHAR *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14006cf40`
- `0x140088c2c`
- `0x14009a234`

## callees

- `0x14006d3a0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14006d075`
- `ADVAPI32!RegOpenKeyExW` at `0x14006d075`
- `KERNEL32!SetLastError` at `0x14006d07d`
- `KERNEL32!SetLastError` at `0x14006d07d`

## pseudocode

```c
ReadRegistryT<256> *__fastcall ReadRegistryT<256>::ReadRegistryT<256>(ReadRegistryT<256> *this, const WCHAR *a2)
{
  LSTATUS v3; // eax
  __int64 v4; // rcx
  HKEY v6; // [rsp+58h] [rbp+20h] BYREF

  *((_QWORD *)this + 2) = &ReadRegistryT<256>::`vbtable';
  *((_QWORD *)this + 4) = &IConstHierarchicalStorage::`vftable';
  v6 = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20119u, &v6);
  SetLastError(v3);
  Private::RegistryBase::RegistryBase(this, v6);
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 2) + 4LL) + 16) = &ReadRegistryT<256>::`vftable';
  v4 = *(int *)(*((_QWORD *)this + 2) + 4LL);
  *(_DWORD *)((char *)this + v4 + 12) = v4 - 16;
  return this;
}

```

## disassembly

```asm
0x14006d01c  mov     r11, rsp
0x14006d01f  mov     [r11+18h], r8d
0x14006d023  mov     [r11+8], rcx
0x14006d027  push    rbx
0x14006d028  sub     rsp, 30h
0x14006d02c  mov     rbx, rcx
0x14006d02f  mov     [rsp+38h+arg_10], 0
0x14006d037  lea     rax, ??_8?$ReadRegistryT@$0BAA@@@7B@; const ReadRegistryT<256>::`vbtable'
0x14006d03e  mov     [rcx+10h], rax
0x14006d042  lea     rax, ??_7IConstHierarchicalStorage@@6B@; const IConstHierarchicalStorage::`vftable'
0x14006d049  mov     [rcx+20h], rax
0x14006d04d  mov     [rsp+38h+arg_10], 1
0x14006d055  mov     qword ptr [r11+20h], 0
0x14006d05d  lea     rax, [r11+20h]
0x14006d061  mov     [r11-18h], rax
0x14006d065  mov     r9d, 20119h; samDesired
0x14006d06b  xor     r8d, r8d; ulOptions
0x14006d06e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14006d075  call    cs:__imp_RegOpenKeyExW
0x14006d07b  mov     ecx, eax; dwErrCode
0x14006d07d  call    cs:__imp_SetLastError
0x14006d083  mov     rdx, [rsp+38h+arg_18]; HKEY
0x14006d088  mov     rcx, rbx; this
0x14006d08b  call    ??0RegistryBase@Private@@IEAA@PEAUHKEY__@@@Z; Private::RegistryBase::RegistryBase(HKEY__ *)
0x14006d090  mov     rax, [rbx+10h]
0x14006d094  movsxd  rcx, dword ptr [rax+4]
0x14006d098  lea     rax, ??_7?$ReadRegistryT@$0BAA@@@6B@; const ReadRegistryT<256>::`vftable'
0x14006d09f  mov     [rcx+rbx+10h], rax
0x14006d0a4  mov     rax, [rbx+10h]
0x14006d0a8  movsxd  rcx, dword ptr [rax+4]
0x14006d0ac  lea     edx, [rcx-10h]
0x14006d0af  mov     [rcx+rbx+0Ch], edx
0x14006d0b3  mov     rax, rbx
0x14006d0b6  add     rsp, 30h
0x14006d0ba  pop     rbx
0x14006d0bb  retn
```
