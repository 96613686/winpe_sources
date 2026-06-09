# ComTaskHost::ComTaskHost(_GUID * const,ushort *,ushort *,ulong,ulong)

- ea: `0x140006210`
- end: `0x140006448`
- name: `??0ComTaskHost@@QEAA@QEAU_GUID@@PEAG1KK@Z`
- size: `568`
- prototype: `ComTaskHost *__fastcall(ComTaskHost *this, struct _GUID *const, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140009910`

## callees

- `0x140006210`
- `0x140007f24`
- `0x1400093b0`
- `0x14000a1f8`
- `0x14000a29b`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14000635a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14000635a`
- `OLEAUT32!__imp_SysAllocString` at `0x140006287`
- `OLEAUT32!__imp_SysAllocString` at `0x140006307`
- `OLEAUT32!__imp_SysAllocString` at `0x140006287`
- `OLEAUT32!__imp_SysAllocString` at `0x140006307`

## pseudocode

```c
ComTaskHost *__fastcall ComTaskHost::ComTaskHost(
        ComTaskHost *this,
        struct _GUID *const a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6)
{
  BSTR *v10; // rax
  struct IErrorInfo *v11; // rdx
  int v12; // ecx
  BSTR *v13; // rbx
  BSTR v14; // rax
  int i; // ebx
  char v16; // al
  BSTR *v17; // rax
  struct IErrorInfo *v18; // rdx
  int v19; // ecx
  BSTR *v20; // rbx
  BSTR v21; // rax
  signed __int32 v22; // ebp
  int j; // ebx

  *(_QWORD *)this = &ComTaskHost::`vftable'{for `ITaskHandlerStatus'};
  *((_QWORD *)this + 1) = &ComTaskHost::`vftable'{for `ITaskVariables'};
  *((_DWORD *)this + 4) = 1;
  *((_DWORD *)this + 5) = 0;
  *(struct _GUID *)((char *)this + 24) = *a2;
  v10 = (BSTR *)operator new(0x18u);
  v13 = v10;
  if ( v10 )
  {
    v10[1] = 0;
    *((_DWORD *)v10 + 4) = 1;
    v14 = SysAllocString(a3);
    *v13 = v14;
    if ( !v14 && a3 )
      _com_raise_error(v12, v11);
  }
  else
  {
    v13 = 0;
  }
  *((_QWORD *)this + 5) = v13;
  if ( !v13 )
    _com_raise_error(v12, v11);
  for ( i = 0; i < 179; ++i )
  {
    if ( !memcmp_0(a2, &qword_14000ED30[2 * i], 0x10u) )
    {
      v16 = 1;
      goto LABEL_9;
    }
  }
  for ( j = 0; j < 24 && memcmp_0(a2, &qword_14000F860[2 * j], 0x10u); ++j )
    ;
  v16 = 0;
LABEL_9:
  *((_BYTE *)this + 48) = v16;
  v17 = (BSTR *)operator new(0x18u);
  v20 = v17;
  if ( v17 )
  {
    v17[1] = 0;
    *((_DWORD *)v17 + 4) = 1;
    v21 = SysAllocString(a4);
    *v20 = v21;
    if ( !v21 && a4 )
      _com_raise_error(v19, v18);
  }
  else
  {
    v20 = 0;
  }
  *((_QWORD *)this + 7) = v20;
  if ( !v20 )
    _com_raise_error(v19, v18);
  *((_DWORD *)this + 16) = a5;
  *((_DWORD *)this + 17) = a6;
  *((_QWORD *)this + 9) = 0;
  _InterlockedExchange64((volatile __int64 *)this + 9, 0);
  *((_QWORD *)this + 10) = 0;
  _InterlockedExchange64((volatile __int64 *)this + 10, 0);
  *((_QWORD *)this + 11) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v22 = _InterlockedIncrement((volatile signed __int32 *)this + 5);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e3bcaed62523302f0a82482d58f13b85_Traceguids, this, v22);
  (*(void (__fastcall **)(ComTaskMgrWnd *, ComTaskHost *))(*(_QWORD *)ComTaskMgrBase::s_pVirtualSingleton + 16LL))(
    ComTaskMgrBase::s_pVirtualSingleton,
    this);
  return this;
}

```

## disassembly

```asm
0x140006210  mov     [rsp+arg_10], rbx
0x140006215  mov     [rsp+arg_18], rbp
0x14000621a  mov     [rsp+arg_0], rcx
0x14000621f  push    rsi
0x140006220  push    rdi
0x140006221  push    r12
0x140006223  push    r14
0x140006225  push    r15
0x140006227  sub     rsp, 30h
0x14000622b  mov     r15, r9
0x14000622e  mov     rsi, r8
0x140006231  mov     rdi, rdx
0x140006234  mov     r14, rcx
0x140006237  lea     rax, ??_7ComTaskHost@@6BITaskHandlerStatus@@@; const ComTaskHost::`vftable'{for `ITaskHandlerStatus'}
0x14000623e  mov     [rcx], rax
0x140006241  lea     rax, ??_7ComTaskHost@@6BITaskVariables@@@; const ComTaskHost::`vftable'{for `ITaskVariables'}
0x140006248  mov     [rcx+8], rax
0x14000624c  mov     ebp, 1
0x140006251  mov     [rcx+10h], ebp
0x140006254  xor     r12d, r12d
0x140006257  mov     [rcx+14h], r12d
0x14000625b  movups  xmm0, xmmword ptr [rdx]
0x14000625e  movups  xmmword ptr [rcx+18h], xmm0
0x140006262  mov     ecx, 18h; Size
0x140006267  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000626c  mov     rbx, rax
0x14000626f  mov     [rsp+58h+arg_8], rax
0x140006274  test    rax, rax
0x140006277  jz      loc_140006406
0x14000627d  mov     [rax+8], r12
0x140006281  mov     [rax+10h], ebp
0x140006284  mov     rcx, rsi; psz
0x140006287  call    cs:__imp_SysAllocString
0x14000628d  mov     [rbx], rax
0x140006290  test    rax, rax
0x140006293  jz      loc_1400063E8
0x140006299  mov     [r14+28h], rbx
0x14000629d  test    rbx, rbx
0x1400062a0  jz      loc_14000641A
0x1400062a6  mov     ebx, r12d
0x1400062a9  lea     rsi, qword_14000ED30
0x1400062b0  cmp     ebx, 0B3h
0x1400062b6  jge     loc_1400063B6
0x1400062bc  movsxd  rdx, ebx
0x1400062bf  shl     rdx, 4
0x1400062c3  add     rdx, rsi; Buf2
0x1400062c6  mov     r8d, 10h; Size
0x1400062cc  mov     rcx, rdi; Buf1
0x1400062cf  call    memcmp_0
0x1400062d4  test    eax, eax
0x1400062d6  jz      short loc_1400062DC
0x1400062d8  inc     ebx
0x1400062da  jmp     short loc_1400062B0
0x1400062dc  mov     al, 1
0x1400062de  mov     [r14+30h], al
0x1400062e2  mov     ecx, 18h; Size
0x1400062e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400062ec  mov     rbx, rax
0x1400062ef  mov     [rsp+58h+arg_8], rax
0x1400062f4  test    rax, rax
0x1400062f7  jz      loc_14000640E
0x1400062fd  mov     [rax+8], r12
0x140006301  mov     [rax+10h], ebp
0x140006304  mov     rcx, r15; psz
0x140006307  call    cs:__imp_SysAllocString
0x14000630d  mov     [rbx], rax
0x140006310  test    rax, rax
0x140006313  jz      loc_1400063F7
0x140006319  mov     [r14+38h], rbx
0x14000631d  test    rbx, rbx
0x140006320  jz      loc_140006420
0x140006326  mov     eax, [rsp+58h+arg_20]
0x14000632d  mov     [r14+40h], eax
0x140006331  mov     eax, [rsp+58h+arg_28]
0x140006338  mov     [r14+44h], eax
0x14000633c  mov     [r14+48h], r12
0x140006340  mov     rax, r12
0x140006343  xchg    rax, [r14+48h]
0x140006347  mov     [r14+50h], r12
0x14000634b  mov     rax, r12
0x14000634e  xchg    rax, [r14+50h]
0x140006352  mov     [r14+58h], r12
0x140006356  lea     rcx, [r14+60h]; lpCriticalSection
0x14000635a  call    cs:__imp_InitializeCriticalSection
0x140006360  lock xadd [r14+14h], ebp
0x140006366  inc     ebp
0x140006368  lea     rax, WPP_GLOBAL_Control
0x14000636f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006376  cmp     rcx, rax
0x140006379  jz      short loc_140006385
0x14000637b  test    byte ptr [rcx+1Ch], 4
0x14000637f  jnz     loc_140006426
0x140006385  mov     rcx, cs:?s_pVirtualSingleton@ComTaskMgrBase@@0PEAV1@EA; ComTaskMgrBase * ComTaskMgrBase::s_pVirtualSingleton
0x14000638c  mov     rax, [rcx]
0x14000638f  mov     rdx, r14
0x140006392  mov     rax, [rax+10h]
0x140006396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000639b  nop
0x14000639c  mov     rax, r14
0x14000639f  mov     rbx, [rsp+58h+arg_10]
0x1400063a4  mov     rbp, [rsp+58h+arg_18]
0x1400063a9  add     rsp, 30h
0x1400063ad  pop     r15
0x1400063af  pop     r14
0x1400063b1  pop     r12
0x1400063b3  pop     rdi
0x1400063b4  pop     rsi
0x1400063b5  retn
0x1400063b6  mov     ebx, r12d
0x1400063b9  lea     rsi, qword_14000F860
0x1400063c0  cmp     ebx, 18h
0x1400063c3  jge     short loc_1400063E1
0x1400063c5  movsxd  rdx, ebx
0x1400063c8  shl     rdx, 4
0x1400063cc  add     rdx, rsi; Buf2
0x1400063cf  mov     r8d, 10h; Size
0x1400063d5  mov     rcx, rdi; Buf1
0x1400063d8  call    memcmp_0
0x1400063dd  test    eax, eax
0x1400063df  jnz     short loc_140006416
0x1400063e1  xor     al, al
0x1400063e3  jmp     loc_1400062DE
0x1400063e8  test    rsi, rsi
0x1400063eb  jz      loc_140006299
0x1400063f1  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1400063f7  test    r15, r15
0x1400063fa  jz      loc_140006319
0x140006400  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x140006406  mov     rbx, r12
0x140006409  jmp     loc_140006299
0x14000640e  mov     rbx, r12
0x140006411  jmp     loc_140006319
0x140006416  inc     ebx
0x140006418  jmp     short loc_1400063C0
0x14000641a  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x140006420  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x140006426  mov     edx, 0Ch
0x14000642b  mov     [rsp+58h+var_38], ebp
0x14000642f  mov     r9, r14
0x140006432  lea     r8, WPP_e3bcaed62523302f0a82482d58f13b85_Traceguids
0x140006439  mov     rcx, [rcx+10h]
0x14000643d  call    WPP_SF_qd
0x140006442  jmp     loc_140006385
```
