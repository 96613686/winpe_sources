# Tpm20ResourceMgr::DeleteTpm20Context(Tpm20Context *,bool)

- ea: `0x140008aac`
- end: `0x140008bf4`
- name: `?DeleteTpm20Context@Tpm20ResourceMgr@@QEAAXPEAVTpm20Context@@_N@Z`
- size: `328`
- prototype: `void(Tpm20ResourceMgr *__hidden this, struct Tpm20Context *, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14001b974`

## callees

- `0x1400078e8`
- `0x140008758`
- `0x140008aac`
- `0x140008f6c`
- `0x140008fb0`
- `0x140008fec`
- `0x14001b1ac`
- `0x14001b6f4`

## pseudocode

```c
void __fastcall Tpm20ResourceMgr::DeleteTpm20Context(Tpm20ResourceMgr *this, struct Tpm20Context **a2, char a3)
{
  Tpm20ResourceMgr *v6; // rcx
  struct Tpm20Context *v7; // rbx
  char v8; // al
  struct Tpm20Context *v9; // rbp
  int v10; // eax
  __int64 v11; // r8
  char v12; // r14

  v6 = (Tpm20ResourceMgr *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids, a2);
  v7 = a2[1];
  if ( v7 != (struct Tpm20Context *)(a2 + 1) )
  {
    do
    {
      v8 = *((_BYTE *)v7 + 60);
      v9 = *(struct Tpm20Context **)v7;
      if ( !v8 && *((_DWORD *)v7 + 14) != 1 )
        goto LABEL_11;
      if ( a3 )
      {
        v10 = Tpm20CmdFlushContextWorker(
                0,
                0,
                *(_QWORD *)this,
                *(unsigned int *)((char *)v7 + (-(__int64)(v8 != 0) & 0xFFFFFFFFFFFFFFFCuLL) + 52));
        v12 = v10;
        if ( v10 )
        {
          v6 = (Tpm20ResourceMgr *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_DDD(
              WPP_GLOBAL_Control->AttachedDevice,
              20,
              WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids,
              *((unsigned int *)v7 + 12),
              *((_DWORD *)v7 + 13),
              v10);
          }
          if ( (TPMEnableBits & 1) != 0 )
            McTemplateK0dqq_EtwWriteTransfer(
              (__int64)v6,
              (const EVENT_DESCRIPTOR *)TPM_HW_PROTOCOL_ERROR,
              v11,
              30,
              43,
              v12);
        }
      }
      if ( *((_BYTE *)v7 + 60) )
        Tpm20ResourceMgr::RemovedLoadedResource(v6, (const struct Tpm20Context *)a2, v7);
      else
LABEL_11:
        Tpm20ResourceMgr::RemovedNonloadedResource(v6, (const struct Tpm20Context *)a2, v7);
      v7 = v9;
    }
    while ( v9 != (struct Tpm20Context *)(a2 + 1) );
  }
  if ( a2 )
    Tpm20Context::`scalar deleting destructor'((Tpm20Context *)a2, (unsigned int)a2);
}

```

## disassembly

```asm
0x140008aac  push    rbx
0x140008aae  push    rbp
0x140008aaf  push    rsi
0x140008ab0  push    rdi
0x140008ab1  push    r12
0x140008ab3  push    r13
0x140008ab5  push    r14
0x140008ab7  push    r15
0x140008ab9  sub     rsp, 38h
0x140008abd  mov     r15b, r8b
0x140008ac0  mov     rdi, rdx
0x140008ac3  mov     r12, rcx
0x140008ac6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140008acd  lea     r13, WPP_GLOBAL_Control
0x140008ad4  cmp     rcx, r13
0x140008ad7  jz      short loc_140008AF8
0x140008ad9  mov     eax, [rcx+2Ch]
0x140008adc  test    al, 4
0x140008ade  jz      short loc_140008AF8
0x140008ae0  mov     rcx, [rcx+18h]
0x140008ae4  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x140008aeb  mov     edx, 13h
0x140008af0  mov     r9, rdi
0x140008af3  call    WPP_SF_q
0x140008af8  lea     rsi, [rdi+8]
0x140008afc  mov     rbx, [rsi]
0x140008aff  cmp     rbx, rsi
0x140008b02  jnz     short loc_140008B23
0x140008b04  test    rdi, rdi
0x140008b07  jz      short loc_140008B11
0x140008b09  mov     rcx, rdi; this
0x140008b0c  call    ??_GTpm20Context@@AEAAPEAXI@Z; Tpm20Context::`scalar deleting destructor'(uint)
0x140008b11  add     rsp, 38h
0x140008b15  pop     r15
0x140008b17  pop     r14
0x140008b19  pop     r13
0x140008b1b  pop     r12
0x140008b1d  pop     rdi
0x140008b1e  pop     rsi
0x140008b1f  pop     rbp
0x140008b20  pop     rbx
0x140008b21  retn
0x140008b23  mov     al, [rbx+3Ch]
0x140008b26  mov     rbp, [rbx]
0x140008b29  test    al, al
0x140008b2b  jz      short loc_140008B51
0x140008b2d  test    r15b, r15b
0x140008b30  jnz     short loc_140008B59
0x140008b32  cmp     byte ptr [rbx+3Ch], 0
0x140008b36  jnz     loc_140008BE4
0x140008b3c  mov     r8, rbx; struct Tpm20Resource *
0x140008b3f  mov     rdx, rdi; struct Tpm20Context *
0x140008b42  call    ?RemovedNonloadedResource@Tpm20ResourceMgr@@AEAAXPEBVTpm20Context@@PEAVTpm20Resource@@@Z; Tpm20ResourceMgr::RemovedNonloadedResource(Tpm20Context const *,Tpm20Resource *)
0x140008b47  mov     rbx, rbp
0x140008b4a  cmp     rbp, rsi
0x140008b4d  jz      short loc_140008B04
0x140008b4f  jmp     short loc_140008B23
0x140008b51  cmp     dword ptr [rbx+38h], 1
0x140008b55  jnz     short loc_140008B3C
0x140008b57  jmp     short loc_140008B2D
0x140008b59  mov     r8, [r12]
0x140008b5d  neg     al
0x140008b5f  sbb     r9, r9
0x140008b62  xor     edx, edx
0x140008b64  and     r9, 0FFFFFFFFFFFFFFFCh
0x140008b68  xor     ecx, ecx
0x140008b6a  mov     r9d, [r9+rbx+34h]
0x140008b6f  call    ?Tpm20CmdFlushContextWorker@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAVTpmTransport@@T_TPM20_HANDLE@@@Z; Tpm20CmdFlushContextWorker(Tpm20Context *,TpmStack *,TpmTransport *,_TPM20_HANDLE)
0x140008b74  mov     r14d, eax
0x140008b77  test    eax, eax
0x140008b79  jz      short loc_140008B32
0x140008b7b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140008b82  cmp     rcx, r13
0x140008b85  jz      short loc_140008BB3
0x140008b87  mov     edx, [rcx+2Ch]
0x140008b8a  test    dl, 1
0x140008b8d  jz      short loc_140008BB3
0x140008b8f  mov     r9d, [rbx+30h]
0x140008b93  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x140008b9a  mov     rcx, [rcx+18h]
0x140008b9e  mov     edx, 14h
0x140008ba3  mov     [rsp+78h+var_50], eax
0x140008ba7  mov     eax, [rbx+34h]
0x140008baa  mov     [rsp+78h+var_58], eax
0x140008bae  call    WPP_SF_DDD
0x140008bb3  test    cs:TPMEnableBits, 1
0x140008bba  jz      loc_140008B32
0x140008bc0  mov     [rsp+78h+var_50], r14d
0x140008bc5  lea     rdx, TPM_HW_PROTOCOL_ERROR
0x140008bcc  mov     r9d, 1Eh
0x140008bd2  mov     [rsp+78h+var_58], 22Bh
0x140008bda  call    McTemplateK0dqq_EtwWriteTransfer
0x140008bdf  jmp     loc_140008B32
0x140008be4  mov     r8, rbx; struct Tpm20Resource *
0x140008be7  mov     rdx, rdi; struct Tpm20Context *
0x140008bea  call    ?RemovedLoadedResource@Tpm20ResourceMgr@@AEAAXPEBVTpm20Context@@PEAVTpm20Resource@@@Z; Tpm20ResourceMgr::RemovedLoadedResource(Tpm20Context const *,Tpm20Resource *)
0x140008bef  jmp     loc_140008B47
```
