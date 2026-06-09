# LRPC_BINDING_HANDLE::Unbind(int)

- ea: `0x18002fff0`
- end: `0x1800303be`
- name: `?Unbind@LRPC_BINDING_HANDLE@@UEAAXH@Z`
- size: `974`
- prototype: `void __fastcall(LRPC_BINDING_HANDLE *__hidden this, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180030df0`

## callees

- `0x180022e80`
- `0x180022fb8`
- `0x180028670`
- `0x18002fff0`
- `0x1800303d0`
- `0x180030b80`
- `0x180031efc`
- `0x180034b14`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!NtAlpcDeleteSecurityContext` at `0x180030130`
- `ntdll!NtAlpcDeleteSecurityContext` at `0x180030130`
- `ntdll!RtlLeaveCriticalSection` at `0x180030056`
- `ntdll!RtlLeaveCriticalSection` at `0x180030056`
- `ntdll!RtlEnterCriticalSection` at `0x180030031`
- `ntdll!RtlEnterCriticalSection` at `0x180030031`

## pseudocode

```c
void __fastcall LRPC_BINDING_HANDLE::Unbind(LRPC_BINDING_HANDLE *this, int a2)
{
  LRPC_CASSOCIATION *v4; // rdi
  __int64 v5; // r8
  int v6; // eax
  struct _LIST_ENTRY *v7; // rdx
  struct _LIST_ENTRY *v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rdi
  unsigned int i; // ecx
  unsigned int j; // ecx
  __int64 v14; // rcx
  int v15; // eax
  int v16; // [rsp+30h] [rbp-81h]
  int v17; // [rsp+38h] [rbp-79h]
  char v18; // [rsp+48h] [rbp-69h] BYREF
  char v19; // [rsp+50h] [rbp-61h] BYREF
  __int64 v20; // [rsp+58h] [rbp-59h] BYREF
  __int64 v21; // [rsp+60h] [rbp-51h] BYREF
  _QWORD v22[2]; // [rsp+68h] [rbp-49h] BYREF
  _BYTE v23[16]; // [rsp+78h] [rbp-39h] BYREF
  char *v24; // [rsp+88h] [rbp-29h]
  __int64 v25; // [rsp+90h] [rbp-21h]
  char *v26; // [rsp+98h] [rbp-19h]
  __int64 v27; // [rsp+A0h] [rbp-11h]
  __int64 *v28; // [rsp+A8h] [rbp-9h]
  __int64 v29; // [rsp+B0h] [rbp-1h]
  __int64 *v30; // [rsp+B8h] [rbp+7h]
  __int64 v31; // [rsp+C0h] [rbp+Fh]
  __int64 *v32; // [rsp+C8h] [rbp+17h]
  __int64 v33; // [rsp+D0h] [rbp+1Fh]

  v4 = 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 304));
  v6 = *((_DWORD *)this + 99);
  *((_QWORD *)this + 79) = 0;
  if ( v6 >= 5 )
  {
    if ( v6 >= 9 )
    {
      v7 = (struct _LIST_ENTRY *)((char *)this + 600);
      v8 = (struct _LIST_ENTRY *)*((_QWORD *)this + 75);
      if ( v8 != (struct _LIST_ENTRY *)((char *)this + 600) )
      {
        do
        {
          v8[7].Flink = 0;
          v8 = v8->Flink;
        }
        while ( v8 != v7 );
        LRPC_CASSOCIATION::SendCausalFlowListForCleanup(*((LRPC_CASSOCIATION **)this + 61), v7);
        *((_DWORD *)this + 148) = 0;
      }
    }
    v9 = *((_DWORD *)this + 99);
    if ( v9 >= 5 )
    {
      if ( v9 >= 9 )
      {
        v10 = *((_QWORD *)this + 53);
        if ( v10 )
        {
          v11 = *((_QWORD *)this + 61);
          if ( dword_1800FE624 )
          {
            for ( i = 0; i < 4; ++i )
            {
              if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 76 )
                goto LABEL_17;
            }
            if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
            {
              v20 = *(_QWORD *)(v11 + 136);
              v21 = v10;
              v24 = &v18;
              v22[0] = 2;
              v26 = &v19;
              v28 = &v20;
              v30 = &v21;
              v32 = v22;
              v19 = 68;
              v18 = 76;
              v25 = 1;
              v27 = 1;
              v29 = 8;
              v31 = 8;
              v33 = 8;
              McGenEventWrite_EtwEventWriteTransfer(&RpcEtwGuid_Context, (__int64)RPCLogEvent, v5, 6, (__int64)v23);
            }
          }
LABEL_17:
          NtAlpcDeleteSecurityContext(*(_QWORD *)(v11 + 136), 0, *((_QWORD *)this + 53));
          *((_QWORD *)this + 53) = 0;
        }
        *((_DWORD *)this + 124) &= ~1u;
        LRPC_BASE_BINDING_HANDLE::FreeCachedCalls(this);
      }
      *((_DWORD *)this + 124) &= ~0x40u;
      v4 = (LRPC_CASSOCIATION *)*((_QWORD *)this + 61);
      *((_QWORD *)this + 61) = 0;
    }
    if ( (*((_DWORD *)this + 124) & 0x10) != 0 )
    {
      (*(void (__fastcall **)(LRPC_BINDING_HANDLE *))(*(_QWORD *)this + 392LL))(this);
      v15 = *((_DWORD *)this + 99);
      if ( a2 )
      {
        if ( v15 > 1 )
        {
          EpFreeLookupHandle(*((void **)this + 9));
          *((_QWORD *)this + 9) = 0;
          if ( dword_1800FE624 )
            LogEventToEtw(0x68u, 0x3Du, (__int64)this, 34, (int)(*((_DWORD *)this + 99) << 16) | 1LL);
          *((_DWORD *)this + 99) = 1;
        }
      }
      else
      {
        LogEvent(0x68u, 0x3Du, this, (void *)0x22, (v15 << 16) | 2LL, v16, v17);
        *((_DWORD *)this + 99) = 2;
      }
    }
    else
    {
      if ( dword_1800FE624 )
      {
        for ( j = 0; j < 4; ++j )
        {
          if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[j] == 104 )
            goto LABEL_28;
        }
        if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
        {
          v14 = (int)(*((_DWORD *)this + 99) << 16);
          v24 = &v19;
          v20 = v14 | 4;
          v26 = &v18;
          v21 = 34;
          v28 = v22;
          v30 = &v21;
          v32 = &v20;
          v22[0] = this;
          v18 = 61;
          v19 = 104;
          v25 = 1;
          v27 = 1;
          v29 = 8;
          v31 = 8;
          v33 = 8;
          McGenEventWrite_EtwEventWriteTransfer(&RpcEtwGuid_Context, (__int64)RPCLogEvent, v5, 6, (__int64)v23);
        }
      }
LABEL_28:
      *((_DWORD *)this + 99) = 4;
    }
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 304));
  if ( v4 )
    LRPC_CASSOCIATION::RemoveReference(v4);
}

```

## disassembly

```asm
0x18002fff0  mov     r11, rsp
0x18002fff3  push    rbp
0x18002fff4  push    rdi
0x18002fff5  lea     rbp, [r11-5Fh]
0x18002fff9  sub     rsp, 0F8h
0x180030000  mov     rax, cs:__security_cookie
0x180030007  xor     rax, rsp
0x18003000a  mov     [rbp+57h+var_30], rax
0x18003000e  mov     [r11+10h], rbx
0x180030012  mov     rbx, rcx
0x180030015  mov     [r11+18h], rsi
0x180030019  add     rcx, 130h; CriticalSection
0x180030020  mov     [r11-20h], r14
0x180030024  mov     r14d, edx
0x180030027  mov     [r11-28h], r15
0x18003002b  xor     r15d, r15d
0x18003002e  mov     edi, r15d
0x180030031  call    cs:__imp_RtlEnterCriticalSection
0x180030038  nop     dword ptr [rax+rax+00h]
0x18003003d  mov     eax, [rbx+18Ch]
0x180030043  mov     [rbx+278h], r15
0x18003004a  cmp     eax, 5
0x18003004d  jge     short loc_1800300A6
0x18003004f  lea     rcx, [rbx+130h]; CriticalSection
0x180030056  call    cs:__imp_RtlLeaveCriticalSection
0x18003005d  nop     dword ptr [rax+rax+00h]
0x180030062  mov     r15, [rsp+100h+var_20]
0x18003006a  mov     r14, [rsp+100h+var_18]
0x180030072  mov     rsi, [rsp+100h+arg_10]
0x18003007a  mov     rbx, [rsp+100h+arg_8]
0x180030082  test    rdi, rdi
0x180030085  jz      short loc_18003008F
0x180030087  mov     rcx, rdi; this
0x18003008a  call    ?RemoveReference@LRPC_CASSOCIATION@@UEAAXXZ; LRPC_CASSOCIATION::RemoveReference(void)
0x18003008f  mov     rcx, [rbp+57h+var_30]
0x180030093  xor     rcx, rsp; StackCookie
0x180030096  call    __security_check_cookie
0x18003009b  add     rsp, 0F8h
0x1800300a2  pop     rdi
0x1800300a3  pop     rbp
0x1800300a4  retn
0x1800300a6  mov     [rsp+0F0h], r12
0x1800300ae  cmp     eax, 9
0x1800300b1  jl      short loc_1800300C6
0x1800300b3  lea     rdx, [rbx+258h]; struct _LIST_ENTRY *
0x1800300ba  mov     rax, [rdx]
0x1800300bd  cmp     rax, rdx
0x1800300c0  jnz     loc_1800301B4
0x1800300c6  mov     eax, [rbx+18Ch]
0x1800300cc  lea     r12, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x1800300d3  cmp     eax, 5
0x1800300d6  jl      loc_180030167
0x1800300dc  cmp     eax, 9
0x1800300df  jl      short loc_180030152
0x1800300e1  mov     rdx, [rbx+1A8h]
0x1800300e8  test    rdx, rdx
0x1800300eb  jz      short loc_180030143
0x1800300ed  cmp     cs:dword_1800FE624, r15d
0x1800300f4  mov     rdi, [rbx+1E8h]
0x1800300fb  jz      short loc_180030120
0x1800300fd  mov     ecx, r15d
0x180030100  cmp     ecx, 4
0x180030103  jnb     short loc_180030113
0x180030105  movsxd  rax, ecx
0x180030108  cmp     byte ptr [rax+r12], 4Ch ; 'L'
0x18003010d  jz      short loc_180030120
0x18003010f  inc     ecx
0x180030111  jmp     short loc_180030100
0x180030113  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18003011a  jnz     loc_180030277
0x180030120  mov     r8, [rbx+1A8h]
0x180030127  xor     edx, edx
0x180030129  mov     rcx, [rdi+88h]
0x180030130  call    cs:__imp_NtAlpcDeleteSecurityContext
0x180030137  nop     dword ptr [rax+rax+00h]
0x18003013c  mov     [rbx+1A8h], r15
0x180030143  and     dword ptr [rbx+1F0h], 0FFFFFFFEh
0x18003014a  mov     rcx, rbx; this
0x18003014d  call    ?FreeCachedCalls@LRPC_BASE_BINDING_HANDLE@@IEAAXXZ; LRPC_BASE_BINDING_HANDLE::FreeCachedCalls(void)
0x180030152  and     dword ptr [rbx+1F0h], 0FFFFFFBFh
0x180030159  mov     rdi, [rbx+1E8h]
0x180030160  mov     [rbx+1E8h], r15
0x180030167  mov     eax, [rbx+1F0h]
0x18003016d  test    al, 10h
0x18003016f  jnz     loc_18003030D
0x180030175  cmp     cs:dword_1800FE624, r15d
0x18003017c  jz      short loc_18003019D
0x18003017e  mov     ecx, r15d
0x180030181  cmp     ecx, 4
0x180030184  jnb     short loc_180030194
0x180030186  movsxd  rax, ecx
0x180030189  cmp     byte ptr [rax+r12], 68h ; 'h'
0x18003018e  jz      short loc_18003019D
0x180030190  inc     ecx
0x180030192  jmp     short loc_180030181
0x180030194  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18003019b  jnz     short loc_1800301D8
0x18003019d  mov     dword ptr [rbx+18Ch], 4
0x1800301a7  mov     r12, [rsp+0F0h]
0x1800301af  jmp     loc_18003004F
0x1800301b4  mov     [rax+70h], r15
0x1800301b8  mov     rax, [rax]
0x1800301bb  cmp     rax, rdx
0x1800301be  jnz     short loc_1800301B4
0x1800301c0  mov     rcx, [rbx+1E8h]; this
0x1800301c7  call    ?SendCausalFlowListForCleanup@LRPC_CASSOCIATION@@QEAAXPEAU_LIST_ENTRY@@@Z; LRPC_CASSOCIATION::SendCausalFlowListForCleanup(_LIST_ENTRY *)
0x1800301cc  mov     [rbx+250h], r15d
0x1800301d3  jmp     loc_1800300C6
0x1800301d8  mov     eax, [rbx+18Ch]
0x1800301de  lea     rdx, RPCLogEvent
0x1800301e5  shl     eax, 10h
0x1800301e8  mov     r9d, 6
0x1800301ee  movsxd  rcx, eax
0x1800301f1  lea     rax, [rbp+57h+var_B8]
0x1800301f5  mov     [rbp+57h+var_80], rax
0x1800301f9  or      rcx, 4
0x1800301fd  lea     rax, [rbp+57h+var_C0]
0x180030201  mov     [rbp+57h+var_B0], rcx
0x180030205  mov     [rbp+57h+var_70], rax
0x180030209  lea     rcx, RpcEtwGuid_Context
0x180030210  lea     rax, [rbp+57h+var_A0]
0x180030214  mov     [rbp+57h+var_A8], 22h ; '"'
0x18003021c  mov     [rbp+57h+var_60], rax
0x180030220  lea     rax, [rbp+57h+var_A8]
0x180030224  mov     [rbp+57h+var_50], rax
0x180030228  lea     rax, [rbp+57h+var_B0]
0x18003022c  mov     [rbp+57h+var_40], rax
0x180030230  lea     rax, [rbp+57h+var_90]
0x180030234  mov     [rsp+20h], rax
0x180030239  mov     [rbp+57h+var_A0], rbx
0x18003023d  mov     [rbp+57h+var_C0], 3Dh ; '='
0x180030241  mov     [rbp+57h+var_B8], 68h ; 'h'
0x180030245  mov     [rbp+57h+var_78], 1
0x18003024d  mov     [rbp+57h+var_68], 1
0x180030255  mov     [rbp+57h+var_58], 8
0x18003025d  mov     [rbp+57h+var_48], 8
0x180030265  mov     [rbp+57h+var_38], 8
0x18003026d  call    McGenEventWrite_EtwEventWriteTransfer
0x180030272  jmp     loc_18003019D
0x180030277  mov     rax, [rdi+88h]
0x18003027e  lea     rcx, RpcEtwGuid_Context
0x180030285  mov     [rbp+57h+var_B0], rax
0x180030289  mov     r9d, 6
0x18003028f  lea     rax, [rbp+57h+var_C0]
0x180030293  mov     [rbp+57h+var_A8], rdx
0x180030297  mov     [rbp+57h+var_80], rax
0x18003029b  lea     rdx, RPCLogEvent
0x1800302a2  lea     rax, [rbp+57h+var_B8]
0x1800302a6  mov     [rbp+57h+var_A0], 2
0x1800302ae  mov     [rbp+57h+var_70], rax
0x1800302b2  lea     rax, [rbp+57h+var_B0]
0x1800302b6  mov     [rbp+57h+var_60], rax
0x1800302ba  lea     rax, [rbp+57h+var_A8]
0x1800302be  mov     [rbp+57h+var_50], rax
0x1800302c2  lea     rax, [rbp+57h+var_A0]
0x1800302c6  mov     [rbp+57h+var_40], rax
0x1800302ca  lea     rax, [rbp+57h+var_90]
0x1800302ce  mov     [rsp+20h], rax
0x1800302d3  mov     [rbp+57h+var_B8], 44h ; 'D'
0x1800302d7  mov     [rbp+57h+var_C0], 4Ch ; 'L'
0x1800302db  mov     [rbp+57h+var_78], 1
0x1800302e3  mov     [rbp+57h+var_68], 1
0x1800302eb  mov     [rbp+57h+var_58], 8
0x1800302f3  mov     [rbp+57h+var_48], 8
0x1800302fb  mov     [rbp+57h+var_38], 8
0x180030303  call    McGenEventWrite_EtwEventWriteTransfer
0x180030308  jmp     loc_180030120
0x18003030d  mov     rax, [rbx]
0x180030310  mov     rcx, rbx
0x180030313  mov     rax, [rax+188h]
0x18003031a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003031f  mov     eax, [rbx+18Ch]
0x180030325  test    r14d, r14d
0x180030328  jz      short loc_180030387
0x18003032a  cmp     eax, 1
0x18003032d  jle     loc_1800301A7
0x180030333  mov     rcx, [rbx+48h]; lpMem
0x180030337  call    EpFreeLookupHandle
0x18003033c  mov     [rbx+48h], r15
0x180030340  cmp     cs:dword_1800FE624, r15d
0x180030347  jz      short loc_180030370
0x180030349  mov     eax, [rbx+18Ch]
0x18003034f  mov     r9d, 22h ; '"'; __int64
0x180030355  shl     eax, 10h
0x180030358  mov     r8, rbx; __int64
0x18003035b  movsxd  rcx, eax
0x18003035e  mov     dl, 3Dh ; '='; unsigned __int8
0x180030360  or      rcx, 1
0x180030364  mov     [rsp+20h], rcx; __int64
0x180030369  mov     cl, 68h ; 'h'; unsigned __int8
0x18003036b  call    ?LogEventToEtw@@YAXEE_J00@Z; LogEventToEtw(uchar,uchar,__int64,__int64,__int64)
0x180030370  mov     r12, [rsp+0F0h]
0x180030378  mov     dword ptr [rbx+18Ch], 1
0x180030382  jmp     loc_18003004F
0x180030387  shl     eax, 10h
0x18003038a  mov     r9d, 22h ; '"'; void *
0x180030390  cdqe
0x180030392  mov     r8, rbx; void *
0x180030395  or      rax, 2
0x180030399  mov     dl, 3Dh ; '='; unsigned __int8
0x18003039b  mov     cl, 68h ; 'h'; unsigned __int8
0x18003039d  mov     [rsp+20h], rax; unsigned __int64
0x1800303a2  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x1800303a7  mov     r12, [rsp+0F0h]
0x1800303af  mov     dword ptr [rbx+18Ch], 2
0x1800303b9  jmp     loc_18003004F
```
