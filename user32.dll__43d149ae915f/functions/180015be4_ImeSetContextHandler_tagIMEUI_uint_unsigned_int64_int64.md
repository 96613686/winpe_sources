# ImeSetContextHandler(tagIMEUI *,uint,unsigned __int64,__int64)

- ea: `0x180015be4`
- end: `0x180015f89`
- name: `?ImeSetContextHandler@@YA_JPEAUtagIMEUI@@I_K_J@Z`
- size: `933`
- prototype: `__int64 __fastcall(struct tagIMEUI *, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x180011800`

## callees

- `0x18000a9f0`
- `0x18000acb0`
- `0x180015780`
- `0x180015be4`
- `0x180015f90`
- `0x180016040`
- `0x1800160a4`
- `0x180016310`
- `0x180016488`
- `0x1800169a0`
- `0x180017b3c`
- `0x180096e00`
- `0x1800a2010`

## import_xrefs

- `win32u!NtUserSetImeOwnerWindow` at `0x180015da0`
- `win32u!NtUserSetImeOwnerWindow` at `0x180015ef4`
- `win32u!NtUserSetImeOwnerWindow` at `0x180015da0`
- `win32u!NtUserSetImeOwnerWindow` at `0x180015ef4`
- `win32u!NtUserCheckImeShowStatusInThread` at `0x180015ca7`
- `win32u!NtUserCheckImeShowStatusInThread` at `0x180015ca7`
- `win32u!NtUserGetIMEShowStatus` at `0x180015c5a`
- `win32u!NtUserGetIMEShowStatus` at `0x180015c5a`
- `win32u!NtUserQueryWindow` at `0x180015c6f`
- `win32u!NtUserQueryWindow` at `0x180015cf9`
- `win32u!NtUserQueryWindow` at `0x180015dcb`
- `win32u!NtUserQueryWindow` at `0x180015c6f`
- `win32u!NtUserQueryWindow` at `0x180015cf9`
- `win32u!NtUserQueryWindow` at `0x180015dcb`

## pseudocode

```c
__int64 __fastcall ImeSetContextHandler(__int64 **a1, unsigned int a2, unsigned __int64 a3, __int64 a4)
{
  HWND v8; // r14
  __int64 v9; // rsi
  HWND v10; // rax
  struct tagWND *v11; // rax
  __int64 v12; // rdx
  struct tagWND *v13; // rdi
  __int64 v15; // rcx
  __int64 Window; // rbp
  HIMC v17; // rdi
  HWND v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rsi
  __int64 (__fastcall *v21)(); // rax
  __int64 *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rdx
  HWND v32; // rcx
  struct tagWND *v33; // rdi
  struct tagWND *v34; // rax
  __int64 NonChildAncestor; // rax
  __int64 v36; // r8
  HWND v37; // rcx
  __int64 *v38; // rax
  __int64 v39; // rcx
  _BYTE v40[32]; // [rsp+30h] [rbp-78h] BYREF

  *((_DWORD *)a1 + 11) &= ~2u;
  v8 = (HWND)a1[2];
  *((_DWORD *)a1 + 11) |= (_DWORD)a3 != 0 ? 2 : 0;
  if ( a3 )
  {
    if ( !a1[4] )
      a1[4] = (__int64 *)CreateIMEUI((struct tagIMEUI *)a1, (HKL)a1[3]);
    if ( *a1 )
      v15 = **a1;
    else
      v15 = 0;
    Window = NtUserQueryWindow(v15, 4);
    v17 = (HIMC)((__int64 (__fastcall *)(__int64))off_1800C85D0[0])(Window);
    if ( v17 )
    {
      v37 = *a1 ? (HWND)**a1 : 0LL;
      if ( !(unsigned int)ImeIsUsableContext(v37, v17) )
      {
        ImeSetImc((struct tagIMEUI *)a1, 0);
        return 0;
      }
    }
    ImeSetImc((struct tagIMEUI *)a1, v17);
    v18 = (HWND)a1[4];
    if ( v18 )
      SetWindowLongPtrW(v18, 0, (LONG_PTR)v17);
    if ( v17 )
    {
      v19 = ((__int64 (__fastcall *)(HIMC))off_1800C8628[0])(v17);
      v20 = v19;
      if ( !v19 )
        return 0;
      if ( Window != *(_QWORD *)v19 )
      {
        ((void (__fastcall *)(HIMC))off_1800C8630[0])(v17);
        return 0;
      }
      if ( (*(_DWORD *)(v19 + 364) & 0x40000) != 0 && v8 != (HWND)Window )
      {
        memset(v40, 0, 28);
        ((void (__fastcall *)(HIMC, _BYTE *))off_1800C8618[0])(v17, v40);
        *(_DWORD *)(v20 + 364) &= ~0x40000u;
      }
      v21 = off_1800C8630[0];
      *(_DWORD *)(v20 + 388) = a4;
      ((void (__fastcall *)(HIMC))v21)(v17);
      v22 = *a1;
      if ( *a1 )
        v22 = (__int64 *)*v22;
      if ( (unsigned int)NtUserSetImeOwnerWindow(v22, Window) )
        a1[2] = (__int64 *)Window;
    }
    else
    {
      v38 = *a1;
      a1[2] = (__int64 *)Window;
      if ( v38 )
        v39 = *v38;
      else
        v39 = 0;
      NtUserSetImeOwnerWindow(v39, 0);
    }
  }
  v9 = SendMessageToUI((struct tagIMEUI *)a1, a2, a3, a4, 0);
  if ( *a1 )
  {
    if ( (*((_BYTE *)a1 + 44) & 0x20) == 0 || !(unsigned int)NtUserGetIMEShowStatus() )
      return v9;
    v10 = (HWND)NtUserQueryWindow(**a1, 4);
    v11 = ValidateHwndNoRip(v10);
    v13 = v11;
    if ( (_DWORD)a3 != 1 )
    {
      if ( *a1 )
        v23 = **a1;
      else
        v23 = 0;
      NtUserQueryWindow(v23, 3);
      if ( !v13 || (v25 = GETPTI(*a1, v24), v26 = GETPTI(v13, v25), v28 != v26) || !v27 )
      {
        if ( IsWindow(v8) )
        {
          SendOpenStatusNotify((struct tagIMEUI *)a1, v8, 0);
        }
        else
        {
          *((_DWORD *)a1 + 11) &= ~1u;
          SendMessageToUI((struct tagIMEUI *)a1, 0x282u, 1u, 0, 0);
        }
      }
      return v9;
    }
    if ( v11 )
    {
      v29 = GETPTI(*a1, v12);
      v30 = GETPTI(v13, v29);
      if ( v31 == v30 )
      {
        v32 = (HWND)a1[2];
        if ( (*((_BYTE *)a1 + 44) & 1) == 0 )
        {
          if ( !ValidateHwndNoRip(v32) )
            goto LABEL_7;
          goto LABEL_45;
        }
        v33 = ValidateHwndNoRip(v32);
        if ( v33 )
        {
          v34 = ValidateHwndNoRip(v8);
          if ( v34 )
          {
            GetNonChildAncestor(v34);
            NonChildAncestor = GetNonChildAncestor(v33);
            if ( NonChildAncestor != v36 )
            {
              SendOpenStatusNotify((struct tagIMEUI *)a1, v8, 0);
LABEL_45:
              SendOpenStatusNotify((struct tagIMEUI *)a1, (HWND)a1[2], 1);
            }
          }
        }
      }
    }
LABEL_7:
    if ( *a1 )
    {
      if ( **a1 )
        NtUserCheckImeShowStatusInThread();
    }
    return v9;
  }
  return 0;
}

```

## disassembly

```asm
0x180015be4  push    rbx
0x180015be6  push    rbp
0x180015be7  push    rsi
0x180015be8  push    rdi
0x180015be9  push    r12
0x180015beb  push    r13
0x180015bed  push    r14
0x180015bef  push    r15
0x180015bf1  sub     rsp, 68h
0x180015bf5  mov     rax, cs:__security_cookie
0x180015bfc  xor     rax, rsp
0x180015bff  mov     [rsp+0A8h+var_58], rax
0x180015c04  and     dword ptr [rcx+2Ch], 0FFFFFFFDh
0x180015c08  mov     rbx, rcx
0x180015c0b  mov     eax, r8d
0x180015c0e  mov     r12, r9
0x180015c11  neg     eax
0x180015c13  mov     r15, r8
0x180015c16  mov     r13d, edx
0x180015c19  mov     r14, [rbx+10h]
0x180015c1d  sbb     ecx, ecx
0x180015c1f  and     ecx, 2
0x180015c22  or      [rbx+2Ch], ecx
0x180015c25  test    r8, r8
0x180015c28  jnz     loc_180015CCE
0x180015c2e  mov     r9, r12; __int64
0x180015c31  mov     [rsp+0A8h+var_88], 0; int
0x180015c39  mov     r8, r15; unsigned __int64
0x180015c3c  mov     edx, r13d; unsigned int
0x180015c3f  mov     rcx, rbx; struct tagIMEUI *
0x180015c42  call    ?SendMessageToUI@@YA_JPEAUtagIMEUI@@I_K_JH@Z; SendMessageToUI(tagIMEUI *,uint,unsigned __int64,__int64,int)
0x180015c47  cmp     qword ptr [rbx], 0
0x180015c4b  mov     rsi, rax
0x180015c4e  jz      loc_180015EBA
0x180015c54  test    byte ptr [rbx+2Ch], 20h
0x180015c58  jz      short loc_180015CAD
0x180015c5a  call    cs:__imp_NtUserGetIMEShowStatus
0x180015c60  test    eax, eax
0x180015c62  jz      short loc_180015CAD
0x180015c64  mov     rcx, [rbx]
0x180015c67  mov     edx, 4
0x180015c6c  mov     rcx, [rcx]
0x180015c6f  call    cs:__imp_NtUserQueryWindow
0x180015c75  mov     rcx, rax; HWND
0x180015c78  call    ?ValidateHwndNoRip@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwndNoRip(HWND__ *)
0x180015c7d  mov     ebp, 1
0x180015c82  mov     rdi, rax
0x180015c85  cmp     r15d, ebp
0x180015c88  jnz     loc_180015DB7
0x180015c8e  test    rax, rax
0x180015c91  jnz     loc_180015E1D
0x180015c97  mov     rcx, [rbx]
0x180015c9a  test    rcx, rcx
0x180015c9d  jz      short loc_180015CAD
0x180015c9f  mov     rcx, [rcx]
0x180015ca2  test    rcx, rcx
0x180015ca5  jz      short loc_180015CAD
0x180015ca7  call    cs:__imp_NtUserCheckImeShowStatusInThread
0x180015cad  mov     rax, rsi
0x180015cb0  mov     rcx, [rsp+0A8h+var_58]
0x180015cb5  xor     rcx, rsp; StackCookie
0x180015cb8  call    __security_check_cookie
0x180015cbd  add     rsp, 68h
0x180015cc1  pop     r15
0x180015cc3  pop     r14
0x180015cc5  pop     r13
0x180015cc7  pop     r12
0x180015cc9  pop     rdi
0x180015cca  pop     rsi
0x180015ccb  pop     rbp
0x180015ccc  pop     rbx
0x180015ccd  retn
0x180015cce  cmp     qword ptr [rbx+20h], 0
0x180015cd3  jnz     short loc_180015CE5
0x180015cd5  mov     rdx, [rbx+18h]; HKL
0x180015cd9  mov     rcx, rbx; struct tagIMEUI *
0x180015cdc  call    ?CreateIMEUI@@YAPEAUHWND__@@PEAUtagIMEUI@@PEAUHKL__@@@Z; CreateIMEUI(tagIMEUI *,HKL__ *)
0x180015ce1  mov     [rbx+20h], rax
0x180015ce5  mov     rax, [rbx]
0x180015ce8  test    rax, rax
0x180015ceb  jz      loc_180015F53
0x180015cf1  mov     rcx, [rax]
0x180015cf4  mov     edx, 4
0x180015cf9  call    cs:__imp_NtUserQueryWindow
0x180015cff  mov     rbp, rax
0x180015d02  mov     rcx, rax
0x180015d05  mov     rax, cs:off_1800C85D0
0x180015d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d11  mov     rdi, rax
0x180015d14  test    rax, rax
0x180015d17  jnz     loc_180015E91
0x180015d1d  mov     rdx, rdi; HIMC
0x180015d20  mov     rcx, rbx; struct tagIMEUI *
0x180015d23  call    ?ImeSetImc@@YAXPEAUtagIMEUI@@PEAUHIMC__@@@Z; ImeSetImc(tagIMEUI *,HIMC__ *)
0x180015d28  mov     rcx, [rbx+20h]; hWnd
0x180015d2c  test    rcx, rcx
0x180015d2f  jz      short loc_180015D3B
0x180015d31  mov     r8, rdi; dwNewLong
0x180015d34  xor     edx, edx; nIndex
0x180015d36  call    SetWindowLongPtrW
0x180015d3b  test    rdi, rdi
0x180015d3e  jz      loc_180015EE3
0x180015d44  mov     rax, cs:off_1800C8628
0x180015d4b  mov     rcx, rdi
0x180015d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d53  mov     rsi, rax
0x180015d56  test    rax, rax
0x180015d59  jz      loc_180015EBA
0x180015d5f  cmp     rbp, [rax]
0x180015d62  jnz     loc_180015F3A
0x180015d68  test    dword ptr [rax+16Ch], 40000h
0x180015d72  jnz     loc_180015F03
0x180015d78  mov     rax, cs:off_1800C8630
0x180015d7f  mov     rcx, rdi
0x180015d82  mov     [rsi+184h], r12d
0x180015d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d8e  mov     rcx, [rbx]
0x180015d91  test    rcx, rcx
0x180015d94  jz      loc_180015F4E
0x180015d9a  mov     rcx, [rcx]
0x180015d9d  mov     rdx, rbp
0x180015da0  call    cs:__imp_NtUserSetImeOwnerWindow
0x180015da6  test    eax, eax
0x180015da8  jz      loc_180015C2E
0x180015dae  mov     [rbx+10h], rbp
0x180015db2  jmp     loc_180015C2E
0x180015db7  mov     rax, [rbx]
0x180015dba  test    rax, rax
0x180015dbd  jz      loc_180015F5A
0x180015dc3  mov     rcx, [rax]
0x180015dc6  mov     edx, 3
0x180015dcb  call    cs:__imp_NtUserQueryWindow
0x180015dd1  mov     r8, rax
0x180015dd4  test    rdi, rdi
0x180015dd7  jz      short loc_180015DFA
0x180015dd9  mov     rcx, [rbx]
0x180015ddc  call    _GETPTI
0x180015de1  mov     rcx, rdi
0x180015de4  mov     rdx, rax
0x180015de7  call    _GETPTI
0x180015dec  cmp     rdx, rax
0x180015def  jnz     short loc_180015DFA
0x180015df1  test    r8, r8
0x180015df4  jnz     loc_180015CAD
0x180015dfa  mov     rcx, r14; hWnd
0x180015dfd  call    IsWindow
0x180015e02  mov     rcx, rbx; struct tagIMEUI *
0x180015e05  test    eax, eax
0x180015e07  jz      loc_180015F61
0x180015e0d  xor     r8d, r8d; int
0x180015e10  mov     rdx, r14; hWnd
0x180015e13  call    ?SendOpenStatusNotify@@YAXPEAUtagIMEUI@@PEAUHWND__@@H@Z; SendOpenStatusNotify(tagIMEUI *,HWND__ *,int)
0x180015e18  jmp     loc_180015CAD
0x180015e1d  mov     rcx, [rbx]
0x180015e20  call    _GETPTI
0x180015e25  mov     rcx, rdi
0x180015e28  mov     rdx, rax
0x180015e2b  call    _GETPTI
0x180015e30  cmp     rdx, rax
0x180015e33  jnz     loc_180015C97
0x180015e39  mov     rcx, [rbx+10h]; HWND
0x180015e3d  test    [rbx+2Ch], bpl
0x180015e41  jz      short loc_180015EC1
0x180015e43  call    ?ValidateHwndNoRip@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwndNoRip(HWND__ *)
0x180015e48  mov     rdi, rax
0x180015e4b  test    rax, rax
0x180015e4e  jz      loc_180015C97
0x180015e54  mov     rcx, r14; HWND
0x180015e57  call    ?ValidateHwndNoRip@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwndNoRip(HWND__ *)
0x180015e5c  test    rax, rax
0x180015e5f  jz      loc_180015C97
0x180015e65  mov     rcx, rax
0x180015e68  call    GetNonChildAncestor
0x180015e6d  mov     rcx, rdi
0x180015e70  mov     r8, rax
0x180015e73  call    GetNonChildAncestor
0x180015e78  cmp     rax, r8
0x180015e7b  jz      loc_180015C97
0x180015e81  xor     r8d, r8d; int
0x180015e84  mov     rdx, r14; hWnd
0x180015e87  mov     rcx, rbx; struct tagIMEUI *
0x180015e8a  call    ?SendOpenStatusNotify@@YAXPEAUtagIMEUI@@PEAUHWND__@@H@Z; SendOpenStatusNotify(tagIMEUI *,HWND__ *,int)
0x180015e8f  jmp     short loc_180015ECF
0x180015e91  mov     rax, [rbx]
0x180015e94  test    rax, rax
0x180015e97  jz      loc_180015F82
0x180015e9d  mov     rcx, [rax]; HWND
0x180015ea0  mov     rdx, rdi; HIMC
0x180015ea3  call    ?ImeIsUsableContext@@YAHPEAUHWND__@@PEAUHIMC__@@@Z; ImeIsUsableContext(HWND__ *,HIMC__ *)
0x180015ea8  test    eax, eax
0x180015eaa  jnz     loc_180015D1D
0x180015eb0  xor     edx, edx; HIMC
0x180015eb2  mov     rcx, rbx; struct tagIMEUI *
0x180015eb5  call    ?ImeSetImc@@YAXPEAUtagIMEUI@@PEAUHIMC__@@@Z; ImeSetImc(tagIMEUI *,HIMC__ *)
0x180015eba  xor     eax, eax
0x180015ebc  jmp     loc_180015CB0
0x180015ec1  call    ?ValidateHwndNoRip@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwndNoRip(HWND__ *)
0x180015ec6  test    rax, rax
0x180015ec9  jz      loc_180015C97
0x180015ecf  mov     rdx, [rbx+10h]; hWnd
0x180015ed3  mov     r8d, ebp; int
0x180015ed6  mov     rcx, rbx; struct tagIMEUI *
0x180015ed9  call    ?SendOpenStatusNotify@@YAXPEAUtagIMEUI@@PEAUHWND__@@H@Z; SendOpenStatusNotify(tagIMEUI *,HWND__ *,int)
0x180015ede  jmp     loc_180015C97
0x180015ee3  mov     rax, [rbx]
0x180015ee6  mov     [rbx+10h], rbp
0x180015eea  test    rax, rax
0x180015eed  jz      short loc_180015EFF
0x180015eef  mov     rcx, [rax]
0x180015ef2  xor     edx, edx
0x180015ef4  call    cs:__imp_NtUserSetImeOwnerWindow
0x180015efa  jmp     loc_180015C2E
0x180015eff  xor     ecx, ecx
0x180015f01  jmp     short loc_180015EF2
0x180015f03  cmp     r14, rbp
0x180015f06  jz      loc_180015D78
0x180015f0c  mov     rax, cs:off_1800C8618
0x180015f13  lea     rdx, [rsp+0A8h+var_78]
0x180015f18  xorps   xmm0, xmm0
0x180015f1b  mov     rcx, rdi
0x180015f1e  movups  xmmword ptr [rsp+0A8h+var_78], xmm0
0x180015f23  movups  xmmword ptr [rsp+0A8h+var_78+0Ch], xmm0
0x180015f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f2d  btr     dword ptr [rsi+16Ch], 12h
0x180015f35  jmp     loc_180015D78
0x180015f3a  mov     rax, cs:off_1800C8630
0x180015f41  mov     rcx, rdi
0x180015f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f49  jmp     loc_180015EBA
0x180015f4e  jmp     loc_180015D9D
0x180015f53  xor     ecx, ecx
0x180015f55  jmp     loc_180015CF4
0x180015f5a  xor     ecx, ecx
0x180015f5c  jmp     loc_180015DC6
0x180015f61  and     dword ptr [rbx+2Ch], 0FFFFFFFEh
0x180015f65  xor     r9d, r9d; __int64
0x180015f68  mov     r8, rbp; unsigned __int64
0x180015f6b  mov     [rsp+0A8h+var_88], 0; int
0x180015f73  mov     edx, 282h; unsigned int
0x180015f78  call    ?SendMessageToUI@@YA_JPEAUtagIMEUI@@I_K_JH@Z; SendMessageToUI(tagIMEUI *,uint,unsigned __int64,__int64,int)
0x180015f7d  jmp     loc_180015CAD
0x180015f82  xor     ecx, ecx
0x180015f84  jmp     loc_180015EA0
```
