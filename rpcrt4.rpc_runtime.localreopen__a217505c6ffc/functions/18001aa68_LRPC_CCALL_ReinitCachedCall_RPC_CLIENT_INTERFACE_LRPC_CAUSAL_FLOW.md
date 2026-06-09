# LRPC_CCALL::ReinitCachedCall(_RPC_CLIENT_INTERFACE *,LRPC_CAUSAL_FLOW *)

- ea: `0x18001aa68`
- end: `0x18001ac9b`
- name: `?ReinitCachedCall@LRPC_CCALL@@QEAAJPEAU_RPC_CLIENT_INTERFACE@@PEAVLRPC_CAUSAL_FLOW@@@Z`
- size: `563`
- prototype: `__int64 __fastcall(LRPC_CCALL *__hidden this, struct _RPC_CLIENT_INTERFACE *, struct LRPC_CAUSAL_FLOW *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a3c70`

## callees

- `0x18001aa68`
- `0x18001c008`
- `0x18001e6d0`
- `0x1800295d8`
- `0x180029c38`
- `0x18002cab0`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x18001ab45`
- `ntdll!NtOpenThreadToken` at `0x18001ab45`
- `ntdll!RtlLeaveCriticalSection` at `0x18001abf2`
- `ntdll!RtlLeaveCriticalSection` at `0x18001abf2`
- `ntdll!RtlEnterCriticalSection` at `0x18001abbc`
- `ntdll!RtlEnterCriticalSection` at `0x18001abbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ab29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ab29`

## pseudocode

```c
__int64 __fastcall LRPC_CCALL::ReinitCachedCall(
        LRPC_CCALL *this,
        struct _RPC_CLIENT_INTERFACE *a2,
        struct LRPC_CAUSAL_FLOW *a3)
{
  __int64 v3; // r9
  struct LRPC_CAUSAL_FLOW *v4; // rsi
  signed __int32 v6; // eax
  void **v7; // rcx
  unsigned int v8; // ebx
  void **v10; // rbx
  __int64 *v11; // r14
  HANDLE CurrentThread; // rax
  NTSTATUS v13; // eax
  __int64 v14; // rax
  unsigned int i; // ecx
  struct LRPC_CAUSAL_FLOW **v16; // r8
  signed __int32 v17[8]; // [rsp+0h] [rbp-88h] BYREF
  _DWORD v18[18]; // [rsp+40h] [rbp-48h] BYREF

  v3 = *((_QWORD *)this + 35);
  v4 = a3;
  v6 = _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 188), 1u);
  *((_QWORD *)this + 80) = a2;
  *((_DWORD *)this + 73) = v6 + 1;
  *((_DWORD *)this + 168) = 0;
  *((_DWORD *)this + 176) = -1073606632;
  v7 = (void **)*((_QWORD *)this + 89);
  if ( v7 )
  {
    do
    {
      v10 = (void **)*v7;
      FreeEEInfoRecord(v7);
      v7 = v10;
    }
    while ( v10 );
    *((_QWORD *)this + 89) = 0;
  }
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 74) = 0;
  *((_DWORD *)this + 198) = 0;
  *((_DWORD *)this + 75) = 0;
  if ( (*((_DWORD *)this + 72) & 2) == 0 )
  {
    REFERENCED_OBJECT::SingleThreadedAddReference(this);
    return 0;
  }
  v8 = 0;
  if ( *(_DWORD *)(*((_QWORD *)this + 34) + 416LL) != 1 )
    goto LABEL_12;
  v11 = (__int64 *)((char *)this + 800);
  CurrentThread = GetCurrentThread();
  v8 = 14;
  v13 = NtOpenThreadToken(CurrentThread, 0xEu, 1u, (PHANDLE)this + 100);
  switch ( v13 )
  {
    case -1073741700:
      v14 = 4294967293LL;
LABEL_10:
      *v11 = v14;
LABEL_11:
      v8 = 0;
LABEL_12:
      *((_DWORD *)this + 4) += 2;
      _InterlockedOr(v17, 0);
      if ( dword_1800FE624 )
      {
        for ( i = 0; i < 4; ++i )
        {
          a3 = (struct LRPC_CAUSAL_FLOW *)"HbBr";
          if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 114 )
            goto LABEL_19;
        }
        if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
        {
          LOBYTE(v3) = 43;
          LOBYTE(a3) = 114;
          McTemplateU0uuxxx_EtwEventWriteTransfer(
            *((_DWORD *)this + 3),
            *((_DWORD *)this + 4),
            (_DWORD)a3,
            v3,
            (char)this,
            *((_DWORD *)this + 3),
            *((_DWORD *)this + 4));
        }
      }
      goto LABEL_19;
    case -1073741790:
      v8 = 5;
      break;
    case -1073741658:
      v14 = 4294967294LL;
      goto LABEL_10;
    case 0:
      goto LABEL_11;
  }
  *v11 = 0;
  v18[2] = v13;
  v18[0] = 3;
  RpcpErrorAddRecord(2u, v8, 0x460u, 1, (struct tagParam *)v18);
LABEL_19:
  if ( v4 )
  {
    _InterlockedAnd((volatile signed __int32 *)this + 72, 0xFFFFFBFF);
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v4 + 2);
    v16 = (struct LRPC_CAUSAL_FLOW **)*((_QWORD *)v4 + 16);
    if ( *v16 != (struct LRPC_CAUSAL_FLOW *)((char *)v4 + 120) )
      __fastfail(3u);
    *((_QWORD *)this + 102) = (char *)v4 + 120;
    *((_QWORD *)this + 103) = v16;
    *v16 = (LRPC_CCALL *)((char *)this + 816);
    *((_QWORD *)v4 + 16) = (char *)this + 816;
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v4 + 2);
    REFERENCED_OBJECT::AddReference(v4);
    *((_QWORD *)this + 70) = v4;
  }
  return v8;
}

```

## disassembly

```asm
0x18001aa68  push    rbx
0x18001aa6a  push    rbp
0x18001aa6b  push    rsi
0x18001aa6c  push    rdi
0x18001aa6d  push    r14
0x18001aa6f  sub     rsp, 60h
0x18001aa73  mov     r9, [rcx+118h]
0x18001aa7a  mov     rsi, r8
0x18001aa7d  mov     rdi, rcx
0x18001aa80  mov     eax, 1
0x18001aa85  lock xadd [r9+0BCh], eax
0x18001aa8e  mov     [rcx+280h], rdx
0x18001aa95  inc     eax
0x18001aa97  mov     [rcx+124h], eax
0x18001aa9d  xor     ebp, ebp
0x18001aa9f  mov     [rcx+2A0h], ebp
0x18001aaa5  mov     dword ptr [rcx+2C0h], 0C0021018h
0x18001aaaf  mov     rcx, [rcx+2C8h]; lpMem
0x18001aab6  test    rcx, rcx
0x18001aab9  jnz     short loc_18001AAF7
0x18001aabb  mov     [rdi+2A8h], rbp
0x18001aac2  mov     [rdi+250h], rbp
0x18001aac9  mov     [rdi+318h], ebp
0x18001aacf  mov     [rdi+12Ch], ebp
0x18001aad5  mov     eax, [rdi+120h]
0x18001aadb  test    al, 2
0x18001aadd  jnz     short loc_18001AB10
0x18001aadf  mov     rcx, rdi; this
0x18001aae2  call    ?SingleThreadedAddReference@REFERENCED_OBJECT@@QEAAXXZ; REFERENCED_OBJECT::SingleThreadedAddReference(void)
0x18001aae7  mov     ebx, ebp
0x18001aae9  mov     eax, ebx
0x18001aaeb  add     rsp, 60h
0x18001aaef  pop     r14
0x18001aaf1  pop     rdi
0x18001aaf2  pop     rsi
0x18001aaf3  pop     rbp
0x18001aaf4  pop     rbx
0x18001aaf5  retn
0x18001aaf7  mov     rbx, [rcx]
0x18001aafa  call    FreeEEInfoRecord
0x18001aaff  mov     rcx, rbx
0x18001ab02  test    rbx, rbx
0x18001ab05  jnz     short loc_18001AAF7
0x18001ab07  mov     [rdi+2C8h], rbp
0x18001ab0e  jmp     short loc_18001AABB
0x18001ab10  mov     rax, [rdi+110h]
0x18001ab17  mov     ebx, ebp
0x18001ab19  cmp     dword ptr [rax+1A0h], 1
0x18001ab20  jnz     short loc_18001AB66
0x18001ab22  lea     r14, [rdi+320h]
0x18001ab29  call    cs:__imp_GetCurrentThread
0x18001ab30  nop     dword ptr [rax+rax+00h]
0x18001ab35  mov     ebx, 0Eh
0x18001ab3a  mov     r9, r14; TokenHandle
0x18001ab3d  mov     edx, ebx; DesiredAccess
0x18001ab3f  mov     rcx, rax; ThreadHandle
0x18001ab42  mov     r8b, 1; OpenAsSelf
0x18001ab45  call    cs:__imp_NtOpenThreadToken
0x18001ab4c  nop     dword ptr [rax+rax+00h]
0x18001ab51  cmp     eax, 0C000007Ch
0x18001ab56  jnz     loc_18001AC35
0x18001ab5c  mov     eax, 0FFFFFFFDh
0x18001ab61  mov     [r14], rax
0x18001ab64  mov     ebx, ebp
0x18001ab66  mov     eax, [rdi+10h]
0x18001ab69  add     eax, 2
0x18001ab6c  mov     [rdi+10h], eax
0x18001ab6f  lock or [rsp+88h+var_88], ebp
0x18001ab73  movsxd  rdx, dword ptr [rdi+10h]
0x18001ab77  cmp     cs:dword_1800FE624, ebp
0x18001ab7d  jz      short loc_18001ABA4
0x18001ab7f  mov     ecx, ebp
0x18001ab81  cmp     ecx, 4
0x18001ab84  jnb     short loc_18001AB9B
0x18001ab86  movsxd  rax, ecx
0x18001ab89  lea     r8, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18001ab90  cmp     byte ptr [rax+r8], 72h ; 'r'
0x18001ab95  jz      short loc_18001ABA4
0x18001ab97  inc     ecx
0x18001ab99  jmp     short loc_18001AB81
0x18001ab9b  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18001aba2  jnz     short loc_18001AC12
0x18001aba4  test    rsi, rsi
0x18001aba7  jz      loc_18001AAE9
0x18001abad  lock and dword ptr [rdi+120h], 0FFFFFBFFh
0x18001abb8  lea     rcx, [rsi+50h]; CriticalSection
0x18001abbc  call    cs:__imp_RtlEnterCriticalSection
0x18001abc3  nop     dword ptr [rax+rax+00h]
0x18001abc8  lea     rdx, [rsi+78h]
0x18001abcc  mov     r8, [rdx+8]
0x18001abd0  cmp     [r8], rdx
0x18001abd3  jnz     loc_18001AC94
0x18001abd9  lea     rax, [rdi+330h]
0x18001abe0  mov     [rax], rdx
0x18001abe3  lea     rcx, [rsi+50h]; CriticalSection
0x18001abe7  mov     [rax+8], r8
0x18001abeb  mov     [r8], rax
0x18001abee  mov     [rdx+8], rax
0x18001abf2  call    cs:__imp_RtlLeaveCriticalSection
0x18001abf9  nop     dword ptr [rax+rax+00h]
0x18001abfe  mov     rcx, rsi; this
0x18001ac01  call    ?AddReference@REFERENCED_OBJECT@@QEAAHXZ; REFERENCED_OBJECT::AddReference(void)
0x18001ac06  mov     [rdi+230h], rsi
0x18001ac0d  jmp     loc_18001AAE9
0x18001ac12  movsxd  rcx, dword ptr [rdi+0Ch]
0x18001ac16  mov     r9b, 2Bh ; '+'
0x18001ac19  mov     [rsp+88h+var_58], rdx
0x18001ac1e  mov     r8b, 72h ; 'r'
0x18001ac21  mov     [rsp+88h+var_60], rcx
0x18001ac26  mov     [rsp+88h+var_68], rdi
0x18001ac2b  call    McTemplateU0uuxxx_EtwEventWriteTransfer
0x18001ac30  jmp     loc_18001ABA4
0x18001ac35  cmp     eax, 0C0000022h
0x18001ac3a  jz      short loc_18001AC57
0x18001ac3c  cmp     eax, 0C00000A6h
0x18001ac41  jz      short loc_18001AC4D
0x18001ac43  test    eax, eax
0x18001ac45  jz      loc_18001AB64
0x18001ac4b  jmp     short loc_18001AC5C
0x18001ac4d  mov     eax, 0FFFFFFFEh
0x18001ac52  jmp     loc_18001AB61
0x18001ac57  mov     ebx, 5
0x18001ac5c  mov     rcx, rbp
0x18001ac5f  mov     r9d, 1; int
0x18001ac65  mov     [r14], rcx
0x18001ac68  mov     r8d, 460h; unsigned __int16
0x18001ac6e  mov     [rsp+88h+var_40], eax
0x18001ac72  mov     edx, ebx; int
0x18001ac74  lea     rax, [rsp+88h+var_48]
0x18001ac79  mov     [rsp+88h+var_48], 3
0x18001ac81  lea     ecx, [r9+1]; unsigned int
0x18001ac85  mov     [rsp+88h+var_68], rax; struct tagParam *
0x18001ac8a  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18001ac8f  jmp     loc_18001ABA4
0x18001ac94  mov     ecx, 3
0x18001ac99  int     29h; Win8: RtlFailFast(ecx)
```
