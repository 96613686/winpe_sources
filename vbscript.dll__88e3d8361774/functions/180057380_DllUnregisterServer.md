# DllUnregisterServer

- ea: `0x180057380`
- end: `0x1800574b4`
- name: `DllUnregisterServer`
- size: `308`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x18003846c`
- `0x180038498`
- `0x180042098`
- `0x1800425d8`
- `0x180044378`
- `0x180057380`
- `0x180076746`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `KERNEL32!GetVersionExA` at `0x1800573c3`
- `KERNEL32!GetVersionExA` at `0x1800573c3`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  CClassFactory *ClassFactory; // rax
  CClassFactory *v2; // rbx
  HRESULT v3; // edi
  CClassFactory *AuthorClassFactory; // rax
  CClassFactory *v5; // rsi
  int v6; // ebx
  CClassFactory *EncodeClassFactory; // rax
  CClassFactory *v8; // rsi
  int v9; // ebx
  CClassFactory *RegExpClassFactory; // rax
  CClassFactory *v11; // rsi
  HRESULT v12; // ebx
  struct _OSVERSIONINFOA VersionInformation; // [rsp+20h] [rbp-B8h] BYREF

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x90u);
  VersionInformation.dwOSVersionInfoSize = 148;
  if ( GetVersionExA(&VersionInformation) && VersionInformation.dwMajorVersion >= 6 )
    return 0;
  ClassFactory = CreateClassFactory();
  v2 = ClassFactory;
  if ( !ClassFactory )
    return -2147418113;
  v3 = CClassFactory::UnregisterServer(ClassFactory);
  (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v2 + 16LL))(v2);
  AuthorClassFactory = CreateAuthorClassFactory();
  v5 = AuthorClassFactory;
  if ( !AuthorClassFactory )
    return -2147418113;
  v6 = CClassFactory::UnregisterServer(AuthorClassFactory);
  (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v6 < 0 )
    v3 = v6;
  EncodeClassFactory = CreateEncodeClassFactory();
  v8 = EncodeClassFactory;
  if ( !EncodeClassFactory )
    return -2147418113;
  v9 = CClassFactory::UnregisterServer(EncodeClassFactory);
  (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v9 < 0 )
    v3 = v9;
  RegExpClassFactory = CreateRegExpClassFactory();
  v11 = RegExpClassFactory;
  if ( !RegExpClassFactory )
    return -2147418113;
  v12 = CClassFactory::UnregisterServer(RegExpClassFactory);
  (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v12 < 0 )
    return v12;
  return v3;
}

```

## disassembly

```asm
0x180057380  mov     [rsp+arg_0], rbx
0x180057385  mov     [rsp+arg_8], rsi
0x18005738a  push    rdi
0x18005738b  sub     rsp, 0D0h
0x180057392  mov     rax, cs:__security_cookie
0x180057399  xor     rax, rsp
0x18005739c  mov     [rsp+0D8h+var_18], rax
0x1800573a4  xor     edx, edx; Val
0x1800573a6  lea     rcx, [rsp+0D8h+VersionInformation.dwMajorVersion]; void *
0x1800573ab  mov     r8d, 90h; Size
0x1800573b1  call    memset_0
0x1800573b6  lea     rcx, [rsp+0D8h+VersionInformation]; lpVersionInformation
0x1800573bb  mov     [rsp+0D8h+VersionInformation.dwOSVersionInfoSize], 94h
0x1800573c3  call    cs:__imp_GetVersionExA
0x1800573c9  test    eax, eax
0x1800573cb  jz      short loc_1800573DB
0x1800573cd  cmp     [rsp+0D8h+VersionInformation.dwMajorVersion], 6
0x1800573d2  jb      short loc_1800573DB
0x1800573d4  xor     eax, eax
0x1800573d6  jmp     loc_18005748F
0x1800573db  call    ?CreateClassFactory@@YAPEAVCClassFactory@@XZ; CreateClassFactory(void)
0x1800573e0  mov     rbx, rax
0x1800573e3  test    rax, rax
0x1800573e6  jz      loc_18005748A
0x1800573ec  mov     rcx, rax; this
0x1800573ef  call    ?UnregisterServer@CClassFactory@@QEAAJXZ; CClassFactory::UnregisterServer(void)
0x1800573f4  mov     rcx, [rbx]
0x1800573f7  mov     edi, eax
0x1800573f9  mov     rax, [rcx+10h]
0x1800573fd  mov     rcx, rbx
0x180057400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057405  call    ?CreateAuthorClassFactory@@YAPEAVCClassFactory@@XZ; CreateAuthorClassFactory(void)
0x18005740a  mov     rsi, rax
0x18005740d  test    rax, rax
0x180057410  jz      short loc_18005748A
0x180057412  mov     rcx, rax; this
0x180057415  call    ?UnregisterServer@CClassFactory@@QEAAJXZ; CClassFactory::UnregisterServer(void)
0x18005741a  mov     rcx, [rsi]
0x18005741d  mov     ebx, eax
0x18005741f  mov     rax, [rcx+10h]
0x180057423  mov     rcx, rsi
0x180057426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005742b  test    ebx, ebx
0x18005742d  cmovs   edi, ebx
0x180057430  call    ?CreateEncodeClassFactory@@YAPEAVCClassFactory@@XZ; CreateEncodeClassFactory(void)
0x180057435  mov     rsi, rax
0x180057438  test    rax, rax
0x18005743b  jz      short loc_18005748A
0x18005743d  mov     rcx, rax; this
0x180057440  call    ?UnregisterServer@CClassFactory@@QEAAJXZ; CClassFactory::UnregisterServer(void)
0x180057445  mov     rcx, [rsi]
0x180057448  mov     ebx, eax
0x18005744a  mov     rax, [rcx+10h]
0x18005744e  mov     rcx, rsi
0x180057451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057456  test    ebx, ebx
0x180057458  cmovs   edi, ebx
0x18005745b  call    ?CreateRegExpClassFactory@@YAPEAVCClassFactory@@XZ; CreateRegExpClassFactory(void)
0x180057460  mov     rsi, rax
0x180057463  test    rax, rax
0x180057466  jz      short loc_18005748A
0x180057468  mov     rcx, rax; this
0x18005746b  call    ?UnregisterServer@CClassFactory@@QEAAJXZ; CClassFactory::UnregisterServer(void)
0x180057470  mov     rcx, [rsi]
0x180057473  mov     ebx, eax
0x180057475  mov     rax, [rcx+10h]
0x180057479  mov     rcx, rsi
0x18005747c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057481  test    ebx, ebx
0x180057483  cmovs   edi, ebx
0x180057486  mov     eax, edi
0x180057488  jmp     short loc_18005748F
0x18005748a  mov     eax, 8000FFFFh
0x18005748f  mov     rcx, [rsp+0D8h+var_18]
0x180057497  xor     rcx, rsp; StackCookie
0x18005749a  call    __security_check_cookie
0x18005749f  lea     r11, [rsp+0D8h+var_8]
0x1800574a7  mov     rbx, [r11+10h]
0x1800574ab  mov     rsi, [r11+18h]
0x1800574af  mov     rsp, r11
0x1800574b2  pop     rdi
0x1800574b3  retn
```
