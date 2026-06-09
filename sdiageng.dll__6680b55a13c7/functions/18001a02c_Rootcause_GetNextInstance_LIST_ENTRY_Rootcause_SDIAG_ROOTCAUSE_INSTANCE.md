# Rootcause::GetNextInstance(_LIST_ENTRY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)

- ea: `0x18001a02c`
- end: `0x18001a0b4`
- name: `?GetNextInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z`
- size: `136`
- prototype: `__int64 __fastcall(Rootcause *this, struct _LIST_ENTRY *, struct _LIST_ENTRY **)`
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

- `0x18001a02c`
- `0x180026fa0`

## pseudocode

```c
__int64 __fastcall Rootcause::GetNextInstance(Rootcause *this, struct _LIST_ENTRY *a2, struct _LIST_ENTRY **a3)
{
  unsigned int v3; // ebx
  int v4; // r8d
  int v5; // r9d
  struct _LIST_ENTRY *v6; // rax
  struct _LIST_ENTRY *Flink; // rax

  if ( !a3 )
  {
    v3 = -2147024809;
    v4 = 2290;
    v5 = -2147024809;
LABEL_3:
    SdpDebugTrace(1u, L"Rootcause::GetNextInstance", v4, v5);
    return v3;
  }
  v3 = 0;
  if ( a2 )
  {
    v6 = (struct _LIST_ENTRY *)*((_QWORD *)this + 17);
    *a3 = 0;
    if ( v6 != a2 )
    {
      if ( v6 )
      {
        Flink = v6->Flink;
        *((_QWORD *)this + 17) = Flink;
        if ( Flink == a2 )
          return v3;
        if ( Flink )
        {
          *a3 = Flink;
          return v3;
        }
        v5 = -2147467261;
        v4 = 2310;
        v3 = -2147467261;
      }
      else
      {
        v5 = -2147467261;
        v4 = 2300;
        v3 = -2147467261;
      }
      goto LABEL_3;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18001a02c  push    rbx
0x18001a02e  sub     rsp, 20h
0x18001a032  test    r8, r8
0x18001a035  jnz     short loc_18001A058
0x18001a037  mov     ebx, 80070057h
0x18001a03c  mov     r8d, 8F2h; int
0x18001a042  mov     r9d, ebx; int
0x18001a045  lea     rdx, aRootcauseGetne; "Rootcause::GetNextInstance"
0x18001a04c  mov     ecx, 1; Level
0x18001a051  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001a056  jmp     short loc_18001A0AC
0x18001a058  xor     ebx, ebx
0x18001a05a  test    rdx, rdx
0x18001a05d  jz      short loc_18001A0AC
0x18001a05f  mov     rax, [rcx+88h]
0x18001a066  mov     [r8], rbx
0x18001a069  cmp     rax, rdx
0x18001a06c  jz      short loc_18001A0AC
0x18001a06e  test    rax, rax
0x18001a071  jnz     short loc_18001A084
0x18001a073  mov     r9d, 80004003h
0x18001a079  mov     r8d, 8FCh
0x18001a07f  mov     ebx, r9d
0x18001a082  jmp     short loc_18001A045
0x18001a084  mov     rax, [rax]
0x18001a087  mov     [rcx+88h], rax
0x18001a08e  cmp     rax, rdx
0x18001a091  jz      short loc_18001A0AC
0x18001a093  test    rax, rax
0x18001a096  jnz     short loc_18001A0A9
0x18001a098  mov     r9d, 80004003h
0x18001a09e  mov     r8d, 906h
0x18001a0a4  mov     ebx, r9d
0x18001a0a7  jmp     short loc_18001A045
0x18001a0a9  mov     [r8], rax
0x18001a0ac  mov     eax, ebx
0x18001a0ae  add     rsp, 20h
0x18001a0b2  pop     rbx
0x18001a0b3  retn
```
