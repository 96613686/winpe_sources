# WcOpenPlaceHolder

- ea: `0x14002d5f8`
- end: `0x14002d78a`
- name: `WcOpenPlaceHolder`
- size: `402`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x140018e28`
- `0x14001c688`
- `0x140026210`
- `0x140027854`
- `0x140027f24`
- `0x1400343c0`

## callees

- `0x1400048a4`
- `0x140007c60`
- `0x14002d5f8`
- `0x14002d790`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14002d758`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d758`
- `FLTMGR!FltClose` at `0x14002d743`
- `FLTMGR!FltClose` at `0x14002d743`

## pseudocode

```c
__int64 __fastcall WcOpenPlaceHolder(
        struct _FLT_INSTANCE *a1,
        struct _UNICODE_STRING *a2,
        ULONG a3,
        int a4,
        void **a5,
        PVOID *a6,
        _BYTE *a7)
{
  int v8; // edx
  int v9; // esi
  void *v10; // rcx
  void *FileHandle; // [rsp+50h] [rbp-41h] BYREF
  PVOID Object; // [rsp+58h] [rbp-39h] BYREF
  __int64 v14[2]; // [rsp+60h] [rbp-31h] BYREF
  _QWORD v15[2]; // [rsp+70h] [rbp-21h] BYREF
  int v16; // [rsp+80h] [rbp-11h]
  int v17; // [rsp+84h] [rbp-Dh]
  __int128 v18; // [rsp+88h] [rbp-9h]
  __int64 v19; // [rsp+98h] [rbp+7h]

  v15[0] = v14;
  v15[1] = v14;
  v14[0] = (__int64)v15;
  v14[1] = (__int64)v15;
  v16 = a4;
  v19 = 48;
  FileHandle = 0;
  Object = 0;
  v18 = 0;
  v17 = -2147483644;
  v9 = WcOpenReparsePoint(a1, a2, 0, 0, 0x80u, a3, 7u, (PVOID **)v14, &FileHandle, (PFILE_OBJECT *)&Object);
  if ( v9 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_sDZd(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        10,
        148,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        110,
        (__int64)a2,
        v9);
    }
    v10 = FileHandle;
    goto LABEL_9;
  }
  if ( a7 )
    *a7 = v17 & 1;
  v10 = 0;
  *a5 = FileHandle;
  FileHandle = 0;
  if ( a6 )
  {
    *a6 = Object;
    Object = 0;
LABEL_9:
    if ( v10 )
      FltClose(v10);
  }
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14002d5f8  mov     [rsp-8+arg_10], rbx
0x14002d5fd  push    rbp
0x14002d5fe  push    rsi
0x14002d5ff  push    rdi
0x14002d600  push    r14
0x14002d602  push    r15
0x14002d604  lea     rbp, [rsp-1Fh]
0x14002d609  sub     rsp, 0B0h
0x14002d610  mov     rax, cs:__security_cookie
0x14002d617  xor     rax, rsp
0x14002d61a  mov     [rbp+3Fh+var_30], rax
0x14002d61e  mov     r14, [rbp+3Fh+arg_20]
0x14002d622  lea     rax, [rbp+3Fh+var_70]
0x14002d626  mov     rdi, [rbp+3Fh+arg_28]
0x14002d62a  xorps   xmm0, xmm0
0x14002d62d  mov     rbx, [rbp+3Fh+arg_30]
0x14002d631  mov     r15, rdx
0x14002d634  mov     [rbp+3Fh+var_60], rax
0x14002d638  lea     rax, [rbp+3Fh+var_70]
0x14002d63c  mov     [rbp+3Fh+var_58], rax
0x14002d640  lea     rax, [rbp+3Fh+var_60]
0x14002d644  mov     [rbp+3Fh+var_70], rax
0x14002d648  lea     rax, [rbp+3Fh+var_60]
0x14002d64c  mov     [rbp+3Fh+var_68], rax
0x14002d650  lea     rax, [rbp+3Fh+Object]
0x14002d654  mov     [rsp+0D0h+FileObject], rax; FileObject
0x14002d659  lea     rax, [rbp+3Fh+var_80]
0x14002d65d  mov     [rsp+0D0h+FileHandle], rax; FileHandle
0x14002d662  lea     rax, [rbp+3Fh+var_70]
0x14002d666  mov     [rsp+0D0h+var_98], rax; __int64
0x14002d66b  mov     [rsp+0D0h+var_A0], 7; ULONG
0x14002d673  mov     [rsp+0D0h+var_A8], r8d; ULONG
0x14002d678  xor     r8d, r8d
0x14002d67b  mov     [rbp+3Fh+var_50], r9d
0x14002d67f  xor     r9d, r9d
0x14002d682  mov     [rbp+3Fh+var_38], 30h ; '0'
0x14002d68a  mov     [rbp+3Fh+var_80], 0
0x14002d692  mov     [rbp+3Fh+Object], 0
0x14002d69a  movups  [rbp+3Fh+var_48], xmm0
0x14002d69e  mov     [rbp+3Fh+var_4C], 80000004h
0x14002d6a5  mov     [rsp+0D0h+DesiredAccess], 80h; DesiredAccess
0x14002d6ad  call    WcOpenReparsePoint
0x14002d6b2  mov     esi, eax
0x14002d6b4  test    eax, eax
0x14002d6b6  jns     short loc_14002D715
0x14002d6b8  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d6bf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d6c6  jz      short loc_14002D70F
0x14002d6c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d6cf  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002d6d6  mov     dword ptr [rsp+0D0h+FileHandle], esi
0x14002d6da  mov     r9d, 94h
0x14002d6e0  mov     [rsp+0D0h+var_98], r15
0x14002d6e5  mov     r8d, 0Ah
0x14002d6eb  mov     [rsp+0D0h+var_A0], 156Eh
0x14002d6f3  mov     dl, 2
0x14002d6f5  mov     rcx, [rcx+40h]
0x14002d6f9  mov     qword ptr [rsp+0D0h+var_A8], rax
0x14002d6fe  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14002d705  mov     qword ptr [rsp+0D0h+DesiredAccess], rax
0x14002d70a  call    WPP_RECORDER_SF_sDZd
0x14002d70f  mov     rcx, [rbp+3Fh+var_80]
0x14002d713  jmp     short loc_14002D73E
0x14002d715  test    rbx, rbx
0x14002d718  jz      short loc_14002D721
0x14002d71a  mov     al, byte ptr [rbp+3Fh+var_4C]
0x14002d71d  and     al, 1
0x14002d71f  mov     [rbx], al
0x14002d721  mov     rax, [rbp+3Fh+var_80]
0x14002d725  xor     ecx, ecx; FileHandle
0x14002d727  mov     [r14], rax
0x14002d72a  mov     [rbp+3Fh+var_80], rcx
0x14002d72e  test    rdi, rdi
0x14002d731  jz      short loc_14002D74F
0x14002d733  mov     rax, [rbp+3Fh+Object]
0x14002d737  mov     [rdi], rax
0x14002d73a  mov     [rbp+3Fh+Object], rcx
0x14002d73e  test    rcx, rcx
0x14002d741  jz      short loc_14002D74F
0x14002d743  call    cs:__imp_FltClose
0x14002d74a  nop     dword ptr [rax+rax+00h]
0x14002d74f  mov     rcx, [rbp+3Fh+Object]; Object
0x14002d753  test    rcx, rcx
0x14002d756  jz      short loc_14002D764
0x14002d758  call    cs:__imp_ObfDereferenceObject
0x14002d75f  nop     dword ptr [rax+rax+00h]
0x14002d764  mov     eax, esi
0x14002d766  mov     rcx, [rbp+3Fh+var_30]
0x14002d76a  xor     rcx, rsp; StackCookie
0x14002d76d  call    __security_check_cookie
0x14002d772  mov     rbx, [rsp+0D0h+arg_10]
0x14002d77a  add     rsp, 0B0h
0x14002d781  pop     r15
0x14002d783  pop     r14
0x14002d785  pop     rdi
0x14002d786  pop     rsi
0x14002d787  pop     rbp
0x14002d788  retn
```
