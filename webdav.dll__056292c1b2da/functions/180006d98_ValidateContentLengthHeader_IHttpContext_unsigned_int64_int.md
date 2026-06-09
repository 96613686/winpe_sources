# ValidateContentLengthHeader(IHttpContext *,unsigned __int64 *,int *)

- ea: `0x180006d98`
- end: `0x180006ebf`
- name: `?ValidateContentLengthHeader@@YAJPEAVIHttpContext@@PEA_KPEAH@Z`
- size: `295`
- prototype: `__int64 __fastcall(struct IHttpContext *, unsigned __int64 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f640`

## callees

- `0x180006d98`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `msvcrt!_strtoui64` at `0x180006e0e`
- `msvcrt!_strtoui64` at `0x180006e0e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006e45`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006e45`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006e8c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006e8c`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180006e5c`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180006e5c`

## pseudocode

```c
__int64 __fastcall ValidateContentLengthHeader(struct IHttpContext *a1, unsigned __int64 *a2, int *a3)
{
  unsigned int v3; // ebp
  __int64 v7; // rax
  __int64 v8; // rax
  const char *v9; // rax
  const char *v10; // r15
  unsigned __int64 v11; // rax
  char *v12; // rdx
  __int64 v13; // rsi
  __int64 v14; // rbx
  void (__fastcall *v15)(__int64, const wchar_t *, __int64, __int64, char); // rdi
  char v17; // [rsp+20h] [rbp-88h]
  char *EndPtr; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v19[32]; // [rsp+38h] [rbp-70h] BYREF
  __int64 v20; // [rsp+58h] [rbp-50h]

  v3 = 0;
  *a2 = 0;
  *a3 = 0;
  v7 = *(_QWORD *)a1;
  EndPtr = 0;
  v8 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v7 + 24))(a1);
  v9 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v8 + 16LL))(v8, 11, 0);
  v10 = v9;
  if ( v9 )
  {
    EndPtr = 0;
    v11 = _strtoui64(v9, &EndPtr, 10);
    v12 = EndPtr;
    *a2 = v11;
    if ( v12 && *v12 )
    {
      v3 = -2147024895;
      v13 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
      STRU::STRU((STRU *)v19);
      v14 = 0;
      v15 = *(void (__fastcall **)(__int64, const wchar_t *, __int64, __int64, char))(*(_QWORD *)v13 + 32LL);
      v17 = 3;
      if ( (int)STRU::CopyA((STRU *)v19, v10) >= 0 )
        v14 = v20;
      v15(v13, L"Content-Length: Header Invalid", v14, 2147942401LL, v17);
      STRU::~STRU((STRU *)v19);
    }
    *a3 = 1;
  }
  return v3;
}

```

## disassembly

```asm
0x180006d98  mov     [rsp+arg_18], rbx
0x180006d9d  push    rbp
0x180006d9e  push    rsi
0x180006d9f  push    rdi
0x180006da0  push    r14
0x180006da2  push    r15
0x180006da4  sub     rsp, 80h
0x180006dab  mov     rax, cs:__security_cookie
0x180006db2  xor     rax, rsp
0x180006db5  mov     [rsp+0A8h+var_38], rax
0x180006dba  xor     ebp, ebp
0x180006dbc  mov     r14, r8
0x180006dbf  mov     [rdx], rbp
0x180006dc2  mov     rbx, rdx
0x180006dc5  mov     [r8], ebp
0x180006dc8  mov     rdi, rcx
0x180006dcb  mov     rax, [rcx]
0x180006dce  mov     [rsp+0A8h+EndPtr], rbp
0x180006dd3  mov     rax, [rax+18h]
0x180006dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ddc  mov     rcx, rax
0x180006ddf  lea     edx, [rbp+0Bh]
0x180006de2  xor     r8d, r8d
0x180006de5  mov     rax, [rax]
0x180006de8  mov     rax, [rax+10h]
0x180006dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006df1  mov     r15, rax
0x180006df4  test    rax, rax
0x180006df7  jz      loc_180006E99
0x180006dfd  lea     r8d, [rbp+0Ah]; Radix
0x180006e01  mov     [rsp+0A8h+EndPtr], rbp
0x180006e06  lea     rdx, [rsp+0A8h+EndPtr]; EndPtr
0x180006e0b  mov     rcx, rax; String
0x180006e0e  call    cs:__imp__strtoui64
0x180006e14  mov     rdx, [rsp+0A8h+EndPtr]
0x180006e19  mov     [rbx], rax
0x180006e1c  test    rdx, rdx
0x180006e1f  jz      short loc_180006E92
0x180006e21  cmp     [rdx], bpl
0x180006e24  jz      short loc_180006E92
0x180006e26  mov     rax, [rdi]
0x180006e29  mov     rcx, rdi
0x180006e2c  mov     ebp, 80070001h
0x180006e31  mov     rax, [rax+110h]
0x180006e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e3d  lea     rcx, [rsp+0A8h+var_70]
0x180006e42  mov     rsi, rax
0x180006e45  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006e4b  mov     rax, [rsi]
0x180006e4e  lea     rcx, [rsp+0A8h+var_70]
0x180006e53  mov     rdx, r15
0x180006e56  xor     ebx, ebx
0x180006e58  mov     rdi, [rax+20h]
0x180006e5c  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x180006e62  mov     r9d, ebp
0x180006e65  mov     [rsp+0A8h+var_88], 3
0x180006e6a  test    eax, eax
0x180006e6c  lea     rdx, aContentLengthH; "Content-Length: Header Invalid"
0x180006e73  mov     rcx, rsi
0x180006e76  mov     rax, rdi
0x180006e79  cmovns  rbx, [rsp+0A8h+var_50]
0x180006e7f  mov     r8, rbx
0x180006e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e87  lea     rcx, [rsp+0A8h+var_70]
0x180006e8c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180006e92  mov     dword ptr [r14], 1
0x180006e99  mov     eax, ebp
0x180006e9b  mov     rcx, [rsp+0A8h+var_38]
0x180006ea0  xor     rcx, rsp; StackCookie
0x180006ea3  call    __security_check_cookie
0x180006ea8  mov     rbx, [rsp+0A8h+arg_18]
0x180006eb0  add     rsp, 80h
0x180006eb7  pop     r15
0x180006eb9  pop     r14
0x180006ebb  pop     rdi
0x180006ebc  pop     rsi
0x180006ebd  pop     rbp
0x180006ebe  retn
```
