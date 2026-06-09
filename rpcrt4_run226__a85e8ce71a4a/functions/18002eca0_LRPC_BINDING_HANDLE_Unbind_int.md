# LRPC_BINDING_HANDLE::Unbind(int)

- ea: `0x18002eca0`
- end: `0x18002f05b`
- name: `?Unbind@LRPC_BINDING_HANDLE@@UEAAXH@Z`
- size: `955`
- prototype: `void __fastcall(LRPC_BINDING_HANDLE *__hidden this, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002fa70`

## callees

- `0x180021ce0`
- `0x180021e18`
- `0x1800274e0`
- `0x18002eca0`
- `0x18002f070`
- `0x18002f800`
- `0x180031760`
- `0x180033aec`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!NtAlpcDeleteSecurityContext` at `0x18002edd3`
- `ntdll!NtAlpcDeleteSecurityContext` at `0x18002edd3`
- `ntdll!RtlLeaveCriticalSection` at `0x18002ed00`
- `ntdll!RtlLeaveCriticalSection` at `0x18002ed00`
- `ntdll!RtlEnterCriticalSection` at `0x18002ece1`
- `ntdll!RtlEnterCriticalSection` at `0x18002ece1`

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
          if ( dword_1800F9624 )
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
          if ( dword_1800F9624 )
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
      if ( dword_1800F9624 )
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
0x18002eca0  mov     r11, rsp
0x18002eca3  push    rbp
0x18002eca4  push    rdi
0x18002eca5  lea     rbp, [r11-5Fh]
0x18002eca9  sub     rsp, 0F8h
0x18002ecb0  mov     rax, cs:__security_cookie
0x18002ecb7  xor     rax, rsp
0x18002ecba  mov     [rbp+57h+var_30], rax
0x18002ecbe  mov     [r11+10h], rbx
0x18002ecc2  mov     rbx, rcx
0x18002ecc5  mov     [r11+18h], rsi
0x18002ecc9  add     rcx, 130h; CriticalSection
0x18002ecd0  mov     [r11-20h], r14
0x18002ecd4  mov     r14d, edx
0x18002ecd7  mov     [r11-28h], r15
0x18002ecdb  xor     r15d, r15d
0x18002ecde  mov     edi, r15d
0x18002ece1  call    cs:__imp_RtlEnterCriticalSection
0x18002ece7  mov     eax, [rbx+18Ch]
0x18002eced  mov     [rbx+278h], r15
0x18002ecf4  cmp     eax, 5
0x18002ecf7  jge     short loc_18002ED49
0x18002ecf9  lea     rcx, [rbx+130h]; CriticalSection
0x18002ed00  call    cs:__imp_RtlLeaveCriticalSection
0x18002ed06  mov     r15, [rsp+100h+var_20]
0x18002ed0e  mov     r14, [rsp+100h+var_18]
0x18002ed16  mov     rsi, [rsp+100h+arg_10]
0x18002ed1e  mov     rbx, [rsp+100h+arg_8]
0x18002ed26  test    rdi, rdi
0x18002ed29  jz      short loc_18002ED33
0x18002ed2b  mov     rcx, rdi; this
0x18002ed2e  call    ?RemoveReference@LRPC_CASSOCIATION@@UEAAXXZ; LRPC_CASSOCIATION::RemoveReference(void)
0x18002ed33  mov     rcx, [rbp+57h+var_30]
0x18002ed37  xor     rcx, rsp; StackCookie
0x18002ed3a  call    __security_check_cookie
0x18002ed3f  add     rsp, 0F8h
0x18002ed46  pop     rdi
0x18002ed47  pop     rbp
0x18002ed48  retn
0x18002ed49  mov     [rsp+0F0h], r12
0x18002ed51  cmp     eax, 9
0x18002ed54  jl      short loc_18002ED69
0x18002ed56  lea     rdx, [rbx+258h]; struct _LIST_ENTRY *
0x18002ed5d  mov     rax, [rdx]
0x18002ed60  cmp     rax, rdx
0x18002ed63  jnz     loc_18002EE51
0x18002ed69  mov     eax, [rbx+18Ch]
0x18002ed6f  lea     r12, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18002ed76  cmp     eax, 5
0x18002ed79  jl      loc_18002EE04
0x18002ed7f  cmp     eax, 9
0x18002ed82  jl      short loc_18002EDEF
0x18002ed84  mov     rdx, [rbx+1A8h]
0x18002ed8b  test    rdx, rdx
0x18002ed8e  jz      short loc_18002EDE0
0x18002ed90  cmp     cs:dword_1800F9624, r15d
0x18002ed97  mov     rdi, [rbx+1E8h]
0x18002ed9e  jz      short loc_18002EDC3
0x18002eda0  mov     ecx, r15d
0x18002eda3  cmp     ecx, 4
0x18002eda6  jnb     short loc_18002EDB6
0x18002eda8  movsxd  rax, ecx
0x18002edab  cmp     byte ptr [rax+r12], 4Ch ; 'L'
0x18002edb0  jz      short loc_18002EDC3
0x18002edb2  inc     ecx
0x18002edb4  jmp     short loc_18002EDA3
0x18002edb6  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18002edbd  jnz     loc_18002EF14
0x18002edc3  mov     r8, [rbx+1A8h]
0x18002edca  xor     edx, edx
0x18002edcc  mov     rcx, [rdi+88h]
0x18002edd3  call    cs:__imp_NtAlpcDeleteSecurityContext
0x18002edd9  mov     [rbx+1A8h], r15
0x18002ede0  and     dword ptr [rbx+1F0h], 0FFFFFFFEh
0x18002ede7  mov     rcx, rbx; this
0x18002edea  call    ?FreeCachedCalls@LRPC_BASE_BINDING_HANDLE@@IEAAXXZ; LRPC_BASE_BINDING_HANDLE::FreeCachedCalls(void)
0x18002edef  and     dword ptr [rbx+1F0h], 0FFFFFFBFh
0x18002edf6  mov     rdi, [rbx+1E8h]
0x18002edfd  mov     [rbx+1E8h], r15
0x18002ee04  mov     eax, [rbx+1F0h]
0x18002ee0a  test    al, 10h
0x18002ee0c  jnz     loc_18002EFAA
0x18002ee12  cmp     cs:dword_1800F9624, r15d
0x18002ee19  jz      short loc_18002EE3A
0x18002ee1b  mov     ecx, r15d
0x18002ee1e  cmp     ecx, 4
0x18002ee21  jnb     short loc_18002EE31
0x18002ee23  movsxd  rax, ecx
0x18002ee26  cmp     byte ptr [rax+r12], 68h ; 'h'
0x18002ee2b  jz      short loc_18002EE3A
0x18002ee2d  inc     ecx
0x18002ee2f  jmp     short loc_18002EE1E
0x18002ee31  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18002ee38  jnz     short loc_18002EE75
0x18002ee3a  mov     dword ptr [rbx+18Ch], 4
0x18002ee44  mov     r12, [rsp+0F0h]
0x18002ee4c  jmp     loc_18002ECF9
0x18002ee51  mov     [rax+70h], r15
0x18002ee55  mov     rax, [rax]
0x18002ee58  cmp     rax, rdx
0x18002ee5b  jnz     short loc_18002EE51
0x18002ee5d  mov     rcx, [rbx+1E8h]; this
0x18002ee64  call    ?SendCausalFlowListForCleanup@LRPC_CASSOCIATION@@QEAAXPEAU_LIST_ENTRY@@@Z; LRPC_CASSOCIATION::SendCausalFlowListForCleanup(_LIST_ENTRY *)
0x18002ee69  mov     [rbx+250h], r15d
0x18002ee70  jmp     loc_18002ED69
0x18002ee75  mov     eax, [rbx+18Ch]
0x18002ee7b  lea     rdx, RPCLogEvent
0x18002ee82  shl     eax, 10h
0x18002ee85  mov     r9d, 6
0x18002ee8b  movsxd  rcx, eax
0x18002ee8e  lea     rax, [rbp+57h+var_B8]
0x18002ee92  mov     [rbp+57h+var_80], rax
0x18002ee96  or      rcx, 4
0x18002ee9a  lea     rax, [rbp+57h+var_C0]
0x18002ee9e  mov     [rbp+57h+var_B0], rcx
0x18002eea2  mov     [rbp+57h+var_70], rax
0x18002eea6  lea     rcx, RpcEtwGuid_Context
0x18002eead  lea     rax, [rbp+57h+var_A0]
0x18002eeb1  mov     [rbp+57h+var_A8], 22h ; '"'
0x18002eeb9  mov     [rbp+57h+var_60], rax
0x18002eebd  lea     rax, [rbp+57h+var_A8]
0x18002eec1  mov     [rbp+57h+var_50], rax
0x18002eec5  lea     rax, [rbp+57h+var_B0]
0x18002eec9  mov     [rbp+57h+var_40], rax
0x18002eecd  lea     rax, [rbp+57h+var_90]
0x18002eed1  mov     [rsp+20h], rax
0x18002eed6  mov     [rbp+57h+var_A0], rbx
0x18002eeda  mov     [rbp+57h+var_C0], 3Dh ; '='
0x18002eede  mov     [rbp+57h+var_B8], 68h ; 'h'
0x18002eee2  mov     [rbp+57h+var_78], 1
0x18002eeea  mov     [rbp+57h+var_68], 1
0x18002eef2  mov     [rbp+57h+var_58], 8
0x18002eefa  mov     [rbp+57h+var_48], 8
0x18002ef02  mov     [rbp+57h+var_38], 8
0x18002ef0a  call    McGenEventWrite_EtwEventWriteTransfer
0x18002ef0f  jmp     loc_18002EE3A
0x18002ef14  mov     rax, [rdi+88h]
0x18002ef1b  lea     rcx, RpcEtwGuid_Context
0x18002ef22  mov     [rbp+57h+var_B0], rax
0x18002ef26  mov     r9d, 6
0x18002ef2c  lea     rax, [rbp+57h+var_C0]
0x18002ef30  mov     [rbp+57h+var_A8], rdx
0x18002ef34  mov     [rbp+57h+var_80], rax
0x18002ef38  lea     rdx, RPCLogEvent
0x18002ef3f  lea     rax, [rbp+57h+var_B8]
0x18002ef43  mov     [rbp+57h+var_A0], 2
0x18002ef4b  mov     [rbp+57h+var_70], rax
0x18002ef4f  lea     rax, [rbp+57h+var_B0]
0x18002ef53  mov     [rbp+57h+var_60], rax
0x18002ef57  lea     rax, [rbp+57h+var_A8]
0x18002ef5b  mov     [rbp+57h+var_50], rax
0x18002ef5f  lea     rax, [rbp+57h+var_A0]
0x18002ef63  mov     [rbp+57h+var_40], rax
0x18002ef67  lea     rax, [rbp+57h+var_90]
0x18002ef6b  mov     [rsp+20h], rax
0x18002ef70  mov     [rbp+57h+var_B8], 44h ; 'D'
0x18002ef74  mov     [rbp+57h+var_C0], 4Ch ; 'L'
0x18002ef78  mov     [rbp+57h+var_78], 1
0x18002ef80  mov     [rbp+57h+var_68], 1
0x18002ef88  mov     [rbp+57h+var_58], 8
0x18002ef90  mov     [rbp+57h+var_48], 8
0x18002ef98  mov     [rbp+57h+var_38], 8
0x18002efa0  call    McGenEventWrite_EtwEventWriteTransfer
0x18002efa5  jmp     loc_18002EDC3
0x18002efaa  mov     rax, [rbx]
0x18002efad  mov     rcx, rbx
0x18002efb0  mov     rax, [rax+188h]
0x18002efb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efbc  mov     eax, [rbx+18Ch]
0x18002efc2  test    r14d, r14d
0x18002efc5  jz      short loc_18002F024
0x18002efc7  cmp     eax, 1
0x18002efca  jle     loc_18002EE44
0x18002efd0  mov     rcx, [rbx+48h]; lpMem
0x18002efd4  call    EpFreeLookupHandle
0x18002efd9  mov     [rbx+48h], r15
0x18002efdd  cmp     cs:dword_1800F9624, r15d
0x18002efe4  jz      short loc_18002F00D
0x18002efe6  mov     eax, [rbx+18Ch]
0x18002efec  mov     r9d, 22h ; '"'; __int64
0x18002eff2  shl     eax, 10h
0x18002eff5  mov     r8, rbx; __int64
0x18002eff8  movsxd  rcx, eax
0x18002effb  mov     dl, 3Dh ; '='; unsigned __int8
0x18002effd  or      rcx, 1
0x18002f001  mov     [rsp+20h], rcx; __int64
0x18002f006  mov     cl, 68h ; 'h'; unsigned __int8
0x18002f008  call    ?LogEventToEtw@@YAXEE_J00@Z; LogEventToEtw(uchar,uchar,__int64,__int64,__int64)
0x18002f00d  mov     r12, [rsp+0F0h]
0x18002f015  mov     dword ptr [rbx+18Ch], 1
0x18002f01f  jmp     loc_18002ECF9
0x18002f024  shl     eax, 10h
0x18002f027  mov     r9d, 22h ; '"'; void *
0x18002f02d  cdqe
0x18002f02f  mov     r8, rbx; void *
0x18002f032  or      rax, 2
0x18002f036  mov     dl, 3Dh ; '='; unsigned __int8
0x18002f038  mov     cl, 68h ; 'h'; unsigned __int8
0x18002f03a  mov     [rsp+20h], rax; unsigned __int64
0x18002f03f  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x18002f044  mov     r12, [rsp+0F0h]
0x18002f04c  mov     dword ptr [rbx+18Ch], 2
0x18002f056  jmp     loc_18002ECF9
```
