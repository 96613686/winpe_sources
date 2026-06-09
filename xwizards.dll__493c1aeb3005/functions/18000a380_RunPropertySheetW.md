# RunPropertySheetW

- ea: `0x18000a380`
- end: `0x18000a4aa`
- name: `RunPropertySheetW`
- size: `298`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a2d0`

## callees

- `0x1800085a8`
- `0x180008634`
- `0x18000a380`
- `0x18000a560`
- `0x18000ae04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a3bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a3bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a433`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a433`

## pseudocode

```c
__int64 __fastcall RunPropertySheetW(va_list hWnd, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  unsigned int v8; // esi
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdi
  unsigned int v11; // ebx
  PVOID *v12; // rcx

  LODWORD(v6) = 0;
  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
  }
  v7 = (unsigned int)(v6 + 21);
  v8 = v7;
  v9 = (unsigned __int16 *)CoTaskMemAlloc(2 * v7);
  v10 = v9;
  if ( v9 )
  {
    *v9 = 0;
    StringCchCopyW(v9, v8, L"/t");
    StringCchCatW(v10, v8, L"propertysheet97");
    if ( a3 )
    {
      StringCchCatW(v10, v8, L" ");
      StringCchCatW(v10, v8, a3);
    }
    v11 = RunWizardW(hWnd, a2, v10);
    CoTaskMemFree(v10);
    goto LABEL_11;
  }
  v11 = -2147024882;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, 2147942414LL);
LABEL_11:
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x10) != 0 )
    WPP_SF_d(v12[2], 67, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x18000a380  push    rbx
0x18000a382  push    rbp
0x18000a383  push    rsi
0x18000a384  push    rdi
0x18000a385  push    r12
0x18000a387  push    r13
0x18000a389  push    r14
0x18000a38b  push    r15
0x18000a38d  sub     rsp, 28h
0x18000a391  xor     r12d, r12d
0x18000a394  mov     ebp, r9d
0x18000a397  mov     rbx, r8
0x18000a39a  mov     r14, rdx
0x18000a39d  mov     r15, rcx
0x18000a3a0  mov     eax, r12d
0x18000a3a3  test    r8, r8
0x18000a3a6  jz      short loc_18000A3B6
0x18000a3a8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a3ac  inc     rax
0x18000a3af  cmp     [r8+rax*2], r12w
0x18000a3b4  jnz     short loc_18000A3AC
0x18000a3b6  add     eax, 15h
0x18000a3b9  mov     esi, eax
0x18000a3bb  lea     rcx, [rax+rax]; cb
0x18000a3bf  call    cs:__imp_CoTaskMemAlloc
0x18000a3c5  lea     r13, WPP_GLOBAL_Control
0x18000a3cc  mov     rdi, rax
0x18000a3cf  test    rax, rax
0x18000a3d2  jz      short loc_18000A43B
0x18000a3d4  lea     r8, aT; "/t"
0x18000a3db  mov     [rax], r12w
0x18000a3df  mov     edx, esi; unsigned __int64
0x18000a3e1  mov     rcx, rax; unsigned __int16 *
0x18000a3e4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a3e9  lea     r8, aPropertysheet9; "propertysheet97"
0x18000a3f0  mov     edx, esi; unsigned __int64
0x18000a3f2  mov     rcx, rdi; unsigned __int16 *
0x18000a3f5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a3fa  test    rbx, rbx
0x18000a3fd  jz      short loc_18000A41D
0x18000a3ff  lea     r8, asc_18003C374; " "
0x18000a406  mov     edx, esi; unsigned __int64
0x18000a408  mov     rcx, rdi; unsigned __int16 *
0x18000a40b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a410  mov     r8, rbx; unsigned __int16 *
0x18000a413  mov     edx, esi; unsigned __int64
0x18000a415  mov     rcx, rdi; unsigned __int16 *
0x18000a418  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a41d  mov     r9d, ebp
0x18000a420  mov     r8, rdi
0x18000a423  mov     rdx, r14
0x18000a426  mov     rcx, r15; hWnd
0x18000a429  call    RunWizardW
0x18000a42e  mov     rcx, rdi; pv
0x18000a431  mov     ebx, eax
0x18000a433  call    cs:__imp_CoTaskMemFree
0x18000a439  jmp     short loc_18000A46D
0x18000a43b  mov     ebx, 8007000Eh
0x18000a440  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a447  cmp     rcx, r13
0x18000a44a  jz      short loc_18000A497
0x18000a44c  test    byte ptr [rcx+1Ch], 4
0x18000a450  jz      short loc_18000A474
0x18000a452  mov     rcx, [rcx+10h]
0x18000a456  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x18000a45d  mov     edx, 42h ; 'B'
0x18000a462  mov     r9d, 8007000Eh
0x18000a468  call    WPP_SF_d
0x18000a46d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a474  cmp     rcx, r13
0x18000a477  jz      short loc_18000A497
0x18000a479  test    byte ptr [rcx+1Ch], 10h
0x18000a47d  jz      short loc_18000A497
0x18000a47f  mov     rcx, [rcx+10h]
0x18000a483  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x18000a48a  mov     edx, 43h ; 'C'
0x18000a48f  mov     r9d, ebx
0x18000a492  call    WPP_SF_d
0x18000a497  mov     eax, ebx
0x18000a499  add     rsp, 28h
0x18000a49d  pop     r15
0x18000a49f  pop     r14
0x18000a4a1  pop     r13
0x18000a4a3  pop     r12
0x18000a4a5  pop     rdi
0x18000a4a6  pop     rsi
0x18000a4a7  pop     rbp
0x18000a4a8  pop     rbx
0x18000a4a9  retn
```
