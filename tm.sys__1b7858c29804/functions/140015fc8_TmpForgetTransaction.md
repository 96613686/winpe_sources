# TmpForgetTransaction

- ea: `0x140015fc8`
- end: `0x140016109`
- name: `TmpForgetTransaction`
- size: `321`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140016110`
- `0x14001ca60`
- `0x140020dd4`

## callees

- `0x14001102c`
- `0x140015fc8`
- `0x14001f3e8`

## import_xrefs

- `CLFS!ClfsReserveAndAppendLog` at `0x14001605a`
- `CLFS!ClfsReserveAndAppendLog` at `0x1400160e2`
- `CLFS!ClfsReserveAndAppendLog` at `0x14001605a`
- `CLFS!ClfsReserveAndAppendLog` at `0x1400160e2`

## pseudocode

```c
__int64 __fastcall TmpForgetTransaction(__int64 Object, char a2, char a3)
{
  __int64 v3; // r14
  NTSTATUS appended; // edi
  NTSTATUS v8; // eax
  __int64 rgcbReservation[7]; // [rsp+50h] [rbp-38h] BYREF

  v3 = *(_QWORD *)(Object + 512);
  appended = 0;
  if ( !a3 )
    goto LABEL_5;
  v8 = TmpLogTransaction(Object, 4, 0);
  if ( !a2 )
    appended = v8;
  if ( appended >= 0 )
  {
LABEL_5:
    if ( (*(_DWORD *)(Object + 196) & 0x1000000) != 0 )
    {
      rgcbReservation[0] = -*(_QWORD *)(Object + 520);
      appended = ClfsReserveAndAppendLog(*(PVOID *)(v3 + 160), 0, 0, 0, 0, 1u, rgcbReservation, 0, 0);
      *(_QWORD *)(Object + 520) = 0;
      _InterlockedAnd((volatile signed __int32 *)(Object + 196), 0xFEFFFFFF);
    }
    _InterlockedOr((volatile signed __int32 *)(Object + 196), 0x400000u);
    TmpFinalizeTransactionForcefully((PVOID)Object);
    if ( !a3 && (*(_DWORD *)(Object + 196) & 0x2000000) != 0 )
    {
      rgcbReservation[0] = -72;
      appended = ClfsReserveAndAppendLog(*(PVOID *)(v3 + 160), 0, 0, 0, 0, 1u, rgcbReservation, 0, 0);
      _InterlockedAnd((volatile signed __int32 *)(Object + 196), 0xFDFFFFFF);
    }
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140015fc8  push    rbx
0x140015fca  push    rbp
0x140015fcb  push    rsi
0x140015fcc  push    rdi
0x140015fcd  push    r14
0x140015fcf  sub     rsp, 60h
0x140015fd3  mov     r14, [rcx+200h]
0x140015fda  xor     edi, edi
0x140015fdc  mov     sil, r8b
0x140015fdf  mov     bpl, dl
0x140015fe2  mov     rbx, rcx
0x140015fe5  test    r8b, r8b
0x140015fe8  jz      short loc_140016003
0x140015fea  xor     r8d, r8d
0x140015fed  lea     edx, [rdi+4]
0x140015ff0  call    TmpLogTransaction
0x140015ff5  test    bpl, bpl
0x140015ff8  cmovz   edi, eax
0x140015ffb  test    edi, edi
0x140015ffd  js      loc_1400160FB
0x140016003  mov     eax, [rbx+0C4h]
0x140016009  mov     ebp, 1
0x14001600e  bt      eax, 18h
0x140016012  jnb     short loc_14001607E
0x140016014  mov     rax, [rbx+208h]
0x14001601b  xor     r9d, r9d; plsnUndoNext
0x14001601e  mov     [rsp+88h+plsn], 0; plsn
0x140016027  neg     rax
0x14001602a  mov     [rsp+88h+var_38], rax
0x14001602f  xor     r8d, r8d; cWriteEntries
0x140016032  mov     rcx, [r14+0A0h]; pvMarshalContext
0x140016039  lea     rax, [rsp+88h+var_38]
0x14001603e  mov     [rsp+88h+fFlags], 0; fFlags
0x140016046  xor     edx, edx; rgWriteEntries
0x140016048  mov     [rsp+88h+rgcbReservation], rax; rgcbReservation
0x14001604d  mov     [rsp+88h+cReserveRecords], ebp; cReserveRecords
0x140016051  mov     [rsp+88h+plsnPrevious], 0; plsnPrevious
0x14001605a  call    cs:__imp_ClfsReserveAndAppendLog
0x140016061  nop     dword ptr [rax+rax+00h]
0x140016066  mov     edi, eax
0x140016068  mov     qword ptr [rbx+208h], 0
0x140016073  lock and dword ptr [rbx+0C4h], 0FEFFFFFFh
0x14001607e  lock or dword ptr [rbx+0C4h], 400000h
0x140016089  mov     rcx, rbx; Object
0x14001608c  call    TmpFinalizeTransactionForcefully
0x140016091  test    sil, sil
0x140016094  jnz     short loc_1400160FB
0x140016096  mov     eax, [rbx+0C4h]
0x14001609c  bt      eax, 19h
0x1400160a0  jnb     short loc_1400160FB
0x1400160a2  mov     [rsp+88h+plsn], 0; plsn
0x1400160ab  lea     rax, [rsp+88h+var_38]
0x1400160b0  mov     [rsp+88h+fFlags], 0; fFlags
0x1400160b8  xor     r9d, r9d; plsnUndoNext
0x1400160bb  mov     [rsp+88h+rgcbReservation], rax; rgcbReservation
0x1400160c0  xor     r8d, r8d; cWriteEntries
0x1400160c3  mov     [rsp+88h+var_38], 0FFFFFFFFFFFFFFB8h
0x1400160cc  xor     edx, edx; rgWriteEntries
0x1400160ce  mov     rcx, [r14+0A0h]; pvMarshalContext
0x1400160d5  mov     [rsp+88h+cReserveRecords], ebp; cReserveRecords
0x1400160d9  mov     [rsp+88h+plsnPrevious], 0; plsnPrevious
0x1400160e2  call    cs:__imp_ClfsReserveAndAppendLog
0x1400160e9  nop     dword ptr [rax+rax+00h]
0x1400160ee  mov     edi, eax
0x1400160f0  lock and dword ptr [rbx+0C4h], 0FDFFFFFFh
0x1400160fb  mov     eax, edi
0x1400160fd  add     rsp, 60h
0x140016101  pop     r14
0x140016103  pop     rdi
0x140016104  pop     rsi
0x140016105  pop     rbp
0x140016106  pop     rbx
0x140016107  retn
```
