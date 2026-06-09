# CChangeData::CreateInstance(_FILE_NOTIFY_INFORMATION *,IChangeData * *)

- ea: `0x180090090`
- end: `0x1800902d5`
- name: `?CreateInstance@CChangeData@@SAJPEAU_FILE_NOTIFY_INFORMATION@@PEAPEAUIChangeData@@@Z`
- size: `581`
- prototype: `__int64 __fastcall(struct _FILE_NOTIFY_INFORMATION *, struct IChangeData **)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800905d0`

## callees

- `0x18000161c`
- `0x180006f7c`
- `0x180008f3c`
- `0x180008f74`
- `0x180009aec`
- `0x180079f40`
- `0x18007a208`
- `0x180090090`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `KERNEL32!GetLongPathNameW` at `0x1800901b9`
- `KERNEL32!GetLongPathNameW` at `0x180090200`
- `KERNEL32!GetLongPathNameW` at `0x1800901b9`
- `KERNEL32!GetLongPathNameW` at `0x180090200`
- `KERNEL32!GetLastError` at `0x180090228`
- `KERNEL32!GetLastError` at `0x180090228`

## pseudocode

```c
__int64 __fastcall CChangeData::CreateInstance(struct _FILE_NOTIFY_INFORMATION *a1, struct IChangeData **a2)
{
  int v4; // r8d
  char *v5; // rax
  char *v6; // rdi
  char *v7; // rax
  signed int v8; // ebx
  const WCHAR *v9; // rcx
  const unsigned __int16 *v10; // rsi
  DWORD LongPathNameW; // eax
  DWORD v12; // r14d
  const WCHAR *v13; // rcx
  DWORD v14; // ebx
  signed int LastError; // eax
  LPWSTR lpszLongPath; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+28h] [rbp-D8h] BYREF
  LPCWSTR lpszShortPath[3]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[24]; // [rsp+48h] [rbp-B8h] BYREF
  int v21; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v22[264]; // [rsp+70h] [rbp-90h] BYREF
  char v23[528]; // [rsp+280h] [rbp+180h] BYREF

  STRW::STRW((STRW *)&v18, v22, 0x104u);
  BUFFER::BUFFER((BUFFER *)v20, v23, 0x20Au);
  v21 = 0;
  lpszLongPath = 0;
  v5 = (char *)operator new((unsigned int)(v4 + 78));
  v6 = v5;
  if ( !v5 )
  {
    v8 = -2147024882;
    goto LABEL_22;
  }
  v7 = v5 + 8;
  *((_DWORD *)v7 + 2) = 1;
  *(_QWORD *)v7 = &CPrivateUnknown::CUnkInner::`vftable';
  *((_QWORD *)v6 + 3) = v7;
  *(_QWORD *)v6 = &CChangeData::`vftable'{for `CPrivateUnknown'};
  *((_QWORD *)v6 + 4) = &CChangeData::`vftable'{for `IChangeData'};
  STRW::STRW((STRW *)(v6 + 568), (unsigned __int16 *)v6 + 22, 0x104u);
  *((_DWORD *)v6 + 10) = 0;
  *((_DWORD *)v6 + 10) = a1->Action;
  v8 = STRW::Append((STRW *)&v18, a1->FileName, (unsigned __int64)a1->FileNameLength >> 1);
  if ( v8 < 0 )
    goto LABEL_12;
  v8 = RESERVE_STRW::ReserveCCH((RESERVE_STRW *)v20, 0x104u, &lpszLongPath);
  if ( v8 < 0 )
    goto LABEL_12;
  v9 = &Str;
  v10 = lpszLongPath;
  if ( v18 )
    v9 = lpszShortPath[0];
  LongPathNameW = GetLongPathNameW(v9, lpszLongPath, 0x104u);
  v12 = LongPathNameW;
  if ( LongPathNameW > 0x104 )
  {
    v8 = RESERVE_STRW::ReserveCCH((RESERVE_STRW *)v20, LongPathNameW, &lpszLongPath);
    if ( v8 < 0 )
      goto LABEL_12;
    v13 = &Str;
    v10 = lpszLongPath;
    if ( v18 )
      v13 = lpszShortPath[0];
    v14 = v12;
    v12 = GetLongPathNameW(v13, lpszLongPath, v12);
    if ( v12 > v14 )
    {
      v8 = -2147418113;
      goto LABEL_12;
    }
  }
  if ( !v12 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)(v8 + 2147024894) > 1 )
      goto LABEL_12;
    v10 = &Str;
    if ( v18 )
      v10 = lpszShortPath[0];
  }
  v8 = STRW::Append((STRW *)(v6 + 568), v10);
  if ( v8 >= 0 )
  {
    *a2 = (struct IChangeData *)((unsigned __int64)(v6 + 32) & -(__int64)(v6 != 0));
    v8 = 0;
    goto LABEL_22;
  }
LABEL_12:
  (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
LABEL_22:
  v21 = 0;
  BUFFER::ReleaseStorage((BUFFER *)v20);
  v18 = 0;
  BUFFER::ReleaseStorage((BUFFER *)lpszShortPath);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180090090  mov     [rsp-8+arg_10], rbx
0x180090095  push    rbp
0x180090096  push    rsi
0x180090097  push    rdi
0x180090098  push    r13
0x18009009a  push    r14
0x18009009c  lea     rbp, [rsp-3A0h]
0x1800900a4  sub     rsp, 4A0h
0x1800900ab  mov     rax, cs:__security_cookie
0x1800900b2  xor     rax, rsp
0x1800900b5  mov     [rbp+3C0h+var_30], rax
0x1800900bc  mov     rbx, rcx
0x1800900bf  mov     r14d, 104h
0x1800900c5  mov     r13, rdx
0x1800900c8  lea     rcx, [rsp+4C0h+var_498]; this
0x1800900cd  mov     r8d, r14d; unsigned int
0x1800900d0  lea     rdx, [rsp+4C0h+var_450]; unsigned __int16 *
0x1800900d5  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x1800900da  mov     r8d, 20Ah; unsigned __int64
0x1800900e0  lea     rcx, [rsp+4C0h+var_478]; this
0x1800900e5  lea     rdx, [rbp+3C0h+var_240]; void *
0x1800900ec  call    ??0BUFFER@@QEAA@PEAX_K@Z; BUFFER::BUFFER(void *,unsigned __int64)
0x1800900f1  lea     ecx, [r8+4Eh]; Size
0x1800900f5  mov     [rsp+4C0h+var_460], 0
0x1800900fd  mov     [rsp+4C0h+lpszLongPath], 0
0x180090106  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009010b  mov     rdi, rax
0x18009010e  test    rax, rax
0x180090111  jz      loc_180090284
0x180090117  add     rax, 8
0x18009011b  lea     rcx, ??_7CUnkInner@CPrivateUnknown@@6B@; const CPrivateUnknown::CUnkInner::`vftable'
0x180090122  lea     rdx, [rdi+2Ch]; unsigned __int16 *
0x180090126  mov     r8d, r14d; unsigned int
0x180090129  mov     dword ptr [rax+8], 1
0x180090130  mov     [rax], rcx
0x180090133  lea     rcx, [rdi+238h]; this
0x18009013a  mov     [rdi+18h], rax
0x18009013e  lea     rax, ??_7CChangeData@@6BCPrivateUnknown@@@; const CChangeData::`vftable'{for `CPrivateUnknown'}
0x180090145  mov     [rdi], rax
0x180090148  lea     rax, ??_7CChangeData@@6BIChangeData@@@; const CChangeData::`vftable'{for `IChangeData'}
0x18009014f  mov     [rdi+20h], rax
0x180090153  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180090158  mov     dword ptr [rdi+28h], 0
0x18009015f  lea     rdx, [rbx+0Ch]; unsigned __int16 *
0x180090163  mov     eax, [rbx+4]
0x180090166  lea     rcx, [rsp+4C0h+var_498]; this
0x18009016b  mov     [rdi+28h], eax
0x18009016e  mov     r8d, [rbx+8]
0x180090172  shr     r8, 1; unsigned __int64
0x180090175  call    ?Append@STRW@@QEAAJPEBG_K@Z; STRW::Append(ushort const *,unsigned __int64)
0x18009017a  mov     ebx, eax
0x18009017c  test    eax, eax
0x18009017e  js      loc_180090212
0x180090184  lea     r8, [rsp+4C0h+lpszLongPath]; unsigned __int16 **
0x180090189  mov     edx, r14d; unsigned int
0x18009018c  lea     rcx, [rsp+4C0h+var_478]; this
0x180090191  call    ?ReserveCCH@RESERVE_STRW@@QEAAJKPEAPEAG@Z; RESERVE_STRW::ReserveCCH(ulong,ushort * *)
0x180090196  mov     ebx, eax
0x180090198  test    eax, eax
0x18009019a  js      short loc_180090212
0x18009019c  cmp     [rsp+4C0h+var_498], 0
0x1800901a1  lea     rcx, Str
0x1800901a8  mov     rsi, [rsp+4C0h+lpszLongPath]
0x1800901ad  mov     r8d, r14d; cchBuffer
0x1800901b0  cmovnz  rcx, [rsp+4C0h+lpszShortPath]; lpszShortPath
0x1800901b6  mov     rdx, rsi; lpszLongPath
0x1800901b9  call    cs:__imp_GetLongPathNameW
0x1800901bf  mov     r14d, eax
0x1800901c2  cmp     eax, 104h
0x1800901c7  jbe     short loc_180090223
0x1800901c9  lea     r8, [rsp+4C0h+lpszLongPath]; unsigned __int16 **
0x1800901ce  mov     edx, eax; unsigned int
0x1800901d0  lea     rcx, [rsp+4C0h+var_478]; this
0x1800901d5  call    ?ReserveCCH@RESERVE_STRW@@QEAAJKPEAPEAG@Z; RESERVE_STRW::ReserveCCH(ulong,ushort * *)
0x1800901da  mov     ebx, eax
0x1800901dc  test    eax, eax
0x1800901de  js      short loc_180090212
0x1800901e0  cmp     [rsp+4C0h+var_498], 0
0x1800901e5  lea     rcx, Str
0x1800901ec  mov     rsi, [rsp+4C0h+lpszLongPath]
0x1800901f1  mov     r8d, r14d; cchBuffer
0x1800901f4  cmovnz  rcx, [rsp+4C0h+lpszShortPath]; lpszShortPath
0x1800901fa  mov     rdx, rsi; lpszLongPath
0x1800901fd  mov     ebx, r14d
0x180090200  call    cs:__imp_GetLongPathNameW
0x180090206  mov     r14d, eax
0x180090209  cmp     eax, ebx
0x18009020b  jbe     short loc_180090223
0x18009020d  mov     ebx, 8000FFFFh
0x180090212  mov     rax, [rdi]
0x180090215  mov     rcx, rdi
0x180090218  mov     rax, [rax+10h]
0x18009021c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090221  jmp     short loc_180090289
0x180090223  test    r14d, r14d
0x180090226  jnz     short loc_18009025A
0x180090228  call    cs:__imp_GetLastError
0x18009022e  mov     ebx, eax
0x180090230  test    eax, eax
0x180090232  jle     short loc_18009023D
0x180090234  movzx   ebx, ax
0x180090237  or      ebx, 80070000h
0x18009023d  lea     eax, [rbx+7FF8FFFEh]
0x180090243  cmp     eax, 1
0x180090246  ja      short loc_180090212
0x180090248  cmp     [rsp+4C0h+var_498], 0
0x18009024d  lea     rsi, Str
0x180090254  cmovnz  rsi, [rsp+4C0h+lpszShortPath]
0x18009025a  lea     rcx, [rdi+238h]; this
0x180090261  mov     rdx, rsi; unsigned __int16 *
0x180090264  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180090269  mov     ebx, eax
0x18009026b  test    eax, eax
0x18009026d  js      short loc_180090212
0x18009026f  lea     rcx, [rdi+20h]
0x180090273  neg     rdi
0x180090276  sbb     rax, rax
0x180090279  and     rax, rcx
0x18009027c  mov     [r13+0], rax
0x180090280  xor     ebx, ebx
0x180090282  jmp     short loc_180090289
0x180090284  mov     ebx, 8007000Eh
0x180090289  lea     rcx, [rsp+4C0h+var_478]; this
0x18009028e  mov     [rsp+4C0h+var_460], 0
0x180090296  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18009029b  lea     rcx, [rsp+4C0h+lpszShortPath]; this
0x1800902a0  mov     [rsp+4C0h+var_498], 0
0x1800902a8  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x1800902ad  mov     eax, ebx
0x1800902af  mov     rcx, [rbp+3C0h+var_30]
0x1800902b6  xor     rcx, rsp; StackCookie
0x1800902b9  call    __security_check_cookie
0x1800902be  mov     rbx, [rsp+4C0h+arg_10]
0x1800902c6  add     rsp, 4A0h
0x1800902cd  pop     r14
0x1800902cf  pop     r13
0x1800902d1  pop     rdi
0x1800902d2  pop     rsi
0x1800902d3  pop     rbp
0x1800902d4  retn
```
