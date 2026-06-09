# CTask::EnumWindowsProc(HWND__ *,__int64)

- ea: `0x180020260`
- end: `0x180020340`
- name: `?EnumWindowsProc@CTask@@CAHPEAUHWND__@@_J@Z`
- size: `224`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004370`
- `0x18000ae04`
- `0x180020260`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180020302`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180020302`
- `USER32!EnumChildWindows` at `0x180020325`
- `USER32!EnumChildWindows` at `0x180020325`
- `USER32!GetPropW` at `0x180020282`
- `USER32!GetPropW` at `0x180020282`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x180020299`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x180020299`

## string_xrefs

- `0x180020275`: `_CTask_WizardInstanceTitle_`

## pseudocode

```c
_BOOL8 __fastcall CTask::EnumWindowsProc(HWND a1, LPARAM a2)
{
  WCHAR *v2; // rdi
  ATOM PropW; // ax
  unsigned int LastErrorHRESULT; // eax

  v2 = (WCHAR *)(a2 + 448);
  *(_WORD *)(a2 + 448) = 0;
  PropW = (unsigned __int16)GetPropW(a1, L"_CTask_WizardInstanceTitle_");
  if ( PropW
    && !GlobalGetAtomNameW(PropW, v2, 260)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    LastErrorHRESULT = GetLastErrorHRESULT();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
      LastErrorHRESULT);
  }
  if ( *v2 && CompareStringW(0x400u, 0, v2, -1, *(PCNZWCH *)(a2 + 440), -1) == 2 )
  {
    *(_QWORD *)(a2 + 1040) = a1;
    return 0;
  }
  else
  {
    EnumChildWindows(a1, CTask::EnumWindowsProc, a2);
    return *(_QWORD *)(a2 + 1040) == 0;
  }
}

```

## disassembly

```asm
0x180020260  push    rbx
0x180020262  push    rbp
0x180020263  push    rsi
0x180020264  push    rdi
0x180020265  sub     rsp, 38h
0x180020269  lea     rdi, [rdx+1C0h]
0x180020270  mov     rbx, rdx
0x180020273  xor     ebp, ebp
0x180020275  lea     rdx, String; "_CTask_WizardInstanceTitle_"
0x18002027c  mov     [rdi], bp
0x18002027f  mov     rsi, rcx
0x180020282  call    cs:__imp_GetPropW
0x180020288  test    ax, ax
0x18002028b  jz      short loc_1800202DE
0x18002028d  mov     r8d, 104h; nSize
0x180020293  mov     rdx, rdi; lpBuffer
0x180020296  movzx   ecx, ax; nAtom
0x180020299  call    cs:__imp_GlobalGetAtomNameW
0x18002029f  test    eax, eax
0x1800202a1  jnz     short loc_1800202DE
0x1800202a3  mov     rax, cs:WPP_GLOBAL_Control
0x1800202aa  lea     rcx, WPP_GLOBAL_Control
0x1800202b1  cmp     rax, rcx
0x1800202b4  jz      short loc_1800202DE
0x1800202b6  test    byte ptr [rax+1Ch], 4
0x1800202ba  jz      short loc_1800202DE
0x1800202bc  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x1800202c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800202c8  lea     edx, [rbp+1Bh]
0x1800202cb  mov     r9d, eax
0x1800202ce  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x1800202d5  mov     rcx, [rcx+10h]
0x1800202d9  call    WPP_SF_d
0x1800202de  cmp     [rdi], bp
0x1800202e1  jz      short loc_180020318
0x1800202e3  mov     rax, [rbx+1B8h]
0x1800202ea  or      r9d, 0FFFFFFFFh; cchCount1
0x1800202ee  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x1800202f3  mov     r8, rdi; lpString1
0x1800202f6  xor     edx, edx; dwCmpFlags
0x1800202f8  mov     [rsp+58h+lpString2], rax; lpString2
0x1800202fd  mov     ecx, 400h; Locale
0x180020302  call    cs:__imp_CompareStringW
0x180020308  cmp     eax, 2
0x18002030b  jnz     short loc_180020318
0x18002030d  mov     [rbx+410h], rsi
0x180020314  xor     eax, eax
0x180020316  jmp     short loc_180020337
0x180020318  mov     r8, rbx; lParam
0x18002031b  lea     rdx, ?EnumWindowsProc@CTask@@CAHPEAUHWND__@@_J@Z; lpEnumFunc
0x180020322  mov     rcx, rsi; hWndParent
0x180020325  call    cs:__imp_EnumChildWindows
0x18002032b  cmp     [rbx+410h], rbp
0x180020332  mov     eax, ebp
0x180020334  setz    al
0x180020337  add     rsp, 38h
0x18002033b  pop     rdi
0x18002033c  pop     rsi
0x18002033d  pop     rbp
0x18002033e  pop     rbx
0x18002033f  retn
```
