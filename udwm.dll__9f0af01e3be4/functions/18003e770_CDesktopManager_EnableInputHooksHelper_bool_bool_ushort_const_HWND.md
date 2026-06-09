# CDesktopManager::EnableInputHooksHelper(bool,bool,ushort const *,HWND__ * *)

- ea: `0x18003e770`
- end: `0x18003e9c3`
- name: `?EnableInputHooksHelper@CDesktopManager@@SAJ_N0PEBGPEAPEAUHWND__@@@Z`
- size: `595`
- prototype: `__int64 __fastcall(bool, bool, const unsigned __int16 *, HWND *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18003e614`
- `0x18003e770`

## callees

- `0x18001f43c`
- `0x18003e770`
- `0x1800b0cd4`

## import_xrefs

- `USER32!PostMessageW` at `0x18003e900`
- `USER32!PostMessageW` at `0x18003e900`
- `USER32!IsWindow` at `0x18003e990`
- `USER32!IsWindow` at `0x18003e990`
- `USER32!SetCursor` at `0x18003e946`
- `USER32!SetCursor` at `0x18003e946`
- `USER32!ChangeWindowMessageFilterEx` at `0x18003e83c`
- `USER32!ChangeWindowMessageFilterEx` at `0x18003e850`
- `USER32!ChangeWindowMessageFilterEx` at `0x18003e862`
- `USER32!ChangeWindowMessageFilterEx` at `0x18003e874`
- `USER32!ChangeWindowMessageFilterEx` at `0x18003e886`
- `USER32!ChangeWindowMessageFilterEx` at `0x18003e83c`
- `USER32!ChangeWindowMessageFilterEx` at `0x18003e850`
- `USER32!ChangeWindowMessageFilterEx` at `0x18003e862`
- `USER32!ChangeWindowMessageFilterEx` at `0x18003e874`
- `USER32!ChangeWindowMessageFilterEx` at `0x18003e886`
- `USER32!SendNotifyMessageW` at `0x18003e7b1`
- `USER32!SendNotifyMessageW` at `0x18003e7b1`
- `USER32!GetForegroundWindow` at `0x18003e79c`
- `USER32!GetForegroundWindow` at `0x18003e79c`
- `USER32!LockSetForegroundWindow` at `0x18003e8d6`
- `USER32!LockSetForegroundWindow` at `0x18003e8d6`
- `USER32!LoadCursorW` at `0x18003e93d`
- `USER32!LoadCursorW` at `0x18003e93d`
- `ext-ms-win-ntuser-private-l1-1-1!CreateWindowInBand` at `0x18003e815`
- `ext-ms-win-ntuser-private-l1-1-1!CreateWindowInBand` at `0x18003e815`

## pseudocode

```c
__int64 __fastcall CDesktopManager::EnableInputHooksHelper(char a1, char a2, const unsigned __int16 *a3, HWND *a4)
{
  unsigned int v4; // ebx
  HWND ForegroundWindow; // r14
  int v8; // ecx
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  HWND WindowInBand; // rax
  HWND v13; // rbp
  bool v14; // r8
  HWND v16; // rcx
  unsigned int v17; // eax
  HCURSOR CursorW; // rax
  bool v19; // r8

  v4 = 0;
  if ( CDesktopManager::s_pDesktopManagerInstance )
  {
    if ( a1 )
    {
      ForegroundWindow = GetForegroundWindow();
      SendNotifyMessageW(ForegroundWindow, 0x1Fu, 0, 0);
      if ( a2 )
      {
        v8 = 0;
        v9 = 0;
        v10 = 0;
        v11 = 0;
      }
      else
      {
        v11 = *((_DWORD *)CDesktopManager::s_pDesktopManagerInstance + 95);
        v10 = *((_DWORD *)CDesktopManager::s_pDesktopManagerInstance + 96);
        v9 = *((_DWORD *)CDesktopManager::s_pDesktopManagerInstance + 97);
        v8 = *((_DWORD *)CDesktopManager::s_pDesktopManagerInstance + 98);
      }
      WindowInBand = (HWND)CreateWindowInBand(
                             136,
                             L"LivePreview",
                             0,
                             0x80000000LL,
                             v11,
                             v10,
                             v9,
                             v8,
                             0,
                             0,
                             g_hInstance,
                             0,
                             2);
      v13 = WindowInBand;
      if ( WindowInBand )
      {
        *a4 = WindowInBand;
        ChangeWindowMessageFilterEx(WindowInBand, 0x319u, 1u, 0);
        ChangeWindowMessageFilterEx(v13, 0x112u, 1u, 0);
        ChangeWindowMessageFilterEx(v13, 0x1Fu, 1u, 0);
        ChangeWindowMessageFilterEx(v13, 6u, 1u, 0);
        ChangeWindowMessageFilterEx(v13, 0x3Du, 1u, 0);
        if ( a2 )
          return v4;
        *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 144) = ForegroundWindow;
        v4 = CDesktopManager::SetForegroundWindowAsync(v13, v13, v14);
        if ( (v4 & 0x80000000) == 0 )
        {
          CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
          SetCursor(CursorW);
          return v4;
        }
        v17 = 2883;
      }
      else
      {
        v4 = -2147024890;
        v17 = 2866;
      }
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1800F9060, 2u, v4, v17, 0);
      CDesktopManager::EnableInputHooksHelper(0, 0, L"LivePreview", a4);
      return v4;
    }
    if ( *a4 )
    {
      LockSetForegroundWindow(2u);
      v16 = (HWND)*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 144);
      if ( v16 )
      {
        if ( IsWindow(v16) )
          CDesktopManager::SetForegroundWindowAsync(
            *a4,
            *((HWND *)CDesktopManager::s_pDesktopManagerInstance + 144),
            v19);
        *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 144) = 0;
      }
      PostMessageW(*a4, 0x10u, 0, 0);
      *a4 = 0;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18003e770  push    rbx
0x18003e772  push    rbp
0x18003e773  push    rsi
0x18003e774  push    rdi
0x18003e775  push    r12
0x18003e777  push    r14
0x18003e779  push    r15
0x18003e77b  sub     rsp, 70h
0x18003e77f  xor     ebx, ebx
0x18003e781  mov     rdi, r9
0x18003e784  cmp     cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA, rbx; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18003e78b  mov     r15b, dl
0x18003e78e  jz      loc_18003E895
0x18003e794  test    cl, cl
0x18003e796  jz      loc_18003E8CC
0x18003e79c  call    cs:__imp_GetForegroundWindow
0x18003e7a2  xor     r9d, r9d; lParam
0x18003e7a5  lea     edx, [rbx+1Fh]; Msg
0x18003e7a8  mov     rcx, rax; hWnd
0x18003e7ab  xor     r8d, r8d; wParam
0x18003e7ae  mov     r14, rax
0x18003e7b1  call    cs:__imp_SendNotifyMessageW
0x18003e7b7  test    r15b, r15b
0x18003e7ba  jz      loc_18003E8A6
0x18003e7c0  xor     ecx, ecx
0x18003e7c2  xor     edx, edx
0x18003e7c4  xor     r8d, r8d
0x18003e7c7  xor     r9d, r9d
0x18003e7ca  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18003e7d1  mov     esi, 2
0x18003e7d6  mov     [rsp+0A8h+var_48], esi
0x18003e7da  mov     [rsp+0A8h+var_50], rbx
0x18003e7df  mov     [rsp+0A8h+var_58], rax
0x18003e7e4  mov     [rsp+0A8h+var_60], rbx
0x18003e7e9  mov     [rsp+0A8h+var_68], rbx
0x18003e7ee  mov     [rsp+0A8h+var_70], ecx
0x18003e7f2  mov     ecx, 88h
0x18003e7f7  mov     [rsp+0A8h+var_78], edx
0x18003e7fb  lea     rdx, aLivepreview; "LivePreview"
0x18003e802  mov     dword ptr [rsp+0A8h+var_80], r8d
0x18003e807  xor     r8d, r8d
0x18003e80a  mov     [rsp+0A8h+var_88], r9d
0x18003e80f  mov     r9d, 80000000h
0x18003e815  call    cs:__imp_CreateWindowInBand
0x18003e81b  mov     rbp, rax
0x18003e81e  test    rax, rax
0x18003e821  jz      loc_18003E90B
0x18003e827  lea     r12d, [rsi-1]
0x18003e82b  mov     [rdi], rax
0x18003e82e  mov     r8d, r12d; action
0x18003e831  xor     r9d, r9d; pChangeFilterStruct
0x18003e834  mov     edx, 319h; message
0x18003e839  mov     rcx, rax; hwnd
0x18003e83c  call    cs:__imp_ChangeWindowMessageFilterEx
0x18003e842  xor     r9d, r9d; pChangeFilterStruct
0x18003e845  mov     r8d, r12d; action
0x18003e848  mov     edx, 112h; message
0x18003e84d  mov     rcx, rbp; hwnd
0x18003e850  call    cs:__imp_ChangeWindowMessageFilterEx
0x18003e856  xor     r9d, r9d; pChangeFilterStruct
0x18003e859  lea     edx, [rsi+1Dh]; message
0x18003e85c  mov     r8d, r12d; action
0x18003e85f  mov     rcx, rbp; hwnd
0x18003e862  call    cs:__imp_ChangeWindowMessageFilterEx
0x18003e868  xor     r9d, r9d; pChangeFilterStruct
0x18003e86b  lea     edx, [rsi+4]; message
0x18003e86e  mov     r8d, r12d; action
0x18003e871  mov     rcx, rbp; hwnd
0x18003e874  call    cs:__imp_ChangeWindowMessageFilterEx
0x18003e87a  xor     r9d, r9d; pChangeFilterStruct
0x18003e87d  lea     edx, [rsi+3Bh]; message
0x18003e880  mov     r8d, r12d; action
0x18003e883  mov     rcx, rbp; hwnd
0x18003e886  call    cs:__imp_ChangeWindowMessageFilterEx
0x18003e88c  test    r15b, r15b
0x18003e88f  jz      loc_18003E917
0x18003e895  mov     eax, ebx
0x18003e897  add     rsp, 70h
0x18003e89b  pop     r15
0x18003e89d  pop     r14
0x18003e89f  pop     r12
0x18003e8a1  pop     rdi
0x18003e8a2  pop     rsi
0x18003e8a3  pop     rbp
0x18003e8a4  pop     rbx
0x18003e8a5  retn
0x18003e8a6  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18003e8ad  mov     r9d, [rax+17Ch]
0x18003e8b4  mov     r8d, [rax+180h]
0x18003e8bb  mov     edx, [rax+184h]
0x18003e8c1  mov     ecx, [rax+188h]
0x18003e8c7  jmp     loc_18003E7CA
0x18003e8cc  cmp     [r9], rbx
0x18003e8cf  jz      short loc_18003E895
0x18003e8d1  mov     ecx, 2; uLockCode
0x18003e8d6  call    cs:__imp_LockSetForegroundWindow
0x18003e8dc  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18003e8e3  mov     rcx, [rax+480h]; hWnd
0x18003e8ea  test    rcx, rcx
0x18003e8ed  jnz     loc_18003E990
0x18003e8f3  mov     rcx, [rdi]; hWnd
0x18003e8f6  xor     r9d, r9d; lParam
0x18003e8f9  xor     r8d, r8d; wParam
0x18003e8fc  lea     edx, [r9+10h]; Msg
0x18003e900  call    cs:__imp_PostMessageW
0x18003e906  mov     [rdi], rbx
0x18003e909  jmp     short loc_18003E895
0x18003e90b  mov     ebx, 80070006h
0x18003e910  mov     eax, 0B32h
0x18003e915  jmp     short loc_18003E956
0x18003e917  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18003e91e  mov     rdx, rbp; wParam
0x18003e921  mov     rcx, rbp; hWnd
0x18003e924  mov     [rax+480h], r14
0x18003e92b  call    ?SetForegroundWindowAsync@CDesktopManager@@SAJPEAUHWND__@@0_N@Z; CDesktopManager::SetForegroundWindowAsync(HWND__ *,HWND__ *,bool)
0x18003e930  mov     ebx, eax
0x18003e932  test    eax, eax
0x18003e934  js      short loc_18003E951
0x18003e936  mov     edx, 7F00h; lpCursorName
0x18003e93b  xor     ecx, ecx; hInstance
0x18003e93d  call    cs:__imp_LoadCursorW
0x18003e943  mov     rcx, rax; hCursor
0x18003e946  call    cs:__imp_SetCursor
0x18003e94c  jmp     loc_18003E895
0x18003e951  mov     eax, 0B43h
0x18003e956  xor     r8d, r8d
0x18003e959  lea     rdx, qword_1800F9060; int *
0x18003e960  mov     [rsp+0A8h+var_80], r8; void *
0x18003e965  mov     r9d, ebx; int
0x18003e968  mov     [rsp+0A8h+var_88], eax; unsigned int
0x18003e96c  lea     ecx, [r8+14h]; unsigned int
0x18003e970  mov     r8d, esi; unsigned int
0x18003e973  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18003e978  mov     r9, rdi; HWND *
0x18003e97b  lea     r8, aLivepreview; "LivePreview"
0x18003e982  xor     edx, edx; bool
0x18003e984  xor     ecx, ecx; bool
0x18003e986  call    ?EnableInputHooksHelper@CDesktopManager@@SAJ_N0PEBGPEAPEAUHWND__@@@Z; CDesktopManager::EnableInputHooksHelper(bool,bool,ushort const *,HWND__ * *)
0x18003e98b  jmp     loc_18003E895
0x18003e990  call    cs:__imp_IsWindow
0x18003e996  test    eax, eax
0x18003e998  jz      short loc_18003E9B0
0x18003e99a  mov     rdx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18003e9a1  mov     rcx, [rdi]; hWnd
0x18003e9a4  mov     rdx, [rdx+480h]; wParam
0x18003e9ab  call    ?SetForegroundWindowAsync@CDesktopManager@@SAJPEAUHWND__@@0_N@Z; CDesktopManager::SetForegroundWindowAsync(HWND__ *,HWND__ *,bool)
0x18003e9b0  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18003e9b7  mov     [rax+480h], rbx
0x18003e9be  jmp     loc_18003E8F3
```
