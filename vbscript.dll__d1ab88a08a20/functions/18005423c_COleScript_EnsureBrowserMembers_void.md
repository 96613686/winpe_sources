# COleScript::EnsureBrowserMembers(void)

- ea: `0x18005423c`
- end: `0x1800542e3`
- name: `?EnsureBrowserMembers@COleScript@@IEAAJXZ`
- size: `167`
- prototype: `__int64 __fastcall(COleScript *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180053ecc`
- `0x180053f64`
- `0x180054070`

## callees

- `0x18001cb34`
- `0x18001eef0`
- `0x18005423c`
- `0x180058108`

## import_xrefs

- `OLE32!CoCreateInstance` at `0x1800542ba`
- `OLE32!CoCreateInstance` at `0x1800542ba`

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
0x18005423c  mov     [rsp+arg_8], rbx
0x180054241  mov     [rsp+arg_10], rsi
0x180054246  push    rdi
0x180054247  sub     rsp, 30h
0x18005424b  lea     rsi, [rcx+328h]
0x180054252  mov     rbx, rcx
0x180054255  mov     rcx, rsi; this
0x180054258  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18005425d  test    eax, eax
0x18005425f  jnz     short loc_180054268
0x180054261  mov     eax, 80004005h
0x180054266  jmp     short loc_1800542D2
0x180054268  xor     edi, edi
0x18005426a  cmp     [rbx+300h], rdi
0x180054271  jnz     short loc_180054294
0x180054273  lea     rcx, [rsp+38h+arg_0]; struct ComDebugFormatter **
0x180054278  mov     [rsp+38h+arg_0], rdi
0x18005427d  call    ?Create@ComDebugFormatter@@SAJPEAPEAV1@@Z; ComDebugFormatter::Create(ComDebugFormatter * *)
0x180054282  mov     edi, eax
0x180054284  test    eax, eax
0x180054286  js      short loc_1800542C8
0x180054288  mov     rcx, [rsp+38h+arg_0]
0x18005428d  mov     [rbx+300h], rcx
0x180054294  add     rbx, 2F8h
0x18005429b  cmp     qword ptr [rbx], 0
0x18005429f  jnz     short loc_1800542C8
0x1800542a1  xor     edx, edx; pUnkOuter
0x1800542a3  mov     [rsp+38h+ppv], rbx; ppv
0x1800542a8  lea     r9, IID_IDebugHelper; riid
0x1800542af  lea     rcx, CLSID_DebugHelper; rclsid
0x1800542b6  lea     r8d, [rdx+15h]; dwClsContext
0x1800542ba  call    cs:__imp_CoCreateInstance
0x1800542c1  nop     dword ptr [rax+rax+00h]
0x1800542c6  mov     edi, eax
0x1800542c8  mov     rcx, rsi; this
0x1800542cb  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x1800542d0  mov     eax, edi
0x1800542d2  mov     rbx, [rsp+38h+arg_8]
0x1800542d7  mov     rsi, [rsp+38h+arg_10]
0x1800542dc  add     rsp, 30h
0x1800542e0  pop     rdi
0x1800542e1  retn
```
