# AutoUpdateGetHandler

- ea: `0x14002dbb0`
- end: `0x14002dcd3`
- name: `AutoUpdateGetHandler`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x14002dbb0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002dbf5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002dbf5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002dc2c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002dc2c`
- `ks!KsGetFilterFromIrp` at `0x14002dbbe`
- `ks!KsGetFilterFromIrp` at `0x14002dbbe`

## pseudocode

```c
__int64 __fastcall AutoUpdateGetHandler(IRP *a1, __int64 a2, __int64 a3)
{
  PKSFILTER FilterFromIrp; // rax
  __int64 v6; // rdi
  KIRQL v7; // al
  char v8; // r14
  __int64 v9; // rbp
  unsigned int v10; // ecx
  __int64 v11; // rdx
  int v12; // eax
  int v13; // eax
  _BYTE v14[9]; // [rsp+25h] [rbp-33h]

  FilterFromIrp = KsGetFilterFromIrp(a1);
  if ( !FilterFromIrp )
    return 3221225473LL;
  v6 = *(_QWORD *)FilterFromIrp->Context;
  *(_OWORD *)a3 = 0;
  *(_DWORD *)(a3 + 16) = 0;
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 392));
  v8 = *(_BYTE *)(v6 + 402);
  v9 = *(unsigned __int8 *)(v6 + 404);
  v14[8] = *(_BYTE *)(v6 + 413);
  *(_QWORD *)v14 = *(_QWORD *)(v6 + 405);
  KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 392), v7);
  v10 = 0;
  *(_DWORD *)a3 = *(unsigned __int8 *)(v6 + 400);
  v11 = *(_QWORD *)(v6 + 120);
  while ( v10 < *(_DWORD *)(v6 + 112) )
  {
    if ( *(_BYTE *)(*(_QWORD *)(v11 + 32) + 3LL) == v8 )
    {
      *(_DWORD *)(a3 + 4) = v10;
      *(_DWORD *)(a3 + 8) = 0xFFFF;
      v12 = *(_DWORD *)(v11 + 44);
      switch ( v12 )
      {
        case 6:
          if ( (unsigned __int8)v9 < 0x12u )
          {
            v13 = ulaCameraProperties[v9];
            goto LABEL_13;
          }
          break;
        case 5:
          if ( (unsigned __int8)v9 < 0x11u )
          {
            v13 = ulaProcAmpProperties[v9];
LABEL_13:
            *(_DWORD *)(a3 + 8) = v13;
          }
          break;
        case 9:
          *(_DWORD *)(a3 + 8) = v9;
          break;
      }
      *(_QWORD *)(a3 + 12) = *(_QWORD *)&v14[1];
      return 0;
    }
    v11 += 480;
    ++v10;
  }
  *(_DWORD *)(a3 + 4) = 0xFFFF;
  return 0;
}

```

## disassembly

```asm
0x14002dbb0  push    rbx
0x14002dbb2  push    rbp
0x14002dbb3  push    rsi
0x14002dbb4  push    rdi
0x14002dbb5  push    r14
0x14002dbb7  sub     rsp, 30h
0x14002dbbb  mov     rsi, r8
0x14002dbbe  call    cs:__imp_KsGetFilterFromIrp
0x14002dbc5  nop     dword ptr [rax+rax+00h]
0x14002dbca  test    rax, rax
0x14002dbcd  jnz     short loc_14002DBD9
0x14002dbcf  mov     eax, 0C0000001h
0x14002dbd4  jmp     loc_14002DCC7
0x14002dbd9  mov     rax, [rax+10h]
0x14002dbdd  xorps   xmm0, xmm0
0x14002dbe0  mov     rdi, [rax]
0x14002dbe3  xor     eax, eax
0x14002dbe5  movups  xmmword ptr [rsi], xmm0
0x14002dbe8  mov     [rsi+10h], eax
0x14002dbeb  lea     rbx, [rdi+188h]
0x14002dbf2  mov     rcx, rbx; SpinLock
0x14002dbf5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002dbfc  nop     dword ptr [rax+rax+00h]
0x14002dc01  mov     dl, [rdi+19Dh]
0x14002dc07  mov     rcx, rbx; SpinLock
0x14002dc0a  movsd   xmm0, qword ptr [rdi+195h]
0x14002dc12  mov     r14b, [rdi+192h]
0x14002dc19  movzx   ebp, byte ptr [rdi+194h]
0x14002dc20  mov     [rsp+58h+var_2B], dl
0x14002dc24  mov     dl, al; NewIrql
0x14002dc26  movsd   [rsp+58h+var_33], xmm0
0x14002dc2c  call    cs:__imp_KeReleaseSpinLock
0x14002dc33  nop     dword ptr [rax+rax+00h]
0x14002dc38  movzx   eax, byte ptr [rdi+190h]
0x14002dc3f  xor     ecx, ecx
0x14002dc41  mov     [rsi], eax
0x14002dc43  mov     rdx, [rdi+78h]
0x14002dc47  mov     r8d, [rdi+70h]
0x14002dc4b  cmp     ecx, r8d
0x14002dc4e  jnb     short loc_14002DCBE
0x14002dc50  mov     rax, [rdx+20h]
0x14002dc54  cmp     [rax+3], r14b
0x14002dc58  jz      short loc_14002DC65
0x14002dc5a  add     rdx, 1E0h
0x14002dc61  inc     ecx
0x14002dc63  jmp     short loc_14002DC4B
0x14002dc65  mov     [rsi+4], ecx
0x14002dc68  mov     dword ptr [rsi+8], 0FFFFh
0x14002dc6f  mov     eax, [rdx+2Ch]
0x14002dc72  cmp     eax, 6
0x14002dc75  jnz     short loc_14002DC8D
0x14002dc77  cmp     bpl, 12h
0x14002dc7b  jnb     short loc_14002DCB3
0x14002dc7d  lea     rcx, cs:140000000h
0x14002dc84  mov     eax, ds:rva ulaCameraProperties[rcx+rbp*4]
0x14002dc8b  jmp     short loc_14002DCA6
0x14002dc8d  cmp     eax, 5
0x14002dc90  jnz     short loc_14002DCAB
0x14002dc92  cmp     bpl, 11h
0x14002dc96  jnb     short loc_14002DCB3
0x14002dc98  lea     rcx, cs:140000000h
0x14002dc9f  mov     eax, ds:rva ulaProcAmpProperties[rcx+rbp*4]
0x14002dca6  mov     [rsi+8], eax
0x14002dca9  jmp     short loc_14002DCB3
0x14002dcab  cmp     eax, 9
0x14002dcae  jnz     short loc_14002DCB3
0x14002dcb0  mov     [rsi+8], ebp
0x14002dcb3  mov     rax, [rsp+58h+var_33+1]
0x14002dcb8  mov     [rsi+0Ch], rax
0x14002dcbc  jmp     short loc_14002DCC5
0x14002dcbe  mov     dword ptr [rsi+4], 0FFFFh
0x14002dcc5  xor     eax, eax
0x14002dcc7  add     rsp, 30h
0x14002dccb  pop     r14
0x14002dccd  pop     rdi
0x14002dcce  pop     rsi
0x14002dccf  pop     rbp
0x14002dcd0  pop     rbx
0x14002dcd1  retn
```
