# EnumDisks

- ea: `0x18004158c`
- end: `0x1800417a0`
- name: `EnumDisks`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800417a8`

## callees

- `0x18004158c`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800416b0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800416b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800416cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800416e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800416fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041712`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041729`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800416cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800416e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800416fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041712`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041729`

## pseudocode

```c
__int64 __fastcall EnumDisks(__int64 *a1, const WCHAR *a2, _QWORD *a3)
{
  int v6; // ebx
  int v7; // edi
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // r14
  WCHAR *v11; // rcx
  int v12; // eax
  int v14; // [rsp+30h] [rbp-79h] BYREF
  __int64 v15; // [rsp+38h] [rbp-71h] BYREF
  int v16; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v17[84]; // [rsp+44h] [rbp-65h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-11h]
  PCNZWCH lpString2; // [rsp+A0h] [rbp-9h]
  LPVOID v20; // [rsp+A8h] [rbp-1h]
  LPVOID v21; // [rsp+B0h] [rbp+7h]
  LPVOID v22; // [rsp+B8h] [rbp+Fh]

  v14 = 0;
  if ( !a1 || !a2 || !a3 )
    return 2147942487LL;
  v6 = 0;
  v7 = 0;
  while ( !v7 )
  {
    v8 = *a1;
    v15 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *, int *))(v8 + 24))(a1, 1, &v15, &v14);
    v6 = v9;
    if ( v9 == 1 )
    {
      v7 = 1;
    }
    else if ( v9 < 0 )
    {
      return (unsigned int)v6;
    }
    if ( v15 )
    {
      v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v15)(v15, &IID_IVdsDisk, a3);
      if ( v6 >= 0 )
      {
        v10 = *a3;
        if ( *a3 )
        {
          v16 = 0;
          memset_0(v17, 0, 0x7Cu);
          v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 24LL))(v10, &v16);
          if ( v6 >= 0 )
          {
            v11 = (WCHAR *)lpString2;
            if ( lpString2 )
            {
              v12 = CompareStringW(0x409u, 1u, a2, -1, lpString2, -1);
              v11 = (WCHAR *)lpString2;
              if ( v12 == 2 )
                v7 = 1;
            }
            if ( pv )
            {
              CoTaskMemFree(pv);
              v11 = (WCHAR *)lpString2;
              pv = 0;
            }
            if ( v11 )
            {
              CoTaskMemFree(v11);
              lpString2 = 0;
            }
            if ( v20 )
            {
              CoTaskMemFree(v20);
              v20 = 0;
            }
            if ( v21 )
            {
              CoTaskMemFree(v21);
              v21 = 0;
            }
            if ( v22 )
            {
              CoTaskMemFree(v22);
              v22 = 0;
            }
          }
          if ( !v7 && *a3 )
          {
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
            *a3 = 0;
          }
        }
      }
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      if ( v6 < 0 )
        break;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004158c  push    rbp
0x18004158e  push    rbx
0x18004158f  push    rsi
0x180041590  push    rdi
0x180041591  push    r12
0x180041593  push    r14
0x180041595  push    r15
0x180041597  lea     rbp, [rsp-27h]
0x18004159c  sub     rsp, 0D0h
0x1800415a3  mov     rax, cs:__security_cookie
0x1800415aa  xor     rax, rsp
0x1800415ad  mov     [rbp+57h+var_40], rax
0x1800415b1  mov     [rbp+57h+var_D0], 0
0x1800415b8  mov     rsi, r8
0x1800415bb  mov     r12, rdx
0x1800415be  mov     r15, rcx
0x1800415c1  test    rcx, rcx
0x1800415c4  jz      loc_18004177D
0x1800415ca  test    rdx, rdx
0x1800415cd  jz      loc_18004177D
0x1800415d3  test    r8, r8
0x1800415d6  jz      loc_18004177D
0x1800415dc  xor     ebx, ebx
0x1800415de  xor     edi, edi
0x1800415e0  lea     r14d, [rbx+1]
0x1800415e4  test    edi, edi
0x1800415e6  jnz     loc_180041779
0x1800415ec  mov     rax, [r15]
0x1800415ef  lea     r9, [rbp+57h+var_D0]
0x1800415f3  lea     r8, [rbp+57h+var_C8]
0x1800415f7  mov     [rbp+57h+var_C8], 0
0x1800415ff  mov     edx, r14d
0x180041602  mov     rcx, r15
0x180041605  mov     rax, [rax+18h]
0x180041609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004160e  mov     ebx, eax
0x180041610  cmp     eax, r14d
0x180041613  jnz     short loc_18004161A
0x180041615  mov     edi, r14d
0x180041618  jmp     short loc_180041622
0x18004161a  test    eax, eax
0x18004161c  js      loc_180041779
0x180041622  mov     rcx, [rbp+57h+var_C8]
0x180041626  test    rcx, rcx
0x180041629  jz      short loc_1800415E4
0x18004162b  mov     rax, [rcx]
0x18004162e  lea     rdx, IID_IVdsDisk
0x180041635  mov     r8, rsi
0x180041638  mov     rax, [rax]
0x18004163b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041640  mov     ebx, eax
0x180041642  test    eax, eax
0x180041644  js      loc_18004175C
0x18004164a  mov     r14, [rsi]
0x18004164d  test    r14, r14
0x180041650  jz      loc_180041756
0x180041656  xor     edx, edx; Val
0x180041658  mov     [rbp+57h+var_C0], 0
0x18004165f  lea     rcx, [rbp+57h+var_BC]; void *
0x180041663  lea     r8d, [rdx+7Ch]; Size
0x180041667  call    memset_0
0x18004166c  mov     rax, [r14]
0x18004166f  lea     rdx, [rbp+57h+var_C0]
0x180041673  mov     rcx, r14
0x180041676  mov     rax, [rax+18h]
0x18004167a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004167f  mov     ebx, eax
0x180041681  test    eax, eax
0x180041683  js      loc_180041737
0x180041689  mov     rcx, [rbp+57h+var_60]
0x18004168d  test    rcx, rcx
0x180041690  jz      short loc_1800416C1
0x180041692  or      eax, 0FFFFFFFFh
0x180041695  mov     r8, r12; lpString1
0x180041698  mov     [rsp+100h+cchCount2], eax; cchCount2
0x18004169c  mov     r9d, eax; cchCount1
0x18004169f  mov     [rsp+100h+lpString2], rcx; lpString2
0x1800416a4  mov     ecx, 409h; Locale
0x1800416a9  lea     r14d, [rax+2]
0x1800416ad  mov     edx, r14d; dwCmpFlags
0x1800416b0  call    cs:__imp_CompareStringW
0x1800416b6  mov     rcx, [rbp+57h+var_60]
0x1800416ba  cmp     eax, 2
0x1800416bd  cmovz   edi, r14d
0x1800416c1  mov     rax, [rbp+57h+pv]
0x1800416c5  test    rax, rax
0x1800416c8  jz      short loc_1800416DF
0x1800416ca  mov     rcx, rax; pv
0x1800416cd  call    cs:__imp_CoTaskMemFree
0x1800416d3  mov     rcx, [rbp+57h+var_60]; pv
0x1800416d7  mov     [rbp+57h+pv], 0
0x1800416df  test    rcx, rcx
0x1800416e2  jz      short loc_1800416F2
0x1800416e4  call    cs:__imp_CoTaskMemFree
0x1800416ea  mov     [rbp+57h+var_60], 0
0x1800416f2  mov     rcx, [rbp+57h+var_58]; pv
0x1800416f6  test    rcx, rcx
0x1800416f9  jz      short loc_180041709
0x1800416fb  call    cs:__imp_CoTaskMemFree
0x180041701  mov     [rbp+57h+var_58], 0
0x180041709  mov     rcx, [rbp+57h+var_50]; pv
0x18004170d  test    rcx, rcx
0x180041710  jz      short loc_180041720
0x180041712  call    cs:__imp_CoTaskMemFree
0x180041718  mov     [rbp+57h+var_50], 0
0x180041720  mov     rcx, [rbp+57h+var_48]; pv
0x180041724  test    rcx, rcx
0x180041727  jz      short loc_180041737
0x180041729  call    cs:__imp_CoTaskMemFree
0x18004172f  mov     [rbp+57h+var_48], 0
0x180041737  test    edi, edi
0x180041739  jnz     short loc_180041756
0x18004173b  mov     rcx, [rsi]
0x18004173e  test    rcx, rcx
0x180041741  jz      short loc_180041756
0x180041743  mov     rax, [rcx]
0x180041746  mov     rax, [rax+10h]
0x18004174a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004174f  mov     qword ptr [rsi], 0
0x180041756  mov     r14d, 1
0x18004175c  mov     rcx, [rbp+57h+var_C8]
0x180041760  test    rcx, rcx
0x180041763  jz      short loc_180041771
0x180041765  mov     rax, [rcx]
0x180041768  mov     rax, [rax+10h]
0x18004176c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041771  test    ebx, ebx
0x180041773  jns     loc_1800415E4
0x180041779  mov     eax, ebx
0x18004177b  jmp     short loc_180041782
0x18004177d  mov     eax, 80070057h
0x180041782  mov     rcx, [rbp+57h+var_40]
0x180041786  xor     rcx, rsp; StackCookie
0x180041789  call    __security_check_cookie
0x18004178e  add     rsp, 0D0h
0x180041795  pop     r15
0x180041797  pop     r14
0x180041799  pop     r12
0x18004179b  pop     rdi
0x18004179c  pop     rsi
0x18004179d  pop     rbx
0x18004179e  pop     rbp
0x18004179f  retn
```
