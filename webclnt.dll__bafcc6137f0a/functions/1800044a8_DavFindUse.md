# DavFindUse

- ea: `0x1800044a8`
- end: `0x1800045e0`
- name: `DavFindUse`
- size: `312`
- prototype: `__int64 __fastcall(__int64, __int64, _WORD *, _QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180006a90`
- `0x180007b50`
- `0x18000a370`

## callees

- `0x180004288`
- `0x180004344`
- `0x1800044a8`
- `0x18000b93c`
- `0x18002cf62`
- `0x18002cfa0`

## import_xrefs

- `DAVHLPR!DavRemoveDummyShareFromFileNameEx` at `0x18000455b`
- `DAVHLPR!DavRemoveDummyShareFromFileNameEx` at `0x18000455b`

## pseudocode

```c
__int64 __fastcall DavFindUse(__int64 a1, __int64 a2, _WORD *a3, _QWORD *a4, _QWORD *a5)
{
  bool v5; // zf
  __int64 v9; // rcx
  _WORD *v10; // rax
  _WORD *v11; // r8
  __int64 v12; // rdx
  _WORD *v13; // rcx
  _QWORD v15[2]; // [rsp+20h] [rbp-258h] BYREF
  _BYTE v16[528]; // [rsp+30h] [rbp-248h] BYREF

  v5 = *a3 == 92;
  v15[0] = 0;
  if ( v5 )
  {
    memset_0(v16, 0, 0x208u);
    v9 = 2147483646;
    v10 = v16;
    v11 = a3;
    v12 = 259;
    do
    {
      if ( !v9 )
        break;
      if ( !*v11 )
        break;
      *v10++ = *v11++;
      --v9;
      --v12;
    }
    while ( v12 );
    v13 = v10 - 1;
    if ( v12 )
      v13 = v10;
    *v13 = 0;
    DavRemoveDummyShareFromFileNameEx(v16, 0);
    DavFindRemote(a2, v16, a4, v15);
  }
  else
  {
    DavFindLocal(a2, a3, a4, v15);
  }
  if ( *a4 )
  {
    if ( a5 )
      *a5 = v15[0];
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 267, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, a3);
    return 2250;
  }
}

```

## disassembly

```asm
0x1800044a8  push    rbx
0x1800044aa  push    rbp
0x1800044ab  push    rsi
0x1800044ac  push    rdi
0x1800044ad  push    r14
0x1800044af  sub     rsp, 250h
0x1800044b6  mov     rax, cs:__security_cookie
0x1800044bd  xor     rax, rsp
0x1800044c0  mov     [rsp+278h+var_38], rax
0x1800044c8  mov     rdi, [rsp+278h+arg_20]
0x1800044d0  xor     r14d, r14d
0x1800044d3  cmp     word ptr [r8], 5Ch ; '\'
0x1800044d8  mov     rsi, r9
0x1800044db  mov     rbx, r8
0x1800044de  mov     [rsp+278h+var_258], r14
0x1800044e3  mov     rbp, rdx
0x1800044e6  jz      short loc_1800044FD
0x1800044e8  lea     r9, [rsp+278h+var_258]
0x1800044ed  mov     r8, rsi
0x1800044f0  mov     rdx, rbx
0x1800044f3  mov     rcx, rbp
0x1800044f6  call    DavFindLocal
0x1800044fb  jmp     short loc_180004576
0x1800044fd  xor     edx, edx; Val
0x1800044ff  lea     rcx, [rsp+278h+var_248]; void *
0x180004504  mov     r8d, 208h; Size
0x18000450a  call    memset_0
0x18000450f  mov     ecx, 7FFFFFFEh
0x180004514  lea     rax, [rsp+278h+var_248]
0x180004519  mov     r8, rbx
0x18000451c  mov     edx, 103h
0x180004521  test    rcx, rcx
0x180004524  jz      short loc_180004545
0x180004526  movzx   r9d, word ptr [r8]
0x18000452a  test    r9w, r9w
0x18000452e  jz      short loc_180004545
0x180004530  mov     [rax], r9w
0x180004534  add     r8, 2
0x180004538  add     rax, 2
0x18000453c  dec     rcx
0x18000453f  sub     rdx, 1
0x180004543  jnz     short loc_180004521
0x180004545  test    rdx, rdx
0x180004548  lea     rcx, [rax-2]
0x18000454c  cmovnz  rcx, rax
0x180004550  xor     edx, edx
0x180004552  mov     [rcx], r14w
0x180004556  lea     rcx, [rsp+278h+var_248]
0x18000455b  call    cs:__imp_DavRemoveDummyShareFromFileNameEx
0x180004561  lea     r9, [rsp+278h+var_258]
0x180004566  mov     r8, rsi
0x180004569  lea     rdx, [rsp+278h+var_248]
0x18000456e  mov     rcx, rbp
0x180004571  call    DavFindRemote
0x180004576  cmp     [rsi], r14
0x180004579  jnz     short loc_1800045B3
0x18000457b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004582  lea     rax, WPP_GLOBAL_Control
0x180004589  cmp     rcx, rax
0x18000458c  jz      short loc_1800045AC
0x18000458e  test    byte ptr [rcx+1Ch], 1
0x180004592  jz      short loc_1800045AC
0x180004594  mov     rcx, [rcx+10h]
0x180004598  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000459f  mov     edx, 10Bh
0x1800045a4  mov     r9, rbx
0x1800045a7  call    WPP_SF_S
0x1800045ac  mov     eax, 8CAh
0x1800045b1  jmp     short loc_1800045C2
0x1800045b3  test    rdi, rdi
0x1800045b6  jz      short loc_1800045C0
0x1800045b8  mov     rax, [rsp+278h+var_258]
0x1800045bd  mov     [rdi], rax
0x1800045c0  xor     eax, eax
0x1800045c2  mov     rcx, [rsp+278h+var_38]
0x1800045ca  xor     rcx, rsp; StackCookie
0x1800045cd  call    __security_check_cookie
0x1800045d2  add     rsp, 250h
0x1800045d9  pop     r14
0x1800045db  pop     rdi
0x1800045dc  pop     rsi
0x1800045dd  pop     rbp
0x1800045de  pop     rbx
0x1800045df  retn
```
