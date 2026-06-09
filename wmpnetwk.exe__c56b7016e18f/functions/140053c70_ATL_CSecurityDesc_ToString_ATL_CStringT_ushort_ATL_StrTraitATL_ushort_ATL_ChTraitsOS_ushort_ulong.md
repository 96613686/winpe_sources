# ATL::CSecurityDesc::ToString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> *,ulong)

- ea: `0x140053c70`
- end: `0x140053cdc`
- name: `?ToString@CSecurityDesc@ATL@@QEBA_NPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@2@K@Z`
- size: `108`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140051db0`

## callees

- `0x14000c780`
- `0x140038f58`
- `0x140053c70`

## import_xrefs

- `ADVAPI32!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x140053ca7`
- `ADVAPI32!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x140053ca7`
- `KERNEL32!LocalFree` at `0x140053cca`
- `KERNEL32!LocalFree` at `0x140053cca`

## pseudocode

```c
char __fastcall ATL::CSecurityDesc::ToString(__int64 a1, __int64 a2)
{
  void *v3; // rcx
  LPWSTR StringSecurityDescriptor; // [rsp+48h] [rbp+10h] BYREF

  if ( !a2 )
    return 0;
  v3 = *(void **)(a1 + 8);
  if ( !v3 )
    return 0;
  StringSecurityDescriptor = 0;
  if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(v3, 1u, 4u, &StringSecurityDescriptor, 0) )
    ATL::AtlThrowLastWin32();
  ATL::CSimpleStringT<unsigned short,0>::SetString(a2, StringSecurityDescriptor);
  LocalFree(StringSecurityDescriptor);
  return 1;
}

```

## disassembly

```asm
0x140053c70  push    rbx
0x140053c72  sub     rsp, 30h
0x140053c76  mov     rbx, rdx
0x140053c79  test    rdx, rdx
0x140053c7c  jz      short loc_140053CD4
0x140053c7e  mov     rcx, [rcx+8]; SecurityDescriptor
0x140053c82  test    rcx, rcx
0x140053c85  jz      short loc_140053CD4
0x140053c87  mov     [rsp+38h+StringSecurityDescriptor], 0
0x140053c90  mov     [rsp+38h+StringSecurityDescriptorLen], 0; StringSecurityDescriptorLen
0x140053c99  lea     r9, [rsp+38h+StringSecurityDescriptor]; StringSecurityDescriptor
0x140053c9e  mov     edx, 1; RequestedStringSDRevision
0x140053ca3  lea     r8d, [rdx+3]; SecurityInformation
0x140053ca7  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x140053cad  test    eax, eax
0x140053caf  jnz     short loc_140053CB7
0x140053cb1  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x140053cb7  mov     rdx, [rsp+38h+StringSecurityDescriptor]
0x140053cbc  mov     rcx, rbx
0x140053cbf  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x140053cc4  nop
0x140053cc5  mov     rcx, [rsp+38h+StringSecurityDescriptor]; hMem
0x140053cca  call    cs:__imp_LocalFree
0x140053cd0  mov     al, 1
0x140053cd2  jmp     short loc_140053CD6
0x140053cd4  xor     al, al
0x140053cd6  add     rsp, 30h
0x140053cda  pop     rbx
0x140053cdb  retn
```
