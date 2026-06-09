# WcOpenPlaceHolder

- ea: `0x14002d648`
- end: `0x14002d7da`
- name: `WcOpenPlaceHolder`
- size: `402`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *, __int64, ULONG, int, void **, PVOID *, _BYTE *)`
- caller_count: `6`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x140018e28`
- `0x14001c688`
- `0x140026260`
- `0x1400278a4`
- `0x140027f74`
- `0x140034410`

## callees

- `0x1400048a4`
- `0x140007c60`
- `0x14002d648`
- `0x14002d7e0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14002d7a8`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d7a8`
- `FLTMGR!FltClose` at `0x14002d793`
- `FLTMGR!FltClose` at `0x14002d793`

## pseudocode

```c
__int64 __fastcall WcOpenPlaceHolder(
        struct _FLT_INSTANCE *a1,
        __int64 a2,
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
  v9 = WcOpenReparsePoint(a1, 0x80u, a3, 7u, (__int64)v14, &FileHandle, (PFILE_OBJECT *)&Object);
  if ( v9 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_sDZd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v8,
        10,
        148,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        110,
        a2,
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
0x14002d648  mov     [rsp-8+arg_10], rbx
0x14002d64d  push    rbp
0x14002d64e  push    rsi
0x14002d64f  push    rdi
0x14002d650  push    r14
0x14002d652  push    r15
0x14002d654  lea     rbp, [rsp-1Fh]
0x14002d659  sub     rsp, 0B0h
0x14002d660  mov     rax, cs:__security_cookie
0x14002d667  xor     rax, rsp
0x14002d66a  mov     [rbp+3Fh+var_30], rax
0x14002d66e  mov     r14, [rbp+3Fh+arg_20]
0x14002d672  lea     rax, [rbp+3Fh+var_70]
0x14002d676  mov     rdi, [rbp+3Fh+arg_28]
0x14002d67a  xorps   xmm0, xmm0
0x14002d67d  mov     rbx, [rbp+3Fh+arg_30]
0x14002d681  mov     r15, rdx
0x14002d684  mov     [rbp+3Fh+var_60], rax
0x14002d688  lea     rax, [rbp+3Fh+var_70]
0x14002d68c  mov     [rbp+3Fh+var_58], rax
0x14002d690  lea     rax, [rbp+3Fh+var_60]
0x14002d694  mov     [rbp+3Fh+var_70], rax
0x14002d698  lea     rax, [rbp+3Fh+var_60]
0x14002d69c  mov     [rbp+3Fh+var_68], rax
0x14002d6a0  lea     rax, [rbp+3Fh+Object]
0x14002d6a4  mov     [rsp+0D0h+FileObject], rax; FileObject
0x14002d6a9  lea     rax, [rbp+3Fh+var_80]
0x14002d6ad  mov     [rsp+0D0h+FileHandle], rax; FileHandle
0x14002d6b2  lea     rax, [rbp+3Fh+var_70]
0x14002d6b6  mov     [rsp+0D0h+var_98], rax; __int64
0x14002d6bb  mov     [rsp+0D0h+var_A0], 7; ULONG
0x14002d6c3  mov     [rsp+0D0h+var_A8], r8d; ULONG
0x14002d6c8  xor     r8d, r8d
0x14002d6cb  mov     [rbp+3Fh+var_50], r9d
0x14002d6cf  xor     r9d, r9d
0x14002d6d2  mov     [rbp+3Fh+var_38], 30h ; '0'
0x14002d6da  mov     [rbp+3Fh+var_80], 0
0x14002d6e2  mov     [rbp+3Fh+Object], 0
0x14002d6ea  movups  [rbp+3Fh+var_48], xmm0
0x14002d6ee  mov     [rbp+3Fh+var_4C], 80000004h
0x14002d6f5  mov     [rsp+0D0h+DesiredAccess], 80h; DesiredAccess
0x14002d6fd  call    WcOpenReparsePoint
0x14002d702  mov     esi, eax
0x14002d704  test    eax, eax
0x14002d706  jns     short loc_14002D765
0x14002d708  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d70f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d716  jz      short loc_14002D75F
0x14002d718  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002d71f  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002d726  mov     dword ptr [rsp+0D0h+FileHandle], esi
0x14002d72a  mov     r9d, 94h
0x14002d730  mov     [rsp+0D0h+var_98], r15
0x14002d735  mov     r8d, 0Ah
0x14002d73b  mov     [rsp+0D0h+var_A0], 156Eh
0x14002d743  mov     dl, 2
0x14002d745  mov     rcx, [rcx+40h]
0x14002d749  mov     qword ptr [rsp+0D0h+var_A8], rax
0x14002d74e  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14002d755  mov     qword ptr [rsp+0D0h+DesiredAccess], rax
0x14002d75a  call    WPP_RECORDER_SF_sDZd
0x14002d75f  mov     rcx, [rbp+3Fh+var_80]
0x14002d763  jmp     short loc_14002D78E
0x14002d765  test    rbx, rbx
0x14002d768  jz      short loc_14002D771
0x14002d76a  mov     al, byte ptr [rbp+3Fh+var_4C]
0x14002d76d  and     al, 1
0x14002d76f  mov     [rbx], al
0x14002d771  mov     rax, [rbp+3Fh+var_80]
0x14002d775  xor     ecx, ecx; FileHandle
0x14002d777  mov     [r14], rax
0x14002d77a  mov     [rbp+3Fh+var_80], rcx
0x14002d77e  test    rdi, rdi
0x14002d781  jz      short loc_14002D79F
0x14002d783  mov     rax, [rbp+3Fh+Object]
0x14002d787  mov     [rdi], rax
0x14002d78a  mov     [rbp+3Fh+Object], rcx
0x14002d78e  test    rcx, rcx
0x14002d791  jz      short loc_14002D79F
0x14002d793  call    cs:__imp_FltClose
0x14002d79a  nop     dword ptr [rax+rax+00h]
0x14002d79f  mov     rcx, [rbp+3Fh+Object]; Object
0x14002d7a3  test    rcx, rcx
0x14002d7a6  jz      short loc_14002D7B4
0x14002d7a8  call    cs:__imp_ObfDereferenceObject
0x14002d7af  nop     dword ptr [rax+rax+00h]
0x14002d7b4  mov     eax, esi
0x14002d7b6  mov     rcx, [rbp+3Fh+var_30]
0x14002d7ba  xor     rcx, rsp; StackCookie
0x14002d7bd  call    __security_check_cookie
0x14002d7c2  mov     rbx, [rsp+0D0h+arg_10]
0x14002d7ca  add     rsp, 0B0h
0x14002d7d1  pop     r15
0x14002d7d3  pop     r14
0x14002d7d5  pop     rdi
0x14002d7d6  pop     rsi
0x14002d7d7  pop     rbp
0x14002d7d8  retn
```
