# SXReadBase::PiT(void)

- ea: `0x10040f590`
- end: `0x10040f6eb`
- name: `?PiT@SXReadBase@@IEAAXXZ`
- size: `347`
- prototype: `void __fastcall(SXReadBase *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x10040edb0`

## callees

- `0x100401350`
- `0x100406550`
- `0x100406be0`
- `0x10040f590`
- `0x100410e60`
- `0x100411000`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10040f648`
- `KERNEL32!HeapFree` at `0x10040f648`

## pseudocode

```c
void __fastcall SXReadBase::PiT(SXReadBase *this)
{
  unsigned int Mb32; // eax
  __int64 v3; // rdx
  void ***v4; // r8
  bool v5; // zf
  struct IMalloc *v6; // rcx
  unsigned int v7; // esi
  unsigned int v8; // edi
  unsigned int v9; // eax
  unsigned __int8 *WCharBuffer; // rax
  LPVOID lpMem; // [rsp+30h] [rbp+8h] BYREF

  Mb32 = SXReadBase::GetMb32(this);
  v3 = *((_QWORD *)this + 90);
  if ( Mb32 )
  {
    lpMem = 0;
    if ( Mb32 >= *(_DWORD *)(v3 + 36) )
    {
      MXRRaiseException(-2147467259);
      __debugbreak();
    }
    _mm_lfence();
    RStringPtr::assign((RStringPtr *)&lpMem, *(struct CStringPtr **)(*(_QWORD *)(v3 + 40) + 8LL * Mb32));
    v4 = (void ***)lpMem;
    *((_QWORD *)this + 164) = (char *)lpMem + 24;
    *((_DWORD *)this + 330) = *((_DWORD *)v4 + 4);
    v5 = (*((_DWORD *)v4 + 5))-- == 1;
    if ( v5 && v4 != &cspNull )
    {
      v6 = (struct IMalloc *)v4[1];
      if ( v6 || (v6 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, void ***))v6->lpVtbl->Free)(v6, v4);
      else
        HeapFree(g_hHeap, 0, v4);
    }
  }
  else
  {
    *((_DWORD *)this + 330) = 0;
    *((_QWORD *)this + 164) = &wnullstr;
  }
  v7 = SXReadBase::GetMb32(this);
  v8 = 2 * v7;
  if ( 2 * v7 < v7 )
  {
    MXRRaiseException(-2147352566);
    JUMPOUT(0x10040F6EALL);
  }
  v9 = *((_DWORD *)this + 174);
  if ( v9 && v8 > v9 )
  {
    MXRRaiseException(-1072897499);
    __debugbreak();
  }
  _mm_lfence();
  if ( v8 )
  {
    WCharBuffer = (unsigned __int8 *)SXReadBase::GetWCharBuffer(this, 0, v7);
    *((_QWORD *)this + 168) = WCharBuffer;
    SXReadBase::GetBytes(this, WCharBuffer, v8);
  }
  else
  {
    *((_QWORD *)this + 168) = SXReadBase::GetWCharBuffer(this, 0, 2u);
  }
  *((_DWORD *)this + 334) = v7;
}

```

## disassembly

```asm
0x10040f590  push    rbx
0x10040f592  sub     rsp, 20h
0x10040f596  mov     rbx, rcx
0x10040f599  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10040f59e  mov     rdx, [rbx+2D0h]
0x10040f5a5  test    eax, eax
0x10040f5a7  jnz     short loc_10040F5C2
0x10040f5a9  mov     [rbx+528h], eax
0x10040f5af  lea     rax, ?wnullstr@@3PA_WA; wchar_t near * wnullstr
0x10040f5b6  mov     [rbx+520h], rax
0x10040f5bd  jmp     loc_10040F64E
0x10040f5c2  mov     [rsp+28h+lpMem], 0
0x10040f5cb  cmp     eax, [rdx+24h]
0x10040f5ce  jnb     loc_10040F6D5
0x10040f5d4  lfence
0x10040f5d7  mov     rdx, [rdx+28h]
0x10040f5db  lea     rcx, [rsp+28h+lpMem]; this
0x10040f5e0  mov     eax, eax
0x10040f5e2  mov     rdx, [rdx+rax*8]; struct CStringPtr *
0x10040f5e6  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040f5eb  mov     r8, [rsp+28h+lpMem]; lpMem
0x10040f5f0  lea     rax, [r8+18h]
0x10040f5f4  mov     [rbx+520h], rax
0x10040f5fb  mov     eax, [r8+10h]
0x10040f5ff  mov     [rbx+528h], eax
0x10040f605  add     dword ptr [r8+14h], 0FFFFFFFFh
0x10040f60a  jnz     short loc_10040F64E
0x10040f60c  lea     rax, ?cspNull@@3VCStringPtr@@A; CStringPtr cspNull
0x10040f613  cmp     r8, rax
0x10040f616  jz      short loc_10040F64E
0x10040f618  mov     rcx, [r8+8]
0x10040f61c  test    rcx, rcx
0x10040f61f  jnz     short loc_10040F62D
0x10040f621  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040f628  test    rcx, rcx
0x10040f62b  jz      short loc_10040F63F
0x10040f62d  mov     rax, [rcx]
0x10040f630  mov     rdx, r8
0x10040f633  mov     rax, [rax+28h]
0x10040f637  call    cs:__guard_dispatch_icall_fptr
0x10040f63d  jmp     short loc_10040F64E
0x10040f63f  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040f646  xor     edx, edx; dwFlags
0x10040f648  call    cs:__imp_HeapFree
0x10040f64e  mov     [rsp+28h+arg_8], rsi
0x10040f653  mov     rcx, rbx; this
0x10040f656  mov     [rsp+28h+arg_10], rdi
0x10040f65b  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10040f660  mov     esi, eax
0x10040f662  lea     edi, [rax+rax]
0x10040f665  cmp     edi, eax
0x10040f667  jb      short loc_10040F6E0
0x10040f669  mov     eax, [rbx+2B8h]
0x10040f66f  test    eax, eax
0x10040f671  jz      short loc_10040F677
0x10040f673  cmp     edi, eax
0x10040f675  ja      short loc_10040F6CA
0x10040f677  lfence
0x10040f67a  xor     edx, edx; int
0x10040f67c  mov     rcx, rbx; this
0x10040f67f  test    edi, edi
0x10040f681  jz      short loc_10040F6A2
0x10040f683  mov     r8d, esi; unsigned int
0x10040f686  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040f68b  mov     r8d, edi; unsigned int
0x10040f68e  mov     [rbx+540h], rax
0x10040f695  mov     rdx, rax; unsigned __int8 *
0x10040f698  mov     rcx, rbx; this
0x10040f69b  call    ?GetBytes@SXReadBase@@IEAAXPEAEK@Z; SXReadBase::GetBytes(uchar *,ulong)
0x10040f6a0  jmp     short loc_10040F6B4
0x10040f6a2  mov     r8d, 2; unsigned int
0x10040f6a8  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040f6ad  mov     [rbx+540h], rax
0x10040f6b4  mov     rdi, [rsp+28h+arg_10]
0x10040f6b9  mov     [rbx+538h], esi
0x10040f6bf  mov     rsi, [rsp+28h+arg_8]
0x10040f6c4  add     rsp, 20h
0x10040f6c8  pop     rbx
0x10040f6c9  retn
0x10040f6ca  mov     ecx, 0C00CE225h; int
0x10040f6cf  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040f6d4  int     3; Trap to Debugger
0x10040f6d5  mov     ecx, 80004005h; int
0x10040f6da  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040f6df  int     3; Trap to Debugger
0x10040f6e0  mov     ecx, 8002000Ah; int
0x10040f6e5  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
