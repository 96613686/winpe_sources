# CHostObj::get_StdErr(ITextStream * *)

- ea: `0x14000fff0`
- end: `0x1400100fa`
- name: `?get_StdErr@CHostObj@@UEAAJPEAPEAUITextStream@@@Z`
- size: `266`
- prototype: `__int64 __fastcall(CHostObj *__hidden this, struct ITextStream **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000fff0`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetStdHandle` at `0x140010074`
- `KERNEL32!GetStdHandle` at `0x140010074`
- `KERNEL32!GetConsoleMode` at `0x14001008a`
- `KERNEL32!GetConsoleMode` at `0x14001008a`
- `ole32!CoCreateInstance` at `0x14001004d`
- `ole32!CoCreateInstance` at `0x14001004d`

## pseudocode

```c
__int64 __fastcall CHostObj::get_StdErr(CHostObj *this, struct ITextStream **a2)
{
  _QWORD *v5; // rbx
  HRESULT v6; // edi
  HANDLE StdHandle; // rax
  _BOOL8 v8; // r8
  DWORD Mode; // [rsp+58h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v5 = (_QWORD *)((char *)this + 120);
  *a2 = 0;
  if ( !*((_QWORD *)this + 15) )
  {
    ppv = 0;
    v6 = CoCreateInstance(&CLSID_FileSystemObject, 0, 1u, &IID_IFileSystem3, &ppv);
    if ( v6 < 0 )
      return (unsigned int)v6;
    v8 = 0;
    if ( Global::g_fWindowsNT )
    {
      if ( *(_BYTE *)(*((_QWORD *)this + 16) + 73LL)
        || (StdHandle = GetStdHandle(0xFFFFFFF4), Mode = 0, GetConsoleMode(StdHandle, &Mode)) )
      {
        v8 = 1;
      }
    }
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, _BOOL8, _QWORD *))(*(_QWORD *)ppv + 256LL))(ppv, 2, v8, v5);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( v6 < 0 )
      return (unsigned int)v6;
  }
  *a2 = (struct ITextStream *)*v5;
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  return 0;
}

```

## disassembly

```asm
0x14000fff0  mov     [rsp+arg_0], rbx
0x14000fff5  push    rbp
0x14000fff6  push    rsi
0x14000fff7  push    rdi
0x14000fff8  sub     rsp, 30h
0x14000fffc  mov     rsi, rdx
0x14000ffff  mov     rbp, rcx
0x140010002  test    rdx, rdx
0x140010005  jnz     short loc_140010011
0x140010007  mov     eax, 80004003h
0x14001000c  jmp     loc_1400100ED
0x140010011  lea     rbx, [rcx+78h]
0x140010015  mov     qword ptr [rdx], 0
0x14001001c  cmp     qword ptr [rbx], 0
0x140010020  jnz     loc_1400100D6
0x140010026  xor     edx, edx; pUnkOuter
0x140010028  mov     [rsp+48h+arg_10], 0
0x140010031  lea     rax, [rsp+48h+arg_10]
0x140010036  lea     r9, IID_IFileSystem3; riid
0x14001003d  mov     [rsp+48h+ppv], rax; ppv
0x140010042  lea     rcx, CLSID_FileSystemObject; rclsid
0x140010049  lea     r8d, [rdx+1]; dwClsContext
0x14001004d  call    cs:__imp_CoCreateInstance
0x140010053  mov     edi, eax
0x140010055  test    eax, eax
0x140010057  js      short loc_1400100D2
0x140010059  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x140010060  jz      short loc_14001009C
0x140010062  mov     rax, [rbp+80h]
0x140010069  cmp     byte ptr [rax+49h], 0
0x14001006d  jnz     short loc_140010094
0x14001006f  mov     ecx, 0FFFFFFF4h; nStdHandle
0x140010074  call    cs:__imp_GetStdHandle
0x14001007a  lea     rdx, [rsp+48h+Mode]; lpMode
0x14001007f  mov     [rsp+48h+Mode], 0
0x140010087  mov     rcx, rax; hConsoleHandle
0x14001008a  call    cs:__imp_GetConsoleMode
0x140010090  test    eax, eax
0x140010092  jz      short loc_14001009C
0x140010094  mov     r8d, 1
0x14001009a  jmp     short loc_14001009F
0x14001009c  xor     r8d, r8d
0x14001009f  mov     rcx, [rsp+48h+arg_10]
0x1400100a4  mov     r9, rbx
0x1400100a7  mov     edx, 2
0x1400100ac  mov     rax, [rcx]
0x1400100af  mov     rax, [rax+100h]
0x1400100b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400100bb  mov     rcx, [rsp+48h+arg_10]
0x1400100c0  mov     edi, eax
0x1400100c2  mov     rax, [rcx]
0x1400100c5  mov     rax, [rax+10h]
0x1400100c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400100ce  test    edi, edi
0x1400100d0  jns     short loc_1400100D6
0x1400100d2  mov     eax, edi
0x1400100d4  jmp     short loc_1400100ED
0x1400100d6  mov     rax, [rbx]
0x1400100d9  mov     [rsi], rax
0x1400100dc  mov     rcx, [rbx]
0x1400100df  mov     rax, [rcx]
0x1400100e2  mov     rax, [rax+8]
0x1400100e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400100eb  xor     eax, eax
0x1400100ed  mov     rbx, [rsp+48h+arg_0]
0x1400100f2  add     rsp, 30h
0x1400100f6  pop     rdi
0x1400100f7  pop     rsi
0x1400100f8  pop     rbp
0x1400100f9  retn
```
