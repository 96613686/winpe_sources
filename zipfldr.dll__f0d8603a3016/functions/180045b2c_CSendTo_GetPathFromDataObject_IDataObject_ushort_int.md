# CSendTo::_GetPathFromDataObject(IDataObject *,ushort *,int)

- ea: `0x180045b2c`
- end: `0x180045bf1`
- name: `?_GetPathFromDataObject@CSendTo@@AEAAJPEAUIDataObject@@PEAGH@Z`
- size: `197`
- prototype: `int(CSendTo *__hidden this, struct IDataObject *, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800450f0`
- `0x180045a30`

## callees

- `0x180010c30`
- `0x180036f50`
- `0x180045b2c`
- `0x180071010`

## import_xrefs

- `SHELL32!SHGetItemFromDataObject` at `0x180045b64`
- `SHELL32!SHGetItemFromDataObject` at `0x180045b64`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180045bb5`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180045bb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045bc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045bc0`

## pseudocode

```c
__int64 __fastcall CSendTo::_GetPathFromDataObject(CSendTo *this, struct IDataObject *a2, unsigned __int16 *a3)
{
  HRESULT v4; // ebx
  LPVOID pv; // [rsp+20h] [rbp-28h] BYREF
  void *ppv; // [rsp+28h] [rbp-20h] BYREF

  *a3 = 0;
  ppv = 0;
  v4 = SHGetItemFromDataObject(a2, DOGIF_DEFAULT, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  if ( v4 >= 0 )
  {
    pv = 0;
    v4 = (*(__int64 (__fastcall **)(void *, __int64, LPVOID *))(*(_QWORD *)ppv + 40LL))(ppv, 2147844096LL, &pv);
    if ( v4 >= 0 )
    {
      v4 = StringCchCopyW(a3, 0x104u, (const unsigned __int16 *)pv);
      if ( v4 >= 0 )
        PathRemoveFileSpecW(a3);
      CoTaskMemFree(pv);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180045b2c  mov     [rsp+arg_0], rbx
0x180045b31  push    rdi
0x180045b32  sub     rsp, 40h
0x180045b36  mov     rax, cs:__security_cookie
0x180045b3d  xor     rax, rsp
0x180045b40  mov     [rsp+48h+var_18], rax
0x180045b45  xor     eax, eax
0x180045b47  lea     r9, [rsp+48h+ppv]; ppv
0x180045b4c  mov     [r8], ax
0x180045b50  mov     rdi, r8
0x180045b53  mov     rcx, rdx; pdtobj
0x180045b56  mov     [rsp+48h+ppv], rax
0x180045b5b  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180045b62  xor     edx, edx; dwFlags
0x180045b64  call    cs:__imp_SHGetItemFromDataObject
0x180045b6a  mov     ebx, eax
0x180045b6c  test    eax, eax
0x180045b6e  js      short loc_180045BD7
0x180045b70  mov     rcx, [rsp+48h+ppv]
0x180045b75  lea     r8, [rsp+48h+pv]
0x180045b7a  mov     [rsp+48h+pv], 0
0x180045b83  mov     edx, 80058000h
0x180045b88  mov     rax, [rcx]
0x180045b8b  mov     rax, [rax+28h]
0x180045b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b94  mov     ebx, eax
0x180045b96  test    eax, eax
0x180045b98  js      short loc_180045BC6
0x180045b9a  mov     r8, [rsp+48h+pv]; unsigned __int16 *
0x180045b9f  mov     edx, 104h; unsigned __int64
0x180045ba4  mov     rcx, rdi; unsigned __int16 *
0x180045ba7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180045bac  mov     ebx, eax
0x180045bae  test    eax, eax
0x180045bb0  js      short loc_180045BBB
0x180045bb2  mov     rcx, rdi; pszPath
0x180045bb5  call    cs:__imp_PathRemoveFileSpecW
0x180045bbb  mov     rcx, [rsp+48h+pv]; pv
0x180045bc0  call    cs:__imp_CoTaskMemFree
0x180045bc6  mov     rcx, [rsp+48h+ppv]
0x180045bcb  mov     rax, [rcx]
0x180045bce  mov     rax, [rax+10h]
0x180045bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045bd7  mov     eax, ebx
0x180045bd9  mov     rcx, [rsp+48h+var_18]
0x180045bde  xor     rcx, rsp; StackCookie
0x180045be1  call    __security_check_cookie
0x180045be6  mov     rbx, [rsp+48h+arg_0]
0x180045beb  add     rsp, 40h
0x180045bef  pop     rdi
0x180045bf0  retn
```
