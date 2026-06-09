# ReadRegistryT<256>::TryOpen(HKEY__ *,ushort const *)

- ea: `0x14006e2b4`
- end: `0x14006e3d9`
- name: `?TryOpen@?$ReadRegistryT@$0BAA@@@SA?AV?$Optional@V?$ReadRegistryT@$0BAA@@@@@PEAUHKEY__@@PEBG@Z`
- size: `293`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140041420`
- `0x14006e624`
- `0x14007d964`

## callees

- `0x14006cfac`
- `0x14006e2b4`
- `0x1400a8010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14006e2e8`
- `ADVAPI32!RegOpenKeyExW` at `0x14006e2e8`
- `KERNEL32!SetLastError` at `0x14006e2f0`
- `KERNEL32!SetLastError` at `0x14006e2f0`

## pseudocode

```c
_QWORD *__fastcall ReadRegistryT<256>::TryOpen(_QWORD *a1, HKEY a2, const WCHAR *a3)
{
  LSTATUS v4; // eax
  Private::RegistryBase *Registry; // rax
  _QWORD *v6; // r8
  __int64 v7; // rcx
  volatile signed __int32 *v8; // rbx
  _BYTE v10[8]; // [rsp+38h] [rbp-30h] BYREF
  volatile signed __int32 *v11; // [rsp+40h] [rbp-28h]
  HKEY v12; // [rsp+88h] [rbp+20h] BYREF

  v12 = 0;
  v4 = RegOpenKeyExW(a2, a3, 0, 0x20119u, &v12);
  SetLastError(v4);
  if ( v12 )
  {
    Registry = ReadRegistryT<256>::ReadRegistryT<256>((Private::RegistryBase *)v10, v12, 1);
    v6 = a1 + 1;
    a1[1] = 0;
    a1[3] = &ReadRegistryT<256>::`vbtable';
    a1[2] = 0;
    a1[5] = &IConstHierarchicalStorage::`vftable';
    a1[1] = *(_QWORD *)Registry;
    a1[2] = *((_QWORD *)Registry + 1);
    *(_QWORD *)Registry = 0;
    *((_QWORD *)Registry + 1) = 0;
    *(_QWORD *)((char *)v6 + *(int *)(a1[3] + 4LL) + 16) = &ReadRegistryT<256>::`vftable';
    v7 = *(int *)(a1[3] + 4LL);
    *(_DWORD *)((char *)v6 + v7 + 12) = v7 - 16;
    v8 = v11;
    a1[6] = a1 + 1;
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
  }
  else
  {
    a1[6] = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x14006e2b4  mov     r11, rsp
0x14006e2b7  mov     [r11+8], rbx
0x14006e2bb  push    rdi
0x14006e2bc  sub     rsp, 60h
0x14006e2c0  mov     rdi, rcx
0x14006e2c3  mov     qword ptr [r11+20h], 0
0x14006e2cb  lea     rcx, [r11+20h]
0x14006e2cf  mov     rax, r8
0x14006e2d2  mov     r10, rdx
0x14006e2d5  mov     [r11-48h], rcx
0x14006e2d9  mov     rcx, r10; hKey
0x14006e2dc  mov     r9d, 20119h; samDesired
0x14006e2e2  xor     r8d, r8d; ulOptions
0x14006e2e5  mov     rdx, rax; lpSubKey
0x14006e2e8  call    cs:__imp_RegOpenKeyExW
0x14006e2ee  mov     ecx, eax; dwErrCode
0x14006e2f0  call    cs:__imp_SetLastError
0x14006e2f6  mov     rdx, [rsp+68h+arg_18]
0x14006e2fe  test    rdx, rdx
0x14006e301  jnz     short loc_14006E30C
0x14006e303  mov     [rdi+30h], rdx
0x14006e307  jmp     loc_14006E3CB
0x14006e30c  mov     r8d, 1
0x14006e312  lea     rcx, [rsp+68h+var_30]
0x14006e317  call    ??0?$ReadRegistryT@$0BAA@@@IEAA@PEAUHKEY__@@@Z; ReadRegistryT<256>::ReadRegistryT<256>(HKEY__ *)
0x14006e31c  lea     r8, [rdi+8]
0x14006e320  mov     qword ptr [r8], 0
0x14006e327  lea     rcx, ??_8?$ReadRegistryT@$0BAA@@@7B@; const ReadRegistryT<256>::`vbtable'
0x14006e32e  mov     [r8+10h], rcx
0x14006e332  lea     rcx, ??_7IConstHierarchicalStorage@@6B@; const IConstHierarchicalStorage::`vftable'
0x14006e339  mov     qword ptr [r8+8], 0
0x14006e341  mov     [r8+20h], rcx
0x14006e345  mov     rcx, [rax]
0x14006e348  mov     [r8], rcx
0x14006e34b  mov     rcx, [rax+8]
0x14006e34f  mov     [r8+8], rcx
0x14006e353  mov     qword ptr [rax], 0
0x14006e35a  mov     qword ptr [rax+8], 0
0x14006e362  mov     rax, [r8+10h]
0x14006e366  movsxd  rcx, dword ptr [rax+4]
0x14006e36a  lea     rax, ??_7?$ReadRegistryT@$0BAA@@@6B@; const ReadRegistryT<256>::`vftable'
0x14006e371  mov     [rcx+r8+10h], rax
0x14006e376  mov     rax, [r8+10h]
0x14006e37a  movsxd  rcx, dword ptr [rax+4]
0x14006e37e  lea     edx, [rcx-10h]
0x14006e381  mov     [rcx+r8+0Ch], edx
0x14006e386  mov     rbx, [rsp+68h+var_28]
0x14006e38b  mov     [rdi+30h], r8
0x14006e38f  test    rbx, rbx
0x14006e392  jz      short loc_14006E3CB
0x14006e394  or      eax, 0FFFFFFFFh
0x14006e397  lock xadd [rbx+8], eax
0x14006e39c  cmp     eax, 1
0x14006e39f  jnz     short loc_14006E3CB
0x14006e3a1  mov     rax, [rbx]
0x14006e3a4  mov     rcx, rbx
0x14006e3a7  mov     rax, [rax]
0x14006e3aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e3af  or      eax, 0FFFFFFFFh
0x14006e3b2  lock xadd [rbx+0Ch], eax
0x14006e3b7  cmp     eax, 1
0x14006e3ba  jnz     short loc_14006E3CB
0x14006e3bc  mov     rax, [rbx]
0x14006e3bf  mov     rcx, rbx
0x14006e3c2  mov     rax, [rax+8]
0x14006e3c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e3cb  mov     rbx, [rsp+68h+arg_0]
0x14006e3d0  mov     rax, rdi
0x14006e3d3  add     rsp, 60h
0x14006e3d7  pop     rdi
0x14006e3d8  retn
```
