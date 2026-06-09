# HTTP2FlowControlSender::FlowControlAckNotify(ulong,ulong)

- ea: `0x180009d9c`
- end: `0x180009f4f`
- name: `?FlowControlAckNotify@HTTP2FlowControlSender@@QEAAJKK@Z`
- size: `435`
- prototype: `__int64 __fastcall(HTTP2FlowControlSender *this, __int64, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180012110`
- `0x180013920`
- `0x180014850`
- `0x1800158e0`

## callees

- `0x180005428`
- `0x180009d58`
- `0x180009d9c`
- `0x180018f08`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180009ecb`
- `ntdll!RtlLeaveCriticalSection` at `0x180009f0e`
- `ntdll!RtlLeaveCriticalSection` at `0x180009ecb`
- `ntdll!RtlLeaveCriticalSection` at `0x180009f0e`
- `ntdll!RtlEnterCriticalSection` at `0x180009def`
- `ntdll!RtlEnterCriticalSection` at `0x180009def`
- `RPCRT4!I_RpcLogEvent` at `0x180009de2`
- `RPCRT4!I_RpcLogEvent` at `0x180009eef`
- `RPCRT4!I_RpcLogEvent` at `0x180009f33`
- `RPCRT4!I_RpcLogEvent` at `0x180009de2`
- `RPCRT4!I_RpcLogEvent` at `0x180009eef`
- `RPCRT4!I_RpcLogEvent` at `0x180009f33`

## pseudocode

```c
__int64 __fastcall HTTP2FlowControlSender::FlowControlAckNotify(HTTP2FlowControlSender *this, __int64 a2, int a3)
{
  int v4; // ebx
  HTTP2FlowControlSender *v5; // rdi
  HTTP2FlowControlSender *v6; // r8
  unsigned int v7; // eax
  _QWORD *v8; // rbx
  unsigned int v9; // ebp
  _QWORD *v10; // rsi
  int v11; // r12d
  _QWORD *v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // r15
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // [rsp+20h] [rbp-68h]

  v21 = (unsigned __int16)a3 | ((_DWORD)a2 << 16);
  v4 = a2;
  v5 = this;
  v6 = this;
  LOBYTE(a2) = 111;
  LOBYTE(this) = 50;
  I_RpcLogEvent(this, a2, v6, 16908307, v21, 0, 0);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v5 + 48));
  if ( (unsigned int)(*((_DWORD *)v5 + 22) - v4) > *((_DWORD *)v5 + 24)
    || (v7 = v4 - *((_DWORD *)v5 + 22) + a3, *((_DWORD *)v5 + 23) = v7, v7 > *((_DWORD *)v5 + 24)) )
  {
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v5 + 48));
    LOBYTE(v19) = 111;
    LOBYTE(v20) = 50;
    I_RpcLogEvent(v20, v19, v5, 131091, -1, 0, 0);
    return 1728;
  }
  else
  {
    v8 = (_QWORD *)((char *)v5 + 32);
    v9 = 0;
    v10 = (_QWORD *)*((_QWORD *)v5 + 4);
    v11 = 0;
    while ( v10 != v8 && *((_DWORD *)v10 - 4) <= *((_DWORD *)v5 + 23) )
    {
      v12 = (_QWORD *)*v8;
      if ( *(_QWORD **)(*v8 + 8LL) != v8 )
        goto LABEL_20;
      v13 = *v12;
      if ( *(_QWORD **)(*v12 + 8LL) != v12 )
        goto LABEL_20;
      *v8 = v13;
      *(_QWORD *)(v13 + 8) = v8;
      if ( v12 != v8 )
      {
        *v12 = 0;
        v12[1] = 0;
      }
      v14 = (_QWORD *)*v8;
      v9 = HTTP2Channel::BeginSimpleSubmitAsync(*((HTTP2Channel **)v5 + 3));
      if ( v9
        || (v9 = HTTP2FlowControlSender::SendInternal(v5, (struct HTTP2SendContext *)(v10 - 9), 1),
            HTTP2Channel::FinishSubmitAsync(*((HTTP2Channel **)v5 + 3)),
            v9) )
      {
        if ( v9 != -1073606614 )
        {
          v15 = *v8;
          if ( *(_QWORD **)(*v8 + 8LL) != v8 )
LABEL_20:
            __fastfail(3u);
          *v10 = v15;
          v10[1] = v8;
          *(_QWORD *)(v15 + 8) = v10;
          *v8 = v10;
          break;
        }
        v11 = 1;
      }
      v10 = v14;
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v5 + 48));
    LOBYTE(v16) = 111;
    LOBYTE(v17) = 50;
    I_RpcLogEvent(v17, v16, v5, 131091, *((_DWORD *)v5 + 23), 0, 0);
    if ( v11 )
      return (unsigned int)-1073606614;
    return v9;
  }
}

```

## disassembly

```asm
0x180009d9c  push    rbx
0x180009d9e  push    rbp
0x180009d9f  push    rsi
0x180009da0  push    rdi
0x180009da1  push    r12
0x180009da3  push    r13
0x180009da5  push    r14
0x180009da7  push    r15
0x180009da9  sub     rsp, 48h
0x180009dad  mov     r9d, edx
0x180009db0  movzx   eax, r8w
0x180009db4  shl     r9d, 10h
0x180009db8  xor     r15d, r15d
0x180009dbb  or      r9d, eax
0x180009dbe  mov     [rsp+88h+var_58], r15d
0x180009dc3  mov     esi, r8d
0x180009dc6  mov     [rsp+88h+var_60], r15d
0x180009dcb  mov     [rsp+88h+var_68], r9d
0x180009dd0  mov     ebx, edx
0x180009dd2  mov     rdi, rcx
0x180009dd5  mov     r8, rcx
0x180009dd8  mov     r9d, 1020013h
0x180009dde  mov     dl, 6Fh ; 'o'
0x180009de0  mov     cl, 32h ; '2'
0x180009de2  call    cs:__imp_I_RpcLogEvent
0x180009de8  lea     r13, [rdi+30h]
0x180009dec  mov     rcx, r13; CriticalSection
0x180009def  call    cs:__imp_RtlEnterCriticalSection
0x180009df5  mov     eax, [rdi+58h]
0x180009df8  sub     eax, ebx
0x180009dfa  cmp     eax, [rdi+60h]
0x180009dfd  ja      loc_180009F0B
0x180009e03  sub     ebx, [rdi+58h]
0x180009e06  lea     eax, [rbx+rsi]
0x180009e09  mov     [rdi+5Ch], eax
0x180009e0c  cmp     eax, [rdi+60h]
0x180009e0f  ja      loc_180009F0B
0x180009e15  lea     rbx, [rdi+20h]
0x180009e19  mov     ebp, r15d
0x180009e1c  mov     rsi, [rbx]
0x180009e1f  mov     r12d, r15d
0x180009e22  cmp     rsi, rbx
0x180009e25  jz      loc_180009EC8
0x180009e2b  mov     eax, [rdi+5Ch]
0x180009e2e  cmp     [rsi-10h], eax
0x180009e31  ja      loc_180009EC8
0x180009e37  mov     rax, [rbx]
0x180009e3a  cmp     [rax+8], rbx
0x180009e3e  jnz     loc_180009F04
0x180009e44  mov     rcx, [rax]
0x180009e47  cmp     [rcx+8], rax
0x180009e4b  jnz     loc_180009F04
0x180009e51  mov     [rbx], rcx
0x180009e54  mov     [rcx+8], rbx
0x180009e58  cmp     rax, rbx
0x180009e5b  jz      short loc_180009E64
0x180009e5d  mov     [rax], r15
0x180009e60  mov     [rax+8], r15
0x180009e64  mov     rcx, [rdi+18h]; this
0x180009e68  mov     r15, [rbx]
0x180009e6b  call    ?BeginSimpleSubmitAsync@HTTP2Channel@@QEAAJXZ; HTTP2Channel::BeginSimpleSubmitAsync(void)
0x180009e70  mov     ebp, eax
0x180009e72  test    eax, eax
0x180009e74  jnz     short loc_180009E95
0x180009e76  lea     r8d, [rax+1]; int
0x180009e7a  mov     rcx, rdi; this
0x180009e7d  lea     rdx, [rsi-48h]; struct HTTP2SendContext *
0x180009e81  call    ?SendInternal@HTTP2FlowControlSender@@AEAAJPEAVHTTP2SendContext@@H@Z; HTTP2FlowControlSender::SendInternal(HTTP2SendContext *,int)
0x180009e86  mov     rcx, [rdi+18h]; this
0x180009e8a  mov     ebp, eax
0x180009e8c  call    ?FinishSubmitAsync@HTTP2Channel@@QEAAXXZ; HTTP2Channel::FinishSubmitAsync(void)
0x180009e91  test    ebp, ebp
0x180009e93  jz      short loc_180009EA3
0x180009e95  cmp     ebp, 0C002102Ah
0x180009e9b  jnz     short loc_180009EAE
0x180009e9d  mov     r12d, 1
0x180009ea3  mov     rsi, r15
0x180009ea6  xor     r15d, r15d
0x180009ea9  jmp     loc_180009E22
0x180009eae  mov     rax, [rbx]
0x180009eb1  cmp     [rax+8], rbx
0x180009eb5  jnz     short loc_180009F04
0x180009eb7  mov     [rsi], rax
0x180009eba  xor     r15d, r15d
0x180009ebd  mov     [rsi+8], rbx
0x180009ec1  mov     [rax+8], rsi
0x180009ec5  mov     [rbx], rsi
0x180009ec8  mov     rcx, r13; CriticalSection
0x180009ecb  call    cs:__imp_RtlLeaveCriticalSection
0x180009ed1  mov     eax, [rdi+5Ch]
0x180009ed4  mov     r9d, 20013h
0x180009eda  mov     [rsp+88h+var_58], r15d
0x180009edf  mov     r8, rdi
0x180009ee2  mov     [rsp+88h+var_60], r15d
0x180009ee7  mov     dl, 6Fh ; 'o'
0x180009ee9  mov     cl, 32h ; '2'
0x180009eeb  mov     [rsp+88h+var_68], eax
0x180009eef  call    cs:__imp_I_RpcLogEvent
0x180009ef5  mov     eax, 0C002102Ah
0x180009efa  test    r12d, r12d
0x180009efd  cmovnz  ebp, eax
0x180009f00  mov     eax, ebp
0x180009f02  jmp     short loc_180009F3E
0x180009f04  mov     ecx, 3
0x180009f09  int     29h; Win8: RtlFailFast(ecx)
0x180009f0b  mov     rcx, r13; CriticalSection
0x180009f0e  call    cs:__imp_RtlLeaveCriticalSection
0x180009f14  mov     [rsp+88h+var_58], r15d
0x180009f19  mov     r9d, 20013h
0x180009f1f  mov     [rsp+88h+var_60], r15d
0x180009f24  mov     r8, rdi
0x180009f27  mov     dl, 6Fh ; 'o'
0x180009f29  mov     [rsp+88h+var_68], 0FFFFFFFFh
0x180009f31  mov     cl, 32h ; '2'
0x180009f33  call    cs:__imp_I_RpcLogEvent
0x180009f39  mov     eax, 6C0h
0x180009f3e  add     rsp, 48h
0x180009f42  pop     r15
0x180009f44  pop     r14
0x180009f46  pop     r13
0x180009f48  pop     r12
0x180009f4a  pop     rdi
0x180009f4b  pop     rsi
0x180009f4c  pop     rbp
0x180009f4d  pop     rbx
0x180009f4e  retn
```
