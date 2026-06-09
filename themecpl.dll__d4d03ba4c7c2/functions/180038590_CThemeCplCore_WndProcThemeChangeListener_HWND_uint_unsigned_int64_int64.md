# CThemeCplCore::_WndProcThemeChangeListener(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180038590`
- end: `0x18003889b`
- name: `?_WndProcThemeChangeListener@CThemeCplCore@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `779`
- prototype: `LRESULT __fastcall(CThemeCplCore *this, HWND hWnd, UINT Msg, WPARAM wParam, LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180038a00`

## callees

- `0x1800213e8`
- `0x180035ae8`
- `0x180037448`
- `0x1800375ec`
- `0x180038590`
- `0x1800395e0`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800385f1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800385f1`
- `USER32!DefWindowProcW` at `0x180038871`
- `USER32!DefWindowProcW` at `0x180038871`
- `USER32!PostMessageW` at `0x18003880f`
- `USER32!PostMessageW` at `0x18003880f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LRESULT __fastcall CThemeCplCore::_WndProcThemeChangeListener(
        CThemeCplCore *this,
        HWND hWnd,
        UINT Msg,
        WPARAM wParam,
        LPCWCH lpString1)
{
  LPCWCH v5; // rbp
  CThemeCplCore *v9; // rbx
  __int64 v10; // r14
  bool v11; // dl
  __int64 v12; // rcx
  int v13; // edi
  int v14; // edx
  char v15; // cl
  _WORD *v16; // rcx
  __int64 v17; // rdx
  _WORD *v18; // rax
  __int64 v19; // r8
  _WORD *v20; // rcx
  HWND ParentWindow; // rax
  int v23; // [rsp+70h] [rbp+18h] BYREF

  v5 = lpString1;
  v9 = this;
  v10 = 0;
  switch ( Msg )
  {
    case 0x1Au:
      if ( !wParam
        && !*((_BYTE *)this + 156)
        && CompareStringOrdinal(lpString1, -1, (LPCWCH)L"WindowsThemeElement", -1, 0) == 2 )
      {
        this = v9;
LABEL_55:
        v11 = 1;
        goto LABEL_56;
      }
      return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)v5);
    case 0x402u:
      if ( wParam )
        return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)v5);
      if ( !*((_BYTE *)this + 156) )
      {
        if ( lpString1 == (LPCWCH)1 )
        {
          CThemeCplCore::_OnThemeDataReady((HCURSOR *)this);
          return v10;
        }
        if ( lpString1 == (LPCWCH)2 )
        {
          v12 = *((_QWORD *)this + 17);
          v23 = 0;
          if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 88LL))(v12, &v23) >= 0 )
          {
            v13 = v23;
            v14 = v23;
            *((_DWORD *)v9 + 36) = v23;
            if ( (int)CGallery::_ChangeFocus((CThemeCplCore *)((char *)v9 + 48), v14) >= 0 )
              *((_DWORD *)v9 + 18) = v13;
          }
          return v10;
        }
        if ( lpString1 == (LPCWCH)3 )
        {
          *((_BYTE *)this + 297) = 1;
          *(_WORD *)((char *)this + 301) = 0;
          return v10;
        }
        if ( lpString1 == (LPCWCH)4 )
        {
          *((_BYTE *)this + 297) = 0;
          return v10;
        }
        if ( lpString1 == (LPCWCH)5 )
        {
          v11 = 0;
LABEL_56:
          CThemeCplCore::_OnNotifyThemeChanged(this, v11);
          return v10;
        }
      }
      if ( lpString1 != (LPCWCH)6 )
      {
        if ( lpString1 != (LPCWCH)7 )
          return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)v5);
        if ( !*((_BYTE *)this + 302) )
          *((_BYTE *)this + 300) = 1;
        return v10;
      }
      if ( !*((_BYTE *)this + 301) )
        *((_BYTE *)this + 299) = 1;
      v15 = 1;
LABEL_37:
      if ( v15 )
        return v10;
      return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)v5);
    case 0x401u:
      v15 = 0;
      *((_BYTE *)v9 + 301) |= wParam == 1;
      *((_BYTE *)v9 + 302) |= wParam == 0;
      if ( !*((_BYTE *)v9 + 156) )
      {
        if ( wParam == 1 )
        {
          if ( *((_BYTE *)v9 + 299) )
            goto LABEL_36;
        }
        else if ( wParam || *((_BYTE *)v9 + 300) )
        {
          goto LABEL_36;
        }
        CThemeCplCore::_OnNotifyThemeChanged(v9, 1);
        v15 = 1;
      }
LABEL_36:
      *((_BYTE *)v9 + 299) &= wParam != 1;
      *((_BYTE *)v9 + 300) &= wParam != 0;
      goto LABEL_37;
  }
  if ( Msg != 74 )
  {
    if ( Msg == 689 )
    {
      if ( !*((_BYTE *)this + 297) && !*((_BYTE *)this + 156) )
        goto LABEL_55;
    }
    else if ( Msg == 1027 )
    {
      ParentWindow = CThemeCplCore::GetParentWindow(this);
      CThemeGalleryData::AddAndSelectTheme(
        (CThemeCplCore *)((char *)v9 + 120),
        (const unsigned __int16 *)v9 + 157,
        ParentWindow);
    }
    return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)v5);
  }
  if ( *(_QWORD *)lpString1 )
    return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)v5);
  v16 = (_WORD *)*((_QWORD *)lpString1 + 2);
  if ( !v16 )
    return DefWindowProcW(hWnd, Msg, wParam, (LPARAM)v5);
  v17 = 260;
  v18 = (_WORD *)((char *)v9 + 314);
  v19 = 2147483646;
  do
  {
    if ( !v19 )
      break;
    if ( !*v16 )
      break;
    *v18++ = *v16++;
    --v19;
    --v17;
  }
  while ( v17 );
  v20 = v18 - 1;
  if ( v17 )
    v20 = v18;
  *v20 = 0;
  if ( v17 && *((_WORD *)v9 + 157) )
    PostMessageW(*((HWND *)v9 + 34), 0x403u, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x180038590  mov     [rsp+arg_0], rbx
0x180038595  mov     [rsp+arg_8], rbp
0x18003859a  push    rsi
0x18003859b  push    rdi
0x18003859c  push    r12
0x18003859e  push    r14
0x1800385a0  push    r15
0x1800385a2  sub     rsp, 30h
0x1800385a6  mov     rbp, [rsp+58h+lpString1]
0x1800385ae  xor     r12d, r12d
0x1800385b1  mov     rdi, r9
0x1800385b4  mov     esi, r8d
0x1800385b7  mov     r15, rdx
0x1800385ba  mov     rbx, rcx
0x1800385bd  mov     r14d, r12d
0x1800385c0  cmp     r8d, 1Ah
0x1800385c4  jnz     short loc_18003860E
0x1800385c6  test    r9, r9
0x1800385c9  jnz     loc_180038866
0x1800385cf  cmp     [rcx+9Ch], r12b
0x1800385d6  jnz     loc_180038866
0x1800385dc  or      edx, 0FFFFFFFFh; cchCount1
0x1800385df  mov     [rsp+58h+bIgnoreCase], r12d; bIgnoreCase
0x1800385e4  mov     r9d, edx; cchCount2
0x1800385e7  lea     r8, lParam; "WindowsThemeElement"
0x1800385ee  mov     rcx, rbp; lpString1
0x1800385f1  call    cs:__imp_CompareStringOrdinal
0x1800385f8  nop     dword ptr [rax+rax+00h]
0x1800385fd  cmp     eax, 2
0x180038600  jnz     loc_180038866
0x180038606  mov     rcx, rbx
0x180038609  jmp     loc_18003883D
0x18003860e  cmp     esi, 402h
0x180038614  jnz     loc_18003870F
0x18003861a  test    rdi, rdi
0x18003861d  jnz     loc_180038866
0x180038623  cmp     [rcx+9Ch], r12b
0x18003862a  jnz     loc_1800386D0
0x180038630  mov     rax, rbp
0x180038633  sub     rax, 1
0x180038637  jz      loc_1800386C6
0x18003863d  sub     rax, 1
0x180038641  jz      short loc_18003867C
0x180038643  sub     rax, 1
0x180038647  jz      short loc_180038668
0x180038649  sub     rax, 1
0x18003864d  jz      short loc_18003865C
0x18003864f  cmp     rax, 1
0x180038653  jnz     short loc_1800386D0
0x180038655  xor     edx, edx
0x180038657  jmp     loc_18003883F
0x18003865c  mov     [rcx+129h], r12b
0x180038663  jmp     loc_180038880
0x180038668  mov     byte ptr [rcx+129h], 1
0x18003866f  mov     [rcx+12Dh], r12w
0x180038677  jmp     loc_180038880
0x18003867c  mov     rcx, [rcx+88h]
0x180038683  lea     rdx, [rsp+58h+arg_10]
0x180038688  mov     [rsp+58h+arg_10], r12d
0x18003868d  mov     rax, [rcx]
0x180038690  mov     rax, [rax+58h]
0x180038694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038699  test    eax, eax
0x18003869b  js      loc_180038880
0x1800386a1  mov     edi, [rsp+58h+arg_10]
0x1800386a5  lea     rcx, [rbx+30h]; this
0x1800386a9  mov     edx, edi; int
0x1800386ab  mov     [rbx+90h], edi
0x1800386b1  call    ?_ChangeFocus@CGallery@@AEAAJH@Z; CGallery::_ChangeFocus(int)
0x1800386b6  test    eax, eax
0x1800386b8  js      loc_180038880
0x1800386be  mov     [rbx+48h], edi
0x1800386c1  jmp     loc_180038880
0x1800386c6  call    ?_OnThemeDataReady@CThemeCplCore@@AEAAXXZ; CThemeCplCore::_OnThemeDataReady(void)
0x1800386cb  jmp     loc_180038880
0x1800386d0  mov     rax, rbp
0x1800386d3  sub     rax, 6
0x1800386d7  jz      short loc_1800386FB
0x1800386d9  cmp     rax, 1
0x1800386dd  jnz     loc_180038866
0x1800386e3  cmp     [rcx+12Eh], r12b
0x1800386ea  jnz     loc_180038880
0x1800386f0  mov     [rcx+12Ch], al
0x1800386f6  jmp     loc_180038880
0x1800386fb  cmp     [rcx+12Dh], r12b
0x180038702  jnz     short loc_18003870B
0x180038704  mov     byte ptr [rcx+12Bh], 1
0x18003870b  mov     cl, 1
0x18003870d  jmp     short loc_180038780
0x18003870f  cmp     esi, 401h
0x180038715  jnz     short loc_18003878D
0x180038717  cmp     rdi, 1
0x18003871b  mov     cl, r12b
0x18003871e  setz    al
0x180038721  or      [rbx+12Dh], al
0x180038727  test    rdi, rdi
0x18003872a  setz    al
0x18003872d  or      [rbx+12Eh], al
0x180038733  cmp     [rbx+9Ch], r12b
0x18003873a  jnz     short loc_180038767
0x18003873c  cmp     rdi, 1
0x180038740  jnz     short loc_18003874D
0x180038742  cmp     [rbx+12Bh], r12b
0x180038749  jz      short loc_18003875B
0x18003874b  jmp     short loc_180038767
0x18003874d  test    rdi, rdi
0x180038750  jnz     short loc_180038767
0x180038752  cmp     [rbx+12Ch], r12b
0x180038759  jnz     short loc_180038767
0x18003875b  mov     dl, 1; bool
0x18003875d  mov     rcx, rbx; this
0x180038760  call    ?_OnNotifyThemeChanged@CThemeCplCore@@AEAAX_N@Z; CThemeCplCore::_OnNotifyThemeChanged(bool)
0x180038765  mov     cl, 1
0x180038767  cmp     rdi, 1
0x18003876b  setnz   al
0x18003876e  and     [rbx+12Bh], al
0x180038774  test    rdi, rdi
0x180038777  setnz   al
0x18003877a  and     [rbx+12Ch], al
0x180038780  test    cl, cl
0x180038782  jz      loc_180038866
0x180038788  jmp     loc_180038880
0x18003878d  cmp     esi, 4Ah ; 'J'
0x180038790  jnz     loc_180038823
0x180038796  cmp     [rbp+0], r12
0x18003879a  jnz     loc_180038866
0x1800387a0  mov     rcx, [rbp+10h]
0x1800387a4  test    rcx, rcx
0x1800387a7  jz      loc_180038866
0x1800387ad  lea     r9, [rbx+13Ah]
0x1800387b4  mov     edx, 104h
0x1800387b9  mov     rax, r9
0x1800387bc  mov     r8d, 7FFFFFFEh
0x1800387c2  test    r8, r8
0x1800387c5  jz      short loc_1800387E6
0x1800387c7  movzx   r10d, word ptr [rcx]
0x1800387cb  test    r10w, r10w
0x1800387cf  jz      short loc_1800387E6
0x1800387d1  mov     [rax], r10w
0x1800387d5  add     rcx, 2
0x1800387d9  add     rax, 2
0x1800387dd  dec     r8
0x1800387e0  sub     rdx, 1
0x1800387e4  jnz     short loc_1800387C2
0x1800387e6  test    rdx, rdx
0x1800387e9  lea     rcx, [rax-2]
0x1800387ed  cmovnz  rcx, rax
0x1800387f1  mov     [rcx], r12w
0x1800387f5  jz      short loc_18003881B
0x1800387f7  cmp     [r9], r12w
0x1800387fb  jz      short loc_18003881B
0x1800387fd  mov     rcx, [rbx+110h]; hWnd
0x180038804  xor     r9d, r9d; lParam
0x180038807  xor     r8d, r8d; wParam
0x18003880a  mov     edx, 403h; Msg
0x18003880f  call    cs:__imp_PostMessageW
0x180038816  nop     dword ptr [rax+rax+00h]
0x18003881b  mov     r14d, 1
0x180038821  jmp     short loc_180038880
0x180038823  cmp     esi, 2B1h
0x180038829  jnz     short loc_180038846
0x18003882b  cmp     [rcx+129h], r12b
0x180038832  jnz     short loc_180038866
0x180038834  cmp     [rcx+9Ch], r12b
0x18003883b  jnz     short loc_180038866
0x18003883d  mov     dl, 1; bool
0x18003883f  call    ?_OnNotifyThemeChanged@CThemeCplCore@@AEAAX_N@Z; CThemeCplCore::_OnNotifyThemeChanged(bool)
0x180038844  jmp     short loc_180038880
0x180038846  cmp     esi, 403h
0x18003884c  jnz     short loc_180038866
0x18003884e  call    ?GetParentWindow@CThemeCplCore@@QEAAPEAUHWND__@@XZ; CThemeCplCore::GetParentWindow(void)
0x180038853  mov     r8, rax; HWND
0x180038856  lea     rdx, [rbx+13Ah]; unsigned __int16 *
0x18003885d  lea     rcx, [rbx+78h]; this
0x180038861  call    ?AddAndSelectTheme@CThemeGalleryData@@QEAAJPEBGPEAUHWND__@@@Z; CThemeGalleryData::AddAndSelectTheme(ushort const *,HWND__ *)
0x180038866  mov     r9, rbp; lParam
0x180038869  mov     r8, rdi; wParam
0x18003886c  mov     edx, esi; Msg
0x18003886e  mov     rcx, r15; hWnd
0x180038871  call    cs:__imp_DefWindowProcW
0x180038878  nop     dword ptr [rax+rax+00h]
0x18003887d  mov     r14, rax
0x180038880  mov     rbx, [rsp+58h+arg_0]
0x180038885  mov     rax, r14
0x180038888  mov     rbp, [rsp+58h+arg_8]
0x18003888d  add     rsp, 30h
0x180038891  pop     r15
0x180038893  pop     r14
0x180038895  pop     r12
0x180038897  pop     rdi
0x180038898  pop     rsi
0x180038899  retn
```
