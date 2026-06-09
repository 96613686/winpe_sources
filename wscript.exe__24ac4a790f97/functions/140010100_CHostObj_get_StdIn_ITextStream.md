# CHostObj::get_StdIn(ITextStream * *)

- ea: `0x140010100`
- end: `0x1400101db`
- name: `?get_StdIn@CHostObj@@UEAAJPEAPEAUITextStream@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(CHostObj *__hidden this, struct ITextStream **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140010100`
- `0x140018010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x14001015a`
- `ole32!CoCreateInstance` at `0x14001015a`

## pseudocode

```c
__int64 __fastcall CHostObj::get_StdIn(CHostObj *this, struct ITextStream **a2)
{
  _QWORD *v5; // rbx
  HRESULT v6; // edi
  _BOOL8 v7; // r8
  LPVOID ppv; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v5 = (_QWORD *)((char *)this + 104);
  *a2 = 0;
  if ( !*((_QWORD *)this + 13) )
  {
    ppv = 0;
    v6 = CoCreateInstance(&CLSID_FileSystemObject, 0, 1u, &IID_IFileSystem3, &ppv);
    if ( v6 < 0 )
      return (unsigned int)v6;
    v7 = Global::g_fWindowsNT && *(_BYTE *)(*((_QWORD *)this + 16) + 73LL);
    v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _BOOL8, _QWORD *))(*(_QWORD *)ppv + 256LL))(ppv, 0, v7, v5);
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
0x140010100  push    rbx
0x140010102  push    rbp
0x140010103  push    rsi
0x140010104  push    rdi
0x140010105  sub     rsp, 38h
0x140010109  mov     rsi, rdx
0x14001010c  mov     rbp, rcx
0x14001010f  test    rdx, rdx
0x140010112  jnz     short loc_14001011E
0x140010114  mov     eax, 80004003h
0x140010119  jmp     loc_1400101D2
0x14001011e  lea     rbx, [rcx+68h]
0x140010122  mov     qword ptr [rdx], 0
0x140010129  cmp     qword ptr [rbx], 0
0x14001012d  jnz     loc_1400101BB
0x140010133  xor     edx, edx; pUnkOuter
0x140010135  mov     [rsp+58h+arg_8], 0
0x14001013e  lea     rax, [rsp+58h+arg_8]
0x140010143  lea     r9, IID_IFileSystem3; riid
0x14001014a  mov     [rsp+58h+ppv], rax; ppv
0x14001014f  lea     rcx, CLSID_FileSystemObject; rclsid
0x140010156  lea     r8d, [rdx+1]; dwClsContext
0x14001015a  call    cs:__imp_CoCreateInstance
0x140010160  mov     edi, eax
0x140010162  test    eax, eax
0x140010164  js      short loc_1400101B7
0x140010166  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x14001016d  jz      short loc_140010184
0x14001016f  mov     rax, [rbp+80h]
0x140010176  cmp     byte ptr [rax+49h], 0
0x14001017a  jz      short loc_140010184
0x14001017c  mov     r8d, 1
0x140010182  jmp     short loc_140010187
0x140010184  xor     r8d, r8d
0x140010187  mov     rcx, [rsp+58h+arg_8]
0x14001018c  mov     r9, rbx
0x14001018f  xor     edx, edx
0x140010191  mov     rax, [rcx]
0x140010194  mov     rax, [rax+100h]
0x14001019b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101a0  mov     rcx, [rsp+58h+arg_8]
0x1400101a5  mov     edi, eax
0x1400101a7  mov     rax, [rcx]
0x1400101aa  mov     rax, [rax+10h]
0x1400101ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101b3  test    edi, edi
0x1400101b5  jns     short loc_1400101BB
0x1400101b7  mov     eax, edi
0x1400101b9  jmp     short loc_1400101D2
0x1400101bb  mov     rax, [rbx]
0x1400101be  mov     [rsi], rax
0x1400101c1  mov     rcx, [rbx]
0x1400101c4  mov     rax, [rcx]
0x1400101c7  mov     rax, [rax+8]
0x1400101cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101d0  xor     eax, eax
0x1400101d2  add     rsp, 38h
0x1400101d6  pop     rdi
0x1400101d7  pop     rsi
0x1400101d8  pop     rbp
0x1400101d9  pop     rbx
0x1400101da  retn
```
