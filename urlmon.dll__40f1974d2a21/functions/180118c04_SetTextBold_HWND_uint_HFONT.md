# SetTextBold(HWND__ *,uint,HFONT__ * *)

- ea: `0x180118c04`
- end: `0x180118d96`
- name: `?SetTextBold@@YAJPEAUHWND__@@IPEAPEAUHFONT__@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(HWND hDlg, unsigned int, HFONT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1801027d0`

## callees

- `0x180118c04`
- `0x18011ba3e`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180118cb2`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180118cb2`
- `ext-ms-win-gdi-dc-l1-2-0!GetStockObject` at `0x180118cdd`
- `ext-ms-win-gdi-dc-l1-2-0!GetStockObject` at `0x180118cdd`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x180118d08`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x180118d08`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x180118cc4`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x180118d2e`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x180118cc4`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x180118d2e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180118c59`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180118c75`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180118d56`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180118c59`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180118c75`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180118d56`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180118d66`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180118d66`

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
0x180118c04  mov     [rsp+arg_8], rbx
0x180118c09  mov     [rsp+arg_18], rbp
0x180118c0e  push    rsi
0x180118c0f  push    rdi
0x180118c10  push    r14
0x180118c12  sub     rsp, 2A0h
0x180118c19  mov     rax, cs:__security_cookie
0x180118c20  xor     rax, rsp
0x180118c23  mov     [rsp+2B8h+var_28], rax
0x180118c2b  mov     rsi, r8
0x180118c2e  mov     rbp, rcx
0x180118c31  test    r8, r8
0x180118c34  jnz     short loc_180118C3D
0x180118c36  xor     edi, edi
0x180118c38  jmp     loc_180118D6C
0x180118c3d  mov     r9, [r8]; wParam
0x180118c40  mov     edx, 0FABh; nIDDlgItem
0x180118c45  test    r9, r9
0x180118c48  jz      short loc_180118C61
0x180118c4a  mov     r8d, 30h ; '0'; Msg
0x180118c50  mov     [rsp+2B8h+lParam], 0; lParam
0x180118c59  call    cs:__imp_SendDlgItemMessageW
0x180118c5f  jmp     short loc_180118C36
0x180118c61  xor     r14d, r14d
0x180118c64  xor     r9d, r9d; wParam
0x180118c67  mov     edi, 80004005h
0x180118c6c  mov     [rsp+2B8h+lParam], r14; lParam
0x180118c71  lea     r8d, [r14+31h]; Msg
0x180118c75  call    cs:__imp_SendDlgItemMessageW
0x180118c7b  mov     rbx, rax
0x180118c7e  test    rax, rax
0x180118c81  jnz     short loc_180118CEB
0x180118c83  xor     edx, edx; Val
0x180118c85  lea     rcx, [rsp+2B8h+var_224]; void *
0x180118c8d  mov     r8d, 1F4h; Size
0x180118c93  call    memset_0
0x180118c98  mov     edx, 1F8h; uiParam
0x180118c9d  lea     r8, [rsp+2B8h+pvParam]; pvParam
0x180118ca5  xor     r9d, r9d; fWinIni
0x180118ca8  mov     [rsp+2B8h+pvParam], edx
0x180118caf  lea     ecx, [rbx+29h]; uiAction
0x180118cb2  call    cs:__imp_SystemParametersInfoW
0x180118cb8  test    eax, eax
0x180118cba  jz      short loc_180118CD8
0x180118cbc  lea     rcx, [rsp+2B8h+lf]; lplf
0x180118cc4  call    cs:__imp_CreateFontIndirectW
0x180118cca  mov     rbx, rax
0x180118ccd  mov     r14d, 1
0x180118cd3  test    rax, rax
0x180118cd6  jnz     short loc_180118CEB
0x180118cd8  mov     ecx, 0Dh; i
0x180118cdd  call    cs:__imp_GetStockObject
0x180118ce3  mov     rbx, rax
0x180118ce6  test    rax, rax
0x180118ce9  jz      short loc_180118D5E
0x180118ceb  xor     edx, edx; Val
0x180118ced  lea     rcx, [rsp+2B8h+pv]; void *
0x180118cf2  lea     r8d, [rdx+5Ch]; Size
0x180118cf6  call    memset_0
0x180118cfb  lea     r8, [rsp+2B8h+pv]; pv
0x180118d00  mov     edx, 5Ch ; '\'; c
0x180118d05  mov     rcx, rbx; h
0x180118d08  call    cs:__imp_GetObjectW
0x180118d0e  test    eax, eax
0x180118d10  jz      short loc_180118D5E
0x180118d12  mov     eax, [rsp+2B8h+var_278]
0x180118d16  mov     ecx, 3E8h
0x180118d1b  add     eax, 12Ch
0x180118d20  cmp     eax, ecx
0x180118d22  cmova   eax, ecx
0x180118d25  lea     rcx, [rsp+2B8h+pv]; lplf
0x180118d2a  mov     [rsp+2B8h+var_278], eax
0x180118d2e  call    cs:__imp_CreateFontIndirectW
0x180118d34  mov     [rsi], rax
0x180118d37  test    rax, rax
0x180118d3a  jz      short loc_180118D5E
0x180118d3c  mov     r9, rax; wParam
0x180118d3f  mov     [rsp+2B8h+lParam], 0; lParam
0x180118d48  mov     edx, 0FABh; nIDDlgItem
0x180118d4d  mov     r8d, 30h ; '0'; Msg
0x180118d53  mov     rcx, rbp; hDlg
0x180118d56  call    cs:__imp_SendDlgItemMessageW
0x180118d5c  xor     edi, edi
0x180118d5e  test    r14d, r14d
0x180118d61  jz      short loc_180118D6C
0x180118d63  mov     rcx, rbx; ho
0x180118d66  call    cs:__imp_DeleteObject
0x180118d6c  mov     eax, edi
0x180118d6e  mov     rcx, [rsp+2B8h+var_28]
0x180118d76  xor     rcx, rsp; StackCookie
0x180118d79  call    __security_check_cookie
0x180118d7e  lea     r11, [rsp+2B8h+var_18]
0x180118d86  mov     rbx, [r11+28h]
0x180118d8a  mov     rbp, [r11+38h]
0x180118d8e  mov     rsp, r11
0x180118d91  pop     r14
0x180118d93  pop     rdi
0x180118d94  pop     rsi
0x180118d95  retn
```
