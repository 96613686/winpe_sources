# ATL::AtlGetDacl(void *,_SE_OBJECT_TYPE,ATL::CDacl *)

- ea: `0x140092348`
- end: `0x1400923d6`
- name: `?AtlGetDacl@ATL@@YA_NPEAXW4_SE_OBJECT_TYPE@@PEAVCDacl@1@@Z`
- size: `142`
- prototype: `bool __fastcall(void *, SE_OBJECT_TYPE, struct ATL::CDacl *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140093330`
- `0x140093924`

## callees

- `0x140091fd8`
- `0x140092348`

## import_xrefs

- `ADVAPI32!GetSecurityInfo` at `0x140092394`
- `ADVAPI32!GetSecurityInfo` at `0x140092394`
- `KERNEL32!LocalFree` at `0x1400923c5`
- `KERNEL32!LocalFree` at `0x1400923c5`
- `KERNEL32!SetLastError` at `0x1400923a0`
- `KERNEL32!SetLastError` at `0x1400923a0`

## pseudocode

```c
bool __fastcall ATL::AtlGetDacl(void *a1, SE_OBJECT_TYPE a2, struct ATL::CDacl *a3)
{
  DWORD SecurityInfo; // eax
  struct _ACL *v6; // [rsp+50h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp+20h] BYREF

  if ( !a1 || !a3 )
    return 0;
  v6 = 0;
  hMem = 0;
  SecurityInfo = GetSecurityInfo(a1, a2, 4u, 0, 0, &v6, 0, &hMem);
  if ( SecurityInfo )
  {
    SetLastError(SecurityInfo);
    return 0;
  }
  if ( v6 )
    ATL::CDacl::operator=(a3, v6);
  LocalFree(hMem);
  return v6 != 0;
}

```

## disassembly

```asm
0x140092348  mov     r11, rsp
0x14009234b  push    rbx
0x14009234c  sub     rsp, 40h
0x140092350  mov     rbx, r8
0x140092353  test    rcx, rcx
0x140092356  jz      short loc_1400923A6
0x140092358  test    rbx, rbx
0x14009235b  jz      short loc_1400923A6
0x14009235d  lea     rax, [r11+20h]
0x140092361  mov     qword ptr [r11+8], 0
0x140092369  mov     [r11-10h], rax
0x14009236d  xor     r9d, r9d; ppsidOwner
0x140092370  mov     qword ptr [r11-18h], 0
0x140092378  lea     rax, [r11+8]
0x14009237c  mov     [r11-20h], rax
0x140092380  mov     qword ptr [r11-28h], 0
0x140092388  lea     r8d, [r9+4]; SecurityInfo
0x14009238c  mov     qword ptr [r11+20h], 0
0x140092394  call    cs:__imp_GetSecurityInfo
0x14009239a  test    eax, eax
0x14009239c  jz      short loc_1400923AE
0x14009239e  mov     ecx, eax; dwErrCode
0x1400923a0  call    cs:__imp_SetLastError
0x1400923a6  xor     al, al
0x1400923a8  add     rsp, 40h
0x1400923ac  pop     rbx
0x1400923ad  retn
0x1400923ae  mov     rdx, [rsp+48h+arg_0]; struct _ACL *
0x1400923b3  test    rdx, rdx
0x1400923b6  jz      short loc_1400923C0
0x1400923b8  mov     rcx, rbx; this
0x1400923bb  call    ??4CDacl@ATL@@QEAAAEAV01@AEBU_ACL@@@Z; ATL::CDacl::operator=(_ACL const &)
0x1400923c0  mov     rcx, [rsp+48h+hMem]; hMem
0x1400923c5  call    cs:__imp_LocalFree
0x1400923cb  cmp     [rsp+48h+arg_0], 0
0x1400923d1  setnz   al
0x1400923d4  jmp     short loc_1400923A8
```
