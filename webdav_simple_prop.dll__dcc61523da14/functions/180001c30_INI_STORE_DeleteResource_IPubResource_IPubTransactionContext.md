# INI_STORE::DeleteResource(IPubResource *,IPubTransactionContext * *)

- ea: `0x180001c30`
- end: `0x180001cd6`
- name: `?DeleteResource@INI_STORE@@UEAAJPEAVIPubResource@@PEAPEAVIPubTransactionContext@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(INI_STORE *this, struct IPubResource *, struct IPubTransactionContext **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001c30`
- `0x180002a7c`
- `0x180002fd0`
- `0x180003490`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180001c5a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001c65`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001c5a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001c65`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001ca2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001cad`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001ca2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001cad`

## pseudocode

```c
__int64 __fastcall INI_STORE::DeleteResource(
        INI_STORE *this,
        struct IPubResource *a2,
        struct IPubTransactionContext **a3)
{
  int IniBinding; // ebx
  LPCWSTR v7[7]; // [rsp+20h] [rbp-88h] BYREF
  _BYTE v8[56]; // [rsp+58h] [rbp-50h] BYREF

  STRU::STRU((STRU *)v7);
  STRU::STRU((STRU *)v8);
  if ( *((_DWORD *)this + 3) )
  {
    IniBinding = 0;
  }
  else
  {
    IniBinding = MakeIniBinding(a2, (INI_STORE *)((char *)this + 12), (struct INI_BINDING *)v7, 1);
    if ( IniBinding >= 0 )
      IniBinding = DeleteEntireSection(v7);
  }
  STRU::~STRU((STRU *)v8);
  STRU::~STRU((STRU *)v7);
  return (unsigned int)IniBinding;
}

```

## disassembly

```asm
0x180001c30  mov     [rsp+arg_0], rbx
0x180001c35  push    rdi
0x180001c36  sub     rsp, 0A0h
0x180001c3d  mov     rax, cs:__security_cookie
0x180001c44  xor     rax, rsp
0x180001c47  mov     [rsp+0A8h+var_18], rax
0x180001c4f  mov     rbx, rcx
0x180001c52  mov     rdi, rdx
0x180001c55  lea     rcx, [rsp+0A8h+var_88]
0x180001c5a  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180001c60  lea     rcx, [rsp+0A8h+var_50]
0x180001c65  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180001c6b  lea     rdx, [rbx+0Ch]; struct INI_OPTIONS *
0x180001c6f  cmp     dword ptr [rdx], 0
0x180001c72  jz      short loc_180001C78
0x180001c74  xor     ebx, ebx
0x180001c76  jmp     short loc_180001C9D
0x180001c78  mov     r9d, 1; int
0x180001c7e  lea     r8, [rsp+0A8h+var_88]; struct INI_BINDING *
0x180001c83  mov     rcx, rdi; struct IPubResource *
0x180001c86  call    ?MakeIniBinding@@YAJPEAVIPubResource@@PEAUINI_OPTIONS@@PEAUINI_BINDING@@H@Z; MakeIniBinding(IPubResource *,INI_OPTIONS *,INI_BINDING *,int)
0x180001c8b  mov     ebx, eax
0x180001c8d  test    eax, eax
0x180001c8f  js      short loc_180001C9D
0x180001c91  lea     rcx, [rsp+0A8h+var_88]; struct INI_BINDING *
0x180001c96  call    ?DeleteEntireSection@@YAJPEAUINI_BINDING@@@Z; DeleteEntireSection(INI_BINDING *)
0x180001c9b  mov     ebx, eax
0x180001c9d  lea     rcx, [rsp+0A8h+var_50]
0x180001ca2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001ca8  lea     rcx, [rsp+0A8h+var_88]
0x180001cad  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001cb3  mov     eax, ebx
0x180001cb5  mov     rcx, [rsp+0A8h+var_18]
0x180001cbd  xor     rcx, rsp; StackCookie
0x180001cc0  call    __security_check_cookie
0x180001cc5  mov     rbx, [rsp+0A8h+arg_0]
0x180001ccd  add     rsp, 0A0h
0x180001cd4  pop     rdi
0x180001cd5  retn
```
