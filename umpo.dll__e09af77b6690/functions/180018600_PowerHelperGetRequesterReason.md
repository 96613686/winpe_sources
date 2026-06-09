# PowerHelperGetRequesterReason

- ea: `0x180018600`
- end: `0x180018760`
- name: `PowerHelperGetRequesterReason`
- size: `352`
- prototype: `unsigned __int16 *__fastcall(__int64, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000bea8`

## callees

- `0x180018060`
- `0x180018600`

## import_xrefs

- `ntdll!RtlLoadString` at `0x180018698`
- `ntdll!RtlLoadString` at `0x180018698`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001873e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001873e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800186c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800186c0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018658`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018658`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018730`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018730`

## pseudocode

```c
unsigned __int16 *__fastcall PowerHelperGetRequesterReason(__int64 a1, int *a2)
{
  bool v4; // zf
  unsigned __int16 *v5; // rsi
  HMODULE Library; // rax
  HMODULE v7; // r14
  struct _UNICODE_STRING *v8; // rdi
  unsigned int v9; // ebp
  unsigned int v10; // r8d
  WCHAR *v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rcx
  unsigned __int16 v15; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int16 *v16; // [rsp+78h] [rbp+10h] BYREF

  *a2 = 0;
  v4 = (*(_BYTE *)a1 & 1) == 0;
  v15 = 0;
  v16 = 0;
  if ( !v4 )
    return (unsigned __int16 *)(a1 + *(_QWORD *)(a1 + 8));
  v5 = 0;
  if ( (*(_BYTE *)a1 & 2) != 0 )
  {
    Library = LoadLibraryExW((LPCWSTR)(a1 + *(_QWORD *)(a1 + 8)), 0, 2u);
    v7 = Library;
    if ( Library )
    {
      v8 = 0;
      if ( (int)RtlLoadString(Library, *(unsigned __int16 *)(a1 + 16), 0, 0, &v16, &v15, 0, 0) >= 0 && v15 )
      {
        v9 = *(_DWORD *)(a1 + 20);
        if ( v9 )
        {
          v8 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, 16LL * v9);
          if ( !v8 )
            goto LABEL_14;
          v10 = 0;
          v11 = (WCHAR *)(a1 + *(_QWORD *)(a1 + 24));
          do
          {
            v12 = v10;
            v13 = -1;
            v8[v10].Buffer = v11;
            do
              ++v13;
            while ( v11[v13] );
            v11 += v13 + 1;
            ++v10;
            v8[v12].Length = 2 * v13;
          }
          while ( v10 < v9 );
        }
        v5 = PowerHelperResolveRequestReason(v16, v15, v9, v8, a2);
      }
LABEL_14:
      FreeLibrary(v7);
      if ( v8 )
        LocalFree(v8);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180018600  mov     rax, rsp
0x180018603  mov     [rax+18h], rbx
0x180018607  mov     [rax+20h], rbp
0x18001860b  push    rsi
0x18001860c  push    rdi
0x18001860d  push    r12
0x18001860f  push    r14
0x180018611  push    r15
0x180018613  sub     rsp, 40h
0x180018617  xor     r12d, r12d
0x18001861a  mov     r15, rdx
0x18001861d  mov     [rdx], r12d
0x180018620  mov     rbx, rcx
0x180018623  test    byte ptr [rcx], 1
0x180018626  mov     [rax+8], r12w
0x18001862b  mov     [rax+10h], r12
0x18001862f  jz      short loc_18001863D
0x180018631  mov     rsi, [rcx+8]
0x180018635  add     rsi, rcx
0x180018638  jmp     loc_180018744
0x18001863d  mov     r8d, 2; dwFlags
0x180018643  mov     rsi, r12
0x180018646  test    [rcx], r8b
0x180018649  jz      loc_180018744
0x18001864f  mov     rcx, [rcx+8]
0x180018653  xor     edx, edx; hFile
0x180018655  add     rcx, rbx; lpLibFileName
0x180018658  call    cs:__imp_LoadLibraryExW
0x18001865e  mov     r14, rax
0x180018661  test    rax, rax
0x180018664  jz      loc_180018744
0x18001866a  movzx   edx, word ptr [rbx+10h]
0x18001866e  lea     rax, [rsp+68h+arg_0]
0x180018673  mov     [rsp+68h+var_30], r12
0x180018678  xor     r9d, r9d
0x18001867b  mov     [rsp+68h+var_38], r12
0x180018680  xor     r8d, r8d
0x180018683  mov     [rsp+68h+var_40], rax
0x180018688  mov     rcx, r14
0x18001868b  lea     rax, [rsp+68h+arg_8]
0x180018690  mov     rdi, r12
0x180018693  mov     [rsp+68h+var_48], rax
0x180018698  call    cs:__imp_RtlLoadString
0x18001869e  test    eax, eax
0x1800186a0  js      loc_18001872D
0x1800186a6  cmp     [rsp+68h+arg_0], r12w
0x1800186ac  jz      short loc_18001872D
0x1800186ae  mov     ebp, [rbx+14h]
0x1800186b1  test    ebp, ebp
0x1800186b3  jz      short loc_180018710
0x1800186b5  mov     edx, ebp
0x1800186b7  mov     ecx, 40h ; '@'; uFlags
0x1800186bc  shl     rdx, 4; uBytes
0x1800186c0  call    cs:__imp_LocalAlloc
0x1800186c6  mov     rdi, rax
0x1800186c9  test    rax, rax
0x1800186cc  jz      short loc_18001872D
0x1800186ce  mov     rdx, [rbx+18h]
0x1800186d2  mov     r8d, r12d
0x1800186d5  add     rdx, rbx
0x1800186d8  test    ebp, ebp
0x1800186da  jz      short loc_180018710
0x1800186dc  mov     r9d, r8d
0x1800186df  add     r9, r9
0x1800186e2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800186e6  mov     [rdi+r9*8+8], rdx
0x1800186eb  inc     rcx
0x1800186ee  cmp     [rdx+rcx*2], r12w
0x1800186f3  jnz     short loc_1800186EB
0x1800186f5  movzx   eax, cx
0x1800186f8  lea     rdx, [rdx+rcx*2]
0x1800186fc  add     ax, ax
0x1800186ff  add     rdx, 2
0x180018703  inc     r8d
0x180018706  mov     [rdi+r9*8], ax
0x18001870b  cmp     r8d, ebp
0x18001870e  jb      short loc_1800186DC
0x180018710  movzx   edx, [rsp+68h+arg_0]; unsigned __int16
0x180018715  mov     r9, rdi; struct _UNICODE_STRING *
0x180018718  mov     rcx, [rsp+68h+arg_8]; unsigned __int16 *
0x18001871d  mov     r8d, ebp; unsigned int
0x180018720  mov     [rsp+68h+var_48], r15; int *
0x180018725  call    ?PowerHelperResolveRequestReason@@YAPEAGPEBGGKPEAU_UNICODE_STRING@@PEAH@Z; PowerHelperResolveRequestReason(ushort const *,ushort,ulong,_UNICODE_STRING *,int *)
0x18001872a  mov     rsi, rax
0x18001872d  mov     rcx, r14; hLibModule
0x180018730  call    cs:__imp_FreeLibrary
0x180018736  test    rdi, rdi
0x180018739  jz      short loc_180018744
0x18001873b  mov     rcx, rdi; hMem
0x18001873e  call    cs:__imp_LocalFree
0x180018744  lea     r11, [rsp+68h+var_28]
0x180018749  mov     rax, rsi
0x18001874c  mov     rbx, [r11+40h]
0x180018750  mov     rbp, [r11+48h]
0x180018754  mov     rsp, r11
0x180018757  pop     r15
0x180018759  pop     r14
0x18001875b  pop     r12
0x18001875d  pop     rdi
0x18001875e  pop     rsi
0x18001875f  retn
```
