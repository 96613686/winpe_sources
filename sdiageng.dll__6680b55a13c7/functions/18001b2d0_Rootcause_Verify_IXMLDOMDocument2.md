# Rootcause::Verify(IXMLDOMDocument2 *)

- ea: `0x18001b2d0`
- end: `0x18001b3b1`
- name: `?Verify@Rootcause@@QEAAJPEAUIXMLDOMDocument2@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY **this, struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001790c`

## callees

- `0x180019ed8`
- `0x18001a02c`
- `0x18001b2d0`
- `0x18001b3b8`
- `0x18001bb50`
- `0x180026fa0`

## pseudocode

```c
__int64 __fastcall Rootcause::Verify(struct _LIST_ENTRY **this, struct IXMLDOMDocument2 *a2)
{
  unsigned int v2; // ebx
  int FirstInstance; // eax
  unsigned int v6; // r8d
  unsigned int v7; // r14d
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *v8; // rdx
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *v9; // rdi
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *v11; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  v11 = 0;
  if ( this[3] )
  {
    FirstInstance = Rootcause::GetFirstInstance((Rootcause *)this, this[15], &v11);
    v2 = FirstInstance;
    if ( FirstInstance >= 0 )
    {
      while ( 1 )
      {
        v9 = v11;
        if ( !v11 )
          break;
        v7 = *((_DWORD *)v11 + 6);
        if ( v7 > 1 )
        {
          v8 = v11;
          *((_DWORD *)v11 + 6) = 2;
          FirstInstance = Rootcause::VerifyInstance((Rootcause *)this, v8);
          v2 = FirstInstance;
          if ( FirstInstance < 0 )
          {
            *((_DWORD *)v9 + 6) = v7;
            v6 = 326;
            goto LABEL_10;
          }
        }
        FirstInstance = Rootcause::GetNextInstance((Rootcause *)this, this[15], (struct _LIST_ENTRY **)&v11);
        v2 = FirstInstance;
        if ( FirstInstance < 0 )
        {
          v6 = 331;
          goto LABEL_10;
        }
      }
      FirstInstance = Rootcause::get_VerificationResult(this, a2);
      v2 = FirstInstance;
      if ( FirstInstance >= 0 )
        return v2;
      v6 = 335;
    }
    else
    {
      v6 = 316;
    }
LABEL_10:
    SdpDebugTrace(1u, L"Rootcause::Verify", v6, FirstInstance);
  }
  return v2;
}

```

## disassembly

```asm
0x18001b2d0  mov     rax, rsp
0x18001b2d3  mov     [rax+10h], rbx
0x18001b2d7  mov     [rax+18h], rsi
0x18001b2db  push    rdi
0x18001b2dc  push    r14
0x18001b2de  push    r15
0x18001b2e0  sub     rsp, 20h
0x18001b2e4  xor     ebx, ebx
0x18001b2e6  mov     qword ptr [rax+8], 0
0x18001b2ee  mov     r15, rdx
0x18001b2f1  mov     rsi, rcx
0x18001b2f4  cmp     [rcx+18h], rbx
0x18001b2f8  jz      loc_18001B387
0x18001b2fe  mov     rdx, [rcx+78h]; struct _LIST_ENTRY *
0x18001b302  lea     r8, [rax+8]; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE **
0x18001b306  call    ?GetFirstInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::GetFirstInstance(_LIST_ENTRY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)
0x18001b30b  mov     ebx, eax
0x18001b30d  test    eax, eax
0x18001b30f  jns     short loc_18001B352
0x18001b311  mov     r8d, 13Ch
0x18001b317  jmp     short loc_18001B373
0x18001b319  mov     r14d, [rdi+18h]
0x18001b31d  cmp     r14d, 1
0x18001b321  jbe     short loc_18001B33B
0x18001b323  mov     rdx, rdi; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *
0x18001b326  mov     dword ptr [rdi+18h], 2
0x18001b32d  mov     rcx, rsi; this
0x18001b330  call    ?VerifyInstance@Rootcause@@AEAAJPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::VerifyInstance(Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *)
0x18001b335  mov     ebx, eax
0x18001b337  test    eax, eax
0x18001b339  js      short loc_18001B39D
0x18001b33b  mov     rdx, [rsi+78h]; struct _LIST_ENTRY *
0x18001b33f  lea     r8, [rsp+38h+arg_0]; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE **
0x18001b344  mov     rcx, rsi; this
0x18001b347  call    ?GetNextInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::GetNextInstance(_LIST_ENTRY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)
0x18001b34c  mov     ebx, eax
0x18001b34e  test    eax, eax
0x18001b350  js      short loc_18001B3A9
0x18001b352  mov     rdi, [rsp+38h+arg_0]
0x18001b357  test    rdi, rdi
0x18001b35a  jnz     short loc_18001B319
0x18001b35c  mov     rdx, r15; struct IXMLDOMDocument2 *
0x18001b35f  mov     rcx, rsi; this
0x18001b362  call    ?get_VerificationResult@Rootcause@@AEAAJPEAUIXMLDOMDocument2@@@Z; Rootcause::get_VerificationResult(IXMLDOMDocument2 *)
0x18001b367  mov     ebx, eax
0x18001b369  test    eax, eax
0x18001b36b  jns     short loc_18001B387
0x18001b36d  mov     r8d, 14Fh; int
0x18001b373  mov     r9d, eax; int
0x18001b376  lea     rdx, aRootcauseVerif; "Rootcause::Verify"
0x18001b37d  mov     ecx, 1; Level
0x18001b382  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001b387  mov     rsi, [rsp+38h+arg_10]
0x18001b38c  mov     eax, ebx
0x18001b38e  mov     rbx, [rsp+38h+arg_8]
0x18001b393  add     rsp, 20h
0x18001b397  pop     r15
0x18001b399  pop     r14
0x18001b39b  pop     rdi
0x18001b39c  retn
0x18001b39d  mov     [rdi+18h], r14d
0x18001b3a1  mov     r8d, 146h
0x18001b3a7  jmp     short loc_18001B373
0x18001b3a9  mov     r8d, 14Bh
0x18001b3af  jmp     short loc_18001B373
```
