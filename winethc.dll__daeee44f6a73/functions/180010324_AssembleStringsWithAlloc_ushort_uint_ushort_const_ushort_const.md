# AssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *)

- ea: `0x180010324`
- end: `0x18001044a`
- name: `?AssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1@Z`
- size: `294`
- prototype: `int(unsigned __int16 **, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005b30`
- `0x180007800`
- `0x180008ec0`
- `0x18000a22c`

## callees

- `0x18000caac`
- `0x180010324`
- `0x1800107dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010399`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010399`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800103d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800103e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800103f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001040e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010422`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800103d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800103e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800103f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001040e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010422`

## pseudocode

```c
__int64 __fastcall AssembleStringsWithAlloc(
        unsigned __int16 **a1,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v4; // rbp
  unsigned __int16 *v8; // rsi
  unsigned __int16 *v9; // rdi
  int StringWithAlloc; // eax
  int v11; // ebx
  int v12; // eax
  unsigned __int16 *v13; // rax
  LPVOID pv; // [rsp+70h] [rbp+18h] BYREF
  unsigned __int16 *v16; // [rsp+78h] [rbp+20h] BYREF

  v4 = 0;
  pv = a3;
  v16 = a4;
  v8 = a3;
  v9 = a4;
  if ( (unsigned __int64)a3 < 0x10000 )
  {
    StringWithAlloc = LoadStringWithAlloc((unsigned __int16)a3, (unsigned __int16 **)&pv, (unsigned int)a3);
    v8 = (unsigned __int16 *)pv;
    v11 = StringWithAlloc;
    if ( StringWithAlloc < 0 )
      goto LABEL_9;
  }
  if ( (unsigned __int64)a4 < 0x10000 )
  {
    v12 = LoadStringWithAlloc((unsigned __int16)a4, &v16, (unsigned int)a3);
    v9 = v16;
    v11 = v12;
    if ( v12 < 0 )
      goto LABEL_8;
  }
  v13 = (unsigned __int16 *)CoTaskMemAlloc(0x800u);
  v4 = v13;
  if ( !v13 )
  {
    v11 = -2147024882;
    goto LABEL_8;
  }
  v11 = StringCchPrintfW(v13, 0x400u, v8, v9);
  if ( v11 < 0 )
  {
LABEL_8:
    if ( (unsigned __int64)a3 >= 0x10000 )
    {
LABEL_10:
      if ( (unsigned __int64)a4 < 0x10000 )
        CoTaskMemFree(v9);
      CoTaskMemFree(v4);
      return (unsigned int)v11;
    }
LABEL_9:
    CoTaskMemFree(v8);
    goto LABEL_10;
  }
  if ( (unsigned __int64)a3 < 0x10000 )
    CoTaskMemFree(v8);
  if ( (unsigned __int64)a4 < 0x10000 )
    CoTaskMemFree(v9);
  *a1 = v4;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180010324  mov     rax, rsp
0x180010327  mov     [rax+8], rbx
0x18001032b  push    rbp
0x18001032c  push    rsi
0x18001032d  push    rdi
0x18001032e  push    r12
0x180010330  push    r13
0x180010332  push    r14
0x180010334  push    r15
0x180010336  sub     rsp, 20h
0x18001033a  xor     ebp, ebp
0x18001033c  mov     [rax+18h], r8
0x180010340  mov     r13d, 10000h
0x180010346  mov     [rax+20h], r9
0x18001034a  mov     r14, r9
0x18001034d  mov     r15, r8
0x180010350  mov     r12, rcx
0x180010353  mov     rsi, r8
0x180010356  mov     rdi, r9
0x180010359  cmp     r8, r13
0x18001035c  jnb     short loc_180010376
0x18001035e  movzx   ecx, r15w; uID
0x180010362  lea     rdx, [rax+18h]; unsigned __int16 **
0x180010366  call    ?LoadStringWithAlloc@@YAJIPEAPEAGI@Z; LoadStringWithAlloc(uint,ushort * *,uint)
0x18001036b  mov     rsi, [rsp+58h+pv]
0x180010370  mov     ebx, eax
0x180010372  test    eax, eax
0x180010374  js      short loc_1800103D2
0x180010376  cmp     r14, r13
0x180010379  jnb     short loc_180010394
0x18001037b  movzx   ecx, r14w; uID
0x18001037f  lea     rdx, [rsp+58h+arg_18]; unsigned __int16 **
0x180010384  call    ?LoadStringWithAlloc@@YAJIPEAPEAGI@Z; LoadStringWithAlloc(uint,ushort * *,uint)
0x180010389  mov     rdi, [rsp+58h+arg_18]
0x18001038e  mov     ebx, eax
0x180010390  test    eax, eax
0x180010392  js      short loc_1800103CD
0x180010394  mov     ecx, 800h; cb
0x180010399  call    cs:__imp_CoTaskMemAlloc
0x1800103a0  nop     dword ptr [rax+rax+00h]
0x1800103a5  mov     rbp, rax
0x1800103a8  test    rax, rax
0x1800103ab  jnz     short loc_1800103B4
0x1800103ad  mov     ebx, 8007000Eh
0x1800103b2  jmp     short loc_1800103CD
0x1800103b4  mov     r9, rdi
0x1800103b7  mov     r8, rsi; unsigned __int16 *
0x1800103ba  mov     edx, 400h; unsigned __int64
0x1800103bf  mov     rcx, rbp; unsigned __int16 *
0x1800103c2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800103c7  mov     ebx, eax
0x1800103c9  test    eax, eax
0x1800103cb  jns     short loc_180010406
0x1800103cd  cmp     r15, r13
0x1800103d0  jnb     short loc_1800103E1
0x1800103d2  mov     rcx, rsi; pv
0x1800103d5  call    cs:__imp_CoTaskMemFree
0x1800103dc  nop     dword ptr [rax+rax+00h]
0x1800103e1  cmp     r14, r13
0x1800103e4  jnb     short loc_1800103F5
0x1800103e6  mov     rcx, rdi; pv
0x1800103e9  call    cs:__imp_CoTaskMemFree
0x1800103f0  nop     dword ptr [rax+rax+00h]
0x1800103f5  mov     rcx, rbp; pv
0x1800103f8  call    cs:__imp_CoTaskMemFree
0x1800103ff  nop     dword ptr [rax+rax+00h]
0x180010404  jmp     short loc_180010432
0x180010406  cmp     r15, r13
0x180010409  jnb     short loc_18001041A
0x18001040b  mov     rcx, rsi; pv
0x18001040e  call    cs:__imp_CoTaskMemFree
0x180010415  nop     dword ptr [rax+rax+00h]
0x18001041a  cmp     r14, r13
0x18001041d  jnb     short loc_18001042E
0x18001041f  mov     rcx, rdi; pv
0x180010422  call    cs:__imp_CoTaskMemFree
0x180010429  nop     dword ptr [rax+rax+00h]
0x18001042e  mov     [r12], rbp
0x180010432  mov     eax, ebx
0x180010434  mov     rbx, [rsp+58h+arg_0]
0x180010439  add     rsp, 20h
0x18001043d  pop     r15
0x18001043f  pop     r14
0x180010441  pop     r13
0x180010443  pop     r12
0x180010445  pop     rdi
0x180010446  pop     rsi
0x180010447  pop     rbp
0x180010448  retn
```
