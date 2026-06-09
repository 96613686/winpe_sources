# CCorrAPOBase::GetEffectsList(_GUID * *,uint *,void *)

- ea: `0x180077874`
- end: `0x180077a79`
- name: `?GetEffectsList@CCorrAPOBase@@QEAAJPEAPEAU_GUID@@PEAIPEAX@Z`
- size: `517`
- prototype: `__int64 __fastcall(CCorrAPOBase *__hidden this, struct _GUID **, unsigned int *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180077860`

## callees

- `0x180014d58`
- `0x180014e94`
- `0x180077874`
- `0x180078f68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180077934`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007793d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180077934`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007793d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077a0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077a58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077a0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077a58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007790b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007790b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180077921`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180077921`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180077967`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180077967`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800779dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800779dd`

## pseudocode

```c
__int64 __fastcall CCorrAPOBase::GetEffectsList(CCorrAPOBase *this, struct _GUID **a2, unsigned int *a3, void *a4)
{
  __int64 v8; // rdx
  unsigned int LastError; // ebx
  __int64 v11; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rsi
  void *v13; // rcx
  HANDLE CurrentProcess; // rbx
  HANDLE v15; // rax
  const char *v16; // r9
  int EffectState; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rax
  struct _GUID *v21; // rax
  unsigned int v22; // r10d
  int v23; // r9d
  unsigned int i; // r8d
  __int64 v25; // rcx
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-58h]
  unsigned int v27[4]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v29; // [rsp+88h] [rbp+10h] BYREF

  if ( !a2 )
  {
    v8 = 1981;
LABEL_3:
    LastError = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"clientcore\\multimedia\\codecdsp\\audio\\lfxgfx\\apo\\lfxgfxapo.cpp",
      (const char *)0x80004003LL,
      dwDesiredAccess);
    return LastError;
  }
  if ( !a3 )
  {
    v8 = 1982;
    goto LABEL_3;
  }
  *a2 = 0;
  *a3 = 0;
  v11 = *(_QWORD *)((char *)this + 156) - *(_QWORD *)&GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1;
  if ( !v11 )
    v11 = *(_QWORD *)((char *)this + 164) - *(_QWORD *)GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4;
  if ( v11 )
  {
    v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 320);
    EnterCriticalSection((LPCRITICAL_SECTION)this + 8);
    v13 = (void *)*((_QWORD *)this + 22);
    if ( v13 )
    {
      CloseHandle(v13);
      *((_QWORD *)this + 22) = 0;
    }
    if ( a4 )
    {
      CurrentProcess = GetCurrentProcess();
      v15 = GetCurrentProcess();
      if ( !DuplicateHandle(v15, a4, CurrentProcess, (LPHANDLE)this + 22, 2u, 0, 0) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x7D2,
                      (unsigned int)"clientcore\\multimedia\\codecdsp\\audio\\lfxgfx\\apo\\lfxgfxapo.cpp",
                      v16);
LABEL_21:
        LeaveCriticalSection(v12);
        return LastError;
      }
    }
    v27[0] = 0;
    v29 = 0;
    EffectState = CCorrAPOBase::GetEffectState(this, v27, &v29);
    LastError = EffectState;
    if ( EffectState < 0 )
    {
      v18 = (unsigned int)EffectState;
      v19 = 2008;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"clientcore\\multimedia\\codecdsp\\audio\\lfxgfx\\apo\\lfxgfxapo.cpp",
        (const char *)v18,
        dwDesiredAccess);
      goto LABEL_21;
    }
    v20 = v29;
    if ( v29 > 0 )
    {
      *a3 = v29;
      v21 = (struct _GUID *)CoTaskMemAlloc(16 * v20);
      *a2 = v21;
      if ( !v21 )
      {
        LastError = -2147024882;
        v19 = 2015;
        v18 = 2147942414LL;
        goto LABEL_20;
      }
      v22 = v27[0];
      v23 = 0;
      for ( i = 0; i < 8; ++i )
      {
        if ( _bittest((const int *)&v22, i) )
        {
          v25 = v23++;
          (*a2)[v25] = *(struct _GUID *)((char *)&xmmword_1801B8454 + 44 * (int)i);
        }
      }
    }
    LeaveCriticalSection(v12);
  }
  return 0;
}

```

## disassembly

```asm
0x180077874  mov     [rsp+arg_0], rbx
0x180077879  mov     [rsp+arg_10], rbp
0x18007787e  push    rsi
0x18007787f  push    rdi
0x180077880  push    r12
0x180077882  push    r14
0x180077884  push    r15
0x180077886  sub     rsp, 50h
0x18007788a  mov     r12, r9
0x18007788d  mov     r15, r8
0x180077890  mov     r14, rdx
0x180077893  mov     rdi, rcx
0x180077896  test    rdx, rdx
0x180077899  jnz     short loc_1800778C0
0x18007789b  mov     edx, 7BDh; void *
0x1800778a0  mov     rcx, [rsp+78h]; this
0x1800778a5  lea     r8, aClientcoreMult; "clientcore\\multimedia\\codecdsp\\audio"...
0x1800778ac  mov     ebx, 80004003h
0x1800778b1  mov     r9d, ebx; char *
0x1800778b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800778b9  mov     eax, ebx
0x1800778bb  jmp     loc_180077A60
0x1800778c0  test    r15, r15
0x1800778c3  jnz     short loc_1800778CC
0x1800778c5  mov     edx, 7BEh
0x1800778ca  jmp     short loc_1800778A0
0x1800778cc  mov     qword ptr [rdx], 0
0x1800778d3  mov     dword ptr [r8], 0
0x1800778da  mov     rax, [rcx+9Ch]
0x1800778e1  sub     rax, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x1800778e8  jnz     short loc_1800778F8
0x1800778ea  mov     rax, [rcx+0A4h]
0x1800778f1  sub     rax, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4
0x1800778f8  test    rax, rax
0x1800778fb  jz      loc_180077A5E
0x180077901  lea     rsi, [rcx+140h]
0x180077908  mov     rcx, rsi; lpCriticalSection
0x18007790b  call    cs:__imp_EnterCriticalSection
0x180077911  lea     rbp, [rdi+0B0h]
0x180077918  mov     rcx, [rbp+0]; hObject
0x18007791c  test    rcx, rcx
0x18007791f  jz      short loc_18007792F
0x180077921  call    cs:__imp_CloseHandle
0x180077927  mov     qword ptr [rbp+0], 0
0x18007792f  test    r12, r12
0x180077932  jz      short loc_18007798B
0x180077934  call    cs:__imp_GetCurrentProcess
0x18007793a  mov     rbx, rax
0x18007793d  call    cs:__imp_GetCurrentProcess
0x180077943  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18007794b  mov     r9, rbp; lpTargetHandle
0x18007794e  mov     rcx, rax; hSourceProcessHandle
0x180077951  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x180077959  mov     r8, rbx; hTargetProcessHandle
0x18007795c  mov     [rsp+78h+dwDesiredAccess], 2; dwDesiredAccess
0x180077964  mov     rdx, r12; hSourceHandle
0x180077967  call    cs:__imp_DuplicateHandle
0x18007796d  test    eax, eax
0x18007796f  jnz     short loc_18007798B
0x180077971  mov     rcx, [rsp+78h]; this
0x180077976  lea     r8, aClientcoreMult; "clientcore\\multimedia\\codecdsp\\audio"...
0x18007797d  mov     edx, 7D2h; void *
0x180077982  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180077987  mov     ebx, eax
0x180077989  jmp     short loc_180077A09
0x18007798b  lea     r8, [rsp+78h+arg_8]; int *
0x180077993  mov     [rsp+78h+var_38], 0
0x18007799b  lea     rdx, [rsp+78h+var_38]; unsigned int *
0x1800779a0  mov     [rsp+78h+arg_8], 0
0x1800779ab  mov     rcx, rdi; this
0x1800779ae  call    ?GetEffectState@CCorrAPOBase@@IEAAJPEAKPEAH@Z; CCorrAPOBase::GetEffectState(ulong *,int *)
0x1800779b3  mov     ebx, eax
0x1800779b5  test    eax, eax
0x1800779b7  jns     short loc_1800779C3
0x1800779b9  mov     r9d, eax
0x1800779bc  mov     edx, 7D8h
0x1800779c1  jmp     short loc_1800779F8
0x1800779c3  movsxd  rax, [rsp+78h+arg_8]
0x1800779cb  test    eax, eax
0x1800779cd  jle     loc_180077A55
0x1800779d3  mov     rcx, rax
0x1800779d6  mov     [r15], eax
0x1800779d9  shl     rcx, 4; cb
0x1800779dd  call    cs:__imp_CoTaskMemAlloc
0x1800779e3  mov     [r14], rax
0x1800779e6  test    rax, rax
0x1800779e9  jnz     short loc_180077A17
0x1800779eb  mov     ebx, 8007000Eh
0x1800779f0  mov     edx, 7DFh; void *
0x1800779f5  mov     r9d, ebx; char *
0x1800779f8  mov     rcx, [rsp+78h]; this
0x1800779fd  lea     r8, aClientcoreMult; "clientcore\\multimedia\\codecdsp\\audio"...
0x180077a04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077a09  mov     rcx, rsi; lpCriticalSection
0x180077a0c  call    cs:__imp_LeaveCriticalSection
0x180077a12  jmp     loc_1800778B9
0x180077a17  mov     r10d, [rsp+78h+var_38]
0x180077a1c  xor     r9d, r9d
0x180077a1f  xor     r8d, r8d
0x180077a22  bt      r10d, r8d
0x180077a26  jnb     short loc_180077A4C
0x180077a28  movsxd  rax, r8d
0x180077a2b  lea     r11, xmmword_1801B8454
0x180077a32  imul    rdx, rax, 2Ch ; ','
0x180077a36  mov     rax, [r14]
0x180077a39  movsxd  rcx, r9d
0x180077a3c  add     rcx, rcx
0x180077a3f  inc     r9d
0x180077a42  movups  xmm0, xmmword ptr [rdx+r11]
0x180077a47  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x180077a4c  inc     r8d
0x180077a4f  cmp     r8d, 8
0x180077a53  jb      short loc_180077A22
0x180077a55  mov     rcx, rsi; lpCriticalSection
0x180077a58  call    cs:__imp_LeaveCriticalSection
0x180077a5e  xor     eax, eax
0x180077a60  lea     r11, [rsp+78h+var_28]
0x180077a65  mov     rbx, [r11+30h]
0x180077a69  mov     rbp, [r11+40h]
0x180077a6d  mov     rsp, r11
0x180077a70  pop     r15
0x180077a72  pop     r14
0x180077a74  pop     r12
0x180077a76  pop     rdi
0x180077a77  pop     rsi
0x180077a78  retn
```
