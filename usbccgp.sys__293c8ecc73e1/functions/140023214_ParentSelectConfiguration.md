# ParentSelectConfiguration

- ea: `0x140023214`
- end: `0x14002340d`
- name: `ParentSelectConfiguration`
- size: `505`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int16)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140028f7c`

## callees

- `0x1400088b4`
- `0x140009acc`
- `0x14000b40c`
- `0x14000ba3c`
- `0x14000f664`
- `0x140014e00`
- `0x140023214`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400233ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400233ed`
- `ntoskrnl!ExAllocatePool2` at `0x140023350`
- `ntoskrnl!ExAllocatePool2` at `0x140023350`

## pseudocode

```c
__int64 __fastcall ParentSelectConfiguration(
        __int64 a1,
        unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 a5)
{
  __int64 v8; // rax
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rsi
  int v13; // ebx
  int v14; // edx
  unsigned __int16 *v15; // r14
  unsigned int v16; // ebp
  __int64 v17; // r15
  void *Pool2; // rax
  int v19; // edx
  size_t Size; // [rsp+30h] [rbp-58h]

  v8 = BuildSelectConfigUrb(a1, a2, a4, a5);
  v12 = v8;
  if ( v8 )
  {
    v13 = SubmitUrb(a1, v8, v10, v11);
    if ( v13 >= 0 )
    {
      v15 = (unsigned __int16 *)(v12 + 40);
      v16 = 0;
      *(_QWORD *)(a1 + 72) = *(_QWORD *)(v12 + 32);
      while ( v16 < a5 )
      {
        v17 = *v15;
        Pool2 = (void *)ExAllocatePool2(64, v17, 1130525525);
        *(_QWORD *)(a4 + 16LL * v16 + 8) = Pool2;
        if ( !Pool2 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v19) = 2;
            WPP_RECORDER_SF_(
              *(_QWORD *)(a1 + 1368),
              v19,
              8,
              16,
              (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids);
          }
          LODWORD(Size) = 0;
          v13 = -1073741670;
          RecordStartFailData(a1, -1073741670, 0, -1610612731, 1347633993, 0, Size);
          break;
        }
        memmove(Pool2, v15, (unsigned int)v17);
        v15 = (unsigned __int16 *)((char *)v15 + v17);
        ++v16;
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_D(
          *(_QWORD *)(a1 + 1368),
          v14,
          8,
          15,
          (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
          v13);
      }
      LODWORD(Size) = a2[1];
      RecordStartFailData(a1, v13, *(_DWORD *)(v12 + 4), -1610612728, 1347633990, a2, Size);
    }
    ExFreePoolWithTag((PVOID)v12, 0x43627355u);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v9, 8, 14, (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids);
    }
    LODWORD(Size) = 0;
    v13 = -1073741670;
    RecordStartFailData(a1, -1073741670, 0, -1610612731, 1347634005, 0, Size);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140023214  push    rbx
0x140023216  push    rbp
0x140023217  push    rsi
0x140023218  push    rdi
0x140023219  push    r12
0x14002321b  push    r13
0x14002321d  push    r14
0x14002321f  push    r15
0x140023221  sub     rsp, 48h
0x140023225  mov     r13, r9
0x140023228  mov     rbp, rdx
0x14002322b  movzx   r9d, [rsp+88h+arg_20]
0x140023234  mov     r8, r13
0x140023237  mov     rdi, rcx
0x14002323a  call    BuildSelectConfigUrb
0x14002323f  xor     r15d, r15d
0x140023242  mov     rsi, rax
0x140023245  test    rax, rax
0x140023248  jnz     short loc_1400232AB
0x14002324a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140023251  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023258  jz      short loc_14002327C
0x14002325a  mov     rcx, [rdi+558h]
0x140023261  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x140023268  lea     r9d, [rsi+0Eh]
0x14002326c  mov     qword ptr [rsp+88h+var_68], rax
0x140023271  lea     r8d, [rsi+8]
0x140023275  mov     dl, 2
0x140023277  call    WPP_RECORDER_SF_
0x14002327c  mov     dword ptr [rsp+88h+Size], r15d; Size
0x140023281  mov     ebx, 0C000009Ah
0x140023286  mov     edx, ebx; int
0x140023288  mov     [rsp+88h+Src], r15; Src
0x14002328d  mov     r9d, 0A0000005h; int
0x140023293  mov     [rsp+88h+var_68], 50534355h; int
0x14002329b  xor     r8d, r8d; int
0x14002329e  mov     rcx, rdi; int
0x1400232a1  call    RecordStartFailData
0x1400232a6  jmp     loc_1400233F9
0x1400232ab  mov     rdx, rsi
0x1400232ae  mov     byte ptr [rsp+88h+Src], r15b
0x1400232b3  mov     rcx, rdi
0x1400232b6  call    SubmitUrb
0x1400232bb  mov     ebx, eax
0x1400232bd  test    eax, eax
0x1400232bf  jns     short loc_14002331D
0x1400232c1  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400232c8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400232cf  jz      short loc_1400232F9
0x1400232d1  mov     rcx, [rdi+558h]
0x1400232d8  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x1400232df  mov     r9d, 0Fh
0x1400232e5  mov     dword ptr [rsp+88h+Src], ebx
0x1400232e9  mov     dl, 2
0x1400232eb  mov     qword ptr [rsp+88h+var_68], rax
0x1400232f0  lea     r8d, [r9-7]
0x1400232f4  call    WPP_RECORDER_SF_D
0x1400232f9  movzx   eax, word ptr [rbp+2]
0x1400232fd  mov     r9d, 0A0000008h
0x140023303  mov     r8d, [rsi+4]
0x140023307  mov     dword ptr [rsp+88h+Size], eax
0x14002330b  mov     [rsp+88h+Src], rbp
0x140023310  mov     [rsp+88h+var_68], 50534346h
0x140023318  jmp     loc_1400233DB
0x14002331d  mov     rax, [rsi+20h]
0x140023321  lea     r14, [rsi+28h]
0x140023325  movzx   r12d, [rsp+88h+arg_20]
0x14002332e  mov     ebp, r15d
0x140023331  mov     [rdi+48h], rax
0x140023335  cmp     ebp, r12d
0x140023338  jnb     loc_1400233E5
0x14002333e  movzx   r15d, word ptr [r14]
0x140023342  mov     r8d, 43627355h
0x140023348  mov     edx, r15d
0x14002334b  mov     ecx, 40h ; '@'
0x140023350  call    cs:__imp_ExAllocatePool2
0x140023357  nop     dword ptr [rax+rax+00h]
0x14002335c  mov     ecx, ebp
0x14002335e  add     rcx, rcx
0x140023361  mov     [r13+rcx*8+8], rax
0x140023366  test    rax, rax
0x140023369  jz      short loc_140023380
0x14002336b  mov     r8d, r15d; Size
0x14002336e  mov     rdx, r14; Src
0x140023371  mov     rcx, rax; void *
0x140023374  call    memmove
0x140023379  add     r14, r15
0x14002337c  inc     ebp
0x14002337e  jmp     short loc_140023335
0x140023380  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140023387  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002338e  jz      short loc_1400233B4
0x140023390  mov     rcx, [rdi+558h]
0x140023397  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14002339e  mov     r9d, 10h
0x1400233a4  mov     qword ptr [rsp+88h+var_68], rax
0x1400233a9  mov     dl, 2
0x1400233ab  lea     r8d, [r9-8]
0x1400233af  call    WPP_RECORDER_SF_
0x1400233b4  mov     dword ptr [rsp+88h+Size], 0; Size
0x1400233bc  mov     r9d, 0A0000005h; int
0x1400233c2  mov     [rsp+88h+Src], 0; Src
0x1400233cb  xor     r8d, r8d; int
0x1400233ce  mov     [rsp+88h+var_68], 50534349h; int
0x1400233d6  mov     ebx, 0C000009Ah
0x1400233db  mov     edx, ebx; int
0x1400233dd  mov     rcx, rdi; int
0x1400233e0  call    RecordStartFailData
0x1400233e5  mov     edx, 43627355h; Tag
0x1400233ea  mov     rcx, rsi; P
0x1400233ed  call    cs:__imp_ExFreePoolWithTag
0x1400233f4  nop     dword ptr [rax+rax+00h]
0x1400233f9  mov     eax, ebx
0x1400233fb  add     rsp, 48h
0x1400233ff  pop     r15
0x140023401  pop     r14
0x140023403  pop     r13
0x140023405  pop     r12
0x140023407  pop     rdi
0x140023408  pop     rsi
0x140023409  pop     rbp
0x14002340a  pop     rbx
0x14002340b  retn
```
