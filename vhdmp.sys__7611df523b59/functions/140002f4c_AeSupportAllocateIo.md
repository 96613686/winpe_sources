# AeSupportAllocateIo

- ea: `0x140002f4c`
- end: `0x14000308d`
- name: `AeSupportAllocateIo`
- size: `321`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `22`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140003288`
- `0x1400213e0`
- `0x14002780c`
- `0x1400281dc`
- `0x140028384`
- `0x140028600`
- `0x140028848`
- `0x140028b44`
- `0x140028cb0`
- `0x1400569f4`
- `0x140057dc8`
- `0x140059030`
- `0x14005a2f4`
- `0x14005a4ac`
- `0x1400d631c`
- `0x1400d8f70`
- `0x1400d9604`
- `0x1400d9900`
- `0x1400daa0c`
- `0x1400db280`
- `0x1400dd550`
- `0x1400eb1c4`

## callees

- `0x140002870`
- `0x140002f4c`
- `0x14005dd00`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x140003024`
- `ntoskrnl!IoAllocateMdl` at `0x140003024`
- `ntoskrnl!IoInitializeIrpEx` at `0x140002fdd`
- `ntoskrnl!IoInitializeIrpEx` at `0x140002fdd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002f74`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002f74`

## pseudocode

```c
__int64 __fastcall AeSupportAllocateIo(_QWORD *a1, __int64 a2, unsigned __int64 a3, int a4)
{
  _QWORD *v8; // rax
  _QWORD *v9; // r14
  _QWORD *v10; // rbp
  unsigned __int16 v11; // si
  __int64 v12; // rbx
  __int64 v13; // rdi
  __int64 v14; // r9
  PMDL Mdl; // rax

  *a1 = 0;
  v8 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a2 + 64));
  v9 = v8;
  if ( v8 )
  {
    v8[21] = a2;
    v8[23] = 0;
    v10 = v8 + 28;
    v11 = *(_WORD *)(a2 + 24);
    v12 = *(_QWORD *)(a2 + 16);
    v13 = *(_QWORD *)(a2 + 8);
    memset(v8 + 3, 0, 0x58u);
    *v9 = v13;
    v9[1] = v12;
    v9[2] = v10;
    LOBYTE(v14) = *(_BYTE *)(v13 + 544);
    IoInitializeIrpEx(v10, -1, v11, v14);
    v10[18] = v9;
    *((_WORD *)v9 + 108) = 255;
    *((_DWORD *)v9 + 53) = a4;
    if ( !a3 )
    {
      v9[23] = 0;
      goto LABEL_6;
    }
    if ( a3 > 0xFFFFF )
    {
      v9[23] = 0;
    }
    else
    {
      Mdl = IoAllocateMdl(0, (_DWORD)a3 << 12, 0, 0, 0);
      v9[23] = Mdl;
      if ( Mdl )
      {
        Mdl->Process = 0;
        *(_DWORD *)(v9[23] + 40LL) = 0;
LABEL_6:
        *((_DWORD *)v9 + 52) = a3;
        *a1 = v9 + 14;
        return 0;
      }
    }
    AeSupportFreeIo(v9 + 14);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140002f4c  push    rbx
0x140002f4e  push    rbp
0x140002f4f  push    rsi
0x140002f50  push    rdi
0x140002f51  push    r12
0x140002f53  push    r13
0x140002f55  push    r14
0x140002f57  push    r15
0x140002f59  sub     rsp, 38h
0x140002f5d  mov     r12, rcx
0x140002f60  mov     qword ptr [rcx], 0
0x140002f67  lea     rcx, [rdx+40h]; Lookaside
0x140002f6b  mov     r13d, r9d
0x140002f6e  mov     r15, r8
0x140002f71  mov     rdi, rdx
0x140002f74  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140002f7b  nop     dword ptr [rax+rax+00h]
0x140002f80  mov     r14, rax
0x140002f83  test    rax, rax
0x140002f86  jz      loc_14000307D
0x140002f8c  mov     [rax+0A8h], rdi
0x140002f93  lea     rcx, [rax+18h]; void *
0x140002f97  mov     qword ptr [rax+0B8h], 0
0x140002fa2  lea     rbp, [rax+0E0h]
0x140002fa9  movzx   esi, word ptr [rdi+18h]
0x140002fad  xor     edx, edx; Val
0x140002faf  mov     rbx, [rdi+10h]
0x140002fb3  mov     rdi, [rdi+8]
0x140002fb7  lea     r8d, [rdx+58h]; Size
0x140002fbb  call    memset
0x140002fc0  mov     [r14], rdi
0x140002fc3  movzx   r8d, si
0x140002fc7  mov     [r14+8], rbx
0x140002fcb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140002fcf  mov     [r14+10h], rbp
0x140002fd3  mov     rcx, rbp
0x140002fd6  mov     r9b, [rdi+220h]
0x140002fdd  call    cs:__imp_IoInitializeIrpEx
0x140002fe4  nop     dword ptr [rax+rax+00h]
0x140002fe9  mov     [rbp+90h], r14
0x140002ff0  xor     ebx, ebx
0x140002ff2  mov     word ptr [r14+0D8h], 0FFh
0x140002ffc  mov     [r14+0D4h], r13d
0x140003003  test    r15, r15
0x140003006  jz      short loc_140003084
0x140003008  cmp     r15, 0FFFFFh
0x14000300f  ja      short loc_14000306D
0x140003011  mov     edx, r15d
0x140003014  mov     [rsp+78h+Irp], rbx; Irp
0x140003019  shl     edx, 0Ch; Length
0x14000301c  xor     r9d, r9d; ChargeQuota
0x14000301f  xor     r8d, r8d; SecondaryBuffer
0x140003022  xor     ecx, ecx; VirtualAddress
0x140003024  call    cs:__imp_IoAllocateMdl
0x14000302b  nop     dword ptr [rax+rax+00h]
0x140003030  mov     [r14+0B8h], rax
0x140003037  test    rax, rax
0x14000303a  jz      short loc_140003074
0x14000303c  mov     [rax+10h], rbx
0x140003040  mov     rax, [r14+0B8h]
0x140003047  mov     [rax+28h], ebx
0x14000304a  lea     rax, [r14+70h]
0x14000304e  mov     [r14+0D0h], r15d
0x140003055  mov     [r12], rax
0x140003059  xor     eax, eax
0x14000305b  add     rsp, 38h
0x14000305f  pop     r15
0x140003061  pop     r14
0x140003063  pop     r13
0x140003065  pop     r12
0x140003067  pop     rdi
0x140003068  pop     rsi
0x140003069  pop     rbp
0x14000306a  pop     rbx
0x14000306b  retn
0x14000306d  mov     [r14+0B8h], rbx
0x140003074  lea     rcx, [r14+70h]
0x140003078  call    AeSupportFreeIo
0x14000307d  mov     eax, 0C000009Ah
0x140003082  jmp     short loc_14000305B
0x140003084  mov     [r14+0B8h], rbx
0x14000308b  jmp     short loc_14000304A
```
