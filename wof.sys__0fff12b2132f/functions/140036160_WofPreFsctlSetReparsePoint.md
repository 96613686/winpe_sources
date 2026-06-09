# WofPreFsctlSetReparsePoint

- ea: `0x140036160`
- end: `0x140036325`
- name: `WofPreFsctlSetReparsePoint`
- size: `453`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1400346f0`

## callees

- `0x14000a914`
- `0x140034f50`
- `0x140036160`
- `0x140036904`

## import_xrefs

- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x1400361d0`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x1400361e8`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x1400361d0`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x1400361e8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400362de`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400362de`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400362a7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400362a7`
- `FLTMGR!FltGetStreamContext` at `0x14003622b`
- `FLTMGR!FltGetStreamContext` at `0x14003622b`
- `FLTMGR!FltReleaseContext` at `0x140036280`
- `FLTMGR!FltReleaseContext` at `0x1400362ee`
- `FLTMGR!FltReleaseContext` at `0x140036308`
- `FLTMGR!FltReleaseContext` at `0x140036280`
- `FLTMGR!FltReleaseContext` at `0x1400362ee`
- `FLTMGR!FltReleaseContext` at `0x140036308`

## pseudocode

```c
__int64 __fastcall WofPreFsctlSetReparsePoint(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  __int64 v6; // rdi
  NTSTATUS v7; // eax
  ULONG v9; // ecx
  _DWORD *v10; // rsi
  int v11; // ecx
  struct _FILE_OBJECT *v12; // rdx
  struct _FLT_INSTANCE *v13; // rcx
  int v14; // edi
  __int64 v15; // r9
  PFLT_CONTEXT Context; // [rsp+40h] [rbp+20h] BYREF
  __int64 v17; // [rsp+50h] [rbp+30h] BYREF

  v17 = a3;
  v3 = *(_QWORD *)(a1 + 16);
  v6 = *(_QWORD *)(v3 + 48);
  if ( !v6 )
  {
    v7 = -1073741306;
LABEL_3:
    *(_DWORD *)(a1 + 24) = v7;
    return 4;
  }
  v9 = *(_DWORD *)(v3 + 32);
  if ( *(_DWORD *)(v3 + 40) == 590860 )
  {
    if ( v9 < 0x20 )
    {
      v7 = -1073741789;
      goto LABEL_3;
    }
    v10 = (_DWORD *)(v6 + 32);
    v7 = FsRtlValidateReparsePointBuffer(v9 - 32, (PREPARSE_DATA_BUFFER)(v6 + 32));
    if ( v7 < 0 )
      goto LABEL_3;
    v11 = *(_DWORD *)(v6 + 4);
  }
  else
  {
    v7 = FsRtlValidateReparsePointBuffer(v9, *(PREPARSE_DATA_BUFFER *)(v3 + 48));
    if ( v7 < 0 )
      goto LABEL_3;
    v11 = 0;
    v10 = (_DWORD *)v6;
  }
  if ( *v10 == FileTag || v11 == FileTag )
  {
    *(_DWORD *)(a1 + 24) = -1073741811;
    return 4;
  }
  v12 = *(struct _FILE_OBJECT **)(a2 + 32);
  v13 = *(struct _FLT_INSTANCE **)(a2 + 24);
  Context = 0;
  LOBYTE(v17) = 0;
  if ( FltGetStreamContext(v13, v12, &Context) >= 0 )
  {
    if ( (int)WofIsDataInFilesystemEx(Context, a2, &v17, 0) >= 0 && !(_BYTE)v17 )
    {
      v14 = WofEnsureExtdFileContext(*(_QWORD *)Context);
      if ( v14 >= 0 )
      {
        WofEnsureExtdFileContext(*(_QWORD *)Context);
        ExAcquireFastMutexUnsafe(*(PFAST_MUTEX *)(*(_QWORD *)Context + 16LL));
        if ( (*((_DWORD *)Context + 2) & 4) == 0 )
        {
          LOBYTE(v15) = 1;
          v14 = WofInflateFile(a1, a2, Context, v15);
        }
        ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(*(_QWORD *)Context + 16LL));
        FltReleaseContext(Context);
        if ( v14 >= 0 )
          return 1;
      }
      else
      {
        FltReleaseContext(Context);
      }
      *(_DWORD *)(a1 + 24) = v14;
      return 4;
    }
    FltReleaseContext(Context);
  }
  return 1;
}

```

## disassembly

```asm
0x140036160  mov     [rsp-18h+arg_8], rbx
0x140036165  mov     [rsp-18h+arg_18], rsi
0x14003616a  mov     [rsp-18h+arg_10], r8
0x14003616f  push    rbp
0x140036170  push    rdi
0x140036171  push    r14
0x140036173  mov     rbp, rsp
0x140036176  sub     rsp, 20h
0x14003617a  mov     rax, [rcx+10h]
0x14003617e  mov     r14, rdx
0x140036181  mov     rbx, rcx
0x140036184  mov     rdi, [rax+30h]
0x140036188  test    rdi, rdi
0x14003618b  jnz     short loc_1400361AE
0x14003618d  mov     eax, 0C0000206h
0x140036192  mov     [rbx+18h], eax
0x140036195  mov     eax, 4
0x14003619a  mov     rbx, [rsp+20h+arg_8]
0x14003619f  mov     rsi, [rsp+20h+arg_18]
0x1400361a4  add     rsp, 20h
0x1400361a8  pop     r14
0x1400361aa  pop     rdi
0x1400361ab  pop     rbp
0x1400361ac  retn
0x1400361ae  cmp     dword ptr [rax+28h], 9040Ch
0x1400361b5  mov     ecx, [rax+20h]; BufferLength
0x1400361b8  jnz     short loc_1400361E5
0x1400361ba  cmp     ecx, 20h ; ' '
0x1400361bd  jnb     short loc_1400361C6
0x1400361bf  mov     eax, 0C0000023h
0x1400361c4  jmp     short loc_140036192
0x1400361c6  lea     rsi, [rdi+20h]
0x1400361ca  add     ecx, 0FFFFFFE0h; BufferLength
0x1400361cd  mov     rdx, rsi; ReparseBuffer
0x1400361d0  call    cs:__imp_FsRtlValidateReparsePointBuffer
0x1400361d7  nop     dword ptr [rax+rax+00h]
0x1400361dc  test    eax, eax
0x1400361de  js      short loc_140036192
0x1400361e0  mov     ecx, [rdi+4]
0x1400361e3  jmp     short loc_1400361FD
0x1400361e5  mov     rdx, rdi; ReparseBuffer
0x1400361e8  call    cs:__imp_FsRtlValidateReparsePointBuffer
0x1400361ef  nop     dword ptr [rax+rax+00h]
0x1400361f4  test    eax, eax
0x1400361f6  js      short loc_140036192
0x1400361f8  xor     ecx, ecx
0x1400361fa  mov     rsi, rdi
0x1400361fd  mov     edx, cs:FileTag
0x140036203  cmp     [rsi], edx
0x140036205  jz      loc_140036319
0x14003620b  cmp     ecx, edx
0x14003620d  jz      loc_140036319
0x140036213  mov     rdx, [r14+20h]; FileObject
0x140036217  lea     r8, [rbp+Context]; Context
0x14003621b  mov     rcx, [r14+18h]; Instance
0x14003621f  mov     [rbp+Context], 0
0x140036227  mov     byte ptr [rbp+arg_10], 0
0x14003622b  call    cs:__imp_FltGetStreamContext
0x140036232  nop     dword ptr [rax+rax+00h]
0x140036237  test    eax, eax
0x140036239  jns     short loc_140036245
0x14003623b  mov     eax, 1
0x140036240  jmp     loc_14003619A
0x140036245  mov     rcx, [rbp+Context]
0x140036249  lea     r8, [rbp+arg_10]
0x14003624d  xor     r9d, r9d
0x140036250  mov     rdx, r14
0x140036253  call    WofIsDataInFilesystemEx
0x140036258  test    eax, eax
0x14003625a  js      loc_140036304
0x140036260  cmp     byte ptr [rbp+arg_10], 0
0x140036264  jnz     loc_140036304
0x14003626a  mov     rcx, [rbp+Context]
0x14003626e  mov     rcx, [rcx]
0x140036271  call    WofEnsureExtdFileContext
0x140036276  mov     rcx, [rbp+Context]; Context
0x14003627a  mov     edi, eax
0x14003627c  test    eax, eax
0x14003627e  jns     short loc_140036294
0x140036280  call    cs:__imp_FltReleaseContext
0x140036287  nop     dword ptr [rax+rax+00h]
0x14003628c  mov     [rbx+18h], edi
0x14003628f  jmp     loc_140036195
0x140036294  mov     rcx, [rcx]
0x140036297  call    WofEnsureExtdFileContext
0x14003629c  mov     rax, [rbp+Context]
0x1400362a0  mov     rcx, [rax]
0x1400362a3  mov     rcx, [rcx+10h]; FastMutex
0x1400362a7  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400362ae  nop     dword ptr [rax+rax+00h]
0x1400362b3  mov     rax, [rbp+Context]
0x1400362b7  mov     ecx, [rax+8]
0x1400362ba  test    cl, 4
0x1400362bd  jnz     short loc_1400362D3
0x1400362bf  mov     r8, [rbp+Context]
0x1400362c3  mov     r9b, 1
0x1400362c6  mov     rdx, r14
0x1400362c9  mov     rcx, rbx
0x1400362cc  call    WofInflateFile
0x1400362d1  mov     edi, eax
0x1400362d3  mov     rax, [rbp+Context]
0x1400362d7  mov     rcx, [rax]
0x1400362da  mov     rcx, [rcx+10h]; FastMutex
0x1400362de  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400362e5  nop     dword ptr [rax+rax+00h]
0x1400362ea  mov     rcx, [rbp+Context]; Context
0x1400362ee  call    cs:__imp_FltReleaseContext
0x1400362f5  nop     dword ptr [rax+rax+00h]
0x1400362fa  test    edi, edi
0x1400362fc  jns     loc_14003623B
0x140036302  jmp     short loc_14003628C
0x140036304  mov     rcx, [rbp+Context]; Context
0x140036308  call    cs:__imp_FltReleaseContext
0x14003630f  nop     dword ptr [rax+rax+00h]
0x140036314  jmp     loc_14003623B
0x140036319  mov     dword ptr [rbx+18h], 0C000000Dh
0x140036320  jmp     loc_140036195
```
