# WofPreWriteCallback

- ea: `0x140008e30`
- end: `0x140008fc1`
- name: `WofPreWriteCallback`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140007670`
- `0x140008e30`
- `0x14000ba78`
- `0x140034f50`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x140008ea4`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140008ea4`
- `FLTMGR!FltGetStreamContext` at `0x140008e60`
- `FLTMGR!FltGetStreamContext` at `0x140008e60`
- `FLTMGR!FltReleaseContext` at `0x140008eeb`
- `FLTMGR!FltReleaseContext` at `0x140008f23`
- `FLTMGR!FltReleaseContext` at `0x140008fa0`
- `FLTMGR!FltReleaseContext` at `0x140008eeb`
- `FLTMGR!FltReleaseContext` at `0x140008f23`
- `FLTMGR!FltReleaseContext` at `0x140008fa0`

## pseudocode

```c
__int64 __fastcall WofPreWriteCallback(__int64 a1, __int64 a2, _QWORD *a3)
{
  struct _FILE_OBJECT *v4; // rdx
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rbx
  __int64 result; // rax
  int v10; // edx
  int IsDataInFilesystem; // ebp
  __int64 v12; // rax
  __int64 v13; // rcx
  signed __int32 v14[8]; // [rsp+0h] [rbp-48h] BYREF
  char v15; // [rsp+58h] [rbp+10h] BYREF
  PFLT_CONTEXT Context; // [rsp+68h] [rbp+20h] BYREF

  Context = 0;
  v4 = *(struct _FILE_OBJECT **)(a2 + 32);
  v15 = 0;
  if ( FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), v4, &Context) < 0 )
  {
    v7 = 10 * ((*(_QWORD *)(*(_QWORD *)(a2 + 32) + 24LL) >> 12) % (unsigned __int64)(unsigned int)dword_140018660);
    do
    {
      v8 = qword_1400186A0[v7];
      _InterlockedOr(v14, 0);
    }
    while ( !ExAcquireRundownProtection((PEX_RUNDOWN_REF)v8) );
    *a3 = v8 | 1;
    return 0;
  }
  IsDataInFilesystem = WofIsDataInFilesystemEx(Context, a2, &v15, 0);
  if ( IsDataInFilesystem < 0 )
  {
    FltReleaseContext(Context);
    result = 4;
    *(_DWORD *)(a1 + 24) = IsDataInFilesystem;
    return result;
  }
  if ( v15 )
  {
LABEL_15:
    FltReleaseContext(Context);
    *a3 = WofAcquireFileSystemRundown(*(_QWORD *)(a2 + 32)) | 1;
    return 0;
  }
  if ( (!*(_QWORD *)(a2 + 40) || (**(_DWORD **)(a1 + 16) & 2) == 0) && (*((_DWORD *)Context + 2) & 0x50) == 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 4;
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        2,
        26,
        (__int64)WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids,
        *(_QWORD *)(a2 + 32));
    }
    goto LABEL_15;
  }
  FltReleaseContext(Context);
  v12 = *(_QWORD *)(a1 + 16);
  *(_DWORD *)(a1 + 24) = 0;
  v13 = *(unsigned int *)(v12 + 24);
  result = 4;
  *(_QWORD *)(a1 + 32) = v13;
  return result;
}

```

## disassembly

```asm
0x140008e30  mov     [rsp+arg_0], rbx
0x140008e35  push    rbp
0x140008e36  push    rsi
0x140008e37  push    rdi
0x140008e38  sub     rsp, 30h
0x140008e3c  mov     rbx, rdx
0x140008e3f  mov     [rsp+48h+Context], 0
0x140008e48  mov     rdx, [rdx+20h]; FileObject
0x140008e4c  mov     rsi, r8
0x140008e4f  mov     rdi, rcx
0x140008e52  mov     [rsp+48h+arg_8], 0
0x140008e57  lea     r8, [rsp+48h+Context]; Context
0x140008e5c  mov     rcx, [rbx+18h]; Instance
0x140008e60  call    cs:__imp_FltGetStreamContext
0x140008e67  nop     dword ptr [rax+rax+00h]
0x140008e6c  test    eax, eax
0x140008e6e  jns     short loc_140008ECB
0x140008e70  mov     rax, [rbx+20h]
0x140008e74  lea     rbp, qword_1400186A0
0x140008e7b  mov     ecx, cs:dword_140018660
0x140008e81  xor     edx, edx
0x140008e83  mov     rax, [rax+18h]
0x140008e87  shr     rax, 0Ch
0x140008e8b  div     rcx
0x140008e8e  mov     eax, edx
0x140008e90  lea     rdi, [rax+rax*4]
0x140008e94  add     rdi, rdi
0x140008e97  mov     rbx, [rbp+rdi*8+0]
0x140008e9c  lock or [rsp+48h+var_48], 0
0x140008ea1  mov     rcx, rbx; RunRef
0x140008ea4  call    cs:__imp_ExAcquireRundownProtection
0x140008eab  nop     dword ptr [rax+rax+00h]
0x140008eb0  test    al, al
0x140008eb2  jz      short loc_140008E97
0x140008eb4  or      rbx, 1
0x140008eb8  mov     [rsi], rbx
0x140008ebb  xor     eax, eax
0x140008ebd  mov     rbx, [rsp+48h+arg_0]
0x140008ec2  add     rsp, 30h
0x140008ec6  pop     rdi
0x140008ec7  pop     rsi
0x140008ec8  pop     rbp
0x140008ec9  retn
0x140008ecb  mov     rcx, [rsp+48h+Context]
0x140008ed0  lea     r8, [rsp+48h+arg_8]
0x140008ed5  xor     r9d, r9d
0x140008ed8  mov     rdx, rbx
0x140008edb  call    WofIsDataInFilesystemEx
0x140008ee0  mov     ebp, eax
0x140008ee2  test    eax, eax
0x140008ee4  jns     short loc_140008F01
0x140008ee6  mov     rcx, [rsp+48h+Context]; Context
0x140008eeb  call    cs:__imp_FltReleaseContext
0x140008ef2  nop     dword ptr [rax+rax+00h]
0x140008ef7  mov     eax, 4
0x140008efc  mov     [rdi+18h], ebp
0x140008eff  jmp     short loc_140008EBD
0x140008f01  cmp     [rsp+48h+arg_8], 0
0x140008f06  jnz     loc_140008F9B
0x140008f0c  cmp     qword ptr [rbx+28h], 0
0x140008f11  jz      short loc_140008F4B
0x140008f13  mov     rax, [rdi+10h]
0x140008f17  mov     ecx, [rax]
0x140008f19  test    cl, 2
0x140008f1c  jz      short loc_140008F4B
0x140008f1e  mov     rcx, [rsp+48h+Context]; Context
0x140008f23  call    cs:__imp_FltReleaseContext
0x140008f2a  nop     dword ptr [rax+rax+00h]
0x140008f2f  mov     rax, [rdi+10h]
0x140008f33  mov     dword ptr [rdi+18h], 0
0x140008f3a  mov     ecx, [rax+18h]
0x140008f3d  mov     eax, 4
0x140008f42  mov     [rdi+20h], rcx
0x140008f46  jmp     loc_140008EBD
0x140008f4b  mov     rax, [rsp+48h+Context]
0x140008f50  mov     ecx, [rax+8]
0x140008f53  test    cl, 50h
0x140008f56  jnz     short loc_140008F1E
0x140008f58  lea     rax, WPP_RECORDER_INITIALIZED
0x140008f5f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140008f66  jz      short loc_140008F9B
0x140008f68  mov     rax, [rbx+20h]
0x140008f6c  mov     r9d, 1Ah
0x140008f72  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f79  mov     r8d, 2
0x140008f7f  mov     [rsp+48h+var_20], rax
0x140008f84  mov     dl, 4
0x140008f86  lea     rax, WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids
0x140008f8d  mov     [rsp+48h+var_28], rax
0x140008f92  mov     rcx, [rcx+40h]
0x140008f96  call    WPP_RECORDER_SF_q
0x140008f9b  mov     rcx, [rsp+48h+Context]; Context
0x140008fa0  call    cs:__imp_FltReleaseContext
0x140008fa7  nop     dword ptr [rax+rax+00h]
0x140008fac  mov     rcx, [rbx+20h]
0x140008fb0  call    WofAcquireFileSystemRundown
0x140008fb5  or      rax, 1
0x140008fb9  mov     [rsi], rax
0x140008fbc  jmp     loc_140008EBB
```
