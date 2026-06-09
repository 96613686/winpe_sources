# SXReadBase::TokenT(void)

- ea: `0x100410010`
- end: `0x1004100c5`
- name: `?TokenT@SXReadBase@@IEAAXXZ`
- size: `181`
- prototype: `void __fastcall(SXTokenTable **this)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x10040edb0`
- `0x10040f700`
- `0x1004101e0`

## callees

- `0x100401350`
- `0x100406be0`
- `0x100406e50`
- `0x100407330`
- `0x100407bb0`
- `0x100413200`
- `0x100413250`
- `0x100414090`

## pseudocode

```c
void __fastcall SXReadBase::TokenT(SXTokenTable **this)
{
  _BYTE v2[8]; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v3[8]; // [rsp+48h] [rbp-30h] BYREF
  _BYTE v4[8]; // [rsp+50h] [rbp-28h] BYREF
  unsigned int Mb32; // [rsp+58h] [rbp-20h]
  unsigned int v6; // [rsp+5Ch] [rbp-1Ch]
  unsigned int v7; // [rsp+60h] [rbp-18h]

  Unitoken::Unitoken((Unitoken *)v2);
  Mb32 = SXReadBase::GetMb32((SXReadBase *)this);
  v6 = SXReadBase::GetMb32((SXReadBase *)this);
  v7 = SXReadBase::GetMb32((SXReadBase *)this);
  SXTokenTable::getRSPNameFromToken(this[90], (struct RStringPtr *)v2, Mb32);
  SXTokenTable::getRSPNameFromToken(this[90], (struct RStringPtr *)v3, v6);
  SXTokenTable::getRSPNameFromToken(this[90], (struct RStringPtr *)v4, v7);
  SXTokenTable::putUnitokenData(this[90], (struct Unitoken *)v2, 0);
  WriterHandleEntry::~WriterHandleEntry((WriterHandleEntry *)v2);
}

```

## disassembly

```asm
0x100410010  push    rbx
0x100410012  sub     rsp, 70h
0x100410016  mov     rbx, rcx
0x100410019  lea     rcx, [rsp+78h+var_38]; this
0x10041001e  call    ??0Unitoken@@QEAA@XZ; Unitoken::Unitoken(void)
0x100410023  nop
0x100410024  mov     rcx, rbx; this
0x100410027  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10041002c  mov     [rsp+78h+var_20], eax
0x100410030  mov     rcx, rbx; this
0x100410033  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x100410038  mov     [rsp+78h+var_1C], eax
0x10041003c  mov     rcx, rbx; this
0x10041003f  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x100410044  mov     [rsp+78h+var_18], eax
0x100410048  mov     r8d, [rsp+78h+var_20]; unsigned int
0x10041004d  lea     rdx, [rsp+78h+var_38]; struct RStringPtr *
0x100410052  mov     rcx, [rbx+2D0h]; this
0x100410059  call    ?getRSPNameFromToken@SXTokenTable@@QEAAXPEAVRStringPtr@@K@Z; SXTokenTable::getRSPNameFromToken(RStringPtr *,ulong)
0x10041005e  mov     r8d, [rsp+78h+var_1C]; unsigned int
0x100410063  lea     rdx, [rsp+78h+var_30]; struct RStringPtr *
0x100410068  mov     rcx, [rbx+2D0h]; this
0x10041006f  call    ?getRSPNameFromToken@SXTokenTable@@QEAAXPEAVRStringPtr@@K@Z; SXTokenTable::getRSPNameFromToken(RStringPtr *,ulong)
0x100410074  mov     r8d, [rsp+78h+var_18]; unsigned int
0x100410079  lea     rdx, [rsp+78h+var_28]; struct RStringPtr *
0x10041007e  mov     rcx, [rbx+2D0h]; this
0x100410085  call    ?getRSPNameFromToken@SXTokenTable@@QEAAXPEAVRStringPtr@@K@Z; SXTokenTable::getRSPNameFromToken(RStringPtr *,ulong)
0x10041008a  xor     r8d, r8d; unsigned int *
0x10041008d  lea     rdx, [rsp+78h+var_38]; struct Unitoken *
0x100410092  mov     rcx, [rbx+2D0h]; this
0x100410099  call    ?putUnitokenData@SXTokenTable@@QEAAXPEAVUnitoken@@PEAK@Z; SXTokenTable::putUnitokenData(Unitoken *,ulong *)
0x10041009e  nop
0x10041009f  lea     rcx, [rsp+78h+var_38]; this
0x1004100a4  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x1004100a9  add     rsp, 70h
0x1004100ad  pop     rbx
0x1004100ae  retn
0x1004100af  xor     edx, edx; unsigned int
0x1004100b1  lea     rcx, [rsp+arg_38]; this
0x1004100b6  call    ??_GUnitoken@@QEAAPEAXI@Z; Unitoken::`scalar deleting destructor'(uint)
0x1004100bb  mov     ecx, [rsp+arg_18]; int
0x1004100bf  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004100c4  nop
0x100424620  push    rbp
0x100424622  sub     rsp, 20h
0x100424626  mov     rbp, rdx
0x100424629  mov     [rbp+38h], rcx
0x10042462d  mov     [rbp+30h], rcx
0x100424631  mov     rax, [rbp+30h]
0x100424635  mov     rcx, [rax]
0x100424638  mov     [rbp+28h], rcx
0x10042463c  mov     rax, [rbp+28h]
0x100424640  mov     eax, [rax]
0x100424642  cmp     eax, 0C0000005h
0x100424647  jz      short loc_100424679
0x100424649  add     eax, 1FFFFFFFh
0x10042464e  cmp     eax, 1
0x100424651  ja      short loc_100424669
0x100424653  mov     rax, [rbp+28h]
0x100424657  cmp     dword ptr [rax+18h], 1
0x10042465b  jnz     short loc_100424669
0x10042465d  mov     rax, [rbp+28h]
0x100424661  mov     ecx, [rax+20h]
0x100424664  mov     [rbp+20h], ecx
0x100424667  jmp     short loc_100424670
0x100424669  mov     dword ptr [rbp+20h], 8000FFFFh
0x100424670  mov     dword ptr [rbp+24h], 1
0x100424677  jmp     short loc_100424680
0x100424679  mov     dword ptr [rbp+24h], 0
0x100424680  mov     eax, [rbp+24h]
0x100424683  add     rsp, 20h
0x100424687  pop     rbp
0x100424688  retn
```
