# UdfSendSptCdb

- ea: `0x14004c1b4`
- end: `0x14004c53a`
- name: `UdfSendSptCdb`
- size: `902`
- prototype: ``
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x14002c7a0`
- `0x14002fdbc`
- `0x14002fe08`
- `0x140031b04`
- `0x14003cf04`
- `0x14003cf8c`
- `0x14003d0c4`
- `0x14003d194`
- `0x14004bdc0`

## callees

- `0x14000ca10`
- `0x14000cad4`
- `0x14001bd80`
- `0x14001c080`
- `0x14004c1b4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004c51a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c51a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004c26d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004c26d`
- `ntoskrnl!KeDelayExecutionThread` at `0x14004c421`
- `ntoskrnl!KeDelayExecutionThread` at `0x14004c421`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14004c35f`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14004c35f`
- `ntoskrnl!IoSynchronousCallDriver` at `0x14004c3a5`
- `ntoskrnl!IoSynchronousCallDriver` at `0x14004c3a5`
- `ntoskrnl!IoFreeIrp` at `0x14004c3b6`
- `ntoskrnl!IoFreeIrp` at `0x14004c3b6`

## pseudocode

```c
__int64 __fastcall UdfSendSptCdb(
        struct _DEVICE_OBJECT *a1,
        unsigned __int8 *a2,
        void *a3,
        unsigned int a4,
        char a5,
        unsigned int a6,
        union _LARGE_INTEGER Interval,
        __int64 a8,
        size_t a9,
        __int64 a10)
{
  unsigned int v10; // eax
  int v11; // r12d
  size_t v12; // rsi
  unsigned __int8 v13; // bp
  unsigned int v14; // r14d
  size_t v15; // rdi
  unsigned int *PoolWithTag; // rax
  unsigned int *v17; // rbx
  char v18; // r15
  char v19; // al
  struct _IRP *v20; // rdi
  PIRP v21; // rax
  IRP *v22; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  int v24; // edi
  char v25; // al
  char v26; // dl
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // eax
  char v34; // [rsp+98h] [rbp+20h]

  v10 = *a2;
  v11 = 200;
  v12 = a4;
  v34 = 0;
  Interval.QuadPart = -1000000;
  if ( !(_BYTE)v10 )
  {
    v11 = 2700;
    Interval.LowPart = -10000000;
  }
  if ( v10 >> 5 )
  {
    if ( v10 >> 5 == 1 || v10 >> 5 == 2 )
    {
      v13 = 10;
    }
    else if ( v10 >> 5 == 5 )
    {
      v13 = 12;
    }
    else
    {
      v13 = 0;
    }
  }
  else
  {
    v13 = 6;
  }
  if ( a4 && a5 )
    memset(a3, 0, a4);
  v14 = v12 + 76;
  v15 = (unsigned int)(v12 + 76);
  a9 = v15;
  if ( (_DWORD)v12 == -76 )
  {
    v18 = 0;
    v17 = 0;
  }
  else
  {
    PoolWithTag = (unsigned int *)ExAllocatePoolWithTag((POOL_TYPE)1552, v14, 0x62666455u);
    v17 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, v14);
    v18 = 1;
  }
  a10 = (_DWORD)v12 != 0 ? 0x4C : 0;
  while ( 1 )
  {
    memset(v17, 0, v15);
    memmove(v17 + 9, a2, v13);
    *((_BYTE *)v17 + 6) = v13;
    *(_WORD *)v17 = 56;
    *((_BYTE *)v17 + 7) = 18;
    if ( (_DWORD)v12 )
      v19 = a5 != 0;
    else
      v19 = 2;
    *((_BYTE *)v17 + 8) = v19;
    v17[4] = a6;
    *((_QWORD *)v17 + 3) = a10;
    v17[3] = v12;
    v17[8] = 56;
    if ( (_DWORD)v12 && !a5 )
      memmove(v17 + 19, a3, v12);
    v20 = 0;
    if ( v14 )
      v20 = (struct _IRP *)v17;
    v21 = IoBuildAsynchronousFsdRequest(9u, a1, 0, 0, 0, 0);
    v22 = v21;
    if ( !v21 )
    {
      v24 = -1073741670;
LABEL_58:
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          11,
          WPP_9fc1880bfcae3bc333ea8e1a40f594fb_Traceguids);
      }
      goto LABEL_61;
    }
    CurrentStackLocation = v21->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].Flags |= 2u;
    v21->AssociatedIrp.MasterIrp = v20;
    CurrentStackLocation[-1].Parameters.Read.Length = v12 + 76;
    CurrentStackLocation[-1].Parameters.Create.Options = v12 + 76;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 315396;
    CurrentStackLocation[-1].MajorFunction = 14;
    v24 = IoSynchronousCallDriver(a1, v21);
    IoFreeIrp(v22);
    if ( v24 >= 0 )
      break;
    if ( v24 != -1073741435 && v24 != -1073741823 || !v11 )
      goto LABEL_58;
    --v11;
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40) != 0 )
    {
      WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 10, WPP_9fc1880bfcae3bc333ea8e1a40f594fb_Traceguids);
    }
LABEL_37:
    KeDelayExecutionThread(0, 0, &Interval);
    v15 = a9;
    v14 = v12 + 76;
  }
  v25 = *((_BYTE *)v17 + 58);
  if ( (v25 & 0xF) != 0 )
  {
    v26 = 1;
    v24 = -1073741435;
    v34 = 1;
  }
  else
  {
    if ( !*((_BYTE *)v17 + 2) )
    {
      v24 = 0;
      goto LABEL_51;
    }
    v26 = v34;
    v24 = -1073741811;
  }
  if ( (v25 & 0xF) == 2 )
  {
    v27 = *((unsigned __int16 *)v17 + 34);
    if ( (_BYTE)v27 == 4 )
    {
      v28 = v27 >> 8;
      if ( v28 == 4 || v28 - 7 <= 1 )
      {
        if ( !v11 )
          goto LABEL_61;
        --v11;
        goto LABEL_37;
      }
    }
  }
  if ( !v26 )
    goto LABEL_61;
LABEL_51:
  if ( a5 )
  {
    v29 = v17[3];
    if ( (unsigned int)v12 >= v29 )
    {
      if ( (unsigned int)v12 > v29 )
        LODWORD(v12) = v17[3];
      memmove(a3, v17 + 19, (unsigned int)v12);
    }
    else
    {
      v24 = -2147483643;
    }
  }
LABEL_61:
  if ( v18 )
    ExFreePoolWithTag(v17, 0);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x14004c1b4  mov     r11, rsp
0x14004c1b7  mov     [r11+18h], r8
0x14004c1bb  mov     [r11+10h], rdx
0x14004c1bf  mov     [r11+8], rcx
0x14004c1c3  push    rbx
0x14004c1c4  push    rbp
0x14004c1c5  push    rsi
0x14004c1c6  push    rdi
0x14004c1c7  push    r12
0x14004c1c9  push    r13
0x14004c1cb  push    r14
0x14004c1cd  push    r15
0x14004c1cf  sub     rsp, 38h
0x14004c1d3  movzx   eax, byte ptr [rdx]
0x14004c1d6  mov     r12d, 0C8h
0x14004c1dc  mov     esi, r9d
0x14004c1df  mov     r9, r8
0x14004c1e2  mov     [rsp+78h+arg_18], 0
0x14004c1ea  mov     qword ptr [r11+38h], 0FFFFFFFFFFF0BDC0h
0x14004c1f2  test    al, al
0x14004c1f4  jnz     short loc_14004C204
0x14004c1f6  mov     r12d, 0A8Ch
0x14004c1fc  mov     dword ptr [r11+38h], 0FF676980h
0x14004c204  mov     ecx, eax
0x14004c206  shr     ecx, 5
0x14004c209  test    ecx, ecx
0x14004c20b  jz      short loc_14004C22B
0x14004c20d  sub     ecx, 1
0x14004c210  jz      short loc_14004C226
0x14004c212  sub     ecx, 1
0x14004c215  jz      short loc_14004C226
0x14004c217  cmp     ecx, 3
0x14004c21a  jz      short loc_14004C221
0x14004c21c  xor     bpl, bpl
0x14004c21f  jmp     short loc_14004C22E
0x14004c221  mov     bpl, 0Ch
0x14004c224  jmp     short loc_14004C22E
0x14004c226  mov     bpl, 0Ah
0x14004c229  jmp     short loc_14004C22E
0x14004c22b  mov     bpl, 6
0x14004c22e  mov     r13b, [rsp+78h+arg_20]
0x14004c236  test    esi, esi
0x14004c238  jz      short loc_14004C24C
0x14004c23a  test    r13b, r13b
0x14004c23d  jz      short loc_14004C24C
0x14004c23f  mov     r8, rsi; Size
0x14004c242  xor     edx, edx; Val
0x14004c244  mov     rcx, r9; void *
0x14004c247  call    memset
0x14004c24c  lea     r14d, [rsi+4Ch]
0x14004c250  mov     edi, r14d
0x14004c253  mov     [rsp+78h+arg_40], rdi
0x14004c25b  test    r14d, r14d
0x14004c25e  jz      short loc_14004C29C
0x14004c260  mov     r8d, 62666455h; Tag
0x14004c266  mov     edx, edi; NumberOfBytes
0x14004c268  mov     ecx, 610h; PoolType
0x14004c26d  call    cs:__imp_ExAllocatePoolWithTag
0x14004c274  nop     dword ptr [rax+rax+00h]
0x14004c279  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14004c280  mov     rbx, rax
0x14004c283  jnz     short loc_14004C297
0x14004c285  test    rax, rax
0x14004c288  jz      short loc_14004C297
0x14004c28a  mov     r8d, edi; Size
0x14004c28d  xor     edx, edx; Val
0x14004c28f  mov     rcx, rax; void *
0x14004c292  call    memset
0x14004c297  mov     r15b, 1
0x14004c29a  jmp     short loc_14004C2A1
0x14004c29c  xor     r15b, r15b
0x14004c29f  xor     ebx, ebx
0x14004c2a1  mov     eax, esi
0x14004c2a3  neg     eax
0x14004c2a5  sbb     rax, rax
0x14004c2a8  and     eax, 4Ch
0x14004c2ab  mov     [rsp+78h+arg_48], rax
0x14004c2b3  mov     r8, rdi; Size
0x14004c2b6  xor     edx, edx; Val
0x14004c2b8  mov     rcx, rbx; void *
0x14004c2bb  call    memset
0x14004c2c0  mov     rdx, [rsp+78h+Src]; Src
0x14004c2c8  lea     rcx, [rbx+24h]; void *
0x14004c2cc  movzx   r8d, bpl; Size
0x14004c2d0  call    memmove
0x14004c2d5  mov     [rbx+6], bpl
0x14004c2d9  mov     ecx, 38h ; '8'
0x14004c2de  mov     [rbx], cx
0x14004c2e1  mov     byte ptr [rbx+7], 12h
0x14004c2e5  test    esi, esi
0x14004c2e7  jz      short loc_14004C2F1
0x14004c2e9  test    r13b, r13b
0x14004c2ec  setnz   al
0x14004c2ef  jmp     short loc_14004C2F6
0x14004c2f1  mov     eax, 2
0x14004c2f6  mov     [rbx+8], al
0x14004c2f9  mov     eax, [rsp+78h+arg_28]
0x14004c300  mov     [rbx+10h], eax
0x14004c303  mov     rax, [rsp+78h+arg_48]
0x14004c30b  mov     [rbx+18h], rax
0x14004c30f  mov     [rbx+0Ch], esi
0x14004c312  mov     [rbx+20h], ecx
0x14004c315  test    esi, esi
0x14004c317  jz      short loc_14004C332
0x14004c319  test    r13b, r13b
0x14004c31c  jnz     short loc_14004C332
0x14004c31e  mov     rdx, [rsp+78h+arg_10]; Src
0x14004c326  lea     rcx, [rbx+4Ch]; void *
0x14004c32a  mov     r8, rsi; Size
0x14004c32d  call    memmove
0x14004c332  mov     rdx, [rsp+78h+DeviceObject]; DeviceObject
0x14004c33a  xor     edi, edi
0x14004c33c  test    r14d, r14d
0x14004c33f  mov     [rsp+78h+IoStatusBlock], 0; IoStatusBlock
0x14004c348  mov     [rsp+78h+StartingOffset], 0; StartingOffset
0x14004c351  cmovnz  rdi, rbx
0x14004c355  xor     r9d, r9d; Length
0x14004c358  xor     r8d, r8d; Buffer
0x14004c35b  lea     ecx, [r9+9]; MajorFunction
0x14004c35f  call    cs:__imp_IoBuildAsynchronousFsdRequest
0x14004c366  nop     dword ptr [rax+rax+00h]
0x14004c36b  mov     r14, rax
0x14004c36e  test    rax, rax
0x14004c371  jz      loc_14004C4D9
0x14004c377  mov     rcx, [rax+0B8h]
0x14004c37e  mov     rdx, r14
0x14004c381  or      byte ptr [rcx-46h], 2
0x14004c385  mov     [rax+18h], rdi
0x14004c389  lea     eax, [rsi+4Ch]
0x14004c38c  mov     [rcx-40h], eax
0x14004c38f  mov     [rcx-38h], eax
0x14004c392  mov     dword ptr [rcx-30h], 4D004h
0x14004c399  mov     byte ptr [rcx-48h], 0Eh
0x14004c39d  mov     rcx, [rsp+78h+DeviceObject]
0x14004c3a5  call    cs:__imp_IoSynchronousCallDriver
0x14004c3ac  nop     dword ptr [rax+rax+00h]
0x14004c3b1  mov     rcx, r14; Irp
0x14004c3b4  mov     edi, eax
0x14004c3b6  call    cs:__imp_IoFreeIrp
0x14004c3bd  nop     dword ptr [rax+rax+00h]
0x14004c3c2  test    edi, edi
0x14004c3c4  jns     short loc_14004C43E
0x14004c3c6  cmp     edi, 0C0000185h
0x14004c3cc  jz      short loc_14004C3DA
0x14004c3ce  cmp     edi, 0C0000001h
0x14004c3d4  jnz     loc_14004C4DE
0x14004c3da  test    r12d, r12d
0x14004c3dd  jz      loc_14004C4DE
0x14004c3e3  dec     r12d
0x14004c3e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c3ed  lea     rax, WPP_GLOBAL_Control
0x14004c3f4  cmp     rcx, rax
0x14004c3f7  jz      short loc_14004C415
0x14004c3f9  mov     eax, [rcx+2Ch]
0x14004c3fc  test    al, 40h
0x14004c3fe  jz      short loc_14004C415
0x14004c400  mov     rcx, [rcx+18h]
0x14004c404  lea     r8, WPP_9fc1880bfcae3bc333ea8e1a40f594fb_Traceguids
0x14004c40b  mov     edx, 0Ah
0x14004c410  call    WPP_SF_
0x14004c415  lea     r8, [rsp+78h+Interval]; Interval
0x14004c41d  xor     edx, edx; Alertable
0x14004c41f  xor     ecx, ecx; WaitMode
0x14004c421  call    cs:__imp_KeDelayExecutionThread
0x14004c428  nop     dword ptr [rax+rax+00h]
0x14004c42d  mov     rdi, [rsp+78h+arg_40]
0x14004c435  lea     r14d, [rsi+4Ch]
0x14004c439  jmp     loc_14004C2B3
0x14004c43e  mov     al, [rbx+3Ah]
0x14004c441  test    al, 0Fh
0x14004c443  jz      short loc_14004C455
0x14004c445  mov     dl, 1
0x14004c447  mov     edi, 0C0000185h
0x14004c44c  mov     [rsp+78h+arg_18], dl
0x14004c453  jmp     short loc_14004C467
0x14004c455  cmp     byte ptr [rbx+2], 0
0x14004c459  jz      short loc_14004C4A2
0x14004c45b  mov     dl, [rsp+78h+arg_18]
0x14004c462  mov     edi, 0C000000Dh
0x14004c467  and     al, 0Fh
0x14004c469  cmp     al, 2
0x14004c46b  jnz     short loc_14004C49C
0x14004c46d  movzx   ecx, byte ptr [rbx+45h]
0x14004c471  movzx   eax, byte ptr [rbx+44h]
0x14004c475  shl     ecx, 8
0x14004c478  or      ecx, eax
0x14004c47a  cmp     cl, 4
0x14004c47d  jnz     short loc_14004C49C
0x14004c47f  shr     ecx, 8
0x14004c482  cmp     ecx, 4
0x14004c485  jz      short loc_14004C48F
0x14004c487  lea     eax, [rcx-7]
0x14004c48a  cmp     eax, 1
0x14004c48d  ja      short loc_14004C49C
0x14004c48f  test    r12d, r12d
0x14004c492  jz      short loc_14004C510
0x14004c494  dec     r12d
0x14004c497  jmp     loc_14004C415
0x14004c49c  test    dl, dl
0x14004c49e  jnz     short loc_14004C4A4
0x14004c4a0  jmp     short loc_14004C510
0x14004c4a2  xor     edi, edi
0x14004c4a4  test    r13b, r13b
0x14004c4a7  jz      short loc_14004C510
0x14004c4a9  mov     eax, [rbx+0Ch]
0x14004c4ac  cmp     esi, eax
0x14004c4ae  jnb     short loc_14004C4B7
0x14004c4b0  mov     edi, 80000005h
0x14004c4b5  jmp     short loc_14004C510
0x14004c4b7  jbe     short loc_14004C4BB
0x14004c4b9  mov     esi, eax
0x14004c4bb  cmp     edi, 80000005h
0x14004c4c1  jz      short loc_14004C510
0x14004c4c3  mov     rcx, [rsp+78h+arg_10]; void *
0x14004c4cb  lea     rdx, [rbx+4Ch]; Src
0x14004c4cf  mov     r8d, esi; Size
0x14004c4d2  call    memmove
0x14004c4d7  jmp     short loc_14004C510
0x14004c4d9  mov     edi, 0C000009Ah
0x14004c4de  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c4e5  lea     rax, WPP_GLOBAL_Control
0x14004c4ec  cmp     rcx, rax
0x14004c4ef  jz      short loc_14004C510
0x14004c4f1  mov     eax, [rcx+2Ch]
0x14004c4f4  test    al, 40h
0x14004c4f6  jz      short loc_14004C510
0x14004c4f8  mov     rcx, [rcx+18h]
0x14004c4fc  lea     r8, WPP_9fc1880bfcae3bc333ea8e1a40f594fb_Traceguids
0x14004c503  mov     edx, 0Bh
0x14004c508  mov     r9d, edi
0x14004c50b  call    WPP_SF_d
0x14004c510  test    r15b, r15b
0x14004c513  jz      short loc_14004C526
0x14004c515  xor     edx, edx; Tag
0x14004c517  mov     rcx, rbx; P
0x14004c51a  call    cs:__imp_ExFreePoolWithTag
0x14004c521  nop     dword ptr [rax+rax+00h]
0x14004c526  mov     eax, edi
0x14004c528  add     rsp, 38h
0x14004c52c  pop     r15
0x14004c52e  pop     r14
0x14004c530  pop     r13
0x14004c532  pop     r12
0x14004c534  pop     rdi
0x14004c535  pop     rsi
0x14004c536  pop     rbp
0x14004c537  pop     rbx
0x14004c538  retn
```
