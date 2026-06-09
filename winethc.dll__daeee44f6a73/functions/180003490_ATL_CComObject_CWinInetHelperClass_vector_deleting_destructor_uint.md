# ATL::CComObject<CWinInetHelperClass>::`vector deleting destructor'(uint)

- ea: `0x180003490`
- end: `0x1800034fd`
- name: `??_E?$CComObject@VCWinInetHelperClass@@@ATL@@UEAAPEAXI@Z`
- size: `109`
- prototype: `__int64 __fastcall(CWinInetHelperClass *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800012c0`
- `0x180002f7c`
- `0x180003490`
- `0x180014010`

## pseudocode

```c
CWinInetHelperClass *__fastcall ATL::CComObject<CWinInetHelperClass>::`vector deleting destructor'(
        CWinInetHelperClass *this,
        char a2)
{
  *((_DWORD *)this + 16) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CWinInetHelperClass>::`vftable'{for `INetDiagHelper'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CWinInetHelperClass>::`vftable'{for `INetDiagHelperInfo'};
  *((_QWORD *)this + 7) = &ATL::CComObject<CWinInetHelperClass>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWinInetHelperClass::~CWinInetHelperClass(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003490  mov     [rsp+arg_0], rbx
0x180003495  push    rdi
0x180003496  sub     rsp, 20h
0x18000349a  mov     dword ptr [rcx+40h], 0C0000001h
0x1800034a1  lea     rax, ??_7?$CComObject@VCWinInetHelperClass@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CWinInetHelperClass>::`vftable'{for `INetDiagHelper'}
0x1800034a8  mov     [rcx], rax
0x1800034ab  mov     rdi, rcx
0x1800034ae  lea     rax, ??_7?$CComObject@VCWinInetHelperClass@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CWinInetHelperClass>::`vftable'{for `INetDiagHelperInfo'}
0x1800034b5  mov     ebx, edx
0x1800034b7  mov     [rcx+8], rax
0x1800034bb  lea     rax, ??_7?$CComObject@VCWinInetHelperClass@@@ATL@@6B@; const ATL::CComObject<CWinInetHelperClass>::`vftable'
0x1800034c2  mov     [rcx+38h], rax
0x1800034c6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800034cd  mov     rax, [rcx]
0x1800034d0  mov     rax, [rax+10h]
0x1800034d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034d9  mov     rcx, rdi; this
0x1800034dc  call    ??1CWinInetHelperClass@@QEAA@XZ; CWinInetHelperClass::~CWinInetHelperClass(void)
0x1800034e1  test    bl, 1
0x1800034e4  jz      short loc_1800034EE
0x1800034e6  mov     rcx, rdi; Block
0x1800034e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800034ee  mov     rbx, [rsp+28h+arg_0]
0x1800034f3  mov     rax, rdi
0x1800034f6  add     rsp, 20h
0x1800034fa  pop     rdi
0x1800034fb  retn
```
