# WofPreFsctlDeleteExternalBacking

- ea: `0x14003e820`
- end: `0x14003e993`
- name: `WofPreFsctlDeleteExternalBacking`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400346f0`

## callees

- `0x14000a914`
- `0x14000e3dc`
- `0x14000f3d4`
- `0x140034f50`
- `0x140036904`
- `0x14003e820`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003e95c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003e95c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003e922`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003e922`
- `FLTMGR!FltGetStreamContext` at `0x14003e855`
- `FLTMGR!FltGetStreamContext` at `0x14003e855`
- `FLTMGR!FltReleaseContext` at `0x14003e8e4`
- `FLTMGR!FltReleaseContext` at `0x14003e971`
- `FLTMGR!FltReleaseContext` at `0x14003e8e4`
- `FLTMGR!FltReleaseContext` at `0x14003e971`

## pseudocode

```c
__int64 __fastcall WofPreFsctlDeleteExternalBacking(__int64 a1, __int64 a2, __int64 a3)
{
  struct _FILE_OBJECT *v4; // rdx
  BOOLEAN IsAdmin; // al
  int v7; // edx
  PFLT_CONTEXT v8; // rcx
  int v10; // eax
  PFLT_CONTEXT v11; // rcx
  int v12; // eax
  PFLT_CONTEXT Context; // [rsp+48h] [rbp+18h] BYREF
  __int64 v14; // [rsp+50h] [rbp+20h] BYREF

  v14 = a3;
  Context = 0;
  v4 = *(struct _FILE_OBJECT **)(a2 + 32);
  LOBYTE(v14) = 0;
  if ( FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), v4, &Context) >= 0 )
  {
    if ( (int)WofIsDataInFilesystemEx(Context, a2, &v14, 0) >= 0 && !(_BYTE)v14 )
    {
      IsAdmin = WofUserIsAdmin();
      v8 = Context;
      if ( IsAdmin || *((_DWORD *)Context + 3) != 1 )
      {
        v10 = WofEnsureExtdFileContext(*(_QWORD *)Context);
        v8 = Context;
        if ( v10 < 0 )
        {
          *(_DWORD *)(a1 + 24) = v10;
          goto LABEL_9;
        }
        WofEnsureExtdFileContext(*(_QWORD *)Context);
        ExAcquireFastMutexUnsafe(*(PFAST_MUTEX *)(*(_QWORD *)Context + 16LL));
        v11 = Context;
        if ( (*((_DWORD *)Context + 2) & 4) != 0 )
        {
          v12 = 0;
        }
        else
        {
          v12 = WofInflateFile(a1, a2, Context, 1);
          v11 = Context;
        }
        *(_DWORD *)(a1 + 24) = v12;
        ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(*(_QWORD *)v11 + 16LL));
      }
      else
      {
        *(_DWORD *)(a1 + 24) = -1073741790;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_9:
          FltReleaseContext(v8);
          return 4;
        }
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v7,
          7,
          10,
          (__int64)WPP_dcfac5c580c33e55513b631fbc558444_Traceguids);
      }
      v8 = Context;
      goto LABEL_9;
    }
    FltReleaseContext(Context);
  }
  return 5;
}

```

## disassembly

```asm
0x14003e820  mov     [rsp-8+arg_0], rbx
0x14003e825  mov     [rsp-8+arg_18], rdi
0x14003e82a  mov     [rsp-8+arg_10], r8
0x14003e82f  push    rbp
0x14003e830  mov     rbp, rsp
0x14003e833  sub     rsp, 30h
0x14003e837  mov     rdi, rdx
0x14003e83a  mov     [rbp+Context], 0
0x14003e842  mov     rdx, [rdx+20h]; FileObject
0x14003e846  lea     r8, [rbp+Context]; Context
0x14003e84a  mov     rbx, rcx
0x14003e84d  mov     byte ptr [rbp+arg_10], 0
0x14003e851  mov     rcx, [rdi+18h]; Instance
0x14003e855  call    cs:__imp_FltGetStreamContext
0x14003e85c  nop     dword ptr [rax+rax+00h]
0x14003e861  test    eax, eax
0x14003e863  js      loc_14003E97D
0x14003e869  mov     rcx, [rbp+Context]
0x14003e86d  lea     r8, [rbp+arg_10]
0x14003e871  xor     r9d, r9d
0x14003e874  mov     rdx, rdi
0x14003e877  call    WofIsDataInFilesystemEx
0x14003e87c  test    eax, eax
0x14003e87e  js      loc_14003E96D
0x14003e884  cmp     byte ptr [rbp+arg_10], 0
0x14003e888  jnz     loc_14003E96D
0x14003e88e  call    WofUserIsAdmin
0x14003e893  mov     rcx, [rbp+Context]
0x14003e897  test    al, al
0x14003e899  jnz     short loc_14003E8FA
0x14003e89b  cmp     dword ptr [rcx+0Ch], 1
0x14003e89f  jnz     short loc_14003E8FA
0x14003e8a1  mov     dword ptr [rbx+18h], 0C0000022h
0x14003e8a8  lea     rax, WPP_RECORDER_INITIALIZED
0x14003e8af  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003e8b6  jz      short loc_14003E8E4
0x14003e8b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e8bf  lea     rax, WPP_dcfac5c580c33e55513b631fbc558444_Traceguids
0x14003e8c6  mov     r9d, 0Ah
0x14003e8cc  mov     [rsp+30h+var_10], rax
0x14003e8d1  mov     dl, 2
0x14003e8d3  mov     rcx, [rcx+40h]
0x14003e8d7  lea     r8d, [r9-3]
0x14003e8db  call    WPP_RECORDER_SF_
0x14003e8e0  mov     rcx, [rbp+Context]; Context
0x14003e8e4  call    cs:__imp_FltReleaseContext
0x14003e8eb  nop     dword ptr [rax+rax+00h]
0x14003e8f0  mov     eax, 4
0x14003e8f5  jmp     loc_14003E982
0x14003e8fa  mov     rcx, [rcx]
0x14003e8fd  call    WofEnsureExtdFileContext
0x14003e902  mov     rcx, [rbp+Context]
0x14003e906  test    eax, eax
0x14003e908  jns     short loc_14003E90F
0x14003e90a  mov     [rbx+18h], eax
0x14003e90d  jmp     short loc_14003E8E4
0x14003e90f  mov     rcx, [rcx]
0x14003e912  call    WofEnsureExtdFileContext
0x14003e917  mov     rax, [rbp+Context]
0x14003e91b  mov     rcx, [rax]
0x14003e91e  mov     rcx, [rcx+10h]; FastMutex
0x14003e922  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14003e929  nop     dword ptr [rax+rax+00h]
0x14003e92e  mov     rcx, [rbp+Context]
0x14003e932  mov     eax, [rcx+8]
0x14003e935  test    al, 4
0x14003e937  jnz     short loc_14003E950
0x14003e939  mov     r8, rcx
0x14003e93c  mov     r9b, 1
0x14003e93f  mov     rcx, rbx
0x14003e942  mov     rdx, rdi
0x14003e945  call    WofInflateFile
0x14003e94a  mov     rcx, [rbp+Context]
0x14003e94e  jmp     short loc_14003E952
0x14003e950  xor     eax, eax
0x14003e952  mov     [rbx+18h], eax
0x14003e955  mov     rcx, [rcx]
0x14003e958  mov     rcx, [rcx+10h]; FastMutex
0x14003e95c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003e963  nop     dword ptr [rax+rax+00h]
0x14003e968  jmp     loc_14003E8E0
0x14003e96d  mov     rcx, [rbp+Context]; Context
0x14003e971  call    cs:__imp_FltReleaseContext
0x14003e978  nop     dword ptr [rax+rax+00h]
0x14003e97d  mov     eax, 5
0x14003e982  mov     rbx, [rsp+30h+arg_0]
0x14003e987  mov     rdi, [rsp+30h+arg_18]
0x14003e98c  add     rsp, 30h
0x14003e990  pop     rbp
0x14003e991  retn
```
