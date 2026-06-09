# CWallpaperCore::_OnChangePosition(DESKTOP_WALLPAPER_POSITION)

- ea: `0x180042204`
- end: `0x1800423d9`
- name: `?_OnChangePosition@CWallpaperCore@@AEAAXW4DESKTOP_WALLPAPER_POSITION@@@Z`
- size: `469`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003ca90`
- `0x18003d730`

## callees

- `0x180042204`
- `0x180042808`
- `0x18004289c`
- `0x180042dc0`
- `0x180043094`
- `0x1800431a0`
- `0x180057010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x1800422b2`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800422b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800423b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800423b5`

## pseudocode

```c
void __fastcall CWallpaperCore::_OnChangePosition(__int64 a1, __int64 a2)
{
  unsigned int v2; // edi
  CWallpaperCore *v4; // rcx
  __int64 v5; // rcx
  WCHAR *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // [rsp+20h] [rbp-10h] BYREF
  void *ppv; // [rsp+28h] [rbp-8h] BYREF
  PCWSTR pszPath; // [rsp+50h] [rbp+20h] BYREF
  struct IShellFolder *v12; // [rsp+60h] [rbp+30h] BYREF
  __int64 v13; // [rsp+68h] [rbp+38h] BYREF

  v2 = a2;
  CWallpaperCore::_SetPictureLayoutSelection(a1, a2);
  CWallpaperCore::_PrepareForChange((CWallpaperCore *)a1);
  if ( (*(int (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 416) + 80LL))(*(_QWORD *)(a1 + 416), v2) >= 0
    && *(_BYTE *)(a1 + 185)
    && ((v2 - 1) & 0xFFFFFFFB) == 0 )
  {
    v5 = *(_QWORD *)(a1 + 416);
    *(_BYTE *)(a1 + 180) = 1;
    pszPath = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, PCWSTR *))(*(_QWORD *)v5 + 32LL))(v5, 0, &pszPath) >= 0 )
    {
      v6 = (WCHAR *)pszPath;
      if ( pszPath && *pszPath )
      {
        ppv = 0;
        if ( SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv) >= 0 )
        {
          v7 = *(_QWORD *)(a1 + 168);
          v9 = 0;
          v8 = *(_QWORD *)(*(_QWORD *)(v7 + 200) + 320LL);
          if ( v8 && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 104LL))(v8, &v9) >= 0 )
          {
            v13 = 0;
            if ( (*(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v9 + 136LL))(
                   v9,
                   &GUID_1af3a467_214f_4298_908e_06b03e0b39f9,
                   &v13) >= 0 )
            {
              v12 = 0;
              if ( (*(int (__fastcall **)(__int64, GUID *, struct IShellFolder **))(*(_QWORD *)v13 + 40LL))(
                     v13,
                     &GUID_000214e6_0000_0000_c000_000000000046,
                     &v12) >= 0 )
              {
                if ( CWallpaperCore::_SelectionHelper((CWallpaperCore *)a1, (struct IShellItem *)ppv, v12, 1) >= 0 )
                {
                  *(_BYTE *)(a1 + 185) = 0;
                  CWallpaperCore::_SetClearAllEnabled((CWallpaperCore *)a1, 1);
                }
                ((void (__fastcall *)(struct IShellFolder *))v12->lpVtbl->Release)(v12);
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        v6 = (WCHAR *)pszPath;
      }
      CoTaskMemFree(v6);
    }
    *(_BYTE *)(a1 + 180) = 0;
  }
  CWallpaperCore::_PostChange(v4);
}

```

## disassembly

```asm
0x180042204  mov     [rsp-18h+arg_8], rbx
0x180042209  push    rbp
0x18004220a  push    rsi
0x18004220b  push    rdi
0x18004220c  mov     rbp, rsp
0x18004220f  sub     rsp, 30h
0x180042213  mov     edi, edx
0x180042215  mov     rbx, rcx
0x180042218  call    ?_SetPictureLayoutSelection@CWallpaperCore@@AEAAXW4DESKTOP_WALLPAPER_POSITION@@@Z; CWallpaperCore::_SetPictureLayoutSelection(DESKTOP_WALLPAPER_POSITION)
0x18004221d  mov     rcx, rbx; this
0x180042220  call    ?_PrepareForChange@CWallpaperCore@@AEAAXXZ; CWallpaperCore::_PrepareForChange(void)
0x180042225  mov     rcx, [rbx+1A0h]
0x18004222c  mov     edx, edi
0x18004222e  mov     rax, [rcx]
0x180042231  mov     rax, [rax+50h]
0x180042235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004223a  xor     esi, esi
0x18004223c  test    eax, eax
0x18004223e  js      loc_1800423C8
0x180042244  cmp     [rbx+0B9h], sil
0x18004224b  jz      loc_1800423C8
0x180042251  lea     eax, [rdi-1]
0x180042254  test    eax, 0FFFFFFFBh
0x180042259  jnz     loc_1800423C8
0x18004225f  mov     rcx, [rbx+1A0h]
0x180042266  lea     r8, [rbp+pszPath]
0x18004226a  mov     byte ptr [rbx+0B4h], 1
0x180042271  xor     edx, edx
0x180042273  mov     [rbp+pszPath], rsi
0x180042277  mov     rax, [rcx]
0x18004227a  mov     rax, [rax+20h]
0x18004227e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042283  test    eax, eax
0x180042285  js      loc_1800423C1
0x18004228b  mov     rcx, [rbp+pszPath]; pszPath
0x18004228f  test    rcx, rcx
0x180042292  jz      loc_1800423B5
0x180042298  cmp     [rcx], si
0x18004229b  jz      loc_1800423B5
0x1800422a1  lea     r9, [rbp+ppv]; ppv
0x1800422a5  mov     [rbp+ppv], rsi
0x1800422a9  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800422b0  xor     edx, edx; pbc
0x1800422b2  call    cs:__imp_SHCreateItemFromParsingName
0x1800422b9  nop     dword ptr [rax+rax+00h]
0x1800422be  test    eax, eax
0x1800422c0  js      loc_1800423B1
0x1800422c6  mov     rax, [rbx+0A8h]
0x1800422cd  mov     [rbp+var_10], rsi
0x1800422d1  mov     rcx, [rax+0C8h]
0x1800422d8  mov     rcx, [rcx+140h]
0x1800422df  test    rcx, rcx
0x1800422e2  jz      loc_1800423A1
0x1800422e8  mov     rax, [rcx]
0x1800422eb  lea     rdx, [rbp+var_10]
0x1800422ef  mov     rax, [rax+68h]
0x1800422f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800422f8  test    eax, eax
0x1800422fa  js      loc_1800423A1
0x180042300  mov     rcx, [rbp+var_10]
0x180042304  lea     r8, [rbp+arg_18]
0x180042308  mov     [rbp+arg_18], rsi
0x18004230c  lea     rdx, _GUID_1af3a467_214f_4298_908e_06b03e0b39f9
0x180042313  mov     rax, [rcx]
0x180042316  mov     rax, [rax+88h]
0x18004231d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042322  test    eax, eax
0x180042324  js      short loc_180042391
0x180042326  mov     rcx, [rbp+arg_18]
0x18004232a  lea     r8, [rbp+arg_10]
0x18004232e  mov     [rbp+arg_10], rsi
0x180042332  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x180042339  mov     rax, [rcx]
0x18004233c  mov     rax, [rax+28h]
0x180042340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042345  test    eax, eax
0x180042347  js      short loc_180042381
0x180042349  mov     r8, [rbp+arg_10]; struct IShellFolder *
0x18004234d  mov     r9b, 1; bool
0x180042350  mov     rdx, [rbp+ppv]; struct IShellItem *
0x180042354  mov     rcx, rbx; this
0x180042357  call    ?_SelectionHelper@CWallpaperCore@@AEAAJPEAUIShellItem@@PEAUIShellFolder@@_N@Z; CWallpaperCore::_SelectionHelper(IShellItem *,IShellFolder *,bool)
0x18004235c  test    eax, eax
0x18004235e  js      short loc_180042371
0x180042360  mov     dl, 1; bool
0x180042362  mov     [rbx+0B9h], sil
0x180042369  mov     rcx, rbx; this
0x18004236c  call    ?_SetClearAllEnabled@CWallpaperCore@@AEAAX_N@Z; CWallpaperCore::_SetClearAllEnabled(bool)
0x180042371  mov     rcx, [rbp+arg_10]
0x180042375  mov     rax, [rcx]
0x180042378  mov     rax, [rax+10h]
0x18004237c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042381  mov     rcx, [rbp+arg_18]
0x180042385  mov     rax, [rcx]
0x180042388  mov     rax, [rax+10h]
0x18004238c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042391  mov     rcx, [rbp+var_10]
0x180042395  mov     rax, [rcx]
0x180042398  mov     rax, [rax+10h]
0x18004239c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423a1  mov     rcx, [rbp+ppv]
0x1800423a5  mov     rax, [rcx]
0x1800423a8  mov     rax, [rax+10h]
0x1800423ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423b1  mov     rcx, [rbp+pszPath]; pv
0x1800423b5  call    cs:__imp_CoTaskMemFree
0x1800423bc  nop     dword ptr [rax+rax+00h]
0x1800423c1  mov     [rbx+0B4h], sil
0x1800423c8  mov     rbx, [rsp+30h+arg_8]
0x1800423cd  add     rsp, 30h
0x1800423d1  pop     rdi
0x1800423d2  pop     rsi
0x1800423d3  pop     rbp
0x1800423d4  jmp     ?_PostChange@CWallpaperCore@@AEAAXXZ; CWallpaperCore::_PostChange(void)
```
