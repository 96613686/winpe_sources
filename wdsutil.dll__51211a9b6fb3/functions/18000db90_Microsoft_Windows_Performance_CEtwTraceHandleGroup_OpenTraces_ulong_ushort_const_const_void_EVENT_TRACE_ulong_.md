# Microsoft::Windows::Performance::CEtwTraceHandleGroup::OpenTraces(ulong,ushort const * const *,void (*)(_EVENT_TRACE *),ulong (*)(_EVENT_TRACE_LOGFILEW *),ulong)

- ea: `0x18000db90`
- end: `0x18000dd0b`
- name: `?OpenTraces@CEtwTraceHandleGroup@Performance@Windows@Microsoft@@QEAAJKPEBQEBGP6AXPEAU_EVENT_TRACE@@@ZP6AKPEAU_EVENT_TRACE_LOGFILEW@@@ZK@Z`
- size: `379`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEtwTraceHandleGroup *__hidden this, unsigned int, const unsigned __int16 *const *, void (*)(struct _EVENT_TRACE *), unsigned int (*)(struct _EVENT_TRACE_LOGFILEW *), unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000bef8`

## callees

- `0x180001b10`
- `0x18000aa34`
- `0x18000abd4`
- `0x18000db90`
- `0x1800319ae`
- `0x1800319f0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000dcf3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000dcf3`
- `ADVAPI32!OpenTraceW` at `0x18000dc51`
- `ADVAPI32!OpenTraceW` at `0x18000dc51`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CEtwTraceHandleGroup::OpenTraces(
        Microsoft::Windows::Performance::CEtwTraceHandleGroup *this,
        unsigned int a2,
        const unsigned __int16 *const *a3,
        void (*a4)(struct _EVENT_TRACE *),
        unsigned int (*a5)(struct _EVENT_TRACE_LOGFILEW *),
        ULONG a6)
{
  __int64 v10; // rbp
  __int64 v11; // rdi
  TRACEHANDLE v12; // rax
  int Error; // edi
  char *v14; // rcx
  char *v15; // rbx
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+40h] [rbp-218h] BYREF

  if ( !(unsigned __int8)ATL::CAutoVectorPtr<Microsoft::Windows::Performance::CEtwTraceHandle>::Allocate(this, a2) )
    return 2147942414LL;
  *((_DWORD *)this + 2) = a2;
  v10 = 0;
  if ( !a2 )
    return 0;
  while ( 1 )
  {
    v11 = *(_QWORD *)this;
    memset_0(&Logfile, 0, sizeof(Logfile));
    Logfile.LogFileName = (LPWSTR)a3[v10];
    Logfile.EventCallback = a4;
    Logfile.BufferCallback = a5;
    Logfile.LogfileHeader.ReservedFlags = a6;
    v12 = OpenTraceW(&Logfile);
    *(_QWORD *)(v11 + 16LL * (unsigned int)v10) = v12;
    *(_DWORD *)(v11 + 16LL * (unsigned int)v10 + 8) = LOWORD(Logfile.LogfileHeader.Version);
    *(_DWORD *)(v11 + 16LL * (unsigned int)v10 + 12) = Logfile.LogfileHeader.BufferSize;
    if ( v12 == -1 )
    {
      Error = ATL::AtlHresultFromLastError();
      if ( Error < 0 )
        break;
    }
    v10 = (unsigned int)(v10 + 1);
    if ( (unsigned int)v10 >= a2 )
      return 0;
  }
  if ( *((_DWORD *)this + 2) )
  {
    v14 = *(char **)this;
    if ( *(_QWORD *)this )
    {
      v15 = v14 - 8;
      `eh vector destructor iterator'(
        v14,
        0x10u,
        *((_QWORD *)v14 - 1),
        (void (*)(void *))Microsoft::Windows::Performance::CEtwTraceHandle::~CEtwTraceHandle);
      operator delete[](v15);
    }
    *(_QWORD *)this = 0;
    *((_DWORD *)this + 2) = 0;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000db90  push    rbx
0x18000db92  push    rbp
0x18000db93  push    rsi
0x18000db94  push    rdi
0x18000db95  push    r12
0x18000db97  push    r13
0x18000db99  push    r14
0x18000db9b  push    r15
0x18000db9d  sub     rsp, 218h
0x18000dba4  mov     [rsp+258h+var_228], 0FFFFFFFFFFFFFFFEh
0x18000dbad  mov     rax, cs:__security_cookie
0x18000dbb4  xor     rax, rsp
0x18000dbb7  mov     [rsp+258h+var_58], rax
0x18000dbbf  mov     [rsp+258h+var_238], r9
0x18000dbc4  mov     r13, r8
0x18000dbc7  mov     r15d, edx
0x18000dbca  mov     r14, rcx
0x18000dbcd  mov     rax, [rsp+258h+arg_20]
0x18000dbd5  mov     [rsp+258h+var_230], rax
0x18000dbda  mov     edx, edx
0x18000dbdc  call    ?Allocate@?$CAutoVectorPtr@VCEtwTraceHandle@Performance@Windows@Microsoft@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<Microsoft::Windows::Performance::CEtwTraceHandle>::Allocate(unsigned __int64)
0x18000dbe1  test    al, al
0x18000dbe3  jnz     short loc_18000DBEF
0x18000dbe5  mov     eax, 8007000Eh
0x18000dbea  jmp     loc_18000DCA5
0x18000dbef  mov     [r14+8], r15d
0x18000dbf3  xor     ebp, ebp
0x18000dbf5  test    r15d, r15d
0x18000dbf8  jz      loc_18000DCA3
0x18000dbfe  mov     r12d, [rsp+258h+arg_28]
0x18000dc06  mov     esi, ebp
0x18000dc08  add     rsi, rsi
0x18000dc0b  mov     rdi, [r14]
0x18000dc0e  xor     edx, edx; Val
0x18000dc10  mov     r8d, 1C0h; Size
0x18000dc16  lea     rcx, [rsp+258h+Logfile]; void *
0x18000dc1b  call    memset_0
0x18000dc20  mov     rax, [r13+rbp*8+0]
0x18000dc25  mov     [rsp+258h+Logfile.LogFileName], rax
0x18000dc2a  mov     rax, [rsp+258h+var_238]
0x18000dc2f  mov     qword ptr [rsp+258h+Logfile.1A8h], rax
0x18000dc37  mov     rax, [rsp+258h+var_230]
0x18000dc3c  mov     [rsp+258h+Logfile.BufferCallback], rax
0x18000dc44  mov     [rsp+258h+Logfile.LogfileHeader.ReservedFlags], r12d
0x18000dc4c  lea     rcx, [rsp+258h+Logfile]; Logfile
0x18000dc51  call    cs:__imp_OpenTraceW
0x18000dc58  nop     dword ptr [rax+rax+00h]
0x18000dc5d  mov     [rdi+rsi*8], rax
0x18000dc61  movzx   edx, byte ptr [rsp+258h+Logfile.LogfileHeader.4+1]
0x18000dc69  shl     edx, 8
0x18000dc6c  movzx   ecx, byte ptr [rsp+258h+Logfile.LogfileHeader.4]
0x18000dc74  or      edx, ecx
0x18000dc76  mov     [rdi+rsi*8+8], edx
0x18000dc7a  mov     ecx, [rsp+258h+Logfile.LogfileHeader.BufferSize]
0x18000dc81  mov     [rdi+rsi*8+0Ch], ecx
0x18000dc85  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000dc89  jnz     short loc_18000DC98
0x18000dc8b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000dc90  mov     edi, eax
0x18000dc92  xor     esi, esi
0x18000dc94  test    eax, eax
0x18000dc96  js      short loc_18000DCCA
0x18000dc98  inc     ebp
0x18000dc9a  cmp     ebp, r15d
0x18000dc9d  jb      loc_18000DC06
0x18000dca3  xor     eax, eax
0x18000dca5  mov     rcx, [rsp+258h+var_58]
0x18000dcad  xor     rcx, rsp; StackCookie
0x18000dcb0  call    __security_check_cookie
0x18000dcb5  add     rsp, 218h
0x18000dcbc  pop     r15
0x18000dcbe  pop     r14
0x18000dcc0  pop     r13
0x18000dcc2  pop     r12
0x18000dcc4  pop     rdi
0x18000dcc5  pop     rsi
0x18000dcc6  pop     rbp
0x18000dcc7  pop     rbx
0x18000dcc8  retn
0x18000dcca  cmp     [r14+8], esi
0x18000dcce  jz      short loc_18000DD07
0x18000dcd0  mov     rcx, [r14]; void *
0x18000dcd3  test    rcx, rcx
0x18000dcd6  jz      short loc_18000DD00
0x18000dcd8  lea     rbx, [rcx-8]
0x18000dcdc  lea     r9, ??1CEtwTraceHandle@Performance@Windows@Microsoft@@QEAA@XZ; void (*)(void *)
0x18000dce3  mov     r8, [rbx]; unsigned __int64
0x18000dce6  mov     edx, 10h; unsigned __int64
0x18000dceb  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000dcf0  mov     rcx, rbx
0x18000dcf3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000dcfa  nop     dword ptr [rax+rax+00h]
0x18000dcff  nop
0x18000dd00  mov     [r14], rsi
0x18000dd03  mov     [r14+8], esi
0x18000dd07  mov     eax, edi
0x18000dd09  jmp     short loc_18000DCA5
```
