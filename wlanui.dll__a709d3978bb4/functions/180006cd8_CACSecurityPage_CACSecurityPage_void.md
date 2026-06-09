# CACSecurityPage::~CACSecurityPage(void)

- ea: `0x180006cd8`
- end: `0x180006e29`
- name: `??1CACSecurityPage@@UEAA@XZ`
- size: `337`
- prototype: `void __fastcall(CACSecurityPage *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006f60`

## callees

- `0x180006860`
- `0x180006cd8`
- `0x180007570`
- `0x18001d010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006d7a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006d98`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006d7a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006d98`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006d5d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006d5d`
- `KERNEL32!GetProcessHeap` at `0x180006d08`
- `KERNEL32!GetProcessHeap` at `0x180006d1c`
- `KERNEL32!GetProcessHeap` at `0x180006d39`
- `KERNEL32!GetProcessHeap` at `0x180006d08`
- `KERNEL32!GetProcessHeap` at `0x180006d1c`
- `KERNEL32!GetProcessHeap` at `0x180006d39`
- `KERNEL32!HeapFree` at `0x180006d16`
- `KERNEL32!HeapFree` at `0x180006d2a`
- `KERNEL32!HeapFree` at `0x180006d47`
- `KERNEL32!HeapFree` at `0x180006d16`
- `KERNEL32!HeapFree` at `0x180006d2a`
- `KERNEL32!HeapFree` at `0x180006d47`
- `USER32!DestroyWindow` at `0x180006e08`
- `USER32!DestroyWindow` at `0x180006e08`
- `wlanapi!WpFreeProfile` at `0x180006df6`
- `wlanapi!WpFreeProfile` at `0x180006df6`

## pseudocode

```c
void __fastcall CACSecurityPage::~CACSecurityPage(CACSecurityPage *this)
{
  _QWORD *v1; // rbp
  _QWORD *v3; // rbp
  _QWORD *v4; // rdi
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v7; // rax
  void *v8; // rbx
  HANDLE v9; // rax
  void *v10; // rcx
  void *v11; // rcx
  struct _AUI_EAP_METHOD_INFO **v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  HWND v16; // rcx

  v1 = (_QWORD *)*((_QWORD *)this + 4);
  *(_QWORD *)this = &CACSecurityPage::`vftable';
  if ( v1 )
  {
    v3 = (_QWORD *)*v1;
    while ( v3 )
    {
      v4 = v3;
      v3 = (_QWORD *)v3[1];
      v5 = (void *)v4[2];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
      v7 = GetProcessHeap();
      HeapFree(v7, 0, v4);
    }
    v8 = (void *)*((_QWORD *)this + 4);
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
    *((_QWORD *)this + 4) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 79);
  if ( v10 )
  {
    operator delete[](v10);
    *((_QWORD *)this + 79) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 166);
  if ( v11 )
    operator delete(v11);
  v12 = (struct _AUI_EAP_METHOD_INFO **)*((_QWORD *)this + 167);
  if ( v12 )
  {
    EapControls::DestroyAuiEapInfo((EapControls *)v11, v12[6]);
    operator delete(v12);
  }
  v13 = *((_QWORD *)this + 169);
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 8LL))(v13, 1);
    *((_QWORD *)this + 169) = 0;
  }
  v14 = *((_QWORD *)this + 168);
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 8LL))(v14, 1);
    *((_QWORD *)this + 168) = 0;
  }
  v15 = *((_QWORD *)this + 6);
  if ( v15 )
    WpFreeProfile(v15);
  v16 = (HWND)*((_QWORD *)this + 76);
  if ( v16 )
    DestroyWindow(v16);
  *((_QWORD *)this + 76) = 0;
  CPropSheetPage::~CPropSheetPage(this);
}

```

## disassembly

```asm
0x180006cd8  push    rbx
0x180006cda  push    rbp
0x180006cdb  push    rsi
0x180006cdc  push    rdi
0x180006cdd  sub     rsp, 28h
0x180006ce1  mov     rbp, [rcx+20h]
0x180006ce5  lea     rax, ??_7CACSecurityPage@@6B@; const CACSecurityPage::`vftable'
0x180006cec  mov     [rcx], rax
0x180006cef  mov     rsi, rcx
0x180006cf2  test    rbp, rbp
0x180006cf5  jz      short loc_180006D51
0x180006cf7  mov     rbp, [rbp+0]
0x180006cfb  jmp     short loc_180006D30
0x180006cfd  mov     rdi, rbp
0x180006d00  mov     rbp, [rbp+8]
0x180006d04  mov     rbx, [rdi+10h]
0x180006d08  call    cs:__imp_GetProcessHeap
0x180006d0e  mov     r8, rbx; lpMem
0x180006d11  xor     edx, edx; dwFlags
0x180006d13  mov     rcx, rax; hHeap
0x180006d16  call    cs:__imp_HeapFree
0x180006d1c  call    cs:__imp_GetProcessHeap
0x180006d22  mov     r8, rdi; lpMem
0x180006d25  xor     edx, edx; dwFlags
0x180006d27  mov     rcx, rax; hHeap
0x180006d2a  call    cs:__imp_HeapFree
0x180006d30  test    rbp, rbp
0x180006d33  jnz     short loc_180006CFD
0x180006d35  mov     rbx, [rsi+20h]
0x180006d39  call    cs:__imp_GetProcessHeap
0x180006d3f  mov     r8, rbx; lpMem
0x180006d42  xor     edx, edx; dwFlags
0x180006d44  mov     rcx, rax; hHeap
0x180006d47  call    cs:__imp_HeapFree
0x180006d4d  mov     [rsi+20h], rbp
0x180006d51  mov     rcx, [rsi+278h]
0x180006d58  test    rcx, rcx
0x180006d5b  jz      short loc_180006D6E
0x180006d5d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180006d63  mov     qword ptr [rsi+278h], 0
0x180006d6e  mov     rcx, [rsi+530h]
0x180006d75  test    rcx, rcx
0x180006d78  jz      short loc_180006D80
0x180006d7a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006d80  mov     rbx, [rsi+538h]
0x180006d87  test    rbx, rbx
0x180006d8a  jz      short loc_180006D9E
0x180006d8c  mov     rdx, [rbx+30h]; struct _AUI_EAP_METHOD_INFO *
0x180006d90  call    ?DestroyAuiEapInfo@EapControls@@QEAAXPEAU_AUI_EAP_METHOD_INFO@@@Z; EapControls::DestroyAuiEapInfo(_AUI_EAP_METHOD_INFO *)
0x180006d95  mov     rcx, rbx
0x180006d98  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006d9e  mov     rcx, [rsi+548h]
0x180006da5  mov     ebx, 1
0x180006daa  test    rcx, rcx
0x180006dad  jz      short loc_180006DC8
0x180006daf  mov     rax, [rcx]
0x180006db2  mov     edx, ebx
0x180006db4  mov     rax, [rax+8]
0x180006db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dbd  mov     qword ptr [rsi+548h], 0
0x180006dc8  mov     rcx, [rsi+540h]
0x180006dcf  test    rcx, rcx
0x180006dd2  jz      short loc_180006DED
0x180006dd4  mov     rax, [rcx]
0x180006dd7  mov     edx, ebx
0x180006dd9  mov     rax, [rax+8]
0x180006ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006de2  mov     qword ptr [rsi+540h], 0
0x180006ded  mov     rcx, [rsi+30h]
0x180006df1  test    rcx, rcx
0x180006df4  jz      short loc_180006DFC
0x180006df6  call    cs:__imp_WpFreeProfile
0x180006dfc  mov     rcx, [rsi+260h]; hWnd
0x180006e03  test    rcx, rcx
0x180006e06  jz      short loc_180006E0E
0x180006e08  call    cs:__imp_DestroyWindow
0x180006e0e  mov     rcx, rsi; this
0x180006e11  mov     qword ptr [rsi+260h], 0
0x180006e1c  add     rsp, 28h
0x180006e20  pop     rdi
0x180006e21  pop     rsi
0x180006e22  pop     rbp
0x180006e23  pop     rbx
0x180006e24  jmp     ??1CPropSheetPage@@UEAA@XZ; CPropSheetPage::~CPropSheetPage(void)
```
