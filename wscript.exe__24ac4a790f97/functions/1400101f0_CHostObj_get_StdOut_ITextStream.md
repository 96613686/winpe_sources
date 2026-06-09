# CHostObj::get_StdOut(ITextStream * *)

- ea: `0x1400101f0`
- end: `0x1400102fc`
- name: `?get_StdOut@CHostObj@@UEAAJPEAPEAUITextStream@@@Z`
- size: `268`
- prototype: `__int64 __fastcall(CHostObj *__hidden this, struct ITextStream **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400101f0`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetStdHandle` at `0x140010274`
- `KERNEL32!GetStdHandle` at `0x140010274`
- `KERNEL32!GetConsoleMode` at `0x14001028a`
- `KERNEL32!GetConsoleMode` at `0x14001028a`
- `ole32!CoCreateInstance` at `0x14001024d`
- `ole32!CoCreateInstance` at `0x14001024d`

## pseudocode

```c
__int64 __fastcall CHostObj::get_StdOut(CHostObj *this, struct ITextStream **a2)
{
  _QWORD *v5; // rbx
  HRESULT v6; // edi
  HANDLE StdHandle; // rax
  _BOOL8 v8; // r8
  DWORD Mode; // [rsp+58h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v5 = (_QWORD *)((char *)this + 112);
  *a2 = 0;
  if ( !*((_QWORD *)this + 14) )
  {
    ppv = 0;
    v6 = CoCreateInstance(&CLSID_FileSystemObject, 0, 1u, &IID_IFileSystem3, &ppv);
    if ( v6 < 0 )
      return (unsigned int)v6;
    v8 = 0;
    if ( Global::g_fWindowsNT )
    {
      if ( *(_BYTE *)(*((_QWORD *)this + 16) + 73LL)
        || (StdHandle = GetStdHandle(0xFFFFFFF5), Mode = 0, GetConsoleMode(StdHandle, &Mode)) )
      {
        v8 = 1;
      }
    }
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, _BOOL8, _QWORD *))(*(_QWORD *)ppv + 256LL))(ppv, 1, v8, v5);
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
0x1400101f0  mov     [rsp+arg_0], rbx
0x1400101f5  push    rbp
0x1400101f6  push    rsi
0x1400101f7  push    rdi
0x1400101f8  sub     rsp, 30h
0x1400101fc  mov     rsi, rdx
0x1400101ff  mov     rbp, rcx
0x140010202  test    rdx, rdx
0x140010205  jnz     short loc_140010211
0x140010207  mov     eax, 80004003h
0x14001020c  jmp     loc_1400102EF
0x140010211  lea     rbx, [rcx+70h]
0x140010215  mov     qword ptr [rdx], 0
0x14001021c  cmp     qword ptr [rbx], 0
0x140010220  jnz     loc_1400102D8
0x140010226  xor     edx, edx; pUnkOuter
0x140010228  mov     [rsp+48h+arg_10], 0
0x140010231  lea     rax, [rsp+48h+arg_10]
0x140010236  lea     r9, IID_IFileSystem3; riid
0x14001023d  mov     [rsp+48h+ppv], rax; ppv
0x140010242  lea     rcx, CLSID_FileSystemObject; rclsid
0x140010249  lea     r8d, [rdx+1]; dwClsContext
0x14001024d  call    cs:__imp_CoCreateInstance
0x140010253  mov     edi, eax
0x140010255  test    eax, eax
0x140010257  js      short loc_1400102D4
0x140010259  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x140010260  jz      short loc_14001029F
0x140010262  mov     rax, [rbp+80h]
0x140010269  cmp     byte ptr [rax+49h], 0
0x14001026d  jnz     short loc_140010294
0x14001026f  mov     ecx, 0FFFFFFF5h; nStdHandle
0x140010274  call    cs:__imp_GetStdHandle
0x14001027a  lea     rdx, [rsp+48h+Mode]; lpMode
0x14001027f  mov     [rsp+48h+Mode], 0
0x140010287  mov     rcx, rax; hConsoleHandle
0x14001028a  call    cs:__imp_GetConsoleMode
0x140010290  test    eax, eax
0x140010292  jz      short loc_14001029F
0x140010294  mov     r8d, 1
0x14001029a  mov     edx, r8d
0x14001029d  jmp     short loc_1400102A6
0x14001029f  xor     r8d, r8d
0x1400102a2  lea     edx, [r8+1]
0x1400102a6  mov     rcx, [rsp+48h+arg_10]
0x1400102ab  mov     r9, rbx
0x1400102ae  mov     rax, [rcx]
0x1400102b1  mov     rax, [rax+100h]
0x1400102b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400102bd  mov     rcx, [rsp+48h+arg_10]
0x1400102c2  mov     edi, eax
0x1400102c4  mov     rax, [rcx]
0x1400102c7  mov     rax, [rax+10h]
0x1400102cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400102d0  test    edi, edi
0x1400102d2  jns     short loc_1400102D8
0x1400102d4  mov     eax, edi
0x1400102d6  jmp     short loc_1400102EF
0x1400102d8  mov     rax, [rbx]
0x1400102db  mov     [rsi], rax
0x1400102de  mov     rcx, [rbx]
0x1400102e1  mov     rax, [rcx]
0x1400102e4  mov     rax, [rax+8]
0x1400102e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400102ed  xor     eax, eax
0x1400102ef  mov     rbx, [rsp+48h+arg_0]
0x1400102f4  add     rsp, 30h
0x1400102f8  pop     rdi
0x1400102f9  pop     rsi
0x1400102fa  pop     rbp
0x1400102fb  retn
```
