# StartComTask

- ea: `0x140001e20`
- end: `0x140001ee9`
- name: `StartComTask`
- size: `201`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, int, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400012b0`

## callees

- `0x140001e20`
- `0x1400093b0`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall StartComTask(__int64 a1, __int64 a2, __int64 a3, int a4, int a5, _QWORD *a6)
{
  int v6; // eax
  unsigned int v8; // ebx

  v6 = (**(__int64 (__fastcall ***)(ComTaskMgrWnd *, __int64, __int64, __int64, int, int, _QWORD *))ComTaskMgrBase::s_pVirtualSingleton)(
         ComTaskMgrBase::s_pVirtualSingleton,
         a1,
         a2,
         a3,
         a4,
         a5,
         a6);
  if ( v6 >= 0 )
    return 0;
  v8 = (unsigned __int16)v6;
  if ( !(_WORD)v6 )
    v8 = 6;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_fd76d537424c3f213087d14e42e29f74_Traceguids, *a6, v8);
  return v8;
}

```

## disassembly

```asm
0x140001e20  push    rbx
0x140001e22  sub     rsp, 60h
0x140001e26  mov     r11, rcx
0x140001e29  mov     rcx, cs:?s_pVirtualSingleton@ComTaskMgrBase@@0PEAV1@EA; ComTaskMgrBase * ComTaskMgrBase::s_pVirtualSingleton
0x140001e30  mov     rax, [rcx]
0x140001e33  mov     r10, [rsp+68h+arg_28]
0x140001e3b  mov     [rsp+68h+var_38], r10
0x140001e40  mov     r10d, [rsp+68h+arg_20]
0x140001e48  mov     [rsp+68h+var_40], r10d
0x140001e4d  mov     [rsp+68h+var_48], r9d
0x140001e52  mov     r9, r8
0x140001e55  mov     r8, rdx
0x140001e58  mov     rdx, r11
0x140001e5b  mov     rax, [rax]
0x140001e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e63  nop
0x140001e64  test    eax, eax
0x140001e66  js      short loc_140001E9B
0x140001e68  xor     eax, eax
0x140001e6a  add     rsp, 60h
0x140001e6e  pop     rbx
0x140001e6f  retn
0x140001e70  jmp     short loc_140001E95
0x140001e72  mov     ebx, 0Eh
0x140001e77  jmp     short loc_140001EA8
0x140001e79  mov     ebx, 57h ; 'W'
0x140001e7e  jmp     short loc_140001EA8
0x140001e80  mov     ebx, 57h ; 'W'
0x140001e85  jmp     short loc_140001EA8
0x140001e87  mov     ebx, 57h ; 'W'
0x140001e8c  jmp     short loc_140001EA8
0x140001e8e  mov     ebx, 4005h
0x140001e93  jmp     short loc_140001EA8
0x140001e95  mov     eax, [rsp+68h+var_28]
0x140001e99  jmp     short loc_140001E64
0x140001e9b  movzx   ebx, ax
0x140001e9e  mov     eax, 6
0x140001ea3  test    ebx, ebx
0x140001ea5  cmovz   ebx, eax
0x140001ea8  lea     rax, WPP_GLOBAL_Control
0x140001eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x140001eb6  cmp     rcx, rax
0x140001eb9  jz      short loc_140001EE5
0x140001ebb  test    byte ptr [rcx+1Ch], 1
0x140001ebf  jz      short loc_140001EE5
0x140001ec1  mov     edx, 0Eh
0x140001ec6  mov     [rsp+68h+var_48], ebx
0x140001eca  mov     r9, [rsp+68h+arg_28]
0x140001ed2  mov     r9, [r9]
0x140001ed5  lea     r8, WPP_fd76d537424c3f213087d14e42e29f74_Traceguids
0x140001edc  mov     rcx, [rcx+10h]
0x140001ee0  call    WPP_SF_qd
0x140001ee5  mov     eax, ebx
0x140001ee7  jmp     short loc_140001E6A
```
