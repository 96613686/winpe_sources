# SetTextBold(HWND__ *,uint,HFONT__ * *)

- ea: `0x180125580`
- end: `0x18012574d`
- name: `?SetTextBold@@YAJPEAUHWND__@@IPEAPEAUHFONT__@@@Z`
- size: `461`
- prototype: `__int64 __fastcall(HWND hDlg, unsigned int, HFONT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18010da00`

## callees

- `0x180125580`
- `0x1801285fe`
- `0x180128660`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18012563a`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18012563a`
- `ext-ms-win-gdi-dc-l1-2-0!GetStockObject` at `0x180125671`
- `ext-ms-win-gdi-dc-l1-2-0!GetStockObject` at `0x180125671`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x1801256a6`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x1801256a6`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x180125652`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x1801256d2`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x180125652`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x1801256d2`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x1801255d5`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x1801255f7`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180125700`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x1801255d5`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x1801255f7`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180125700`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180125716`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180125716`

## pseudocode

```c
__int64 __fastcall SetTextBold(HWND hDlg, __int64 a2, HFONT *a3)
{
  unsigned int v5; // edi
  int v6; // r14d
  void *StockObject; // rbx
  LONG v8; // eax
  HFONT v9; // rax
  LOGFONTW pv; // [rsp+30h] [rbp-288h] BYREF
  int pvParam; // [rsp+90h] [rbp-228h] BYREF
  _BYTE v13[404]; // [rsp+94h] [rbp-224h] BYREF
  LOGFONTW lf; // [rsp+228h] [rbp-90h] BYREF

  if ( !a3 )
    return 0;
  if ( *a3 )
  {
    SendDlgItemMessageW(hDlg, 4011, 0x30u, (WPARAM)*a3, 0);
    return 0;
  }
  v6 = 0;
  v5 = -2147467259;
  StockObject = (void *)SendDlgItemMessageW(hDlg, 4011, 0x31u, 0, 0);
  if ( StockObject
    || (memset_0(v13, 0, 0x1F4u), pvParam = 504, SystemParametersInfoW(0x29u, 0x1F8u, &pvParam, 0))
    && (StockObject = CreateFontIndirectW(&lf), v6 = 1, StockObject)
    || (StockObject = GetStockObject(13)) != 0 )
  {
    memset_0(&pv, 0, sizeof(pv));
    if ( GetObjectW(StockObject, 92, &pv) )
    {
      v8 = pv.lfWeight + 300;
      if ( (unsigned int)(pv.lfWeight + 300) > 0x3E8 )
        v8 = 1000;
      pv.lfWeight = v8;
      v9 = CreateFontIndirectW(&pv);
      *a3 = v9;
      if ( v9 )
      {
        SendDlgItemMessageW(hDlg, 4011, 0x30u, (WPARAM)v9, 0);
        v5 = 0;
      }
    }
  }
  if ( v6 )
    DeleteObject(StockObject);
  return v5;
}

```

## disassembly

```asm
0x180125580  mov     [rsp+arg_8], rbx
0x180125585  mov     [rsp+arg_18], rbp
0x18012558a  push    rsi
0x18012558b  push    rdi
0x18012558c  push    r14
0x18012558e  sub     rsp, 2A0h
0x180125595  mov     rax, cs:__security_cookie
0x18012559c  xor     rax, rsp
0x18012559f  mov     [rsp+2B8h+var_28], rax
0x1801255a7  mov     rsi, r8
0x1801255aa  mov     rbp, rcx
0x1801255ad  test    r8, r8
0x1801255b0  jnz     short loc_1801255B9
0x1801255b2  xor     edi, edi
0x1801255b4  jmp     loc_180125722
0x1801255b9  mov     r9, [r8]; wParam
0x1801255bc  mov     edx, 0FABh; nIDDlgItem
0x1801255c1  test    r9, r9
0x1801255c4  jz      short loc_1801255E3
0x1801255c6  mov     r8d, 30h ; '0'; Msg
0x1801255cc  mov     [rsp+2B8h+lParam], 0; lParam
0x1801255d5  call    cs:__imp_SendDlgItemMessageW
0x1801255dc  nop     dword ptr [rax+rax+00h]
0x1801255e1  jmp     short loc_1801255B2
0x1801255e3  xor     r14d, r14d
0x1801255e6  xor     r9d, r9d; wParam
0x1801255e9  mov     edi, 80004005h
0x1801255ee  mov     [rsp+2B8h+lParam], r14; lParam
0x1801255f3  lea     r8d, [r14+31h]; Msg
0x1801255f7  call    cs:__imp_SendDlgItemMessageW
0x1801255fe  nop     dword ptr [rax+rax+00h]
0x180125603  mov     rbx, rax
0x180125606  test    rax, rax
0x180125609  jnz     short loc_180125689
0x18012560b  xor     edx, edx; Val
0x18012560d  lea     rcx, [rsp+2B8h+var_224]; void *
0x180125615  mov     r8d, 1F4h; Size
0x18012561b  call    memset_0
0x180125620  mov     edx, 1F8h; uiParam
0x180125625  lea     r8, [rsp+2B8h+pvParam]; pvParam
0x18012562d  xor     r9d, r9d; fWinIni
0x180125630  mov     [rsp+2B8h+pvParam], edx
0x180125637  lea     ecx, [rbx+29h]; uiAction
0x18012563a  call    cs:__imp_SystemParametersInfoW
0x180125641  nop     dword ptr [rax+rax+00h]
0x180125646  test    eax, eax
0x180125648  jz      short loc_18012566C
0x18012564a  lea     rcx, [rsp+2B8h+lf]; lplf
0x180125652  call    cs:__imp_CreateFontIndirectW
0x180125659  nop     dword ptr [rax+rax+00h]
0x18012565e  mov     rbx, rax
0x180125661  mov     r14d, 1
0x180125667  test    rax, rax
0x18012566a  jnz     short loc_180125689
0x18012566c  mov     ecx, 0Dh; i
0x180125671  call    cs:__imp_GetStockObject
0x180125678  nop     dword ptr [rax+rax+00h]
0x18012567d  mov     rbx, rax
0x180125680  test    rax, rax
0x180125683  jz      loc_18012570E
0x180125689  xor     edx, edx; Val
0x18012568b  lea     rcx, [rsp+2B8h+pv]; void *
0x180125690  lea     r8d, [rdx+5Ch]; Size
0x180125694  call    memset_0
0x180125699  lea     r8, [rsp+2B8h+pv]; pv
0x18012569e  mov     edx, 5Ch ; '\'; c
0x1801256a3  mov     rcx, rbx; h
0x1801256a6  call    cs:__imp_GetObjectW
0x1801256ad  nop     dword ptr [rax+rax+00h]
0x1801256b2  test    eax, eax
0x1801256b4  jz      short loc_18012570E
0x1801256b6  mov     eax, [rsp+2B8h+var_278]
0x1801256ba  mov     ecx, 3E8h
0x1801256bf  add     eax, 12Ch
0x1801256c4  cmp     eax, ecx
0x1801256c6  cmova   eax, ecx
0x1801256c9  lea     rcx, [rsp+2B8h+pv]; lplf
0x1801256ce  mov     [rsp+2B8h+var_278], eax
0x1801256d2  call    cs:__imp_CreateFontIndirectW
0x1801256d9  nop     dword ptr [rax+rax+00h]
0x1801256de  mov     [rsi], rax
0x1801256e1  test    rax, rax
0x1801256e4  jz      short loc_18012570E
0x1801256e6  mov     r9, rax; wParam
0x1801256e9  mov     [rsp+2B8h+lParam], 0; lParam
0x1801256f2  mov     edx, 0FABh; nIDDlgItem
0x1801256f7  mov     r8d, 30h ; '0'; Msg
0x1801256fd  mov     rcx, rbp; hDlg
0x180125700  call    cs:__imp_SendDlgItemMessageW
0x180125707  nop     dword ptr [rax+rax+00h]
0x18012570c  xor     edi, edi
0x18012570e  test    r14d, r14d
0x180125711  jz      short loc_180125722
0x180125713  mov     rcx, rbx; ho
0x180125716  call    cs:__imp_DeleteObject
0x18012571d  nop     dword ptr [rax+rax+00h]
0x180125722  mov     eax, edi
0x180125724  mov     rcx, [rsp+2B8h+var_28]
0x18012572c  xor     rcx, rsp; StackCookie
0x18012572f  call    __security_check_cookie
0x180125734  lea     r11, [rsp+2B8h+var_18]
0x18012573c  mov     rbx, [r11+28h]
0x180125740  mov     rbp, [r11+38h]
0x180125744  mov     rsp, r11
0x180125747  pop     r14
0x180125749  pop     rdi
0x18012574a  pop     rsi
0x18012574b  retn
```
