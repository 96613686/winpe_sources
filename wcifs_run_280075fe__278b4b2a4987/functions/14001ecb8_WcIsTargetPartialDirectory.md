# WcIsTargetPartialDirectory

- ea: `0x14001ecb8`
- end: `0x14001ef48`
- name: `WcIsTargetPartialDirectory`
- size: `656`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, loader_planting`

## callers

- `0x14001f1c8`

## callees

- `0x140001bc8`
- `0x140001fd0`
- `0x140001ffc`
- `0x1400048a4`
- `0x14001eadc`
- `0x14001ecb8`
- `0x140029608`
- `0x14002cae8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14001ef1b`
- `ntoskrnl!ObfDereferenceObject` at `0x14001ef1b`
- `FLTMGR!FltClose` at `0x14001ef06`
- `FLTMGR!FltClose` at `0x14001ef06`
- `FLTMGR!FltReleaseContext` at `0x14001eedd`
- `FLTMGR!FltReleaseContext` at `0x14001eef1`
- `FLTMGR!FltReleaseContext` at `0x14001eedd`
- `FLTMGR!FltReleaseContext` at `0x14001eef1`

## pseudocode

```c
__int64 __fastcall WcIsTargetPartialDirectory(
        PFLT_INSTANCE Instance,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        __int64 a4,
        void *a5,
        _BYTE *a6)
{
  int v9; // eax
  PFLT_CONTEXT v10; // rsi
  PFLT_CONTEXT v11; // rdi
  int v12; // eax
  int v13; // edx
  int IsDirectoryEmpty; // ebx
  int SetContextFileObject; // eax
  int v16; // edx
  int v18; // [rsp+20h] [rbp-79h]
  PFLT_CONTEXT Context; // [rsp+78h] [rbp-21h] BYREF
  PFLT_CONTEXT v20; // [rsp+80h] [rbp-19h] BYREF
  PVOID Object; // [rsp+88h] [rbp-11h] BYREF
  HANDLE FileHandle; // [rsp+90h] [rbp-9h] BYREF
  bool v23; // [rsp+F8h] [rbp+5Fh] BYREF

  FileHandle = 0;
  Object = 0;
  v9 = *(_DWORD *)(a2 + 36);
  v10 = 0;
  v11 = 0;
  Context = 0;
  v20 = 0;
  v23 = 0;
  v12 = WcOpenAsReparsePoint(a3, a5, a4, Instance, 0x80u, v9, &FileHandle, (PFILE_OBJECT *)&Object, &v23, 0, 0, 0, 0);
  IsDirectoryEmpty = v12;
  if ( v12 != -1073741772 && v23 )
  {
    if ( v12 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = 2;
        WPP_RECORDER_SF_sDZd(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          13,
          185,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          135,
          (__int64)a3,
          v12);
      }
      goto LABEL_23;
    }
    SetContextFileObject = WcGetSetContextFileObject(Instance, (PFILE_OBJECT)Object, a2, 1, v18, &v20, &Context);
    IsDirectoryEmpty = SetContextFileObject;
    if ( SetContextFileObject < 0 )
    {
      if ( SetContextFileObject != -1073741195 )
      {
        v10 = Context;
        v11 = v20;
        goto LABEL_19;
      }
    }
    else if ( SetContextFileObject != 260 )
    {
      v10 = Context;
      v11 = v20;
      if ( WcIsPlaceHolderDirectory((__int64)v20, (__int64)Context)
        && !(unsigned __int8)WcIsExpanded(v11)
        && (unsigned __int8)WcIsSourcedStream(v10) )
      {
        IsDirectoryEmpty = WcIsDirectoryEmpty(Instance, (PFILE_OBJECT)Object);
        if ( IsDirectoryEmpty >= 0 )
        {
          *a6 = 1;
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = 2;
          WPP_RECORDER_SF_sDZd(
            WPP_GLOBAL_Control->DeviceExtension,
            v16,
            13,
            186,
            (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
            177,
            (__int64)a3,
            IsDirectoryEmpty);
        }
        goto LABEL_19;
      }
      goto LABEL_18;
    }
    v10 = Context;
    v11 = v20;
  }
  IsDirectoryEmpty = 0;
LABEL_18:
  *a6 = 0;
LABEL_19:
  if ( v10 )
    FltReleaseContext(v10);
  if ( v11 )
    FltReleaseContext(v11);
LABEL_23:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)IsDirectoryEmpty;
}

```

## disassembly

```asm
0x14001ecb8  push    rbp
0x14001ecba  push    rbx
0x14001ecbb  push    rsi
0x14001ecbc  push    rdi
0x14001ecbd  push    r12
0x14001ecbf  push    r13
0x14001ecc1  push    r14
0x14001ecc3  push    r15
0x14001ecc5  lea     rbp, [rsp-0Fh]
0x14001ecca  sub     rsp, 0A8h
0x14001ecd1  xor     r13d, r13d
0x14001ecd4  lea     rax, [rbp+47h+arg_8]
0x14001ecd8  mov     [rsp+0E0h+var_80], r13
0x14001ecdd  mov     r10, r9
0x14001ece0  mov     [rsp+0E0h+var_88], r13
0x14001ece5  mov     r12, r8
0x14001ece8  mov     [rsp+0E0h+var_90], r13
0x14001eced  mov     r15, rdx
0x14001ecf0  mov     [rsp+0E0h+var_98], r13
0x14001ecf5  mov     r14, rcx
0x14001ecf8  mov     [rsp+0E0h+var_A0], rax
0x14001ecfd  mov     r9, rcx
0x14001ed00  lea     rax, [rbp+47h+Object]
0x14001ed04  mov     [rbp+47h+FileHandle], r13
0x14001ed08  mov     [rsp+0E0h+var_A8], rax
0x14001ed0d  mov     r8, r10
0x14001ed10  lea     rax, [rbp+47h+FileHandle]
0x14001ed14  mov     [rbp+47h+Object], r13
0x14001ed18  mov     [rsp+0E0h+var_B0], rax
0x14001ed1d  mov     rcx, r12
0x14001ed20  mov     eax, [rdx+24h]
0x14001ed23  mov     esi, r13d
0x14001ed26  mov     rdx, [rbp+47h+arg_20]
0x14001ed2a  mov     edi, r13d
0x14001ed2d  mov     dword ptr [rsp+0E0h+var_B8], eax
0x14001ed31  mov     [rsp+0E0h+var_C0], 80h; int
0x14001ed39  mov     [rbp+47h+var_70], r13b
0x14001ed3d  mov     [rbp+47h+Context], r13
0x14001ed41  mov     [rbp+47h+var_60], r13
0x14001ed45  mov     [rbp+47h+arg_8], r13b
0x14001ed49  call    WcOpenAsReparsePoint
0x14001ed4e  mov     ebx, eax
0x14001ed50  cmp     eax, 0C0000034h
0x14001ed55  jz      loc_14001EECB
0x14001ed5b  cmp     [rbp+47h+arg_8], r13b
0x14001ed5f  jz      loc_14001EECB
0x14001ed65  test    eax, eax
0x14001ed67  jns     short loc_14001EDC7
0x14001ed69  lea     rax, WPP_RECORDER_INITIALIZED
0x14001ed70  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001ed77  jz      loc_14001EEFD
0x14001ed7d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ed84  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001ed8b  mov     dword ptr [rsp+0E0h+var_A0], ebx
0x14001ed8f  lea     r8d, [r13+0Dh]
0x14001ed93  mov     [rsp+0E0h+var_A8], r12
0x14001ed98  mov     r9d, 0B9h
0x14001ed9e  mov     dword ptr [rsp+0E0h+var_B0], 1F87h
0x14001eda6  mov     dl, 2
0x14001eda8  mov     rcx, [rcx+40h]
0x14001edac  mov     [rsp+0E0h+var_B8], rax
0x14001edb1  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001edb8  mov     qword ptr [rsp+0E0h+var_C0], rax
0x14001edbd  call    WPP_RECORDER_SF_sDZd
0x14001edc2  jmp     loc_14001EEFD
0x14001edc7  mov     rdx, [rbp+47h+Object]; FileObject
0x14001edcb  lea     rax, [rbp+47h+Context]
0x14001edcf  mov     [rsp+0E0h+var_B0], rax; __int64
0x14001edd4  mov     r9d, 1
0x14001edda  lea     rax, [rbp+47h+var_60]
0x14001edde  mov     r8, r15
0x14001ede1  mov     rcx, r14; Instance
0x14001ede4  mov     [rsp+0E0h+var_B8], rax; __int64
0x14001ede9  call    WcGetSetContextFileObject
0x14001edee  mov     ebx, eax
0x14001edf0  test    eax, eax
0x14001edf2  js      loc_14001EEBC
0x14001edf8  cmp     eax, 104h
0x14001edfd  jz      loc_14001EEC3
0x14001ee03  mov     rsi, [rbp+47h+Context]
0x14001ee07  mov     rdi, [rbp+47h+var_60]
0x14001ee0b  mov     rdx, rsi
0x14001ee0e  mov     rcx, rdi
0x14001ee11  call    WcIsPlaceHolderDirectory
0x14001ee16  test    al, al
0x14001ee18  jz      loc_14001EECE
0x14001ee1e  mov     rcx, rdi
0x14001ee21  call    WcIsExpanded
0x14001ee26  test    al, al
0x14001ee28  jnz     loc_14001EECE
0x14001ee2e  mov     rcx, rsi
0x14001ee31  call    WcIsSourcedStream
0x14001ee36  test    al, al
0x14001ee38  jz      loc_14001EECE
0x14001ee3e  mov     rdx, [rbp+47h+Object]; FileObject
0x14001ee42  lea     r8, [rbp+47h+var_70]
0x14001ee46  mov     rcx, r14; Instance
0x14001ee49  call    WcIsDirectoryEmpty
0x14001ee4e  mov     ebx, eax
0x14001ee50  test    eax, eax
0x14001ee52  jns     short loc_14001EEAD
0x14001ee54  lea     rax, WPP_RECORDER_INITIALIZED
0x14001ee5b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001ee62  jz      short loc_14001EED5
0x14001ee64  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ee6b  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001ee72  mov     dword ptr [rsp+0E0h+var_A0], ebx
0x14001ee76  mov     r9d, 0BAh
0x14001ee7c  mov     [rsp+0E0h+var_A8], r12
0x14001ee81  mov     r8d, 0Dh
0x14001ee87  mov     dword ptr [rsp+0E0h+var_B0], 1FB1h
0x14001ee8f  mov     dl, 2
0x14001ee91  mov     rcx, [rcx+40h]
0x14001ee95  mov     [rsp+0E0h+var_B8], rax
0x14001ee9a  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001eea1  mov     qword ptr [rsp+0E0h+var_C0], rax
0x14001eea6  call    WPP_RECORDER_SF_sDZd
0x14001eeab  jmp     short loc_14001EED5
0x14001eead  cmp     [rbp+47h+var_70], r13b
0x14001eeb1  mov     rax, [rbp+47h+arg_28]
0x14001eeb5  setz    cl
0x14001eeb8  mov     [rax], cl
0x14001eeba  jmp     short loc_14001EED5
0x14001eebc  cmp     eax, 0C0000275h
0x14001eec1  jnz     short loc_14001EF3E
0x14001eec3  mov     rsi, [rbp+47h+Context]
0x14001eec7  mov     rdi, [rbp+47h+var_60]
0x14001eecb  mov     ebx, r13d
0x14001eece  mov     rax, [rbp+47h+arg_28]
0x14001eed2  mov     [rax], r13b
0x14001eed5  test    rsi, rsi
0x14001eed8  jz      short loc_14001EEE9
0x14001eeda  mov     rcx, rsi; Context
0x14001eedd  call    cs:__imp_FltReleaseContext
0x14001eee4  nop     dword ptr [rax+rax+00h]
0x14001eee9  test    rdi, rdi
0x14001eeec  jz      short loc_14001EEFD
0x14001eeee  mov     rcx, rdi; Context
0x14001eef1  call    cs:__imp_FltReleaseContext
0x14001eef8  nop     dword ptr [rax+rax+00h]
0x14001eefd  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x14001ef01  test    rcx, rcx
0x14001ef04  jz      short loc_14001EF12
0x14001ef06  call    cs:__imp_FltClose
0x14001ef0d  nop     dword ptr [rax+rax+00h]
0x14001ef12  mov     rcx, [rbp+47h+Object]; Object
0x14001ef16  test    rcx, rcx
0x14001ef19  jz      short loc_14001EF27
0x14001ef1b  call    cs:__imp_ObfDereferenceObject
0x14001ef22  nop     dword ptr [rax+rax+00h]
0x14001ef27  mov     eax, ebx
0x14001ef29  add     rsp, 0A8h
0x14001ef30  pop     r15
0x14001ef32  pop     r14
0x14001ef34  pop     r13
0x14001ef36  pop     r12
0x14001ef38  pop     rdi
0x14001ef39  pop     rsi
0x14001ef3a  pop     rbx
0x14001ef3b  pop     rbp
0x14001ef3c  retn
0x14001ef3e  mov     rsi, [rbp+47h+Context]
0x14001ef42  mov     rdi, [rbp+47h+var_60]
0x14001ef46  jmp     short loc_14001EED5
```
