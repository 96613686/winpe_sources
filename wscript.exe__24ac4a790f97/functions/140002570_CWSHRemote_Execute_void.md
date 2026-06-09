# CWSHRemote::Execute(void)

- ea: `0x140002570`
- end: `0x140002635`
- name: `?Execute@CWSHRemote@@UEAAJXZ`
- size: `197`
- prototype: `__int64 __fastcall(CWSHRemote *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002570`
- `0x14000a098`
- `0x140018010`

## import_xrefs

- `msvcrt!_beginthread` at `0x1400025f4`
- `msvcrt!_beginthread` at `0x1400025f4`
- `KERNEL32!GetCurrentThreadId` at `0x140002580`
- `KERNEL32!GetCurrentThreadId` at `0x140002580`

## pseudocode

```c
__int64 __fastcall CWSHRemote::Execute(CWSHRemote *this)
{
  int v1; // ebx
  __int64 v4; // rax

  v1 = *((_DWORD *)this + 10);
  if ( GetCurrentThreadId() != v1 )
    return 2147549183LL;
  if ( *((_BYTE *)this + 57) )
    return 2147500037LL;
  *((_BYTE *)this + 57) = 1;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 11, 0, 0) )
  {
    Signal_Exception(&IID_IWSHRemote, L"WSHRemote.Execute", 0xA2Bu);
    return 2147614729LL;
  }
  else
  {
    v4 = *(_QWORD *)this;
    *((_DWORD *)this + 11) = 1;
    (*(void (__fastcall **)(CWSHRemote *))(v4 + 8))(this);
    if ( _beginthread(CWSHRemote::ThreadProc, 0, this) == -1 )
    {
      (*(void (__fastcall **)(CWSHRemote *))(*(_QWORD *)this + 16LL))(this);
      Signal_Exception(&IID_IWSHRemote, L"WSHRemote.Execute", 0xA2Cu);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x140002570  mov     [rsp+arg_8], rbx
0x140002575  push    rdi
0x140002576  sub     rsp, 20h
0x14000257a  mov     ebx, [rcx+28h]
0x14000257d  mov     rdi, rcx
0x140002580  call    cs:__imp_GetCurrentThreadId
0x140002586  cmp     eax, ebx
0x140002588  jz      short loc_140002594
0x14000258a  mov     eax, 8000FFFFh
0x14000258f  jmp     loc_14000262A
0x140002594  xor     ecx, ecx
0x140002596  cmp     [rdi+39h], cl
0x140002599  jz      short loc_1400025A5
0x14000259b  mov     eax, 80004005h
0x1400025a0  jmp     loc_14000262A
0x1400025a5  mov     byte ptr [rdi+39h], 1
0x1400025a9  xor     eax, eax
0x1400025ab  lock cmpxchg [rdi+2Ch], ecx
0x1400025b0  jz      short loc_1400025D2
0x1400025b2  mov     r8d, 0A2Bh; unsigned int
0x1400025b8  lea     rdx, aWshremoteExecu; "WSHRemote.Execute"
0x1400025bf  lea     rcx, IID_IWSHRemote; struct _GUID *
0x1400025c6  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x1400025cb  mov     eax, 80020009h
0x1400025d0  jmp     short loc_14000262A
0x1400025d2  mov     rax, [rdi]
0x1400025d5  mov     rcx, rdi
0x1400025d8  mov     dword ptr [rdi+2Ch], 1
0x1400025df  mov     rax, [rax+8]
0x1400025e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400025e8  mov     r8, rdi; ArgList
0x1400025eb  lea     rcx, ?ThreadProc@CWSHRemote@@CAXPEAX@Z; StartAddress
0x1400025f2  xor     edx, edx; StackSize
0x1400025f4  call    cs:__imp__beginthread
0x1400025fa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400025fe  jnz     short loc_140002628
0x140002600  mov     rax, [rdi]
0x140002603  mov     rcx, rdi
0x140002606  mov     rax, [rax+10h]
0x14000260a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000260f  mov     r8d, 0A2Ch; unsigned int
0x140002615  lea     rdx, aWshremoteExecu; "WSHRemote.Execute"
0x14000261c  lea     rcx, IID_IWSHRemote; struct _GUID *
0x140002623  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x140002628  xor     eax, eax
0x14000262a  mov     rbx, [rsp+28h+arg_8]
0x14000262f  add     rsp, 20h
0x140002633  pop     rdi
0x140002634  retn
```
