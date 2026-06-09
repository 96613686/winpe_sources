# SkWriteProcessStartEvent

- ea: `0x1400bb42c`
- end: `0x1400bb5ad`
- name: `SkWriteProcessStartEvent`
- size: `385`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14002b5f4`

## callees

- `0x14000e460`
- `0x14000f0f0`
- `0x14002ba08`
- `0x140037e68`
- `0x140040c7c`
- `0x1400bb1a8`
- `0x1400bb42c`
- `0x1400d4e8c`
- `0x1400fc664`
- `0x1400fc6a0`

## string_xrefs

- `0x1400bb558`: `SkWriteProcessStartEvent`

## pseudocode

```c
__int64 __fastcall SkWriteProcessStartEvent(__int64 a1, char a2)
{
  __int64 v3; // r12
  __int64 v4; // r15
  __int64 ULong64FromUser; // rax
  __int64 v6; // rbx
  unsigned __int16 ULongFromUser; // di
  __int64 v8; // rax
  void *v9; // r13
  void *Pool; // rax
  __int64 v11; // rbx
  int v12; // ecx
  int v13; // r8d
  char v14; // al

  LODWORD(v3) = 0;
  v4 = SkiAttachProcess(a1);
  ULong64FromUser = RtlReadULong64FromUser(*(_QWORD *)(a1 + 160) + 32LL);
  if ( (ULong64FromUser & 7) != 0
    || (v6 = ULong64FromUser + 96,
        ULongFromUser = RtlReadULongFromUser(ULong64FromUser + 96),
        v8 = RtlReadULong64FromUser(v6 + 8),
        v9 = (void *)v8,
        ULongFromUser)
    && (v8 & 1) != 0 )
  {
    ExRaiseDatatypeMisalignment();
  }
  Pool = (void *)SkAllocatePool(1, ULongFromUser + 2LL);
  v11 = (__int64)Pool;
  if ( Pool )
  {
    RtlCopyFromUser(Pool, v9, ULongFromUser);
    *(_WORD *)(v11 + 2 * ((unsigned __int64)ULongFromUser >> 1)) = 0;
    if ( a1 == 1 || (v14 = 1, (*(_DWORD *)a1 & 0x1600) != 0) )
      v14 = 0;
    if ( v14 )
      v3 = *(_QWORD *)(a1 + 432);
    if ( (Microsoft_Windows_IsolatedUserModeEnableBits & 1) != 0 )
      McTemplateK0xqqz_EtwWriteTransfer(v12, (unsigned int)IumProcessStart, v13, v3, *(_DWORD *)(a1 + 56), a2, v11);
  }
  if ( v11 )
    SkFreePool(1, v11);
  return SkiAttachProcess(v4);
}

```

## disassembly

```asm
0x1400bb42c  mov     rax, rsp
0x1400bb42f  mov     [rax+18h], rbx
0x1400bb433  mov     [rax+20h], rsi
0x1400bb437  mov     [rax+10h], edx
0x1400bb43a  push    rdi
0x1400bb43b  push    r12
0x1400bb43d  push    r13
0x1400bb43f  push    r14
0x1400bb441  push    r15
0x1400bb443  sub     rsp, 70h
0x1400bb447  mov     r14, rcx
0x1400bb44a  xor     esi, esi
0x1400bb44c  mov     r12d, esi
0x1400bb44f  mov     [rax-58h], rsi
0x1400bb453  call    SkiAttachProcess
0x1400bb458  mov     r15, rax
0x1400bb45b  mov     [rsp+98h+arg_0], rax
0x1400bb463  mov     rcx, [r14+0A0h]
0x1400bb46a  add     rcx, 20h ; ' '
0x1400bb46e  call    RtlReadULong64FromUser
0x1400bb473  test    al, 7
0x1400bb475  jnz     loc_1400BB54F
0x1400bb47b  lea     rbx, [rax+60h]
0x1400bb47f  xorps   xmm0, xmm0
0x1400bb482  movups  [rsp+98h+var_48], xmm0
0x1400bb487  mov     rcx, rbx
0x1400bb48a  call    RtlReadULongFromUser
0x1400bb48f  mov     edi, eax
0x1400bb491  mov     dword ptr [rsp+98h+var_48], edi
0x1400bb495  lea     rcx, [rbx+8]
0x1400bb499  call    RtlReadULong64FromUser
0x1400bb49e  mov     r13, rax
0x1400bb4a1  mov     qword ptr [rsp+98h+var_48+8], rax
0x1400bb4a6  movaps  xmm0, [rsp+98h+var_48]
0x1400bb4ab  movdqa  [rsp+98h+var_38], xmm0
0x1400bb4b1  movzx   edi, di
0x1400bb4b4  test    rdi, rdi
0x1400bb4b7  jz      short loc_1400BB4C3
0x1400bb4b9  test    r13b, 1
0x1400bb4bd  jnz     loc_1400BB54F
0x1400bb4c3  lea     rdx, [rdi+2]
0x1400bb4c7  mov     ecx, 1
0x1400bb4cc  mov     r8d, 63617254h
0x1400bb4d2  call    SkAllocatePool
0x1400bb4d7  mov     rbx, rax
0x1400bb4da  mov     [rsp+98h+var_58], rax
0x1400bb4df  test    rax, rax
0x1400bb4e2  jz      loc_1400BB578
0x1400bb4e8  mov     r8, rdi; Size
0x1400bb4eb  mov     rdx, r13; Src
0x1400bb4ee  mov     rcx, rbx; void *
0x1400bb4f1  call    RtlCopyFromUser
0x1400bb4f6  shr     rdi, 1
0x1400bb4f9  mov     [rbx+rdi*2], si
0x1400bb4fd  cmp     r14, 1
0x1400bb501  jz      short loc_1400BB50E
0x1400bb503  test    dword ptr [r14], 1600h
0x1400bb50a  mov     al, 1
0x1400bb50c  jz      short loc_1400BB511
0x1400bb50e  mov     al, sil
0x1400bb511  test    al, al
0x1400bb513  jz      short loc_1400BB51C
0x1400bb515  mov     r12, [r14+1B0h]
0x1400bb51c  mov     eax, cs:Microsoft_Windows_IsolatedUserModeEnableBits
0x1400bb522  test    al, 1
0x1400bb524  jz      short loc_1400BB54D
0x1400bb526  mov     [rsp+98h+var_68], rbx
0x1400bb52b  mov     eax, [rsp+98h+arg_8]
0x1400bb532  mov     [rsp+98h+var_70], eax
0x1400bb536  mov     eax, [r14+38h]
0x1400bb53a  mov     [rsp+98h+var_78], eax
0x1400bb53e  mov     r9, r12
0x1400bb541  lea     rdx, IumProcessStart
0x1400bb548  call    McTemplateK0xqqz_EtwWriteTransfer
0x1400bb54d  jmp     short loc_1400BB578
0x1400bb54f  call    ExRaiseDatatypeMisalignment
0x1400bb555  mov     r8d, eax
0x1400bb558  lea     rdx, aSkwriteprocess; "SkWriteProcessStartEvent"
0x1400bb55f  lea     rcx, aHsExceptionGen; "%hs: Exception generated with status 0x"...
0x1400bb566  call    DbgPrint
0x1400bb56b  mov     rbx, [rsp+98h+var_58]
0x1400bb570  mov     r15, [rsp+98h+arg_0]
0x1400bb578  test    rbx, rbx
0x1400bb57b  jz      short loc_1400BB58A
0x1400bb57d  mov     rdx, rbx
0x1400bb580  mov     ecx, 1
0x1400bb585  call    SkFreePool
0x1400bb58a  mov     rcx, r15
0x1400bb58d  call    SkiAttachProcess
0x1400bb592  lea     r11, [rsp+98h+var_28]
0x1400bb597  mov     rbx, [r11+40h]
0x1400bb59b  mov     rsi, [r11+48h]
0x1400bb59f  mov     rsp, r11
0x1400bb5a2  pop     r15
0x1400bb5a4  pop     r14
0x1400bb5a6  pop     r13
0x1400bb5a8  pop     r12
0x1400bb5aa  pop     rdi
0x1400bb5ab  retn
```
