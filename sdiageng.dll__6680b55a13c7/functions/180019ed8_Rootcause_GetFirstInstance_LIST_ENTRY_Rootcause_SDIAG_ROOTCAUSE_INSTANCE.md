# Rootcause::GetFirstInstance(_LIST_ENTRY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)

- ea: `0x180019ed8`
- end: `0x180019f3a`
- name: `?GetFirstInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z`
- size: `98`
- prototype: `__int64 __fastcall(Rootcause *__hidden this, struct _LIST_ENTRY *, struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE **)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180019f40`
- `0x18001b0b4`
- `0x18001b2d0`
- `0x18001b4d4`
- `0x18001b9c8`
- `0x18001bb50`

## callees

- `0x180019ed8`
- `0x180026fa0`

## pseudocode

```c
__int64 __fastcall Rootcause::GetFirstInstance(
        Rootcause *this,
        struct _LIST_ENTRY *a2,
        struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE **a3)
{
  unsigned int v3; // ebx
  int v4; // r8d
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *Flink; // rax

  if ( !a3 )
  {
    v3 = -2147024809;
    v4 = 2250;
LABEL_3:
    SdpDebugTrace(1u, L"Rootcause::GetFirstInstance", v4, v3);
    return v3;
  }
  v3 = 0;
  if ( a2 )
  {
    Flink = (struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *)a2->Flink;
    *a3 = 0;
    *((_QWORD *)this + 17) = Flink;
    if ( Flink != (struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *)a2 )
    {
      if ( Flink )
      {
        *a3 = Flink;
        return v3;
      }
      v3 = -2147467261;
      v4 = 2265;
      goto LABEL_3;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180019ed8  push    rbx
0x180019eda  sub     rsp, 20h
0x180019ede  test    r8, r8
0x180019ee1  jnz     short loc_180019F04
0x180019ee3  mov     ebx, 80070057h
0x180019ee8  mov     r8d, 8CAh; int
0x180019eee  mov     r9d, ebx; int
0x180019ef1  lea     rdx, aRootcauseGetfi; "Rootcause::GetFirstInstance"
0x180019ef8  mov     ecx, 1; Level
0x180019efd  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180019f02  jmp     short loc_180019F32
0x180019f04  xor     ebx, ebx
0x180019f06  test    rdx, rdx
0x180019f09  jz      short loc_180019F32
0x180019f0b  mov     rax, [rdx]
0x180019f0e  mov     [r8], rbx
0x180019f11  mov     [rcx+88h], rax
0x180019f18  cmp     rax, rdx
0x180019f1b  jz      short loc_180019F32
0x180019f1d  test    rax, rax
0x180019f20  jnz     short loc_180019F2F
0x180019f22  mov     ebx, 80004003h
0x180019f27  mov     r8d, 8D9h
0x180019f2d  jmp     short loc_180019EEE
0x180019f2f  mov     [r8], rax
0x180019f32  mov     eax, ebx
0x180019f34  add     rsp, 20h
0x180019f38  pop     rbx
0x180019f39  retn
```
