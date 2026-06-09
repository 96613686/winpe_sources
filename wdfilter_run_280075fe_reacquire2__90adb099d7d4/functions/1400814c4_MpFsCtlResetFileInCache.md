# MpFsCtlResetFileInCache

- ea: `0x1400814c4`
- end: `0x14008167c`
- name: `MpFsCtlResetFileInCache`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400448f0`

## callees

- `0x1400018a4`
- `0x140005944`
- `0x1400118d0`
- `0x1400814c4`

## import_xrefs

- `ntoskrnl!IoThreadToProcess` at `0x140081515`
- `ntoskrnl!IoThreadToProcess` at `0x14008153d`
- `ntoskrnl!IoThreadToProcess` at `0x140081515`
- `ntoskrnl!IoThreadToProcess` at `0x14008153d`
- `FLTMGR!FltReleaseContext` at `0x140081655`
- `FLTMGR!FltReleaseContext` at `0x140081655`
- `FLTMGR!FltGetStreamContext` at `0x1400815a2`
- `FLTMGR!FltGetStreamContext` at `0x1400815a2`

## pseudocode

```c
NTSTATUS __fastcall MpFsCtlResetFileInCache(__int64 a1, __int64 a2)
{
  struct _KPROCESS *v3; // rbx
  struct _KPROCESS *v4; // rbx
  NTSTATUS result; // eax
  unsigned int v6; // r8d
  int v7; // eax
  PDEVICE_OBJECT v8; // rcx
  int v9; // edx
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-18h] BYREF

  Context = 0;
  if ( *(int *)(MpData + 868) < 0
    || (v3 = *(struct _KPROCESS **)(MpData + 232), IoThreadToProcess(KeGetCurrentThread()) == v3)
    || (v4 = *(struct _KPROCESS **)(MpData + 256), IoThreadToProcess(KeGetCurrentThread()) == v4) )
  {
    result = FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context);
    if ( result < 0 )
    {
      _mm_lfence();
      return result;
    }
    v6 = *((_DWORD *)Context + 8);
    if ( v6 == 3 || v6 <= 7 && (v7 = 148, _bittest(&v7, v6)) )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        goto LABEL_20;
      v9 = 25;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
        goto LABEL_20;
      v9 = 24;
    }
    WPP_SF_Zd(
      v8->AttachedDevice,
      v9,
      (unsigned int)WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids,
      *(_QWORD *)(a2 + 32) + 88,
      v6);
LABEL_20:
    *((_DWORD *)Context + 8) = 0;
    _InterlockedAnd((volatile signed __int32 *)Context + 12, 0xFFFFBFFF);
    FltReleaseContext(Context);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      23,
      WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids,
      *(unsigned int *)(MpData + 868));
  return -1073741790;
}

```

## disassembly

```asm
0x1400814c4  mov     [rsp+arg_0], rbx
0x1400814c9  push    rdi
0x1400814ca  sub     rsp, 40h
0x1400814ce  mov     rax, cs:__security_cookie
0x1400814d5  xor     rax, rsp
0x1400814d8  mov     [rsp+48h+var_10], rax
0x1400814dd  mov     rax, cs:MpData
0x1400814e4  mov     rdi, rdx
0x1400814e7  mov     [rsp+48h+Context], 0
0x1400814f0  mov     ecx, [rax+364h]
0x1400814f6  test    ecx, ecx
0x1400814f8  js      loc_140081595
0x1400814fe  mov     rcx, gs:188h; Thread
0x140081507  mov     rax, cs:MpData
0x14008150e  mov     rbx, [rax+0E8h]
0x140081515  call    cs:__imp_IoThreadToProcess
0x14008151c  nop     dword ptr [rax+rax+00h]
0x140081521  cmp     rax, rbx
0x140081524  jz      short loc_140081595
0x140081526  mov     rcx, gs:188h; Thread
0x14008152f  mov     rax, cs:MpData
0x140081536  mov     rbx, [rax+100h]
0x14008153d  call    cs:__imp_IoThreadToProcess
0x140081544  nop     dword ptr [rax+rax+00h]
0x140081549  cmp     rax, rbx
0x14008154c  jz      short loc_140081595
0x14008154e  mov     rcx, cs:WPP_GLOBAL_Control
0x140081555  lea     rax, WPP_GLOBAL_Control
0x14008155c  cmp     rcx, rax
0x14008155f  jz      short loc_14008158B
0x140081561  mov     eax, [rcx+2Ch]
0x140081564  test    al, 1
0x140081566  jz      short loc_14008158B
0x140081568  mov     r9, cs:MpData
0x14008156f  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x140081576  mov     rcx, [rcx+18h]
0x14008157a  mov     edx, 17h
0x14008157f  mov     r9d, [r9+364h]
0x140081586  call    WPP_SF_d
0x14008158b  mov     eax, 0C0000022h
0x140081590  jmp     loc_140081663
0x140081595  mov     rdx, [rdi+20h]; FileObject
0x140081599  lea     r8, [rsp+48h+Context]; Context
0x14008159e  mov     rcx, [rdi+18h]; Instance
0x1400815a2  call    cs:__imp_FltGetStreamContext
0x1400815a9  nop     dword ptr [rax+rax+00h]
0x1400815ae  test    eax, eax
0x1400815b0  jns     short loc_1400815BA
0x1400815b2  lfence
0x1400815b5  jmp     loc_140081663
0x1400815ba  mov     rax, [rsp+48h+Context]
0x1400815bf  mov     r8d, [rax+20h]
0x1400815c3  cmp     r8d, 3
0x1400815c7  jz      short loc_1400815FB
0x1400815c9  cmp     r8d, 7
0x1400815cd  ja      short loc_1400815DA
0x1400815cf  mov     eax, 94h
0x1400815d4  bt      eax, r8d
0x1400815d8  jb      short loc_1400815FB
0x1400815da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400815e1  lea     rax, WPP_GLOBAL_Control
0x1400815e8  cmp     rcx, rax
0x1400815eb  jz      short loc_140081637
0x1400815ed  mov     eax, [rcx+2Ch]
0x1400815f0  test    al, 2
0x1400815f2  jz      short loc_140081637
0x1400815f4  mov     edx, 18h
0x1400815f9  jmp     short loc_14008161A
0x1400815fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140081602  lea     rax, WPP_GLOBAL_Control
0x140081609  cmp     rcx, rax
0x14008160c  jz      short loc_140081637
0x14008160e  mov     eax, [rcx+2Ch]
0x140081611  test    al, 4
0x140081613  jz      short loc_140081637
0x140081615  mov     edx, 19h
0x14008161a  mov     r9, [rdi+20h]
0x14008161e  mov     rcx, [rcx+18h]
0x140081622  add     r9, 58h ; 'X'
0x140081626  mov     [rsp+48h+var_28], r8d
0x14008162b  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x140081632  call    WPP_SF_Zd
0x140081637  mov     rax, [rsp+48h+Context]
0x14008163c  mov     dword ptr [rax+20h], 0
0x140081643  mov     rax, [rsp+48h+Context]
0x140081648  lock and dword ptr [rax+30h], 0FFFFBFFFh
0x140081650  mov     rcx, [rsp+48h+Context]; Context
0x140081655  call    cs:__imp_FltReleaseContext
0x14008165c  nop     dword ptr [rax+rax+00h]
0x140081661  xor     eax, eax
0x140081663  mov     rcx, [rsp+48h+var_10]
0x140081668  xor     rcx, rsp; StackCookie
0x14008166b  call    __security_check_cookie
0x140081670  mov     rbx, [rsp+48h+arg_0]
0x140081675  add     rsp, 40h
0x140081679  pop     rdi
0x14008167a  retn
```
