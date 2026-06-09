# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x18000f500`
- end: `0x18000f685`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `389`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180012cac`
- `0x180013070`

## callees

- `0x180003b70`
- `0x1800099ac`
- `0x18000f1e8`
- `0x18000f500`
- `0x180014270`
- `0x180014300`

## import_xrefs

- `msvcrt!free` at `0x18000f631`
- `msvcrt!free` at `0x18000f646`
- `msvcrt!free` at `0x18000f631`
- `msvcrt!free` at `0x18000f646`
- `msvcrt!malloc` at `0x18000f5c3`
- `msvcrt!malloc` at `0x18000f5c3`
- `KERNEL32!WideCharToMultiByte` at `0x18000f604`
- `KERNEL32!WideCharToMultiByte` at `0x18000f604`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rax
  __int64 cbMultiByte; // rsi
  _QWORD *v8; // rbx
  unsigned __int64 v9; // rax
  void *v10; // rsp
  CHAR *lpMultiByteStr; // rdi
  _QWORD *v12; // rax
  unsigned int v13; // edi
  void *v14; // rcx
  void *v16; // rcx
  CHAR MultiByteStr[8]; // [rsp+40h] [rbp+0h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  cbMultiByte = 2LL * ((int)v6 + 1);
  if ( (unsigned __int64)(cbMultiByte + 0x80000000LL) > 0xFFFFFFFF )
    return 2147942414LL;
  v8 = 0;
  if ( (int)cbMultiByte <= 1024
    && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(
         (ATL::_ATL_SAFE_ALLOCA_IMPL *)(int)cbMultiByte,
         (unsigned __int64)a2) )
  {
    v9 = (int)cbMultiByte + 15LL;
    if ( v9 < (int)cbMultiByte )
      v9 = 0xFFFFFFFFFFFFFF0LL;
    v10 = alloca(v9 & 0xFFFFFFFFFFFFFFF0uLL);
    lpMultiByteStr = MultiByteStr;
  }
  else
  {
    if ( (unsigned __int64)~(__int64)(int)cbMultiByte < 0x10 )
      ATL::AtlThrowImpl(-2147024809);
    v12 = malloc((int)cbMultiByte + 16LL);
    if ( v12 )
    {
      *v12 = 0;
      lpMultiByteStr = (CHAR *)(v12 + 2);
      v8 = v12;
    }
    else
    {
      lpMultiByteStr = 0;
    }
  }
  if ( !lpMultiByteStr || (*lpMultiByteStr = 0, !WideCharToMultiByte(3u, 0, a2, -1, lpMultiByteStr, cbMultiByte, 0, 0)) )
  {
    while ( v8 )
    {
      v16 = v8;
      v8 = (_QWORD *)*v8;
      free(v16);
    }
    return 2147942414LL;
  }
  v13 = ATL::CExpansionVector::Add((ATL::CRegObject *)((char *)this + 8), lpMultiByteStr, a3) == 0 ? 0x8007000E : 0;
  while ( v8 )
  {
    v14 = v8;
    v8 = (_QWORD *)*v8;
    free(v14);
  }
  return v13;
}

```

## disassembly

```asm
0x18000f500  push    rbp
0x18000f502  push    rbx
0x18000f503  push    rsi
0x18000f504  push    rdi
0x18000f505  push    r12
0x18000f507  push    r13
0x18000f509  push    r14
0x18000f50b  push    r15
0x18000f50d  sub     rsp, 58h
0x18000f511  lea     rbp, [rsp+40h]
0x18000f516  mov     rax, cs:__security_cookie
0x18000f51d  xor     rax, rbp
0x18000f520  mov     qword ptr [rbp+50h+MultiByteStr], rax
0x18000f524  xor     r12d, r12d
0x18000f527  mov     r15, r8
0x18000f52a  mov     r14, rdx
0x18000f52d  mov     r13, rcx
0x18000f530  test    rdx, rdx
0x18000f533  jz      loc_18000F658
0x18000f539  test    r8, r8
0x18000f53c  jz      loc_18000F658
0x18000f542  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f546  inc     rax
0x18000f549  cmp     [rdx+rax*2], r12w
0x18000f54e  jnz     short loc_18000F546
0x18000f550  inc     eax
0x18000f552  movsxd  rcx, eax
0x18000f555  mov     eax, 80000000h
0x18000f55a  lea     rsi, [rcx+rcx]
0x18000f55e  mov     ecx, 0FFFFFFFFh
0x18000f563  add     rax, rsi
0x18000f566  cmp     rax, rcx
0x18000f569  ja      loc_18000F651
0x18000f56f  movsxd  rdi, esi
0x18000f572  mov     rbx, r12
0x18000f575  cmp     esi, 400h
0x18000f57b  jg      short loc_18000F5AF
0x18000f57d  mov     rcx, rdi; this
0x18000f580  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x18000f585  test    al, al
0x18000f587  jz      short loc_18000F5AF
0x18000f589  lea     rax, [rdi+0Fh]
0x18000f58d  cmp     rax, rdi
0x18000f590  ja      short loc_18000F59C
0x18000f592  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000f59c  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000f5a0  call    _alloca_probe
0x18000f5a5  sub     rsp, rax
0x18000f5a8  lea     rdi, [rsp+90h+MultiByteStr]
0x18000f5ad  jmp     short loc_18000F5DD
0x18000f5af  mov     rax, rdi
0x18000f5b2  not     rax
0x18000f5b5  cmp     rax, 10h
0x18000f5b9  jb      loc_18000F67A
0x18000f5bf  lea     rcx, [rdi+10h]; Size
0x18000f5c3  call    cs:__imp_malloc
0x18000f5c9  test    rax, rax
0x18000f5cc  jnz     short loc_18000F5D3
0x18000f5ce  mov     rdi, r12
0x18000f5d1  jmp     short loc_18000F5DD
0x18000f5d3  mov     [rax], r12
0x18000f5d6  lea     rdi, [rax+10h]
0x18000f5da  mov     rbx, rax
0x18000f5dd  test    rdi, rdi
0x18000f5e0  jz      short loc_18000F64C
0x18000f5e2  mov     [rsp+90h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18000f5e7  xor     edx, edx; dwFlags
0x18000f5e9  mov     [rsp+90h+lpDefaultChar], r12; lpDefaultChar
0x18000f5ee  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000f5f2  mov     [rsp+90h+cbMultiByte], esi; cbMultiByte
0x18000f5f6  mov     r8, r14; lpWideCharStr
0x18000f5f9  mov     [rdi], r12b
0x18000f5fc  lea     ecx, [rdx+3]; CodePage
0x18000f5ff  mov     [rsp+90h+lpMultiByteStr], rdi; lpMultiByteStr
0x18000f604  call    cs:__imp_WideCharToMultiByte
0x18000f60a  test    eax, eax
0x18000f60c  jz      short loc_18000F64C
0x18000f60e  lea     rcx, [r13+8]; this
0x18000f612  mov     r8, r15; unsigned __int16 *
0x18000f615  mov     rdx, rdi; char *
0x18000f618  call    ?Add@CExpansionVector@ATL@@QEAAHPEBDPEBG@Z; ATL::CExpansionVector::Add(char const *,ushort const *)
0x18000f61d  neg     eax
0x18000f61f  sbb     edi, edi
0x18000f621  not     edi
0x18000f623  and     edi, 8007000Eh
0x18000f629  jmp     short loc_18000F637
0x18000f62b  mov     rcx, rbx; Block
0x18000f62e  mov     rbx, [rbx]
0x18000f631  call    cs:__imp_free
0x18000f637  test    rbx, rbx
0x18000f63a  jnz     short loc_18000F62B
0x18000f63c  mov     eax, edi
0x18000f63e  jmp     short loc_18000F65D
0x18000f640  mov     rcx, rbx; Block
0x18000f643  mov     rbx, [rbx]
0x18000f646  call    cs:__imp_free
0x18000f64c  test    rbx, rbx
0x18000f64f  jnz     short loc_18000F640
0x18000f651  mov     eax, 8007000Eh
0x18000f656  jmp     short loc_18000F65D
0x18000f658  mov     eax, 80070057h
0x18000f65d  mov     rcx, qword ptr [rbp+50h+MultiByteStr]
0x18000f661  xor     rcx, rbp; StackCookie
0x18000f664  call    __security_check_cookie
0x18000f669  lea     rsp, [rbp+18h]
0x18000f66d  pop     r15
0x18000f66f  pop     r14
0x18000f671  pop     r13
0x18000f673  pop     r12
0x18000f675  pop     rdi
0x18000f676  pop     rsi
0x18000f677  pop     rbx
0x18000f678  pop     rbp
0x18000f679  retn
0x18000f67a  mov     ecx, 80070057h; int
0x18000f67f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
