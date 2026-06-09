# CEngineLocaleHandlerJPN::WordBreakerEngineFormat(ushort const *,long,__MIDL___MIDL_itf_msasrloc_base_0000_0000_0003 *)

- ea: `0x1800dc8b8`
- end: `0x1800dca47`
- name: `?WordBreakerEngineFormat@CEngineLocaleHandlerJPN@@QEAAJPEBGJPEAU__MIDL___MIDL_itf_msasrloc_base_0000_0000_0003@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(CEngineLocaleHandlerJPN *__hidden this, const unsigned __int16 *, int, struct __MIDL___MIDL_itf_msasrloc_base_0000_0000_0003 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800db098`

## callees

- `0x1800034b0`
- `0x180004312`
- `0x1800c77ac`
- `0x1800c77d8`
- `0x1800cf094`
- `0x1800dc8b8`
- `0x1800e06a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dc99a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dc99a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEngineLocaleHandlerJPN::WordBreakerEngineFormat(
        CEngineLocaleHandlerJPN *this,
        const unsigned __int16 *a2,
        int a3,
        struct __MIDL___MIDL_itf_msasrloc_base_0000_0000_0003 *a4)
{
  unsigned __int64 v5; // rsi
  __int16 v6; // cx
  _WORD *v7; // r10
  int v8; // ebx
  _WORD *v9; // rax
  _WORD *v10; // rax
  void *v11; // rdx
  _BYTE v13[16]; // [rsp+30h] [rbp-D8h] BYREF
  _BYTE v14[48]; // [rsp+40h] [rbp-C8h] BYREF
  void **v15; // [rsp+70h] [rbp-98h] BYREF
  void *Src; // [rsp+78h] [rbp-90h]
  unsigned int v17; // [rsp+80h] [rbp-88h]
  __int16 v18; // [rsp+88h] [rbp-80h] BYREF

  v17 = 0x80000000;
  Src = &v18;
  v5 = a3;
  v18 = 0;
  v15 = &CQuickStringW<32>::`vftable';
  if ( a3 <= 0 || CEngineLocaleHandler::IsWhiteChar(a2[a3 - 1]) )
  {
    v8 = -2147024809;
  }
  else if ( *v7 == 47
         && (int)v5 >= 5
         && v6 == 59
         && (v8 = CQuickStringTBase::Append((CQuickStringTBase *)&v15, v7, v5, 0x20u), v8 >= 0)
         && (unsigned int)CWordParserJPN::Extract(v13, Src, v14) == 3 )
  {
    v9 = CoTaskMemAlloc(((2 * v5 + 9) & 0xFFFFFFFFFFFFFFF8uLL) + 32);
    if ( v9 )
    {
      *((_QWORD *)a4 + 5) = v9;
      *((_QWORD *)a4 + 3) = v9;
      *(_DWORD *)a4 = 1;
      *v9 = 0;
      v10 = v9 + 4;
      *((_QWORD *)a4 + 2) = v10;
      *(_QWORD *)v10 = v10 + 12;
      *((_QWORD *)a4 + 4) = v10 + 4;
      *((_DWORD *)v10 + 2) = 0;
      *(_WORD *)(*((_QWORD *)a4 + 4) + 4LL) = v5;
      *(_DWORD *)(*((_QWORD *)a4 + 4) + 8LL) = 0;
      v11 = Src;
      *((_QWORD *)a4 + 1) = v10 + 12;
      memcpy_0(v10 + 12, v11, 2 * v5 + 2);
      *(_WORD *)(*((_QWORD *)a4 + 1) + 2 * v5) = 0;
    }
    else
    {
      v8 = -2147024882;
    }
  }
  else
  {
    v8 = 1;
  }
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v15);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800dc8b8  mov     r11, rsp
0x1800dc8bb  push    rbx
0x1800dc8bc  push    rbp
0x1800dc8bd  push    rsi
0x1800dc8be  push    rdi
0x1800dc8bf  push    r14
0x1800dc8c1  sub     rsp, 0E0h
0x1800dc8c8  mov     rax, cs:__security_cookie
0x1800dc8cf  xor     rax, rsp
0x1800dc8d2  mov     [rsp+108h+var_38], rax
0x1800dc8da  lea     rax, [r11-80h]
0x1800dc8de  mov     [rsp+108h+var_88], 80000000h
0x1800dc8e9  mov     [rsp+108h+Src], rax
0x1800dc8ee  mov     r14, r9
0x1800dc8f1  xor     eax, eax
0x1800dc8f3  movsxd  rsi, r8d
0x1800dc8f6  mov     [r11-80h], ax
0x1800dc8fb  lea     rax, ??_7?$CQuickStringW@$0CA@@@6B@; const CQuickStringW<32>::`vftable'
0x1800dc902  mov     [rsp+108h+var_98], rax
0x1800dc907  mov     r10, rdx
0x1800dc90a  test    r8d, r8d
0x1800dc90d  jle     loc_1800DCA18
0x1800dc913  movzx   ecx, word ptr [rdx+rsi*2-2]; unsigned __int16
0x1800dc918  call    ?IsWhiteChar@CEngineLocaleHandler@@KA_NG@Z; CEngineLocaleHandler::IsWhiteChar(ushort)
0x1800dc91d  test    al, al
0x1800dc91f  jnz     loc_1800DCA18
0x1800dc925  mov     eax, 2Fh ; '/'
0x1800dc92a  cmp     ax, [r10]
0x1800dc92e  jnz     loc_1800DCA11
0x1800dc934  cmp     esi, 5
0x1800dc937  jl      loc_1800DCA11
0x1800dc93d  mov     eax, 3Bh ; ';'
0x1800dc942  cmp     ax, cx
0x1800dc945  jnz     loc_1800DCA11
0x1800dc94b  lea     r9d, [rax-1Bh]; unsigned int
0x1800dc94f  mov     r8, rsi; unsigned __int64
0x1800dc952  mov     rdx, r10; void *
0x1800dc955  lea     rcx, [rsp+108h+var_98]; this
0x1800dc95a  call    ?Append@CQuickStringTBase@@IEAAJPEAX_KI1@Z; CQuickStringTBase::Append(void *,unsigned __int64,uint,unsigned __int64)
0x1800dc95f  mov     ebx, eax
0x1800dc961  test    eax, eax
0x1800dc963  js      loc_1800DCA11
0x1800dc969  mov     rdx, [rsp+108h+Src]
0x1800dc96e  lea     r8, [rsp+108h+var_C8]
0x1800dc973  lea     rcx, [rsp+108h+var_D8]
0x1800dc978  call    ?Extract@CWordParserJPN@@UEAA?AW4tagWordFormat@@PEBGPEAUWordFeatures_t@@@Z; CWordParserJPN::Extract(ushort const *,WordFeatures_t *)
0x1800dc97d  cmp     eax, 3
0x1800dc980  jnz     loc_1800DCA11
0x1800dc986  lea     rbp, ds:2[rsi*2]
0x1800dc98e  lea     rcx, [rbp+7]
0x1800dc992  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800dc996  add     rcx, 20h ; ' '; cb
0x1800dc99a  call    cs:__imp_CoTaskMemAlloc
0x1800dc9a0  test    rax, rax
0x1800dc9a3  jz      short loc_1800DCA0A
0x1800dc9a5  mov     [r14+28h], rax
0x1800dc9a9  xor     ecx, ecx
0x1800dc9ab  mov     [r14+18h], rax
0x1800dc9af  mov     r8, rbp; Size
0x1800dc9b2  mov     dword ptr [r14], 1
0x1800dc9b9  mov     [rax], cx
0x1800dc9bc  add     rax, 8
0x1800dc9c0  mov     [r14+10h], rax
0x1800dc9c4  lea     rcx, [rax+18h]
0x1800dc9c8  mov     [rax], rcx
0x1800dc9cb  lea     rcx, [rax+8]
0x1800dc9cf  mov     [r14+20h], rcx
0x1800dc9d3  mov     dword ptr [rcx], 0
0x1800dc9d9  add     rcx, 10h; void *
0x1800dc9dd  mov     rax, [r14+20h]
0x1800dc9e1  mov     [rax+4], si
0x1800dc9e5  mov     rax, [r14+20h]
0x1800dc9e9  mov     dword ptr [rax+8], 0
0x1800dc9f0  mov     rdx, [rsp+108h+Src]; Src
0x1800dc9f5  mov     [r14+8], rcx
0x1800dc9f9  call    memcpy_0
0x1800dc9fe  mov     rcx, [r14+8]
0x1800dca02  xor     eax, eax
0x1800dca04  mov     [rcx+rsi*2], ax
0x1800dca08  jmp     short loc_1800DCA1D
0x1800dca0a  mov     ebx, 8007000Eh
0x1800dca0f  jmp     short loc_1800DCA1D
0x1800dca11  mov     ebx, 1
0x1800dca16  jmp     short loc_1800DCA1D
0x1800dca18  mov     ebx, 80070057h
0x1800dca1d  lea     rcx, [rsp+108h+var_98]; this
0x1800dca22  call    ??1CQuickStringTBase@@MEAA@XZ; CQuickStringTBase::~CQuickStringTBase(void)
0x1800dca27  mov     eax, ebx
0x1800dca29  mov     rcx, [rsp+108h+var_38]
0x1800dca31  xor     rcx, rsp; StackCookie
0x1800dca34  call    __security_check_cookie
0x1800dca39  add     rsp, 0E0h
0x1800dca40  pop     r14
0x1800dca42  pop     rdi
0x1800dca43  pop     rsi
0x1800dca44  pop     rbp
0x1800dca45  pop     rbx
0x1800dca46  retn
```
