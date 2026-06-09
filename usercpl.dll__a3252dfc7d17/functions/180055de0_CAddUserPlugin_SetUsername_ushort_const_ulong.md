# CAddUserPlugin::SetUsername(ushort const *,ulong *)

- ea: `0x180055de0`
- end: `0x180055e78`
- name: `?SetUsername@CAddUserPlugin@@UEAAJPEBGPEAK@Z`
- size: `152`
- prototype: `int(CAddUserPlugin *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180026218`
- `0x180055de0`
- `0x180078010`

## import_xrefs

- `SHLWAPI!StrTrimW` at `0x180055e1d`
- `SHLWAPI!StrTrimW` at `0x180055e1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055e4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055e67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055e4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055e67`

## pseudocode

```c
__int64 __fastcall CAddUserPlugin::SetUsername(CAddUserPlugin *this, const unsigned __int16 *a2, unsigned int *a3)
{
  int v5; // ebx
  PWSTR v6; // rdi
  PWSTR psz; // [rsp+68h] [rbp+20h] BYREF

  psz = 0;
  v5 = CoAllocString(a2, &psz);
  if ( v5 >= 0 )
  {
    v6 = psz;
    StrTrimW(psz, Str);
    v5 = (*(__int64 (__fastcall **)(_QWORD, PWSTR, unsigned int *))(**((_QWORD **)this + 5) + 56LL))(
           *((_QWORD *)this + 5),
           v6,
           a3);
    if ( v5 >= 0 )
    {
      if ( *a3 )
      {
        v5 = -2147024809;
      }
      else
      {
        v5 = 0;
        CoTaskMemFree(*((LPVOID *)this + 19));
        *((_QWORD *)this + 19) = v6;
        v6 = 0;
      }
      CoTaskMemFree(v6);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180055de0  push    rbx
0x180055de2  push    rbp
0x180055de3  push    rsi
0x180055de4  push    rdi
0x180055de5  sub     rsp, 28h
0x180055de9  mov     rax, rdx
0x180055dec  mov     [rsp+48h+psz], 0
0x180055df5  mov     rsi, rcx
0x180055df8  lea     rdx, [rsp+48h+psz]; unsigned __int16 **
0x180055dfd  mov     rcx, rax; unsigned __int16 *
0x180055e00  mov     rbp, r8
0x180055e03  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x180055e08  mov     ebx, eax
0x180055e0a  test    eax, eax
0x180055e0c  js      short loc_180055E6D
0x180055e0e  mov     rdi, [rsp+48h+psz]
0x180055e13  lea     rdx, Str; " \t"
0x180055e1a  mov     rcx, rdi; psz
0x180055e1d  call    cs:__imp_StrTrimW
0x180055e23  mov     rcx, [rsi+28h]
0x180055e27  mov     r8, rbp
0x180055e2a  mov     rdx, rdi
0x180055e2d  mov     rax, [rcx]
0x180055e30  mov     rax, [rax+38h]
0x180055e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055e39  mov     ebx, eax
0x180055e3b  test    eax, eax
0x180055e3d  js      short loc_180055E6D
0x180055e3f  cmp     dword ptr [rbp+0], 0
0x180055e43  jnz     short loc_180055E5F
0x180055e45  mov     rcx, [rsi+98h]; pv
0x180055e4c  xor     ebx, ebx
0x180055e4e  call    cs:__imp_CoTaskMemFree
0x180055e54  mov     [rsi+98h], rdi
0x180055e5b  xor     edi, edi
0x180055e5d  jmp     short loc_180055E64
0x180055e5f  mov     ebx, 80070057h
0x180055e64  mov     rcx, rdi; pv
0x180055e67  call    cs:__imp_CoTaskMemFree
0x180055e6d  mov     eax, ebx
0x180055e6f  add     rsp, 28h
0x180055e73  pop     rdi
0x180055e74  pop     rsi
0x180055e75  pop     rbp
0x180055e76  pop     rbx
0x180055e77  retn
```
