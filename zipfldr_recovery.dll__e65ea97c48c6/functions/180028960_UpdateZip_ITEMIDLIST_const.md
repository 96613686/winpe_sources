# UpdateZip(_ITEMIDLIST const *)

- ea: `0x180028960`
- end: `0x1800289b8`
- name: `?UpdateZip@@YAXPEFBU_ITEMIDLIST@@@Z`
- size: `88`
- prototype: `void __fastcall(LPCITEMIDLIST pidl)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180028928`

## callees

- `0x180028960`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x180028976`
- `SHELL32!SHChangeNotify` at `0x1800289a3`
- `SHELL32!SHChangeNotify` at `0x180028976`
- `SHELL32!SHChangeNotify` at `0x1800289a3`
- `SHELL32!__imp_ILRemoveLastID` at `0x180028990`
- `SHELL32!__imp_ILRemoveLastID` at `0x180028990`
- `SHELL32!__imp_ILClone` at `0x18002897f`
- `SHELL32!__imp_ILClone` at `0x18002897f`
- `SHELL32!__imp_ILFree` at `0x1800289ac`
- `SHELL32!__imp_ILFree` at `0x1800289ac`

## pseudocode

```c
void __fastcall UpdateZip(LPCITEMIDLIST pidl)
{
  ITEMIDLIST *v2; // rax
  ITEMIDLIST *v3; // rbx

  SHChangeNotify(0x2000, 0, pidl, 0);
  v2 = ILClone(pidl);
  v3 = v2;
  if ( v2 )
  {
    ILRemoveLastID(v2);
    SHChangeNotify(4096, 0, v3, 0);
    ILFree(v3);
  }
}

```

## disassembly

```asm
0x180028960  push    rbx
0x180028962  sub     rsp, 20h
0x180028966  mov     rbx, rcx
0x180028969  mov     r8, rcx; dwItem1
0x18002896c  mov     ecx, 2000h; wEventId
0x180028971  xor     r9d, r9d; dwItem2
0x180028974  xor     edx, edx; uFlags
0x180028976  call    cs:__imp_SHChangeNotify
0x18002897c  mov     rcx, rbx; pidl
0x18002897f  call    cs:__imp_ILClone
0x180028985  mov     rbx, rax
0x180028988  test    rax, rax
0x18002898b  jz      short loc_1800289B2
0x18002898d  mov     rcx, rax; pidl
0x180028990  call    cs:__imp_ILRemoveLastID
0x180028996  xor     r9d, r9d; dwItem2
0x180028999  mov     r8, rbx; dwItem1
0x18002899c  xor     edx, edx; uFlags
0x18002899e  mov     ecx, 1000h; wEventId
0x1800289a3  call    cs:__imp_SHChangeNotify
0x1800289a9  mov     rcx, rbx; pidl
0x1800289ac  call    cs:__imp_ILFree
0x1800289b2  add     rsp, 20h
0x1800289b6  pop     rbx
0x1800289b7  retn
```
