# CryptCATAdminReleaseContext

- ea: `0x180007590`
- end: `0x180007678`
- name: `CryptCATAdminReleaseContext`
- size: `232`
- prototype: `BOOL __stdcall(HCATADMIN hCatAdmin, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180009d2c`
- `0x18002cc80`

## callees

- `0x180005d00`
- `0x180007590`
- `0x180007680`
- `0x1800077e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000765b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000765b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800075ea`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800075ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800075e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800075f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007621`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000762a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800075e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800075f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007621`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000762a`

## pseudocode

```c
BOOL __stdcall CryptCATAdminReleaseContext(HCATADMIN hCatAdmin, DWORD dwFlags)
{
  _QWORD *i; // rsi
  _QWORD *v4; // rcx
  HLOCAL *v6; // rdi
  _QWORD *v7; // rdi
  unsigned __int16 *v8; // rcx
  int v9; // [rsp+20h] [rbp-18h]
  int v10; // [rsp+28h] [rbp-10h]

  if ( hCatAdmin && *(_DWORD *)hCatAdmin == 184 )
  {
    for ( i = (_QWORD *)*((_QWORD *)hCatAdmin + 4); i; i = (_QWORD *)*i )
    {
      v6 = (HLOCAL *)i[1];
      SortedCatalogClose(v6[2]);
      LocalFree(v6[1]);
      LocalFree(v6);
    }
    v4 = (_QWORD *)*((_QWORD *)hCatAdmin + 4);
    if ( v4 )
    {
      do
      {
        v7 = (_QWORD *)*v4;
        PkiFree(v4);
        v4 = v7;
      }
      while ( v7 );
    }
    *((_QWORD *)hCatAdmin + 5) = 0;
    *((_QWORD *)hCatAdmin + 4) = 0;
    *((_DWORD *)hCatAdmin + 12) = 0;
    LocalFree(*((HLOCAL *)hCatAdmin + 3));
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)hCatAdmin + 64));
    LocalFree(hCatAdmin);
    return 1;
  }
  else
  {
    SetLastError(0x57u);
    ErrLog_LogError(v8, 2u, 0x237u, 0, v9, v10);
    return 0;
  }
}

```

## disassembly

```asm
0x180007590  push    rbx
0x180007592  sub     rsp, 30h
0x180007596  mov     rbx, rcx
0x180007599  test    rcx, rcx
0x18000759c  jz      loc_180007656
0x1800075a2  cmp     dword ptr [rcx], 0B8h
0x1800075a8  jnz     loc_180007656
0x1800075ae  mov     [rsp+38h+arg_0], rsi
0x1800075b3  mov     rsi, [rcx+20h]
0x1800075b7  mov     [rsp+38h+arg_8], rdi
0x1800075bc  test    rsi, rsi
0x1800075bf  jnz     short loc_180007610
0x1800075c1  mov     rcx, [rbx+20h]; hMem
0x1800075c5  mov     rsi, [rsp+38h+arg_0]
0x1800075ca  test    rcx, rcx
0x1800075cd  jnz     short loc_180007640
0x1800075cf  xor     eax, eax
0x1800075d1  mov     [rbx+28h], rax
0x1800075d5  mov     [rbx+20h], rax
0x1800075d9  mov     [rbx+30h], eax
0x1800075dc  mov     rcx, [rbx+18h]; hMem
0x1800075e0  call    cs:__imp_LocalFree
0x1800075e6  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800075ea  call    cs:__imp_DeleteCriticalSection
0x1800075f0  mov     rcx, rbx; hMem
0x1800075f3  call    cs:__imp_LocalFree
0x1800075f9  mov     rdi, [rsp+38h+arg_8]
0x1800075fe  mov     eax, 1
0x180007603  add     rsp, 30h
0x180007607  pop     rbx
0x180007608  retn
0x180007610  mov     rdi, [rsi+8]
0x180007614  mov     rcx, [rdi+10h]; hMem
0x180007618  call    SortedCatalogClose
0x18000761d  mov     rcx, [rdi+8]; hMem
0x180007621  call    cs:__imp_LocalFree
0x180007627  mov     rcx, rdi; hMem
0x18000762a  call    cs:__imp_LocalFree
0x180007630  mov     rsi, [rsi]
0x180007633  test    rsi, rsi
0x180007636  jz      short loc_1800075C1
0x180007638  jmp     short loc_180007610
0x180007640  mov     rdi, [rcx]
0x180007643  call    PkiFree
0x180007648  mov     rcx, rdi
0x18000764b  test    rdi, rdi
0x18000764e  jz      loc_1800075CF
0x180007654  jmp     short loc_180007640
0x180007656  mov     ecx, 57h ; 'W'; dwErrCode
0x18000765b  call    cs:__imp_SetLastError
0x180007661  xor     r9d, r9d; unsigned int
0x180007664  mov     edx, 2; unsigned int
0x180007669  mov     r8d, 237h; unsigned int
0x18000766f  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180007674  xor     eax, eax
0x180007676  jmp     short loc_180007603
```
