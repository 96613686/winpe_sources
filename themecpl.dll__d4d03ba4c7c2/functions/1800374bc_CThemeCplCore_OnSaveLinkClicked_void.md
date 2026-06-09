# CThemeCplCore::_OnSaveLinkClicked(void)

- ea: `0x1800374bc`
- end: `0x1800375e3`
- name: `?_OnSaveLinkClicked@CThemeCplCore@@AEAAXXZ`
- size: `295`
- prototype: `void __fastcall(CThemeCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180036314`

## callees

- `0x180002280`
- `0x180035ae8`
- `0x1800374bc`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800375b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800375b1`
- `USER32!DialogBoxParamW` at `0x180037512`
- `USER32!DialogBoxParamW` at `0x180037512`

## pseudocode

```c
void __fastcall CThemeCplCore::_OnSaveLinkClicked(CThemeCplCore *this)
{
  HWND ParentWindow; // rdi
  __int64 v3; // rcx
  LPARAM *v4; // r8
  __int64 v5; // rdx
  _WORD *v6; // rax
  _WORD *v7; // rcx
  __int64 v8; // rcx
  LPVOID pv[2]; // [rsp+30h] [rbp-308h] BYREF
  _WORD dwInitParam[104]; // [rsp+40h] [rbp-2F8h] BYREF
  _WORD v11[264]; // [rsp+110h] [rbp-228h] BYREF

  dwInitParam[0] = 0;
  ParentWindow = CThemeCplCore::GetParentWindow(this);
  if ( DialogBoxParamW(g_hinst, (LPCWSTR)0x2BC, ParentWindow, CDlgSaveThemeName::s_DialogProc, (LPARAM)dwInitParam) == 1 )
  {
    v3 = 2147483646;
    v4 = (LPARAM *)dwInitParam;
    v5 = 260;
    v6 = v11;
    do
    {
      if ( !v3 )
        break;
      if ( !*(_WORD *)v4 )
        break;
      *v6 = *(_WORD *)v4;
      v4 = (LPARAM *)((char *)v4 + 2);
      ++v6;
      --v3;
      --v5;
    }
    while ( v5 );
    v7 = v6 - 1;
    if ( v5 )
      v7 = v6;
    *v7 = 0;
    if ( v5 && v11[0] )
    {
      v8 = *((_QWORD *)this + 17);
      pv[0] = 0;
      if ( (*(int (__fastcall **)(__int64, HWND, _WORD *, LPVOID *))(*(_QWORD *)v8 + 128LL))(v8, ParentWindow, v11, pv) >= 0 )
        CoTaskMemFree(pv[0]);
    }
  }
}

```

## disassembly

```asm
0x1800374bc  mov     [rsp+arg_8], rbx
0x1800374c1  mov     [rsp+arg_10], rsi
0x1800374c6  push    rdi
0x1800374c7  sub     rsp, 330h
0x1800374ce  mov     rax, cs:__security_cookie
0x1800374d5  xor     rax, rsp
0x1800374d8  mov     [rsp+338h+var_18], rax
0x1800374e0  xor     esi, esi
0x1800374e2  mov     rbx, rcx
0x1800374e5  mov     [rsp+338h+var_2F8], si
0x1800374ea  call    ?GetParentWindow@CThemeCplCore@@QEAAPEAUHWND__@@XZ; CThemeCplCore::GetParentWindow(void)
0x1800374ef  mov     rcx, cs:g_hinst; hInstance
0x1800374f6  lea     r9, ?s_DialogProc@CDlgSaveThemeName@@CA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1800374fd  mov     rdi, rax
0x180037500  mov     edx, 2BCh; lpTemplateName
0x180037505  lea     rax, [rsp+338h+var_2F8]
0x18003750a  mov     r8, rdi; hWndParent
0x18003750d  mov     [rsp+338h+dwInitParam], rax; dwInitParam
0x180037512  call    cs:__imp_DialogBoxParamW
0x180037519  nop     dword ptr [rax+rax+00h]
0x18003751e  cmp     rax, 1
0x180037522  jnz     loc_1800375BD
0x180037528  mov     ecx, 7FFFFFFEh
0x18003752d  lea     r8, [rsp+338h+var_2F8]
0x180037532  mov     edx, 104h
0x180037537  lea     rax, [rsp+338h+var_228]
0x18003753f  test    rcx, rcx
0x180037542  jz      short loc_180037563
0x180037544  movzx   r9d, word ptr [r8]
0x180037548  test    r9w, r9w
0x18003754c  jz      short loc_180037563
0x18003754e  mov     [rax], r9w
0x180037552  add     r8, 2
0x180037556  add     rax, 2
0x18003755a  dec     rcx
0x18003755d  sub     rdx, 1
0x180037561  jnz     short loc_18003753F
0x180037563  test    rdx, rdx
0x180037566  lea     rcx, [rax-2]
0x18003756a  cmovnz  rcx, rax
0x18003756e  mov     [rcx], si
0x180037571  jz      short loc_1800375BD
0x180037573  cmp     [rsp+338h+var_228], si
0x18003757b  jz      short loc_1800375BD
0x18003757d  mov     rcx, [rbx+88h]
0x180037584  lea     r9, [rsp+338h+pv]
0x180037589  mov     [rsp+338h+pv], rsi
0x18003758e  lea     r8, [rsp+338h+var_228]
0x180037596  mov     rdx, rdi
0x180037599  mov     rax, [rcx]
0x18003759c  mov     rax, [rax+80h]
0x1800375a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375a8  test    eax, eax
0x1800375aa  js      short loc_1800375BD
0x1800375ac  mov     rcx, [rsp+338h+pv]; pv
0x1800375b1  call    cs:__imp_CoTaskMemFree
0x1800375b8  nop     dword ptr [rax+rax+00h]
0x1800375bd  mov     rcx, [rsp+338h+var_18]
0x1800375c5  xor     rcx, rsp; StackCookie
0x1800375c8  call    __security_check_cookie
0x1800375cd  lea     r11, [rsp+338h+var_8]
0x1800375d5  mov     rbx, [r11+18h]
0x1800375d9  mov     rsi, [r11+20h]
0x1800375dd  mov     rsp, r11
0x1800375e0  pop     rdi
0x1800375e1  retn
```
