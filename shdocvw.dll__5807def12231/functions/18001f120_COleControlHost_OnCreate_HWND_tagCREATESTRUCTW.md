# COleControlHost::_OnCreate(HWND__ *,tagCREATESTRUCTW *)

- ea: `0x18001f120`
- end: `0x18001f1fb`
- name: `?_OnCreate@COleControlHost@@IEAA_JPEAUHWND__@@PEAUtagCREATESTRUCTW@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(COleControlHost *__hidden this, HWND hWnd, struct tagCREATESTRUCTW *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e1b0`

## callees

- `0x180008320`
- `0x18001f0a4`
- `0x18001f120`

## import_xrefs

- `SHELL32!__imp_SHCLSIDFromString` at `0x18001f1a3`
- `SHELL32!__imp_SHCLSIDFromString` at `0x18001f1a3`
- `USER32!GetWindowTextW` at `0x18001f175`
- `USER32!GetWindowTextW` at `0x18001f175`
- `USER32!GetParent` at `0x18001f149`
- `USER32!GetParent` at `0x18001f149`
- `USER32!SetWindowLongPtrW` at `0x18001f15b`
- `USER32!SetWindowLongPtrW` at `0x18001f15b`

## pseudocode

```c
__int64 __fastcall COleControlHost::_OnCreate(COleControlHost *this, HWND hWnd, struct tagCREATESTRUCTW *a3)
{
  struct _OCHINITSTRUCT *lpCreateParams; // rdx
  int v8; // [rsp+20h] [rbp-B8h] BYREF
  CLSID pclsid; // [rsp+24h] [rbp-B4h] BYREF
  __int64 v10; // [rsp+34h] [rbp-A4h]
  WCHAR String[56]; // [rsp+40h] [rbp-98h] BYREF

  *((_QWORD *)this + 11) = GetParent(hWnd);
  SetWindowLongPtrW(hWnd, 0, (LONG_PTR)this);
  lpCreateParams = (struct _OCHINITSTRUCT *)a3->lpCreateParams;
  if ( a3->lpCreateParams )
    return ((int)COleControlHost::_InitOCStruct(this, lpCreateParams) >= 0) - 1LL;
  if ( GetWindowTextW(hWnd, String, 50) )
  {
    v10 = 0;
    v8 = 28;
    pclsid = 0;
    if ( SHCLSIDFromString(String, &pclsid) < 0 )
      pclsid = GUID_NULL;
    v10 = 0;
    lpCreateParams = (struct _OCHINITSTRUCT *)&v8;
    return ((int)COleControlHost::_InitOCStruct(this, lpCreateParams) >= 0) - 1LL;
  }
  return 0;
}

```

## disassembly

```asm
0x18001f120  push    rbx
0x18001f122  push    rsi
0x18001f123  push    rdi
0x18001f124  sub     rsp, 0C0h
0x18001f12b  mov     rax, cs:__security_cookie
0x18001f132  xor     rax, rsp
0x18001f135  mov     [rsp+0D8h+var_28], rax
0x18001f13d  mov     rdi, rcx
0x18001f140  mov     rbx, r8
0x18001f143  mov     rcx, rdx; hWnd
0x18001f146  mov     rsi, rdx
0x18001f149  call    cs:__imp_GetParent
0x18001f14f  mov     r8, rdi; dwNewLong
0x18001f152  xor     edx, edx; nIndex
0x18001f154  mov     rcx, rsi; hWnd
0x18001f157  mov     [rdi+58h], rax
0x18001f15b  call    cs:__imp_SetWindowLongPtrW
0x18001f161  mov     rdx, [rbx]
0x18001f164  test    rdx, rdx
0x18001f167  jnz     short loc_18001F1C8
0x18001f169  lea     r8d, [rdx+32h]; nMaxCount
0x18001f16d  mov     rcx, rsi; hWnd
0x18001f170  lea     rdx, [rsp+0D8h+String]; lpString
0x18001f175  call    cs:__imp_GetWindowTextW
0x18001f17b  test    eax, eax
0x18001f17d  jz      short loc_18001F1DE
0x18001f17f  xorps   xmm0, xmm0
0x18001f182  mov     [rsp+0D8h+var_A4], 0
0x18001f18b  lea     rdx, [rsp+0D8h+pclsid]; pclsid
0x18001f190  mov     [rsp+0D8h+var_B8], 1Ch
0x18001f198  lea     rcx, [rsp+0D8h+String]; psz
0x18001f19d  movdqu  xmmword ptr [rsp+0D8h+pclsid.Data1], xmm0
0x18001f1a3  call    cs:__imp_SHCLSIDFromString
0x18001f1a9  test    eax, eax
0x18001f1ab  jns     short loc_18001F1BA
0x18001f1ad  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001f1b4  movdqu  xmmword ptr [rsp+0D8h+pclsid.Data1], xmm0
0x18001f1ba  mov     [rsp+0D8h+var_A4], 0
0x18001f1c3  lea     rdx, [rsp+0D8h+var_B8]; struct _OCHINITSTRUCT *
0x18001f1c8  mov     rcx, rdi; this
0x18001f1cb  call    ?_InitOCStruct@COleControlHost@@IEAAJPEAU_OCHINITSTRUCT@@@Z; COleControlHost::_InitOCStruct(_OCHINITSTRUCT *)
0x18001f1d0  mov     ecx, eax
0x18001f1d2  xor     eax, eax
0x18001f1d4  test    ecx, ecx
0x18001f1d6  setns   al
0x18001f1d9  dec     rax
0x18001f1dc  jmp     short loc_18001F1E0
0x18001f1de  xor     eax, eax
0x18001f1e0  mov     rcx, [rsp+0D8h+var_28]
0x18001f1e8  xor     rcx, rsp; StackCookie
0x18001f1eb  call    __security_check_cookie
0x18001f1f0  add     rsp, 0C0h
0x18001f1f7  pop     rdi
0x18001f1f8  pop     rsi
0x18001f1f9  pop     rbx
0x18001f1fa  retn
```
