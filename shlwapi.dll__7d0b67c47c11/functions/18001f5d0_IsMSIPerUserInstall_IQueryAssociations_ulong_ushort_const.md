# _IsMSIPerUserInstall(IQueryAssociations *,ulong,ushort const *)

- ea: `0x18001f5d0`
- end: `0x18001f67d`
- name: `?_IsMSIPerUserInstall@@YAHPEAUIQueryAssociations@@KPEBG@Z`
- size: `173`
- prototype: `__int64 __fastcall(struct IQueryAssociations *, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18001f2a0`
- `0x18001fa90`

## callees

- `0x180012550`
- `0x18001f5d0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x18001f652`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x18001f652`
- `msiltcfg!__imp_MsiGetProductInfoW` at `0x18001f63c`
- `msiltcfg!__imp_MsiGetProductInfoW` at `0x18001f63c`

## pseudocode

```c
_BOOL8 __fastcall _IsMSIPerUserInstall(struct IQueryAssociations *a1, __int64 a2, const unsigned __int16 *a3)
{
  struct IQueryAssociationsVtbl *lpVtbl; // rax
  DWORD pcchValueBuf; // [rsp+40h] [rbp-238h] BYREF
  WCHAR ValueBuf[6]; // [rsp+44h] [rbp-234h] BYREF
  WCHAR szProduct[264]; // [rsp+50h] [rbp-228h] BYREF

  lpVtbl = a1->lpVtbl;
  pcchValueBuf = 520;
  if ( ((int (__fastcall *)(struct IQueryAssociations *, __int64, __int64, const unsigned __int16 *, WCHAR *, DWORD *))lpVtbl[1].GetString)(
         a1,
         a2,
         1,
         a3,
         szProduct,
         &pcchValueBuf) < 0 )
    return 0;
  pcchValueBuf = 3;
  return !MsiGetProductInfoW(szProduct, L"AssignmentType", ValueBuf, &pcchValueBuf) && StrCmpW(ValueBuf, L"0") == 0;
}

```

## disassembly

```asm
0x18001f5d0  sub     rsp, 278h
0x18001f5d7  mov     rax, cs:__security_cookie
0x18001f5de  xor     rax, rsp
0x18001f5e1  mov     [rsp+278h+var_18], rax
0x18001f5e9  mov     rax, [rcx]
0x18001f5ec  lea     r9, [rsp+278h+pcchValueBuf]
0x18001f5f1  mov     [rsp+278h+var_250], r9
0x18001f5f6  lea     r9, [rsp+278h+szProduct]
0x18001f5fb  mov     [rsp+278h+var_258], r9
0x18001f600  mov     r9, r8
0x18001f603  mov     r8d, 1
0x18001f609  mov     [rsp+278h+pcchValueBuf], 208h
0x18001f611  mov     rax, [rax+30h]
0x18001f615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f61a  test    eax, eax
0x18001f61c  js      short loc_18001F663
0x18001f61e  lea     r9, [rsp+278h+pcchValueBuf]; pcchValueBuf
0x18001f623  mov     [rsp+278h+pcchValueBuf], 3
0x18001f62b  lea     r8, [rsp+278h+ValueBuf]; lpValueBuf
0x18001f630  lea     rdx, szAttribute; "AssignmentType"
0x18001f637  lea     rcx, [rsp+278h+szProduct]; szProduct
0x18001f63c  call    cs:__imp_MsiGetProductInfoW
0x18001f642  test    eax, eax
0x18001f644  jnz     short loc_18001F663
0x18001f646  lea     rdx, a0; "0"
0x18001f64d  lea     rcx, [rsp+278h+ValueBuf]; psz1
0x18001f652  call    cs:__imp_StrCmpW
0x18001f658  xor     ecx, ecx
0x18001f65a  test    eax, eax
0x18001f65c  setz    cl
0x18001f65f  mov     eax, ecx
0x18001f661  jmp     short loc_18001F665
0x18001f663  xor     eax, eax
0x18001f665  mov     rcx, [rsp+278h+var_18]
0x18001f66d  xor     rcx, rsp; StackCookie
0x18001f670  call    __security_check_cookie
0x18001f675  add     rsp, 278h
0x18001f67c  retn
```
