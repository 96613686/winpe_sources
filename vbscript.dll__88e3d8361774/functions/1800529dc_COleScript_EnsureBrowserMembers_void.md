# COleScript::EnsureBrowserMembers(void)

- ea: `0x1800529dc`
- end: `0x180052a7c`
- name: `?EnsureBrowserMembers@COleScript@@IEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(COleScript *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180052678`
- `0x180052710`
- `0x18005281c`

## callees

- `0x180022ce0`
- `0x1800238f4`
- `0x1800529dc`
- `0x180056758`

## import_xrefs

- `OLE32!CoCreateInstance` at `0x180052a5a`
- `OLE32!CoCreateInstance` at `0x180052a5a`

## pseudocode

```c
__int64 __fastcall COleScript::EnsureBrowserMembers(COleScript *this)
{
  MUTX *v1; // rsi
  HRESULT Instance; // edi
  LPVOID *ppv; // rbx
  struct ComDebugFormatter *v6; // [rsp+40h] [rbp+8h] BYREF

  v1 = (COleScript *)((char *)this + 808);
  if ( !(unsigned int)MUTX::Enter((COleScript *)((char *)this + 808)) )
    return 2147500037LL;
  Instance = 0;
  if ( *((_QWORD *)this + 96) )
    goto LABEL_6;
  v6 = 0;
  Instance = ComDebugFormatter::Create(&v6);
  if ( Instance >= 0 )
  {
    *((_QWORD *)this + 96) = v6;
LABEL_6:
    ppv = (LPVOID *)((char *)this + 760);
    if ( !*ppv )
      Instance = CoCreateInstance(&CLSID_DebugHelper, 0, 0x15u, &IID_IDebugHelper, ppv);
  }
  MUTX::Leave(v1);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800529dc  mov     [rsp+arg_8], rbx
0x1800529e1  mov     [rsp+arg_10], rsi
0x1800529e6  push    rdi
0x1800529e7  sub     rsp, 30h
0x1800529eb  lea     rsi, [rcx+328h]
0x1800529f2  mov     rbx, rcx
0x1800529f5  mov     rcx, rsi; this
0x1800529f8  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x1800529fd  test    eax, eax
0x1800529ff  jnz     short loc_180052A08
0x180052a01  mov     eax, 80004005h
0x180052a06  jmp     short loc_180052A6C
0x180052a08  xor     edi, edi
0x180052a0a  cmp     [rbx+300h], rdi
0x180052a11  jnz     short loc_180052A34
0x180052a13  lea     rcx, [rsp+38h+arg_0]; struct ComDebugFormatter **
0x180052a18  mov     [rsp+38h+arg_0], rdi
0x180052a1d  call    ?Create@ComDebugFormatter@@SAJPEAPEAV1@@Z; ComDebugFormatter::Create(ComDebugFormatter * *)
0x180052a22  mov     edi, eax
0x180052a24  test    eax, eax
0x180052a26  js      short loc_180052A62
0x180052a28  mov     rcx, [rsp+38h+arg_0]
0x180052a2d  mov     [rbx+300h], rcx
0x180052a34  add     rbx, 2F8h
0x180052a3b  cmp     qword ptr [rbx], 0
0x180052a3f  jnz     short loc_180052A62
0x180052a41  xor     edx, edx; pUnkOuter
0x180052a43  mov     [rsp+38h+ppv], rbx; ppv
0x180052a48  lea     r9, IID_IDebugHelper; riid
0x180052a4f  lea     rcx, CLSID_DebugHelper; rclsid
0x180052a56  lea     r8d, [rdx+15h]; dwClsContext
0x180052a5a  call    cs:__imp_CoCreateInstance
0x180052a60  mov     edi, eax
0x180052a62  mov     rcx, rsi; this
0x180052a65  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x180052a6a  mov     eax, edi
0x180052a6c  mov     rbx, [rsp+38h+arg_8]
0x180052a71  mov     rsi, [rsp+38h+arg_10]
0x180052a76  add     rsp, 30h
0x180052a7a  pop     rdi
0x180052a7b  retn
```
