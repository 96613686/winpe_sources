# HTTP2EndpointReceiver::DirectReceiveComplete(uchar * *,ulong *,void * *,int *)

- ea: `0x180008b30`
- end: `0x180008d18`
- name: `?DirectReceiveComplete@HTTP2EndpointReceiver@@UEAAJPEAPEAEPEAKPEAPEAXPEAH@Z`
- size: `488`
- prototype: `__int64 __usercall@<rax>(HTTP2EndpointReceiver *__hidden this@<rcx>, unsigned __int8 **@<rdx>, unsigned int *@<r8>, void **@<r9>, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005634`
- `0x180008b30`
- `0x1800167d0`
- `0x18001b930`
- `0x18001ec2c`
- `0x180025010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180008c54`
- `ntdll!RtlLeaveCriticalSection` at `0x180008c54`
- `ntdll!RtlEnterCriticalSection` at `0x180008b8b`
- `ntdll!RtlEnterCriticalSection` at `0x180008b8b`

## pseudocode

```c
__int64 __fastcall HTTP2EndpointReceiver::DirectReceiveComplete(
        HTTP2EndpointReceiver *this,
        unsigned __int8 **a2,
        unsigned int *a3,
        void **a4,
        int *a5)
{
  int v6; // r9d
  __int64 v10; // rax
  unsigned int v11; // r13d
  unsigned int v12; // edi
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rsi
  unsigned int v15; // r15d
  int v16; // r14d
  unsigned int v17; // r12d
  __int64 v18; // rdx
  unsigned int v19; // ebx
  unsigned int v21; // [rsp+30h] [rbp-18h] BYREF
  __int64 v22; // [rsp+38h] [rbp-10h] BYREF
  unsigned int v23; // [rsp+90h] [rbp+48h] BYREF
  unsigned int v24; // [rsp+98h] [rbp+50h] BYREF
  unsigned int v25; // [rsp+A0h] [rbp+58h] BYREF
  void **v26; // [rsp+A8h] [rbp+60h]

  v26 = a4;
  v21 = 0;
  v6 = *((_DWORD *)this + 44);
  v22 = 0;
  *a5 = v6;
  v10 = *((_QWORD *)this + 3);
  v11 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  *a4 = *(void **)(v10 + 48);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 112));
  _InterlockedIncrement((volatile signed __int32 *)this + 39);
  v12 = *((_DWORD *)this + 47);
  *((_DWORD *)this + 38) = 0;
  v13 = (unsigned __int64)QUEUE::TakeOffQueue((HTTP2EndpointReceiver *)((char *)this + 32), &v23);
  if ( !*((_DWORD *)this + 11) )
    *((_DWORD *)this + 47) = 0;
  LODWORD(a5) = 0;
  v14 = v13 & 0xFFFFFFFFFFFFFFFEuLL;
  *a2 = (unsigned __int8 *)(v13 & 0xFFFFFFFFFFFFFFFEuLL);
  v15 = v23;
  *a3 = v23;
  v16 = 0;
  if ( v12 == 2 && (v13 & 1) == 0 )
  {
    HTTP2GenericReceiver::BytesConsumedNotification(this, v15, 1, (int *)&a5, &v24, &v25);
    v16 = (int)a5;
    v11 = v24;
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, unsigned int *))(**((_QWORD **)this + 3) + 144LL))(
          *((_QWORD *)this + 3),
          &v22,
          &v21);
  if ( !v17 && v16 )
    v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 3) + 104LL))(
            *((_QWORD *)this + 3),
            v11,
            v25);
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 112));
  _InterlockedDecrement((volatile signed __int32 *)this + 39);
  if ( !*((_DWORD *)this + 44)
    && v12 != 1
    && !*(_QWORD *)(*((_QWORD *)this + 2) + 96LL)
    && *v26
    && !(*((unsigned int (**)(void))pRuntimeImportTable + 26))() )
  {
    RpcpReportFatalError(21);
    __debugbreak();
  }
  v18 = (unsigned int)HTTP2TransportChannel::ReceiveComplete(this, v17, v12, v14, v15);
  if ( v12 == 1 )
  {
    v18 = 3221360681LL;
  }
  else if ( (_DWORD)v18 == -1073606646 )
  {
    v18 = 3221360649LL;
  }
  v19 = (*(__int64 (__fastcall **)(HTTP2EndpointReceiver *, __int64))(*(_QWORD *)this + 80LL))(this, v18);
  (*((void (__fastcall **)(_QWORD, __int64))pRuntimeImportTable + 75))(v21, v22);
  return v19;
}

```

## disassembly

```asm
0x180008b30  mov     [rsp-40h+arg_18], r9
0x180008b35  push    rbp
0x180008b36  push    rbx
0x180008b37  push    rsi
0x180008b38  push    rdi
0x180008b39  push    r12
0x180008b3b  push    r13
0x180008b3d  push    r14
0x180008b3f  push    r15
0x180008b41  mov     rbp, rsp
0x180008b44  sub     rsp, 48h
0x180008b48  mov     rax, [rbp+arg_20]
0x180008b4c  xor     r12d, r12d
0x180008b4f  mov     r10, r9
0x180008b52  mov     [rbp+var_18], r12d
0x180008b56  mov     r9d, [rcx+0B0h]
0x180008b5d  mov     rbx, rcx
0x180008b60  mov     [rbp+var_10], r12
0x180008b64  mov     r14, r8
0x180008b67  mov     [rax], r9d
0x180008b6a  mov     r15, rdx
0x180008b6d  mov     rax, [rcx+18h]
0x180008b71  mov     r13d, r12d
0x180008b74  mov     [rbp+arg_0], r12d
0x180008b78  mov     [rbp+arg_8], r12d
0x180008b7c  mov     [rbp+arg_10], r12d
0x180008b80  mov     rcx, [rax+30h]
0x180008b84  mov     [r10], rcx
0x180008b87  lea     rcx, [rbx+70h]; CriticalSection
0x180008b8b  call    cs:__imp_RtlEnterCriticalSection
0x180008b91  lock inc dword ptr [rbx+9Ch]
0x180008b98  mov     edi, [rbx+0BCh]
0x180008b9e  lea     rcx, [rbx+20h]; this
0x180008ba2  lea     rdx, [rbp+arg_0]; unsigned int *
0x180008ba6  mov     [rbx+98h], r12d
0x180008bad  call    ?TakeOffQueue@QUEUE@@QEAAPEAXPEAI@Z; QUEUE::TakeOffQueue(uint *)
0x180008bb2  cmp     [rbx+2Ch], r12d
0x180008bb6  jnz     short loc_180008BBF
0x180008bb8  mov     [rbx+0BCh], r12d
0x180008bbf  mov     rsi, rax
0x180008bc2  mov     dword ptr [rbp+arg_20], r12d
0x180008bc6  and     rsi, 0FFFFFFFFFFFFFFFEh
0x180008bca  mov     [r15], rsi
0x180008bcd  mov     r15d, [rbp+arg_0]
0x180008bd1  mov     [r14], r15d
0x180008bd4  mov     r14d, r12d
0x180008bd7  cmp     edi, 2
0x180008bda  jnz     short loc_180008C0F
0x180008bdc  not     eax
0x180008bde  test    al, 1
0x180008be0  jz      short loc_180008C0F
0x180008be2  lea     rax, [rbp+arg_10]
0x180008be6  mov     edx, r15d; unsigned int
0x180008be9  mov     [rsp+48h+var_20], rax; unsigned int *
0x180008bee  lea     r9, [rbp+arg_20]; int *
0x180008bf2  lea     rax, [rbp+arg_8]
0x180008bf6  mov     rcx, rbx; this
0x180008bf9  lea     r8d, [rdi-1]; int
0x180008bfd  mov     [rsp+48h+var_28], rax; unsigned int *
0x180008c02  call    ?BytesConsumedNotification@HTTP2GenericReceiver@@QEAAXKHPEAHPEAK1@Z; HTTP2GenericReceiver::BytesConsumedNotification(ulong,int,int *,ulong *,ulong *)
0x180008c07  mov     r14d, dword ptr [rbp+arg_20]
0x180008c0b  mov     r13d, [rbp+arg_8]
0x180008c0f  mov     rcx, [rbx+18h]
0x180008c13  lea     r8, [rbp+var_18]
0x180008c17  lea     rdx, [rbp+var_10]
0x180008c1b  mov     rax, [rcx]
0x180008c1e  mov     rax, [rax+90h]
0x180008c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c2a  mov     r12d, eax
0x180008c2d  test    eax, eax
0x180008c2f  jnz     short loc_180008C50
0x180008c31  test    r14d, r14d
0x180008c34  jz      short loc_180008C50
0x180008c36  mov     rcx, [rbx+18h]
0x180008c3a  mov     edx, r13d
0x180008c3d  mov     r8d, [rbp+arg_10]
0x180008c41  mov     rax, [rcx]
0x180008c44  mov     rax, [rax+68h]
0x180008c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c4d  mov     r12d, eax
0x180008c50  lea     rcx, [rbx+70h]; CriticalSection
0x180008c54  call    cs:__imp_RtlLeaveCriticalSection
0x180008c5a  lock dec dword ptr [rbx+9Ch]
0x180008c61  cmp     dword ptr [rbx+0B0h], 0
0x180008c68  jnz     short loc_180008CA8
0x180008c6a  cmp     edi, 1
0x180008c6d  jz      short loc_180008CA8
0x180008c6f  mov     rax, [rbx+10h]
0x180008c73  cmp     qword ptr [rax+60h], 0
0x180008c78  jnz     short loc_180008CA8
0x180008c7a  mov     rcx, [rbp+arg_18]
0x180008c7e  mov     rcx, [rcx]
0x180008c81  test    rcx, rcx
0x180008c84  jz      short loc_180008CA8
0x180008c86  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180008c8d  mov     rax, [rax+0D0h]
0x180008c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c99  test    eax, eax
0x180008c9b  jnz     short loc_180008CA8
0x180008c9d  xor     edx, edx
0x180008c9f  lea     ecx, [rax+15h]
0x180008ca2  call    RpcpReportFatalError
0x180008ca7  int     3; Trap to Debugger
0x180008ca8  mov     r9, rsi
0x180008cab  mov     dword ptr [rsp+48h+var_28], r15d
0x180008cb0  mov     r8d, edi
0x180008cb3  mov     edx, r12d
0x180008cb6  mov     rcx, rbx
0x180008cb9  call    ?ReceiveComplete@HTTP2TransportChannel@@UEAAJJW4tagHTTP2TrafficType@@PEAEI@Z; HTTP2TransportChannel::ReceiveComplete(long,tagHTTP2TrafficType,uchar *,uint)
0x180008cbe  mov     edx, eax
0x180008cc0  cmp     edi, 1
0x180008cc3  jnz     short loc_180008CCC
0x180008cc5  mov     edx, 0C0021029h
0x180008cca  jmp     short loc_180008CDA
0x180008ccc  cmp     edx, 0C002100Ah
0x180008cd2  mov     eax, 0C0021009h
0x180008cd7  cmovz   edx, eax
0x180008cda  mov     rax, [rbx]
0x180008cdd  mov     rcx, rbx
0x180008ce0  mov     rax, [rax+50h]
0x180008ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ce9  mov     rcx, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180008cf0  mov     ebx, eax
0x180008cf2  mov     rdx, [rbp+var_10]
0x180008cf6  mov     rax, [rcx+258h]
0x180008cfd  mov     ecx, [rbp+var_18]
0x180008d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d05  mov     eax, ebx
0x180008d07  add     rsp, 48h
0x180008d0b  pop     r15
0x180008d0d  pop     r14
0x180008d0f  pop     r13
0x180008d11  pop     r12
0x180008d13  pop     rdi
0x180008d14  pop     rsi
0x180008d15  pop     rbx
0x180008d16  pop     rbp
0x180008d17  retn
```
