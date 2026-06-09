# LRPC_SCALL::SendReceive(_RPC_MESSAGE *)

- ea: `0x18006fc20`
- end: `0x18007026f`
- name: `?SendReceive@LRPC_SCALL@@UEAAJPEAU_RPC_MESSAGE@@@Z`
- size: `1615`
- prototype: `int(LRPC_SCALL *__hidden this, struct _RPC_MESSAGE *)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, installer_update`

## callees

- `0x1800182c0`
- `0x18001a30c`
- `0x1800217d0`
- `0x180022e80`
- `0x1800263a0`
- `0x180026500`
- `0x180027e20`
- `0x1800295d8`
- `0x18006fc20`
- `0x180070278`
- `0x18007031c`
- `0x1800703c0`
- `0x180070458`
- `0x180070aa0`
- `0x1800716d4`
- `0x18009858c`
- `0x1800cec91`
- `0x1800ceda0`

## import_xrefs

- `ntdll!NtAlpcDeleteSectionView` at `0x180070110`
- `ntdll!NtAlpcDeleteSectionView` at `0x180070110`
- `ntdll!NtAlpcDeletePortSection` at `0x18007025e`
- `ntdll!NtAlpcDeletePortSection` at `0x18007025e`

## pseudocode

```c
__int64 __fastcall LRPC_SCALL::SendReceive(LRPC_SCALL *this, struct _RPC_MESSAGE *a2)
{
  void *v4; // r15
  int v5; // ebx
  ULONG Flags; // r12d
  __int64 result; // rax
  BCACHE *v8; // rcx
  ULONG v9; // r12d
  unsigned __int64 v10; // rdx
  struct _SLIST_ENTRY *v11; // r14
  unsigned int BufferLength; // eax
  __int16 v13; // si
  size_t v14; // rbx
  unsigned int v15; // ebx
  unsigned __int64 v16; // r8
  unsigned int HeaderSize; // eax
  unsigned int v18; // edx
  __int64 v19; // r10
  void *v20; // r12
  int v21; // ecx
  __int16 v22; // ax
  PRTL_CRITICAL_SECTION v23; // rcx
  int v24; // eax
  int *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  struct RPC_DISPATCH_TABLE *v28; // r9
  unsigned int v29; // esi
  unsigned __int64 v30; // rdx
  struct _SLIST_ENTRY *v31; // rsi
  struct _SLIST_ENTRY *v32; // rax
  int v33; // ebx
  int v34; // edx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rcx
  unsigned int v38; // eax
  __int64 v39; // rbx
  const void *v40; // rdx
  __int64 v41; // rcx
  void *v42; // rdx
  unsigned int v43; // eax
  __int64 v44; // rbx
  struct _PORT_MESSAGE *v45; // [rsp+20h] [rbp-A9h]
  unsigned __int64 *v46; // [rsp+28h] [rbp-A1h]
  struct LRPC_SYSTEM_HANDLE_DATA *v47; // [rsp+30h] [rbp-99h]
  union _LARGE_INTEGER *v48; // [rsp+38h] [rbp-91h]
  void *v49; // [rsp+50h] [rbp-79h] BYREF
  void *v50; // [rsp+58h] [rbp-71h] BYREF
  void *v51; // [rsp+60h] [rbp-69h] BYREF
  _DWORD v52[6]; // [rsp+68h] [rbp-61h] BYREF
  _DWORD v53[24]; // [rsp+80h] [rbp-49h] BYREF

  v50 = 0;
  v49 = 0;
  v51 = 0;
  v4 = 0;
  v5 = *((_DWORD *)this + 58);
  Flags = NtCurrentPeb()->ProcessParameters->Flags;
  result = LRPC_SCALL::PrepareForCallbackIfNecessary(this);
  if ( !(_DWORD)result )
  {
    v9 = Flags >> 31;
    if ( (v5 & 0x40) != 0 )
      goto LABEL_3;
    v30 = 65280;
    if ( !v9 )
      v30 = 4096;
    v31 = BCACHE::Allocate(v8, v30);
    if ( v31 )
    {
      v32 = (struct _SLIST_ENTRY *)*((_QWORD *)this + 56);
      *v31 = *v32;
      v31[1] = v32[1];
      v31[2].Next = v32[2].Next;
      *((_QWORD *)&v31[2].Next + 1) = 6;
      HIDWORD(v31[3].Next) = *((_DWORD *)this + 133);
      LODWORD(v31[3].Next) = 0;
      if ( (*((_DWORD *)this + 58) & 0x20) != 0 && (*((_DWORD *)this + 58) & 0x1000) == 0 )
      {
        *(_QWORD *)(*((_QWORD *)this + 74) + 208LL) = *((_QWORD *)this + 44);
        _InterlockedOr((volatile signed __int32 *)this + 58, 0x4000u);
      }
      *(_DWORD *)(*((_QWORD *)this + 74) + 224LL) = 1;
      v33 = LRPC_ADDRESS::AlpcSend(
              *(LRPC_ADDRESS **)(*((_QWORD *)this + 38) + 56LL),
              (struct _PORT_MESSAGE *)v31,
              0,
              0,
              0,
              0,
              0);
      I_RpcBCacheFree(v31);
      if ( v33 < 0 )
      {
        return 1727;
      }
      else
      {
        SEMAPHORE_EVENT::Wait((SEMAPHORE_EVENT *)(*((_QWORD *)this + 74) + 16LL), v34);
        *(_DWORD *)(*((_QWORD *)this + 74) + 224LL) = 2;
        v35 = *((_QWORD *)this + 74);
        v29 = *(_DWORD *)(v35 + 28);
        if ( !v29 )
        {
          v36 = *(_QWORD *)(v35 + 32);
          v37 = *((_QWORD *)this + 56);
          *(_OWORD *)v37 = *(_OWORD *)v36;
          *(_OWORD *)(v37 + 16) = *(_OWORD *)(v36 + 16);
          *(_QWORD *)(v37 + 32) = *(_QWORD *)(v36 + 32);
          LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(
            *(LRPC_ADDRESS **)(*((_QWORD *)this + 38) + 56LL),
            *(void **)(*((_QWORD *)this + 74) + 32LL));
          *(_QWORD *)(*((_QWORD *)this + 74) + 32LL) = 0;
LABEL_3:
          v10 = 65280;
          ++*(_DWORD *)(*((_QWORD *)this + 74) + 8LL);
          if ( !v9 )
            v10 = 4096;
          v11 = BCACHE::Allocate(v8, v10);
          if ( !v11 )
          {
            v29 = 14;
            v20 = 0;
LABEL_48:
            --*(_DWORD *)(*((_QWORD *)this + 74) + 8LL);
            if ( v4 )
            {
              v39 = *((_QWORD *)this + 38);
              LogEvent(0x4Cu, 0x44u, *(void **)(v39 + 48), v4, 1u, (int)v46, (int)v47);
              NtAlpcDeleteSectionView(*(_QWORD *)(v39 + 48), 0, v4);
            }
            goto LABEL_28;
          }
          BufferLength = a2->BufferLength;
          v13 = 72;
          if ( v9 )
          {
            if ( BufferLength <= 0xFE98 )
              memcpy_0(&v11[6].Next + 1, (const void *)(*((_QWORD *)this + 56) + 64LL), a2->BufferLength);
          }
          else
          {
            v14 = BufferLength;
            if ( BufferLength > 0xF98 )
            {
              v38 = AlpcAllocateSectionAndView(
                      *(void **)(*((_QWORD *)this + 38) + 48LL),
                      BufferLength,
                      &v51,
                      &v50,
                      (unsigned __int64 *)&v49);
              v4 = v50;
              v29 = v38;
              if ( v38 )
              {
                v20 = v51;
                goto LABEL_48;
              }
              v40 = (const void *)*((_QWORD *)this + 58);
              if ( v40 )
              {
                memcpy_0(v50, v40, v14);
                LRPC_ADDRESS::AlpcFreeSection(*(LRPC_ADDRESS **)(*((_QWORD *)this + 38) + 56LL), *((void **)this + 57));
                v41 = *((_QWORD *)this + 38);
                v42 = (void *)*((_QWORD *)this + 58);
                *((_QWORD *)this + 57) = 0;
                LRPC_ADDRESS::AlpcFreeView(*(LRPC_ADDRESS **)(v41 + 56), v42);
                *((_QWORD *)this + 58) = 0;
              }
              else
              {
                memcpy_0(v50, (const void *)(*((_QWORD *)this + 56) + 64LL), v14);
              }
              v13 = 72;
              v49 = v51;
            }
            else
            {
              memcpy_0(&v11[6].Next + 1, (const void *)(*((_QWORD *)this + 56) + 64LL), BufferLength);
            }
            if ( v4 )
            {
              v15 = 1610612736;
              v16 = 72;
              goto LABEL_14;
            }
          }
          v15 = 0x20000000;
          v16 = 40;
LABEL_14:
          RpcpAlpcInitializeMessageAttribute(
            v15,
            (struct RPCP_ALPC_MESSAGE_ATTRIBUTES *)v53,
            v16,
            (unsigned __int64 *)&v50);
          HeaderSize = RpcpAlpcpGetHeaderSize(v53[0] & 0xC0000000);
          v19 = 0;
          *(_QWORD *)((char *)&v53[2] + HeaderSize) = this;
          *(_QWORD *)((char *)v53 + HeaderSize) = 0;
          if ( v4 )
          {
            v43 = RpcpAlpcpGetHeaderSize(v53[0] & 0x80000000);
            v20 = v49;
            *(_DWORD *)((char *)v53 + v43) = 393216;
            *(_QWORD *)((char *)&v53[2] + v43) = v20;
            *(_QWORD *)((char *)&v53[4] + v43) = v4;
            *(_QWORD *)((char *)&v53[6] + v43) = a2->BufferLength;
          }
          else
          {
            v20 = v49;
          }
          v53[1] = v15;
          *v11 = 0;
          v11[1] = 0;
          v11[2].Next = 0;
          if ( v4 )
          {
            LOWORD(v11->Next) = 72;
            v21 = 4;
            *((_QWORD *)&v11[6].Next + 1) = a2->BufferLength;
          }
          else
          {
            v21 = v19;
            v22 = LOWORD(a2->BufferLength) + 64;
            LOWORD(v11->Next) = v22;
            v13 = v22;
          }
          LODWORD(v11[3].Next) = v21;
          WORD2(v11->Next) = 0x4000;
          WORD1(v11->Next) = v13 + 40;
          *((_QWORD *)&v11[2].Next + 1) = 9;
          *((_DWORD *)&v11[3].Next + 2) = *(unsigned __int16 *)(*((_QWORD *)this + 39) + 8LL);
          v23 = GlobalRpcServer;
          *((_DWORD *)&v11[3].Next + 3) = a2->ProcNum;
          HIDWORD(v11[3].Next) = *((_DWORD *)this + 133);
          LODWORD(v11[4].Next) = v19;
          *((_QWORD *)&v11[4].Next + 1) = v19;
          LODWORD(v11[5].Next) = v19;
          ++LODWORD(v23[1].OwningThread);
          v24 = LRPC_SASSOCIATION::AlpcSendWaitReceivePort(
                  *((LRPC_SASSOCIATION **)this + 38),
                  v18,
                  (struct _PORT_MESSAGE *)v11,
                  (struct _ALPC_MESSAGE_ATTRIBUTES *)v53,
                  v45,
                  v46,
                  v47,
                  v48);
          if ( v24 != -1073741801 )
          {
            if ( v24 == -1073741769 )
              goto LABEL_60;
            if ( v24 != -1073741756 && v24 != -1073741670 )
            {
              switch ( v24 )
              {
                case -1073740031:
                  goto LABEL_59;
                case 0:
                  a2->DataRepresentation = 16;
                  v25 = (int *)*((_QWORD *)this + 39);
                  v26 = *(_QWORD *)v25;
                  if ( (*(_DWORD *)(*(_QWORD *)v25 + 168LL) & 0x2000000) != 0 )
                  {
                    v27 = *(_QWORD *)(v26 + 176) + 80LL * v25[3];
                    a2->TransferSyntax = (PRPC_SYNTAX_IDENTIFIER)v27;
                    v28 = *(struct RPC_DISPATCH_TABLE **)(v27 + 24);
                    if ( v28 )
                    {
LABEL_27:
                      v29 = LRPC_CALLBACK::SendReceiveLoop(
                              *((LRPC_CALLBACK **)this + 74),
                              0,
                              (struct _RPC_SYNTAX_IDENTIFIER *)v27,
                              v28,
                              a2,
                              (unsigned int)v46,
                              *((_DWORD *)this + 128),
                              (LRPC_SCALL *)((char *)this + 516),
                              *((struct LRPC_SBINDING **)this + 39));
LABEL_28:
                      if ( v20 )
                      {
                        v44 = *((_QWORD *)this + 38);
                        LogEvent(0x4Cu, 0x44u, *(void **)(v44 + 48), v20, 0, (int)v46, (int)v47);
                        NtAlpcDeletePortSection(*(_QWORD *)(v44 + 48), 0, v20);
                      }
                      if ( v11 )
                        I_RpcBCacheFree(v11);
                      return v29;
                    }
                  }
                  else
                  {
                    v27 = v26 + 104;
                    a2->TransferSyntax = (PRPC_SYNTAX_IDENTIFIER)(v26 + 104);
                  }
                  v28 = *(struct RPC_DISPATCH_TABLE **)(v26 + 128);
                  goto LABEL_27;
                case 258:
LABEL_59:
                  v29 = 1818;
LABEL_47:
                  v52[2] = v24;
                  v52[0] = 3;
                  RpcpErrorAddRecord(2u, v29, 0x500u, 1, (struct tagParam *)v52);
                  goto LABEL_48;
              }
LABEL_60:
              v29 = 1726;
              goto LABEL_47;
            }
          }
          v29 = 14;
          goto LABEL_47;
        }
      }
    }
    else
    {
      return 14;
    }
    return v29;
  }
  return result;
}

```

## disassembly

```asm
0x18006fc20  mov     [rsp-8+arg_10], rbx
0x18006fc25  push    rbp
0x18006fc26  push    rsi
0x18006fc27  push    rdi
0x18006fc28  push    r12
0x18006fc2a  push    r13
0x18006fc2c  push    r14
0x18006fc2e  push    r15
0x18006fc30  lea     rbp, [rsp-27h]
0x18006fc35  sub     rsp, 0F0h
0x18006fc3c  mov     rax, cs:__security_cookie
0x18006fc43  xor     rax, rsp
0x18006fc46  mov     [rbp+57h+var_40], rax
0x18006fc4a  xor     r14d, r14d
0x18006fc4d  mov     r13, rdx
0x18006fc50  mov     eax, r14d
0x18006fc53  mov     [rbp+57h+var_C8], r14
0x18006fc57  mov     [rbp+57h+var_D0], rax
0x18006fc5b  mov     rdi, rcx
0x18006fc5e  mov     [rbp+57h+var_C0], rax
0x18006fc62  mov     r15d, r14d
0x18006fc65  mov     rax, gs:60h
0x18006fc6e  mov     ebx, [rcx+0E8h]
0x18006fc74  mov     r8, [rax+20h]
0x18006fc78  mov     r12d, [r8+8]
0x18006fc7c  call    ?PrepareForCallbackIfNecessary@LRPC_SCALL@@AEAAJXZ; LRPC_SCALL::PrepareForCallbackIfNecessary(void)
0x18006fc81  test    eax, eax
0x18006fc83  jnz     loc_18006FEC4
0x18006fc89  shr     r12d, 1Fh
0x18006fc8d  test    bl, 40h
0x18006fc90  jz      loc_18006FEEC
0x18006fc96  mov     rax, [rdi+250h]
0x18006fc9d  mov     edx, 0FF00h
0x18006fca2  inc     dword ptr [rax+8]
0x18006fca5  test    r12d, r12d
0x18006fca8  jnz     short loc_18006FCAF
0x18006fcaa  mov     edx, 1000h; unsigned __int64
0x18006fcaf  call    ?Allocate@BCACHE@@QEAAPEAX_K@Z; BCACHE::Allocate(unsigned __int64)
0x18006fcb4  mov     r14, rax
0x18006fcb7  test    rax, rax
0x18006fcba  jz      loc_180070135
0x18006fcc0  mov     eax, [r13+18h]
0x18006fcc4  mov     esi, 48h ; 'H'
0x18006fcc9  test    r12d, r12d
0x18006fccc  jnz     short loc_18006FD01
0x18006fcce  mov     ebx, eax
0x18006fcd0  cmp     eax, 0F98h
0x18006fcd5  ja      loc_180070072
0x18006fcdb  mov     rdx, [rdi+1C0h]
0x18006fce2  lea     rcx, [r14+68h]; void *
0x18006fce6  add     rdx, 40h ; '@'; Src
0x18006fcea  mov     r8d, eax; Size
0x18006fced  call    memcpy_0
0x18006fcf2  test    r15, r15
0x18006fcf5  jz      short loc_18006FD0C
0x18006fcf7  mov     ebx, 60000000h
0x18006fcfc  mov     r8, rsi
0x18006fcff  jmp     short loc_18006FD17
0x18006fd01  cmp     eax, 0FE98h
0x18006fd06  jbe     loc_18007013F
0x18006fd0c  mov     ebx, 20000000h
0x18006fd11  mov     r8d, 28h ; '('; unsigned __int64
0x18006fd17  lea     r9, [rbp+57h+var_C8]; unsigned __int64 *
0x18006fd1b  mov     ecx, ebx; unsigned int
0x18006fd1d  lea     rdx, [rbp+57h+var_A0]; struct RPCP_ALPC_MESSAGE_ATTRIBUTES *
0x18006fd21  call    ?RpcpAlpcInitializeMessageAttribute@@YAJKPEAVRPCP_ALPC_MESSAGE_ATTRIBUTES@@_KPEA_K@Z; RpcpAlpcInitializeMessageAttribute(ulong,RPCP_ALPC_MESSAGE_ATTRIBUTES *,unsigned __int64,unsigned __int64 *)
0x18006fd26  mov     ecx, dword ptr [rbp+57h+var_A0]
0x18006fd29  and     ecx, 0C0000000h; unsigned int
0x18006fd2f  call    ?RpcpAlpcpGetHeaderSize@@YAKK@Z; RpcpAlpcpGetHeaderSize(ulong)
0x18006fd34  mov     r9d, eax
0x18006fd37  xor     r10d, r10d
0x18006fd3a  mov     [rbp+r9+57h+var_98], rdi
0x18006fd3f  mov     [rbp+r9+57h+var_A0], r10
0x18006fd44  test    r15, r15
0x18006fd47  jnz     loc_1800701DA
0x18006fd4d  mov     r12, [rbp+57h+var_D0]
0x18006fd51  mov     dword ptr [rbp+57h+var_A0+4], ebx
0x18006fd54  xorps   xmm0, xmm0
0x18006fd57  xor     eax, eax
0x18006fd59  movups  xmmword ptr [r14], xmm0
0x18006fd5d  movups  xmmword ptr [r14+10h], xmm0
0x18006fd62  mov     [r14+20h], rax
0x18006fd66  test    r15, r15
0x18006fd69  jnz     loc_18007005C
0x18006fd6f  movzx   eax, word ptr [r13+18h]
0x18006fd74  mov     ecx, r10d
0x18006fd77  add     ax, 40h ; '@'
0x18006fd7b  mov     [r14], ax
0x18006fd7f  movzx   esi, ax
0x18006fd82  mov     [r14+30h], ecx
0x18006fd86  lea     r9, [rbp+57h+var_A0]; struct _ALPC_MESSAGE_ATTRIBUTES *
0x18006fd8a  mov     word ptr [r14+4], 4000h
0x18006fd91  add     si, 28h ; '('
0x18006fd95  mov     [r14+2], si
0x18006fd9a  mov     r8, r14; struct _PORT_MESSAGE *
0x18006fd9d  mov     qword ptr [r14+28h], 9
0x18006fda5  mov     rax, [rdi+138h]
0x18006fdac  movzx   ecx, word ptr [rax+8]
0x18006fdb0  mov     [r14+38h], ecx
0x18006fdb4  mov     eax, [r13+1Ch]
0x18006fdb8  mov     rcx, cs:?GlobalRpcServer@@3PEAVRPC_SERVER@@EA; RPC_SERVER * GlobalRpcServer
0x18006fdbf  mov     [r14+3Ch], eax
0x18006fdc3  mov     eax, [rdi+214h]
0x18006fdc9  mov     [r14+34h], eax
0x18006fdcd  mov     [r14+40h], r10d
0x18006fdd1  mov     [r14+48h], r10
0x18006fdd5  mov     [r14+50h], r10d
0x18006fdd9  mov     eax, [rcx+38h]
0x18006fddc  inc     eax
0x18006fdde  mov     [rcx+38h], eax
0x18006fde1  mov     rcx, [rdi+130h]; this
0x18006fde8  call    ?AlpcSendWaitReceivePort@LRPC_SASSOCIATION@@QEAAJKPEAU_PORT_MESSAGE@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@0PEA_K1PEAT_LARGE_INTEGER@@@Z; LRPC_SASSOCIATION::AlpcSendWaitReceivePort(ulong,_PORT_MESSAGE *,_ALPC_MESSAGE_ATTRIBUTES *,_PORT_MESSAGE *,unsigned __int64 *,_ALPC_MESSAGE_ATTRIBUTES *,_LARGE_INTEGER *)
0x18006fded  cmp     eax, 0C0000017h
0x18006fdf2  jz      loc_18007022B
0x18006fdf8  cmp     eax, 0C0000037h
0x18006fdfd  jz      loc_180070221
0x18006fe03  cmp     eax, 0C0000044h
0x18006fe08  jz      loc_18007022B
0x18006fe0e  cmp     eax, 0C000009Ah
0x18006fe13  jz      loc_18007022B
0x18006fe19  cmp     eax, 0C0000701h
0x18006fe1e  jz      loc_180070217
0x18006fe24  test    eax, eax
0x18006fe26  jnz     loc_180070210
0x18006fe2c  mov     dword ptr [r13+8], 10h
0x18006fe34  mov     rax, [rdi+138h]
0x18006fe3b  mov     rdx, [rax]
0x18006fe3e  test    dword ptr [rdx+0A8h], 2000000h
0x18006fe48  jz      loc_18007001A
0x18006fe4e  movsxd  rax, dword ptr [rax+0Ch]
0x18006fe52  lea     r8, [rax+rax*4]
0x18006fe56  shl     r8, 4
0x18006fe5a  add     r8, [rdx+0B0h]; struct _RPC_SYNTAX_IDENTIFIER *
0x18006fe61  mov     [r13+20h], r8
0x18006fe65  mov     r9, [r8+18h]
0x18006fe69  test    r9, r9
0x18006fe6c  jnz     short loc_18006FE75
0x18006fe6e  mov     r9, [rdx+80h]; struct RPC_DISPATCH_TABLE *
0x18006fe75  mov     rax, [rdi+138h]
0x18006fe7c  lea     rcx, [rdi+204h]
0x18006fe83  mov     [rsp+120h+var_E0], rax; struct LRPC_SBINDING *
0x18006fe88  xor     edx, edx; int
0x18006fe8a  mov     eax, [rdi+200h]
0x18006fe90  mov     [rsp+120h+var_E8], rcx; struct RPC_UUID *
0x18006fe95  mov     rcx, [rdi+250h]; this
0x18006fe9c  mov     dword ptr [rsp+120h+var_F0], eax; int
0x18006fea0  mov     [rsp+120h+var_100], r13; struct _RPC_MESSAGE *
0x18006fea5  call    ?SendReceiveLoop@LRPC_CALLBACK@@QEAAJHPEAU_RPC_SYNTAX_IDENTIFIER@@PEAURPC_DISPATCH_TABLE@@PEAU_RPC_MESSAGE@@KHPEAVRPC_UUID@@PEAVLRPC_SBINDING@@@Z; LRPC_CALLBACK::SendReceiveLoop(int,_RPC_SYNTAX_IDENTIFIER *,RPC_DISPATCH_TABLE *,_RPC_MESSAGE *,ulong,int,RPC_UUID *,LRPC_SBINDING *)
0x18006feaa  mov     esi, eax
0x18006feac  test    r12, r12
0x18006feaf  jnz     loc_180070235
0x18006feb5  test    r14, r14
0x18006feb8  jz      short loc_18006FEC2
0x18006feba  mov     rcx, r14; void *
0x18006febd  call    I_RpcBCacheFree
0x18006fec2  mov     eax, esi
0x18006fec4  mov     rcx, [rbp+57h+var_40]
0x18006fec8  xor     rcx, rsp; StackCookie
0x18006fecb  call    __security_check_cookie
0x18006fed0  mov     rbx, [rsp+120h+arg_10]
0x18006fed8  add     rsp, 0F0h
0x18006fedf  pop     r15
0x18006fee1  pop     r14
0x18006fee3  pop     r13
0x18006fee5  pop     r12
0x18006fee7  pop     rdi
0x18006fee8  pop     rsi
0x18006fee9  pop     rbp
0x18006feea  retn
0x18006feec  mov     edx, 0FF00h
0x18006fef1  test    r12d, r12d
0x18006fef4  jnz     short loc_18006FEFB
0x18006fef6  mov     edx, 1000h; unsigned __int64
0x18006fefb  call    ?Allocate@BCACHE@@QEAAPEAX_K@Z; BCACHE::Allocate(unsigned __int64)
0x18006ff00  mov     rsi, rax
0x18006ff03  test    rax, rax
0x18006ff06  jz      loc_180070121
0x18006ff0c  mov     rax, [rdi+1C0h]
0x18006ff13  movups  xmm0, xmmword ptr [rax]
0x18006ff16  movups  xmmword ptr [rsi], xmm0
0x18006ff19  movups  xmm1, xmmword ptr [rax+10h]
0x18006ff1d  movups  xmmword ptr [rsi+10h], xmm1
0x18006ff21  movsd   xmm0, qword ptr [rax+20h]
0x18006ff26  movsd   qword ptr [rsi+20h], xmm0
0x18006ff2b  mov     qword ptr [rsi+28h], 6
0x18006ff33  mov     eax, [rdi+214h]
0x18006ff39  mov     [rsi+34h], eax
0x18006ff3c  mov     [rsi+30h], r14d
0x18006ff40  mov     eax, [rdi+0E8h]
0x18006ff46  test    al, 20h
0x18006ff48  jnz     loc_180070027
0x18006ff4e  mov     rax, [rdi+250h]
0x18006ff55  xor     r9d, r9d; void *
0x18006ff58  mov     [rsp+120h+var_F0], r14; struct LRPC_SYSTEM_HANDLE_DATA *
0x18006ff5d  xor     r8d, r8d; int
0x18006ff60  mov     [rsp+120h+var_F8], r14; unsigned __int64
0x18006ff65  mov     rdx, rsi; struct _PORT_MESSAGE *
0x18006ff68  mov     [rsp+120h+var_100], r14; void *
0x18006ff6d  mov     dword ptr [rax+0E0h], 1
0x18006ff77  mov     rcx, [rdi+130h]
0x18006ff7e  mov     rcx, [rcx+38h]; this
0x18006ff82  call    ?AlpcSend@LRPC_ADDRESS@@QEAAJPEAU_PORT_MESSAGE@@HPEAX1_KPEAVLRPC_SYSTEM_HANDLE_DATA@@@Z; LRPC_ADDRESS::AlpcSend(_PORT_MESSAGE *,int,void *,void *,unsigned __int64,LRPC_SYSTEM_HANDLE_DATA *)
0x18006ff87  mov     rcx, rsi; void *
0x18006ff8a  mov     ebx, eax
0x18006ff8c  call    I_RpcBCacheFree
0x18006ff91  test    ebx, ebx
0x18006ff93  js      loc_18007012B
0x18006ff99  mov     rcx, [rdi+250h]
0x18006ffa0  add     rcx, 10h; this
0x18006ffa4  call    ?Wait@SEMAPHORE_EVENT@@QEAAHJ@Z; SEMAPHORE_EVENT::Wait(long)
0x18006ffa9  mov     rax, [rdi+250h]
0x18006ffb0  mov     dword ptr [rax+0E0h], 2
0x18006ffba  mov     rax, [rdi+250h]
0x18006ffc1  mov     esi, [rax+1Ch]
0x18006ffc4  test    esi, esi
0x18006ffc6  jnz     loc_18006FEC2
0x18006ffcc  mov     rax, [rax+20h]
0x18006ffd0  mov     rcx, [rdi+1C0h]
0x18006ffd7  movups  xmm0, xmmword ptr [rax]
0x18006ffda  movups  xmmword ptr [rcx], xmm0
0x18006ffdd  movups  xmm1, xmmword ptr [rax+10h]
0x18006ffe1  movups  xmmword ptr [rcx+10h], xmm1
0x18006ffe5  movsd   xmm0, qword ptr [rax+20h]
0x18006ffea  movsd   qword ptr [rcx+20h], xmm0
0x18006ffef  mov     rdx, [rdi+250h]
0x18006fff6  mov     rcx, [rdi+130h]
0x18006fffd  mov     rdx, [rdx+20h]; void *
0x180070001  mov     rcx, [rcx+38h]; this
0x180070005  call    ?RpcFreeLrpcAddressBuffer@LRPC_ADDRESS@@QEAAXPEAX@Z; LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(void *)
0x18007000a  mov     rax, [rdi+250h]
0x180070011  mov     [rax+20h], r14
0x180070015  jmp     loc_18006FC96
0x18007001a  lea     r8, [rdx+68h]
0x18007001e  mov     [r13+20h], r8
0x180070022  jmp     loc_18006FE6E
0x180070027  mov     eax, [rdi+0E8h]
0x18007002d  bt      eax, 0Ch
0x180070031  jb      loc_18006FF4E
0x180070037  mov     rcx, [rdi+250h]
0x18007003e  mov     rax, [rdi+160h]
0x180070045  mov     [rcx+0D0h], rax
0x18007004c  lock or dword ptr [rdi+0E8h], 4000h
0x180070057  jmp     loc_18006FF4E
0x18007005c  mov     [r14], si
0x180070060  mov     ecx, 4
0x180070065  mov     eax, [r13+18h]
0x180070069  mov     [r14+68h], rax
0x18007006d  jmp     loc_18006FD82
0x180070072  mov     rcx, [rdi+130h]
0x180070079  lea     rax, [rbp+57h+var_D0]
0x18007007d  lea     r9, [rbp+57h+var_C8]; void **
0x180070081  mov     [rsp+120h+var_100], rax; unsigned __int64 *
0x180070086  lea     r8, [rbp+57h+var_C0]; void **
0x18007008a  mov     rdx, rbx; unsigned __int64
0x18007008d  mov     rcx, [rcx+30h]; void *
0x180070091  call    ?AlpcAllocateSectionAndView@@YAJPEAX_KPEAPEAX2PEA_K@Z; AlpcAllocateSectionAndView(void *,unsigned __int64,void * *,void * *,unsigned __int64 *)
0x180070096  mov     r15, [rbp+57h+var_C8]
0x18007009a  mov     esi, eax
0x18007009c  test    eax, eax
0x18007009e  jz      loc_18007015B
0x1800700a4  mov     r12, [rbp+57h+var_C0]
0x1800700a8  jmp     short loc_1800700D4
0x1800700aa  mov     r9d, 1; int
0x1800700b0  mov     [rbp+57h+var_B0], eax
0x1800700b3  lea     rax, [rbp+57h+var_B8]
0x1800700b7  mov     [rbp+57h+var_B8], 3
0x1800700be  mov     r8d, 500h; unsigned __int16
0x1800700c4  mov     [rsp+120h+var_100], rax; struct tagParam *
0x1800700c9  mov     edx, esi; int
0x1800700cb  lea     ecx, [r9+1]; unsigned int
0x1800700cf  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800700d4  mov     rax, [rdi+250h]
0x1800700db  dec     dword ptr [rax+8]
0x1800700de  test    r15, r15
0x1800700e1  jz      loc_18006FEAC
0x1800700e7  mov     rbx, [rdi+130h]
0x1800700ee  mov     r9, r15; void *
0x1800700f1  mov     dl, 44h ; 'D'; unsigned __int8
0x1800700f3  mov     [rsp+120h+var_100], 1; unsigned __int64
0x1800700fc  mov     cl, 4Ch ; 'L'; unsigned __int8
0x1800700fe  mov     r8, [rbx+30h]; void *
0x180070102  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x180070107  mov     rcx, [rbx+30h]
0x18007010b  mov     r8, r15
0x18007010e  xor     edx, edx
0x180070110  call    cs:__imp_NtAlpcDeleteSectionView
0x180070117  nop     dword ptr [rax+rax+00h]
0x18007011c  jmp     loc_18006FEAC
0x180070121  mov     esi, 0Eh
0x180070126  jmp     loc_18006FEC2
0x18007012b  mov     esi, 6BFh
0x180070130  jmp     loc_18006FEC2
0x180070135  mov     esi, 0Eh
0x18007013a  mov     r12, r15
0x18007013d  jmp     short loc_1800700D4
0x18007013f  mov     rdx, [rdi+1C0h]
0x180070146  lea     rcx, [r14+68h]; void *
0x18007014a  add     rdx, 40h ; '@'; Src
0x18007014e  mov     r8, rax; Size
0x180070151  call    memcpy_0
  ... truncated ...
```
