# CSDiagSchdFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800025f0`
- end: `0x1800026fb`
- name: `?CreateInstance@CSDiagSchdFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `267`
- prototype: `__int64 __fastcall(CSDiagSchdFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001174`
- `0x1800025f0`
- `0x180008604`
- `0x18000b13c`
- `0x18000d010`

## import_xrefs

- `KERNEL32!InitializeSRWLock` at `0x18000266e`
- `KERNEL32!InitializeSRWLock` at `0x18000266e`

## string_xrefs

- `0x1800026a6`: `CSDiagSchdFactory::CreateInstance`
- `0x1800026d5`: `CSDiagSchdFactory::CreateInstance`

## pseudocode

```c
__int64 __fastcall CSDiagSchdFactory::CreateInstance(
        CSDiagSchdFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v6; // ebx
  RTL_SRWLOCK *v7; // rax
  RTL_SRWLOCK *v8; // rdi
  int v9; // eax

  if ( !a4 )
  {
    v6 = -2147024809;
LABEL_10:
    SdpDebugTrace(1u, L"CSDiagSchdFactory::CreateInstance", 34, v6);
    return v6;
  }
  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    goto LABEL_10;
  }
  v7 = (RTL_SRWLOCK *)operator new(0x40u);
  v8 = v7;
  if ( !v7 )
  {
    v6 = -2147024882;
    goto LABEL_10;
  }
  HIDWORD(v7[1].Ptr) = 0;
  v7[2].Ptr = 0;
  v7[3].Ptr = 0;
  v7[4].Ptr = 0;
  v7[6].Ptr = 0;
  LODWORD(v7[7].Ptr) = 0;
  v7->Ptr = &CSDiagSchd::`vftable';
  LODWORD(v7[1].Ptr) = 1;
  InitializeSRWLock(v7 + 5);
  _InterlockedIncrement(&g_Count);
  McGenEventRegister_EventRegister();
  v9 = (*(__int64 (__fastcall **)(RTL_SRWLOCK *, const struct _GUID *, void **))v8->Ptr)(v8, a3, a4);
  v6 = v9;
  if ( v9 < 0 )
    SdpDebugTrace(1u, L"CSDiagSchdFactory::CreateInstance", 34, v9);
  (*((void (__fastcall **)(RTL_SRWLOCK *))v8->Ptr + 2))(v8);
  return v6;
}

```

## disassembly

```asm
0x1800025f0  mov     [rsp+arg_0], rbx
0x1800025f5  mov     [rsp+arg_8], rsi
0x1800025fa  push    rdi
0x1800025fb  sub     rsp, 20h
0x1800025ff  mov     rbx, r9
0x180002602  mov     rsi, r8
0x180002605  test    r9, r9
0x180002608  jnz     short loc_180002614
0x18000260a  mov     ebx, 80070057h
0x18000260f  jmp     loc_1800026CF
0x180002614  and     qword ptr [r9], 0
0x180002618  test    rdx, rdx
0x18000261b  jz      short loc_180002627
0x18000261d  mov     ebx, 80040110h
0x180002622  jmp     loc_1800026CF
0x180002627  mov     ecx, 40h ; '@'; Size
0x18000262c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002631  mov     rdi, rax
0x180002634  test    rax, rax
0x180002637  jz      loc_1800026CA
0x18000263d  and     dword ptr [rdi+0Ch], 0
0x180002641  lea     rax, ??_7CSDiagSchd@@6B@; const CSDiagSchd::`vftable'
0x180002648  and     qword ptr [rdi+10h], 0
0x18000264d  lea     rcx, [rdi+28h]; SRWLock
0x180002651  and     qword ptr [rdi+18h], 0
0x180002656  and     qword ptr [rdi+20h], 0
0x18000265b  and     qword ptr [rdi+30h], 0
0x180002660  and     dword ptr [rdi+38h], 0
0x180002664  mov     [rdi], rax
0x180002667  mov     dword ptr [rdi+8], 1
0x18000266e  call    cs:__imp_InitializeSRWLock
0x180002675  nop     dword ptr [rax+rax+00h]
0x18000267a  lock inc cs:?g_Count@@3JA; long g_Count
0x180002681  call    McGenEventRegister_EventRegister
0x180002686  mov     rax, [rdi]
0x180002689  mov     r8, rbx
0x18000268c  mov     rdx, rsi
0x18000268f  mov     rcx, rdi
0x180002692  mov     rax, [rax]
0x180002695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000269a  mov     ebx, eax
0x18000269c  test    eax, eax
0x18000269e  jns     short loc_1800026B9
0x1800026a0  mov     r8d, 22h ; '"'; int
0x1800026a6  lea     rdx, aCsdiagschdfact; "CSDiagSchdFactory::CreateInstance"
0x1800026ad  mov     r9d, eax; int
0x1800026b0  lea     ecx, [r8-21h]; Level
0x1800026b4  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800026b9  mov     rcx, [rdi]
0x1800026bc  mov     rax, [rcx+10h]
0x1800026c0  mov     rcx, rdi
0x1800026c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026c8  jmp     short loc_1800026E8
0x1800026ca  mov     ebx, 8007000Eh
0x1800026cf  mov     r8d, 22h ; '"'; int
0x1800026d5  lea     rdx, aCsdiagschdfact; "CSDiagSchdFactory::CreateInstance"
0x1800026dc  mov     r9d, ebx; int
0x1800026df  lea     ecx, [r8-21h]; Level
0x1800026e3  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800026e8  mov     rsi, [rsp+28h+arg_8]
0x1800026ed  mov     eax, ebx
0x1800026ef  mov     rbx, [rsp+28h+arg_0]
0x1800026f4  add     rsp, 20h
0x1800026f8  pop     rdi
0x1800026f9  retn
```
