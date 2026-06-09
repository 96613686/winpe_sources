# HTTP2ChannelPointer::FreeChannelPointer(int,int,int,long)

- ea: `0x18000a4ec`
- end: `0x18000a5d4`
- name: `?FreeChannelPointer@HTTP2ChannelPointer@@QEAAXHHHJ@Z`
- size: `232`
- prototype: `void __fastcall(HTTP2ChannelPointer *this, __int64, int, int, unsigned int)`
- caller_count: `8`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006050`
- `0x180009940`
- `0x18000f1b0`
- `0x18000f250`
- `0x180012110`
- `0x180013920`
- `0x180014850`
- `0x1800158e0`

## callees

- `0x180009aa4`
- `0x18000a4ec`
- `0x180016df8`
- `0x18001b930`
- `0x180025010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18000a556`
- `KERNEL32!Sleep` at `0x18000a556`
- `RPCRT4!I_RpcLogEvent` at `0x18000a52f`
- `RPCRT4!I_RpcLogEvent` at `0x18000a52f`

## pseudocode

```c
void __fastcall HTTP2ChannelPointer::FreeChannelPointer(
        HTTP2ChannelPointer *this,
        __int64 a2,
        int a3,
        int a4,
        unsigned int a5)
{
  int v7; // ebp
  HTTP2ChannelPointer *v8; // rdi
  int v9; // eax
  HTTP2ChannelPointer *v10; // r8
  __int64 v11; // r9
  HTTP2Channel *v12; // rbx
  int v13; // edx
  signed __int32 v14[8]; // [rsp+0h] [rbp-58h] BYREF

  v7 = a2;
  v8 = this;
  _InterlockedOr(v14, 0);
  v9 = *(_DWORD *)this;
  v10 = this;
  v11 = *((_QWORD *)this + 1);
  LOBYTE(a2) = 68;
  LOBYTE(this) = 50;
  I_RpcLogEvent(this, a2, v10, v11, v9, 1, 1);
  v12 = (HTTP2Channel *)*((_QWORD *)v8 + 1);
  while ( _InterlockedCompareExchange((volatile signed __int32 *)v8, -101, 0) )
  {
    _InterlockedOr(v14, 0);
    if ( *(int *)v8 < 0 )
      return;
    Sleep(2u);
  }
  if ( v12 )
  {
    if ( v7 )
    {
      if ( a3 )
      {
        if ( !(*((unsigned int (**)(void))pRuntimeImportTable + 79))() )
        {
          RpcpReportFatalError(21);
          __debugbreak();
        }
        v13 = 1;
      }
      else
      {
        v13 = 0;
      }
      HTTP2Channel::DrainUpcallsAndFreeParentInternal(v12, v13);
    }
    if ( a4 )
      (*(void (__fastcall **)(HTTP2Channel *, _QWORD))(*(_QWORD *)v12 + 40LL))(v12, a5);
    HTTP2Channel::RemoveReference(v12);
  }
}

```

## disassembly

```asm
0x18000a4ec  mov     [rsp+arg_8], rbx
0x18000a4f1  mov     [rsp+arg_10], rbp
0x18000a4f6  push    rsi
0x18000a4f7  push    rdi
0x18000a4f8  push    r14
0x18000a4fa  sub     rsp, 40h
0x18000a4fe  mov     r14d, r9d
0x18000a501  mov     esi, r8d
0x18000a504  mov     ebp, edx
0x18000a506  mov     rdi, rcx
0x18000a509  lock or [rsp+58h+var_58], 0
0x18000a50e  mov     eax, [rcx]
0x18000a510  mov     r8, rcx
0x18000a513  mov     r9, [rcx+8]
0x18000a517  mov     dl, 44h ; 'D'
0x18000a519  mov     [rsp+58h+var_28], 1
0x18000a521  mov     cl, 32h ; '2'
0x18000a523  mov     [rsp+58h+var_30], 1
0x18000a52b  mov     [rsp+58h+var_38], eax
0x18000a52f  call    cs:__imp_I_RpcLogEvent
0x18000a535  mov     rbx, [rdi+8]
0x18000a539  mov     ecx, 0FFFFFF9Bh
0x18000a53e  xor     eax, eax
0x18000a540  lock cmpxchg [rdi], ecx
0x18000a544  jz      short loc_18000A55E
0x18000a546  lock or [rsp+58h+var_58], 0
0x18000a54b  mov     eax, [rdi]
0x18000a54d  test    eax, eax
0x18000a54f  js      short loc_18000A5C1
0x18000a551  mov     ecx, 2; dwMilliseconds
0x18000a556  call    cs:__imp_Sleep
0x18000a55c  jmp     short loc_18000A539
0x18000a55e  test    rbx, rbx
0x18000a561  jz      short loc_18000A5C1
0x18000a563  test    ebp, ebp
0x18000a565  jz      short loc_18000A59E
0x18000a567  test    esi, esi
0x18000a569  jz      short loc_18000A594
0x18000a56b  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000a572  mov     rax, [rax+278h]
0x18000a579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a57e  test    eax, eax
0x18000a580  jnz     short loc_18000A58D
0x18000a582  xor     edx, edx
0x18000a584  lea     ecx, [rax+15h]
0x18000a587  call    RpcpReportFatalError
0x18000a58c  int     3; Trap to Debugger
0x18000a58d  mov     edx, 1
0x18000a592  jmp     short loc_18000A596
0x18000a594  xor     edx, edx; int
0x18000a596  mov     rcx, rbx; this
0x18000a599  call    ?DrainUpcallsAndFreeParentInternal@HTTP2Channel@@IEAAXH@Z; HTTP2Channel::DrainUpcallsAndFreeParentInternal(int)
0x18000a59e  test    r14d, r14d
0x18000a5a1  jz      short loc_18000A5B9
0x18000a5a3  mov     rax, [rbx]
0x18000a5a6  mov     rcx, rbx
0x18000a5a9  mov     edx, [rsp+58h+arg_20]
0x18000a5b0  mov     rax, [rax+28h]
0x18000a5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5b9  mov     rcx, rbx; this
0x18000a5bc  call    ?RemoveReference@HTTP2Channel@@QEAAXXZ; HTTP2Channel::RemoveReference(void)
0x18000a5c1  mov     rbx, [rsp+58h+arg_8]
0x18000a5c6  mov     rbp, [rsp+58h+arg_10]
0x18000a5cb  add     rsp, 40h
0x18000a5cf  pop     r14
0x18000a5d1  pop     rdi
0x18000a5d2  pop     rsi
0x18000a5d3  retn
```
