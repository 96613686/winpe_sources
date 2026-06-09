# ATL::AtlModuleUnRegisterTypeLib(ATL::_ATL_MODULE *,ushort const *)

- ea: `0x14000a9ec`
- end: `0x14000aad8`
- name: `?AtlModuleUnRegisterTypeLib@ATL@@YAJPEAU_ATL_MODULE@1@PEBG@Z`
- size: `236`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000ccb8`

## callees

- `0x14000a68c`
- `0x14000a9ec`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000aa68`
- `KERNEL32!GetProcAddress` at `0x14000aa68`
- `KERNEL32!FreeLibrary` at `0x14000aa95`
- `KERNEL32!FreeLibrary` at `0x14000aa95`
- `KERNEL32!LoadLibraryExW` at `0x14000aa50`
- `KERNEL32!LoadLibraryExW` at `0x14000aa50`
- `OLEAUT32!__imp_SysFreeString` at `0x14000aac8`
- `OLEAUT32!__imp_SysFreeString` at `0x14000aac8`

## string_xrefs

- `0x14000aa47`: `oleaut32.dll`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleUnRegisterTypeLib(struct ATL::_ATL_MODULE *a1, const unsigned __int16 *a2)
{
  int v2; // ebx
  HMODULE Library; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rax
  struct ITypeLib *v7; // [rsp+58h] [rbp+28h] BYREF
  __int64 v8; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  bstrString = 0;
  v7 = 0;
  v2 = ATL::AtlModuleLoadTypeLib(a1, a2, &bstrString, &v7);
  if ( v2 >= 0 )
  {
    v8 = 0;
    v2 = ((__int64 (__fastcall *)(struct ITypeLib *, __int64 *))v7->lpVtbl->GetLibAttr)(v7, &v8);
    if ( v2 >= 0 )
    {
      Library = LoadLibraryExW(L"oleaut32.dll", 0, 0);
      v4 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "UnRegisterTypeLib");
        if ( ProcAddress )
          v2 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))ProcAddress)(
                 v8,
                 *(unsigned __int16 *)(v8 + 24),
                 *(unsigned __int16 *)(v8 + 26),
                 *(unsigned int *)(v8 + 16),
                 *(_DWORD *)(v8 + 20));
        FreeLibrary(v4);
      }
      ((void (__fastcall *)(struct ITypeLib *, __int64))v7->lpVtbl->ReleaseTLibAttr)(v7, v8);
    }
  }
  if ( v7 )
    ((void (__fastcall *)(struct ITypeLib *))v7->lpVtbl->Release)(v7);
  SysFreeString(bstrString);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000a9ec  mov     [rsp-18h+arg_8], rdx
0x14000a9f1  push    rbp
0x14000a9f2  push    rbx
0x14000a9f3  push    rdi
0x14000a9f4  mov     rbp, rsp
0x14000a9f7  sub     rsp, 30h
0x14000a9fb  lea     r9, [rbp+arg_8]; struct ITypeLib **
0x14000a9ff  mov     [rbp+bstrString], 0
0x14000aa07  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x14000aa0b  mov     [rbp+arg_8], 0
0x14000aa13  call    ?AtlModuleLoadTypeLib@ATL@@YAJPEAU_ATL_MODULE@1@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlModuleLoadTypeLib(ATL::_ATL_MODULE *,ushort const *,ushort * *,ITypeLib * *)
0x14000aa18  mov     ebx, eax
0x14000aa1a  test    eax, eax
0x14000aa1c  js      loc_14000AAAF
0x14000aa22  mov     rcx, [rbp+arg_8]
0x14000aa26  lea     rdx, [rbp+arg_10]
0x14000aa2a  mov     [rbp+arg_10], 0
0x14000aa32  mov     rax, [rcx]
0x14000aa35  mov     rax, [rax+38h]
0x14000aa39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa3e  mov     ebx, eax
0x14000aa40  test    eax, eax
0x14000aa42  js      short loc_14000AAAF
0x14000aa44  xor     r8d, r8d; dwFlags
0x14000aa47  lea     rcx, LibFileName; "oleaut32.dll"
0x14000aa4e  xor     edx, edx; hFile
0x14000aa50  call    cs:__imp_LoadLibraryExW
0x14000aa56  mov     rdi, rax
0x14000aa59  test    rax, rax
0x14000aa5c  jz      short loc_14000AA9B
0x14000aa5e  lea     rdx, ProcName; "UnRegisterTypeLib"
0x14000aa65  mov     rcx, rax; hModule
0x14000aa68  call    cs:__imp_GetProcAddress
0x14000aa6e  test    rax, rax
0x14000aa71  jz      short loc_14000AA92
0x14000aa73  mov     rcx, [rbp+arg_10]
0x14000aa77  mov     edx, [rcx+14h]
0x14000aa7a  mov     r9d, [rcx+10h]
0x14000aa7e  movzx   r8d, word ptr [rcx+1Ah]
0x14000aa83  mov     [rsp+30h+var_10], edx
0x14000aa87  movzx   edx, word ptr [rcx+18h]
0x14000aa8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa90  mov     ebx, eax
0x14000aa92  mov     rcx, rdi; hLibModule
0x14000aa95  call    cs:__imp_FreeLibrary
0x14000aa9b  mov     rcx, [rbp+arg_8]
0x14000aa9f  mov     rdx, [rbp+arg_10]
0x14000aaa3  mov     rax, [rcx]
0x14000aaa6  mov     rax, [rax+60h]
0x14000aaaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aaaf  mov     rcx, [rbp+arg_8]
0x14000aab3  test    rcx, rcx
0x14000aab6  jz      short loc_14000AAC4
0x14000aab8  mov     rax, [rcx]
0x14000aabb  mov     rax, [rax+10h]
0x14000aabf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aac4  mov     rcx, [rbp+bstrString]; bstrString
0x14000aac8  call    cs:__imp_SysFreeString
0x14000aace  mov     eax, ebx
0x14000aad0  add     rsp, 30h
0x14000aad4  pop     rdi
0x14000aad5  pop     rbx
0x14000aad6  pop     rbp
0x14000aad7  retn
```
