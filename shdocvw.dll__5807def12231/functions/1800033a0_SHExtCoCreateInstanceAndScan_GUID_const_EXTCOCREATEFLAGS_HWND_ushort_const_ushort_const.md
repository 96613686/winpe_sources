# _SHExtCoCreateInstanceAndScan(_GUID const &,EXTCOCREATEFLAGS,HWND__ *,ushort const *,ushort const *)

- ea: `0x1800033a0`
- end: `0x180003486`
- name: `?_SHExtCoCreateInstanceAndScan@@YAJAEBU_GUID@@W4EXTCOCREATEFLAGS@@PEAUHWND__@@PEBG3@Z`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800030e0`

## callees

- `0x1800033a0`
- `0x180029010`

## import_xrefs

- `SHELL32!__imp_SHExtCoCreateInstance` at `0x1800033dd`
- `SHELL32!__imp_SHExtCoCreateInstance` at `0x1800033dd`

## pseudocode

```c
__int64 __fastcall _SHExtCoCreateInstanceAndScan(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 result; // rax
  unsigned int v8; // ebx
  __int64 v9; // [rsp+30h] [rbp-38h] BYREF
  int v10; // [rsp+38h] [rbp-30h] BYREF
  int v11; // [rsp+3Ch] [rbp-2Ch]
  __int64 v12; // [rsp+40h] [rbp-28h]
  __int64 v13; // [rsp+48h] [rbp-20h]
  const wchar_t *v14; // [rsp+50h] [rbp-18h]
  __int64 v15; // [rsp+58h] [rbp-10h]

  v9 = 0;
  result = SHExtCoCreateInstance(a1, 0, 1, 2, &IID_IOfficeAntiVirus, &v9);
  if ( (int)result < 0 )
  {
    if ( (_DWORD)result == -2147221164 || (_DWORD)result == -2147467262 || (_DWORD)result == -2147024770 )
      return 0;
  }
  else
  {
    v10 = 40;
    v14 = L"SHDOCVW";
    v13 = a4;
    v12 = a3;
    if ( a5 )
    {
      v11 = 9;
      v15 = a5;
    }
    else
    {
      v11 = 1;
      v15 = a4;
    }
    v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 24LL))(v9, &v10);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x1800033a0  mov     [rsp+arg_0], rbx
0x1800033a5  push    rdi
0x1800033a6  sub     rsp, 60h
0x1800033aa  lea     rax, [rsp+68h+var_38]
0x1800033af  mov     [rsp+68h+var_38], 0
0x1800033b8  mov     [rsp+68h+var_40], rax
0x1800033bd  mov     rbx, r9
0x1800033c0  lea     rax, IID_IOfficeAntiVirus
0x1800033c7  mov     rdi, r8
0x1800033ca  xor     edx, edx
0x1800033cc  mov     [rsp+68h+var_48], rax
0x1800033d1  mov     r9d, 2
0x1800033d7  mov     r8d, 1
0x1800033dd  call    cs:__imp_SHExtCoCreateInstance
0x1800033e3  test    eax, eax
0x1800033e5  js      short loc_180003464
0x1800033e7  lea     rax, aShdocvw; "SHDOCVW"
0x1800033ee  mov     [rsp+68h+var_30], 28h ; '('
0x1800033f6  mov     [rsp+68h+var_18], rax
0x1800033fb  mov     rax, [rsp+68h+arg_20]
0x180003403  mov     [rsp+68h+var_20], rbx
0x180003408  mov     [rsp+68h+var_28], rdi
0x18000340d  test    rax, rax
0x180003410  jnz     short loc_180003421
0x180003412  mov     [rsp+68h+var_2C], 1
0x18000341a  mov     [rsp+68h+var_10], rbx
0x18000341f  jmp     short loc_18000342E
0x180003421  mov     [rsp+68h+var_2C], 9
0x180003429  mov     [rsp+68h+var_10], rax
0x18000342e  mov     rcx, [rsp+68h+var_38]
0x180003433  lea     rdx, [rsp+68h+var_30]
0x180003438  mov     rax, [rcx]
0x18000343b  mov     rax, [rax+18h]
0x18000343f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003444  mov     rcx, [rsp+68h+var_38]
0x180003449  mov     ebx, eax
0x18000344b  mov     rdx, [rcx]
0x18000344e  mov     rax, [rdx+10h]
0x180003452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003457  mov     eax, ebx
0x180003459  mov     rbx, [rsp+68h+arg_0]
0x18000345e  add     rsp, 60h
0x180003462  pop     rdi
0x180003463  retn
0x180003464  cmp     eax, 80040154h
0x180003469  jz      short loc_180003479
0x18000346b  cmp     eax, 80004002h
0x180003470  jz      short loc_180003479
0x180003472  cmp     eax, 8007007Eh
0x180003477  jnz     short loc_18000347B
0x180003479  xor     eax, eax
0x18000347b  mov     rbx, [rsp+68h+arg_0]
0x180003480  add     rsp, 60h
0x180003484  pop     rdi
0x180003485  retn
```
