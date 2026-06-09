# CDesktopManager::EnableLivePreviewInputHooks(bool,bool)

- ea: `0x18003e614`
- end: `0x18003e6af`
- name: `?EnableLivePreviewInputHooks@CDesktopManager@@SAJ_N0@Z`
- size: `155`
- prototype: `static int(bool, bool)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001d710`
- `0x18003deb8`
- `0x18003e410`

## callees

- `0x18003e614`
- `0x18003e770`
- `0x18003e9cc`

## import_xrefs

- `USER32!SetPropW` at `0x18003e698`
- `USER32!SetPropW` at `0x18003e698`
- `USER32!RemovePropW` at `0x18003e6a7`
- `USER32!RemovePropW` at `0x18003e6a7`

## pseudocode

```c
__int64 __fastcall CDesktopManager::EnableLivePreviewInputHooks(char a1, char a2, const unsigned __int16 *a3)
{
  HWND v5; // rcx
  unsigned int v6; // edi
  HWND v8; // rcx

  if ( !a1 )
  {
    CIconicBitmapRegistry::OnLivePreviewDismissed(*((CIconicBitmapRegistry **)CDesktopManager::s_pDesktopManagerInstance
                                                  + 28));
    v5 = (HWND)*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 143);
    if ( v5 )
      RemovePropW(v5, aLivepreviewwin);
  }
  v6 = CDesktopManager::EnableInputHooksHelper(a1, a2, a3, (HWND *)CDesktopManager::s_pDesktopManagerInstance + 143);
  if ( a1 )
  {
    v8 = (HWND)*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 143);
    if ( v8 )
      SetPropW(v8, aLivepreviewwin, HANDLE_FLAG_INHERIT);
  }
  return v6;
}

```

## disassembly

```asm
0x18003e614  mov     [rsp+arg_0], rbx
0x18003e619  push    rdi
0x18003e61a  sub     rsp, 20h
0x18003e61e  mov     dil, dl
0x18003e621  mov     bl, cl
0x18003e623  test    cl, cl
0x18003e625  jnz     short loc_18003E64D
0x18003e627  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18003e62e  mov     rcx, [rcx+0E0h]; this
0x18003e635  call    ?OnLivePreviewDismissed@CIconicBitmapRegistry@@QEAAXXZ; CIconicBitmapRegistry::OnLivePreviewDismissed(void)
0x18003e63a  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18003e641  mov     rcx, [rax+478h]; hWnd
0x18003e648  test    rcx, rcx
0x18003e64b  jnz     short loc_18003E6A0
0x18003e64d  mov     r9, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18003e654  mov     dl, dil; bool
0x18003e657  add     r9, 478h; HWND *
0x18003e65e  mov     cl, bl; bool
0x18003e660  call    ?EnableInputHooksHelper@CDesktopManager@@SAJ_N0PEBGPEAPEAUHWND__@@@Z; CDesktopManager::EnableInputHooksHelper(bool,bool,ushort const *,HWND__ * *)
0x18003e665  mov     edi, eax
0x18003e667  test    bl, bl
0x18003e669  jnz     short loc_18003E678
0x18003e66b  mov     rbx, [rsp+28h+arg_0]
0x18003e670  mov     eax, edi
0x18003e672  add     rsp, 20h
0x18003e676  pop     rdi
0x18003e677  retn
0x18003e678  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18003e67f  mov     rcx, [rcx+478h]; hWnd
0x18003e686  test    rcx, rcx
0x18003e689  jz      short loc_18003E66B
0x18003e68b  mov     r8d, 1; hData
0x18003e691  lea     rdx, aLivepreviewwin; "LivePreviewWindow"
0x18003e698  call    cs:__imp_SetPropW
0x18003e69e  jmp     short loc_18003E66B
0x18003e6a0  lea     rdx, aLivepreviewwin; "LivePreviewWindow"
0x18003e6a7  call    cs:__imp_RemovePropW
0x18003e6ad  jmp     short loc_18003E64D
```
