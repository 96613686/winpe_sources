# Tpm20Scheduler::DoContextCleanup(void)

- ea: `0x140008bfc`
- end: `0x140008d99`
- name: `?DoContextCleanup@Tpm20Scheduler@@AEAAXXZ`
- size: `413`
- prototype: `void __fastcall(Tpm20Scheduler *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400179c4`

## callees

- `0x1400078e8`
- `0x140008758`
- `0x140008bfc`
- `0x140008f6c`
- `0x140008fb0`
- `0x140008fec`
- `0x14001b1ac`
- `0x14001b6f4`

## import_xrefs

- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x140008c1e`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x140008c93`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x140008c1e`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x140008c93`

## pseudocode

```c
void __fastcall Tpm20Scheduler::DoContextCleanup(KSPIN_LOCK *this)
{
  KSPIN_LOCK *v1; // r12
  struct _LIST_ENTRY *v3; // r13
  PLIST_ENTRY v4; // rax
  PDEVICE_OBJECT *v5; // rdx
  struct _LIST_ENTRY **p_Blink; // rdi
  Tpm20ResourceMgr *v7; // rcx
  struct _LIST_ENTRY *v8; // rbx
  char v9; // al
  struct _LIST_ENTRY **p_Flink; // r14
  int v11; // eax
  int v12; // r8d
  char v13; // r15
  _QWORD *v14; // [rsp+80h] [rbp+8h]

  v1 = this + 14;
  v3 = (struct _LIST_ENTRY *)(this + 15);
  v4 = ExInterlockedRemoveHeadList((PLIST_ENTRY)(this + 15), this + 14);
  if ( v4 )
  {
    v5 = &WPP_GLOBAL_Control;
    do
    {
      p_Blink = &v4[-2].Blink;
      v14 = (_QWORD *)this[17];
      v7 = (Tpm20ResourceMgr *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids, p_Blink);
      v8 = p_Blink[1];
      if ( v8 != (struct _LIST_ENTRY *)(p_Blink + 1) )
      {
        do
        {
          v9 = BYTE4(v8[3].Blink);
          p_Flink = &v8->Flink->Flink;
          if ( !v9 && LODWORD(v8[3].Blink) != 1 )
            goto LABEL_20;
          v11 = Tpm20CmdFlushContextWorker(
                  0,
                  0,
                  *v14,
                  *(unsigned int *)((char *)&v8[3].Flink + (-(__int64)(v9 != 0) & 0xFFFFFFFFFFFFFFFCuLL) + 4));
          v13 = v11;
          if ( v11 )
          {
            v7 = (Tpm20ResourceMgr *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_DDD(
                WPP_GLOBAL_Control->AttachedDevice,
                20,
                WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids,
                LODWORD(v8[3].Flink),
                HIDWORD(v8[3].Flink),
                v11);
            }
            if ( (TPMEnableBits & 1) != 0 )
              McTemplateK0dqq_EtwWriteTransfer((_DWORD)v7, (unsigned int)TPM_HW_PROTOCOL_ERROR, v12, 30, 43, v13);
          }
          if ( BYTE4(v8[3].Blink) )
            Tpm20ResourceMgr::RemovedLoadedResource(
              v7,
              (const struct Tpm20Context *)p_Blink,
              (struct Tpm20Resource *)v8);
          else
LABEL_20:
            Tpm20ResourceMgr::RemovedNonloadedResource(
              v7,
              (const struct Tpm20Context *)p_Blink,
              (struct Tpm20Resource *)v8);
          v8 = (struct _LIST_ENTRY *)p_Flink;
        }
        while ( p_Flink != p_Blink + 1 );
        v1 = this + 14;
        v3 = (struct _LIST_ENTRY *)(this + 15);
      }
      if ( p_Blink )
        Tpm20Context::`scalar deleting destructor'((Tpm20Context *)p_Blink, (unsigned int)v5);
      v4 = ExInterlockedRemoveHeadList(v3, v1);
      v5 = &WPP_GLOBAL_Control;
    }
    while ( v4 );
  }
}

```

## disassembly

```asm
0x140008bfc  push    rbx
0x140008bfe  push    rbp
0x140008bff  push    rsi
0x140008c00  push    rdi
0x140008c01  push    r12
0x140008c03  push    r13
0x140008c05  push    r14
0x140008c07  push    r15
0x140008c09  sub     rsp, 38h
0x140008c0d  lea     r12, [rcx+70h]
0x140008c11  mov     rbp, rcx
0x140008c14  lea     r13, [rcx+78h]
0x140008c18  mov     rdx, r12; Lock
0x140008c1b  mov     rcx, r13; ListHead
0x140008c1e  call    cs:__imp_ExInterlockedRemoveHeadList
0x140008c25  nop     dword ptr [rax+rax+00h]
0x140008c2a  test    rax, rax
0x140008c2d  jz      short loc_140008CAB
0x140008c2f  lea     rdx, WPP_GLOBAL_Control
0x140008c36  lea     rdi, [rax-18h]
0x140008c3a  mov     rax, [rbp+88h]
0x140008c41  mov     [rsp+78h+arg_0], rax
0x140008c49  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140008c50  cmp     rcx, rdx
0x140008c53  jz      short loc_140008C74
0x140008c55  mov     eax, [rcx+2Ch]
0x140008c58  test    al, 4
0x140008c5a  jz      short loc_140008C74
0x140008c5c  mov     rcx, [rcx+18h]
0x140008c60  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x140008c67  mov     edx, 13h
0x140008c6c  mov     r9, rdi
0x140008c6f  call    WPP_SF_q
0x140008c74  lea     rsi, [rdi+8]
0x140008c78  mov     rbx, [rsi]
0x140008c7b  cmp     rbx, rsi
0x140008c7e  jnz     short loc_140008CBD
0x140008c80  test    rdi, rdi
0x140008c83  jz      short loc_140008C8D
0x140008c85  mov     rcx, rdi; this
0x140008c88  call    ??_GTpm20Context@@AEAAPEAXI@Z; Tpm20Context::`scalar deleting destructor'(uint)
0x140008c8d  mov     rdx, r12; Lock
0x140008c90  mov     rcx, r13; ListHead
0x140008c93  call    cs:__imp_ExInterlockedRemoveHeadList
0x140008c9a  nop     dword ptr [rax+rax+00h]
0x140008c9f  lea     rdx, WPP_GLOBAL_Control
0x140008ca6  test    rax, rax
0x140008ca9  jnz     short loc_140008C36
0x140008cab  add     rsp, 38h
0x140008caf  pop     r15
0x140008cb1  pop     r14
0x140008cb3  pop     r13
0x140008cb5  pop     r12
0x140008cb7  pop     rdi
0x140008cb8  pop     rsi
0x140008cb9  pop     rbp
0x140008cba  pop     rbx
0x140008cbb  retn
0x140008cbd  mov     r12, [rsp+78h+arg_0]
0x140008cc5  lea     r13, WPP_GLOBAL_Control
0x140008ccc  mov     al, [rbx+3Ch]
0x140008ccf  mov     r14, [rbx]
0x140008cd2  test    al, al
0x140008cd4  jnz     short loc_140008CE0
0x140008cd6  cmp     dword ptr [rbx+38h], 1
0x140008cda  jnz     loc_140008D68
0x140008ce0  mov     r8, [r12]
0x140008ce4  neg     al
0x140008ce6  sbb     r9, r9
0x140008ce9  xor     edx, edx
0x140008ceb  and     r9, 0FFFFFFFFFFFFFFFCh
0x140008cef  xor     ecx, ecx
0x140008cf1  mov     r9d, [r9+rbx+34h]
0x140008cf6  call    ?Tpm20CmdFlushContextWorker@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAVTpmTransport@@T_TPM20_HANDLE@@@Z; Tpm20CmdFlushContextWorker(Tpm20Context *,TpmStack *,TpmTransport *,_TPM20_HANDLE)
0x140008cfb  mov     r15d, eax
0x140008cfe  test    eax, eax
0x140008d00  jz      short loc_140008D62
0x140008d02  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140008d09  cmp     rcx, r13
0x140008d0c  jz      short loc_140008D3A
0x140008d0e  mov     edx, [rcx+2Ch]
0x140008d11  test    dl, 1
0x140008d14  jz      short loc_140008D3A
0x140008d16  mov     r9d, [rbx+30h]
0x140008d1a  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x140008d21  mov     rcx, [rcx+18h]
0x140008d25  mov     edx, 14h
0x140008d2a  mov     [rsp+78h+var_50], eax
0x140008d2e  mov     eax, [rbx+34h]
0x140008d31  mov     [rsp+78h+var_58], eax
0x140008d35  call    WPP_SF_DDD
0x140008d3a  test    cs:TPMEnableBits, 1
0x140008d41  jz      short loc_140008D62
0x140008d43  mov     [rsp+78h+var_50], r15d
0x140008d48  lea     rdx, TPM_HW_PROTOCOL_ERROR
0x140008d4f  mov     r9d, 1Eh
0x140008d55  mov     [rsp+78h+var_58], 22Bh
0x140008d5d  call    McTemplateK0dqq_EtwWriteTransfer
0x140008d62  cmp     byte ptr [rbx+3Ch], 0
0x140008d66  jnz     short loc_140008D8C
0x140008d68  mov     r8, rbx; struct Tpm20Resource *
0x140008d6b  mov     rdx, rdi; struct Tpm20Context *
0x140008d6e  call    ?RemovedNonloadedResource@Tpm20ResourceMgr@@AEAAXPEBVTpm20Context@@PEAVTpm20Resource@@@Z; Tpm20ResourceMgr::RemovedNonloadedResource(Tpm20Context const *,Tpm20Resource *)
0x140008d73  mov     rbx, r14
0x140008d76  cmp     r14, rsi
0x140008d79  jnz     loc_140008CCC
0x140008d7f  lea     r12, [rbp+70h]
0x140008d83  lea     r13, [rbp+78h]
0x140008d87  jmp     loc_140008C80
0x140008d8c  mov     r8, rbx; struct Tpm20Resource *
0x140008d8f  mov     rdx, rdi; struct Tpm20Context *
0x140008d92  call    ?RemovedLoadedResource@Tpm20ResourceMgr@@AEAAXPEBVTpm20Context@@PEAVTpm20Resource@@@Z; Tpm20ResourceMgr::RemovedLoadedResource(Tpm20Context const *,Tpm20Resource *)
0x140008d97  jmp     short loc_140008D73
```
