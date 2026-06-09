# CompileScriptException::ProcessError(COleScript *,Scanner *,ErrHandler *,ParseNode *,long,void *,ushort const *)

- ea: `0x180040b38`
- end: `0x180040d51`
- name: `?ProcessError@CompileScriptException@@QEAAJPEAVCOleScript@@PEAVScanner@@PEAVErrHandler@@PEAUParseNode@@JPEAXPEBG@Z`
- size: `537`
- prototype: `__int64 __fastcall(CompileScriptException *__hidden this, struct COleScript *, struct Scanner *, struct ErrHandler *, struct ParseNode *, UINT len, LPCSTR psz, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013a1c`

## callees

- `0x180011650`
- `0x18001199c`
- `0x180014c8c`
- `0x180040b38`
- `0x180079436`
- `0x180079490`

## import_xrefs

- `msvcrt!wcscspn` at `0x180040cff`
- `msvcrt!wcscspn` at `0x180040cff`
- `msvcrt!_snwprintf_s` at `0x180040bf7`
- `msvcrt!_snwprintf_s` at `0x180040bf7`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180040c59`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180040c59`

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
0x180040b38  mov     [rsp+arg_10], rbx
0x180040b3d  push    rbp
0x180040b3e  push    rsi
0x180040b3f  push    rdi
0x180040b40  push    r12
0x180040b42  push    r13
0x180040b44  push    r14
0x180040b46  push    r15
0x180040b48  sub     rsp, 0B0h
0x180040b4f  mov     rax, cs:__security_cookie
0x180040b56  xor     rax, rsp
0x180040b59  mov     [rsp+0E8h+var_48], rax
0x180040b61  mov     ebp, [rsp+0E8h+len]
0x180040b68  xor     r13d, r13d
0x180040b6b  mov     r15, [rsp+0E8h+psz]
0x180040b73  mov     rsi, r9
0x180040b76  mov     r12, [rsp+0E8h+arg_38]
0x180040b7e  mov     rbx, r8
0x180040b81  mov     r14, rdx
0x180040b84  mov     rdi, rcx
0x180040b87  test    rcx, rcx
0x180040b8a  jnz     short loc_180040B98
0x180040b8c  mov     eax, [r9+100h]
0x180040b93  jmp     loc_180040D1E
0x180040b98  xor     edx, edx; Val
0x180040b9a  lea     r8d, [rdx+68h]; Size
0x180040b9e  call    memset_0
0x180040ba3  mov     eax, [rsi+100h]
0x180040ba9  mov     [rdi+40h], eax
0x180040bac  mov     ecx, [rsi+100h]
0x180040bb2  mov     eax, ecx
0x180040bb4  mov     r14d, [r14+0B8h]
0x180040bbb  and     eax, 1FFF0000h
0x180040bc0  cmp     eax, 0A0000h
0x180040bc5  jnz     short loc_180040BDB
0x180040bc7  movzx   ecx, cx; int
0x180040bca  mov     edx, r14d; unsigned int
0x180040bcd  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x180040bd2  mov     [rdi+18h], rax
0x180040bd6  test    rax, rax
0x180040bd9  jnz     short loc_180040C1D
0x180040bdb  mov     eax, [rdi+40h]
0x180040bde  lea     r9, aErrorD; "error %d"
0x180040be5  mov     edx, 32h ; '2'; BufferCount
0x180040bea  mov     [rsp+0E8h+var_C8], eax
0x180040bee  lea     rcx, [rsp+0E8h+Buffer]; Buffer
0x180040bf3  lea     r8d, [rdx-1]; MaxCount
0x180040bf7  call    cs:__imp__snwprintf_s
0x180040bfe  nop     dword ptr [rax+rax+00h]
0x180040c03  lea     rcx, [rsp+0E8h+Buffer]; unsigned __int16 *
0x180040c08  call    ?_SysAllocString@@YAPEAGPEBG@Z; _SysAllocString(ushort const *)
0x180040c0d  mov     [rdi+18h], rax
0x180040c11  test    rax, rax
0x180040c14  jnz     short loc_180040C1D
0x180040c16  mov     dword ptr [rdi+40h], 8007000Eh
0x180040c1d  mov     edx, r14d; unsigned int
0x180040c20  mov     ecx, 1000h; int
0x180040c25  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x180040c2a  mov     [rdi+10h], rax
0x180040c2e  cmp     [rsp+0E8h+arg_20], r13
0x180040c36  jnz     loc_180040D19
0x180040c3c  test    rbx, rbx
0x180040c3f  jz      loc_180040D19
0x180040c45  test    ebp, ebp
0x180040c47  jle     short loc_180040C69
0x180040c49  mov     rax, r13
0x180040c4c  cmp     ebp, 7FFFFFFDh
0x180040c52  jnb     short loc_180040C65
0x180040c54  mov     edx, ebp; len
0x180040c56  mov     rcx, r15; psz
0x180040c59  call    cs:__imp_SysAllocStringByteLen
0x180040c60  nop     dword ptr [rax+rax+00h]
0x180040c65  mov     [rdi+60h], rax
0x180040c69  mov     rax, [rbx+20h]
0x180040c6d  sub     rax, [rbx+10h]
0x180040c71  sar     rax, 1
0x180040c74  mov     [rdi], eax
0x180040c76  mov     rax, [rbx+28h]
0x180040c7a  sub     rax, [rbx+10h]
0x180040c7e  sar     rax, 1
0x180040c81  mov     [rdi+4], eax
0x180040c84  mov     rcx, [rbx+28h]
0x180040c88  cmp     [rbx+18h], rcx
0x180040c8c  jnz     short loc_180040CA0
0x180040c8e  mov     eax, [rbx+180h]
0x180040c94  test    eax, eax
0x180040c96  jle     short loc_180040CA0
0x180040c98  cmp     [rbx+20h], rcx
0x180040c9c  dec     eax
0x180040c9e  jb      short loc_180040CA6
0x180040ca0  mov     eax, [rbx+180h]
0x180040ca6  mov     [rdi+50h], eax
0x180040ca9  mov     rcx, [rbx+28h]
0x180040cad  mov     rax, [rbx+18h]
0x180040cb1  cmp     rax, rcx
0x180040cb4  jnz     short loc_180040CC9
0x180040cb6  cmp     [rbx+180h], r13d
0x180040cbd  jle     short loc_180040CC9
0x180040cbf  cmp     [rbx+20h], rcx
0x180040cc3  jnb     short loc_180040CC9
0x180040cc5  mov     rax, [rbx+30h]
0x180040cc9  sub     rax, [rbx+10h]
0x180040ccd  sar     rax, 1
0x180040cd0  mov     [rdi+54h], eax
0x180040cd3  test    eax, eax
0x180040cd5  js      short loc_180040D4A
0x180040cd7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180040cdb  inc     rcx
0x180040cde  cmp     [r12+rcx*2], r13w
0x180040ce3  jnz     short loc_180040CDB
0x180040ce5  cmp     eax, ecx
0x180040ce7  jg      short loc_180040D4A
0x180040ce9  cmp     [rdi], eax
0x180040ceb  jge     short loc_180040CEF
0x180040ced  mov     [rdi], eax
0x180040cef  cdqe
0x180040cf1  lea     rdx, Control; "\n\r"
0x180040cf8  lea     rbx, [r12+rax*2]
0x180040cfc  mov     rcx, rbx; String
0x180040cff  call    cs:__imp_wcscspn
0x180040d06  nop     dword ptr [rax+rax+00h]
0x180040d0b  mov     edx, eax; unsigned int
0x180040d0d  mov     rcx, rbx; unsigned __int16 *
0x180040d10  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x180040d15  mov     [rdi+58h], rax
0x180040d19  mov     eax, 86664004h
0x180040d1e  mov     rcx, [rsp+0E8h+var_48]
0x180040d26  xor     rcx, rsp; StackCookie
0x180040d29  call    __security_check_cookie
0x180040d2e  mov     rbx, [rsp+0E8h+arg_10]
0x180040d36  add     rsp, 0B0h
0x180040d3d  pop     r15
0x180040d3f  pop     r14
0x180040d41  pop     r13
0x180040d43  pop     r12
0x180040d45  pop     rdi
0x180040d46  pop     rsi
0x180040d47  pop     rbp
0x180040d48  retn
0x180040d4a  mov     eax, 8000FFFFh
0x180040d4f  jmp     short loc_180040D1E
```
