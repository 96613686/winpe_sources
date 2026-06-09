# ForceContactCommit(IContact *)

- ea: `0x180012b74`
- end: `0x180012cff`
- name: `?ForceContactCommit@@YAJPEAUIContact@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(struct IContact *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000eef0`

## callees

- `0x180002818`
- `0x180006f7c`
- `0x180008f74`
- `0x180012b74`
- `0x180013950`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `MSOERT2!OpenFileStreamW` at `0x180012c7c`
- `MSOERT2!OpenFileStreamW` at `0x180012c7c`
- `KERNEL32!GetLastError` at `0x180012c4a`
- `KERNEL32!GetLastError` at `0x180012c4a`
- `KERNEL32!DeleteFileW` at `0x180012c40`
- `KERNEL32!DeleteFileW` at `0x180012c40`

## pseudocode

```c
__int64 __fastcall ForceContactCommit(struct IContact *a1)
{
  struct IContactVtbl *lpVtbl; // rax
  int v3; // eax
  signed int PathFromContact; // ebx
  int v5; // edi
  LPCWSTR v6; // rbx
  const WCHAR *v7; // rcx
  signed int LastError; // eax
  __int64 v10; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v11; // [rsp+28h] [rbp-D8h] BYREF
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v14[264]; // [rsp+50h] [rbp-B0h] BYREF

  v11 = 0;
  STRW::STRW((STRW *)&v12, v14, 0x104u);
  lpVtbl = a1->lpVtbl;
  v10 = 0;
  v3 = ((__int64 (__fastcall *)(struct IContact *, _QWORD))lpVtbl->CommitChanges)(a1, 0);
  PathFromContact = v3;
  if ( v3 >= 0 )
    goto LABEL_15;
  if ( v3 != -2147024681 )
    goto LABEL_16;
  PathFromContact = GetPathFromContact(a1, (struct STRW *)&v12);
  if ( PathFromContact < 0 )
    goto LABEL_16;
  PathFromContact = ((__int64 (__fastcall *)(struct IContact *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
                      a1,
                      &GUID_00000109_0000_0000_c000_000000000046,
                      &v11);
  if ( PathFromContact < 0 )
    goto LABEL_16;
  v5 = v12;
  v6 = &Str;
  v7 = &Str;
  if ( v12 )
    v7 = lpFileName[0];
  if ( !DeleteFileW(v7) )
  {
    LastError = GetLastError();
    PathFromContact = LastError;
    if ( LastError > 0 )
      PathFromContact = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_16;
  }
  if ( v5 )
    v6 = lpFileName[0];
  PathFromContact = OpenFileStreamW(v6, 1, 0x40000000, &v10);
  if ( PathFromContact >= 0 )
  {
    PathFromContact = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v11 + 48LL))(v11, v10, 0);
    if ( PathFromContact >= 0 )
    {
      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v10);
LABEL_15:
      PathFromContact = 0;
    }
  }
LABEL_16:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v10);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v11);
  v12 = 0;
  BUFFER::ReleaseStorage((BUFFER *)lpFileName);
  return (unsigned int)PathFromContact;
}

```

## disassembly

```asm
0x180012b74  mov     [rsp-8+arg_8], rbx
0x180012b79  mov     [rsp-8+arg_10], rdi
0x180012b7e  push    rbp
0x180012b7f  lea     rbp, [rsp-170h]
0x180012b87  sub     rsp, 270h
0x180012b8e  mov     rax, cs:__security_cookie
0x180012b95  xor     rax, rsp
0x180012b98  mov     [rbp+170h+var_10], rax
0x180012b9f  mov     rdi, rcx
0x180012ba2  mov     [rsp+270h+var_248], 0
0x180012bab  lea     rcx, [rsp+270h+var_240]; this
0x180012bb0  mov     r8d, 104h; unsigned int
0x180012bb6  lea     rdx, [rsp+270h+var_220]; unsigned __int16 *
0x180012bbb  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180012bc0  mov     rax, [rdi]
0x180012bc3  xor     edx, edx
0x180012bc5  mov     rcx, rdi
0x180012bc8  mov     [rsp+270h+var_250], 0
0x180012bd1  mov     rax, [rax+28h]
0x180012bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bda  mov     ebx, eax
0x180012bdc  test    eax, eax
0x180012bde  jns     loc_180012CB1
0x180012be4  cmp     eax, 800700D7h
0x180012be9  jnz     loc_180012CB3
0x180012bef  lea     rdx, [rsp+270h+var_240]; struct STRW *
0x180012bf4  mov     rcx, rdi; struct IContact *
0x180012bf7  call    ?GetPathFromContact@@YAJPEAUIContact@@PEAVSTRW@@@Z; GetPathFromContact(IContact *,STRW *)
0x180012bfc  mov     ebx, eax
0x180012bfe  test    eax, eax
0x180012c00  js      loc_180012CB3
0x180012c06  mov     rax, [rdi]
0x180012c09  lea     r8, [rsp+270h+var_248]
0x180012c0e  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x180012c15  mov     rcx, rdi
0x180012c18  mov     rax, [rax]
0x180012c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c20  mov     ebx, eax
0x180012c22  test    eax, eax
0x180012c24  js      loc_180012CB3
0x180012c2a  mov     edi, [rsp+270h+var_240]
0x180012c2e  lea     rbx, Str
0x180012c35  test    edi, edi
0x180012c37  mov     rcx, rbx
0x180012c3a  cmovnz  rcx, [rsp+270h+lpFileName]; lpFileName
0x180012c40  call    cs:__imp_DeleteFileW
0x180012c46  test    eax, eax
0x180012c48  jnz     short loc_180012C61
0x180012c4a  call    cs:__imp_GetLastError
0x180012c50  mov     ebx, eax
0x180012c52  test    eax, eax
0x180012c54  jle     short loc_180012CB3
0x180012c56  movzx   ebx, ax
0x180012c59  or      ebx, 80070000h
0x180012c5f  jmp     short loc_180012CB3
0x180012c61  test    edi, edi
0x180012c63  lea     r9, [rsp+270h+var_250]
0x180012c68  mov     edx, 1
0x180012c6d  mov     r8d, 40000000h
0x180012c73  cmovnz  rbx, [rsp+270h+lpFileName]
0x180012c79  mov     rcx, rbx
0x180012c7c  call    cs:__imp_OpenFileStreamW
0x180012c82  mov     ebx, eax
0x180012c84  test    eax, eax
0x180012c86  js      short loc_180012CB3
0x180012c88  mov     rcx, [rsp+270h+var_248]
0x180012c8d  xor     r8d, r8d
0x180012c90  mov     rdx, [rsp+270h+var_250]
0x180012c95  mov     rax, [rcx]
0x180012c98  mov     rax, [rax+30h]
0x180012c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ca1  mov     ebx, eax
0x180012ca3  test    eax, eax
0x180012ca5  js      short loc_180012CB3
0x180012ca7  lea     rcx, [rsp+270h+var_250]
0x180012cac  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180012cb1  xor     ebx, ebx
0x180012cb3  lea     rcx, [rsp+270h+var_250]
0x180012cb8  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180012cbd  lea     rcx, [rsp+270h+var_248]
0x180012cc2  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180012cc7  lea     rcx, [rsp+270h+lpFileName]; this
0x180012ccc  mov     [rsp+270h+var_240], 0
0x180012cd4  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x180012cd9  mov     eax, ebx
0x180012cdb  mov     rcx, [rbp+170h+var_10]
0x180012ce2  xor     rcx, rsp; StackCookie
0x180012ce5  call    __security_check_cookie
0x180012cea  lea     r11, [rsp+270h+var_s0]
0x180012cf2  mov     rbx, [r11+18h]
0x180012cf6  mov     rdi, [r11+20h]
0x180012cfa  mov     rsp, r11
0x180012cfd  pop     rbp
0x180012cfe  retn
```
