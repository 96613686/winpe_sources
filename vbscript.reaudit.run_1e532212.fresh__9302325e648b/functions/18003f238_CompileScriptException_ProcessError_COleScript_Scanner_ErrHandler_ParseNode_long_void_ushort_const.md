# CompileScriptException::ProcessError(COleScript *,Scanner *,ErrHandler *,ParseNode *,long,void *,ushort const *)

- ea: `0x18003f238`
- end: `0x18003f43e`
- name: `?ProcessError@CompileScriptException@@QEAAJPEAVCOleScript@@PEAVScanner@@PEAVErrHandler@@PEAUParseNode@@JPEAXPEBG@Z`
- size: `518`
- prototype: `__int64 __fastcall(CompileScriptException *__hidden this, struct COleScript *, struct Scanner *, struct ErrHandler *, struct ParseNode *, UINT len, LPCSTR psz, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018e3c`

## callees

- `0x18001b104`
- `0x18003512c`
- `0x180035154`
- `0x18003f238`
- `0x180076746`
- `0x1800767a0`

## import_xrefs

- `msvcrt!wcscspn` at `0x18003f3f3`
- `msvcrt!wcscspn` at `0x18003f3f3`
- `msvcrt!_snwprintf_s` at `0x18003f2f7`
- `msvcrt!_snwprintf_s` at `0x18003f2f7`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18003f353`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18003f353`

## pseudocode

```c
__int64 __fastcall CompileScriptException::ProcessError(
        CompileScriptException *this,
        struct COleScript *a2,
        struct Scanner *a3,
        struct ErrHandler *a4,
        struct ParseNode *a5,
        int len,
        LPCSTR psz,
        const unsigned __int16 *a8)
{
  int v13; // ecx
  unsigned int v14; // r14d
  unsigned __int16 *ResourceString; // rax
  unsigned __int16 *v16; // rax
  BSTR v17; // rax
  unsigned __int64 v18; // rcx
  int v19; // eax
  int v20; // eax
  unsigned __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  const wchar_t *v25; // rbx
  unsigned int v26; // eax
  wchar_t Buffer[56]; // [rsp+30h] [rbp-B8h] BYREF

  if ( !this )
    return *((unsigned int *)a4 + 64);
  memset_0(this, 0, 0x68u);
  *((_DWORD *)this + 16) = *((_DWORD *)a4 + 64);
  v13 = *((_DWORD *)a4 + 64);
  v14 = *((_DWORD *)a2 + 46);
  if ( (v13 & 0x1FFF0000) != 0xA0000
    || (ResourceString = BstrGetResourceString((unsigned __int16)v13, v14), (*((_QWORD *)this + 3) = ResourceString) == 0) )
  {
    _snwprintf_s(Buffer, 0x32u, 0x31u, L"error %d", *((_DWORD *)this + 16));
    v16 = _SysAllocString(Buffer);
    *((_QWORD *)this + 3) = v16;
    if ( !v16 )
      *((_DWORD *)this + 16) = -2147024882;
  }
  *((_QWORD *)this + 2) = BstrGetResourceString(4096, v14);
  if ( a5 || !a3 )
    return 2254848004LL;
  if ( len > 0 )
  {
    v17 = 0;
    if ( (unsigned int)len < 0x7FFFFFFD )
      v17 = SysAllocStringByteLen(psz, len);
    *((_QWORD *)this + 12) = v17;
  }
  *(_DWORD *)this = (__int64)(*((_QWORD *)a3 + 4) - *((_QWORD *)a3 + 2)) >> 1;
  *((_DWORD *)this + 1) = (__int64)(*((_QWORD *)a3 + 5) - *((_QWORD *)a3 + 2)) >> 1;
  v18 = *((_QWORD *)a3 + 5);
  if ( *((_QWORD *)a3 + 3) != v18
    || (v19 = *((_DWORD *)a3 + 96), v19 <= 0)
    || (v20 = v19 - 1, *((_QWORD *)a3 + 4) >= v18) )
  {
    v20 = *((_DWORD *)a3 + 96);
  }
  *((_DWORD *)this + 20) = v20;
  v21 = *((_QWORD *)a3 + 5);
  v22 = *((_QWORD *)a3 + 3);
  if ( v22 == v21 && *((int *)a3 + 96) > 0 && *((_QWORD *)a3 + 4) < v21 )
    v22 = *((_QWORD *)a3 + 6);
  v23 = (v22 - *((_QWORD *)a3 + 2)) >> 1;
  *((_DWORD *)this + 21) = v23;
  if ( (int)v23 >= 0 )
  {
    v24 = -1;
    do
      ++v24;
    while ( a8[v24] );
    if ( (int)v23 <= (int)v24 )
    {
      if ( *(_DWORD *)this < (int)v23 )
        *(_DWORD *)this = v23;
      v25 = &a8[(int)v23];
      v26 = wcscspn(v25, L"\n\r");
      *((_QWORD *)this + 11) = _SysAllocStringLen(v25, v26);
      return 2254848004LL;
    }
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x18003f238  mov     [rsp+arg_10], rbx
0x18003f23d  push    rbp
0x18003f23e  push    rsi
0x18003f23f  push    rdi
0x18003f240  push    r12
0x18003f242  push    r13
0x18003f244  push    r14
0x18003f246  push    r15
0x18003f248  sub     rsp, 0B0h
0x18003f24f  mov     rax, cs:__security_cookie
0x18003f256  xor     rax, rsp
0x18003f259  mov     [rsp+0E8h+var_48], rax
0x18003f261  mov     ebp, [rsp+0E8h+len]
0x18003f268  xor     r13d, r13d
0x18003f26b  mov     r15, [rsp+0E8h+psz]
0x18003f273  mov     rsi, r9
0x18003f276  mov     r12, [rsp+0E8h+arg_38]
0x18003f27e  mov     rbx, r8
0x18003f281  mov     r14, rdx
0x18003f284  mov     rdi, rcx
0x18003f287  test    rcx, rcx
0x18003f28a  jnz     short loc_18003F298
0x18003f28c  mov     eax, [r9+100h]
0x18003f293  jmp     loc_18003F40C
0x18003f298  xor     edx, edx; Val
0x18003f29a  lea     r8d, [rdx+68h]; Size
0x18003f29e  call    memset_0
0x18003f2a3  mov     eax, [rsi+100h]
0x18003f2a9  mov     [rdi+40h], eax
0x18003f2ac  mov     ecx, [rsi+100h]
0x18003f2b2  mov     eax, ecx
0x18003f2b4  mov     r14d, [r14+0B8h]
0x18003f2bb  and     eax, 1FFF0000h
0x18003f2c0  cmp     eax, 0A0000h
0x18003f2c5  jnz     short loc_18003F2DB
0x18003f2c7  movzx   ecx, cx; int
0x18003f2ca  mov     edx, r14d; unsigned int
0x18003f2cd  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x18003f2d2  mov     [rdi+18h], rax
0x18003f2d6  test    rax, rax
0x18003f2d9  jnz     short loc_18003F317
0x18003f2db  mov     eax, [rdi+40h]
0x18003f2de  lea     r9, aErrorD; "error %d"
0x18003f2e5  mov     edx, 32h ; '2'; BufferCount
0x18003f2ea  mov     [rsp+0E8h+var_C8], eax
0x18003f2ee  lea     rcx, [rsp+0E8h+Buffer]; Buffer
0x18003f2f3  lea     r8d, [rdx-1]; MaxCount
0x18003f2f7  call    cs:__imp__snwprintf_s
0x18003f2fd  lea     rcx, [rsp+0E8h+Buffer]; unsigned __int16 *
0x18003f302  call    ?_SysAllocString@@YAPEAGPEBG@Z; _SysAllocString(ushort const *)
0x18003f307  mov     [rdi+18h], rax
0x18003f30b  test    rax, rax
0x18003f30e  jnz     short loc_18003F317
0x18003f310  mov     dword ptr [rdi+40h], 8007000Eh
0x18003f317  mov     edx, r14d; unsigned int
0x18003f31a  mov     ecx, 1000h; int
0x18003f31f  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x18003f324  mov     [rdi+10h], rax
0x18003f328  cmp     [rsp+0E8h+arg_20], r13
0x18003f330  jnz     loc_18003F407
0x18003f336  test    rbx, rbx
0x18003f339  jz      loc_18003F407
0x18003f33f  test    ebp, ebp
0x18003f341  jle     short loc_18003F35D
0x18003f343  mov     rax, r13
0x18003f346  cmp     ebp, 7FFFFFFDh
0x18003f34c  jnb     short loc_18003F359
0x18003f34e  mov     edx, ebp; len
0x18003f350  mov     rcx, r15; psz
0x18003f353  call    cs:__imp_SysAllocStringByteLen
0x18003f359  mov     [rdi+60h], rax
0x18003f35d  mov     rax, [rbx+20h]
0x18003f361  sub     rax, [rbx+10h]
0x18003f365  sar     rax, 1
0x18003f368  mov     [rdi], eax
0x18003f36a  mov     rax, [rbx+28h]
0x18003f36e  sub     rax, [rbx+10h]
0x18003f372  sar     rax, 1
0x18003f375  mov     [rdi+4], eax
0x18003f378  mov     rcx, [rbx+28h]
0x18003f37c  cmp     [rbx+18h], rcx
0x18003f380  jnz     short loc_18003F394
0x18003f382  mov     eax, [rbx+180h]
0x18003f388  test    eax, eax
0x18003f38a  jle     short loc_18003F394
0x18003f38c  cmp     [rbx+20h], rcx
0x18003f390  dec     eax
0x18003f392  jb      short loc_18003F39A
0x18003f394  mov     eax, [rbx+180h]
0x18003f39a  mov     [rdi+50h], eax
0x18003f39d  mov     rcx, [rbx+28h]
0x18003f3a1  mov     rax, [rbx+18h]
0x18003f3a5  cmp     rax, rcx
0x18003f3a8  jnz     short loc_18003F3BD
0x18003f3aa  cmp     [rbx+180h], r13d
0x18003f3b1  jle     short loc_18003F3BD
0x18003f3b3  cmp     [rbx+20h], rcx
0x18003f3b7  jnb     short loc_18003F3BD
0x18003f3b9  mov     rax, [rbx+30h]
0x18003f3bd  sub     rax, [rbx+10h]
0x18003f3c1  sar     rax, 1
0x18003f3c4  mov     [rdi+54h], eax
0x18003f3c7  test    eax, eax
0x18003f3c9  js      short loc_18003F437
0x18003f3cb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003f3cf  inc     rcx
0x18003f3d2  cmp     [r12+rcx*2], r13w
0x18003f3d7  jnz     short loc_18003F3CF
0x18003f3d9  cmp     eax, ecx
0x18003f3db  jg      short loc_18003F437
0x18003f3dd  cmp     [rdi], eax
0x18003f3df  jge     short loc_18003F3E3
0x18003f3e1  mov     [rdi], eax
0x18003f3e3  cdqe
0x18003f3e5  lea     rdx, Control; "\n\r"
0x18003f3ec  lea     rbx, [r12+rax*2]
0x18003f3f0  mov     rcx, rbx; String
0x18003f3f3  call    cs:__imp_wcscspn
0x18003f3f9  mov     edx, eax; unsigned int
0x18003f3fb  mov     rcx, rbx; unsigned __int16 *
0x18003f3fe  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18003f403  mov     [rdi+58h], rax
0x18003f407  mov     eax, 86664004h
0x18003f40c  mov     rcx, [rsp+0E8h+var_48]
0x18003f414  xor     rcx, rsp; StackCookie
0x18003f417  call    __security_check_cookie
0x18003f41c  mov     rbx, [rsp+0E8h+arg_10]
0x18003f424  add     rsp, 0B0h
0x18003f42b  pop     r15
0x18003f42d  pop     r14
0x18003f42f  pop     r13
0x18003f431  pop     r12
0x18003f433  pop     rdi
0x18003f434  pop     rsi
0x18003f435  pop     rbp
0x18003f436  retn
0x18003f437  mov     eax, 8000FFFFh
0x18003f43c  jmp     short loc_18003F40C
```
