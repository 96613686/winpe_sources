# HTTP2WinHttpTransportChannel::DirectSendComplete(uchar * *,void * *)

- ea: `0x180009620`
- end: `0x1800097ac`
- name: `?DirectSendComplete@HTTP2WinHttpTransportChannel@@QEAAJPEAPEAEPEAPEAX@Z`
- size: `396`
- prototype: `__int64 __fastcall(HTTP2WinHttpTransportChannel *__hidden this, unsigned __int8 **, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000bc50`

## callees

- `0x180009620`
- `0x1800189a0`
- `0x18001e4a4`
- `0x180025010`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x18000966e`
- `RPCRT4!I_RpcLogEvent` at `0x180009790`
- `RPCRT4!I_RpcLogEvent` at `0x18000966e`
- `RPCRT4!I_RpcLogEvent` at `0x180009790`

## pseudocode

```c
__int64 __fastcall HTTP2WinHttpTransportChannel::DirectSendComplete(
        HTTP2WinHttpTransportChannel *this,
        unsigned __int8 **a2,
        void **a3)
{
  unsigned __int8 **v4; // r15
  HTTP2WinHttpTransportChannel *v5; // rdi
  HTTP2WinHttpTransportChannel *v6; // r8
  int v7; // eax
  ULONG v8; // edx
  unsigned int v9; // eax
  _QWORD *v10; // rbx
  unsigned int v11; // esi
  unsigned __int8 *v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int v17; // [rsp+60h] [rbp+8h] BYREF
  __int64 v18; // [rsp+78h] [rbp+20h] BYREF

  v4 = a2;
  v17 = 0;
  v5 = this;
  v18 = 0;
  v6 = this;
  v7 = *((_DWORD *)this + 21);
  LOBYTE(this) = 50;
  LOBYTE(a2) = 111;
  I_RpcLogEvent(this, a2, v6, 17432597, v7, 0, 0);
  if ( *((_DWORD *)v5 + 21) )
  {
    (*((void (__fastcall **)(_QWORD))pRuntimeImportTable + 67))(*((_QWORD *)v5 + 11));
    v8 = *((_DWORD *)v5 + 21);
    *((_QWORD *)v5 + 11) = 0;
    CompRpcpErrorAddRecord(0xDu, v8, 0x582u);
  }
  v9 = *((_DWORD *)v5 + 21);
  *((_DWORD *)v5 + 45) = 3;
  if ( v9 )
  {
    v17 = 0;
    v18 = 0;
  }
  else
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, unsigned int *))(**((_QWORD **)v5 + 3) + 144LL))(
           *((_QWORD *)v5 + 3),
           &v18,
           &v17);
    *((_DWORD *)v5 + 21) = v9;
  }
  v10 = (_QWORD *)*((_QWORD *)v5 + 23);
  if ( v9 == -1073606647 )
    v9 = -1073606646;
  v11 = HTTP2WinHttpTransportChannel::SendComplete(v5, v9, *((struct HTTP2SendContext **)v5 + 23));
  if ( v11 == -1073606615 )
  {
    v12 = 0;
    v10 = 0;
  }
  else
  {
    (*((void (__fastcall **)(_QWORD *))pRuntimeImportTable + 28))(v10);
    v12 = (unsigned __int8 *)v10[6];
  }
  *a3 = v10;
  *v4 = v12;
  v13 = (*(__int64 (__fastcall **)(HTTP2WinHttpTransportChannel *, _QWORD))(*(_QWORD *)v5 + 80LL))(v5, v11);
  (*((void (__fastcall **)(_QWORD, __int64))pRuntimeImportTable + 75))(v17, v18);
  LOBYTE(v14) = 111;
  LOBYTE(v15) = 50;
  I_RpcLogEvent(v15, v14, v5, 655381, v13, 0, 0);
  return v13;
}

```

## disassembly

```asm
0x180009620  mov     rax, rsp
0x180009623  mov     [rax+10h], rbx
0x180009627  mov     [rax+18h], rsi
0x18000962b  push    rdi
0x18000962c  push    r14
0x18000962e  push    r15
0x180009630  sub     rsp, 40h
0x180009634  mov     dword ptr [rax-28h], 0
0x18000963b  mov     r14, r8
0x18000963e  mov     dword ptr [rax-30h], 0
0x180009645  mov     r15, rdx
0x180009648  mov     dword ptr [rax+8], 0
0x18000964f  mov     rdi, rcx
0x180009652  mov     qword ptr [rax+20h], 0
0x18000965a  mov     r8, rcx
0x18000965d  mov     eax, [rcx+54h]
0x180009660  mov     r9d, 10A0015h
0x180009666  mov     cl, 32h ; '2'
0x180009668  mov     [rsp+58h+var_38], eax
0x18000966c  mov     dl, 6Fh ; 'o'
0x18000966e  call    cs:__imp_I_RpcLogEvent
0x180009674  cmp     dword ptr [rdi+54h], 0
0x180009678  jz      short loc_1800096AC
0x18000967a  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180009681  mov     rcx, [rdi+58h]
0x180009685  mov     rax, [rax+218h]
0x18000968c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009691  mov     edx, [rdi+54h]; unsigned int
0x180009694  mov     r8d, 582h; unsigned __int16
0x18000969a  mov     ecx, 0Dh; unsigned int
0x18000969f  mov     qword ptr [rdi+58h], 0
0x1800096a7  call    ?CompRpcpErrorAddRecord@@YAXKKG@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort)
0x1800096ac  mov     eax, [rdi+54h]
0x1800096af  mov     dword ptr [rdi+0B4h], 3
0x1800096b9  test    eax, eax
0x1800096bb  jnz     short loc_1800096DF
0x1800096bd  mov     rcx, [rdi+18h]
0x1800096c1  lea     r8, [rsp+58h+arg_0]
0x1800096c6  lea     rdx, [rsp+58h+arg_18]
0x1800096cb  mov     rax, [rcx]
0x1800096ce  mov     rax, [rax+90h]
0x1800096d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096da  mov     [rdi+54h], eax
0x1800096dd  jmp     short loc_1800096F0
0x1800096df  mov     [rsp+58h+arg_0], 0
0x1800096e7  mov     [rsp+58h+arg_18], 0
0x1800096f0  mov     rbx, [rdi+0B8h]
0x1800096f7  cmp     eax, 0C0021009h
0x1800096fc  mov     ecx, 0C002100Ah
0x180009701  mov     r8, rbx; struct HTTP2SendContext *
0x180009704  cmovz   eax, ecx
0x180009707  mov     rcx, rdi; this
0x18000970a  mov     edx, eax; int
0x18000970c  call    ?SendComplete@HTTP2WinHttpTransportChannel@@UEAAJJPEAVHTTP2SendContext@@@Z; HTTP2WinHttpTransportChannel::SendComplete(long,HTTP2SendContext *)
0x180009711  mov     esi, eax
0x180009713  cmp     eax, 0C0021029h
0x180009718  jz      short loc_180009736
0x18000971a  mov     rcx, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180009721  mov     rax, [rcx+0E0h]
0x180009728  mov     rcx, rbx
0x18000972b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009730  mov     rcx, [rbx+30h]
0x180009734  jmp     short loc_18000973A
0x180009736  xor     ecx, ecx
0x180009738  xor     ebx, ebx
0x18000973a  mov     [r14], rbx
0x18000973d  mov     edx, esi
0x18000973f  mov     [r15], rcx
0x180009742  mov     rcx, rdi
0x180009745  mov     rax, [rdi]
0x180009748  mov     rax, [rax+50h]
0x18000974c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009751  mov     r8, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180009758  mov     ebx, eax
0x18000975a  mov     rdx, [rsp+58h+arg_18]
0x18000975f  mov     ecx, [rsp+58h+arg_0]
0x180009763  mov     rax, [r8+258h]
0x18000976a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000976f  mov     [rsp+58h+var_28], 0
0x180009777  mov     r9d, 0A0015h
0x18000977d  mov     [rsp+58h+var_30], 0
0x180009785  mov     r8, rdi
0x180009788  mov     dl, 6Fh ; 'o'
0x18000978a  mov     [rsp+58h+var_38], ebx
0x18000978e  mov     cl, 32h ; '2'
0x180009790  call    cs:__imp_I_RpcLogEvent
0x180009796  mov     rsi, [rsp+58h+arg_10]
0x18000979b  mov     eax, ebx
0x18000979d  mov     rbx, [rsp+58h+arg_8]
0x1800097a2  add     rsp, 40h
0x1800097a6  pop     r15
0x1800097a8  pop     r14
0x1800097aa  pop     rdi
0x1800097ab  retn
```
