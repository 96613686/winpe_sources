# CSxNodeListStack::Push(void)

- ea: `0x18001cc0c`
- end: `0x18001cd63`
- name: `?Push@CSxNodeListStack@@QEAAJXZ`
- size: `343`
- prototype: `__int64 __fastcall(CSxNodeListStack *__hidden this)`
- caller_count: `1`
- callee_count: `7`
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
- `0x18001cc0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ccb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ccb7`

## pseudocode

```c
__int64 __fastcall CSxNodeListStack::Push(CSxNodeListStack *this)
{
  char *v2; // rax
  volatile signed __int32 *v3; // rbx
  _QWORD *v4; // rcx
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  volatile signed __int32 *v7; // rcx
  unsigned int v8; // edi
  _QWORD *v9; // rdx
  __int64 v10; // r8
  int v12; // [rsp+20h] [rbp-48h] BYREF
  __int16 v13; // [rsp+24h] [rbp-44h]
  __int16 v14; // [rsp+26h] [rbp-42h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "CSxNodeListStack::Push", 1417, 1);
  v2 = (char *)operator new(0x30u);
  v3 = (volatile signed __int32 *)v2;
  if ( v2 )
  {
    v4 = v2 + 8;
    v5 = v2 + 24;
    *v5 = v4;
    v5[1] = v4;
    v4[1] = v5;
    *v4 = v5;
    *v3 = 1;
    *((_DWORD *)v3 + 10) = 1;
    v12 = 0;
    v13 = 1421;
    v6 = CoTaskMemAlloc(0x18u);
    v7 = v3 + 10;
    if ( v6 )
    {
      v6[2] = v3;
      _InterlockedIncrement(v7);
      v9 = (_QWORD *)((char *)this + 8);
      v10 = *((_QWORD *)this + 1);
      if ( *(CSxNodeListStack **)(v10 + 8) != (CSxNodeListStack *)((char *)this + 8) )
        __fastfail(3u);
      *v6 = v10;
      v6[1] = v9;
      *(_QWORD *)(v10 + 8) = v6;
      *v9 = v6;
      _InterlockedIncrement((volatile signed __int32 *)this);
      v12 = 0;
      v13 = 1422;
      v8 = 0;
    }
    else
    {
      v8 = -2147024882;
      v12 = -2147024882;
      v14 = 1422;
    }
    if ( _InterlockedExchangeAdd(v7, 0xFFFFFFFF) == 1 )
    {
      CSxNodeList::~CSxNodeList((CSxNodeList *)v3);
      operator delete((void *)v3);
    }
  }
  else
  {
    v8 = -2147024882;
    v12 = -2147024882;
    v14 = 1421;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return v8;
}

```

## disassembly

```asm
0x18001cc0c  mov     [rsp+arg_0], rbx
0x18001cc11  push    rdi
0x18001cc12  sub     rsp, 60h
0x18001cc16  mov     rdi, rcx
0x18001cc19  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc20  lea     rax, WPP_GLOBAL_Control
0x18001cc27  cmp     rcx, rax
0x18001cc2a  jz      short loc_18001CC4A
0x18001cc2c  test    dword ptr [rcx+1Ch], 20000000h
0x18001cc33  jz      short loc_18001CC4A
0x18001cc35  mov     rcx, [rcx+10h]
0x18001cc39  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18001cc40  mov     edx, 2Bh ; '+'
0x18001cc45  call    WPP_SF_
0x18001cc4a  mov     r9d, 1; unsigned __int16
0x18001cc50  lea     rdx, aCsxnodeliststa; "CSxNodeListStack::Push"
0x18001cc57  mov     r8d, 589h; unsigned __int16
0x18001cc5d  lea     rcx, [rsp+68h+var_48]; this
0x18001cc62  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001cc67  mov     ecx, 30h ; '0'; Size
0x18001cc6c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cc71  mov     rbx, rax
0x18001cc74  test    rax, rax
0x18001cc77  jz      loc_18001CD39
0x18001cc7d  lea     rcx, [rax+8]
0x18001cc81  add     rax, 18h
0x18001cc85  mov     [rax], rcx
0x18001cc88  mov     [rax+8], rcx
0x18001cc8c  mov     [rcx+8], rax
0x18001cc90  mov     [rcx], rax
0x18001cc93  mov     dword ptr [rbx], 1
0x18001cc99  mov     dword ptr [rbx+28h], 1
0x18001cca0  mov     eax, 58Dh
0x18001cca5  mov     [rsp+68h+var_48], 0
0x18001ccad  mov     ecx, 18h; cb
0x18001ccb2  mov     [rsp+68h+var_44], ax
0x18001ccb7  call    cs:__imp_CoTaskMemAlloc
0x18001ccbd  lea     rcx, [rbx+28h]
0x18001ccc1  test    rax, rax
0x18001ccc4  jnz     short loc_18001CCDB
0x18001ccc6  mov     edi, 8007000Eh
0x18001cccb  mov     eax, 58Eh
0x18001ccd0  mov     [rsp+68h+var_48], edi
0x18001ccd4  mov     [rsp+68h+var_42], ax
0x18001ccd9  jmp     short loc_18001CD1B
0x18001ccdb  mov     [rax+10h], rbx
0x18001ccdf  lock inc dword ptr [rcx]
0x18001cce2  lea     rdx, [rdi+8]
0x18001cce6  mov     r8, [rdx]
0x18001cce9  cmp     [r8+8], rdx
0x18001cced  jz      short loc_18001CCF6
0x18001ccef  mov     ecx, 3
0x18001ccf4  int     29h; Win8: RtlFailFast(ecx)
0x18001ccf6  mov     [rax], r8
0x18001ccf9  mov     [rax+8], rdx
0x18001ccfd  mov     [r8+8], rax
0x18001cd01  mov     [rdx], rax
0x18001cd04  lock inc dword ptr [rdi]
0x18001cd07  mov     eax, 58Eh
0x18001cd0c  mov     [rsp+68h+var_48], 0
0x18001cd14  mov     [rsp+68h+var_44], ax
0x18001cd19  xor     edi, edi
0x18001cd1b  or      eax, 0FFFFFFFFh
0x18001cd1e  lock xadd [rcx], eax
0x18001cd22  cmp     eax, 1
0x18001cd25  jnz     short loc_18001CD4C
0x18001cd27  mov     rcx, rbx; this
0x18001cd2a  call    ??1CSxNodeList@@AEAA@XZ; CSxNodeList::~CSxNodeList(void)
0x18001cd2f  mov     rcx, rbx; Block
0x18001cd32  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cd37  jmp     short loc_18001CD4C
0x18001cd39  mov     edi, 8007000Eh
0x18001cd3e  mov     eax, 58Dh
0x18001cd43  mov     [rsp+68h+var_48], edi
0x18001cd47  mov     [rsp+68h+var_42], ax
0x18001cd4c  lea     rcx, [rsp+68h+var_48]; this
0x18001cd51  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001cd56  mov     rbx, [rsp+68h+arg_0]
0x18001cd5b  mov     eax, edi
0x18001cd5d  add     rsp, 60h
0x18001cd61  pop     rdi
0x18001cd62  retn
```
