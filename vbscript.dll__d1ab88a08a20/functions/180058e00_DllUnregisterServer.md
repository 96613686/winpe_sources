# DllUnregisterServer

- ea: `0x180058e00`
- end: `0x180058f3b`
- name: `DllUnregisterServer`
- size: `315`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x18003a5bc`
- `0x18003a5e8`
- `0x1800436f4`
- `0x180043c68`
- `0x1800455dc`
- `0x180058e00`
- `0x180079436`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `KERNEL32!GetVersionExA` at `0x180058e43`
- `KERNEL32!GetVersionExA` at `0x180058e43`

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
0x180058e00  mov     [rsp+arg_0], rbx
0x180058e05  mov     [rsp+arg_8], rsi
0x180058e0a  push    rdi
0x180058e0b  sub     rsp, 0D0h
0x180058e12  mov     rax, cs:__security_cookie
0x180058e19  xor     rax, rsp
0x180058e1c  mov     [rsp+0D8h+var_18], rax
0x180058e24  xor     edx, edx; Val
0x180058e26  lea     rcx, [rsp+0D8h+VersionInformation.dwMajorVersion]; void *
0x180058e2b  mov     r8d, 90h; Size
0x180058e31  call    memset_0
0x180058e36  lea     rcx, [rsp+0D8h+VersionInformation]; lpVersionInformation
0x180058e3b  mov     [rsp+0D8h+VersionInformation.dwOSVersionInfoSize], 94h
0x180058e43  call    cs:__imp_GetVersionExA
0x180058e4a  nop     dword ptr [rax+rax+00h]
0x180058e4f  test    eax, eax
0x180058e51  jz      short loc_180058E61
0x180058e53  cmp     [rsp+0D8h+VersionInformation.dwMajorVersion], 6
0x180058e58  jb      short loc_180058E61
0x180058e5a  xor     eax, eax
0x180058e5c  jmp     loc_180058F15
0x180058e61  call    ?CreateClassFactory@@YAPEAVCClassFactory@@XZ; CreateClassFactory(void)
0x180058e66  mov     rbx, rax
0x180058e69  test    rax, rax
0x180058e6c  jz      loc_180058F10
0x180058e72  mov     rcx, rax; this
0x180058e75  call    ?UnregisterServer@CClassFactory@@QEAAJXZ; CClassFactory::UnregisterServer(void)
0x180058e7a  mov     rcx, [rbx]
0x180058e7d  mov     edi, eax
0x180058e7f  mov     rax, [rcx+10h]
0x180058e83  mov     rcx, rbx
0x180058e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e8b  call    ?CreateAuthorClassFactory@@YAPEAVCClassFactory@@XZ; CreateAuthorClassFactory(void)
0x180058e90  mov     rsi, rax
0x180058e93  test    rax, rax
0x180058e96  jz      short loc_180058F10
0x180058e98  mov     rcx, rax; this
0x180058e9b  call    ?UnregisterServer@CClassFactory@@QEAAJXZ; CClassFactory::UnregisterServer(void)
0x180058ea0  mov     rcx, [rsi]
0x180058ea3  mov     ebx, eax
0x180058ea5  mov     rax, [rcx+10h]
0x180058ea9  mov     rcx, rsi
0x180058eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058eb1  test    ebx, ebx
0x180058eb3  cmovs   edi, ebx
0x180058eb6  call    ?CreateEncodeClassFactory@@YAPEAVCClassFactory@@XZ; CreateEncodeClassFactory(void)
0x180058ebb  mov     rsi, rax
0x180058ebe  test    rax, rax
0x180058ec1  jz      short loc_180058F10
0x180058ec3  mov     rcx, rax; this
0x180058ec6  call    ?UnregisterServer@CClassFactory@@QEAAJXZ; CClassFactory::UnregisterServer(void)
0x180058ecb  mov     rcx, [rsi]
0x180058ece  mov     ebx, eax
0x180058ed0  mov     rax, [rcx+10h]
0x180058ed4  mov     rcx, rsi
0x180058ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058edc  test    ebx, ebx
0x180058ede  cmovs   edi, ebx
0x180058ee1  call    ?CreateRegExpClassFactory@@YAPEAVCClassFactory@@XZ; CreateRegExpClassFactory(void)
0x180058ee6  mov     rsi, rax
0x180058ee9  test    rax, rax
0x180058eec  jz      short loc_180058F10
0x180058eee  mov     rcx, rax; this
0x180058ef1  call    ?UnregisterServer@CClassFactory@@QEAAJXZ; CClassFactory::UnregisterServer(void)
0x180058ef6  mov     rcx, [rsi]
0x180058ef9  mov     ebx, eax
0x180058efb  mov     rax, [rcx+10h]
0x180058eff  mov     rcx, rsi
0x180058f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058f07  test    ebx, ebx
0x180058f09  cmovs   edi, ebx
0x180058f0c  mov     eax, edi
0x180058f0e  jmp     short loc_180058F15
0x180058f10  mov     eax, 8000FFFFh
0x180058f15  mov     rcx, [rsp+0D8h+var_18]
0x180058f1d  xor     rcx, rsp; StackCookie
0x180058f20  call    __security_check_cookie
0x180058f25  lea     r11, [rsp+0D8h+var_8]
0x180058f2d  mov     rbx, [r11+10h]
0x180058f31  mov     rsi, [r11+18h]
0x180058f35  mov     rsp, r11
0x180058f38  pop     rdi
0x180058f39  retn
```
