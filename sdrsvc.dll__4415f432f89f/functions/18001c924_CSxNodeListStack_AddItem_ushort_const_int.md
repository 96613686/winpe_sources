# CSxNodeListStack::AddItem(ushort const *,int)

- ea: `0x18001c924`
- end: `0x18001cb34`
- name: `?AddItem@CSxNodeListStack@@QEAAJPEBGH@Z`
- size: `528`
- prototype: `__int64 __fastcall(CSxNodeListStack **this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001d4dc`

## callees

- `0x180001554`
- `0x180001578`
- `0x18000ea0c`
- `0x18001586c`
- `0x180015974`
- `0x18001c8b4`
- `0x18001c924`
- `0x18001f624`
- `0x180020488`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ca6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ca6d`

## pseudocode

```c
__int64 __fastcall CSxNodeListStack::AddItem(CSxNodeListStack **this, const unsigned __int16 *a2, int a3)
{
  char *v6; // r14
  __int16 v7; // ax
  int v8; // esi
  _BYTE *v9; // rax
  void *v10; // rdi
  _WORD *v11; // rcx
  __int16 v12; // ax
  __int64 v13; // rbx
  CSxNodeListStack *v14; // rbx
  _QWORD *v15; // rax
  _QWORD *v16; // rdx
  int v18; // [rsp+20h] [rbp-48h] BYREF
  __int16 v19; // [rsp+24h] [rbp-44h]
  __int16 v20; // [rsp+26h] [rbp-42h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v18, "CSxNodeListStack::AddItem", 1507, 1);
  v6 = (char *)(this + 3);
  v7 = 1512;
  if ( this[1] == (CSxNodeListStack *)(this + 3) )
  {
    v8 = -2147418113;
LABEL_26:
    v20 = v7;
    v18 = v8;
    goto LABEL_27;
  }
  v18 = 0;
  v19 = 1512;
  v9 = operator new(0x18u);
  v10 = v9;
  if ( !v9 )
  {
    v8 = -2147024882;
    v7 = 1514;
    goto LABEL_26;
  }
  v9[20] &= 0xFCu;
  *(_QWORD *)v9 = qword_180028260;
  *((_QWORD *)v9 + 1) = 0;
  *((_DWORD *)v9 + 4) = 1;
  v18 = 0;
  v19 = 1514;
  if ( *((_DWORD *)v9 + 2) )
  {
    v11 = *(_WORD **)v9;
    *((_DWORD *)v9 + 2) = 0;
    *v11 = 0;
  }
  v8 = CBsString::Append((CBsString *)v9, a2);
  v18 = v8;
  v12 = 1515;
  if ( v8 >= 0 )
  {
    v19 = 1515;
    *((_BYTE *)v10 + 20) &= ~2u;
    *((_BYTE *)v10 + 20) |= a3 != 0 ? 2 : 0;
    v14 = this[1];
    if ( v14 == (CSxNodeListStack *)v6 )
    {
      v13 = 0;
      v18 = 1;
    }
    else
    {
      v13 = *((_QWORD *)v14 + 2);
      _InterlockedIncrement((volatile signed __int32 *)(v13 + 40));
      v18 = 0;
    }
    v19 = 1518;
    v15 = CoTaskMemAlloc(0x18u);
    if ( v15 )
    {
      v15[2] = v10;
      _InterlockedIncrement((volatile signed __int32 *)v10 + 4);
      v16 = *(_QWORD **)(v13 + 32);
      if ( *v16 != v13 + 24 )
        __fastfail(3u);
      *v15 = v13 + 24;
      v15[1] = v16;
      *v16 = v15;
      *(_QWORD *)(v13 + 32) = v15;
      _InterlockedIncrement((volatile signed __int32 *)v13);
      v18 = 0;
      v19 = 1519;
      v8 = 0;
      goto LABEL_20;
    }
    v8 = -2147024882;
    v12 = 1519;
    v18 = -2147024882;
  }
  else
  {
    v13 = 0;
  }
  v20 = v12;
LABEL_20:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 4, 0xFFFFFFFF) == 1 )
  {
    CBsString::_Release((LPVOID *)v10);
    operator delete(v10);
  }
  if ( v13 && _InterlockedExchangeAdd((volatile signed __int32 *)(v13 + 40), 0xFFFFFFFF) == 1 )
  {
    CSxNodeList::~CSxNodeList((CSxNodeList *)v13);
    operator delete((void *)v13);
  }
LABEL_27:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001c924  push    rbp
0x18001c926  push    rbx
0x18001c927  push    rsi
0x18001c928  push    rdi
0x18001c929  push    r14
0x18001c92b  push    r15
0x18001c92d  mov     rbp, rsp
0x18001c930  sub     rsp, 68h
0x18001c934  mov     r15d, r8d
0x18001c937  mov     rsi, rdx
0x18001c93a  mov     rbx, rcx
0x18001c93d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c944  lea     rax, WPP_GLOBAL_Control
0x18001c94b  cmp     rcx, rax
0x18001c94e  jz      short loc_18001C96E
0x18001c950  test    dword ptr [rcx+1Ch], 20000000h
0x18001c957  jz      short loc_18001C96E
0x18001c959  mov     rcx, [rcx+10h]
0x18001c95d  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18001c964  mov     edx, 2Fh ; '/'
0x18001c969  call    WPP_SF_
0x18001c96e  mov     r9d, 1; unsigned __int16
0x18001c974  lea     rdx, aCsxnodeliststa_2; "CSxNodeListStack::AddItem"
0x18001c97b  mov     r8d, 5E3h; unsigned __int16
0x18001c981  lea     rcx, [rbp+var_48]; this
0x18001c985  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001c98a  lea     r14, [rbx+18h]
0x18001c98e  mov     eax, 5E8h
0x18001c993  cmp     [rbx+8], r14
0x18001c997  jnz     short loc_18001C9A3
0x18001c999  mov     esi, 8000FFFFh
0x18001c99e  jmp     loc_18001CB15
0x18001c9a3  mov     ecx, 18h; Size
0x18001c9a8  mov     [rbp+var_48], 0
0x18001c9af  mov     [rbp+var_44], ax
0x18001c9b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c9b8  mov     rdi, rax
0x18001c9bb  test    rax, rax
0x18001c9be  jz      loc_18001CB0B
0x18001c9c4  and     byte ptr [rdi+14h], 0FCh
0x18001c9c8  lea     rax, qword_180028260
0x18001c9cf  mov     [rdi], rax
0x18001c9d2  mov     qword ptr [rdi+8], 0
0x18001c9da  mov     dword ptr [rdi+10h], 1
0x18001c9e1  mov     eax, 5EAh
0x18001c9e6  mov     [rbp+var_48], 0
0x18001c9ed  mov     [rbp+var_44], ax
0x18001c9f1  cmp     dword ptr [rdi+8], 0
0x18001c9f5  jz      short loc_18001CA06
0x18001c9f7  mov     rcx, [rdi]
0x18001c9fa  xor     eax, eax
0x18001c9fc  mov     dword ptr [rdi+8], 0
0x18001ca03  mov     [rcx], ax
0x18001ca06  mov     rdx, rsi; unsigned __int16 *
0x18001ca09  mov     rcx, rdi; this
0x18001ca0c  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18001ca11  mov     esi, eax
0x18001ca13  mov     [rbp+var_48], eax
0x18001ca16  test    eax, eax
0x18001ca18  mov     eax, 5EBh
0x18001ca1d  jns     short loc_18001CA2A
0x18001ca1f  xor     ebx, ebx
0x18001ca21  mov     [rbp+var_42], ax
0x18001ca25  jmp     loc_18001CAC6
0x18001ca2a  mov     [rbp+var_44], ax
0x18001ca2e  and     byte ptr [rdi+14h], 0FDh
0x18001ca32  neg     r15d
0x18001ca35  sbb     al, al
0x18001ca37  and     al, 2
0x18001ca39  or      [rdi+14h], al
0x18001ca3c  mov     rbx, [rbx+8]
0x18001ca40  cmp     rbx, r14
0x18001ca43  jnz     short loc_18001CA50
0x18001ca45  xor     ebx, ebx
0x18001ca47  mov     [rbp+var_48], 1
0x18001ca4e  jmp     short loc_18001CA5F
0x18001ca50  mov     rbx, [rbx+10h]
0x18001ca54  lock inc dword ptr [rbx+28h]
0x18001ca58  mov     [rbp+var_48], 0
0x18001ca5f  mov     eax, 5EEh
0x18001ca64  mov     ecx, 18h; cb
0x18001ca69  mov     [rbp+var_44], ax
0x18001ca6d  call    cs:__imp_CoTaskMemAlloc
0x18001ca73  test    rax, rax
0x18001ca76  jnz     short loc_18001CA87
0x18001ca78  mov     esi, 8007000Eh
0x18001ca7d  mov     eax, 5EFh
0x18001ca82  mov     [rbp+var_48], esi
0x18001ca85  jmp     short loc_18001CA21
0x18001ca87  mov     [rax+10h], rdi
0x18001ca8b  lock inc dword ptr [rdi+10h]
0x18001ca8f  lea     rcx, [rbx+18h]
0x18001ca93  mov     rdx, [rcx+8]
0x18001ca97  cmp     [rdx], rcx
0x18001ca9a  jz      short loc_18001CAA3
0x18001ca9c  mov     ecx, 3
0x18001caa1  int     29h; Win8: RtlFailFast(ecx)
0x18001caa3  mov     [rax], rcx
0x18001caa6  mov     [rax+8], rdx
0x18001caaa  mov     [rdx], rax
0x18001caad  mov     [rcx+8], rax
0x18001cab1  lock inc dword ptr [rbx]
0x18001cab4  mov     eax, 5EFh
0x18001cab9  mov     [rbp+var_48], 0
0x18001cac0  mov     [rbp+var_44], ax
0x18001cac4  xor     esi, esi
0x18001cac6  or      r14d, 0FFFFFFFFh
0x18001caca  mov     eax, r14d
0x18001cacd  lock xadd [rdi+10h], eax
0x18001cad2  add     eax, r14d
0x18001cad5  jnz     short loc_18001CAE7
0x18001cad7  mov     rcx, rdi; this
0x18001cada  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001cadf  mov     rcx, rdi; Block
0x18001cae2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cae7  test    rbx, rbx
0x18001caea  jz      short loc_18001CB1C
0x18001caec  mov     eax, r14d
0x18001caef  lock xadd [rbx+28h], eax
0x18001caf4  add     eax, r14d
0x18001caf7  jnz     short loc_18001CB1C
0x18001caf9  mov     rcx, rbx; this
0x18001cafc  call    ??1CSxNodeList@@AEAA@XZ; CSxNodeList::~CSxNodeList(void)
0x18001cb01  mov     rcx, rbx; Block
0x18001cb04  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cb09  jmp     short loc_18001CB1C
0x18001cb0b  mov     esi, 8007000Eh
0x18001cb10  mov     eax, 5EAh
0x18001cb15  mov     [rbp+var_42], ax
0x18001cb19  mov     [rbp+var_48], esi
0x18001cb1c  lea     rcx, [rbp+var_48]; this
0x18001cb20  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001cb25  mov     eax, esi
0x18001cb27  add     rsp, 68h
0x18001cb2b  pop     r15
0x18001cb2d  pop     r14
0x18001cb2f  pop     rdi
0x18001cb30  pop     rsi
0x18001cb31  pop     rbx
0x18001cb32  pop     rbp
0x18001cb33  retn
```
