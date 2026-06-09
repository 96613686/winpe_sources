# MSMSecInitializeAuthMgrHandleTable(void * *)

- ea: `0x180050c20`
- end: `0x180050cdf`
- name: `?MSMSecInitializeAuthMgrHandleTable@@YAKPEAPEAX@Z`
- size: `191`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003ae08`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180050c20`

## import_xrefs

- `MobileNetworking!HtCreateHandleTable` at `0x180050c68`
- `MobileNetworking!HtCreateHandleTable` at `0x180050c68`

## pseudocode

```c
__int64 __fastcall MSMSecInitializeAuthMgrHandleTable(void **a1)
{
  unsigned int HandleTable; // eax
  unsigned int v3; // ebx
  PVOID *v4; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 31, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids);
  HandleTable = HtCreateHandleTable(0, 2048, a1);
  v3 = HandleTable;
  if ( !HandleTable )
    goto LABEL_8;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 32, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids, HandleTable);
LABEL_8:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x100) != 0 )
    WPP_SF_d(v4[7], 33, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180050c20  mov     [rsp+arg_0], rbx
0x180050c25  push    rdi
0x180050c26  sub     rsp, 20h
0x180050c2a  mov     rbx, rcx
0x180050c2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180050c34  lea     rdi, WPP_GLOBAL_Control
0x180050c3b  cmp     rcx, rdi
0x180050c3e  jz      short loc_180050C5E
0x180050c40  test    dword ptr [rcx+44h], 100h
0x180050c47  jz      short loc_180050C5E
0x180050c49  mov     rcx, [rcx+38h]
0x180050c4d  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x180050c54  mov     edx, 1Fh
0x180050c59  call    WPP_SF_
0x180050c5e  mov     r8, rbx
0x180050c61  mov     edx, 800h
0x180050c66  xor     ecx, ecx
0x180050c68  call    cs:__imp_HtCreateHandleTable
0x180050c6f  nop     dword ptr [rax+rax+00h]
0x180050c74  mov     ebx, eax
0x180050c76  test    eax, eax
0x180050c78  jz      short loc_180050CA4
0x180050c7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180050c81  cmp     rcx, rdi
0x180050c84  jz      short loc_180050CD1
0x180050c86  test    byte ptr [rcx+44h], 1
0x180050c8a  jz      short loc_180050CAB
0x180050c8c  mov     rcx, [rcx+38h]
0x180050c90  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x180050c97  mov     edx, 20h ; ' '
0x180050c9c  mov     r9d, eax
0x180050c9f  call    WPP_SF_d
0x180050ca4  mov     rcx, cs:WPP_GLOBAL_Control
0x180050cab  cmp     rcx, rdi
0x180050cae  jz      short loc_180050CD1
0x180050cb0  test    dword ptr [rcx+44h], 100h
0x180050cb7  jz      short loc_180050CD1
0x180050cb9  mov     rcx, [rcx+38h]
0x180050cbd  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x180050cc4  mov     edx, 21h ; '!'
0x180050cc9  mov     r9d, ebx
0x180050ccc  call    WPP_SF_d
0x180050cd1  mov     eax, ebx
0x180050cd3  mov     rbx, [rsp+28h+arg_0]
0x180050cd8  add     rsp, 20h
0x180050cdc  pop     rdi
0x180050cdd  retn
```
