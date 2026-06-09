# CreateCachedSslProv(CACHED_SSL_PROVIDER *,ushort const *)

- ea: `0x180041840`
- end: `0x180041952`
- name: `?CreateCachedSslProv@@YAJPEAUCACHED_SSL_PROVIDER@@PEBG@Z`
- size: `274`
- prototype: `int(struct CACHED_SSL_PROVIDER *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180026310`

## callees

- `0x180021e64`
- `0x180041840`
- `0x18005a148`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800418a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800418a9`
- `ncrypt!SslOpenProvider` at `0x180041874`
- `ncrypt!SslOpenProvider` at `0x180041874`
- `ncrypt!SslFreeObject` at `0x180041928`
- `ncrypt!SslFreeObject` at `0x180041928`

## pseudocode

```c
__int64 __fastcall CreateCachedSslProv(struct CACHED_SSL_PROVIDER *a1, const unsigned __int16 *a2)
{
  unsigned int v4; // ebp
  __int64 v5; // rdx
  rsize_t v7; // rsi
  wchar_t *v8; // rax
  wchar_t *v9; // rdi
  int v11; // eax
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  v12 = 0;
  v4 = SslOpenProvider(&v12, a2, (unsigned int)dword_1800AE78C);
  if ( !v4 )
  {
    v5 = -1;
    while ( a2[++v5] != 0 )
      ;
    v7 = v5 + 1;
    v8 = (wchar_t *)LocalAlloc(0x40u, 2 * (v5 + 1));
    v9 = v8;
    if ( v8 )
    {
      wcscpy_s(v8, v7, a2);
      *(_QWORD *)a1 = v12;
      *((_QWORD *)a1 + 1) = v9;
      v12 = 0;
      goto LABEL_6;
    }
    v4 = -2146893056;
  }
  if ( v12 )
    SslFreeObject(v12, 0);
LABEL_6:
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control )
  {
    if ( (v11 = *((_DWORD *)WPP_GLOBAL_Control + 7), (v11 & 1) != 0) && v4 || (v11 & 4) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_eb5149e4312e3fc6c7b47b99acf2d5dc_Traceguids, v4, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180041840  mov     rax, rsp
0x180041843  push    rbp
0x180041844  sub     rsp, 40h
0x180041848  mov     r8d, cs:dword_1800AE78C
0x18004184f  mov     [rax+8], rbx
0x180041853  mov     rbx, rdx
0x180041856  mov     [rax+10h], rsi
0x18004185a  mov     [rax+20h], rdi
0x18004185e  mov     [rax-10h], r14
0x180041862  mov     r14, rcx
0x180041865  mov     [rax-18h], r15
0x180041869  lea     rcx, [rax+18h]
0x18004186d  xor     r15d, r15d
0x180041870  mov     [rax+18h], r15
0x180041874  call    cs:__imp_SslOpenProvider
0x18004187a  mov     ebp, eax
0x18004187c  test    eax, eax
0x18004187e  jnz     loc_18004191C
0x180041884  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18004188b  nop     dword ptr [rax+rax+00h]
0x180041890  cmp     [rbx+rdx*2+2], r15w
0x180041896  lea     rdx, [rdx+1]
0x18004189a  jnz     short loc_180041890
0x18004189c  lea     rsi, [rdx+1]
0x1800418a0  mov     ecx, 40h ; '@'; uFlags
0x1800418a5  lea     rdx, [rsi+rsi]; uBytes
0x1800418a9  call    cs:__imp_LocalAlloc
0x1800418af  mov     rdi, rax
0x1800418b2  test    rax, rax
0x1800418b5  jz      short loc_180041917
0x1800418b7  mov     r8, rbx; Source
0x1800418ba  mov     rdx, rsi; SizeInWords
0x1800418bd  mov     rcx, rax; Destination
0x1800418c0  call    wcscpy_s
0x1800418c5  mov     rax, [rsp+48h+arg_10]
0x1800418ca  mov     [r14], rax
0x1800418cd  mov     [r14+8], rdi
0x1800418d1  mov     [rsp+48h+arg_10], r15
0x1800418d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800418dd  lea     rax, WPP_GLOBAL_Control
0x1800418e4  mov     r15, [rsp+48h+var_18]
0x1800418e9  mov     r14, [rsp+48h+var_10]
0x1800418ee  mov     rdi, [rsp+48h+arg_18]
0x1800418f3  mov     rsi, [rsp+48h+arg_8]
0x1800418f8  mov     rbx, [rsp+48h+arg_0]
0x1800418fd  cmp     rcx, rax
0x180041900  jnz     short loc_18004190A
0x180041902  mov     eax, ebp
0x180041904  add     rsp, 40h
0x180041908  pop     rbp
0x180041909  retn
0x18004190a  mov     eax, [rcx+1Ch]
0x18004190d  test    al, 1
0x18004190f  jnz     short loc_180041930
0x180041911  test    al, 4
0x180041913  jz      short loc_180041902
0x180041915  jmp     short loc_180041934
0x180041917  mov     ebp, 80090300h
0x18004191c  mov     rcx, [rsp+48h+arg_10]
0x180041921  test    rcx, rcx
0x180041924  jz      short loc_1800418D6
0x180041926  xor     edx, edx
0x180041928  call    cs:__imp_SslFreeObject
0x18004192e  jmp     short loc_1800418D6
0x180041930  test    ebp, ebp
0x180041932  jz      short loc_180041911
0x180041934  mov     rcx, [rcx+10h]
0x180041938  lea     r8, WPP_eb5149e4312e3fc6c7b47b99acf2d5dc_Traceguids
0x18004193f  mov     edx, 0Eh
0x180041944  mov     [rsp+48h+var_28], ebp
0x180041948  mov     r9d, ebp
0x18004194b  call    WPP_SF_dd
0x180041950  jmp     short loc_180041902
```
