# PFOnlyConsiderDirectories

- ea: `0x1400097f0`
- end: `0x1400098a0`
- name: `PFOnlyConsiderDirectories`
- size: `176`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation`

## callees

- `0x1400097f0`

## import_xrefs

- `FLTMGR!FltReissueSynchronousIo` at `0x140009880`
- `FLTMGR!FltReissueSynchronousIo` at `0x140009880`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140009848`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140009848`
- `FLTMGR!FltIsDirectory` at `0x140009816`
- `FLTMGR!FltIsDirectory` at `0x140009816`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14000986d`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14000986d`

## pseudocode

```c
__int64 __fastcall PFOnlyConsiderDirectories(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        struct _FILE_OBJECT *a3,
        __int64 a4,
        _BYTE *a5)
{
  NTSTATUS v8; // ebp
  _QWORD *v9; // rax
  unsigned __int8 IsDirectory; // [rsp+58h] [rbp+10h] BYREF

  IsDirectory = 0;
  v8 = FltIsDirectory(a3, *(PFLT_INSTANCE *)(a2 + 24), &IsDirectory);
  if ( v8 >= 0 && a4 && !IsDirectory )
  {
    if ( *(_QWORD *)a4 )
    {
      if ( **(_QWORD **)a4 != *(_QWORD *)a4 )
      {
        FltRemoveOpenReparseEntry(*(_QWORD *)(a2 + 8), CallbackData);
        v9 = *(_QWORD **)a4;
        v9[1] = v9;
        *v9 = v9;
      }
    }
    else
    {
      CallbackData->Iopb->Parameters.Create.Options |= *(_DWORD *)(a4 + 56);
      FltSetCallbackDataDirty(CallbackData);
    }
    FltReissueSynchronousIo(*(PFLT_INSTANCE *)(a2 + 24), CallbackData);
    *a5 = 1;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400097f0  push    rbx
0x1400097f2  push    rbp
0x1400097f3  push    rsi
0x1400097f4  push    rdi
0x1400097f5  sub     rsp, 28h
0x1400097f9  mov     rax, r8
0x1400097fc  mov     [rsp+48h+IsDirectory], 0
0x140009801  mov     rsi, rdx
0x140009804  lea     r8, [rsp+48h+IsDirectory]; IsDirectory
0x140009809  mov     rdx, [rdx+18h]; Instance
0x14000980d  mov     rdi, rcx
0x140009810  mov     rcx, rax; FileObject
0x140009813  mov     rbx, r9
0x140009816  call    cs:__imp_FltIsDirectory
0x14000981d  nop     dword ptr [rax+rax+00h]
0x140009822  mov     ebp, eax
0x140009824  test    eax, eax
0x140009826  js      short loc_140009894
0x140009828  test    rbx, rbx
0x14000982b  jz      short loc_140009894
0x14000982d  cmp     [rsp+48h+IsDirectory], 0
0x140009832  jnz     short loc_140009894
0x140009834  mov     r8, [rbx]
0x140009837  test    r8, r8
0x14000983a  jz      short loc_140009860
0x14000983c  cmp     [r8], r8
0x14000983f  jz      short loc_140009879
0x140009841  mov     rcx, [rsi+8]
0x140009845  mov     rdx, rdi
0x140009848  call    cs:__imp_FltRemoveOpenReparseEntry
0x14000984f  nop     dword ptr [rax+rax+00h]
0x140009854  mov     rax, [rbx]
0x140009857  mov     [rax+8], rax
0x14000985b  mov     [rax], rax
0x14000985e  jmp     short loc_140009879
0x140009860  mov     rcx, [rdi+10h]
0x140009864  mov     eax, [rbx+38h]
0x140009867  or      [rcx+20h], eax
0x14000986a  mov     rcx, rdi; Data
0x14000986d  call    cs:__imp_FltSetCallbackDataDirty
0x140009874  nop     dword ptr [rax+rax+00h]
0x140009879  mov     rcx, [rsi+18h]; InitiatingInstance
0x14000987d  mov     rdx, rdi; CallbackData
0x140009880  call    cs:__imp_FltReissueSynchronousIo
0x140009887  nop     dword ptr [rax+rax+00h]
0x14000988c  mov     rax, [rsp+48h+arg_20]
0x140009891  mov     byte ptr [rax], 1
0x140009894  mov     eax, ebp
0x140009896  add     rsp, 28h
0x14000989a  pop     rdi
0x14000989b  pop     rsi
0x14000989c  pop     rbp
0x14000989d  pop     rbx
0x14000989e  retn
```
