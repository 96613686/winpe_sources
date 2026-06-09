# ConstructSpartanPackageRootFolderPath(ushort * *)

- ea: `0x180074020`
- end: `0x1800740cf`
- name: `?ConstructSpartanPackageRootFolderPath@@YAJPEAPEAG@Z`
- size: `175`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180073dc4`

## callees

- `0x180027550`
- `0x180074020`
- `0x180080f94`
- `0x1800814bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800740be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800740be`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180074047`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180074047`

## pseudocode

```c
__int64 __fastcall ConstructSpartanPackageRootFolderPath(unsigned __int16 **a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rbx
  unsigned __int64 v4; // rbx
  unsigned __int16 *v5; // rdi
  PWSTR ppszPath; // [rsp+60h] [rbp+8h] BYREF

  *a1 = 0;
  ppszPath = 0;
  v2 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0, 0, &ppszPath);
  if ( !v2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( ppszPath[v3] );
    v4 = v3 + 48;
    v5 = (unsigned __int16 *)operator new(saturated_mul(v4, 2u));
    v2 = StringCchPrintfW(v5, v4, L"%s%s", ppszPath, L"\\Packages\\Microsoft.MicrosoftEdge_8wekyb3d8bbwe");
    if ( v2 )
      operator delete(v5);
    else
      *a1 = v5;
    CoTaskMemFree(ppszPath);
  }
  return v2;
}

```

## disassembly

```asm
0x180074020  push    rbx
0x180074022  push    rbp
0x180074023  push    rsi
0x180074024  push    rdi
0x180074025  sub     rsp, 38h
0x180074029  xor     ebp, ebp
0x18007402b  lea     r9, [rsp+58h+ppszPath]; ppszPath
0x180074030  mov     [rcx], rbp
0x180074033  mov     rsi, rcx
0x180074036  lea     rcx, FOLDERID_LocalAppData; rfid
0x18007403d  mov     [rsp+58h+ppszPath], rbp
0x180074042  xor     r8d, r8d; hToken
0x180074045  xor     edx, edx; dwFlags
0x180074047  call    cs:__imp_SHGetKnownFolderPath
0x18007404d  mov     ebx, eax
0x18007404f  test    eax, eax
0x180074051  jnz     short loc_1800740C4
0x180074053  mov     rax, [rsp+58h+ppszPath]
0x180074058  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007405c  mov     rbx, rcx
0x18007405f  inc     rbx
0x180074062  cmp     [rax+rbx*2], bp
0x180074066  jnz     short loc_18007405F
0x180074068  add     rbx, 30h ; '0'
0x18007406c  mov     eax, 2
0x180074071  mul     rbx
0x180074074  cmovb   rax, rcx
0x180074078  mov     rcx, rax; Size
0x18007407b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180074080  mov     r9, [rsp+58h+ppszPath]
0x180074085  lea     r8, aSS_0; "%s%s"
0x18007408c  mov     rdi, rax
0x18007408f  mov     rdx, rbx; unsigned __int64
0x180074092  lea     rax, aPackagesMicros; "\\Packages\\Microsoft.MicrosoftEdge_8we"...
0x180074099  mov     rcx, rdi; unsigned __int16 *
0x18007409c  mov     [rsp+58h+var_38], rax
0x1800740a1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800740a6  mov     ebx, eax
0x1800740a8  test    eax, eax
0x1800740aa  jnz     short loc_1800740B1
0x1800740ac  mov     [rsi], rdi
0x1800740af  jmp     short loc_1800740B9
0x1800740b1  mov     rcx, rdi; Block
0x1800740b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800740b9  mov     rcx, [rsp+58h+ppszPath]; pv
0x1800740be  call    cs:__imp_CoTaskMemFree
0x1800740c4  mov     eax, ebx
0x1800740c6  add     rsp, 38h
0x1800740ca  pop     rdi
0x1800740cb  pop     rsi
0x1800740cc  pop     rbp
0x1800740cd  pop     rbx
0x1800740ce  retn
```
