# SqospCreateStreamHandleContext

- ea: `0x14000603c`
- end: `0x14000617f`
- name: `SqospCreateStreamHandleContext`
- size: `323`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400142c0`
- `0x140014950`
- `0x140014d10`

## callees

- `0x140003460`
- `0x14000603c`
- `0x140006188`
- `0x14000666c`

## import_xrefs

- `FLTMGR!FltSetStreamHandleContext` at `0x14000609e`
- `FLTMGR!FltSetStreamHandleContext` at `0x14000609e`
- `FLTMGR!FltReleaseContext` at `0x1400060ba`
- `FLTMGR!FltReleaseContext` at `0x14000614d`
- `FLTMGR!FltReleaseContext` at `0x140006163`
- `FLTMGR!FltReleaseContext` at `0x1400060ba`
- `FLTMGR!FltReleaseContext` at `0x14000614d`
- `FLTMGR!FltReleaseContext` at `0x140006163`

## pseudocode

```c
__int64 __fastcall SqospCreateStreamHandleContext(__int64 a1, __int64 a2, __int64 a3, char a4, char a5, _QWORD *a6)
{
  int StreamHandleContext; // eax
  PFLT_CONTEXT v11; // rbx
  int v12; // edi
  NTSTATUS v13; // eax
  int OldContext; // [rsp+20h] [rbp-58h]
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-48h] BYREF
  PFLT_CONTEXT NewContext[8]; // [rsp+38h] [rbp-40h] BYREF

  NewContext[0] = 0;
  Context = 0;
  StreamHandleContext = SqospAllocateStreamHandleContext(a2, NewContext);
  v11 = NewContext[0];
  v12 = StreamHandleContext;
  if ( StreamHandleContext >= 0 )
  {
    v13 = FltSetStreamHandleContext(
            *(PFLT_INSTANCE *)(a2 + 24),
            *(PFILE_OBJECT *)(a2 + 32),
            FLT_SET_CONTEXT_KEEP_IF_EXISTS,
            NewContext[0],
            &Context);
    v12 = v13;
    if ( v13 >= 0 )
      goto LABEL_10;
    if ( v13 == -1071906814 )
    {
      FltReleaseContext(v11);
      v11 = Context;
      Context = 0;
      if ( !a5 )
      {
        v12 = 0;
LABEL_11:
        *a6 = v11;
        v11 = 0;
        goto LABEL_12;
      }
LABEL_10:
      LOBYTE(OldContext) = a4;
      v12 = SqospModifyStreamHandleContext(a1, a2, v11, a3, OldContext);
      if ( v12 < 0 )
        goto LABEL_12;
      goto LABEL_11;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_af53c64ad8bd3a498290aca5a9ae070a_Traceguids,
        (unsigned int)v13);
    }
  }
LABEL_12:
  if ( v11 )
    FltReleaseContext(v11);
  if ( Context )
    FltReleaseContext(Context);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000603c  push    rbx
0x14000603e  push    rbp
0x14000603f  push    rsi
0x140006040  push    rdi
0x140006041  push    r14
0x140006043  push    r15
0x140006045  sub     rsp, 48h
0x140006049  mov     rsi, rdx
0x14000604c  mov     [rsp+78h+NewContext], 0
0x140006055  mov     r15, rcx
0x140006058  mov     [rsp+78h+Context], 0
0x140006061  mov     rcx, rsi
0x140006064  lea     rdx, [rsp+78h+NewContext]
0x140006069  mov     bpl, r9b
0x14000606c  mov     r14, r8
0x14000606f  call    SqospAllocateStreamHandleContext
0x140006074  mov     rbx, [rsp+78h+NewContext]
0x140006079  mov     edi, eax
0x14000607b  test    eax, eax
0x14000607d  js      loc_140006145
0x140006083  mov     rdx, [rsi+20h]; FileObject
0x140006087  lea     rax, [rsp+78h+Context]
0x14000608c  mov     rcx, [rsi+18h]; Instance
0x140006090  mov     r9, rbx; NewContext
0x140006093  mov     r8d, 1; Operation
0x140006099  mov     qword ptr [rsp+78h+OldContext], rax; OldContext
0x14000609e  call    cs:__imp_FltSetStreamHandleContext
0x1400060a5  nop     dword ptr [rax+rax+00h]
0x1400060aa  mov     edi, eax
0x1400060ac  test    eax, eax
0x1400060ae  jns     short loc_14000611C
0x1400060b0  cmp     eax, 0C01C0002h
0x1400060b5  jnz     short loc_1400060E2
0x1400060b7  mov     rcx, rbx; Context
0x1400060ba  call    cs:__imp_FltReleaseContext
0x1400060c1  nop     dword ptr [rax+rax+00h]
0x1400060c6  cmp     [rsp+78h+arg_20], 0
0x1400060ce  mov     rbx, [rsp+78h+Context]
0x1400060d3  mov     [rsp+78h+Context], 0
0x1400060dc  jnz     short loc_14000611C
0x1400060de  xor     edi, edi
0x1400060e0  jmp     short loc_140006138
0x1400060e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400060e9  lea     rax, WPP_GLOBAL_Control
0x1400060f0  cmp     rcx, rax
0x1400060f3  jz      short loc_140006145
0x1400060f5  mov     eax, [rcx+2Ch]
0x1400060f8  test    al, 10h
0x1400060fa  jz      short loc_140006145
0x1400060fc  cmp     byte ptr [rcx+29h], 2
0x140006100  jb      short loc_140006145
0x140006102  mov     rcx, [rcx+18h]
0x140006106  lea     r8, WPP_af53c64ad8bd3a498290aca5a9ae070a_Traceguids
0x14000610d  mov     edx, 0Ch
0x140006112  mov     r9d, edi
0x140006115  call    WPP_SF_d
0x14000611a  jmp     short loc_140006145
0x14000611c  mov     r9, r14
0x14000611f  mov     byte ptr [rsp+78h+OldContext], bpl
0x140006124  mov     r8, rbx
0x140006127  mov     rdx, rsi
0x14000612a  mov     rcx, r15
0x14000612d  call    SqospModifyStreamHandleContext
0x140006132  mov     edi, eax
0x140006134  test    eax, eax
0x140006136  js      short loc_140006145
0x140006138  mov     rax, [rsp+78h+arg_28]
0x140006140  mov     [rax], rbx
0x140006143  xor     ebx, ebx
0x140006145  test    rbx, rbx
0x140006148  jz      short loc_140006159
0x14000614a  mov     rcx, rbx; Context
0x14000614d  call    cs:__imp_FltReleaseContext
0x140006154  nop     dword ptr [rax+rax+00h]
0x140006159  mov     rcx, [rsp+78h+Context]; Context
0x14000615e  test    rcx, rcx
0x140006161  jz      short loc_14000616F
0x140006163  call    cs:__imp_FltReleaseContext
0x14000616a  nop     dword ptr [rax+rax+00h]
0x14000616f  mov     eax, edi
0x140006171  add     rsp, 48h
0x140006175  pop     r15
0x140006177  pop     r14
0x140006179  pop     rdi
0x14000617a  pop     rsi
0x14000617b  pop     rbp
0x14000617c  pop     rbx
0x14000617d  retn
```
