# SXReadBase::XmlNsReset(void)

- ea: `0x100410d20`
- end: `0x100410e51`
- name: `?XmlNsReset@SXReadBase@@IEAAXXZ`
- size: `305`
- prototype: `void __fastcall(SXReadBase *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1004045a0`
- `0x100404f80`

## callees

- `0x100410810`
- `0x100410d20`
- `0x100411520`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapFree` at `0x100410d96`
- `KERNEL32!HeapFree` at `0x100410d96`

## string_xrefs

- `0x100410dd3`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c
void __fastcall SXReadBase::XmlNsReset(SXReadBase *this)
{
  int v1; // eax
  LPVOID *v3; // r9
  struct IMalloc *v4; // rcx
  bool v5; // zf
  unsigned int v6; // ecx
  _OWORD *v7; // rcx

  v1 = *((_DWORD *)this + 30);
  if ( v1 )
  {
    do
    {
      v3 = (LPVOID *)(*((_QWORD *)this + 14) + 48LL * (unsigned int)(v1 - 1));
      if ( *((int *)v3 + 7) < 0 )
        break;
      *(_DWORD *)(*((_QWORD *)this + 11) + 4LL * (unsigned int)(*((_DWORD *)v3 + 9) % *((_DWORD *)this + 21))) = *((_DWORD *)v3 + 10);
      if ( *v3 )
      {
        v4 = (struct IMalloc *)*((_QWORD *)this + 1);
        if ( v4 || (v4 = g_pMalloc) != 0 )
          ((void (__fastcall *)(struct IMalloc *, LPVOID))v4->lpVtbl->Free)(v4, *v3);
        else
          HeapFree(g_hHeap, 0, *v3);
      }
      v5 = (*((_DWORD *)this + 30))-- == 1;
      v1 = *((_DWORD *)this + 30);
    }
    while ( !v5 );
  }
  else
  {
    v6 = 0;
    if ( !*((_DWORD *)this + 31) )
    {
      _stack<SXReadBase::XmlNsDecl,10>::grow((char *)this + 96, 0);
      v6 = *((_DWORD *)this + 30);
    }
    *((_DWORD *)this + 30) = v6 + 1;
    v7 = (_OWORD *)(*((_QWORD *)this + 14) + 48LL * v6);
    *v7 = 0;
    v7[1] = 0;
    v7[2] = 0;
    SXReadBase::PushXmlns(this, L"xml", 3u, L"http://www.w3.org/XML/1998/namespace", 0x24u, 0, -1);
    SXReadBase::PushXmlns(this, &qword_10042F910, 0, &qword_10042F910, 0, 0, -1);
  }
}

```

## disassembly

```asm
0x100410d20  push    rbx
0x100410d22  sub     rsp, 40h
0x100410d26  mov     eax, [rcx+78h]
0x100410d29  mov     rbx, rcx
0x100410d2c  test    eax, eax
0x100410d2e  jz      short loc_100410DAB
0x100410d30  lea     eax, [rax-1]
0x100410d33  lea     r9, [rax+rax*2]
0x100410d37  shl     r9, 4
0x100410d3b  add     r9, [rbx+70h]
0x100410d3f  cmp     dword ptr [r9+1Ch], 0
0x100410d44  jl      loc_100410E4B
0x100410d4a  mov     eax, [r9+24h]
0x100410d4e  xor     edx, edx
0x100410d50  div     dword ptr [rbx+54h]
0x100410d53  mov     rcx, [rbx+58h]
0x100410d57  mov     eax, [r9+28h]
0x100410d5b  mov     [rcx+rdx*4], eax
0x100410d5e  mov     r8, [r9]; lpMem
0x100410d61  test    r8, r8
0x100410d64  jz      short loc_100410D9C
0x100410d66  mov     rcx, [rbx+8]
0x100410d6a  test    rcx, rcx
0x100410d6d  jnz     short loc_100410D7B
0x100410d6f  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100410d76  test    rcx, rcx
0x100410d79  jz      short loc_100410D8D
0x100410d7b  mov     rax, [rcx]
0x100410d7e  mov     rdx, r8
0x100410d81  mov     rax, [rax+28h]
0x100410d85  call    cs:__guard_dispatch_icall_fptr
0x100410d8b  jmp     short loc_100410D9C
0x100410d8d  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100410d94  xor     edx, edx; dwFlags
0x100410d96  call    cs:__imp_HeapFree
0x100410d9c  add     dword ptr [rbx+78h], 0FFFFFFFFh
0x100410da0  mov     eax, [rbx+78h]
0x100410da3  jnz     short loc_100410D30
0x100410da5  add     rsp, 40h
0x100410da9  pop     rbx
0x100410daa  retn
0x100410dab  mov     ecx, eax
0x100410dad  mov     [rsp+48h+arg_0], rdi
0x100410db2  cmp     [rbx+7Ch], eax
0x100410db5  jnz     short loc_100410DC5
0x100410db7  xor     edx, edx
0x100410db9  lea     rcx, [rbx+60h]
0x100410dbd  call    ?grow@?$_stack@UXmlNsDecl@SXReadBase@@$09@@AEAAXI@Z; _stack<SXReadBase::XmlNsDecl,10>::grow(uint)
0x100410dc2  mov     ecx, [rbx+78h]
0x100410dc5  lea     eax, [rcx+1]
0x100410dc8  mov     [rsp+48h+var_18], 0FFFFFFFFh; int
0x100410dd0  mov     [rbx+78h], eax
0x100410dd3  lea     r9, aHttpWwwW3OrgXm; "http://www.w3.org/XML/1998/namespace"
0x100410dda  mov     eax, ecx
0x100410ddc  lea     rdx, aXml; "xml"
0x100410de3  xorps   xmm0, xmm0
0x100410de6  mov     [rsp+48h+var_20], 0; bool
0x100410deb  mov     r8d, 3; unsigned int
0x100410df1  mov     [rsp+48h+var_28], 24h ; '$'; unsigned int
0x100410df9  lea     rcx, [rax+rax*2]
0x100410dfd  shl     rcx, 4
0x100410e01  add     rcx, [rbx+70h]
0x100410e05  movups  xmmword ptr [rcx], xmm0
0x100410e08  movups  xmmword ptr [rcx+10h], xmm0
0x100410e0c  movups  xmmword ptr [rcx+20h], xmm0
0x100410e10  mov     rcx, rbx; this
0x100410e13  call    ?PushXmlns@SXReadBase@@IEAAXPEB_WK0K_NH@Z; SXReadBase::PushXmlns(wchar_t const *,ulong,wchar_t const *,ulong,bool,int)
0x100410e18  mov     [rsp+48h+var_18], 0FFFFFFFFh; int
0x100410e20  lea     r9, qword_10042F910; wchar_t *
0x100410e27  mov     [rsp+48h+var_20], 0; bool
0x100410e2c  lea     rdx, qword_10042F910; wchar_t *
0x100410e33  xor     r8d, r8d; unsigned int
0x100410e36  mov     [rsp+48h+var_28], 0; unsigned int
0x100410e3e  mov     rcx, rbx; this
0x100410e41  call    ?PushXmlns@SXReadBase@@IEAAXPEB_WK0K_NH@Z; SXReadBase::PushXmlns(wchar_t const *,ulong,wchar_t const *,ulong,bool,int)
0x100410e46  mov     rdi, [rsp+48h+arg_0]
0x100410e4b  add     rsp, 40h
0x100410e4f  pop     rbx
0x100410e50  retn
```
