# DeleteInterfaceFromSourceMfe

- ea: `0x18001d908`
- end: `0x18001db80`
- name: `DeleteInterfaceFromSourceMfe`
- size: `632`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180012800`
- `0x18001d2a0`
- `0x18001d378`

## callees

- `0x18001b548`
- `0x18001d908`
- `0x18001db88`
- `0x18001dcbc`
- `0x18001f11c`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `ntdll!RtlUpdateTimer` at `0x18001db3b`
- `ntdll!RtlUpdateTimer` at `0x18001db3b`

## string_xrefs

- `0x18001daa6`: `Invoked Prune Alert for protocol %x, %x`
- `0x18001da5d`: `DeleteInterfaceFromSourceMfe : Protocol not found%x, %x`

## pseudocode

```c
int __fastcall DeleteInterfaceFromSourceMfe(__int64 a1, __int64 a2, int a3, int a4, int a5, int a6, int a7, int a8)
{
  __int64 ProtocolEntry; // rax
  __int16 *v13; // rcx
  bool v14; // zf
  int v15; // edi
  unsigned int v16; // edx
  unsigned int v17; // r8d
  __int64 v18; // rbx
  ULONG DueTime; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[4]; // [rsp+54h] [rbp-ACh] BYREF
  __int16 *v22; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  DueTime = 0;
  v22 = 0;
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  LODWORD(ProtocolEntry) = FindOutInterfaceEntry((int)a2 + 88, a3, a4, a5, a6, (__int64)v21, (__int64)&v22);
  if ( !(_DWORD)ProtocolEntry )
    return ProtocolEntry;
  v13 = v22;
  if ( a7 )
  {
    if ( v22[17] >= 0 )
      goto LABEL_10;
    LODWORD(ProtocolEntry) = 0xFFFF;
    v14 = v22[18]-- == 1;
    if ( !v14 )
      goto LABEL_10;
    LODWORD(ProtocolEntry) = 0x7FFF;
  }
  else
  {
    if ( (v22[17] & 0x4000) == 0 )
      goto LABEL_10;
    LODWORD(ProtocolEntry) = 0xFFFF;
    v14 = v22[19]-- == 1;
    if ( !v14 )
      goto LABEL_10;
    LODWORD(ProtocolEntry) = 49151;
  }
  v13[17] &= ProtocolEntry;
LABEL_10:
  if ( a8 || (v15 = 0, v13[17] >= 0) && (v13[17] & 0x4000) == 0 )
  {
    LODWORD(ProtocolEntry) = DeleteOutInterfaceEntry(v13, 0x4000);
    --*(_DWORD *)(a2 + 80);
    v15 = *(_DWORD *)(a2 + 144);
  }
  if ( *(_QWORD *)(a2 + 88) == a2 + 88 )
  {
    ProtocolEntry = GetProtocolEntry(&qword_18002B9A8, *(unsigned int *)(a2 + 136), *(unsigned int *)(a2 + 140));
    v18 = ProtocolEntry;
    if ( ProtocolEntry )
    {
      if ( *(_QWORD *)(ProtocolEntry + 56) )
      {
        if ( qword_18002B8A8 )
        {
          LOWORD(v23) = 0;
          FormatRRASErrorString(
            &v23,
            L"Invoked Prune Alert for protocol %x, %x",
            *(unsigned int *)(ProtocolEntry + 16),
            *(unsigned int *)(ProtocolEntry + 20));
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v23);
        }
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, ULONG *))(v18 + 56))(
          *(unsigned int *)(a2 + 104),
          *(unsigned int *)(a2 + 108),
          *(unsigned int *)(a1 + 32),
          *(unsigned int *)(a1 + 36),
          *(_DWORD *)(a2 + 112),
          *(_DWORD *)(a2 + 116),
          0,
          &DueTime);
        LODWORD(ProtocolEntry) = RtlUpdateTimer(
                                   *((HANDLE *)qword_18002BA48 + *(_DWORD *)(a1 + 32) % (unsigned int)dword_18002B95C),
                                   *(HANDLE *)(a2 + 152),
                                   DueTime,
                                   0);
      }
    }
    else if ( qword_18002B8A8 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"DeleteInterfaceFromSourceMfe : Protocol not found%x, %x", v16, v17);
      LODWORD(ProtocolEntry) = ((__int64 (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(
                                 gMgmEtwContext,
                                 qword_18002B8A8,
                                 &v23);
    }
  }
  if ( v15 )
    LODWORD(ProtocolEntry) = AddMfeToForwarder(a1, a2, DueTime);
  return ProtocolEntry;
}

```

## disassembly

```asm
0x18001d908  mov     [rsp-8+arg_10], rbx
0x18001d90d  mov     [rsp-8+arg_18], rsi
0x18001d912  push    rbp
0x18001d913  push    rdi
0x18001d914  push    r12
0x18001d916  push    r14
0x18001d918  push    r15
0x18001d91a  lea     rbp, [rsp-770h]
0x18001d922  sub     rsp, 870h
0x18001d929  mov     rax, cs:__security_cookie
0x18001d930  xor     rax, rsp
0x18001d933  mov     [rbp+790h+var_30], rax
0x18001d93a  xor     r12d, r12d
0x18001d93d  mov     edi, r8d
0x18001d940  mov     rsi, rdx
0x18001d943  mov     [rsp+890h+DueTime], r12d
0x18001d948  mov     r15, rcx
0x18001d94b  mov     [rsp+890h+var_838], r12
0x18001d950  xor     edx, edx; Val
0x18001d952  mov     [rsp+890h+var_830], r12d
0x18001d957  mov     r8d, 7FCh; Size
0x18001d95d  lea     rcx, [rsp+890h+var_82C]; void *
0x18001d962  mov     ebx, r9d
0x18001d965  call    memset_0
0x18001d96a  mov     r9d, [rbp+790h+arg_20]
0x18001d971  lea     rax, [rsp+890h+var_838]
0x18001d976  mov     [rsp+890h+var_860], rax
0x18001d97b  lea     r14, [rsi+58h]
0x18001d97f  lea     rax, [rsp+890h+var_83C]
0x18001d984  mov     r8d, ebx
0x18001d987  mov     [rsp+890h+var_868], rax
0x18001d98c  mov     edx, edi
0x18001d98e  mov     eax, [rbp+790h+arg_28]
0x18001d994  mov     rcx, r14
0x18001d997  mov     [rsp+890h+var_870], eax
0x18001d99b  call    FindOutInterfaceEntry
0x18001d9a0  test    eax, eax
0x18001d9a2  jz      loc_18001DB55
0x18001d9a8  mov     edx, 4000h
0x18001d9ad  mov     rcx, [rsp+890h+var_838]
0x18001d9b2  cmp     [rbp+790h+arg_30], r12d
0x18001d9b9  jz      short loc_18001D9D4
0x18001d9bb  cmp     [rcx+22h], r12w
0x18001d9c0  jge     short loc_18001D9EE
0x18001d9c2  mov     eax, 0FFFFh
0x18001d9c7  add     [rcx+24h], ax
0x18001d9cb  jnz     short loc_18001D9EE
0x18001d9cd  mov     eax, 7FFFh
0x18001d9d2  jmp     short loc_18001D9EA
0x18001d9d4  test    [rcx+22h], dx
0x18001d9d8  jz      short loc_18001D9EE
0x18001d9da  mov     eax, 0FFFFh
0x18001d9df  add     [rcx+26h], ax
0x18001d9e3  jnz     short loc_18001D9EE
0x18001d9e5  mov     eax, 0BFFFh
0x18001d9ea  and     [rcx+22h], ax
0x18001d9ee  cmp     [rbp+790h+arg_38], r12d
0x18001d9f5  jnz     short loc_18001DA07
0x18001d9f7  mov     edi, r12d
0x18001d9fa  cmp     [rcx+22h], r12w
0x18001d9ff  jl      short loc_18001DA15
0x18001da01  test    [rcx+22h], dx
0x18001da05  jnz     short loc_18001DA15
0x18001da07  call    DeleteOutInterfaceEntry
0x18001da0c  dec     dword ptr [rsi+50h]
0x18001da0f  mov     edi, [rsi+90h]
0x18001da15  cmp     [r14], r14
0x18001da18  jnz     loc_18001DB41
0x18001da1e  mov     r8d, [rsi+8Ch]
0x18001da25  lea     rcx, qword_18002B9A8
0x18001da2c  mov     edx, [rsi+88h]
0x18001da32  call    GetProtocolEntry
0x18001da37  mov     rbx, rax
0x18001da3a  test    rax, rax
0x18001da3d  jnz     short loc_18001DA8D
0x18001da3f  cmp     cs:qword_18002B8A8, r12
0x18001da46  jz      loc_18001DB41
0x18001da4c  mov     r9d, r8d
0x18001da4f  mov     word ptr [rsp+890h+var_830], r12w
0x18001da55  mov     r8d, edx
0x18001da58  lea     rcx, [rsp+890h+var_830]
0x18001da5d  lea     rdx, aDeleteinterfac; "DeleteInterfaceFromSourceMfe : Protocol"...
0x18001da64  call    FormatRRASErrorString
0x18001da69  mov     rdx, cs:qword_18002B8A8
0x18001da70  lea     r8, [rsp+890h+var_830]
0x18001da75  mov     rcx, cs:gMgmEtwContext
0x18001da7c  mov     rax, cs:gMgmTemplateFunc
0x18001da83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da88  jmp     loc_18001DB41
0x18001da8d  cmp     [rax+38h], r12
0x18001da91  jz      loc_18001DB41
0x18001da97  cmp     cs:qword_18002B8A8, r12
0x18001da9e  jz      short loc_18001DADE
0x18001daa0  mov     word ptr [rsp+890h+var_830], r12w
0x18001daa6  lea     rdx, aInvokedPruneAl; "Invoked Prune Alert for protocol %x, %x"
0x18001daad  mov     r9d, [rax+14h]
0x18001dab1  lea     rcx, [rsp+890h+var_830]
0x18001dab6  mov     r8d, [rax+10h]
0x18001daba  call    FormatRRASErrorString
0x18001dabf  mov     rdx, cs:qword_18002B8A8
0x18001dac6  lea     r8, [rsp+890h+var_830]
0x18001dacb  mov     rcx, cs:gMgmEtwContext
0x18001dad2  mov     rax, cs:gMgmTemplateFunc
0x18001dad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dade  mov     ecx, [rsi+74h]
0x18001dae1  lea     rax, [rsp+890h+DueTime]
0x18001dae6  mov     r9d, [r15+24h]
0x18001daea  mov     r8d, [r15+20h]
0x18001daee  mov     edx, [rsi+6Ch]
0x18001daf1  mov     [rsp+890h+var_858], rax
0x18001daf6  mov     rax, [rbx+38h]
0x18001dafa  mov     dword ptr [rsp+890h+var_860], r12d
0x18001daff  mov     dword ptr [rsp+890h+var_868], ecx
0x18001db03  mov     ecx, [rsi+70h]
0x18001db06  mov     [rsp+890h+var_870], ecx
0x18001db0a  mov     ecx, [rsi+68h]
0x18001db0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db12  mov     eax, [r15+20h]
0x18001db16  xor     edx, edx
0x18001db18  div     cs:dword_18002B95C
0x18001db1e  mov     rcx, cs:qword_18002BA48
0x18001db25  xor     r9d, r9d; Period
0x18001db28  mov     r8d, [rsp+890h+DueTime]; DueTime
0x18001db2d  mov     r10d, edx
0x18001db30  mov     rdx, [rsi+98h]; Timer
0x18001db37  mov     rcx, [rcx+r10*8]; TimerQueue
0x18001db3b  call    cs:__imp_RtlUpdateTimer
0x18001db41  test    edi, edi
0x18001db43  jz      short loc_18001DB55
0x18001db45  mov     r8d, [rsp+890h+DueTime]
0x18001db4a  mov     rdx, rsi
0x18001db4d  mov     rcx, r15
0x18001db50  call    AddMfeToForwarder
0x18001db55  mov     rcx, [rbp+790h+var_30]
0x18001db5c  xor     rcx, rsp; StackCookie
0x18001db5f  call    __security_check_cookie
0x18001db64  lea     r11, [rsp+890h+var_20]
0x18001db6c  mov     rbx, [r11+40h]
0x18001db70  mov     rsi, [r11+48h]
0x18001db74  mov     rsp, r11
0x18001db77  pop     r15
0x18001db79  pop     r14
0x18001db7b  pop     r12
0x18001db7d  pop     rdi
0x18001db7e  pop     rbp
0x18001db7f  retn
```
