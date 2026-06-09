# CShellWrappers::GetAttribsFromChildPidl(IShellFolder *,_ITEMID_CHILD const *,ulong *,ulong *)

- ea: `0x18002cc10`
- end: `0x18002cd01`
- name: `?GetAttribsFromChildPidl@CShellWrappers@@QEAAJPEAUIShellFolder@@PEBU_ITEMID_CHILD@@PEAK2@Z`
- size: `241`
- prototype: `__int64 __fastcall(CShellWrappers *__hidden this, struct IShellFolder *, const struct _ITEMID_CHILD *, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180024f0c`
- `0x180025b24`
- `0x18002cb8c`

## callees

- `0x180005cc0`
- `0x18000d4dc`
- `0x18002cc10`
- `0x18002d3a0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18002ccc6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18002ccc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cce2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cce2`

## pseudocode

```c
__int64 __fastcall CShellWrappers::GetAttribsFromChildPidl(
        CShellWrappers *this,
        struct IShellFolder *a2,
        const struct _ITEMID_CHILD *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  int PathFromChildPidl; // ebx
  WCHAR *v8; // rcx
  LPCWSTR lpFileName; // [rsp+30h] [rbp-40h] BYREF
  struct _ITEMID_CHILD *v11; // [rsp+38h] [rbp-38h] BYREF
  _OWORD FileInformation[2]; // [rsp+40h] [rbp-30h] BYREF
  int v13; // [rsp+60h] [rbp-10h]

  v11 = a3;
  if ( a4 )
    *a4 = 0;
  *a5 = 1614839808;
  PathFromChildPidl = ((__int64 (__fastcall *)(struct IShellFolder *, __int64, struct _ITEMID_CHILD **, unsigned int *))a2->lpVtbl->GetAttributesOf)(
                        a2,
                        1,
                        &v11,
                        a5);
  if ( PathFromChildPidl >= 0 )
  {
    v8 = (WCHAR *)*a5;
    if ( ((unsigned int)v8 & 0x40000000) != 0 )
    {
      if ( ((unsigned __int16)v8 & 0x8000) != 0 )
      {
        LODWORD(v8) = (unsigned int)v8 & 0xFFFF7FFF;
        *a5 = (unsigned int)v8;
      }
      lpFileName = 0;
      PathFromChildPidl = CShellWrappers::GetPathFromChildPidl(
                            v8,
                            a2,
                            (const ITEMIDLIST *)v11,
                            (unsigned __int16 **)&lpFileName,
                            0);
      if ( PathFromChildPidl >= 0 && a4 )
      {
        v13 = 0;
        memset(FileInformation, 0, sizeof(FileInformation));
        if ( GetFileAttributesExW(lpFileName, GetFileExInfoStandard, FileInformation) )
          *a4 = FileInformation[0];
        else
          PathFromChildPidl = ResultFromKnownLastError();
      }
      CoTaskMemFree((LPVOID)lpFileName);
    }
  }
  return (unsigned int)PathFromChildPidl;
}

```

## disassembly

```asm
0x18002cc10  push    rbp
0x18002cc12  push    rbx
0x18002cc13  push    rsi
0x18002cc14  push    rdi
0x18002cc15  push    r14
0x18002cc17  mov     rbp, rsp
0x18002cc1a  sub     rsp, 70h
0x18002cc1e  mov     rax, cs:__security_cookie
0x18002cc25  xor     rax, rsp
0x18002cc28  mov     [rbp+var_8], rax
0x18002cc2c  mov     rsi, [rbp+arg_20]
0x18002cc30  mov     rdi, r9
0x18002cc33  mov     [rbp+var_38], r8
0x18002cc37  mov     r14, rdx
0x18002cc3a  test    r9, r9
0x18002cc3d  jz      short loc_18002CC46
0x18002cc3f  mov     dword ptr [r9], 0
0x18002cc46  mov     dword ptr [rsi], 60408000h
0x18002cc4c  lea     r8, [rbp+var_38]
0x18002cc50  mov     rax, [rdx]
0x18002cc53  mov     r9, rsi
0x18002cc56  mov     edx, 1
0x18002cc5b  mov     rcx, r14
0x18002cc5e  mov     rax, [rax+48h]
0x18002cc62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc67  mov     ebx, eax
0x18002cc69  test    eax, eax
0x18002cc6b  js      short loc_18002CCE8
0x18002cc6d  mov     ecx, [rsi]
0x18002cc6f  bt      ecx, 1Eh
0x18002cc73  jnb     short loc_18002CCE8
0x18002cc75  bt      ecx, 0Fh
0x18002cc79  jnb     short loc_18002CC81
0x18002cc7b  btr     ecx, 0Fh; this
0x18002cc7f  mov     [rsi], ecx
0x18002cc81  mov     r8, [rbp+var_38]; struct _ITEMID_CHILD *
0x18002cc85  lea     r9, [rbp+lpFileName]; unsigned __int16 **
0x18002cc89  mov     rdx, r14; struct IShellFolder *
0x18002cc8c  mov     [rbp+lpFileName], 0
0x18002cc94  mov     [rsp+70h+var_50], 0; int
0x18002cc9c  call    ?GetPathFromChildPidl@CShellWrappers@@QEAAJPEAUIShellFolder@@PEBU_ITEMID_CHILD@@PEAPEAGH@Z; CShellWrappers::GetPathFromChildPidl(IShellFolder *,_ITEMID_CHILD const *,ushort * *,int)
0x18002cca1  mov     ebx, eax
0x18002cca3  test    eax, eax
0x18002cca5  js      short loc_18002CCDE
0x18002cca7  test    rdi, rdi
0x18002ccaa  jz      short loc_18002CCDE
0x18002ccac  mov     rcx, [rbp+lpFileName]; lpFileName
0x18002ccb0  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18002ccb4  xorps   xmm0, xmm0
0x18002ccb7  xor     eax, eax
0x18002ccb9  xor     edx, edx; fInfoLevelId
0x18002ccbb  mov     [rbp+var_10], eax
0x18002ccbe  movups  [rbp+FileInformation], xmm0
0x18002ccc2  movups  [rbp+var_20], xmm0
0x18002ccc6  call    cs:__imp_GetFileAttributesExW
0x18002cccc  test    eax, eax
0x18002ccce  jz      short loc_18002CCD7
0x18002ccd0  mov     eax, dword ptr [rbp+FileInformation]
0x18002ccd3  mov     [rdi], eax
0x18002ccd5  jmp     short loc_18002CCDE
0x18002ccd7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002ccdc  mov     ebx, eax
0x18002ccde  mov     rcx, [rbp+lpFileName]; pv
0x18002cce2  call    cs:__imp_CoTaskMemFree
0x18002cce8  mov     eax, ebx
0x18002ccea  mov     rcx, [rbp+var_8]
0x18002ccee  xor     rcx, rsp; StackCookie
0x18002ccf1  call    __security_check_cookie
0x18002ccf6  add     rsp, 70h
0x18002ccfa  pop     r14
0x18002ccfc  pop     rdi
0x18002ccfd  pop     rsi
0x18002ccfe  pop     rbx
0x18002ccff  pop     rbp
0x18002cd00  retn
```
