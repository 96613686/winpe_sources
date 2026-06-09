# CSxNodeListStack::TopItemDelete(void)

- ea: `0x18001dc74`
- end: `0x18001dd90`
- name: `?TopItemDelete@CSxNodeListStack@@QEAAJXZ`
- size: `284`
- prototype: `__int64 __fastcall(CSxNodeListStack *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18001d4dc`

## callees

- `0x180001554`
- `0x18000ea0c`
- `0x18001586c`
- `0x180015974`
- `0x18001c8b4`
- `0x18001cd6c`
- `0x18001dc74`
- `0x180020488`

## string_xrefs

- `0x18001dcb9`: `CSxNodeListStack::TopItemDelete`

## pseudocode

```c
__int64 __fastcall CSxNodeListStack::TopItemDelete(CSxNodeListStack *this)
{
  int v2; // esi
  _QWORD *v3; // rcx
  volatile signed __int32 *v4; // rbx
  __int16 v5; // ax
  LPVOID *v6; // rdi
  int v8; // [rsp+20h] [rbp-48h] BYREF
  __int16 v9; // [rsp+24h] [rbp-44h]
  __int16 v10; // [rsp+26h] [rbp-42h]
  void *Block; // [rsp+98h] [rbp+30h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  v2 = 1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "CSxNodeListStack::TopItemDelete", 1480, 1);
  v3 = (_QWORD *)*((_QWORD *)this + 1);
  Block = 0;
  if ( v3 == (_QWORD *)((char *)this + 24) )
  {
    v4 = 0;
    v8 = 1;
    v5 = 1488;
  }
  else
  {
    v4 = (volatile signed __int32 *)v3[2];
    _InterlockedAdd(v4 + 10, 1u);
    v8 = 0;
    v9 = 1485;
    v2 = CSxList<CSxNodeList,CSxNodeItem>::RemoveHead((__int64)v4, &Block);
    v8 = v2;
    v5 = 1491;
    if ( v2 < 0 )
    {
      v10 = 1491;
      goto LABEL_7;
    }
  }
  v9 = v5;
LABEL_7:
  v6 = (LPVOID *)Block;
  if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 )
  {
    CBsString::_Release(v6);
    operator delete(v6);
  }
  if ( v4 && _InterlockedExchangeAdd(v4 + 10, 0xFFFFFFFF) == 1 )
  {
    CSxNodeList::~CSxNodeList((CSxNodeList *)v4);
    operator delete((void *)v4);
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001dc74  push    rbp
0x18001dc76  push    rbx
0x18001dc77  push    rsi
0x18001dc78  push    rdi
0x18001dc79  mov     rbp, rsp
0x18001dc7c  sub     rsp, 68h
0x18001dc80  mov     rbx, rcx
0x18001dc83  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dc8a  lea     rax, WPP_GLOBAL_Control
0x18001dc91  cmp     rcx, rax
0x18001dc94  jz      short loc_18001DCB4
0x18001dc96  test    dword ptr [rcx+1Ch], 20000000h
0x18001dc9d  jz      short loc_18001DCB4
0x18001dc9f  mov     rcx, [rcx+10h]
0x18001dca3  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18001dcaa  mov     edx, 2Eh ; '.'
0x18001dcaf  call    WPP_SF_
0x18001dcb4  mov     esi, 1
0x18001dcb9  lea     rdx, aCsxnodeliststa_1; "CSxNodeListStack::TopItemDelete"
0x18001dcc0  mov     r9d, esi; unsigned __int16
0x18001dcc3  lea     rcx, [rbp+var_48]; this
0x18001dcc7  mov     r8d, 5C8h; unsigned __int16
0x18001dccd  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001dcd2  mov     rcx, [rbx+8]
0x18001dcd6  lea     rax, [rbx+18h]
0x18001dcda  mov     [rbp+Block], 0
0x18001dce2  cmp     rcx, rax
0x18001dce5  jnz     short loc_18001DD51
0x18001dce7  xor     ebx, ebx
0x18001dce9  mov     [rbp+var_48], esi
0x18001dcec  mov     eax, 5D0h
0x18001dcf1  mov     [rbp+var_44], ax
0x18001dcf5  mov     rdi, [rbp+Block]
0x18001dcf9  test    rdi, rdi
0x18001dcfc  jz      short loc_18001DD1B
0x18001dcfe  or      eax, 0FFFFFFFFh
0x18001dd01  lock xadd [rdi+10h], eax
0x18001dd06  cmp     eax, 1
0x18001dd09  jnz     short loc_18001DD1B
0x18001dd0b  mov     rcx, rdi; this
0x18001dd0e  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001dd13  mov     rcx, rdi; Block
0x18001dd16  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001dd1b  test    rbx, rbx
0x18001dd1e  jz      short loc_18001DD3D
0x18001dd20  or      ecx, 0FFFFFFFFh
0x18001dd23  lock xadd [rbx+28h], ecx
0x18001dd28  cmp     ecx, 1
0x18001dd2b  jnz     short loc_18001DD3D
0x18001dd2d  mov     rcx, rbx; this
0x18001dd30  call    ??1CSxNodeList@@AEAA@XZ; CSxNodeList::~CSxNodeList(void)
0x18001dd35  mov     rcx, rbx; Block
0x18001dd38  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001dd3d  lea     rcx, [rbp+var_48]; this
0x18001dd41  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001dd46  mov     eax, esi
0x18001dd48  add     rsp, 68h
0x18001dd4c  pop     rdi
0x18001dd4d  pop     rsi
0x18001dd4e  pop     rbx
0x18001dd4f  pop     rbp
0x18001dd50  retn
0x18001dd51  mov     rbx, [rcx+10h]
0x18001dd55  lock add [rbx+28h], esi
0x18001dd59  mov     eax, 5CDh
0x18001dd5e  mov     [rbp+var_48], 0
0x18001dd65  lea     rdx, [rbp+Block]
0x18001dd69  mov     [rbp+var_44], ax
0x18001dd6d  mov     rcx, rbx
0x18001dd70  call    ?RemoveHead@?$CSxList@VCSxNodeList@@VCSxNodeItem@@@@QEAAJPEAPEAVCSxNodeItem@@@Z; CSxList<CSxNodeList,CSxNodeItem>::RemoveHead(CSxNodeItem * *)
0x18001dd75  mov     esi, eax
0x18001dd77  mov     [rbp+var_48], eax
0x18001dd7a  test    eax, eax
0x18001dd7c  mov     eax, 5D3h
0x18001dd81  jns     loc_18001DCF1
0x18001dd87  mov     [rbp+var_42], ax
0x18001dd8b  jmp     loc_18001DCF5
```
