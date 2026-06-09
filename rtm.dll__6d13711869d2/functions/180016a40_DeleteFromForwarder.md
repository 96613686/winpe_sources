# DeleteFromForwarder

- ea: `0x180016a40`
- end: `0x180016cec`
- name: `DeleteFromForwarder`
- size: `684`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180014bfc`
- `0x180014d2c`
- `0x180015100`
- `0x180015178`
- `0x180016a40`
- `0x18001de20`
- `0x18001de98`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## string_xrefs

- `0x180016a9a`: `ENTERED DeleteFromForwarder, Entries %x`
- `0x180016bac`: `DeleteFromForwarder - Source Entry not found : ( %x, %x )`
- `0x180016c0a`: `DeleteFromForwarder - Group Entry not found : ( %x )`
- `0x180016cad`: `LEAVING DeleteFromForwarder\n`

## pseudocode

```c
__int64 __fastcall DeleteFromForwarder(unsigned int a1, __int64 a2)
{
  unsigned int v4; // edi
  __int64 v5; // r9
  unsigned int v6; // eax
  unsigned int v7; // edx
  __int64 v8; // r12
  __int64 GroupEntry; // rax
  unsigned int v10; // edx
  __int64 v11; // r13
  unsigned int v12; // ebx
  unsigned int v13; // edx
  __int64 SourceEntry; // rax
  unsigned int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  if ( qword_18002B8A8 )
  {
    LOWORD(v17) = 0;
    FormatRRASErrorString(&v17, L"ENTERED DeleteFromForwarder, Entries %x", a1);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v17);
  }
  v4 = 0;
  if ( !a1 )
    goto LABEL_23;
  while ( 1 )
  {
    v5 = *(unsigned int *)(a2 + 16LL * v4 + 12);
    if ( (unsigned int)v5 >= 0x21 )
      break;
    v16 = *((_DWORD *)MgmIpv4Mask + v5);
    v6 = *(_DWORD *)(a2 + 16LL * v4 + 4);
    if ( v6 )
      v7 = v6 % (dword_18002B930 - 1) + 1;
    else
      v7 = 0;
    v8 = 32LL * v7;
    AcquireReadLock((char *)qword_18002BA40 + v8 + 16);
    GroupEntry = GetGroupEntry((char *)qword_18002BA40 + v8, *(unsigned int *)(a2 + 16LL * v4 + 4));
    v11 = GroupEntry;
    if ( GroupEntry )
    {
      AcquireWriteLock(GroupEntry + 40);
      v12 = *(_DWORD *)(a2 + 16LL * v4 + 8);
      if ( v12 )
        v13 = v12 % (dword_18002B934 - 1) + 1;
      else
        v13 = 0;
      SourceEntry = GetSourceEntry(v11 + 16LL * v13 + 88, v12);
      if ( SourceEntry )
      {
        *(_DWORD *)(SourceEntry + 144) = 0;
      }
      else if ( qword_18002B8A8 )
      {
        LOWORD(v17) = 0;
        FormatRRASErrorString(&v17, L"DeleteFromForwarder - Source Entry not found : ( %x, %x )", v12, v16);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v17);
      }
      ReleaseWriteLock(v11 + 40);
    }
    else if ( qword_18002B8A8 )
    {
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v17, L"DeleteFromForwarder - Group Entry not found : ( %x )", v10);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v17);
    }
    ReleaseReadLock((char *)qword_18002BA40 + v8 + 16);
    if ( ++v4 >= a1 )
      goto LABEL_23;
  }
  if ( qword_18002B8A8 )
  {
    LOWORD(v17) = 0;
    FormatRRASErrorString(&v17, L"Failed with %x to convert IPv6 prefix %x to Mask", 87);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v17);
LABEL_23:
    if ( qword_18002B8A8 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
        gMgmEtwContext,
        qword_18002B8A8,
        L"LEAVING DeleteFromForwarder\n");
  }
  return 0;
}

```

## disassembly

```asm
0x180016a40  mov     [rsp-8+arg_10], rbx
0x180016a45  push    rbp
0x180016a46  push    rsi
0x180016a47  push    rdi
0x180016a48  push    r12
0x180016a4a  push    r13
0x180016a4c  push    r14
0x180016a4e  push    r15
0x180016a50  lea     rbp, [rsp-740h]
0x180016a58  sub     rsp, 840h
0x180016a5f  mov     rax, cs:__security_cookie
0x180016a66  xor     rax, rsp
0x180016a69  mov     [rbp+770h+var_40], rax
0x180016a70  mov     rsi, rdx
0x180016a73  mov     r14d, ecx
0x180016a76  xor     eax, eax
0x180016a78  lea     rcx, [rsp+870h+var_83C]; void *
0x180016a7d  xor     edx, edx; Val
0x180016a7f  mov     [rsp+870h+var_840], eax
0x180016a83  mov     r8d, 7FCh; Size
0x180016a89  call    memset_0
0x180016a8e  cmp     cs:qword_18002B8A8, 0
0x180016a96  jz      short loc_180016AD2
0x180016a98  xor     eax, eax
0x180016a9a  lea     rdx, aEnteredDeletef; "ENTERED DeleteFromForwarder, Entries %x"
0x180016aa1  mov     r8d, r14d
0x180016aa4  mov     word ptr [rsp+870h+var_840], ax
0x180016aa9  lea     rcx, [rsp+870h+var_840]
0x180016aae  call    FormatRRASErrorString
0x180016ab3  mov     rdx, cs:qword_18002B8A8
0x180016aba  lea     r8, [rsp+870h+var_840]
0x180016abf  mov     rcx, cs:gMgmEtwContext
0x180016ac6  mov     rax, cs:gMgmTemplateFunc
0x180016acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ad2  xor     edi, edi
0x180016ad4  test    r14d, r14d
0x180016ad7  jz      loc_180016C9A
0x180016add  mov     ebx, edi
0x180016adf  add     rbx, rbx
0x180016ae2  mov     r9d, [rsi+rbx*8+0Ch]
0x180016ae7  cmp     r9d, 21h ; '!'
0x180016aeb  jnb     loc_180016C55
0x180016af1  lea     rcx, MgmIpv4Mask
0x180016af8  mov     eax, [rcx+r9*4]
0x180016afc  mov     [rsp+870h+var_850], eax
0x180016b00  mov     eax, [rsi+rbx*8+4]
0x180016b04  test    eax, eax
0x180016b06  jz      short loc_180016B18
0x180016b08  mov     ecx, cs:dword_18002B930
0x180016b0e  xor     edx, edx
0x180016b10  dec     ecx
0x180016b12  div     ecx
0x180016b14  inc     edx
0x180016b16  jmp     short loc_180016B1A
0x180016b18  xor     edx, edx
0x180016b1a  mov     rcx, cs:qword_18002BA40
0x180016b21  mov     r12d, edx
0x180016b24  add     rcx, 10h
0x180016b28  shl     r12, 5
0x180016b2c  add     rcx, r12
0x180016b2f  call    AcquireReadLock
0x180016b34  mov     rcx, cs:qword_18002BA40
0x180016b3b  mov     edx, [rsi+rbx*8+4]
0x180016b3f  add     rcx, r12
0x180016b42  call    GetGroupEntry
0x180016b47  mov     r13, rax
0x180016b4a  test    rax, rax
0x180016b4d  jz      loc_180016BF1
0x180016b53  lea     rcx, [rax+28h]
0x180016b57  call    AcquireWriteLock
0x180016b5c  mov     ebx, [rsi+rbx*8+8]
0x180016b60  test    ebx, ebx
0x180016b62  jz      short loc_180016B76
0x180016b64  mov     ecx, cs:dword_18002B934
0x180016b6a  xor     edx, edx
0x180016b6c  dec     ecx
0x180016b6e  mov     eax, ebx
0x180016b70  div     ecx
0x180016b72  inc     edx
0x180016b74  jmp     short loc_180016B78
0x180016b76  xor     edx, edx
0x180016b78  mov     ecx, edx
0x180016b7a  mov     edx, ebx
0x180016b7c  shl     rcx, 4
0x180016b80  add     rcx, 58h ; 'X'
0x180016b84  add     rcx, r13
0x180016b87  call    GetSourceEntry
0x180016b8c  test    rax, rax
0x180016b8f  jz      short loc_180016B9D
0x180016b91  mov     dword ptr [rax+90h], 0
0x180016b9b  jmp     short loc_180016BE6
0x180016b9d  cmp     cs:qword_18002B8A8, 0
0x180016ba5  jz      short loc_180016BE6
0x180016ba7  mov     r9d, [rsp+870h+var_850]
0x180016bac  lea     rdx, aDeletefromforw_0; "DeleteFromForwarder - Source Entry not "...
0x180016bb3  xor     eax, eax
0x180016bb5  lea     rcx, [rsp+870h+var_840]
0x180016bba  mov     r8d, ebx
0x180016bbd  mov     word ptr [rsp+870h+var_840], ax
0x180016bc2  call    FormatRRASErrorString
0x180016bc7  mov     rdx, cs:qword_18002B8A8
0x180016bce  lea     r8, [rsp+870h+var_840]
0x180016bd3  mov     rcx, cs:gMgmEtwContext
0x180016bda  mov     rax, cs:gMgmTemplateFunc
0x180016be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016be6  lea     rcx, [r13+28h]
0x180016bea  call    ReleaseWriteLock
0x180016bef  jmp     short loc_180016C35
0x180016bf1  cmp     cs:qword_18002B8A8, 0
0x180016bf9  jz      short loc_180016C35
0x180016bfb  xor     eax, eax
0x180016bfd  lea     rcx, [rsp+870h+var_840]
0x180016c02  mov     r8d, edx
0x180016c05  mov     word ptr [rsp+870h+var_840], ax
0x180016c0a  lea     rdx, aDeletefromforw; "DeleteFromForwarder - Group Entry not f"...
0x180016c11  call    FormatRRASErrorString
0x180016c16  mov     rdx, cs:qword_18002B8A8
0x180016c1d  lea     r8, [rsp+870h+var_840]
0x180016c22  mov     rcx, cs:gMgmEtwContext
0x180016c29  mov     rax, cs:gMgmTemplateFunc
0x180016c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c35  mov     rcx, cs:qword_18002BA40
0x180016c3c  add     rcx, 10h
0x180016c40  add     rcx, r12
0x180016c43  call    ReleaseReadLock
0x180016c48  inc     edi
0x180016c4a  cmp     edi, r14d
0x180016c4d  jb      loc_180016ADD
0x180016c53  jmp     short loc_180016C9A
0x180016c55  cmp     cs:qword_18002B8A8, 0
0x180016c5d  jz      short loc_180016CC0
0x180016c5f  xor     eax, eax
0x180016c61  lea     rdx, aFailedWithXToC; "Failed with %x to convert IPv6 prefix %"...
0x180016c68  lea     rcx, [rsp+870h+var_840]
0x180016c6d  mov     word ptr [rsp+870h+var_840], ax
0x180016c72  lea     r8d, [rax+57h]
0x180016c76  call    FormatRRASErrorString
0x180016c7b  mov     rdx, cs:qword_18002B8A8
0x180016c82  lea     r8, [rsp+870h+var_840]
0x180016c87  mov     rcx, cs:gMgmEtwContext
0x180016c8e  mov     rax, cs:gMgmTemplateFunc
0x180016c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c9a  mov     rdx, cs:qword_18002B8A8
0x180016ca1  test    rdx, rdx
0x180016ca4  jz      short loc_180016CC0
0x180016ca6  mov     rcx, cs:gMgmEtwContext
0x180016cad  lea     r8, aLeavingDeletef; "LEAVING DeleteFromForwarder\n"
0x180016cb4  mov     rax, cs:gMgmTemplateFunc
0x180016cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cc0  xor     eax, eax
0x180016cc2  mov     rcx, [rbp+770h+var_40]
0x180016cc9  xor     rcx, rsp; StackCookie
0x180016ccc  call    __security_check_cookie
0x180016cd1  mov     rbx, [rsp+870h+arg_10]
0x180016cd9  add     rsp, 840h
0x180016ce0  pop     r15
0x180016ce2  pop     r14
0x180016ce4  pop     r13
0x180016ce6  pop     r12
0x180016ce8  pop     rdi
0x180016ce9  pop     rsi
0x180016cea  pop     rbp
0x180016ceb  retn
```
